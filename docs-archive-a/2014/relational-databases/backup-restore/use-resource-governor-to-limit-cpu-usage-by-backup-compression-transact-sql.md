---
title: Utiliser Resource Governor pour limiter l’utilisation de l’UC par compression de la sauvegarde (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup compression [SQL Server], Resource Governor
- backup compression [SQL Server], CPU usage
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- Resource Governor, backup compression
ms.assetid: 01796551-578d-4425-9b9e-d87210f7ba72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19a95cfa5c6780fbdf71ae58bd141aa9aa351efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709672"
---
# <a name="use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql"></a><span data-ttu-id="0cec5-102">Utiliser le gouverneur de ressources pour limiter l'utilisation de l'UC par compression de sauvegarde (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0cec5-102">Use Resource Governor to Limit CPU Usage by Backup Compression (Transact-SQL)</span></span>
  <span data-ttu-id="0cec5-103">Par défaut, sauvegarder en utilisant la compression augmente considérablement l'utilisation de l'UC et l'UC supplémentaire consommée par le processus de compression peut nuire aux opérations simultanées.</span><span class="sxs-lookup"><span data-stu-id="0cec5-103">By default, backing up using compression significantly increases CPU usage, and the additional CPU consumed by the compression process can adversely impact concurrent operations.</span></span> <span data-ttu-id="0cec5-104">Ainsi, il peut être préférable, dans une session où l’utilisation du processeur est limitée, de créer une sauvegarde compressée de priorité basse à l’aide de[Resource Governor](../resource-governor/resource-governor.md) en cas de contention du processeur.</span><span class="sxs-lookup"><span data-stu-id="0cec5-104">Therefore, you might want to create a low-priority compressed backup in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md) when CPU contention occurs.</span></span> <span data-ttu-id="0cec5-105">Cette rubrique présente un scénario qui classifie les sessions d'un utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] particulier en les mappant à un groupe de charge de travail de Resource Governor qui limite l'utilisation de l'UC dans de tels cas.</span><span class="sxs-lookup"><span data-stu-id="0cec5-105">This topic presents a scenario that classifies the sessions of a particular [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user by mapping them to a Resource Governor workload group that limits CPU usage in such cases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0cec5-106">Dans un scénario donné de Resource Governor, la classification des sessions peut être basée sur un nom d'utilisateur, un nom d'application ou tout autre élément permettant d'identifier une connexion.</span><span class="sxs-lookup"><span data-stu-id="0cec5-106">In a given Resource Governor scenario, session classification might be based on a user name, an application name, or anything else that can differentiate a connection.</span></span> <span data-ttu-id="0cec5-107">Pour plus d'informations, consultez [Fonction classifieur de Resource Governor](../resource-governor/resource-governor-classifier-function.md) et [Groupe de charge de travail de Resource Governor](../resource-governor/resource-governor-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="0cec5-107">For more information, see [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) and [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span></span>  
  
##  <a name="this-topic-contains-the-following-set-of-scenarios-which-are-presented-in-sequence"></a><a name="Top"></a> <span data-ttu-id="0cec5-108">Cette rubrique propose les scénarios suivants, présentés dans l'ordre :</span><span class="sxs-lookup"><span data-stu-id="0cec5-108">This topic contains the following set of scenarios, which are presented in sequence:</span></span>  
  
1.  [<span data-ttu-id="0cec5-109">Configuration d'une connexion et d'un utilisateur pour les opérations de priorité basse</span><span class="sxs-lookup"><span data-stu-id="0cec5-109">Setting Up a Login and User for Low-Priority Operations</span></span>](#setup_login_and_user)  
  
2.  [<span data-ttu-id="0cec5-110">Configuration de Resource Governor pour limiter l'utilisation de l'UC</span><span class="sxs-lookup"><span data-stu-id="0cec5-110">Configuring Resource Governor to Limit CPU Usage</span></span>](#configure_RG)  
  
3.  [<span data-ttu-id="0cec5-111">Vérification de la classification de la session active (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0cec5-111">Verifying the Classification of the Current Session (Transact-SQL)</span></span>](#verifying)  
  
4.  [<span data-ttu-id="0cec5-112">Compression de sauvegardes dans une session à utilisation maximale de l'UC limitée</span><span class="sxs-lookup"><span data-stu-id="0cec5-112">Compressing Backups Using a Session with Limited CPU</span></span>](#creating_compressed_backup)  
  
##  <a name="setting-up-a-login-and-user-for-low-priority-operations"></a><a name="setup_login_and_user"></a> <span data-ttu-id="0cec5-113">Configuration d'une connexion et d'un utilisateur pour les opérations de priorité basse</span><span class="sxs-lookup"><span data-stu-id="0cec5-113">Setting Up a Login and User for Low-Priority Operations</span></span>  
 <span data-ttu-id="0cec5-114">Le scénario de cette rubrique requiert une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de priorité basse et un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0cec5-114">The scenario in this topic requires a low-priority [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user.</span></span> <span data-ttu-id="0cec5-115">Le nom d'utilisateur sera utilisé pour classifier des sessions exécutées dans la connexion et pour les router vers un groupe de charge de travail de Resource Governor qui limite l'utilisation de l'UC.</span><span class="sxs-lookup"><span data-stu-id="0cec5-115">The user name will be used to classify sessions running in the login and route them to a Resource Governor workload group that limits CPU usage.</span></span>  
  
 <span data-ttu-id="0cec5-116">La procédure ci-dessous décrit les étapes nécessaires à la configuration d’une connexion et d’un utilisateur à cette fin. Elle est suivie d’un exemple [!INCLUDE[tsql](../../includes/tsql-md.md)], « Exemple A : configuration d’une connexion et d’un utilisateur (Transact-SQL) ».</span><span class="sxs-lookup"><span data-stu-id="0cec5-116">The following procedure describes the steps for setting up a login and user for this purpose, followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example, "Example A: Setting Up a Login and User (Transact-SQL)."</span></span>  
  
### <a name="to-set-up-a-login-and-database-user-for-classifying-sessions"></a><span data-ttu-id="0cec5-117">Pour configurer une connexion et un utilisateur de base de données afin de classifier des sessions</span><span class="sxs-lookup"><span data-stu-id="0cec5-117">To set up a login and database user for classifying sessions</span></span>  
  
1.  <span data-ttu-id="0cec5-118">Créez une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour créer des sauvegardes compressées de priorité basse.</span><span class="sxs-lookup"><span data-stu-id="0cec5-118">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login for creating low-priority compressed backups.</span></span>  
  
     <span data-ttu-id="0cec5-119">**Pour créer une connexion**</span><span class="sxs-lookup"><span data-stu-id="0cec5-119">**To create a login**</span></span>  
  
    -   [<span data-ttu-id="0cec5-120">Créer un compte de connexion</span><span class="sxs-lookup"><span data-stu-id="0cec5-120">Create a Login</span></span>](../security/authentication-access/create-a-login.md)  
  
    -   [<span data-ttu-id="0cec5-121">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0cec5-121">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
2.  <span data-ttu-id="0cec5-122">Accordez éventuellement à cette connexion l'autorisation VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="0cec5-122">Optionally, grant VIEW SERVER STATE to this login.</span></span>  
  
    -   [<span data-ttu-id="0cec5-123">GRANT – octroi d’autorisations d’objet système &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0cec5-123">GRANT System Object Permissions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-system-object-permissions-transact-sql)  
  
     <span data-ttu-id="0cec5-124">Pour plus d’informations, consultez [GRANT – octroi d’autorisations de principal de base de données &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0cec5-124">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
3.  <span data-ttu-id="0cec5-125">Créez un utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour cette connexion.</span><span class="sxs-lookup"><span data-stu-id="0cec5-125">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user for this login.</span></span>  
  
     <span data-ttu-id="0cec5-126">**Pour créer un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="0cec5-126">**To create a user**</span></span>  
  
    -   [<span data-ttu-id="0cec5-127">Créer un utilisateur de base de données</span><span class="sxs-lookup"><span data-stu-id="0cec5-127">Create a Database User</span></span>](../security/authentication-access/create-a-database-user.md)  
  
    -   [<span data-ttu-id="0cec5-128">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0cec5-128">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
4.  <span data-ttu-id="0cec5-129">Pour permettre aux sessions de cette connexion et cet utilisateur de sauvegarder une base de données spécifique, ajoutez l'utilisateur au rôle de base de données db_backupoperator de cette base de données.</span><span class="sxs-lookup"><span data-stu-id="0cec5-129">To enable sessions of this login and user to back up a given database, add the user to the db_backupoperator database role of that database.</span></span> <span data-ttu-id="0cec5-130">Répétez l'opération pour chaque base de données que cet utilisateur doit sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="0cec5-130">Do this for each database that this user will back up.</span></span> <span data-ttu-id="0cec5-131">Ajoutez éventuellement l'utilisateur à d'autres rôles de base de données fixes.</span><span class="sxs-lookup"><span data-stu-id="0cec5-131">Optionally, add the user to other fixed database roles.</span></span>  
  
     <span data-ttu-id="0cec5-132">**Pour ajouter un utilisateur de base de données à un rôle de base de données fixe**</span><span class="sxs-lookup"><span data-stu-id="0cec5-132">**To add a user to a fixed database role**</span></span>  
  
    -   [<span data-ttu-id="0cec5-133">sp_addrolemember &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0cec5-133">sp_addrolemember &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql)  
  
     <span data-ttu-id="0cec5-134">Pour plus d’informations, consultez [GRANT – octroi d’autorisations de principal de base de données &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0cec5-134">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
### <a name="example-a-setting-up-a-login-and-user-transact-sql"></a><span data-ttu-id="0cec5-135">Exemple A : configuration d’une connexion et d’un utilisateur (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0cec5-135">Example A: Setting Up a Login and User (Transact-SQL)</span></span>  
 <span data-ttu-id="0cec5-136">L'exemple ci-dessous est pertinent uniquement si vous choisissez de créer une connexion et un utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour des sauvegardes de priorité basse.</span><span class="sxs-lookup"><span data-stu-id="0cec5-136">The following example is relevant only if you choose to create a new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user for low-priority backups.</span></span> <span data-ttu-id="0cec5-137">Vous avez également la possibilité d'utiliser une connexion et un utilisateur existants, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="0cec5-137">Alternatively, you can use an existing login and user, if an appropriate one exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0cec5-138">L’exemple ci-dessous utilise un exemple de connexion et de nom d’utilisateur, *domaine_nom*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="0cec5-138">The following example uses a sample login and user name, *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="0cec5-139">Remplacez-le par les noms de la connexion et de l'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous projetez d'utiliser lors de la création de vos sauvegardes compressées de priorité basse.</span><span class="sxs-lookup"><span data-stu-id="0cec5-139">Replace these with the names of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user that you plan to use when creating your low-priority compressed backups.</span></span>  
  
 <span data-ttu-id="0cec5-140">Cet exemple crée une connexion pour le compte Windows *domaine_nom*`\MAX_CPU` , puis accorde l’autorisation VIEW SERVER STATE à la connexion.</span><span class="sxs-lookup"><span data-stu-id="0cec5-140">This example creates a login for the *domain_name*`\MAX_CPU` Windows account and then grants VIEW SERVER STATE permission to the login.</span></span> <span data-ttu-id="0cec5-141">Cette autorisation vous permet de vérifier la classification de Resource Governor pour les sessions de la connexion.</span><span class="sxs-lookup"><span data-stu-id="0cec5-141">This permission enables you to verify the Resource Governor classification of sessions of the login.</span></span> <span data-ttu-id="0cec5-142">L’exemple crée ensuite un utilisateur pour *domaine_nom*`\MAX_CPU` et l’ajoute au rôle de base de données fixe db_backupoperator pour l’exemple de base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cec5-142">The example then creates a user for *domain_name*`\MAX_CPU` and adds it to the db_backupoperator fixed database role for the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="0cec5-143">Ce nom d'utilisateur sera utilisé par la fonction classifieur de Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="0cec5-143">This user name will be used by the Resource Governor classifier function.</span></span>  
  
```sql  
-- Create a SQL Server login for low-priority operations  
USE master;  
CREATE LOGIN [domain_name\MAX_CPU] FROM WINDOWS;  
GRANT VIEW SERVER STATE TO [domain_name\MAX_CPU];  
GO  
-- Create a SQL Server user in AdventureWorks2012 for this login  
USE AdventureWorks2012;  
CREATE USER [domain_name\MAX_CPU] FOR LOGIN [domain_name\MAX_CPU];  
EXEC sp_addrolemember 'db_backupoperator', 'domain_name\MAX_CPU';  
GO  
  
```  
  
 [<span data-ttu-id="0cec5-144">&#91;Haut&#93;</span><span class="sxs-lookup"><span data-stu-id="0cec5-144">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="configuring-resource-governor-to-limit-cpu-usage"></a><a name="configure_RG"></a> <span data-ttu-id="0cec5-145">Configuration de Resource Governor pour limiter l'utilisation de l'UC</span><span class="sxs-lookup"><span data-stu-id="0cec5-145">Configuring Resource Governor to Limit CPU Usage</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0cec5-146">Vérifiez que Resource Governor est activé.</span><span class="sxs-lookup"><span data-stu-id="0cec5-146">Ensure that Resource Governor is enabled.</span></span> <span data-ttu-id="0cec5-147">Pour plus d’informations, consultez [Activer Resource Governor](../resource-governor/enable-resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="0cec5-147">For more information, see [Enable Resource Governor](../resource-governor/enable-resource-governor.md).</span></span>  
  
 <span data-ttu-id="0cec5-148">Dans ce scénario de Resource Governor, la configuration comprend les étapes de base indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="0cec5-148">In this Resource Governor scenario, configuration comprises the following basic steps:</span></span>  
  
1.  <span data-ttu-id="0cec5-149">Création et configuration d'un pool de ressources de Resource Governor limitant la bande passante processeur moyenne maximale qui sera allouée aux demandes dans le pool de ressources en cas de contention du processeur.</span><span class="sxs-lookup"><span data-stu-id="0cec5-149">Create and configure a Resource Governor resource pool that limits the maximum average CPU bandwidth that will be given to requests in the resource pool when CPU contention occurs.</span></span>  
  
2.  <span data-ttu-id="0cec5-150">Création et configuration d'un groupe de charge de travail de Resource Governor qui utilise ce pool.</span><span class="sxs-lookup"><span data-stu-id="0cec5-150">Create and configure a Resource Governor workload group that uses this pool.</span></span>  
  
3.  <span data-ttu-id="0cec5-151">Création d’une *fonction classifieur*, qui est une fonction définie par l’utilisateur et dont les valeurs de retour sont utilisées par Resource Governor pour classifier des sessions pour qu’elles soient routées vers le groupe de charge de travail approprié.</span><span class="sxs-lookup"><span data-stu-id="0cec5-151">Create a *classifier function*, which is a user-defined function (UDF) whose return values are used by Resource Governor for classifying sessions so that they are routed to the appropriate workload group.</span></span>  
  
4.  <span data-ttu-id="0cec5-152">Inscription de la fonction classifieur auprès de Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="0cec5-152">Register the classifier function with Resource Governor.</span></span>  
  
5.  <span data-ttu-id="0cec5-153">Application des modifications à la configuration en mémoire de Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="0cec5-153">Apply the changes to the Resource Governor in-memory configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0cec5-154">Pour plus d’informations sur les pools de ressources, les groupes de charge de travail et la classification de Resource Governor, consultez [Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="0cec5-154">For information about Resource Governor resource pools, workload groups, and classification, see [Resource Governor](../resource-governor/resource-governor.md).</span></span>  
  
 <span data-ttu-id="0cec5-155">Les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] pour ces étapes sont décrites dans la procédure « Pour configurer Resource Governor afin de limiter l'utilisation de l'UC » qui est suivie d'un exemple [!INCLUDE[tsql](../../includes/tsql-md.md)] de la procédure.</span><span class="sxs-lookup"><span data-stu-id="0cec5-155">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for these steps are described in the procedure, "To configure Resource Governor for limiting CPU usage," which is followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of the procedure.</span></span>  
  
 <span data-ttu-id="0cec5-156">**Pour configurer Resource Governor (SQL Server Management Studio)**</span><span class="sxs-lookup"><span data-stu-id="0cec5-156">**To configure Resource Governor (SQL Server Management Studio)**</span></span>  
  
-   [<span data-ttu-id="0cec5-157">Configurer Resource Governor à l’aide d’un modèle</span><span class="sxs-lookup"><span data-stu-id="0cec5-157">Configure Resource Governor Using a Template</span></span>](../resource-governor/configure-resource-governor-using-a-template.md)  
  
-   [<span data-ttu-id="0cec5-158">Créer un pool de ressources</span><span class="sxs-lookup"><span data-stu-id="0cec5-158">Create a Resource Pool</span></span>](../resource-governor/create-a-resource-pool.md)  
  
-   [<span data-ttu-id="0cec5-159">Créer un groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="0cec5-159">Create a Workload Group</span></span>](../resource-governor/create-a-workload-group.md)  
  
### <a name="to-configure-resource-governor-for-limiting-cpu-usage-transact-sql"></a><span data-ttu-id="0cec5-160">Pour configurer Resource Governor afin de limiter l'utilisation de l'UC (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0cec5-160">To configure Resource Governor for limiting CPU usage (Transact-SQL)</span></span>  
  
1.  <span data-ttu-id="0cec5-161">Émettez une instruction [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) pour créer un pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="0cec5-161">Issue a [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) statement to create a resource pool.</span></span> <span data-ttu-id="0cec5-162">L'exemple de cette procédure utilise la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="0cec5-162">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="0cec5-163">*CREATE RESOURCE POOL nom_du_pool* WITH ( MAX_CPU_PERCENT = *valeur* );</span><span class="sxs-lookup"><span data-stu-id="0cec5-163">*CREATE RESOURCE POOL pool_name* WITH ( MAX_CPU_PERCENT = *value* );</span></span>  
  
     <span data-ttu-id="0cec5-164">*Value* est un entier de 1 à 100 qui indique le pourcentage de bande passante processeur moyenne maximale.</span><span class="sxs-lookup"><span data-stu-id="0cec5-164">*Value* is an integer from 1 to 100 that indicates the percentage of maximum average CPU bandwidth.</span></span> <span data-ttu-id="0cec5-165">La valeur appropriée dépend de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="0cec5-165">The appropriate value depends on your environment.</span></span> <span data-ttu-id="0cec5-166">À des fins d'illustration, l'exemple de cette rubrique utilise 20 % (MAX_CPU_PERCENT = 20.)</span><span class="sxs-lookup"><span data-stu-id="0cec5-166">For the purpose of illustration, the example in this topic uses 20%  percent (MAX_CPU_PERCENT = 20.)</span></span>  
  
2.  <span data-ttu-id="0cec5-167">Émettez une instruction [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) pour créer un groupe de charge de travail pour les opérations de priorité basse dont vous souhaitez régir l’utilisation de l’UC.</span><span class="sxs-lookup"><span data-stu-id="0cec5-167">Issue a [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) statement to create a workload group for low-priority operations whose CPU usage you want to govern.</span></span> <span data-ttu-id="0cec5-168">L'exemple de cette procédure utilise la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="0cec5-168">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="0cec5-169">CREATE WORKLOAD GROUP *nom_du_groupe* USING *nom_du_pool*;</span><span class="sxs-lookup"><span data-stu-id="0cec5-169">CREATE WORKLOAD GROUP *group_name* USING *pool_name*;</span></span>  
  
3.  <span data-ttu-id="0cec5-170">Émettez une instruction [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) pour créer une fonction classifieur qui mappe le groupe de charge de travail créé à l’étape précédente à l’utilisateur de la connexion de priorité basse.</span><span class="sxs-lookup"><span data-stu-id="0cec5-170">Issue a [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) statement to create a classifier function that maps the workload group created in the preceding step to the user of the low-priority login.</span></span> <span data-ttu-id="0cec5-171">L'exemple de cette procédure utilise la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="0cec5-171">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="0cec5-172">CREATE FUNCTION [*nom_de_schéma*.]*nom_de_fonction*() RETURNS sysname</span><span class="sxs-lookup"><span data-stu-id="0cec5-172">CREATE FUNCTION [*schema_name*.]*function_name*() RETURNS sysname</span></span>  
  
     <span data-ttu-id="0cec5-173">WITH SCHEMABINDING</span><span class="sxs-lookup"><span data-stu-id="0cec5-173">WITH SCHEMABINDING</span></span>  
  
     <span data-ttu-id="0cec5-174">AS</span><span class="sxs-lookup"><span data-stu-id="0cec5-174">AS</span></span>  
  
     <span data-ttu-id="0cec5-175">BEGIN</span><span class="sxs-lookup"><span data-stu-id="0cec5-175">BEGIN</span></span>  
  
     <span data-ttu-id="0cec5-176">DECLARE @workload_group_name AS *sysname*</span><span class="sxs-lookup"><span data-stu-id="0cec5-176">DECLARE @workload_group_name AS *sysname*</span></span>  
  
     <span data-ttu-id="0cec5-177">IF (SUSER_NAME() = '*utilisateur_de_connexion_faible_priorité*')</span><span class="sxs-lookup"><span data-stu-id="0cec5-177">IF (SUSER_NAME() = '*user_of_low_priority_login*')</span></span>  
  
     <span data-ttu-id="0cec5-178">SET @workload_group_name = '*nom_groupe_charge_de_travail*'</span><span class="sxs-lookup"><span data-stu-id="0cec5-178">SET @workload_group_name = '*workload_group_name*'</span></span>  
  
     <span data-ttu-id="0cec5-179">RETURN @workload_group_name</span><span class="sxs-lookup"><span data-stu-id="0cec5-179">RETURN @workload_group_name</span></span>  
  
     <span data-ttu-id="0cec5-180">FIN</span><span class="sxs-lookup"><span data-stu-id="0cec5-180">END</span></span>  
  
     <span data-ttu-id="0cec5-181">Pour plus d'informations sur les composants de cette instruction CREATE FUNCTION, consultez :</span><span class="sxs-lookup"><span data-stu-id="0cec5-181">For information about the components of this CREATE FUNCTION statement, see:</span></span>  
  
    -   [<span data-ttu-id="0cec5-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0cec5-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
    -   [<span data-ttu-id="0cec5-183">SUSER_SNAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0cec5-183">SUSER_SNAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/suser-sname-transact-sql)  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="0cec5-184">SUSER_NAME est simplement l'une des fonctions système qui peuvent être utilisées dans une fonction classifieur.</span><span class="sxs-lookup"><span data-stu-id="0cec5-184">SUSER_NAME is just one of several system functions that can be used in a classifier function.</span></span> <span data-ttu-id="0cec5-185">Pour plus d’informations, consultez [Créer et tester une fonction classifieur définie par l’utilisateur](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span><span class="sxs-lookup"><span data-stu-id="0cec5-185">For more information, see [Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span></span>  
  
    -   <span data-ttu-id="0cec5-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0cec5-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span></span>  
  
4.  <span data-ttu-id="0cec5-187">Émettez une instruction [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) pour inscrire la fonction classifieur auprès de Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="0cec5-187">Issue an [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) statement to register the classifier function with Resource Governor.</span></span> <span data-ttu-id="0cec5-188">L'exemple de cette procédure utilise la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="0cec5-188">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="0cec5-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *nom_de_schéma*.*nom_de_fonction*);</span><span class="sxs-lookup"><span data-stu-id="0cec5-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *schema_name*.*function_name*);</span></span>  
  
5.  <span data-ttu-id="0cec5-190">Émettez une deuxième instruction ALTER RESOURCE GOVERNOR pour appliquer les modifications à la configuration en mémoire de Resource Governor, comme suit :</span><span class="sxs-lookup"><span data-stu-id="0cec5-190">Issue a second ALTER RESOURCE GOVERNOR statement to apply the changes to the Resource Governor in-memory configuration, as follows:</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE;  
    ```  
  
### <a name="example-b-configuring-resource-governor-transact-sql"></a><span data-ttu-id="0cec5-191">Exemple B : configuration de Resource Governor (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0cec5-191">Example B: Configuring Resource Governor (Transact-SQL)</span></span>  
 <span data-ttu-id="0cec5-192">L'exemple ci-dessous effectue les étapes qui suivent dans une transaction unique.</span><span class="sxs-lookup"><span data-stu-id="0cec5-192">The following example performs the following steps within a single transaction:</span></span>  
  
1.  <span data-ttu-id="0cec5-193">Il crée le pool de ressources `pMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="0cec5-193">Creates the `pMAX_CPU_PERCENT_20` resource pool.</span></span>  
  
2.  <span data-ttu-id="0cec5-194">Il crée le groupe de charge de travail `gMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="0cec5-194">Creates the `gMAX_CPU_PERCENT_20` workload group.</span></span>  
  
3.  <span data-ttu-id="0cec5-195">Il crée la fonction classifieur `rgclassifier_MAX_CPU()` , qui utilise le nom d'utilisateur créé à l'exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="0cec5-195">Creates the `rgclassifier_MAX_CPU()` classifier function, which uses the user name created in the preceding example.</span></span>  
  
4.  <span data-ttu-id="0cec5-196">Il inscrit la fonction classifieur auprès de Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="0cec5-196">Registers the classifier function with Resource Governor.</span></span>  
  
 <span data-ttu-id="0cec5-197">Après avoir validé la transaction, l'exemple applique les modifications de configuration demandées dans les instructions ALTER WORKLOAD GROUP ou ALTER RESOURCE POOL.</span><span class="sxs-lookup"><span data-stu-id="0cec5-197">After committing the transaction, the example applies the configuration changes requested in the ALTER WORKLOAD GROUP or ALTER RESOURCE POOL statements.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0cec5-198">L’exemple suivant utilise le nom d’utilisateur de l’exemple d’utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] créé dans « Exemple A : configuration d’une connexion et d’un utilisateur (Transact-SQL) », *nom_domaine*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="0cec5-198">The following example uses the user name of the sample [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user created in "Example A: Setting Up a Login and User (Transact-SQL)," *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="0cec5-199">Remplacez-le par le nom de l'utilisateur de la connexion que vous projetez d'utiliser pour créer les sauvegardes compressées de priorité basse.</span><span class="sxs-lookup"><span data-stu-id="0cec5-199">Replace this with the name of the user of the login that you plan to use for creating low-priority compressed backups.</span></span>  
  
```sql  
-- Configure Resource Governor.  
BEGIN TRAN  
USE master;  
-- Create a resource pool that sets the MAX_CPU_PERCENT to 20%.   
CREATE RESOURCE POOL pMAX_CPU_PERCENT_20  
   WITH  
      (MAX_CPU_PERCENT = 20);  
GO  
-- Create a workload group to use this pool.   
CREATE WORKLOAD GROUP gMAX_CPU_PERCENT_20  
USING pMAX_CPU_PERCENT_20;  
GO  
-- Create a classification function.  
-- Note that any request that does not get classified goes into   
-- the 'Default' group.  
CREATE FUNCTION dbo.rgclassifier_MAX_CPU() RETURNS sysname   
WITH SCHEMABINDING  
AS  
BEGIN  
    DECLARE @workload_group_name AS sysname  
      IF (SUSER_NAME() = 'domain_name\MAX_CPU')  
          SET @workload_group_name = 'gMAX_CPU_PERCENT_20'  
    RETURN @workload_group_name  
END;  
GO  
  
-- Register the classifier function with Resource Governor.  
ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION= dbo.rgclassifier_MAX_CPU);  
COMMIT TRAN;  
GO  
-- Start Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
  
```  
  
 [<span data-ttu-id="0cec5-200">&#91;Haut&#93;</span><span class="sxs-lookup"><span data-stu-id="0cec5-200">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="verifying-the-classification-of-the-current-session-transact-sql"></a><a name="verifying"></a> <span data-ttu-id="0cec5-201">Vérification de la classification de la session active (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0cec5-201">Verifying the Classification of the Current Session (Transact-SQL)</span></span>  
 <span data-ttu-id="0cec5-202">Éventuellement, connectez-vous en tant que l’utilisateur spécifié dans votre fonction classifieur et vérifiez la classification des sessions au moyen de l’instruction [SELECT](/sql/t-sql/queries/select-transact-sql) suivante dans l’Explorateur d’objets :</span><span class="sxs-lookup"><span data-stu-id="0cec5-202">Optionally, log in as the user that you specified in your classifier function, and verify the session classification by issuing the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement in Object Explorer:</span></span>  
  
```sql  
USE master;  
SELECT sess.session_id, sess.login_name, sess.group_id, grps.name   
FROM sys.dm_exec_sessions AS sess   
JOIN sys.dm_resource_governor_workload_groups AS grps   
    ON sess.group_id = grps.group_id  
WHERE session_id > 50;  
GO  
```  
  
 <span data-ttu-id="0cec5-203">Dans le volet de résultats, la colonne **nom** doit répertorier une ou plusieurs sessions pour le nom de groupe de charge de travail que vous avez spécifié dans votre fonction classifieur.</span><span class="sxs-lookup"><span data-stu-id="0cec5-203">In the results pane, the **name** column should list one or more sessions for the workload-group name that you specified in your classifier function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0cec5-204">Pour plus d’informations sur les vues de gestion dynamique appelées par cette instruction SELECT, consultez [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) et [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0cec5-204">For information about the dynamic management views called by this SELECT statement, see [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span></span>  
  
 [<span data-ttu-id="0cec5-205">&#91;Haut&#93;</span><span class="sxs-lookup"><span data-stu-id="0cec5-205">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="compressing-backups-using-a-session-with-limited-cpu"></a><a name="creating_compressed_backup"></a> <span data-ttu-id="0cec5-206">Compression de sauvegardes dans une session à utilisation maximale de l'UC limitée</span><span class="sxs-lookup"><span data-stu-id="0cec5-206">Compressing Backups Using a Session with Limited CPU</span></span>  
 <span data-ttu-id="0cec5-207">Pour créer une sauvegarde compressée dans une session à utilisation maximale de l'UC limitée, connectez-vous en tant que l'utilisateur spécifié dans votre fonction classifieur.</span><span class="sxs-lookup"><span data-stu-id="0cec5-207">To create a compressed backup in a session with a limited maximum CPU, log in as the user specified in your classifier function.</span></span> <span data-ttu-id="0cec5-208">Dans votre commande de sauvegarde, spécifiez WITH COMPRESSION ( [!INCLUDE[tsql](../../includes/tsql-md.md)] ) ou sélectionnez **compresser la sauvegarde** ( [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="0cec5-208">In your backup command, either specify WITH COMPRESSION ([!INCLUDE[tsql](../../includes/tsql-md.md)]) or select **Compress backup** ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]).</span></span> <span data-ttu-id="0cec5-209">Pour créer une sauvegarde de base de données compressée, consultez [Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0cec5-209">To create a compressed database backup, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
### <a name="example-c-creating-a-compressed-backup-transact-sql"></a><span data-ttu-id="0cec5-210">Exemple C : création d’une sauvegarde compressée (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0cec5-210">Example C: Creating a Compressed Backup (Transact-SQL)</span></span>  
 <span data-ttu-id="0cec5-211">L’exemple [BACKUP](/sql/t-sql/statements/backup-transact-sql) suivant crée une sauvegarde complète compressée de la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] dans un fichier de sauvegarde récemment formaté, `Z:\SQLServerBackups\AdvWorksData.bak`.</span><span class="sxs-lookup"><span data-stu-id="0cec5-211">The following [BACKUP](/sql/t-sql/statements/backup-transact-sql) example creates a compressed full backup of the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database in a newly formatted backup file, `Z:\SQLServerBackups\AdvWorksData.bak`.</span></span>  
  
```sql  
--Run backup statement in the gBackup session.  
BACKUP DATABASE AdventureWorks2012 TO DISK='Z:\SQLServerBackups\AdvWorksData.bak'   
WITH   
   FORMAT,   
   MEDIADESCRIPTION='AdventureWorks2012 Compressed Data Backups'  
   DESCRIPTION='First database backup on AdventureWorks2012 Compressed Data Backups media set'  
   COMPRESSION;  
GO  
```  
  
 [<span data-ttu-id="0cec5-212">&#91;Haut&#93;</span><span class="sxs-lookup"><span data-stu-id="0cec5-212">&#91;Top&#93;</span></span>](#Top)  
  
## <a name="see-also"></a><span data-ttu-id="0cec5-213">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0cec5-213">See Also</span></span>  
 <span data-ttu-id="0cec5-214">[Créer et tester une fonction classifieur définie par l’utilisateur](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="0cec5-214">[Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span></span>  
 [<span data-ttu-id="0cec5-215">gouverneur de ressources</span><span class="sxs-lookup"><span data-stu-id="0cec5-215">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
