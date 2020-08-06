---
title: MSSQL_REPL027183 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027183 error
ms.assetid: 52c271ac-1a0e-43d5-85d4-35886d1efd32
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4484318cd6ec6ff4f0b201be69dc9b7544dd2c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709155"
---
# <a name="mssql_repl027183"></a><span data-ttu-id="e8077-102">MSSQL_REPL027183</span><span class="sxs-lookup"><span data-stu-id="e8077-102">MSSQL_REPL027183</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e8077-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="e8077-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8077-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e8077-104">Product Name</span></span>|<span data-ttu-id="e8077-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8077-105">SQL Server</span></span>|  
|<span data-ttu-id="e8077-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e8077-106">Event ID</span></span>|<span data-ttu-id="e8077-107">27183</span><span class="sxs-lookup"><span data-stu-id="e8077-107">27183</span></span>|  
|<span data-ttu-id="e8077-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e8077-108">Event Source</span></span>|<span data-ttu-id="e8077-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e8077-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e8077-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e8077-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e8077-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e8077-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e8077-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e8077-112">Message Text</span></span>|<span data-ttu-id="e8077-113">Le processus de fusion n'a pas pu énumérer les modifications apportées aux articles via le filtre de lignes paramétrable.</span><span class="sxs-lookup"><span data-stu-id="e8077-113">The merge process failed to enumerate changes in articles with parameterized row filters.</span></span> <span data-ttu-id="e8077-114">Si le problème persiste, augmentez le délai de requête du processus, réduisez la période de rétention de la publication, puis améliorez les index des tables publiées.</span><span class="sxs-lookup"><span data-stu-id="e8077-114">If this failure continues, increase the query timeout for this process, reduce the retention period for the publication, and improve indexes on published tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e8077-115">Explication</span><span class="sxs-lookup"><span data-stu-id="e8077-115">Explanation</span></span>  
 <span data-ttu-id="e8077-116">Cette erreur est émise si le délai d'attente d'un Agent de fusion est dépassé lors du traitement des modifications dans une publication filtrée.</span><span class="sxs-lookup"><span data-stu-id="e8077-116">This error is raised if a Merge Agent timeout occurs while processing changes in a filtered publication.</span></span> <span data-ttu-id="e8077-117">Le dépassement du délai d'attente peut être causé par l'un des problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="e8077-117">The timeout might be caused by one of the following issues:</span></span>  
  
-   <span data-ttu-id="e8077-118">Non-utilisation de l'optimisation des partitions précalculées.</span><span class="sxs-lookup"><span data-stu-id="e8077-118">Not using the precomputed partitions optimization.</span></span>  
  
-   <span data-ttu-id="e8077-119">Fragmentation de l'index sur les colonnes utilisées pour le filtrage.</span><span class="sxs-lookup"><span data-stu-id="e8077-119">Index fragmentation on columns used for filtering.</span></span>  
  
-   <span data-ttu-id="e8077-120">Tables volumineuses de métadonnées de fusion, comme **MSmerge_tombstone**, **MSmerge_contents**et **MSmerge_genhistory**.</span><span class="sxs-lookup"><span data-stu-id="e8077-120">Large merge metadata tables, such as **MSmerge_tombstone**, **MSmerge_contents**, and **MSmerge_genhistory**.</span></span>  
  
-   <span data-ttu-id="e8077-121">Tables filtrées qui ne sont pas jointes sur une clé unique, et filtres de jointures qui impliquent un grand nombre de tables.</span><span class="sxs-lookup"><span data-stu-id="e8077-121">Filtered tables that are not joined on a unique key and join filters that involve a large number of tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8077-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e8077-122">User Action</span></span>  
 <span data-ttu-id="e8077-123">Pour résoudre le problème :</span><span class="sxs-lookup"><span data-stu-id="e8077-123">To resolve the issue:</span></span>  
  
-   <span data-ttu-id="e8077-124">Augmentez la valeur du paramètre **-QueryTimeOut** pour l’Agent de fusion afin de permettre au processus de se poursuivre pendant que vous résolvez les problèmes sous-jacents qui provoquent cette erreur.</span><span class="sxs-lookup"><span data-stu-id="e8077-124">Increase the value of the **-QueryTimeOut** parameter for the Merge Agent to allow processing to continue while you address the underlying issues causing the error.</span></span> <span data-ttu-id="e8077-125">Les paramètres des agents peuvent être spécifiés dans des profils d'agent et sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e8077-125">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="e8077-126">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="e8077-126">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="e8077-127">Utiliser des profils d’agent de réplication</span><span class="sxs-lookup"><span data-stu-id="e8077-127">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="e8077-128">Afficher et modifier des paramètres d’invite de commandes d’un Agent de réplication &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e8077-128">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="e8077-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="e8077-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="e8077-130">Utilisez si possible l'optimisation des partitions précalculées.</span><span class="sxs-lookup"><span data-stu-id="e8077-130">Use the precomputed partitions optimization if possible.</span></span> <span data-ttu-id="e8077-131">Cette optimisation est utilisée par défaut si un certain nombre de conditions de publication sont remplies.</span><span class="sxs-lookup"><span data-stu-id="e8077-131">This optimization is used by default if a number of publication requirements are met.</span></span> <span data-ttu-id="e8077-132">Pour plus d’informations sur ces exigences, consultez [Optimiser les performances des filtres paramétrés avec des partitions précalculées](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="e8077-132">For more information about these requirements, see [Optimize Parameterized Filter Performance with Precomputed Partitions](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span></span> <span data-ttu-id="e8077-133">Si la publication ne remplit pas ces conditions, envisagez de modifier sa conception.</span><span class="sxs-lookup"><span data-stu-id="e8077-133">If the publication does not meet these requirements, consider redesigning the publication.</span></span>  
  
-   <span data-ttu-id="e8077-134">Spécifiez la valeur la plus basse possible pour la période de rétention de la publication, parce que la réplication ne peut pas nettoyer les métadonnées de la publication et des bases de données d'abonnement tant que la période de rétention n'est pas achevée.</span><span class="sxs-lookup"><span data-stu-id="e8077-134">Specify the lowest setting possible for the publication retention period, because replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="e8077-135">Pour plus d’informations, voir [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="e8077-135">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="e8077-136">Dans le cadre de la gestion d'une réplication de fusion, contrôlez de temps en temps le développement des tables système associées à cette réplication : **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**et **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="e8077-136">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="e8077-137">Réindexez périodiquement ces tables.</span><span class="sxs-lookup"><span data-stu-id="e8077-137">Periodically re-index these tables.</span></span> <span data-ttu-id="e8077-138">Pour plus d’informations, consultez [Réorganiser et reconstruire des index](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e8077-138">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="e8077-139">Assurez-vous que les colonnes utilisées pour le filtrage sont correctement indexées et le cas échéant rebâtissez les index.</span><span class="sxs-lookup"><span data-stu-id="e8077-139">Ensure that columns used for filtering are properly indexed and rebuild such indexes if necessary.</span></span> <span data-ttu-id="e8077-140">Pour plus d’informations, consultez [Réorganiser et reconstruire des index](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e8077-140">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="e8077-141">Définissez la propriété **join_unique_key** sur les filtres de jointure qui sont basés sur des colonnes uniques</span><span class="sxs-lookup"><span data-stu-id="e8077-141">Set the **join_unique_key** property for join filters that are based on unique columns.</span></span> <span data-ttu-id="e8077-142">Pour plus d’informations, voir [Join Filters](merge/join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="e8077-142">For more information, see [Join Filters](merge/join-filters.md).</span></span>  
  
-   <span data-ttu-id="e8077-143">Limitez le nombre de tables dans la hiérarchie du filtre de jointure.</span><span class="sxs-lookup"><span data-stu-id="e8077-143">Limit the number of tables in the join filter hierarchy.</span></span> <span data-ttu-id="e8077-144">Si vous générez des filtres de jointure pour au moins cinq tables, envisagez d'autres solutions : ne filtrez pas les petites tables, les tables qui ne changent pas ou les tables de recherche principales.</span><span class="sxs-lookup"><span data-stu-id="e8077-144">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="e8077-145">Utilisez des filtres de jointure seulement entre des tables qui doivent être partitionnées entre des abonnements.</span><span class="sxs-lookup"><span data-stu-id="e8077-145">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="e8077-146">Réduisez entre les synchronisations le nombre de changements apportés aux tables filtrées, ou exécutez l'Agent de fusion plus souvent.</span><span class="sxs-lookup"><span data-stu-id="e8077-146">Make a smaller number of changes on filtered tables between synchronizations, or run the Merge Agent more frequently.</span></span> <span data-ttu-id="e8077-147">Pour plus d'informations sur la définition de planifications de synchronisation, consultez [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="e8077-147">For more information about setting synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8077-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8077-148">See Also</span></span>  
 [<span data-ttu-id="e8077-149">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="e8077-149">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
