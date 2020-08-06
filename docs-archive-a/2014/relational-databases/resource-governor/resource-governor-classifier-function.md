---
title: Fonction classifieur de Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function
- user-defined functions [SQL Server], classifier function
- classifier function [SQL Server]
- classifier function [SQL Server], overview
ms.assetid: 64c25012-7068-476f-afa2-0b4f3adde9a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69b6fd10ac0adc6f76925e0d41f110b917111466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699389"
---
# <a name="resource-governor-classifier-function"></a><span data-ttu-id="e6a98-102">Fonction classifieur du gouverneur de ressources</span><span class="sxs-lookup"><span data-stu-id="e6a98-102">Resource Governor Classifier Function</span></span>
  <span data-ttu-id="e6a98-103">Le processus de classification de Resource Governor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affecte les sessions entrantes à un groupe de charge de travail en fonction des caractéristiques de la session.</span><span class="sxs-lookup"><span data-stu-id="e6a98-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource governor classification process assigns incoming sessions to a workload group based on the characteristics of the session.</span></span> <span data-ttu-id="e6a98-104">Vous pouvez adapter la logique de classification en entrant une fonction définie par l'utilisateur, appelée fonction classifieur.</span><span class="sxs-lookup"><span data-stu-id="e6a98-104">You can tailor the classification logic by writing a user-defined function, called a classifier function.</span></span>  
  
## <a name="classification"></a><span data-ttu-id="e6a98-105">classification ;</span><span class="sxs-lookup"><span data-stu-id="e6a98-105">Classification</span></span>  
 <span data-ttu-id="e6a98-106">Resource Governor prend en charge la classification des sessions entrantes.</span><span class="sxs-lookup"><span data-stu-id="e6a98-106">Resource Governor supports the classification of incoming sessions.</span></span> <span data-ttu-id="e6a98-107">La classification est basée sur un jeu de critères écrits par l'utilisateur et contenus dans une fonction.</span><span class="sxs-lookup"><span data-stu-id="e6a98-107">Classification is based on a set of user-written criteria contained in a function.</span></span> <span data-ttu-id="e6a98-108">Les résultats de la logique de la fonction permettent à Resource Governor de classer des sessions en groupes de charges de travail existants.</span><span class="sxs-lookup"><span data-stu-id="e6a98-108">The results of the function logic enable Resource Governor to classify sessions into existing workload groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6a98-109">Le groupe de charges de travail interne est rempli avec les demandes destinées à un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="e6a98-109">The internal workload group is populated with requests that are for internal use only.</span></span> <span data-ttu-id="e6a98-110">Vous ne pouvez pas modifier les critères utilisés pour acheminer ces demandes et vous ne pouvez pas classer de demandes dans le groupe de charges de travail interne.</span><span class="sxs-lookup"><span data-stu-id="e6a98-110">You cannot change the criteria used for routing these requests and you cannot classify requests into the internal workload group.</span></span>  
  
 <span data-ttu-id="e6a98-111">Vous pouvez écrire une fonction scalaire qui contient la logique utilisée pour assigner des sessions entrantes à un groupe de charges de travail.</span><span class="sxs-lookup"><span data-stu-id="e6a98-111">You can write a scalar function that contains the logic that is used to assign incoming sessions to a workload group.</span></span> <span data-ttu-id="e6a98-112">Avant de pouvoir utiliser cette fonction, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e6a98-112">Before you can use this function, you must complete the following actions:</span></span>  
  
-   <span data-ttu-id="e6a98-113">Créer et enregistrer la fonction à l'aide de l'instruction ALTER RESOURCE GOVERNOR.</span><span class="sxs-lookup"><span data-stu-id="e6a98-113">Create and register the function using the ALTER RESOURCE GOVERNOR statement.</span></span> <span data-ttu-id="e6a98-114">Pour plus d’informations, consultez [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e6a98-114">For more information, see [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span></span>  
  
-   <span data-ttu-id="e6a98-115">Mettre à jour la configuration de Resource Governor à l'aide de l'instruction ALTER RESOURCE GOVERNOR avec le paramètre RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="e6a98-115">Update the Resource Governor configuration using the ALTER RESOURCE GOVERNOR statement with the RECONFIGURE parameter.</span></span>  
  
 <span data-ttu-id="e6a98-116">Une fois la fonction créé et les modifications de configuration appliquées, le classifieur de Resource Governor utilise le nom du groupe de charges de travail retourné par la fonction pour envoyer une nouvelle demande au groupe de charge de travail approprié.</span><span class="sxs-lookup"><span data-stu-id="e6a98-116">After you create the function and apply the configuration changes, the Resource Governor classifier will use the workload group name returned by the function to send a new request to the appropriate workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e6a98-117">La session cliente peut expirer si la fonction de classification ne se termine pas dans le délai d'attente spécifié pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="e6a98-117">The client session may time out if the classification function does not complete within the specified time-out for the login.</span></span> <span data-ttu-id="e6a98-118">Le délai d'attente de connexion est une propriété cliente et à ce titre, le serveur n'en a pas connaissance. Une fonction classifieur de longue durée peut entraîner des connexions orphelines au niveau du serveur pendant de longues périodes.</span><span class="sxs-lookup"><span data-stu-id="e6a98-118">Login time-out is a client property and as such, the server is unaware of a time-out. A long-running classifier function can leave the server with orphaned connections for long periods.</span></span> <span data-ttu-id="e6a98-119">Il est important de créer des fonctions classifieur dont l'exécution se termine avant l'expiration d'un délai de connexion.</span><span class="sxs-lookup"><span data-stu-id="e6a98-119">It is important that you create classifier functions that finish executing before a connection time-out.</span></span>  
  
 <span data-ttu-id="e6a98-120">La fonction définie par l'utilisateur a les caractéristiques et les comportements suivants :</span><span class="sxs-lookup"><span data-stu-id="e6a98-120">The user-defined function has the following characteristics and behaviors:</span></span>  
  
-   <span data-ttu-id="e6a98-121">La fonction définie par l'utilisateur est évaluée pour chaque nouvelle session, même lorsque le regroupement de connexions est activé.</span><span class="sxs-lookup"><span data-stu-id="e6a98-121">The user-defined function is evaluated for every new session, even when connection pooling is enabled.</span></span>  
  
-   <span data-ttu-id="e6a98-122">La fonction définie par l'utilisateur donne le contexte de groupe de charges de travail pour la session.</span><span class="sxs-lookup"><span data-stu-id="e6a98-122">The user-defined function gives workload group context for the session.</span></span> <span data-ttu-id="e6a98-123">Une fois l'appartenance aux groupes déterminée, la session est liée au groupe de charges de travail pour la durée de la session.</span><span class="sxs-lookup"><span data-stu-id="e6a98-123">After group membership is determined, the session is bound to the workload group for the lifetime of the session.</span></span>  
  
-   <span data-ttu-id="e6a98-124">Si la fonction définie par l'utilisateur retourne NULL, la valeur par défaut ou le nom de groupe inexistant, elle se voit attribuer le contexte de groupe de charges de travail par défaut.</span><span class="sxs-lookup"><span data-stu-id="e6a98-124">If the user-defined function returns NULL, default, or the name of non-existent group the session is given the default workload group context.</span></span> <span data-ttu-id="e6a98-125">La session se voit attribuer aussi le contexte par défaut si la fonction échoue pour une raison donnée.</span><span class="sxs-lookup"><span data-stu-id="e6a98-125">The session is also given the default context if the function fails for any reason.</span></span>  
  
-   <span data-ttu-id="e6a98-126">La fonction doit être définie avec une étendue de serveur (base de données master).</span><span class="sxs-lookup"><span data-stu-id="e6a98-126">The function should be defined with server scope (master database).</span></span>  
  
-   <span data-ttu-id="e6a98-127">La désignation de la fonction classifieur définie par l'utilisateur entre seulement en vigueur après l'exécution de l'instruction ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="e6a98-127">The classifier user-defined function designation only takes effect after ALTER RESOURCE GOVERNOR RECONFIGURE is executed.</span></span>  
  
-   <span data-ttu-id="e6a98-128">Une seule fonction définie par l'utilisateur peut être désignée à la fois comme classifieur.</span><span class="sxs-lookup"><span data-stu-id="e6a98-128">Only one user-defined function can be designated as a classifier at a time.</span></span>  
  
-   <span data-ttu-id="e6a98-129">La fonction classifieur définie par l'utilisateur ne peut pas être supprimée ou modifiée sauf si son état classifieur est supprimé.</span><span class="sxs-lookup"><span data-stu-id="e6a98-129">The classifier user-defined function cannot be dropped or altered unless its classifier status is removed.</span></span>  
  
-   <span data-ttu-id="e6a98-130">En l'absence d'une fonction classifieur définie par l'utilisateur, toutes les sessions sont classifiées dans le groupe par défaut.</span><span class="sxs-lookup"><span data-stu-id="e6a98-130">In the absence of a classifier user-defined function, all sessions are classified into the default group.</span></span>  
  
-   <span data-ttu-id="e6a98-131">Le groupe de charges de travail retourné par la fonction classifieur est hors de la portée de la restriction de liaison du schéma.</span><span class="sxs-lookup"><span data-stu-id="e6a98-131">The workload group returned by the classifier function is outside the scope of the schema-binding restriction.</span></span> <span data-ttu-id="e6a98-132">Par exemple, vous ne pouvez pas supprimer une table mais vous pouvez supprimer un groupe de charges de travail.</span><span class="sxs-lookup"><span data-stu-id="e6a98-132">For example, you cannot drop a table, but you can drop a workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e6a98-133">L'activation de la connexion administrateur dédiée (DAC) sur le serveur est conseillée.</span><span class="sxs-lookup"><span data-stu-id="e6a98-133">We recommend enabling the Dedicated Administrator Connection (DAC) on the server.</span></span> <span data-ttu-id="e6a98-134">La connexion administrateur dédiée n'est pas soumise à la classification de Resource Governor et peut être utilisée pour surveiller et dépanner une fonction classifieur.</span><span class="sxs-lookup"><span data-stu-id="e6a98-134">The DAC is not subject to Resource Governor classification and can be used to monitor and troubleshoot a classifier function.</span></span> <span data-ttu-id="e6a98-135">Pour plus d’informations, consultez [Connexion de diagnostic pour les administrateurs de base de données](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="e6a98-135">For more information, see [Diagnostic Connection for Database Administrators](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span></span> <span data-ttu-id="e6a98-136">L'autre solution, lorsqu'une connexion administrateur dédiée n'est pas disponible pour la résolution des problèmes, consiste à redémarrer le système en mode mono-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e6a98-136">If a DAC is not available for troubleshooting, the other option is to restart the system in single user mode.</span></span> <span data-ttu-id="e6a98-137">Le mode mono-utilisateur n'est pas sujet à la classification ; toutefois, il ne vous permet pas d'effectuer un diagnostic de la classification de Resource Governor s'il est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e6a98-137">Although single user mode is not subject to classification, it does not give you the ability to diagnose Resource Governor classification while it is running.</span></span>  
  
### <a name="classification-process"></a><span data-ttu-id="e6a98-138">Processus de classification</span><span class="sxs-lookup"><span data-stu-id="e6a98-138">Classification Process</span></span>  
 <span data-ttu-id="e6a98-139">Dans le contexte de Resource Governor, le processus de connexion pour une session comprend les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e6a98-139">In the context of Resource Governor, the login process for a session consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="e6a98-140">authentification des connexions ;</span><span class="sxs-lookup"><span data-stu-id="e6a98-140">Login authentication</span></span>  
  
2.  <span data-ttu-id="e6a98-141">exécution des déclencheurs LOGON ;</span><span class="sxs-lookup"><span data-stu-id="e6a98-141">LOGON trigger execution</span></span>  
  
3.  <span data-ttu-id="e6a98-142">classification ;</span><span class="sxs-lookup"><span data-stu-id="e6a98-142">Classification</span></span>  
  
 <span data-ttu-id="e6a98-143">Lorsque la classification commence, Resource Governor exécute la fonction classifieur et utilise la valeur retournée par la fonction pour envoyer des demandes au groupe de charges de travail approprié.</span><span class="sxs-lookup"><span data-stu-id="e6a98-143">When classification starts, Resource Governor executes the classifier function and uses the value returned by the function to send requests to the appropriate workload group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6a98-144">Les informations relatives à l’exécution de la fonction classifieur et des déclencheurs LOGON sont exposées dans [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) et [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e6a98-144">Information about the execution of the classifier function and LOGON triggers is exposed in [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span></span>  
  
## <a name="classification-function-tasks"></a><span data-ttu-id="e6a98-145">Tâches de fonction de classification</span><span class="sxs-lookup"><span data-stu-id="e6a98-145">Classification Function Tasks</span></span>  
  
|<span data-ttu-id="e6a98-146">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="e6a98-146">Task Description</span></span>|<span data-ttu-id="e6a98-147">Rubrique</span><span class="sxs-lookup"><span data-stu-id="e6a98-147">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="e6a98-148">Décrit comment créer et tester une fonction définie par l'utilisateur classifieur.</span><span class="sxs-lookup"><span data-stu-id="e6a98-148">Describes how to create and test a classifier user-defined function.</span></span>|[<span data-ttu-id="e6a98-149">Créer et tester une fonction classifieur définie par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="e6a98-149">Create and Test a Classifier User-Defined Function</span></span>](create-and-test-a-classifier-user-defined-function.md)|  
  
## <a name="see-also"></a><span data-ttu-id="e6a98-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6a98-150">See Also</span></span>  
 <span data-ttu-id="e6a98-151">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="e6a98-151">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="e6a98-152">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="e6a98-152">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="e6a98-153">[Pool de ressources de Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="e6a98-153">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="e6a98-154">[Groupe de charge de travail de Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="e6a98-154">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="e6a98-155">[Configurer le gouverneur de ressources à l'aide d'un modèle](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="e6a98-155">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="e6a98-156">Afficher les propriétés du gouverneur de ressources</span><span class="sxs-lookup"><span data-stu-id="e6a98-156">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
