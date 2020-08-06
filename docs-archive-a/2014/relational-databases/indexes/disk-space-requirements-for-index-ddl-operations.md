---
title: Espace disque nécessaire pour les opérations DDL d’index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- index disk space [SQL Server]
- space [SQL Server], indexes
- indexes [SQL Server], disk space requirements
- temporary disk space [SQL Server]
ms.assetid: 35930826-c870-44c1-a966-a6a4638f62ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4ac25fc1555d6b6cfd8ee97b50d261cf5788f587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614062"
---
# <a name="disk-space-requirements-for-index-ddl-operations"></a><span data-ttu-id="ced8f-102">Espace disque nécessaire pour les opérations DDL d'index</span><span class="sxs-lookup"><span data-stu-id="ced8f-102">Disk Space Requirements for Index DDL Operations</span></span>
  <span data-ttu-id="ced8f-103">L'espace disque est un élément important à prendre en compte lors de la création, de la reconstruction ou de la suppression d'index.</span><span class="sxs-lookup"><span data-stu-id="ced8f-103">Disk space is an important consideration when you create, rebuild, or drop indexes.</span></span> <span data-ttu-id="ced8f-104">Un espace disque inadéquat peut réduire les performances, voire entraîner l'échec de l'opération d'index.</span><span class="sxs-lookup"><span data-stu-id="ced8f-104">Inadequate disk space can degrade performance or even cause the index operation to fail.</span></span> <span data-ttu-id="ced8f-105">Cette rubrique propose des informations générales qui peuvent vous aider à déterminer la quantité d'espace disque nécessaire pour les opérations DDL d'index.</span><span class="sxs-lookup"><span data-stu-id="ced8f-105">This topic provides general information that can help you determine the amount of disk space required for index data definition language (DDL) operations.</span></span>  
  
## <a name="index-operations-that-require-no-additional-disk-space"></a><span data-ttu-id="ced8f-106">Opérations d'index ne nécessitant pas d'espace disque supplémentaire</span><span class="sxs-lookup"><span data-stu-id="ced8f-106">Index Operations That Require No Additional Disk Space</span></span>  
 <span data-ttu-id="ced8f-107">Les opérations d'index suivantes ne nécessitent pas d'espace disque supplémentaire :</span><span class="sxs-lookup"><span data-stu-id="ced8f-107">The following index operations require no additional disk space:</span></span>  
  
-   <span data-ttu-id="ced8f-108">ALTER INDEX REORGANIZE ; un espace journal est toutefois nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ced8f-108">ALTER INDEX REORGANIZE; however, log space is required.</span></span>  
  
-   <span data-ttu-id="ced8f-109">DROP INDEX lors de la suppression d'un index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="ced8f-109">DROP INDEX when you are dropping a nonclustered index.</span></span>  
  
-   <span data-ttu-id="ced8f-110">DROP INDEX lors de la suppression d'un index cluster hors ligne sans spécifier la clause MOVE TO et qu'il n'existe pas d'index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="ced8f-110">DROP INDEX when you are dropping a clustered index offline without specifying the MOVE TO clause and nonclustered indexes do not exist.</span></span>  
  
-   <span data-ttu-id="ced8f-111">CREATE TABLE (contraintes PRIMARY KEY ou UNIQUE)</span><span class="sxs-lookup"><span data-stu-id="ced8f-111">CREATE TABLE (PRIMARY KEY or UNIQUE constraints)</span></span>  
  
## <a name="index-operations-that-require-additional-disk-space"></a><span data-ttu-id="ced8f-112">Opérations d'index nécessitant de l'espace disque supplémentaire</span><span class="sxs-lookup"><span data-stu-id="ced8f-112">Index Operations That Require Additional Disk Space</span></span>  
 <span data-ttu-id="ced8f-113">Toutes les autres opérations DDL d'index nécessitent de l'espace disque temporaire supplémentaire lors de l'exécution de l'opération ainsi que de l'espace disque permanent pour stocker la ou les nouvelles structures d'index.</span><span class="sxs-lookup"><span data-stu-id="ced8f-113">All other index DDL operations require additional temporary disk space to use during the operation, and permanent disk space to store the new index structure or structures.</span></span>  
  
 <span data-ttu-id="ced8f-114">Lorsqu'une nouvelle structure d'index est créée, de l'espace disque est nécessaire pour l'ancienne structure (source) et la nouvelle (cible) dans les fichiers et groupes de fichiers appropriés.</span><span class="sxs-lookup"><span data-stu-id="ced8f-114">When a new index structure is created, disk space for both the old (source) and new (target) structures is required in their appropriate files and filegroups.</span></span> <span data-ttu-id="ced8f-115">L'ancienne structure n'est pas désallouée aussi longtemps que la transaction de création d'index n'est pas validée.</span><span class="sxs-lookup"><span data-stu-id="ced8f-115">The old structure is not deallocated until the index creation transaction commits.</span></span>  
  
 <span data-ttu-id="ced8f-116">Les opérations DDL d'index suivantes créent de nouvelles structures d'index et nécessitent de l'espace disque supplémentaire :</span><span class="sxs-lookup"><span data-stu-id="ced8f-116">The following index DDL operations create new index structures and require additional disk space:</span></span>  
  
-   <span data-ttu-id="ced8f-117">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="ced8f-117">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="ced8f-118">CREATE INDEX WITH DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="ced8f-118">CREATE INDEX WITH DROP_EXISTING</span></span>  
  
-   <span data-ttu-id="ced8f-119">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="ced8f-119">ALTER INDEX REBUILD</span></span>  
  
-   <span data-ttu-id="ced8f-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY ou UNIQUE)</span><span class="sxs-lookup"><span data-stu-id="ced8f-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY or UNIQUE)</span></span>  
  
-   <span data-ttu-id="ced8f-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY ou UNIQUE) lorsque la contrainte est basée sur un index cluster</span><span class="sxs-lookup"><span data-stu-id="ced8f-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY or UNIQUE) when the constraint is based on a clustered index</span></span>  
  
-   <span data-ttu-id="ced8f-122">DROP INDEX MOVE TO (concerne uniquement les index cluster)</span><span class="sxs-lookup"><span data-stu-id="ced8f-122">DROP INDEX MOVE TO (Applies only to clustered indexes.)</span></span>  
  
## <a name="temporary-disk-space-for-sorting"></a><span data-ttu-id="ced8f-123">Espace disque temporaire à des fins de tri</span><span class="sxs-lookup"><span data-stu-id="ced8f-123">Temporary Disk Space for Sorting</span></span>  
 <span data-ttu-id="ced8f-124">Outre l'espace disque nécessaire pour les structures source et cible, de l'espace disque temporaire est nécessaire à des fins de tri, à moins que l'optimiseur de requête trouve un plan d'exécution ne nécessitant pas de tri.</span><span class="sxs-lookup"><span data-stu-id="ced8f-124">Besides the disk space required for the source and target structures, temporary disk space is required for sorting, unless the query optimizer finds an execution plan that does not require sorting.</span></span>  
  
 <span data-ttu-id="ced8f-125">En cas de tri, celui-ci s'applique à un nouvel index à la fois.</span><span class="sxs-lookup"><span data-stu-id="ced8f-125">If sorting is required, sorting occurs one new index at a time.</span></span> <span data-ttu-id="ced8f-126">Par exemple, lorsque vous reconstruisez un index cluster et des index non-cluster associés dans une seule instruction, les index sont triés un après l'autre.</span><span class="sxs-lookup"><span data-stu-id="ced8f-126">For example, when you rebuild a clustered index and associated nonclustered indexes within a single statement, the indexes are sorted one after the other.</span></span> <span data-ttu-id="ced8f-127">La quantité d'espace disque temporaire supplémentaire nécessaire pour le tri doit par conséquent correspondre à l'index le plus volumineux traité.</span><span class="sxs-lookup"><span data-stu-id="ced8f-127">Therefore, the additional temporary disk space that is required for sorting only has to be as large as the largest index in the operation.</span></span> <span data-ttu-id="ced8f-128">Il s'agit généralement de l'index cluster.</span><span class="sxs-lookup"><span data-stu-id="ced8f-128">This is almost always the clustered index.</span></span>  
  
 <span data-ttu-id="ced8f-129">Si l’option SORT_IN_TEMPDB a la valeur ON, l’index le plus volumineux doit tenir dans **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="ced8f-129">If the SORT_IN_TEMPDB option is set to ON, the largest index must fit into **tempdb**.</span></span> <span data-ttu-id="ced8f-130">Bien que cette option augmente la quantité d’espace disque temporaire utilisée pour créer un index, elle peut réduire le temps nécessaire pour créer un index quand **tempdb** ne se trouve pas sur le même ensemble de disques que la base de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ced8f-130">Although this option increases the amount of temporary disk space that is used to create an index, it may reduce the time that is required to create an index when **tempdb** is on a set of disks different from the user database.</span></span>  
  
 <span data-ttu-id="ced8f-131">Si l'option SORT_IN_TEMPDB est définie sur OFF (par défaut) chaque index, y compris les index partitionnés, est stocké sur l'espace disque de destination et de l'espace disque n'est nécessaire que pour les nouvelles structures d'index.</span><span class="sxs-lookup"><span data-stu-id="ced8f-131">If SORT_IN_TEMPDB is set to OFF (the default) each index, including partitioned indexes, is sorted in its destination disk space; and only the disk space for the new index structures is required.</span></span>  
  
 <span data-ttu-id="ced8f-132">Pour obtenir un exemple de calcul de l’espace disque, consultez [Exemple d’espace disque d’un index](index-disk-space-example.md).</span><span class="sxs-lookup"><span data-stu-id="ced8f-132">For an example of calculating disk space, see [Index Disk Space Example](index-disk-space-example.md).</span></span>  
  
## <a name="temporary-disk-space-for-online-index-operations"></a><span data-ttu-id="ced8f-133">Espace disque temporaire pour les opérations d'index en ligne</span><span class="sxs-lookup"><span data-stu-id="ced8f-133">Temporary Disk Space for Online Index Operations</span></span>  
 <span data-ttu-id="ced8f-134">L'exécution d'opérations d'index en ligne nécessite de l'espace disque temporaire supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="ced8f-134">When you perform index operations online, additional temporary disk space is required.</span></span>  
  
 <span data-ttu-id="ced8f-135">Lors de la création, reconstruction ou suppression d'un index cluster, un index non-cluster temporaire est créé pour mapper les anciens signets sur les nouveaux.</span><span class="sxs-lookup"><span data-stu-id="ced8f-135">If a clustered index is created, rebuilt, or dropped online, a temporary nonclustered index is created to map old bookmarks to new bookmarks.</span></span> <span data-ttu-id="ced8f-136">Si l’option SORT_IN_TEMPDB a la valeur ON, cet index temporaire est créé dans **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="ced8f-136">If the SORT_IN_TEMPDB option is set to ON, this temporary index is created in **tempdb**.</span></span> <span data-ttu-id="ced8f-137">En revanche, si elle est définie sur OFF, le même groupe de fichiers ou schéma de partition que l'index cible est utilisé.</span><span class="sxs-lookup"><span data-stu-id="ced8f-137">If SORT_IN_TEMPDB is set to OFF, the same filegroup or partition scheme as the target index is used.</span></span> <span data-ttu-id="ced8f-138">L'index de mappage temporaire contient un enregistrement pour chaque ligne de la table et son contenu constitue un lien entre les anciennes et les nouvelles colonnes à signets, y compris les indicateurs d'unicité et les identificateurs d'enregistrement ; il ne comprend qu'une seule copie de chaque colonne utilisée dans les deux signets.</span><span class="sxs-lookup"><span data-stu-id="ced8f-138">The temporary mapping index contains one record for each row in the table, and its contents is the union of the old and new bookmark columns, including uniqueifiers and record identifiers and including only a single copy of any column used in both bookmarks.</span></span> <span data-ttu-id="ced8f-139">Pour plus d’informations sur les opérations en ligne sur les index, consultez [Exécuter des opérations en ligne sur les index](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="ced8f-139">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ced8f-140">L'option SORT_IN_TEMPDB ne peut pas être définie pour les instructions DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="ced8f-140">The SORT_IN_TEMPDB option cannot be set for DROP INDEX statements.</span></span> <span data-ttu-id="ced8f-141">L'index de mappage temporaire est toujours créé dans le même groupe de fichiers ou schéma de partition que l'index cible.</span><span class="sxs-lookup"><span data-stu-id="ced8f-141">The temporary mapping index is always created in the same filegroup or partition scheme as the target index.</span></span>  
  
 <span data-ttu-id="ced8f-142">Les opérations d'index en ligne utilisent le contrôle de version de ligne pour isoler l'opération d'index des effets des modifications d'autres transactions.</span><span class="sxs-lookup"><span data-stu-id="ced8f-142">Online index operations use row versioning to isolate the index operation from the effects of modifications made by other transactions.</span></span> <span data-ttu-id="ced8f-143">Ceci permet d'éviter de demander des verrous partagés sur des lignes qui ont été lues.</span><span class="sxs-lookup"><span data-stu-id="ced8f-143">This avoids the need for requesting share locks on rows that have been read.</span></span> <span data-ttu-id="ced8f-144">Les opérations simultanées de suppression et de mise à jour d’utilisateur lors d’opérations d’index en ligne nécessitent de l’espace pour les enregistrements de version dans **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="ced8f-144">Concurrent user update and delete operations during online index operations require space for version records in **tempdb**.</span></span> <span data-ttu-id="ced8f-145">Pour plus d’informations, consultez [Exécuter des opérations en ligne sur les index](perform-index-operations-online.md) .</span><span class="sxs-lookup"><span data-stu-id="ced8f-145">For more information, see [Perform Index Operations Online](perform-index-operations-online.md) .</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ced8f-146">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ced8f-146">Related Tasks</span></span>  
 [<span data-ttu-id="ced8f-147">Exemple d'espace disque d'un index</span><span class="sxs-lookup"><span data-stu-id="ced8f-147">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
 [<span data-ttu-id="ced8f-148">Espace disque du journal des transactions pour les opérations d’index</span><span class="sxs-lookup"><span data-stu-id="ced8f-148">Transaction Log Disk Space for Index Operations</span></span>](transaction-log-disk-space-for-index-operations.md)  
  
 [<span data-ttu-id="ced8f-149">Estimer la taille d’une table</span><span class="sxs-lookup"><span data-stu-id="ced8f-149">Estimate the Size of a Table</span></span>](../databases/estimate-the-size-of-a-table.md)  
  
 [<span data-ttu-id="ced8f-150">Estimer la taille d'un index cluster</span><span class="sxs-lookup"><span data-stu-id="ced8f-150">Estimate the Size of a Clustered Index</span></span>](../databases/estimate-the-size-of-a-clustered-index.md)  
  
 [<span data-ttu-id="ced8f-151">Estimer la taille d'un index non-cluster</span><span class="sxs-lookup"><span data-stu-id="ced8f-151">Estimate the Size of a Nonclustered Index</span></span>](../databases/estimate-the-size-of-a-nonclustered-index.md)  
  
 [<span data-ttu-id="ced8f-152">Estimer la taille d’un segment de mémoire</span><span class="sxs-lookup"><span data-stu-id="ced8f-152">Estimate the Size of a Heap</span></span>](../databases/estimate-the-size-of-a-heap.md)  
  
## <a name="related-content"></a><span data-ttu-id="ced8f-153">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="ced8f-153">Related Content</span></span>  
 [<span data-ttu-id="ced8f-154">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ced8f-154">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="ced8f-155">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ced8f-155">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
 [<span data-ttu-id="ced8f-156">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ced8f-156">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="ced8f-157">Spécifier un facteur de remplissage pour un index</span><span class="sxs-lookup"><span data-stu-id="ced8f-157">Specify Fill Factor for an Index</span></span>](specify-fill-factor-for-an-index.md)  
  
 [<span data-ttu-id="ced8f-158">Réorganiser et reconstruire des index</span><span class="sxs-lookup"><span data-stu-id="ced8f-158">Reorganize and Rebuild Indexes</span></span>](indexes.md)  
  
  
