---
title: Exécuter la logique métier pendant la synchronisation de fusion | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- custom error resolution [SQL Server replication]
- custom change handling [SQL Server replication]
- errors [SQL Server replication], business logic handlers
- merge replication business logic handlers [SQL Server replication]
- conflict resolution [SQL Server replication], merge replication
- business logic handlers [SQL Server replication]
ms.assetid: 9d4da2ef-c17f-4a31-a1f6-5c3b7ca85f71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1e082cbbb46ceae712cd39925c28fe89988a3793
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599954"
---
# <a name="execute-business-logic-during-merge-synchronization"></a><span data-ttu-id="9dbfc-102">Exécuter la logique métier lors de la synchronisation de fusion</span><span class="sxs-lookup"><span data-stu-id="9dbfc-102">Execute Business Logic During Merge Synchronization</span></span>
  <span data-ttu-id="9dbfc-103">L'infrastructure de gestion de logique métier permet d'écrire un assembly de code managé qui est appelé pendant le processus de synchronisation de fusion.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-103">The business logic handler framework allows you to write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="9dbfc-104">L'assembly comprend une logique métier qui peut répondre à un certain nombre de conditions au cours de la synchronisation : les modifications de données, les conflits et les erreurs.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-104">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="9dbfc-105">L'infrastructure de gestionnaires de logique métier propose un modèle de programmation simple et les données fournies par le processus de fusion à votre assembly se présentent sous la forme d'un dataset ADO.NET, de sorte que vous pouvez tirer parti de la connaissance d'ADO.NET au lieu d'apprendre une interface propriétaire.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-105">The business logic handler framework provides a simple programming model, and the data that the merge process provides to your assembly is in the form of an ADO.NET data set, so you can leverage knowledge of ADO.NET rather than learning a proprietary interface.</span></span> <span data-ttu-id="9dbfc-106">Pour plus d'informations sur la programmation de gestionnaires de logique métier, consultez :</span><span class="sxs-lookup"><span data-stu-id="9dbfc-106">For more information on programming business logic handlers, see:</span></span>  
  
-   <span data-ttu-id="9dbfc-107">Référence de l'interface de programmation d'applications (API) : <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span><span class="sxs-lookup"><span data-stu-id="9dbfc-107">The application programming interface (API) reference: <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span></span>  
  
-   <span data-ttu-id="9dbfc-108">Instructions sur l’implémentation d’un gestionnaire de logique métier : [Implémenter un gestionnaire de logique métier pour un article de fusion](../implement-a-business-logic-handler-for-a-merge-article.md)</span><span class="sxs-lookup"><span data-stu-id="9dbfc-108">Instructions on how to implement a business logic handler: [Implement a Business Logic Handler for a Merge Article](../implement-a-business-logic-handler-for-a-merge-article.md)</span></span>  
  
## <a name="uses-for-business-logic-handlers"></a><span data-ttu-id="9dbfc-109">Utilisations des gestionnaires de logique métier</span><span class="sxs-lookup"><span data-stu-id="9dbfc-109">Uses for Business Logic Handlers</span></span>  
 <span data-ttu-id="9dbfc-110">Le processus de synchronisation de fusion peut appeler les gestionnaires de logique métier pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9dbfc-110">The merge synchronization process can invoke business logic handlers to perform:</span></span>  
  
-   <span data-ttu-id="9dbfc-111">Gestion personnalisée des modifications</span><span class="sxs-lookup"><span data-stu-id="9dbfc-111">Custom change handling</span></span>  
  
-   <span data-ttu-id="9dbfc-112">Résolution personnalisée des conflits</span><span class="sxs-lookup"><span data-stu-id="9dbfc-112">Custom conflict resolution</span></span>  
  
-   <span data-ttu-id="9dbfc-113">Résolution personnalisée des erreurs</span><span class="sxs-lookup"><span data-stu-id="9dbfc-113">Custom error resolution</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9dbfc-114">Le gestionnaire de logique métier que vous spécifiez est exécuté pour chaque ligne faisant l'objet d'une synchronisation.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-114">The business logic handler you specify is executed for every row that is synchronized.</span></span> <span data-ttu-id="9dbfc-115">Une logique complexe et des appels à d'autres applications ou services réseau peuvent avoir une incidence sur les performances.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-115">Complex logic and calls to other applications or network services can impact performance.</span></span>  
  
### <a name="custom-change-handling"></a><span data-ttu-id="9dbfc-116">Gestion personnalisée des modifications</span><span class="sxs-lookup"><span data-stu-id="9dbfc-116">Custom Change Handling</span></span>  
 <span data-ttu-id="9dbfc-117">Le gestionnaire de logique métier peut être appelé au cours du traitement de modifications de données non conflictuelles et peut effectuer l'une des trois actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9dbfc-117">The business logic handler can be invoked during the processing of non-conflicting data changes and can perform one of three actions:</span></span>  
  
-   <span data-ttu-id="9dbfc-118">Refuser les données</span><span class="sxs-lookup"><span data-stu-id="9dbfc-118">Reject the data</span></span>  
  
     <span data-ttu-id="9dbfc-119">Cette option est utile dans le cas d'applications qui ne veulent pas propager des modifications vers un Abonné spécifique ou à partir de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-119">This is useful for applications that do not want changes propagated to or from a given Subscriber.</span></span> <span data-ttu-id="9dbfc-120">Ainsi, un administrateur peut éliminer les insertions qui n’appartiennent pas à la partition de l’Abonné ou éventuellement rejeter des suppressions effectuées au niveau d’un Abonné.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-120">For example, an administrator could filter out inserts that do not belong in the Subscriber's partition, or possibly reject deletes performed at a Subscriber.</span></span> <span data-ttu-id="9dbfc-121">Une application qui refuse une commande entrée sur l'Abonné pour indisponibilité de stock en est un autre exemple.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-121">As another example, an application could reject an order entered at a Subscriber because the inventory is no longer available.</span></span>  
  
-   <span data-ttu-id="9dbfc-122">Accepter les données</span><span class="sxs-lookup"><span data-stu-id="9dbfc-122">Accept the data</span></span>  
  
     <span data-ttu-id="9dbfc-123">Cette option est utile pour les applications dans lesquelles il est nécessaire de contrôler les modifications effectuées sur le serveur de publication ou sur l'Abonné avant d'autoriser leur propagation.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-123">This is useful for applications in which it is necessary to review data changes made at either the Publisher or Subscriber before allowing them to be propagated.</span></span> <span data-ttu-id="9dbfc-124">Par exemple, une application de niveau intermédiaire peut examiner les nouvelles commandes transmises par la force de vente et les intégrer à un processus de flux de travail d'approvisionnement au niveau intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-124">For example, a mid-tier application could examine new orders coming in from the field and integrate with a procurement workflow process in the mid-tier.</span></span>  
  
-   <span data-ttu-id="9dbfc-125">Appliquer des données personnalisées</span><span class="sxs-lookup"><span data-stu-id="9dbfc-125">Apply custom data</span></span>  
  
     <span data-ttu-id="9dbfc-126">Cette option est utile pour les applications qui doivent substituer des opérations ou des valeurs de données spécifiques.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-126">This is useful for applications that need to override specific data values or operations.</span></span> <span data-ttu-id="9dbfc-127">Par exemple, une application peut transformer une suppression de ligne en mise à jour spéciale qui affecte la valeur « supprimé » à une colonne **status** de la ligne puis effectue un suivi du client à l'origine de la suppression.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-127">For example, an application could transform a row delete into a special update that sets a **status** column in the row to a value of "deleted" and then tracks the identity of the client performing the delete.</span></span> <span data-ttu-id="9dbfc-128">Cela peut s'avérer utile pour l'audit ou le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-128">This might be useful for auditing or workflow purposes.</span></span>  
  
### <a name="custom-conflict-resolution"></a><span data-ttu-id="9dbfc-129">Résolution personnalisée des conflits</span><span class="sxs-lookup"><span data-stu-id="9dbfc-129">Custom Conflict Resolution</span></span>  
 <span data-ttu-id="9dbfc-130">La réplication de fusion offre des fonctionnalités de résolution ou de détection de conflits. Vous pouvez accepter une stratégie de résolution par défaut ou opter pour une résolution personnalisée des conflits.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-130">Merge replication provides conflict detection and resolution, allowing you to accept a default resolution strategy or choose custom resolution for conflicts.</span></span> <span data-ttu-id="9dbfc-131">Pour plus d’informations, consultez [Détection et résolution avancées des conflits de réplication de fusion](advanced-merge-replication-conflict-detection-and-resolution.md).</span><span class="sxs-lookup"><span data-stu-id="9dbfc-131">For more information, see [Advanced Merge Replication Conflict Detection and Resolution](advanced-merge-replication-conflict-detection-and-resolution.md).</span></span> <span data-ttu-id="9dbfc-132">Le gestionnaire de logique métier peut être appelé au cours du traitement de modifications de données conflictuelles et effectuer l'une des deux actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9dbfc-132">The business logic handler can be invoked during the processing of conflicting data changes and can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="9dbfc-133">Accepter la résolution par défaut</span><span class="sxs-lookup"><span data-stu-id="9dbfc-133">Accept default resolution</span></span>  
  
     <span data-ttu-id="9dbfc-134">Cette option est utile pour les applications qui doivent examiner le conflit, effectuer des opérations supplémentaires et éventuellement enregistrer un message de conflit personnalisé dans un journal.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-134">This is useful for applications that might need to review the conflict, perform additional actions, and possibly log a custom conflict log message.</span></span>  
  
-   <span data-ttu-id="9dbfc-135">Appliquer une résolution de conflits personnalisée</span><span class="sxs-lookup"><span data-stu-id="9dbfc-135">Perform custom resolution</span></span>  
  
     <span data-ttu-id="9dbfc-136">Cette option est utile pour les applications qui ont besoin de sélectionner des valeurs de données spécifiques à leur logique métier et fournir le processus de synchronisation avec ce dataset personnalisé.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-136">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="9dbfc-137">Ainsi, une application peut fournir une nouvelle version de la ligne qui prime en cas de conflit en combinant des valeurs des datasets du serveur de publication et de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-137">For example, an application could provide a new version of the winning row by combining values from the Publisher and Subscriber data sets.</span></span>  
  
### <a name="custom-error-resolution"></a><span data-ttu-id="9dbfc-138">Résolution personnalisée des erreurs</span><span class="sxs-lookup"><span data-stu-id="9dbfc-138">Custom Error Resolution</span></span>  
 <span data-ttu-id="9dbfc-139">La logique métier peut être appelée au cours de la propagation des modifications qui génèrent des erreurs.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-139">Custom logic can be invoked during the propagation of changes that result in errors.</span></span> <span data-ttu-id="9dbfc-140">La logique peut effectuer l'une des deux actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9dbfc-140">The logic can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="9dbfc-141">Accepter la résolution d'erreur par défaut</span><span class="sxs-lookup"><span data-stu-id="9dbfc-141">Accept default error resolution</span></span>  
  
     <span data-ttu-id="9dbfc-142">Cette option est utile pour les applications qui doivent examiner l'erreur, effectuer des opérations supplémentaires et éventuellement enregistrer un message d'erreur personnalisé dans un journal.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-142">This is useful for applications that might need to review the error and perform additional action and possibly log a custom error log message.</span></span>  
  
-   <span data-ttu-id="9dbfc-143">Accepter la résolution d'erreur personnalisée</span><span class="sxs-lookup"><span data-stu-id="9dbfc-143">Accept custom error resolution</span></span>  
  
     <span data-ttu-id="9dbfc-144">Cette option est utile pour les applications qui ont besoin de sélectionner des valeurs de données spécifiques à leur logique métier et fournir le processus de synchronisation avec ce dataset personnalisé.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-144">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="9dbfc-145">Si, par exemple, le processus de réplication rencontre une violation de clé dupliquée, le gestionnaire de logique métier peut fournir une nouvelle version de la modification de données dans laquelle le conflit de clé est éliminé.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-145">For example, if the replication process encounters a duplicate key violation, the business logic handler could provide a new version of the data change in which the key will no longer conflict.</span></span> <span data-ttu-id="9dbfc-146">Les modifications apportées au serveur de publication et à l'Abonné peuvent alors être conservées dans la base de données et le processus de réplication n'a plus à compenser l'échec d'insertion par une suppression.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-146">Changes made at the Publisher and Subscriber can then persist in the database, and the replication process doesn't have to compensate for the failed insert with a delete.</span></span>  
  
## <a name="deployment-scenarios-for-business-logic-handlers"></a><span data-ttu-id="9dbfc-147">Scénarios de déploiement des gestionnaires de logique métier</span><span class="sxs-lookup"><span data-stu-id="9dbfc-147">Deployment Scenarios for Business Logic Handlers</span></span>  
 <span data-ttu-id="9dbfc-148">Les gestionnaires de logique métier peuvent être déployés sur les serveurs suivants :</span><span class="sxs-lookup"><span data-stu-id="9dbfc-148">Business logic handlers can be deployed at:</span></span>  
  
-   <span data-ttu-id="9dbfc-149">Le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-149">The Distributor.</span></span> <span data-ttu-id="9dbfc-150">Utilisez un abonnement envoyé afin que la logique métier soit exécutée sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-150">Use a push subscription so that business logic is executed at the Distributor.</span></span>  
  
-   <span data-ttu-id="9dbfc-151">Abonné.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-151">The Subscriber.</span></span> <span data-ttu-id="9dbfc-152">Utilisez un abonnement extrait afin que la logique métier soit exécutée sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-152">Use a pull subscription so that business logic is executed at the Subscriber.</span></span>  
  
-   <span data-ttu-id="9dbfc-153">Serveur IIS (Internet Information Services) en cas d'utilisation de la synchronisation Web.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-153">An Internet Information Services (IIS) server if Web synchronization is used.</span></span> <span data-ttu-id="9dbfc-154">Utilisez un abonnement extrait synchronisé avec la synchronisation Web et le gestionnaire de logique métier s'exécutera sur le serveur IIS.</span><span class="sxs-lookup"><span data-stu-id="9dbfc-154">Use a pull subscription synchronized with Web synchronization, and the business logic handler will execute at the IIS Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbfc-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9dbfc-155">See Also</span></span>  
 <span data-ttu-id="9dbfc-156">[Réplication de fusion](merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="9dbfc-156">[Merge Replication](merge-replication.md) </span></span>  
 <span data-ttu-id="9dbfc-157">[S’abonner aux Publications](../subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="9dbfc-157">[Subscribe to Publications](../subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="9dbfc-158">[Synchroniser les données](../synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="9dbfc-158">[Synchronize Data](../synchronize-data.md) </span></span>  
 [<span data-ttu-id="9dbfc-159">Synchronisation web pour la réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="9dbfc-159">Web Synchronization for Merge Replication</span></span>](../web-synchronization-for-merge-replication.md)  
  
  
