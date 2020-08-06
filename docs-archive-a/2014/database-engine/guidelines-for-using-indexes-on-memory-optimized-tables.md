---
title: Instructions relatives à l’utilisation d’index sur des tables optimisées en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- hash indexes
ms.assetid: 16ef63a4-367a-46ac-917d-9eebc81ab29b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f00d643088634c918eb626917eae64a001ce3678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701562"
---
# <a name="guidelines-for-using-indexes-on-memory-optimized-tables"></a><span data-ttu-id="0b75d-102">Instructions pour utiliser les index sur les tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="0b75d-102">Guidelines for Using Indexes on Memory-Optimized Tables</span></span>
  <span data-ttu-id="0b75d-103">Les index sont utilisés pour accéder efficacement aux données dans les tables [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b75d-103">Indexes are used for efficiently accessing data in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="0b75d-104">Spécifier les index appropriés peut améliorer considérablement les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="0b75d-104">Specifying the right indexes can dramatically improve query performance.</span></span> <span data-ttu-id="0b75d-105">Par exemple, considérez la requête :</span><span class="sxs-lookup"><span data-stu-id="0b75d-105">Consider, for example, the query:</span></span>  
  
```sql  
SELECT c1, c2 FROM t WHERE c1 = 1;  
```  
  
 <span data-ttu-id="0b75d-106">S'il n'y a pas d'index sur la colonne c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] doit analyser la totalité de la table t, puis filtrer sur les lignes qui répondent à la condition c1=1.</span><span class="sxs-lookup"><span data-stu-id="0b75d-106">If there is no index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will need to scan the entire table t, and then filter on the rows that satisfy the condition c1=1.</span></span> <span data-ttu-id="0b75d-107">Toutefois, si t a un index sur la colonne c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] peut rechercher directement la valeur 1 et récupérer les lignes.</span><span class="sxs-lookup"><span data-stu-id="0b75d-107">However, if t has an index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can seek directly on the value 1 and retrieve the rows.</span></span>  
  
 <span data-ttu-id="0b75d-108">Lorsque vous recherchez des enregistrements ayant une valeur spécifique, ou une plage de valeurs, dans une ou plusieurs colonnes de la table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] peut utiliser un index sur ces colonnes pour localiser rapidement les enregistrements correspondants.</span><span class="sxs-lookup"><span data-stu-id="0b75d-108">When searching for records that have a specific value, or range of values, for one or more columns in the table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can use an index on those columns to quickly locate the corresponding records.</span></span> <span data-ttu-id="0b75d-109">Les tables sur disque et optimisées en mémoire tirent parti des index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-109">Both disk-based and memory-optimized tables benefit from indexes.</span></span> <span data-ttu-id="0b75d-110">Il existe, toutefois, certaines différences entre les structures d'index, dont il faut tenir compte lorsqu'on utilise des tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="0b75d-110">There are, however, certain differences between index structures that need to be considered when using memory-optimized tables.</span></span> <span data-ttu-id="0b75d-111">(Les index sur les tables optimisées en mémoire sont appelés des index optimisés en mémoire.) Voici quelques-unes des principales différences :</span><span class="sxs-lookup"><span data-stu-id="0b75d-111">(Indexes on memory-optimized tables are referred to as memory-optimized indexes.) Some of the key differences are:</span></span>  
  
-   <span data-ttu-id="0b75d-112">Les index à mémoire optimisée doivent être créés avec [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0b75d-112">Memory-optimized indexes must be created with [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span> <span data-ttu-id="0b75d-113">Les index sur disque peuvent être créés avec `CREATE TABLE` et `CREATE INDEX`.</span><span class="sxs-lookup"><span data-stu-id="0b75d-113">Disk-based indexes can be created with `CREATE TABLE` and `CREATE INDEX`.</span></span>  
  
-   <span data-ttu-id="0b75d-114">Les index optimisés en mémoire existent uniquement en mémoire.</span><span class="sxs-lookup"><span data-stu-id="0b75d-114">Memory-optimized indexes exist only in memory.</span></span> <span data-ttu-id="0b75d-115">Les structures d'index ne sont pas conservées sur le disque et les opérations d'index ne sont pas consignées dans le journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="0b75d-115">Index structures are not persisted to disk and index operations are not logged in the transaction log.</span></span> <span data-ttu-id="0b75d-116">La structure de l'index est créée lorsque la table optimisée en mémoire est créée dans la mémoire, au cours de CREATE TABLE et lors du démarrage de la base de données.</span><span class="sxs-lookup"><span data-stu-id="0b75d-116">The index structure is created when the memory-optimized table is created in memory, both during CREATE TABLE and during database startup.</span></span>  
  
-   <span data-ttu-id="0b75d-117">Les index optimisés en mémoire sont couvrants.</span><span class="sxs-lookup"><span data-stu-id="0b75d-117">Memory-optimized indexes are inherently covering.</span></span> <span data-ttu-id="0b75d-118">La couverture signifie que toutes les colonnes sont virtuellement incluses dans l'index, et que les recherches de signets ne sont pas nécessaires pour les tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="0b75d-118">Covering means that all columns are virtually included in the index and bookmark lookups are not needed for memory-optimized tables.</span></span> <span data-ttu-id="0b75d-119">Au lieu d'une référence à la clé primaire, les index optimisés en mémoire contiennent simplement un pointeur de mémoire sur la ligne réelle dans la structure de données de la table.</span><span class="sxs-lookup"><span data-stu-id="0b75d-119">Rather than a reference to the primary key, memory-optimized indexes simply contain a memory pointer to the actual row in the table data structure.</span></span>  
  
-   <span data-ttu-id="0b75d-120">Les concepts de fragmentation et de fillfactor ne s'appliquent pas aux index optimisés en mémoire.</span><span class="sxs-lookup"><span data-stu-id="0b75d-120">Fragmentation and fillfactor do not apply to memory-optimized indexes.</span></span> <span data-ttu-id="0b75d-121">Dans les index sur disque, la fragmentation fait référence aux pages de l'arbre B (B-tree) écrites sur le disque dans le désordre.</span><span class="sxs-lookup"><span data-stu-id="0b75d-121">In disk-based indexes, fragmentation refers to pages in the B-tree being written to disk out-of-order.</span></span> <span data-ttu-id="0b75d-122">Les index optimisés en mémoire ne sont pas écrits sur le disque, ou lus à partir de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="0b75d-122">Memory-optimized indexes are not written to or read from disk.</span></span> <span data-ttu-id="0b75d-123">Fillfactor dans les index d'arbre B (B-tree) sur disque fait référence au degré selon lequel les structures des pages physiques sont remplies avec des données réelles.</span><span class="sxs-lookup"><span data-stu-id="0b75d-123">Fillfactor in disk-based B-tree indexes refers to the degree to which the physical page structures are filled with actual data.</span></span> <span data-ttu-id="0b75d-124">Les structures d'index optimisés en mémoire n'ont pas de pages de taille fixe.</span><span class="sxs-lookup"><span data-stu-id="0b75d-124">The memory-optimized index structures do not have fixed-size pages.</span></span>  
  
 <span data-ttu-id="0b75d-125">Il existe deux types d'index optimisés en mémoire :</span><span class="sxs-lookup"><span data-stu-id="0b75d-125">There are two types of memory-optimized indexes:</span></span>  
  
-   <span data-ttu-id="0b75d-126">Les index de hachage non cluster, qui sont faits pour les recherches de point.</span><span class="sxs-lookup"><span data-stu-id="0b75d-126">Nonclustered hash indexes, which are made for point lookups.</span></span> <span data-ttu-id="0b75d-127">Pour plus d’informations sur les index de hachage, consultez [index de hachage](hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="0b75d-127">For more information about hash indexes, see [Hash Indexes](hash-indexes.md).</span></span>  
  
-   <span data-ttu-id="0b75d-128">Les index non cluster, qui sont faits pour les analyses de plage et les analyses triées.</span><span class="sxs-lookup"><span data-stu-id="0b75d-128">Nonclustered indexes, which are made for range scans and ordered scans.</span></span>  
  
 <span data-ttu-id="0b75d-129">Avec un index de hachage, les données sont accédées via une table de hachage en mémoire.</span><span class="sxs-lookup"><span data-stu-id="0b75d-129">With a hash index, data is accessed through an in-memory hash table.</span></span> <span data-ttu-id="0b75d-130">Les index de hachage n'ont pas de pages et sont toujours d'une taille fixe.</span><span class="sxs-lookup"><span data-stu-id="0b75d-130">Hash indexes do not have pages and are always of a fixed size.</span></span> <span data-ttu-id="0b75d-131">Toutefois, un index de hachage peut avoir des compartiments de hachage vides, ce qui aboutit à un espace gaspillé limité.</span><span class="sxs-lookup"><span data-stu-id="0b75d-131">However, a hash index can have empty hash buckets, which result in limited wasted space.</span></span> <span data-ttu-id="0b75d-132">Les valeurs retournées par une requête utilisant un index de hachage ne sont pas triées.</span><span class="sxs-lookup"><span data-stu-id="0b75d-132">The values returned from a query using a hash index are not sorted.</span></span> <span data-ttu-id="0b75d-133">Les index de hachage sont optimisés pour les recherches d'index sur les prédicats d'égalité et prennent également en charge les analyses complètes d'index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-133">Hash indexes are optimized for index seeks on equality predicates and also support full index scans.</span></span>  
  
 <span data-ttu-id="0b75d-134">Les index non cluster (pas les index de hachage) prennent en charge toutes les opérations prises en charge par les index de hachage en plus des opérations de recherche sur les prédicats d'inégalité comme supérieur ou inférieur à, ainsi que l'ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="0b75d-134">Nonclustered indexes (not hash indexes) support everything that hash indexes supports plus seek operations on inequality predicates such as greater than or less than, as well as sort order.</span></span> <span data-ttu-id="0b75d-135">Les lignes peuvent être récupérées selon l'ordre spécifié à la création de l'index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-135">Rows can be retrieved according to the order specified with index creation.</span></span> <span data-ttu-id="0b75d-136">Si l'ordre de tri de l'index représente l'ordre de tri requis pour une requête spécifique, par exemple si la clé d'index correspond à la clause ORDER BY, il n'est pas nécessaire de trier les lignes dans le cadre de l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="0b75d-136">If the sort order of the index matches the sort order required for a particular query, for example if the index key matches the ORDER BY clause, there is no need to sort the rows as part of query execution.</span></span> <span data-ttu-id="0b75d-137">Les index non cluster optimisés en mémoire sont unidirectionnels ; ils ne prennent pas en charge la récupération de lignes dans un ordre de tri qui est l'inverse de l'ordre de tri de l'index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-137">Memory-optimized nonclustered indexes are unidirectional; they do not support retrieving rows in a sort order that is the reverse of the sort order of the index.</span></span> <span data-ttu-id="0b75d-138">Par exemple, pour un index spécifié sous la forme (c1 ASC), il n'est pas possible d'analyser l'index dans l'ordre inverse, sous la forme (c1 DESC).</span><span class="sxs-lookup"><span data-stu-id="0b75d-138">For example, for an index specified as (c1 ASC), it is not possible to scan the index in reverse order, as (c1 DESC).</span></span>  
  
 <span data-ttu-id="0b75d-139">Chaque index consomme de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="0b75d-139">Each index consumes memory.</span></span> <span data-ttu-id="0b75d-140">Les index de hachage consomment une quantité fixe de mémoire, en fonction du nombre de compartiments.</span><span class="sxs-lookup"><span data-stu-id="0b75d-140">Hash indexes consume a fixed amount of memory, which is a function of the bucket count.</span></span> <span data-ttu-id="0b75d-141">Pour les index non cluster, la consommation de mémoire est une fonction du nombre de lignes et de la taille des colonnes clés d'index, avec une surcharge supplémentaire dépendant de la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="0b75d-141">For nonclustered indexes, memory consumption is a function of the row count and the size of the index key columns, with some additional overhead depending on the workload.</span></span> <span data-ttu-id="0b75d-142">La mémoire pour les index optimisés en mémoire est en plus et est distincte de la mémoire utilisée pour stocker les lignes dans les tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="0b75d-142">Memory for memory-optimized indexes is in addition to and separate from the memory used to store rows in memory-optimized tables.</span></span>  
  
 <span data-ttu-id="0b75d-143">Les valeurs de clé en double partagent le même compartiment de hachage.</span><span class="sxs-lookup"><span data-stu-id="0b75d-143">Duplicate key values always share the same hash bucket.</span></span> <span data-ttu-id="0b75d-144">Si un index de hachage contient plusieurs clés en double, les chaînes de hachage longues qui en résulte auront un impact sur les performances.</span><span class="sxs-lookup"><span data-stu-id="0b75d-144">If a hash index contains many duplicate key values, the resulting long hash chains will harm performance.</span></span> <span data-ttu-id="0b75d-145">Les collisions de hachage, qui se produisent dans un index de hachage, réduisent également les performances dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="0b75d-145">Hash collisions, which occur in any hash index, will further reduce performance in this scenario.</span></span> <span data-ttu-id="0b75d-146">Pour cette raison, si le nombre de clés d’index uniques est au moins de 100 fois plus petit que le nombre de lignes, vous pouvez réduire le risque de collisions de hachage en rendant le nombre de compartiments plus grand (au moins huit fois le nombre de clés d’index uniques. pour plus d’informations, consultez [détermination du nombre de compartiments correct pour les index de hachage](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) )</span><span class="sxs-lookup"><span data-stu-id="0b75d-146">For that reason, if the number of unique index keys is at least 100 times smaller than the row count, you can reduce the risk of hash collisions by making the bucket count much larger (at least eight times the number of unique index keys; see [Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) for more information) or you can eliminate hash collisions entirely by using a nonclustered index.</span></span>  
  
## <a name="determining-which-indexes-to-use-for-a-memory-optimized-table"></a><span data-ttu-id="0b75d-147">Détermination des index à utiliser pour une table optimisée en mémoire</span><span class="sxs-lookup"><span data-stu-id="0b75d-147">Determining Which Indexes to Use for a Memory-Optimized Table</span></span>  
 <span data-ttu-id="0b75d-148">Chaque table optimisée en mémoire doit avoir au moins un index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-148">Each memory-optimized table must have at least one index.</span></span> <span data-ttu-id="0b75d-149">Notez que chaque contrainte PRIMARY KEY crée implicitement un index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-149">Note that each PRIMARY KEY constraint implicitly creates an index.</span></span> <span data-ttu-id="0b75d-150">Par conséquent, si une table possède une clé primaire, elle possède un index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-150">Therefore, if a table has a primary key, it has an index.</span></span> <span data-ttu-id="0b75d-151">Une clé primaire est requise pour une table optimisée en mémoire durable.</span><span class="sxs-lookup"><span data-stu-id="0b75d-151">A primary key is a requirement for a durable memory-optimized table.</span></span>  
  
 <span data-ttu-id="0b75d-152">Lors de l'interrogation d'une table optimisée en mémoire, les index de hachage s'avèrent plus efficaces si la clause de prédicat contient uniquement des prédicats d'égalité.</span><span class="sxs-lookup"><span data-stu-id="0b75d-152">When querying a memory-optimized table, hash indexes perform better when the predicate clause contains only equality predicates.</span></span> <span data-ttu-id="0b75d-153">Le prédicat doit inclure toutes les colonnes dans la clé d'index de hachage.</span><span class="sxs-lookup"><span data-stu-id="0b75d-153">The predicate must include all columns in the hash index key.</span></span> <span data-ttu-id="0b75d-154">Un index de hachage rétablit une analyse en fonction d'un prédicat d'inégalité.</span><span class="sxs-lookup"><span data-stu-id="0b75d-154">A hash index will revert to a scan given an inequality predicate.</span></span>  
  
 <span data-ttu-id="0b75d-155">Une colonne dans une table optimisée en mémoire peut faire partie d'un index de hachage et d'un index non cluster.</span><span class="sxs-lookup"><span data-stu-id="0b75d-155">A column in a memory-optimized table can be part of both a hash index and a nonclustered index.</span></span>  
  
 <span data-ttu-id="0b75d-156">Lors de l'interrogation d'une table optimisée en mémoire avec des prédicats d'inégalité, les index non cluster s'avèrent plus efficaces que les index de hachage non cluster.</span><span class="sxs-lookup"><span data-stu-id="0b75d-156">When querying a memory-optimized table with inequality predicates, nonclustered indexes will perform better than nonclustered hash indexes.</span></span>  
  
 <span data-ttu-id="0b75d-157">L'index de hachage nécessite une clé (pour hacher) pour rechercher dans l'index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-157">The hash index requires a key (to hash) to seek into the index.</span></span> <span data-ttu-id="0b75d-158">Si une clé d'index est constituée de deux colonnes et vous indiquez uniquement la première colonne, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ne dispose pas d'une clé complète pour hacher.</span><span class="sxs-lookup"><span data-stu-id="0b75d-158">If an index key consists of two columns and you only provide the first column, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a complete key to hash.</span></span> <span data-ttu-id="0b75d-159">Cela génère un plan de requête d'analyse d'index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-159">This will result in an index scan query plan.</span></span> <span data-ttu-id="0b75d-160">L'utilisation détermine les colonnes qui doivent être indexées.</span><span class="sxs-lookup"><span data-stu-id="0b75d-160">Usage determines which columns should be indexed.</span></span>  
  
 <span data-ttu-id="0b75d-161">Lorsqu'une colonne dans un index non cluster a la même valeur dans plusieurs de lignes (les colonnes clés d'index ont plusieurs valeurs dupliquées), cela peut nuire aux performances lors des mises à jour, des insertions et des suppressions.</span><span class="sxs-lookup"><span data-stu-id="0b75d-161">When a column in a nonclustered index has the same value in many rows (index key columns have a lot of duplicate values), performance can degrade for updates, inserts, and deletions.</span></span>  <span data-ttu-id="0b75d-162">Une façon d'améliorer les performances dans cette situation consiste à ajouter une autre colonne à l'index non cluster.</span><span class="sxs-lookup"><span data-stu-id="0b75d-162">One way to improve performance in this situation is to add another column to the nonclustered index.</span></span>  
  
### <a name="operations-on-memory-optimized-and-disk-based-indexes"></a><span data-ttu-id="0b75d-163">Opérations sur les index optimisés en mémoire et les index sur disque.</span><span class="sxs-lookup"><span data-stu-id="0b75d-163">Operations on memory-optimized and disk-based indexes.</span></span>  
  
|<span data-ttu-id="0b75d-164">Opération</span><span class="sxs-lookup"><span data-stu-id="0b75d-164">Operation</span></span>|<span data-ttu-id="0b75d-165">Index de hachage non cluster optimisé en mémoire</span><span class="sxs-lookup"><span data-stu-id="0b75d-165">Memory-optimized, nonclustered hash, index</span></span>|<span data-ttu-id="0b75d-166">Index non cluster optimisé en mémoire</span><span class="sxs-lookup"><span data-stu-id="0b75d-166">Memory-optimized nonclustered index</span></span>|<span data-ttu-id="0b75d-167">Index sur disque</span><span class="sxs-lookup"><span data-stu-id="0b75d-167">Disk-based index</span></span>|  
|---------------|-------------------------------------------------|------------------------------------------|-----------------------|  
|<span data-ttu-id="0b75d-168">Analyse d'index, récupère toutes les lignes de la table.</span><span class="sxs-lookup"><span data-stu-id="0b75d-168">Index Scan, retrieve all table rows.</span></span>|<span data-ttu-id="0b75d-169">Oui</span><span class="sxs-lookup"><span data-stu-id="0b75d-169">Yes</span></span>|<span data-ttu-id="0b75d-170">Oui</span><span class="sxs-lookup"><span data-stu-id="0b75d-170">Yes</span></span>|<span data-ttu-id="0b75d-171">Oui</span><span class="sxs-lookup"><span data-stu-id="0b75d-171">Yes</span></span>|  
|<span data-ttu-id="0b75d-172">Recherche d'index sur les prédicats d'égalité (=).</span><span class="sxs-lookup"><span data-stu-id="0b75d-172">Index seek on equality predicate(s) (=).</span></span>|<span data-ttu-id="0b75d-173">Oui</span><span class="sxs-lookup"><span data-stu-id="0b75d-173">Yes</span></span><br /><br /> <span data-ttu-id="0b75d-174">(Clé complète requise.)</span><span class="sxs-lookup"><span data-stu-id="0b75d-174">(Full key required.)</span></span>|<span data-ttu-id="0b75d-175">Oui <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0b75d-175">Yes <sup>1</sup></span></span>|<span data-ttu-id="0b75d-176">Oui</span><span class="sxs-lookup"><span data-stu-id="0b75d-176">Yes</span></span>|  
|<span data-ttu-id="0b75d-177">Recherche d’index sur les prédicats d’inégalité (>, <, \<=, > =, between).</span><span class="sxs-lookup"><span data-stu-id="0b75d-177">Index seek on inequality predicates (>, <, \<=, >=, BETWEEN).</span></span>|<span data-ttu-id="0b75d-178">Non (résulte dans une analyse d'index)</span><span class="sxs-lookup"><span data-stu-id="0b75d-178">No (results in an index scan)</span></span>|<span data-ttu-id="0b75d-179">Oui <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0b75d-179">Yes <sup>1</sup></span></span>|<span data-ttu-id="0b75d-180">Oui</span><span class="sxs-lookup"><span data-stu-id="0b75d-180">Yes</span></span>|  
|<span data-ttu-id="0b75d-181">Récupérez les lignes selon un ordre de tri qui correspond à la définition de l'index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-181">Retrieve rows in a sort-order matching the index definition.</span></span>|<span data-ttu-id="0b75d-182">Non</span><span class="sxs-lookup"><span data-stu-id="0b75d-182">No</span></span>|<span data-ttu-id="0b75d-183">Oui</span><span class="sxs-lookup"><span data-stu-id="0b75d-183">Yes</span></span>|<span data-ttu-id="0b75d-184">Oui</span><span class="sxs-lookup"><span data-stu-id="0b75d-184">Yes</span></span>|  
|<span data-ttu-id="0b75d-185">Récupérez les lignes selon un ordre de tri inverse par rapport à la définition de l'index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-185">Retrieve rows in a sort-order matching the reverse of the index definition.</span></span>|<span data-ttu-id="0b75d-186">Non</span><span class="sxs-lookup"><span data-stu-id="0b75d-186">No</span></span>|<span data-ttu-id="0b75d-187">Non</span><span class="sxs-lookup"><span data-stu-id="0b75d-187">No</span></span>|<span data-ttu-id="0b75d-188">Oui</span><span class="sxs-lookup"><span data-stu-id="0b75d-188">Yes</span></span>|  
  
 <span data-ttu-id="0b75d-189">Dans la table, Oui signifie que l'index peut traiter la demande et Non signifie que l'index ne peut pas être utilisé pour répondre à cette demande.</span><span class="sxs-lookup"><span data-stu-id="0b75d-189">In the table, Yes means that the index can adequately service the request and No means that the index cannot be used successfully to satisfy the request.</span></span>  
  
 <span data-ttu-id="0b75d-190"><sup>1</sup> pour un index optimisé en mémoire non cluster, la clé complète n’est pas requise pour effectuer une recherche d’index.</span><span class="sxs-lookup"><span data-stu-id="0b75d-190"><sup>1</sup> For a nonclustered memory-optimized index, the full key is not required to perform an index seek.</span></span> <span data-ttu-id="0b75d-191">Même si, en fonction de l'ordre des colonnes de la clé d'index, une analyse se produit si une valeur d'une colonne vient après une colonne manquante.</span><span class="sxs-lookup"><span data-stu-id="0b75d-191">Although, given the column order of the index key, a scan will occur if a value for a column comes after a missing column.</span></span>  
  
## <a name="index-count"></a><span data-ttu-id="0b75d-192">Nombre d'index</span><span class="sxs-lookup"><span data-stu-id="0b75d-192">Index Count</span></span>  
 <span data-ttu-id="0b75d-193">Une table optimisée en mémoire peut avoir jusqu'à 8 index, y compris l'index créé avec la clé primaire.</span><span class="sxs-lookup"><span data-stu-id="0b75d-193">A memory-optimized table can have up to 8 indexes, including the index created with the primary key.</span></span>  
  
 <span data-ttu-id="0b75d-194">En ce qui concerne le nombre d'index créés sur une table optimisée en mémoire, tenez compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0b75d-194">Regarding the number of indexes created on a memory-optimized table, consider the following:</span></span>  
  
-   <span data-ttu-id="0b75d-195">Spécifiez les index dont vous avez besoin lors de la création de la table.</span><span class="sxs-lookup"><span data-stu-id="0b75d-195">Specify the indexes you need when you create the table.</span></span> <span data-ttu-id="0b75d-196">Vous ne pouvez pas créer d'index pour une table optimisée en mémoire après la création de la table.</span><span class="sxs-lookup"><span data-stu-id="0b75d-196">You cannot create an index for a memory-optimized table after the table is created.</span></span> <span data-ttu-id="0b75d-197">Si vous souhaitez ajouter un index sur une table optimisée en mémoire, supprimez et recréez cette table.</span><span class="sxs-lookup"><span data-stu-id="0b75d-197">If you want to add an index to a memory-optimized table, drop and recreate that table.</span></span>  
  
-   <span data-ttu-id="0b75d-198">Ne créez pas d'index que vous utilisez rarement :</span><span class="sxs-lookup"><span data-stu-id="0b75d-198">Do not create an index that you rarely use:</span></span>  
  
     <span data-ttu-id="0b75d-199">Le nettoyage de la mémoire fonctionne mieux si tous les index de la table sont utilisés fréquemment.</span><span class="sxs-lookup"><span data-stu-id="0b75d-199">Garbage collection works best if all indexes on the table are frequently used.</span></span> <span data-ttu-id="0b75d-200">Les index rarement utilisés peuvent entraîner un fonctionnement non optimal du système de nettoyage de la mémoire pour les anciennes versions de ligne.</span><span class="sxs-lookup"><span data-stu-id="0b75d-200">Rarely-used indexes may cause the garbage collection system to not perform optimally for old row versions.</span></span>  
  
## <a name="creating-a-memory-optimized-index-code-samples"></a><span data-ttu-id="0b75d-201">Création d'un index mémoire optimisé : exemples de code</span><span class="sxs-lookup"><span data-stu-id="0b75d-201">Creating a Memory-Optimized Index: Code Samples</span></span>  
 <span data-ttu-id="0b75d-202">Index de hachage au niveau des colonnes :</span><span class="sxs-lookup"><span data-stu-id="0b75d-202">Column level hash index:</span></span>  
  
```sql  
CREATE TABLE t1   
   (c1 INT NOT NULL INDEX idx HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="0b75d-203">Index de hachage au niveau des tables :</span><span class="sxs-lookup"><span data-stu-id="0b75d-203">Table level hash index:</span></span>  
  
```sql  
CREATE TABLE t1_1   
   (c1 INT NOT NULL,   
   INDEX IDX HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="0b75d-204">Index de hachage de clé primaire au niveau des colonnes :</span><span class="sxs-lookup"><span data-stu-id="0b75d-204">Column level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="0b75d-205">Index de hachage de clé primaire au niveau des tables :</span><span class="sxs-lookup"><span data-stu-id="0b75d-205">Table level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2_2   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="0b75d-206">Index non cluster au niveau de la colonne :</span><span class="sxs-lookup"><span data-stu-id="0b75d-206">Column level nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t3   
   (c1 INT NOT NULL INDEX ID)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="0b75d-207">Index non cluster au niveau de la table :</span><span class="sxs-lookup"><span data-stu-id="0b75d-207">Table level nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t3_3   
   (c1 INT NOT NULL,   
   INDEX IDX NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="0b75d-208">Index non cluster de clé primaire au niveau de la colonne :</span><span class="sxs-lookup"><span data-stu-id="0b75d-208">Column level primary key nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t4   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="0b75d-209">Index non cluster de clé primaire de niveau table :</span><span class="sxs-lookup"><span data-stu-id="0b75d-209">Table level primary key nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t4_4   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="0b75d-210">Index multicolonne défini après la définition des colonnes :</span><span class="sxs-lookup"><span data-stu-id="0b75d-210">Multicolumn index defined after columns are defined:</span></span>  
  
```sql  
create table t (  
       a int not null constraint ta primary key nonclustered,  
       b int not null,  
       c int not null,  
       d int not null,  
       index idx_t_b_c_d nonclustered (b, c asc, d desc)  
) with (memory_optimized = on, durability = SCHEMA_AND_DATA)  
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b75d-211">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b75d-211">See Also</span></span>  
 <span data-ttu-id="0b75d-212">[Index sur les tables optimisées en mémoire](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="0b75d-212">[Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="0b75d-213">[Détermination du nombre de compartiments correct pour les index de hachage](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="0b75d-213">[Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span></span>  
 [<span data-ttu-id="0b75d-214">Index de hachage</span><span class="sxs-lookup"><span data-stu-id="0b75d-214">Hash Indexes</span></span>](hash-indexes.md)  
  
  
