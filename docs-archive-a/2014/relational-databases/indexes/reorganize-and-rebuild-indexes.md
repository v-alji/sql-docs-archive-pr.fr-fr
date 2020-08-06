---
title: Réorganiser et reconstruire des index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.fragmentation.f1
- sql12.swb.index.reorg.f1
- sql12.swb.index.rebuild.f1
helpviewer_keywords:
- large object defragmenting
- indexes [SQL Server], reorganizing
- index reorganization [SQL Server]
- reorganizing indexes
- defragmenting large object data types
- index fragmentation [SQL Server]
- index rebuilding [SQL Server]
- rebuilding indexes
- indexes [SQL Server], rebuilding
- defragmenting indexes
- nonclustered indexes [SQL Server], defragmenting
- fragmentation [SQL Server]
- index defragmenting [SQL Server]
- LOB data [SQL Server], defragmenting
- clustered indexes, defragmenting
ms.assetid: a28c684a-c4e9-4b24-a7ae-e248808b31e9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c00f2128bb4c54064511ffff9e8929c9faf4d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707552"
---
# <a name="reorganize-and-rebuild-indexes"></a><span data-ttu-id="f0295-102">Réorganiser et reconstruire des index</span><span class="sxs-lookup"><span data-stu-id="f0295-102">Reorganize and Rebuild Indexes</span></span>
  <span data-ttu-id="f0295-103">Cette rubrique explique comment réorganiser ou reconstruire un index fragmenté dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0295-103">This topic describes how to reorganize or rebuild a fragmented index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f0295-104">Le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] gère automatiquement des index lorsque des opérations d'insertion, de mise à jour ou de suppression sont effectuées sur les données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="f0295-104">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically maintains indexes whenever insert, update, or delete operations are made to the underlying data.</span></span> <span data-ttu-id="f0295-105">Au fil des modifications, les informations figurant dans l'index sont éparpillées dans la base de données (fragmentée).</span><span class="sxs-lookup"><span data-stu-id="f0295-105">Over time these modifications can cause the information in the index to become scattered in the database (fragmented).</span></span> <span data-ttu-id="f0295-106">La fragmentation intervient lorsque des index possèdent des pages dans lesquelles l'organisation logique (reposant sur la valeur de la clé) ne correspond pas à l'organisation physique dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="f0295-106">Fragmentation exists when indexes have pages in which the logical ordering, based on the key value, does not match the physical ordering inside the data file.</span></span> <span data-ttu-id="f0295-107">Une fragmentation importante des index peut diminuer les performances des requêtes et ralentir la vitesse de réponse de votre application.</span><span class="sxs-lookup"><span data-stu-id="f0295-107">Heavily fragmented indexes can degrade query performance and cause your application to respond slowly.</span></span>  
  
 <span data-ttu-id="f0295-108">Vous pouvez remédier à la fragmentation des index en réorganisant un index ou en reconstruisant un index.</span><span class="sxs-lookup"><span data-stu-id="f0295-108">You can remedy index fragmentation by reorganizing or rebuilding an index.</span></span> <span data-ttu-id="f0295-109">Dans le cas d'index partitionnés reposant sur un schéma de partition, vous pouvez utiliser les méthodes suivantes sur la totalité ou sur une partition unique d'un index.</span><span class="sxs-lookup"><span data-stu-id="f0295-109">For partitioned indexes built on a partition scheme, you can use either of these methods on a complete index or a single partition of an index.</span></span> <span data-ttu-id="f0295-110">La reconstruction d'un index entraîne sa suppression puis sa recréation.</span><span class="sxs-lookup"><span data-stu-id="f0295-110">Rebuilding an index drops and re-creates the index.</span></span> <span data-ttu-id="f0295-111">Ceci permet d'éviter toute fragmentation, de libérer de l'espace disque en compactant les pages d'après le paramètre du facteur de remplissage spécifié ou déjà existant et en retriant les lignes de l'index en pages contiguës.</span><span class="sxs-lookup"><span data-stu-id="f0295-111">This removes fragmentation, reclaims disk space by compacting the pages based on the specified or existing fill factor setting, and reorders the index rows in contiguous pages.</span></span> <span data-ttu-id="f0295-112">Quand ALL est précisé, tous les index sur la table sont supprimés puis reconstruits en une seule transaction.</span><span class="sxs-lookup"><span data-stu-id="f0295-112">When ALL is specified, all indexes on the table are dropped and rebuilt in a single transaction.</span></span> <span data-ttu-id="f0295-113">La réorganisation d'un index utilise des ressources système minimes.</span><span class="sxs-lookup"><span data-stu-id="f0295-113">Reorganizing an index uses minimal system resources.</span></span> <span data-ttu-id="f0295-114">En effet, elle défragmente le niveau feuille des index cluster et non cluster sur les tables et les vues en retriant les pages de niveau feuille de façon physique afin de resuivre l'ordre logique, c'est-à-dire de gauche à droite, des nœuds.</span><span class="sxs-lookup"><span data-stu-id="f0295-114">It defragments the leaf level of clustered and nonclustered indexes on tables and views by physically reordering the leaf-level pages to match the logical, left to right, order of the leaf nodes.</span></span> <span data-ttu-id="f0295-115">Cette opération compacte également les pages d'index.</span><span class="sxs-lookup"><span data-stu-id="f0295-115">Reorganizing also compacts the index pages.</span></span> <span data-ttu-id="f0295-116">Le compactage s'appuie sur la valeur du facteur de remplissage existante.</span><span class="sxs-lookup"><span data-stu-id="f0295-116">Compaction is based on the existing fill factor value.</span></span>  
  
 <span data-ttu-id="f0295-117">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f0295-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f0295-118">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f0295-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f0295-119">Détection de la fragmentation</span><span class="sxs-lookup"><span data-stu-id="f0295-119">Detecting Fragmentation</span></span>](#Fragmentation)  
  
     [<span data-ttu-id="f0295-120">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f0295-120">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f0295-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0295-121">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f0295-122">**Pour vérifier la fragmentation d'un index, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="f0295-122">**To check the fragmentation of an index, using:**</span></span>  
  
     [<span data-ttu-id="f0295-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0295-123">SQL Server Management Studio</span></span>](#SSMSProcedureFrag)  
  
     [<span data-ttu-id="f0295-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0295-124">Transact-SQL</span></span>](#TsqlProcedureFrag)  
  
-   <span data-ttu-id="f0295-125">**Pour réorganiser ou reconstruire un index, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="f0295-125">**To reorganize or rebuild an index, using:**</span></span>  
  
     [<span data-ttu-id="f0295-126">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0295-126">SQL Server Management Studio</span></span>](#SSMSProcedureReorg)  
  
     [<span data-ttu-id="f0295-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0295-127">Transact-SQL</span></span>](#TsqlProcedureReorg)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0295-128">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f0295-128">Before You Begin</span></span>  
  
###  <a name="detecting-fragmentation"></a><a name="Fragmentation"></a><span data-ttu-id="f0295-129">Détection de la fragmentation</span><span class="sxs-lookup"><span data-stu-id="f0295-129">Detecting Fragmentation</span></span>  
 <span data-ttu-id="f0295-130">Lorsque vous déterminez la méthode de défragmentation à adopter, la première étape consiste à analyser l'index pour évaluer son degré de fragmentation.</span><span class="sxs-lookup"><span data-stu-id="f0295-130">The first step in deciding which defragmentation method to use is to analyze the index to determine the degree of fragmentation.</span></span> <span data-ttu-id="f0295-131">La fonction système [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql)vous permet de détecter la fragmentation dans un index spécifique, dans tous les index d’une table ou d’une vue indexée, dans tous les index d’une base de données ou dans tous les index de l’ensemble des bases de données.</span><span class="sxs-lookup"><span data-stu-id="f0295-131">By using the system function [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql), you can detect fragmentation in a specific index, all indexes on a table or indexed view, all indexes in a database, or all indexes in all databases.</span></span> <span data-ttu-id="f0295-132">Pour les index partitionnés, **sys.dm_db_index_physical_stats** procure aussi des informations de fragmentation pour chaque partition.</span><span class="sxs-lookup"><span data-stu-id="f0295-132">For partitioned indexes, **sys.dm_db_index_physical_stats** also provides fragmentation information for each partition.</span></span>  
  
 <span data-ttu-id="f0295-133">Le jeu de résultats retourné par la fonction **sys.dm_db_index_physical_stats** inclut les colonnes suivantes.</span><span class="sxs-lookup"><span data-stu-id="f0295-133">The result set returned by the **sys.dm_db_index_physical_stats** function includes the following columns.</span></span>  
  
|<span data-ttu-id="f0295-134">Colonne</span><span class="sxs-lookup"><span data-stu-id="f0295-134">Column</span></span>|<span data-ttu-id="f0295-135">Description</span><span class="sxs-lookup"><span data-stu-id="f0295-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f0295-136">**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="f0295-136">**avg_fragmentation_in_percent**</span></span>|<span data-ttu-id="f0295-137">Pourcentage de fragmentation logique (pages non ordonnées dans un index).</span><span class="sxs-lookup"><span data-stu-id="f0295-137">The percent of logical fragmentation (out-of-order pages in the index).</span></span>|  
|<span data-ttu-id="f0295-138">**fragment_count**</span><span class="sxs-lookup"><span data-stu-id="f0295-138">**fragment_count**</span></span>|<span data-ttu-id="f0295-139">Nombre de fragments (pages de feuille consécutives physiquement) dans l'index.</span><span class="sxs-lookup"><span data-stu-id="f0295-139">The number of fragments (physically consecutive leaf pages) in the index.</span></span>|  
|<span data-ttu-id="f0295-140">**avg_fragment_size_in_pages**</span><span class="sxs-lookup"><span data-stu-id="f0295-140">**avg_fragment_size_in_pages**</span></span>|<span data-ttu-id="f0295-141">Nombre moyen de pages dans un fragment d'un index.</span><span class="sxs-lookup"><span data-stu-id="f0295-141">Average number of pages in one fragment in an index.</span></span>|  
  
 <span data-ttu-id="f0295-142">Une fois le degré de fragmentation connu, utilisez le tableau suivant pour déterminer la méthode la mieux adaptée pour corriger la fragmentation.</span><span class="sxs-lookup"><span data-stu-id="f0295-142">After the degree of fragmentation is known, use the following table to determine the best method to correct the fragmentation.</span></span>  
  
|<span data-ttu-id="f0295-143">Valeur**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="f0295-143">**avg_fragmentation_in_percent** value</span></span>|<span data-ttu-id="f0295-144">Instruction corrective</span><span class="sxs-lookup"><span data-stu-id="f0295-144">Corrective statement</span></span>|  
|-----------------------------------------------|--------------------------|  
|<span data-ttu-id="f0295-145">> 5% et \< = 30%</span><span class="sxs-lookup"><span data-stu-id="f0295-145">> 5% and \< = 30%</span></span>|<span data-ttu-id="f0295-146">ALTER INDEX REORGANIZE</span><span class="sxs-lookup"><span data-stu-id="f0295-146">ALTER INDEX REORGANIZE</span></span>|  
|<span data-ttu-id="f0295-147">> 30%</span><span class="sxs-lookup"><span data-stu-id="f0295-147">> 30%</span></span>|<span data-ttu-id="f0295-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f0295-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span></span>|

<span data-ttu-id="f0295-149"><sup>1</sup> La reconstruction d’un index peut être exécutée en ligne ou hors connexion.</span><span class="sxs-lookup"><span data-stu-id="f0295-149"><sup>1</sup> Rebuilding an index can be executed online or offline.</span></span> <span data-ttu-id="f0295-150">La réorganisation d'un index s'effectue toujours en ligne.</span><span class="sxs-lookup"><span data-stu-id="f0295-150">Reorganizing an index is always executed online.</span></span> <span data-ttu-id="f0295-151">Pour obtenir le même niveau de disponibilité qu'avec l'option de réorganisation, vous devez reconstruire les index en ligne.</span><span class="sxs-lookup"><span data-stu-id="f0295-151">To achieve availability similar to the reorganize option, you should rebuild indexes online.</span></span>  
  
> [!TIP]
> <span data-ttu-id="f0295-152">Ces valeurs fournissent des directives approximatives pour déterminer le point auquel vous devez basculer entre `ALTER INDEX REORGANIZE` et `ALTER INDEX REBUILD`.</span><span class="sxs-lookup"><span data-stu-id="f0295-152">These values provide a rough guideline for determining the point at which you should switch between `ALTER INDEX REORGANIZE` and `ALTER INDEX REBUILD`.</span></span> <span data-ttu-id="f0295-153">Toutefois, les valeurs réelles peuvent varier d'un cas à l'autre.</span><span class="sxs-lookup"><span data-stu-id="f0295-153">However, the actual values may vary from case to case.</span></span> <span data-ttu-id="f0295-154">Il est important que vous fassiez des essais pour déterminer le meilleur seuil pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="f0295-154">It is important that you experiment to determine the best threshold for your environment.</span></span> <span data-ttu-id="f0295-155">Par exemple, si un index donné est principalement utilisé pour les opérations d’analyse, la suppression de la fragmentation peut améliorer les performances de ces opérations.</span><span class="sxs-lookup"><span data-stu-id="f0295-155">For example, if a given index is used mainly for scan operations, removing fragmentation can improve performance of these operations.</span></span> <span data-ttu-id="f0295-156">L’avantage en matière de performances est moins perceptible pour les index utilisés principalement pour les opérations de recherche.</span><span class="sxs-lookup"><span data-stu-id="f0295-156">The performance benefit is less noticeable for indexes that are used primarily for seek operations.</span></span> <span data-ttu-id="f0295-157">De même, la suppression de la fragmentation dans un segment de mémoire (une table sans index cluster) est particulièrement utile pour les opérations d’analyse d’index non-cluster, mais n’a que peu d’effet dans les opérations de recherche.</span><span class="sxs-lookup"><span data-stu-id="f0295-157">Similarly, removing fragmentation in a heap (a table with no clustered index) is especially useful for nonclustered index scan operations, but has little effect in lookup operations.</span></span>

<span data-ttu-id="f0295-158">Des niveaux très bas de fragmentation (inférieurs à 5 %) ne doivent pas être pris en compte par ces commandes, car l’avantage de la suppression d’un volume de fragmentation aussi réduit est quasiment toujours largement contrebalancé par le coût de la réorganisation ou de la reconstruction de l’index.</span><span class="sxs-lookup"><span data-stu-id="f0295-158">Very low levels of fragmentation (less than 5 percent) should typically not be addressed by either of these commands, because the benefit from removing such a small amount of fragmentation is almost always vastly outweighed by the cost of reorganizing or rebuilding the index.</span></span> 

> [!NOTE]
> <span data-ttu-id="f0295-159">Bien souvent, la reconstruction ou la réorganisation de petits index ne réduit pas la fragmentation.</span><span class="sxs-lookup"><span data-stu-id="f0295-159">Rebuilding or reorganizing small indexes often does not reduce fragmentation.</span></span> <span data-ttu-id="f0295-160">Les pages de petits index sont parfois stockées sur des extensions mixtes.</span><span class="sxs-lookup"><span data-stu-id="f0295-160">The pages of small indexes are sometimes stored on mixed extents.</span></span> <span data-ttu-id="f0295-161">Les extensions mixtes sont partagées par huit objets maximum ; par conséquent, la fragmentation dans un petit index peut ne pas être réduite après sa réorganisation ou sa reconstruction.</span><span class="sxs-lookup"><span data-stu-id="f0295-161">Mixed extents are shared by up to eight objects, so the fragmentation in a small index might not be reduced after reorganizing or rebuilding it.</span></span>

### <a name="index-defragmentation-considerations"></a><span data-ttu-id="f0295-162">Considérations sur la défragmentation d’index</span><span class="sxs-lookup"><span data-stu-id="f0295-162">Index defragmentation considerations</span></span>
<span data-ttu-id="f0295-163">Dans certaines conditions, la recréation d’un index cluster recrée automatiquement tout index non-cluster qui référence la clé de clustering, si les identificateurs physiques ou logiques contenus dans les enregistrements d’index non-cluster doivent être modifiés.</span><span class="sxs-lookup"><span data-stu-id="f0295-163">Under certain conditions, rebuilding a clustered index will automatically rebuild any nonclustered index that reference the clustering key, if the physical or logical identifiers contained in the nonclustered index records needs to change.</span></span>

<span data-ttu-id="f0295-164">Scénarios qui forcent la recréation automatique de tous les index non-cluster sur une table :</span><span class="sxs-lookup"><span data-stu-id="f0295-164">Scenarios that force all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="f0295-165">Création d’un index cluster sur une table</span><span class="sxs-lookup"><span data-stu-id="f0295-165">Creating a clustered index on a table</span></span>
-  <span data-ttu-id="f0295-166">Suppression d’un index cluster, provoquant le stockage de la table en tant que segment de mémoire</span><span class="sxs-lookup"><span data-stu-id="f0295-166">Removing a clustered index, causing the table to be stored as a heap</span></span>
-  <span data-ttu-id="f0295-167">Modification de la clé de clustering pour inclure ou exclure des colonnes</span><span class="sxs-lookup"><span data-stu-id="f0295-167">Changing the clustering key to include or exclude columns</span></span>

<span data-ttu-id="f0295-168">Scénarios qui ne nécessitent pas la recréation automatique de tous les index non-cluster sur une table :</span><span class="sxs-lookup"><span data-stu-id="f0295-168">Scenarios that do not require all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="f0295-169">Recréation d’un index cluster unique</span><span class="sxs-lookup"><span data-stu-id="f0295-169">Rebuilding a unique clustered index</span></span>
-  <span data-ttu-id="f0295-170">Recréation d’un index cluster non unique</span><span class="sxs-lookup"><span data-stu-id="f0295-170">Rebuilding a non-unique clustered index</span></span>
-  <span data-ttu-id="f0295-171">Modification du schéma d’index, telle que l’application d’un schéma de partitionnement à un index cluster ou le déplacement de l’index cluster vers un autre groupe de fichiers</span><span class="sxs-lookup"><span data-stu-id="f0295-171">Changing the index schema, such as applying a partitioning scheme to a clustered index or moving the clustered index to a different filegroup</span></span>
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f0295-172">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f0295-172">Limitations and Restrictions</span></span>  
  
<span data-ttu-id="f0295-173">Les index possédant plus de 128 extensions sont reconstruits en deux phases distinctes : une phase logique et une phase physique.</span><span class="sxs-lookup"><span data-stu-id="f0295-173">Indexes with more than 128 extents are rebuilt in two separate phases: logical and physical.</span></span> <span data-ttu-id="f0295-174">Dans la phase logique, les unités d'allocation utilisées par l'index sont signalées comme devant être désallouées, les lignes de données sont copiées et triées, puis elles sont déplacées vers les nouvelles unités d'allocation ayant été créées pour stocker l'index reconstruit.</span><span class="sxs-lookup"><span data-stu-id="f0295-174">In the logical phase, the existing allocation units used by the index are marked for deallocation, the data rows are copied and sorted, then moved to new allocation units created to store the rebuilt index.</span></span> <span data-ttu-id="f0295-175">Dans la phase physique, les unités d'allocation préalablement signalées pour être désallouées sont supprimées physiquement dans des transactions courtes qui interviennent en arrière-plan et nécessitent peu de verrous.</span><span class="sxs-lookup"><span data-stu-id="f0295-175">In the physical phase, the allocation units previously marked for deallocation are physically dropped in short transactions that happen in the background, and do not require many locks.</span></span> <span data-ttu-id="f0295-176">Pour plus d’informations sur les étendues, consultez [Guide d’architecture des pages et des étendues](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span><span class="sxs-lookup"><span data-stu-id="f0295-176">For more information about extents, refer to the [Pages and Extents Architecture Guide](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span></span>

<span data-ttu-id="f0295-177">L’instruction `ALTER INDEX REORGANIZE` a besoin du fichier de données contenant l’index pour disposer d’espace, car l’opération peut uniquement allouer des pages de travail temporaires à un même fichier, mais pas à un autre fichier du groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f0295-177">The `ALTER INDEX REORGANIZE` statement requires the data file containing the index to have space available, because the operation can only allocate temporary work pages on the same file, not another file within the filegroup.</span></span> <span data-ttu-id="f0295-178">De ce fait, même si le groupe de fichiers a des pages libres, l’utilisateur peut toujours rencontrer l’erreur 1105 : `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span><span class="sxs-lookup"><span data-stu-id="f0295-178">So although the filegroup might have free pages available, the user can still encounter error 1105: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span></span>

<span data-ttu-id="f0295-179">Il est possible de créer et de reconstruire des index non alignés sur une table constituée de plus de 1 000 partitions, mais cela n’est pas recommandé.</span><span class="sxs-lookup"><span data-stu-id="f0295-179">Creating and rebuilding non-aligned indexes on a table with more than 1,000 partitions is possible, but is not recommended.</span></span> <span data-ttu-id="f0295-180">Ces opérations peuvent entraîner une dégradation des performances ou une consommation de mémoire excessive.</span><span class="sxs-lookup"><span data-stu-id="f0295-180">Doing so may cause degraded performance or excessive memory consumption during these operations.</span></span>

<span data-ttu-id="f0295-181">Un index ne peut pas être réorganisé ou reconstruit si le groupe de fichiers dans lequel il se trouve est hors connexion ou en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="f0295-181">An index cannot be reorganized or rebuilt if the filegroup in which it is located is offline or set to read-only.</span></span> <span data-ttu-id="f0295-182">Si le mot clé `ALL` est spécifié et qu’un ou plusieurs index se trouvent dans un groupe de fichiers hors connexion ou en lecture seule, l’instruction échoue.</span><span class="sxs-lookup"><span data-stu-id="f0295-182">When the keyword `ALL` is specified and one or more indexes are in an offline or read-only filegroup, the statement fails.</span></span>
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0295-183">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0295-183">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0295-184">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f0295-184">Permissions</span></span>  
 <span data-ttu-id="f0295-185">Nécessite l’autorisation `ALTER` sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="f0295-185">Requires `ALTER` permission on the table or view.</span></span> <span data-ttu-id="f0295-186">L’utilisateur doit être membre du rôle serveur fixe **sysadmin** ou des rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="f0295-186">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureFrag"></a> <span data-ttu-id="f0295-187">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0295-187">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="f0295-188">Pour vérifier la fragmentation d'un index</span><span class="sxs-lookup"><span data-stu-id="f0295-188">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="f0295-189">Dans l’Explorateur d’objets, développez la base de données qui contient la table sur laquelle vous souhaitez vérifier une fragmentation d’index.</span><span class="sxs-lookup"><span data-stu-id="f0295-189">In Object Explorer, Expand the database that contains the table on which you want to check an index's fragmentation.</span></span>  
  
2.  <span data-ttu-id="f0295-190">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="f0295-190">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="f0295-191">Développez la table sur laquelle vous souhaitez vérifier une fragmentation d’index.</span><span class="sxs-lookup"><span data-stu-id="f0295-191">Expand the table on which you want to check an index's fragmentation.</span></span>  
  
4.  <span data-ttu-id="f0295-192">Développez le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="f0295-192">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="f0295-193">Cliquez avec le bouton droit sur l’index dont vous voulez vérifier la fragmentation, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f0295-193">Right-click the index of which you want to check the fragmentation and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="f0295-194">Sous **Sélectionner une page**, sélectionnez **Fragmentation**.</span><span class="sxs-lookup"><span data-stu-id="f0295-194">Under **Select a page**, select **Fragmentation**.</span></span>  
  
     <span data-ttu-id="f0295-195">Les informations suivantes sont disponibles dans la page **Fragmentation** :</span><span class="sxs-lookup"><span data-stu-id="f0295-195">The following information is available on the **Fragmentation** page:</span></span>  
  
     <span data-ttu-id="f0295-196">**Remplissage de la page**</span><span class="sxs-lookup"><span data-stu-id="f0295-196">**Page fullness**</span></span>  
     <span data-ttu-id="f0295-197">Indique le remplissage moyen des pages d'index, sous forme de pourcentage.</span><span class="sxs-lookup"><span data-stu-id="f0295-197">Indicates average fullness of the index pages, as a percentage.</span></span> <span data-ttu-id="f0295-198">100% signifie que les pages d'index sont totalement remplies.</span><span class="sxs-lookup"><span data-stu-id="f0295-198">100% means the index pages are completely full.</span></span> <span data-ttu-id="f0295-199">50% signifie qu'en moyenne, chaque page d'index est remplie à moitié.</span><span class="sxs-lookup"><span data-stu-id="f0295-199">50% means that, on average, each index page is half full.</span></span>  
  
     <span data-ttu-id="f0295-200">**Fragmentation totale**</span><span class="sxs-lookup"><span data-stu-id="f0295-200">**Total fragmentation**</span></span>  
     <span data-ttu-id="f0295-201">Pourcentage de fragmentation logique.</span><span class="sxs-lookup"><span data-stu-id="f0295-201">The logical fragmentation percentage.</span></span> <span data-ttu-id="f0295-202">Cette valeur indique le nombre de pages dans un index qui ne sont pas stockées dans l'ordre.</span><span class="sxs-lookup"><span data-stu-id="f0295-202">This indicates the number of pages in an index that are not stored in order.</span></span>  
  
     <span data-ttu-id="f0295-203">**Taille moyenne de ligne**</span><span class="sxs-lookup"><span data-stu-id="f0295-203">**Average row size**</span></span>  
     <span data-ttu-id="f0295-204">Taille moyenne d'une ligne de niveau feuille.</span><span class="sxs-lookup"><span data-stu-id="f0295-204">The average size of a leaf level row.</span></span>  
  
     <span data-ttu-id="f0295-205">**Profondeur**</span><span class="sxs-lookup"><span data-stu-id="f0295-205">**Depth**</span></span>  
     <span data-ttu-id="f0295-206">Nombre de niveaux dans l'index, notamment le niveau feuille.</span><span class="sxs-lookup"><span data-stu-id="f0295-206">The number of levels in the index, including the leaf level.</span></span>  
  
     <span data-ttu-id="f0295-207">**Enregistrements transférés**</span><span class="sxs-lookup"><span data-stu-id="f0295-207">**Forwarded records**</span></span>  
     <span data-ttu-id="f0295-208">Nombre d'enregistrements d'un segment qui contiennent des pointeurs avant vers un autre emplacement de données.</span><span class="sxs-lookup"><span data-stu-id="f0295-208">The number of records in a heap that have forward pointers to another data location.</span></span> <span data-ttu-id="f0295-209">(Cet état se produit pendant une mise à jour, lorsque l'espace disponible est insuffisant pour stocker la nouvelle ligne à l'emplacement d'origine.)</span><span class="sxs-lookup"><span data-stu-id="f0295-209">(This state occurs during an update, when there is not enough room to store the new row in the original location.)</span></span>  
  
     <span data-ttu-id="f0295-210">**Lignes fantômes**</span><span class="sxs-lookup"><span data-stu-id="f0295-210">**Ghost rows**</span></span>  
     <span data-ttu-id="f0295-211">Nombre de lignes marquées pour la suppression qui ne sont pas encore supprimées.</span><span class="sxs-lookup"><span data-stu-id="f0295-211">The number of rows that are marked as deleted but not yet removed.</span></span> <span data-ttu-id="f0295-212">Ces lignes seront supprimées par un thread de nettoyage, lorsque le serveur n'est pas occupé.</span><span class="sxs-lookup"><span data-stu-id="f0295-212">These rows will be removed by a clean-up thread, when the server is not busy.</span></span> <span data-ttu-id="f0295-213">Cette valeur ne comprend pas les lignes qui sont conservées à cause d'une transaction d'isolement d'instantané en suspens.</span><span class="sxs-lookup"><span data-stu-id="f0295-213">This value does not include rows that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
     <span data-ttu-id="f0295-214">**Type d'index**</span><span class="sxs-lookup"><span data-stu-id="f0295-214">**Index type**</span></span>  
     <span data-ttu-id="f0295-215">Type de l'index.</span><span class="sxs-lookup"><span data-stu-id="f0295-215">The type of index.</span></span> <span data-ttu-id="f0295-216">Les valeurs possibles sont **Index cluster**, **Index non-cluster**et **XML primaire**.</span><span class="sxs-lookup"><span data-stu-id="f0295-216">Possible values are **Clustered index**, **Nonclustered index**, and **Primary XML**.</span></span> <span data-ttu-id="f0295-217">Les tables peuvent également être stockées en tant que segment (sans index), mais dans ce cas la page Propriétés de l'index est impossible à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="f0295-217">Tables can also be stored as a heap (without indexes), but then this Index Properties page cannot be opened.</span></span>  
  
     <span data-ttu-id="f0295-218">**Lignes de niveau feuille**</span><span class="sxs-lookup"><span data-stu-id="f0295-218">**Leaf-level rows**</span></span>  
     <span data-ttu-id="f0295-219">Nombre de lignes de niveau feuille.</span><span class="sxs-lookup"><span data-stu-id="f0295-219">The number of leaf level rows.</span></span>  
  
     <span data-ttu-id="f0295-220">**Taille maximale de ligne**</span><span class="sxs-lookup"><span data-stu-id="f0295-220">**Maximum row size**</span></span>  
     <span data-ttu-id="f0295-221">Taille maximale des lignes de niveau feuille.</span><span class="sxs-lookup"><span data-stu-id="f0295-221">The maximum leaf-level row size.</span></span>  
  
     <span data-ttu-id="f0295-222">**Taille minimale de ligne**</span><span class="sxs-lookup"><span data-stu-id="f0295-222">**Minimum row size**</span></span>  
     <span data-ttu-id="f0295-223">Taille minimale des lignes de niveau feuille.</span><span class="sxs-lookup"><span data-stu-id="f0295-223">The minimum leaf-level row size.</span></span>  
  
     <span data-ttu-id="f0295-224">**Pages**</span><span class="sxs-lookup"><span data-stu-id="f0295-224">**Pages**</span></span>  
     <span data-ttu-id="f0295-225">Nombre total de pages de données.</span><span class="sxs-lookup"><span data-stu-id="f0295-225">The total number of data pages.</span></span>  
  
     <span data-ttu-id="f0295-226">**ID de partition**</span><span class="sxs-lookup"><span data-stu-id="f0295-226">**Partition ID**</span></span>  
     <span data-ttu-id="f0295-227">ID de partition de l'arbre B (B-tree) qui contient l'index.</span><span class="sxs-lookup"><span data-stu-id="f0295-227">The partition ID of the b-tree containing the index.</span></span>  
  
     <span data-ttu-id="f0295-228">**Enregistrement de version fantôme**</span><span class="sxs-lookup"><span data-stu-id="f0295-228">**Version ghost rows**</span></span>  
     <span data-ttu-id="f0295-229">Nombre d'enregistrements fantômes étant conservés en raison d'une transaction d'isolement d'instantané en attente.</span><span class="sxs-lookup"><span data-stu-id="f0295-229">The number of ghost records that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureFrag"></a> <span data-ttu-id="f0295-230">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0295-230">Using Transact-SQL</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="f0295-231">Pour vérifier la fragmentation d'un index</span><span class="sxs-lookup"><span data-stu-id="f0295-231">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="f0295-232">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0295-232">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0295-233">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f0295-233">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0295-234">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f0295-234">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find the average fragmentation percentage of all indexes  
    -- in the HumanResources.Employee table.   
    SELECT a.index_id, name, avg_fragmentation_in_percent  
    FROM sys.dm_db_index_physical_stats (DB_ID(N'AdventureWorks2012'), OBJECT_ID(N'HumanResources.Employee'), NULL, NULL, NULL) AS a  
        JOIN sys.indexes AS b ON a.object_id = b.object_id AND a.index_id = b.index_id;   
    GO  
    ```  
  
     <span data-ttu-id="f0295-235">L'instruction ci-dessus peut retourner un jeu de résultats similaire au suivant.</span><span class="sxs-lookup"><span data-stu-id="f0295-235">The statement above might return a result set similar to the following.</span></span>  
  
    ```  
    index_id    name                                                  avg_fragmentation_in_percent  
    ----------- ----------------------------------------------------- ----------------------------  
    1           PK_Employee_BusinessEntityID                          0  
    2           IX_Employee_OrganizationalNode                        0  
    3           IX_Employee_OrganizationalLevel_OrganizationalNode    0  
    5           AK_Employee_LoginID                                   66.6666666666667  
    6           AK_Employee_NationalIDNumber                          50  
    7           AK_Employee_rowguid                                   0  
  
    (6 row(s) affected)  
    ```  
  
 <span data-ttu-id="f0295-236">Pour plus d’informations, consultez [sys. dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0295-236">For more information, see  [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureReorg"></a> <span data-ttu-id="f0295-237">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0295-237">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-reorganize-or-rebuild-an-index"></a><span data-ttu-id="f0295-238">Pour réorganiser ou reconstruire un index</span><span class="sxs-lookup"><span data-stu-id="f0295-238">To reorganize or rebuild an index</span></span>  
  
1.  <span data-ttu-id="f0295-239">Dans l'Explorateur d'objets, développez la base de données qui contient la table sur laquelle vous souhaitez réorganiser un index.</span><span class="sxs-lookup"><span data-stu-id="f0295-239">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="f0295-240">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="f0295-240">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="f0295-241">Développez la table sur laquelle vous souhaitez réorganiser un index.</span><span class="sxs-lookup"><span data-stu-id="f0295-241">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="f0295-242">Développez le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="f0295-242">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="f0295-243">Cliquez avec le bouton droit sur l’index que vous souhaitez réorganiser et sélectionnez **Réorganiser**.</span><span class="sxs-lookup"><span data-stu-id="f0295-243">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="f0295-244">Dans la boîte de dialogue **Réorganiser les index** , vérifiez que l'index correct figure dans la grille **Index à réorganiser** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0295-244">In the **Reorganize Indexes** dialog box, verify that the correct index is in the **Indexes to be reorganized** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="f0295-245">Cochez la case **Compacter les données de la colonne d’objets volumineux** pour indiquer que toutes les pages qui contiennent des données LOB seront aussi compactées.</span><span class="sxs-lookup"><span data-stu-id="f0295-245">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="f0295-246">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0295-246">Click **OK.**</span></span>  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="f0295-247">Pour réorganiser tous les index d'une table</span><span class="sxs-lookup"><span data-stu-id="f0295-247">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="f0295-248">Dans l'Explorateur d'objets, développez la base de données qui contient la table sur laquelle vous souhaitez réorganiser les index.</span><span class="sxs-lookup"><span data-stu-id="f0295-248">In Object Explorer, Expand the database that contains the table on which you want to reorganize the indexes.</span></span>  
  
2.  <span data-ttu-id="f0295-249">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="f0295-249">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="f0295-250">Développez la table sur laquelle vous souhaitez réorganiser les index.</span><span class="sxs-lookup"><span data-stu-id="f0295-250">Expand the table on which you want to reorganize the indexes.</span></span>  
  
4.  <span data-ttu-id="f0295-251">Cliquez avec le bouton droit sur le dossier **Index** , puis sélectionnez **Réorganiser tout**.</span><span class="sxs-lookup"><span data-stu-id="f0295-251">Right-click the **Indexes** folder and select **Reorganize All**.</span></span>  
  
5.  <span data-ttu-id="f0295-252">Dans la boîte de dialogue **Réorganiser les index** , vérifiez que les index corrects sont dans **Index à réorganiser**.</span><span class="sxs-lookup"><span data-stu-id="f0295-252">In the **Reorganize Indexes** dialog box, verify that the correct indexes are in the **Indexes to be reorganized**.</span></span> <span data-ttu-id="f0295-253">Pour supprimer un index de la grille **Index à réorganiser** , sélectionnez l'index et appuyez sur la touche SUPPR.</span><span class="sxs-lookup"><span data-stu-id="f0295-253">To remove an index from the **Indexes to be reorganized** grid, select the index and then press the Delete key.</span></span>  
  
6.  <span data-ttu-id="f0295-254">Cochez la case **Compacter les données de la colonne d’objets volumineux** pour indiquer que toutes les pages qui contiennent des données LOB seront aussi compactées.</span><span class="sxs-lookup"><span data-stu-id="f0295-254">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
7.  <span data-ttu-id="f0295-255">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0295-255">Click **OK.**</span></span>  
  
#### <a name="to-rebuild-an-index"></a><span data-ttu-id="f0295-256">Pour reconstruire un index</span><span class="sxs-lookup"><span data-stu-id="f0295-256">To rebuild an index</span></span>  
  
1.  <span data-ttu-id="f0295-257">Dans l'Explorateur d'objets, développez la base de données qui contient la table sur laquelle vous souhaitez réorganiser un index.</span><span class="sxs-lookup"><span data-stu-id="f0295-257">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="f0295-258">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="f0295-258">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="f0295-259">Développez la table sur laquelle vous souhaitez réorganiser un index.</span><span class="sxs-lookup"><span data-stu-id="f0295-259">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="f0295-260">Développez le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="f0295-260">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="f0295-261">Cliquez avec le bouton droit sur l’index que vous souhaitez réorganiser et sélectionnez **Réorganiser**.</span><span class="sxs-lookup"><span data-stu-id="f0295-261">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="f0295-262">Dans la boîte de dialogue **Reconstruire les index** , vérifiez que l'index correct figure dans la grille **Index à reconstruire** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0295-262">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to be rebuilt** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="f0295-263">Cochez la case **Compacter les données de la colonne d’objets volumineux** pour indiquer que toutes les pages qui contiennent des données LOB seront aussi compactées.</span><span class="sxs-lookup"><span data-stu-id="f0295-263">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="f0295-264">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0295-264">Click **OK.**</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureReorg"></a> <span data-ttu-id="f0295-265">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0295-265">Using Transact-SQL</span></span>  
  
#### <a name="to-reorganize-a-defragmented-index"></a><span data-ttu-id="f0295-266">Pour réorganiser un index défragmenté</span><span class="sxs-lookup"><span data-stu-id="f0295-266">To reorganize a defragmented index</span></span>  
  
1.  <span data-ttu-id="f0295-267">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0295-267">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0295-268">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f0295-268">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0295-269">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f0295-269">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize the IX_Employee_OrganizationalLevel_OrganizationalNode index on the HumanResources.Employee table.   
  
    ALTER INDEX IX_Employee_OrganizationalLevel_OrganizationalNode ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="f0295-270">Pour réorganiser tous les index d'une table</span><span class="sxs-lookup"><span data-stu-id="f0295-270">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="f0295-271">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0295-271">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0295-272">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f0295-272">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0295-273">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f0295-273">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-rebuild-a-defragmented-index"></a><span data-ttu-id="f0295-274">Pour reconstruire un index défragmenté</span><span class="sxs-lookup"><span data-stu-id="f0295-274">To rebuild a defragmented index</span></span>  
  
1.  <span data-ttu-id="f0295-275">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0295-275">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0295-276">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f0295-276">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0295-277">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f0295-277">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f0295-278">L'exemple reconstruit un seul index portant sur la table `Employee` .</span><span class="sxs-lookup"><span data-stu-id="f0295-278">The example rebuilds a single index on the `Employee` table.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex1](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex1)]  
  
#### <a name="to-rebuild-all-indexes-in-a-table"></a><span data-ttu-id="f0295-279">Pour reconstruire tous les index d'une table</span><span class="sxs-lookup"><span data-stu-id="f0295-279">To rebuild all indexes in a table</span></span>  
  
1.  <span data-ttu-id="f0295-280">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0295-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0295-281">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f0295-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0295-282">Copiez et collez l'exemple suivant dans la fenêtre de requête. L'exemple spécifie le mot de passe `ALL`.</span><span class="sxs-lookup"><span data-stu-id="f0295-282">Copy and paste the following example into the query The example specifies the keyword `ALL`.</span></span> <span data-ttu-id="f0295-283">Ceci permet de reconstruire tous les index associés à la table.</span><span class="sxs-lookup"><span data-stu-id="f0295-283">This rebuilds all indexes associated with the table.</span></span> <span data-ttu-id="f0295-284">Trois options sont spécifiées.</span><span class="sxs-lookup"><span data-stu-id="f0295-284">Three options are specified.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="f0295-285">Pour plus d’informations, consultez [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0295-285">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0295-286">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0295-286">See Also</span></span>  
 [<span data-ttu-id="f0295-287">Meilleures pratiques de défragmentation d'index Microsoft SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="f0295-287">Microsoft SQL Server 2000 Index Defragmentation Best Practices</span></span>](https://technet.microsoft.com/library/cc966523.aspx)  
  
  
