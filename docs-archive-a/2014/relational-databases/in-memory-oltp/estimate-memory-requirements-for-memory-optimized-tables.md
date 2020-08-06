---
title: Estimer les besoins en mémoire des tables optimisées en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5c5cc1fc-1fdf-4562-9443-272ad9ab5ba8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5c5218a96d3650cbae22501ab2794b1b553996b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706504"
---
# <a name="estimate-memory-requirements-for-memory-optimized-tables"></a><span data-ttu-id="48b8f-102">Estimer les besoins en mémoire des tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="48b8f-102">Estimate Memory Requirements for Memory-Optimized Tables</span></span>
  <span data-ttu-id="48b8f-103">Que vous soyez en train de créer une [!INCLUDE[hek_2](../../includes/hek-2-md.md)] table optimisée en mémoire ou de migrer une table sur disque existante vers une table optimisée en mémoire, il est important d’avoir une estimation raisonnable des besoins en mémoire de chaque table afin que vous puissiez approvisionner le serveur avec suffisamment de mémoire.</span><span class="sxs-lookup"><span data-stu-id="48b8f-103">Whether you are creating a new [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized table or migrating an existing disk-based table to a memory-optimized table, it is important to have a reasonable estimate of each table's memory needs so you can provision the server with sufficient memory.</span></span> <span data-ttu-id="48b8f-104">Cette section explique comment estimer la quantité de mémoire nécessaire pour accueillir les données d'une table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="48b8f-104">This section describes how to estimate the amount of memory that you need to hold data for a memory-optimized table.</span></span>  
  
 <span data-ttu-id="48b8f-105">Si vous envisagez d’effectuer une migration à partir de tables sur disque vers des tables optimisées en mémoire, avant de poursuivre la lecture de cette rubrique, consultez [Déterminer si une table ou une procédure stockée doit être déplacée vers l’OLTP en mémoire](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) pour obtenir des conseils sur les tables les plus judicieuses à faire migrer.</span><span class="sxs-lookup"><span data-stu-id="48b8f-105">If you are contemplating migrating from disk-based tables to memory-optimized tables, before you proceed in this topic, see the topic [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) for guidance on which tables are best to migrate.</span></span> <span data-ttu-id="48b8f-106">Toutes les rubriques sous [Migration vers OLTP en mémoire](migrating-to-in-memory-oltp.md) fournissent des conseils sur la migration à partir de tables sur disque vers des tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="48b8f-106">All the topics under [Migrating to In-Memory OLTP](migrating-to-in-memory-oltp.md) provide guidance on migrating from disk-based to memory-optimized tables.</span></span>  
  
## <a name="sections-in-this-topic"></a><span data-ttu-id="48b8f-107">Sections de cette rubrique</span><span class="sxs-lookup"><span data-stu-id="48b8f-107">Sections in this topic</span></span>  
  
-   [<span data-ttu-id="48b8f-108">Exemple de table optimisée en mémoire</span><span class="sxs-lookup"><span data-stu-id="48b8f-108">Example memory-optimized table</span></span>](#bkmk_ExampleTable)  
  
-   [<span data-ttu-id="48b8f-109">Mémoire pour la table</span><span class="sxs-lookup"><span data-stu-id="48b8f-109">Memory for the table</span></span>](#bkmk_MemoryForTable)  
  
-   [<span data-ttu-id="48b8f-110">Mémoire pour les index</span><span class="sxs-lookup"><span data-stu-id="48b8f-110">Memory for indexes</span></span>](#bkmk_IndexMeemory)  
  
-   [<span data-ttu-id="48b8f-111">Mémoire pour le contrôle de version de ligne</span><span class="sxs-lookup"><span data-stu-id="48b8f-111">Memory for row versioning</span></span>](#bkmk_MemoryForRowVersions)  
  
-   [<span data-ttu-id="48b8f-112">Mémoire pour les variables de table</span><span class="sxs-lookup"><span data-stu-id="48b8f-112">Memory for table variables</span></span>](#bkmk_TableVariables)  
  
-   [<span data-ttu-id="48b8f-113">Mémoire pour la croissance</span><span class="sxs-lookup"><span data-stu-id="48b8f-113">Memory for growth</span></span>](#bkmk_MemoryForGrowth)  
  
##  <a name="example-memory-optimized-table"></a><a name="bkmk_ExampleTable"></a> <span data-ttu-id="48b8f-114">Exemple de table optimisée en mémoire</span><span class="sxs-lookup"><span data-stu-id="48b8f-114">Example memory-optimized table</span></span>  
 <span data-ttu-id="48b8f-115">Prenons le schéma de table mémoire optimisée suivant :</span><span class="sxs-lookup"><span data-stu-id="48b8f-115">Consider the following memory-optimized table schema:</span></span>  
  
```sql  
  
CREATE TABLE t_hk (  
col1 int NOT NULL PRIMARY KEY NONCLUSTERED,  
col2 int NOT NULL INDEX t1c2_index   
     HASH WITH (bucket_count = 5000000),  
col3 int NOT NULL INDEX t1c3_index   
     HASH WITH (bucket_count = 5000000),  
col4 int NOT NULL INDEX t1c4_index   
     HASH WITH (bucket_count = 5000000),  
col5 int NOT NULL INDEX t1c5_index NONCLUSTERED,  
col6 char (50) NOT NULL,  
col7 char (50) NOT NULL,   
col8 char (30) NOT NULL,   
col9 char (50) NOT NULL  
     WITH (memory_optimized = on)  
GO  
  
```  
  
 <span data-ttu-id="48b8f-116">Ce schéma va permettre de déterminer la mémoire minimale requise pour cette table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="48b8f-116">Using this schema we will determine the minimum memory needed for this memory-optimized table.</span></span>  
  
##  <a name="memory-for-the-table"></a><a name="bkmk_MemoryForTable"></a> <span data-ttu-id="48b8f-117">Mémoire pour la table</span><span class="sxs-lookup"><span data-stu-id="48b8f-117">Memory for the table</span></span>  
 <span data-ttu-id="48b8f-118">Une ligne de table mémoire optimisée est composée de trois parties :</span><span class="sxs-lookup"><span data-stu-id="48b8f-118">A memory-optimized table row is comprised of three parts:</span></span>  
  
-   <span data-ttu-id="48b8f-119">**Horodateurs** </span><span class="sxs-lookup"><span data-stu-id="48b8f-119">**Timestamps** </span></span>  
    <span data-ttu-id="48b8f-120">En-tête de ligne/horodateurs = 24 octets.</span><span class="sxs-lookup"><span data-stu-id="48b8f-120">Row header/timestamps = 24 bytes.</span></span>  
  
-   <span data-ttu-id="48b8f-121">**Pointeurs d’index** </span><span class="sxs-lookup"><span data-stu-id="48b8f-121">**Index pointers** </span></span>  
    <span data-ttu-id="48b8f-122">Pour chaque index de hachage dans la table, chaque ligne a un pointeur d'adresse 8 octets vers la ligne suivante dans l'index.</span><span class="sxs-lookup"><span data-stu-id="48b8f-122">For each hash index in the table, each row has an 8-byte address pointer to the next row in the index.</span></span>  <span data-ttu-id="48b8f-123">Étant donné qu'il y a 4 index, chaque ligne alloue 32 octets pour les pointeurs d'index (pointeur de 8 octets pour chaque index).</span><span class="sxs-lookup"><span data-stu-id="48b8f-123">Since there are 4 indexes, each row will allocate 32 bytes for index pointers (an 8 byte pointer for each index).</span></span>  
  
-   <span data-ttu-id="48b8f-124">**Données** </span><span class="sxs-lookup"><span data-stu-id="48b8f-124">**Data** </span></span>  
    <span data-ttu-id="48b8f-125">La taille de la partie données de la ligne est déterminé en additionnant la taille du type pour chaque colonne de données.</span><span class="sxs-lookup"><span data-stu-id="48b8f-125">The size of the data portion of the row is determined by summing the type size for each data column.</span></span>  <span data-ttu-id="48b8f-126">Dans notre table, il y a cinq entiers de 4 octets, trois colonnes de type caractère de 50 octets et une colonne de type caractère de 30 octets.</span><span class="sxs-lookup"><span data-stu-id="48b8f-126">In our table we have five 4-byte integers, three 50-byte character columns, and one 30-byte character column.</span></span>  <span data-ttu-id="48b8f-127">Par conséquent, la partie données de chaque ligne est de 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 ou 200 octets.</span><span class="sxs-lookup"><span data-stu-id="48b8f-127">Therefore the data portion of each row is 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 or 200 bytes.</span></span>  
  
 <span data-ttu-id="48b8f-128">Voici un calcul de taille de 5 millions de lignes dans une table mémoire optimisée :</span><span class="sxs-lookup"><span data-stu-id="48b8f-128">The following is a size computation for 5,000,000 (5 million) rows in a memory-optimized table.</span></span> <span data-ttu-id="48b8f-129">La quantité totale de mémoire utilisée par les lignes de données estimée est la suivante :</span><span class="sxs-lookup"><span data-stu-id="48b8f-129">The total memory used by data rows is estimated as follows:</span></span>  
  
 <span data-ttu-id="48b8f-130">**Mémoire pour les lignes de la table**</span><span class="sxs-lookup"><span data-stu-id="48b8f-130">**Memory for the table's rows**</span></span>  
  
 <span data-ttu-id="48b8f-131">Selon les calculs ci-dessus, la taille de chaque ligne de la table mémoire optimisée est de 24 + 32 + 200, ou 256 octets.</span><span class="sxs-lookup"><span data-stu-id="48b8f-131">From the above calculations, the size of each row in the memory-optimized table is 24 + 32 + 200, or 256 bytes.</span></span>  <span data-ttu-id="48b8f-132">Étant donné qu’il y a 5 millions de lignes, la table consommera 5 000 000 \* 256 octets, ou 1 280 000 000 octets (soit environ 1,28 Go).</span><span class="sxs-lookup"><span data-stu-id="48b8f-132">Since we have 5 million rows, the table will consume 5,000,000 \* 256 bytes, or 1,280,000,000 bytes - approximately 1.28 GB.</span></span>  
  
##  <a name="memory-for-indexes"></a><a name="bkmk_IndexMeemory"></a> <span data-ttu-id="48b8f-133">Mémoire pour les index</span><span class="sxs-lookup"><span data-stu-id="48b8f-133">Memory for indexes</span></span>  
 <span data-ttu-id="48b8f-134">**Mémoire pour chaque index de hachage**</span><span class="sxs-lookup"><span data-stu-id="48b8f-134">**Memory for each hash index**</span></span>  
  
 <span data-ttu-id="48b8f-135">Chaque index de hachage est un tableau de hachage de pointeurs d'adresse 8 octets.</span><span class="sxs-lookup"><span data-stu-id="48b8f-135">Each hash index is a hash array of 8-byte address pointers.</span></span>  <span data-ttu-id="48b8f-136">La taille du tableau est mieux déterminée par le nombre de valeurs d’index uniques pour cet index, par exemple le nombre de valeurs uniques Col2 est un bon point de départ pour la taille du tableau de t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="48b8f-136">The size of the array is best determined by the number of unique index values for that index - e.g., the number of unique Col2 values is a good starting point for the array size for the t1c2_index.</span></span> <span data-ttu-id="48b8f-137">Un tableau de hachage qui est trop grand gaspille de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="48b8f-137">A hash array that is too big wastes memory.</span></span>  <span data-ttu-id="48b8f-138">Un tableau de hachage qui est trop petit ralentit les performances, car il y a trop de collisions par valeurs d'index qui hachent au même index.</span><span class="sxs-lookup"><span data-stu-id="48b8f-138">A hash array that is too small slows performance since there will be too many collisions by index values that hash to the same index.</span></span>  
  
 <span data-ttu-id="48b8f-139">Les index de hachage exécutent des recherches d'égalité rapides, notamment :</span><span class="sxs-lookup"><span data-stu-id="48b8f-139">Hash indexes achieve very fast equality lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 = 3  
  
```  
  
 <span data-ttu-id="48b8f-140">Les index non cluster sont plus rapides pour les recherches de plage suivantes :</span><span class="sxs-lookup"><span data-stu-id="48b8f-140">Nonclustered indexes are faster for range lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 >= 3  
  
```  
  
 <span data-ttu-id="48b8f-141">Si vous migrez une table basée sur disque, utilisez les éléments suivants pour déterminer le nombre de valeurs uniques de l'index t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="48b8f-141">If you are migrating a disk-based table you can use the following to determine the number of unique values for the index t1c2_index.</span></span>  
  
```sql  
  
SELECT COUNT(DISTINCT [Col2])  
  FROM t_hk  
  
```  
  
 <span data-ttu-id="48b8f-142">Si vous créez une table, vous devrez évaluer la taille du tableau ou regrouper les données de votre test avant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="48b8f-142">If you are creating a new table, you'll need to estimate the array size or gather data from your testing prior to deployment.</span></span>  
  
 <span data-ttu-id="48b8f-143">Pour plus d’informations sur le fonctionnement des index de hachage dans les tables optimisées en mémoire [!INCLUDE[hek_2](../../includes/hek-2-md.md)] , consultez [Index de hachage](../../database-engine/hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="48b8f-143">For information on how hash indexes work in [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized tables, see [Hash Indexes](../../database-engine/hash-indexes.md).</span></span>  
  
 <span data-ttu-id="48b8f-144">**Remarque :** Vous ne pouvez pas modifier la taille du tableau d’index de hachage à la volée.</span><span class="sxs-lookup"><span data-stu-id="48b8f-144">**Note:** You cannot change the hash index array size on the fly.</span></span> <span data-ttu-id="48b8f-145">Pour modifier la taille du tableau d'index de hachage, vous devez supprimer la table, modifier la valeur bucket_count et recréer la table.</span><span class="sxs-lookup"><span data-stu-id="48b8f-145">To change the hash index array size you must drop the table, change the bucket_count value and recreate the table.</span></span>  
  
 <span data-ttu-id="48b8f-146">**Définition de la taille du tableau d'index de hachage**</span><span class="sxs-lookup"><span data-stu-id="48b8f-146">**Setting the hash index array size**</span></span>  
  
 <span data-ttu-id="48b8f-147">La taille du tableau d’index de hachage est définie par `(bucket_count= <value>)` où \<value> est un entier supérieur à zéro.</span><span class="sxs-lookup"><span data-stu-id="48b8f-147">The hash array size is set by `(bucket_count= <value>)` where \<value> is an integer value greater than zero.</span></span> <span data-ttu-id="48b8f-148">Si \<value> n’est pas une puissance de 2, le nombre réel de compartiments (bucket_count) est arrondi à la puissance de 2 supérieur la plus proche.</span><span class="sxs-lookup"><span data-stu-id="48b8f-148">If \<value> is not a power of 2, the actual bucket_count is rounded up to the next closest power of 2.</span></span>  <span data-ttu-id="48b8f-149">Dans notre exemple de table, (bucket_count = 5 millions), étant donné que 5 millions n’est pas une puissance de 2, le nombre réel de compartiments est arrondi à 8 388 608 (2<sup>23</sup>).</span><span class="sxs-lookup"><span data-stu-id="48b8f-149">In our example table, (bucket_count = 5000000), since 5,000,000 is not a power of 2, the actual bucket count rounds up to 8,388,608 (2<sup>23</sup>).</span></span>  <span data-ttu-id="48b8f-150">Vous devez utiliser ce nombre, et non pas 5 000 000, lorsque vous calculez la mémoire nécessaire pour le tableau de hachage.</span><span class="sxs-lookup"><span data-stu-id="48b8f-150">You must use this number, not 5,000,000 when calculating memory needed by the hash array.</span></span>  
  
 <span data-ttu-id="48b8f-151">Ainsi, dans notre exemple, la mémoire nécessaire pour chaque tableau de hachage est :</span><span class="sxs-lookup"><span data-stu-id="48b8f-151">Thus, in our example, the memory needed for each hash array is:</span></span>  
  
 <span data-ttu-id="48b8f-152">8 388 608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67 108 864 ou environ 64 Mo.</span><span class="sxs-lookup"><span data-stu-id="48b8f-152">8,388,608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67,108,864 or approximately 64 MB.</span></span>  
  
 <span data-ttu-id="48b8f-153">Comme il y a trois index de hachage, la mémoire nécessaire pour les index de hachage est de 3 \* 64 Mo = 192 Mo.</span><span class="sxs-lookup"><span data-stu-id="48b8f-153">Since we have three hash indexes, the memory needed for the hash indexes is 3 \* 64MB = 192MB.</span></span>  
  
 <span data-ttu-id="48b8f-154">**Mémoire pour les index non-cluster**</span><span class="sxs-lookup"><span data-stu-id="48b8f-154">**Memory for nonclustered indexes**</span></span>  
  
 <span data-ttu-id="48b8f-155">Les index non-cluster sont implémentés en tant que BTrees avec des nœuds internes contenant la valeur des index et les pointeurs vers les nœuds suivants.</span><span class="sxs-lookup"><span data-stu-id="48b8f-155">Nonclustered indexes are implemented as BTrees with the inner nodes containing the index value and pointers to subsequent nodes.</span></span>  <span data-ttu-id="48b8f-156">Les nœuds terminaux contiennent la valeur d'index et un pointeur vers la ligne de table en mémoire.</span><span class="sxs-lookup"><span data-stu-id="48b8f-156">Leaf nodes contain the index value and a pointer to the table row in memory.</span></span>  
  
 <span data-ttu-id="48b8f-157">Contrairement aux index de hachage, les index non-cluster n’ont pas une taille fixe de compartiment.</span><span class="sxs-lookup"><span data-stu-id="48b8f-157">Unlike hash indexes, nonclustered indexes do not have a fixed bucket size.</span></span> <span data-ttu-id="48b8f-158">L'index augmente et se réduit de façon dynamique avec les données.</span><span class="sxs-lookup"><span data-stu-id="48b8f-158">The index grows and shrinks dynamically with the data.</span></span>  
  
 <span data-ttu-id="48b8f-159">La mémoire nécessaire pour les index non-cluster peut être calculée de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="48b8f-159">Memory needed by nonclustered indexes can be computed as follows:</span></span>  
  
-   <span data-ttu-id="48b8f-160">**Mémoire allouée aux nœuds non terminaux** </span><span class="sxs-lookup"><span data-stu-id="48b8f-160">**Memory allocated to non-leaf nodes** </span></span>  
    <span data-ttu-id="48b8f-161">Pour une configuration spécifique, la mémoire allouée aux nœuds non terminaux représente un tout petit pourcentage de la mémoire globale utilisée par l'index.</span><span class="sxs-lookup"><span data-stu-id="48b8f-161">For a typical configuration, the memory allocated to non-leaf nodes is a small percentage of the overall memory taken by the index.</span></span> <span data-ttu-id="48b8f-162">Il est si petit qu'il peut être ignoré sans risque.</span><span class="sxs-lookup"><span data-stu-id="48b8f-162">This is so small it can safely be ignored.</span></span>  
  
-   <span data-ttu-id="48b8f-163">**Mémoire allouée aux nœuds terminaux** </span><span class="sxs-lookup"><span data-stu-id="48b8f-163">**Memory for leaf nodes** </span></span>  
    <span data-ttu-id="48b8f-164">Les nœuds terminaux ont une ligne pour chaque clé unique dans la table et elle pointe vers les lignes de données avec cette clé unique.</span><span class="sxs-lookup"><span data-stu-id="48b8f-164">The leaf nodes have one row for each unique key in the table that points to the data rows with that unique key.</span></span>  <span data-ttu-id="48b8f-165">Si vous avez plusieurs lignes comportant la même clé (c’est-à-dire que vous avez un index non-cluster non unique), il n’y a qu’une seule ligne dans le nœud terminal d’index qui pointe vers l’une des lignes, et les autres lignes sont liées entre elles.</span><span class="sxs-lookup"><span data-stu-id="48b8f-165">If you have multiple rows with the same key (i.e., you have a non-unique nonclustered index), there is only one row in the index leaf node that points to one of the rows with the other rows linked to each other.</span></span>  <span data-ttu-id="48b8f-166">Ainsi, la mémoire totale requise peut être estimée par :</span><span class="sxs-lookup"><span data-stu-id="48b8f-166">Thus, the total memory required can be approximated by:</span></span>   
    <span data-ttu-id="48b8f-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span><span class="sxs-lookup"><span data-stu-id="48b8f-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span></span>  
  
 <span data-ttu-id="48b8f-168">Les index non-cluster sont préférables lorsqu’ils sont utilisés pour les recherches de plage, comme l’illustre la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="48b8f-168">Nonclustered indexes are best when used for range lookups, as exemplified by the following query:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE c2 > 5  
```  
  
##  <a name="memory-for-row-versioning"></a><a name="bkmk_MemoryForRowVersions"></a> <span data-ttu-id="48b8f-169">Mémoire pour le contrôle de version de ligne</span><span class="sxs-lookup"><span data-stu-id="48b8f-169">Memory for row versioning</span></span>  
 <span data-ttu-id="48b8f-170">Pour éviter les verrous, OLTP en mémoire utilise l'accès concurrentiel optimiste lors de la mise à jour ou de la suppression des lignes.</span><span class="sxs-lookup"><span data-stu-id="48b8f-170">To avoid locks, In-Memory OLTP uses optimistic concurrency when updating or deleting rows.</span></span> <span data-ttu-id="48b8f-171">Cela signifie que lorsqu'une ligne est mise à jour, une version supplémentaire de la ligne est créée.</span><span class="sxs-lookup"><span data-stu-id="48b8f-171">This means that when a row is updated, an additional version of the row is created.</span></span> <span data-ttu-id="48b8f-172">Le système conserve les versions précédentes disponibles tant que toutes les transactions susceptibles d'utiliser la version ne sont pas exécutées.</span><span class="sxs-lookup"><span data-stu-id="48b8f-172">The system keeps the previous versions available until all transactions that could possibly use the version have finished execution.</span></span> <span data-ttu-id="48b8f-173">Lorsqu'une ligne est supprimée, le système agit d'une manière similaire à une mise à jour, en conservant la version disponible jusqu'à ce qu'elle ne soit plus nécessaire.</span><span class="sxs-lookup"><span data-stu-id="48b8f-173">When a row is deleted, the system acts in a similar way to an update, keeping the version available until it is no longer necessary.</span></span> <span data-ttu-id="48b8f-174">Les opérations de lecture et d'insertion ne créent pas de versions supplémentaires de ligne.</span><span class="sxs-lookup"><span data-stu-id="48b8f-174">Reads and inserts do not create additional row versions.</span></span>  
  
 <span data-ttu-id="48b8f-175">Étant donné qu'il peut y avoir plusieurs lignes supplémentaires en mémoire à tout moment lors de l'attente du cycle de garbage collection pour libérer la mémoire, vous devez disposer de suffisamment de mémoire pour gérer ces lignes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="48b8f-175">Because there may be a number of additional rows in memory at any time waiting for the garbage collection cycle to release their memory, you must have sufficient memory to accommodate these additional rows.</span></span>  
  
 <span data-ttu-id="48b8f-176">Le nombre de lignes supplémentaires peut être estimé en calculant le nombre maximal de mises à jour et de suppressions de ligne par seconde, puis en le multipliant par le nombre de secondes nécessaires pour la plus longue transaction (au moins 1).</span><span class="sxs-lookup"><span data-stu-id="48b8f-176">The number of additional rows can be estimated by computing the peak number of row updates and deletions per second, then multiplying that by the number of seconds the longest transaction takes (minimum of 1).</span></span>  
  
 <span data-ttu-id="48b8f-177">Cette valeur est ensuite multipliée par la taille de ligne pour obtenir le nombre d'octets nécessaires pour le contrôle de version de ligne.</span><span class="sxs-lookup"><span data-stu-id="48b8f-177">That value is then multiplied by the row size to get the number of bytes you need for row versioning.</span></span>  
  
 `rowVersions = durationOfLongestTransactionInSeconds * peakNumberOfRowUpdatesOrDeletesPerSecond`  
  
 <span data-ttu-id="48b8f-178">Les besoins en mémoire pour les lignes obsolètes sont ensuite estimées en multipliant le nombre de lignes obsolètes par la taille d’une ligne de table mémoire optimisée (voir la [mémoire pour le tableau](#bkmk_MemoryForTable) ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="48b8f-178">Memory needs for stale rows is then estimated by multiplying the number of stale rows by the size of a memory-optimized table row (see [Memory for the table](#bkmk_MemoryForTable) above).</span></span>  
  
 `memoryForRowVersions = rowVersions * rowSize`  
  
##  <a name="memory-for-table-variables"></a><a name="bkmk_TableVariables"></a> <span data-ttu-id="48b8f-179">Mémoire pour les variables de table</span><span class="sxs-lookup"><span data-stu-id="48b8f-179">Memory for table variables</span></span>  
 <span data-ttu-id="48b8f-180">La mémoire utilisée pour une variable de table est libérée uniquement lorsque la variable de table sort de l'étendue.</span><span class="sxs-lookup"><span data-stu-id="48b8f-180">Memory used for a table variable is released only when the table variable goes out of scope.</span></span> <span data-ttu-id="48b8f-181">Les lignes supprimées d'une variable de table, y compris les lignes supprimées dans le cadre d'une mise à jour, ne sont pas concernées par l'opération de garbage collection.</span><span class="sxs-lookup"><span data-stu-id="48b8f-181">Deleted rows, including rows deleted as part of an update, from a table variable are not subject to garbage collection.</span></span> <span data-ttu-id="48b8f-182">Aucun volume de mémoire n'est libéré avant que la variable de table sorte de l'étendue.</span><span class="sxs-lookup"><span data-stu-id="48b8f-182">No memory is released until the table variable exits scope.</span></span>  
  
 <span data-ttu-id="48b8f-183">Les variables de table définies dans un grand lot SQL, par opposition à une étendue de procédure, et qui sont utilisées par plusieurs transactions, peuvent consommer beaucoup de mémoire.</span><span class="sxs-lookup"><span data-stu-id="48b8f-183">Table variables defined in a large SQL batch, as opposed to a procedure scope, which are used in many transactions, can consume a lot of memory.</span></span> <span data-ttu-id="48b8f-184">Étant donné qu'elles ne sont pas nettoyées, les lignes supprimées d'une variable de table peuvent utiliser beaucoup de mémoire et réduire les performances, car les opérations de lecture doivent analyser au-delà des lignes supprimées.</span><span class="sxs-lookup"><span data-stu-id="48b8f-184">Because they are not garbage collected, deleted rows in a table variable can consume a lot memory and degrade performance since read operations need to scan past the deleted rows.</span></span>  
  
##  <a name="memory-for-growth"></a><a name="bkmk_MemoryForGrowth"></a> <span data-ttu-id="48b8f-185">Mémoire pour la croissance</span><span class="sxs-lookup"><span data-stu-id="48b8f-185">Memory for growth</span></span>  
 <span data-ttu-id="48b8f-186">Les calculs ci-dessus estiment les besoins en mémoire de la table, telle qu'elle existe actuellement.</span><span class="sxs-lookup"><span data-stu-id="48b8f-186">The above calculations estimate your memory needs for the table as it currently exists.</span></span> <span data-ttu-id="48b8f-187">Outre cette mémoire, vous devez évaluer la croissance de la table et fournir suffisamment de mémoire pour gérer cette croissance.</span><span class="sxs-lookup"><span data-stu-id="48b8f-187">In addition to this memory, you need to estimate the growth of the table and provide sufficient memory to accommodate that growth.</span></span>  <span data-ttu-id="48b8f-188">Par exemple, si vous anticipez une croissance de 10 %, vous devez multiplier le résultat ci-dessus par 1,1 pour obtenir la mémoire totale nécessaire pour votre table.</span><span class="sxs-lookup"><span data-stu-id="48b8f-188">For example, if you anticipate 10% growth then you need to multiple the results from above by 1.1 to get the total memory needed for your table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b8f-189">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48b8f-189">See Also</span></span>  
 [<span data-ttu-id="48b8f-190">Migration vers OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="48b8f-190">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
