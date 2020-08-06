---
title: Taille de la table et des lignes dans les tables à mémoire optimisée | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b0a248a4-4488-4cc8-89fc-46906a8c24a1
author: rothja
ms.author: jroth
ms.openlocfilehash: 74cc40b7d1f2d0132d79d1e9ae15c2321ac9b74a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709408"
---
# <a name="table-and-row-size-in-memory-optimized-tables"></a><span data-ttu-id="86b0e-102">Taille de la table et des lignes dans les tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="86b0e-102">Table and Row Size in Memory-Optimized Tables</span></span>
  <span data-ttu-id="86b0e-103">Une table mémoire optimisée se compose d'une collection de lignes et d'index qui contiennent des pointeurs vers les lignes.</span><span class="sxs-lookup"><span data-stu-id="86b0e-103">A memory-optimized table consists of a collection of rows and indexes that contain pointers to rows.</span></span> <span data-ttu-id="86b0e-104">Dans une table mémoire optimisée, les lignes ne peuvent pas dépasser 8 060 octets.</span><span class="sxs-lookup"><span data-stu-id="86b0e-104">In a memory-optimized table, rows cannot be longer than 8,060 bytes.</span></span> <span data-ttu-id="86b0e-105">La compréhension de la taille d'une table mémoire optimisée vous aidera à comprendre si votre ordinateur dispose de suffisamment de mémoire.</span><span class="sxs-lookup"><span data-stu-id="86b0e-105">Understanding the size of a memory-optimized table will help you understand if your computer has enough memory.</span></span>  
  
 <span data-ttu-id="86b0e-106">Il existe deux raisons pour calculer la taille des tables et des lignes :</span><span class="sxs-lookup"><span data-stu-id="86b0e-106">There are two reasons for computing table and row size:</span></span>  
  
-   <span data-ttu-id="86b0e-107">Connaître la quantité de mémoire utilisée par une table</span><span class="sxs-lookup"><span data-stu-id="86b0e-107">How much memory does a table use?</span></span>  
  
    -   <span data-ttu-id="86b0e-108">La quantité de mémoire utilisée par la table ne peut pas être calculée exactement.</span><span class="sxs-lookup"><span data-stu-id="86b0e-108">The amount of memory used by the table cannot be calculated exactly.</span></span> <span data-ttu-id="86b0e-109">De nombreux facteurs affectent la quantité de mémoire utilisée.</span><span class="sxs-lookup"><span data-stu-id="86b0e-109">Many factors affect the amount of memory used.</span></span> <span data-ttu-id="86b0e-110">Notamment, l'allocation de mémoire, la localité, la mise en cache, et le remplissage basés sur la page.</span><span class="sxs-lookup"><span data-stu-id="86b0e-110">Factors such as page-based memory allocation, locality, caching, and padding.</span></span> <span data-ttu-id="86b0e-111">Ainsi que, plusieurs versions de ligne associées à des transactions actives ou qui attendent le garbage collection.</span><span class="sxs-lookup"><span data-stu-id="86b0e-111">Also, multiple versions of rows that either have active transactions associated or that are waiting for garbage collection.</span></span>  
  
    -   <span data-ttu-id="86b0e-112">La taille minimale nécessaire pour les données et les index de la table est fournie par le calcul [taille de la table], présenté ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="86b0e-112">The minimum size required for the data and indexes in the table is given by the calculation for [table size], discussed below.</span></span>  
  
    -   <span data-ttu-id="86b0e-113">Le calcul de l'utilisation de la mémoire est une approximation et nous vous recommandons d'inclure la planification des capacités dans vos plans de déploiement.</span><span class="sxs-lookup"><span data-stu-id="86b0e-113">Calculating memory use is at best an approximation and you are advised to include capacity planning in your deployment plans.</span></span>  
  
-   <span data-ttu-id="86b0e-114">Connaître la taille des données d'une ligne, et si elle dépasse la limite de taille de ligne de 8 060 octets.</span><span class="sxs-lookup"><span data-stu-id="86b0e-114">The data size of a row, and does it fit in the 8,060 byte row size limitation?</span></span> <span data-ttu-id="86b0e-115">Pour répondre à ces questions, utilisez le calcul de [taille du corps de ligne], présenté ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="86b0e-115">To answer these questions, use the computation for [row body size], discussed below.</span></span>  
  
 <span data-ttu-id="86b0e-116">La figure ci-dessous illustre une table avec des index et des lignes, qui ont à leur tour des en-têtes de ligne et des corps :</span><span class="sxs-lookup"><span data-stu-id="86b0e-116">The following figure illustrates a table with indexes and rows, which in turn have row headers and bodies:</span></span>  
  
 <span data-ttu-id="86b0e-117">![Table à mémoire optimisée.](../../database-engine/media/hekaton-guide-1.gif "Table à mémoire optimisée.")</span><span class="sxs-lookup"><span data-stu-id="86b0e-117">![Memory optimized table.](../../database-engine/media/hekaton-guide-1.gif "Memory optimized table.")</span></span>  
<span data-ttu-id="86b0e-118">Table mémoire optimisée, comportant des index et des lignes.</span><span class="sxs-lookup"><span data-stu-id="86b0e-118">Memory-optimized table, consisting of indexes and rows.</span></span>  
  
 <span data-ttu-id="86b0e-119">La taille en mémoire d'une table, en octets, est calculée comme suit :</span><span class="sxs-lookup"><span data-stu-id="86b0e-119">The in-memory size of a table, in bytes, is computed as follows:</span></span>  
  
```  
[table size] = [size of index 1] + ... + [size of index n] + ([row size] * [row count])  
```  
  
 <span data-ttu-id="86b0e-120">La taille d'un index de hachage est définie au moment de la création de la table et dépend du nombre réel de compartiments.</span><span class="sxs-lookup"><span data-stu-id="86b0e-120">The size of a hash index is fixed at table creation time and depends on the actual bucket count.</span></span> <span data-ttu-id="86b0e-121">Le bucket_count indiqué avec la spécification de l'index est arrondi à la puissance de 2 la plus proche pour obtenir le [nombre de compartiments réel].</span><span class="sxs-lookup"><span data-stu-id="86b0e-121">The bucket_count specified with the index specification is rounded up to the nearest power of 2 to obtain the [actual bucket count].</span></span> <span data-ttu-id="86b0e-122">Par exemple, si le bucket_count spécifié est 100 000, le [nombre de compartiments réel] pour l'index est 131 072.</span><span class="sxs-lookup"><span data-stu-id="86b0e-122">For example, if the specified bucket_count is 100000, the [actual bucket count] for the index is 131072.</span></span>  
  
```  
[hash index size] = 8 * [actual bucket count]  
```  
  
 <span data-ttu-id="86b0e-123">La taille de ligne est calculée en ajoutant l'en-tête et le corps :</span><span class="sxs-lookup"><span data-stu-id="86b0e-123">The row size is computed by adding the header and the body:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices]  
```  
  
 <span data-ttu-id="86b0e-124">**Taille du corps de ligne**</span><span class="sxs-lookup"><span data-stu-id="86b0e-124">**Row body size**</span></span>  
  
 <span data-ttu-id="86b0e-125">Le calcul de la [taille du corps de ligne] est expliqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="86b0e-125">The calculation of [row body size] is discussed in the following table.</span></span>  
  
 <span data-ttu-id="86b0e-126">Il existe deux calculs différents pour la taille du corps de ligne : la taille calculée et la taille réelle :</span><span class="sxs-lookup"><span data-stu-id="86b0e-126">There are two different computations for row body size: computed size and the actual size:</span></span>  
  
-   <span data-ttu-id="86b0e-127">La taille calculée, indiquée par [taille calculée du corps de ligne], est utilisée pour déterminer si la limite de taille de ligne de 8 060 octets est dépassée.</span><span class="sxs-lookup"><span data-stu-id="86b0e-127">The computed size, denoted with [computed row body size], is used to determine if the row size limitation of 8,060 bytes is exceeded.</span></span>  
  
-   <span data-ttu-id="86b0e-128">La taille réelle, indiquée par [taille réelle du corps de ligne], est la taille de stockage réelle du corps de ligne en mémoire et dans les fichiers de point de contrôle.</span><span class="sxs-lookup"><span data-stu-id="86b0e-128">The actual size, denoted with [actual row body size], is the actual storage size of the row body in memory and in the checkpoint files.</span></span>  
  
 <span data-ttu-id="86b0e-129">Les deux tailles [taille calculée du corps de ligne] et [taille réelle du corps de ligne] sont calculées de façon similaire.</span><span class="sxs-lookup"><span data-stu-id="86b0e-129">Both [computed row body size] and [actual row body size] are calculated similarly.</span></span> <span data-ttu-id="86b0e-130">La seule différence est le calcul de la taille des colonnes (n)varchar(i) et varbinary(i), comme indiqué en bas du tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="86b0e-130">The only difference is the calculation of the size of (n)varchar(i) and varbinary(i) columns, as reflected at the bottom of the following table.</span></span> <span data-ttu-id="86b0e-131">La taille calculée du corps de ligne utilise la taille déclarée *i* comme taille de la colonne, tandis que la taille réelle du corps de ligne utilise la taille réelle des données.</span><span class="sxs-lookup"><span data-stu-id="86b0e-131">The computed row body size uses the declared size *i* as the size of the column, while the actual row body size uses the actual size of the data.</span></span>  
  
 <span data-ttu-id="86b0e-132">Le tableau suivant décrit le calcul de la taille du corps de ligne, fourni en tant que [taille réelle du corps de ligne] = SUM([taille des types superficiels]) + 2 + 2 \* [nombre de colonnes de type profond].</span><span class="sxs-lookup"><span data-stu-id="86b0e-132">The following table describes the calculation of the row body size, given as [actual row body size] = SUM([size of shallow types]) + 2 + 2 \* [number of deep type columns].</span></span>  
  
|<span data-ttu-id="86b0e-133">Section</span><span class="sxs-lookup"><span data-stu-id="86b0e-133">Section</span></span>|<span data-ttu-id="86b0e-134">Taille</span><span class="sxs-lookup"><span data-stu-id="86b0e-134">Size</span></span>|<span data-ttu-id="86b0e-135">Commentaires</span><span class="sxs-lookup"><span data-stu-id="86b0e-135">Comments</span></span>|  
|-------------|----------|--------------|  
|<span data-ttu-id="86b0e-136">Colonnes de type superficiel</span><span class="sxs-lookup"><span data-stu-id="86b0e-136">Shallow type columns</span></span>|<span data-ttu-id="86b0e-137">SUM ([taille des types superficiels])</span><span class="sxs-lookup"><span data-stu-id="86b0e-137">SUM([size of shallow types])</span></span><br /><br /> <span data-ttu-id="86b0e-138">**La taille des types est la suivante :**</span><span class="sxs-lookup"><span data-stu-id="86b0e-138">**Size of the individual types is as follows:**</span></span><br /><br /> <span data-ttu-id="86b0e-139">Bit &#124; 1</span><span class="sxs-lookup"><span data-stu-id="86b0e-139">Bit &#124; 1</span></span><br /><br /> <span data-ttu-id="86b0e-140">Tinyint &#124; 1</span><span class="sxs-lookup"><span data-stu-id="86b0e-140">Tinyint &#124; 1</span></span><br /><br /> <span data-ttu-id="86b0e-141">Smallint &#124; 2</span><span class="sxs-lookup"><span data-stu-id="86b0e-141">Smallint &#124; 2</span></span><br /><br /> <span data-ttu-id="86b0e-142">Int &#124; 4</span><span class="sxs-lookup"><span data-stu-id="86b0e-142">Int &#124; 4</span></span><br /><br /> <span data-ttu-id="86b0e-143">Real &#124; 4</span><span class="sxs-lookup"><span data-stu-id="86b0e-143">Real &#124; 4</span></span><br /><br /> <span data-ttu-id="86b0e-144">Smalldatetime &#124; 4</span><span class="sxs-lookup"><span data-stu-id="86b0e-144">Smalldatetime &#124; 4</span></span><br /><br /> <span data-ttu-id="86b0e-145">Smallmoney &#124; 4</span><span class="sxs-lookup"><span data-stu-id="86b0e-145">Smallmoney &#124; 4</span></span><br /><br /> <span data-ttu-id="86b0e-146">Bigint &#124; 8</span><span class="sxs-lookup"><span data-stu-id="86b0e-146">Bigint &#124; 8</span></span><br /><br /> <span data-ttu-id="86b0e-147">Datetime &#124; 8</span><span class="sxs-lookup"><span data-stu-id="86b0e-147">Datetime &#124; 8</span></span><br /><br /> <span data-ttu-id="86b0e-148">Datetime2 &#124; 8</span><span class="sxs-lookup"><span data-stu-id="86b0e-148">Datetime2 &#124; 8</span></span><br /><br /> <span data-ttu-id="86b0e-149">Float 8</span><span class="sxs-lookup"><span data-stu-id="86b0e-149">Float 8</span></span><br /><br /> <span data-ttu-id="86b0e-150">Money 8</span><span class="sxs-lookup"><span data-stu-id="86b0e-150">Money 8</span></span><br /><br /> <span data-ttu-id="86b0e-151">Numeric (précision <= 18) &#124; 8</span><span class="sxs-lookup"><span data-stu-id="86b0e-151">Numeric (precision <=18) &#124; 8</span></span><br /><br /> <span data-ttu-id="86b0e-152">Time &#124; 8</span><span class="sxs-lookup"><span data-stu-id="86b0e-152">Time &#124; 8</span></span><br /><br /> <span data-ttu-id="86b0e-153">Numeric (précision>18) &#124; 16</span><span class="sxs-lookup"><span data-stu-id="86b0e-153">Numeric(precision>18) &#124; 16</span></span><br /><br /> <span data-ttu-id="86b0e-154">Uniqueidentifier &#124; 16</span><span class="sxs-lookup"><span data-stu-id="86b0e-154">Uniqueidentifier &#124; 16</span></span>||  
|<span data-ttu-id="86b0e-155">Remplissage de colonne superficielle</span><span class="sxs-lookup"><span data-stu-id="86b0e-155">Shallow column padding</span></span>|<span data-ttu-id="86b0e-156">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="86b0e-156">Possible values are:</span></span><br /><br /> <span data-ttu-id="86b0e-157">1 s'il y a des colonnes de type profond et la taille de données totale des colonnes superficielles est un nombre impair.</span><span class="sxs-lookup"><span data-stu-id="86b0e-157">1 if there are deep type columns and the total data size of the shallow columns is as odd number.</span></span><br /><br /> <span data-ttu-id="86b0e-158">0 dans les autres cas</span><span class="sxs-lookup"><span data-stu-id="86b0e-158">0 otherwise</span></span>|<span data-ttu-id="86b0e-159">Les types profonds sont les types (var)binary et (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="86b0e-159">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="86b0e-160">Tableau « offset » pour les colonnes de type profond</span><span class="sxs-lookup"><span data-stu-id="86b0e-160">Offset array for deep type columns</span></span>|<span data-ttu-id="86b0e-161">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="86b0e-161">Possible values are:</span></span><br /><br /> <span data-ttu-id="86b0e-162">0 s'il n'y a aucune colonne de type profond</span><span class="sxs-lookup"><span data-stu-id="86b0e-162">0 if there are no deep type columns</span></span><br /><br /> <span data-ttu-id="86b0e-163">2 + 2 \* [nombre de colonnes de type profond] dans les autres cas</span><span class="sxs-lookup"><span data-stu-id="86b0e-163">2 + 2 \* [number of deep type columns] otherwise</span></span>|<span data-ttu-id="86b0e-164">Les types profonds sont les types (var)binary et (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="86b0e-164">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="86b0e-165">Tableau NULL</span><span class="sxs-lookup"><span data-stu-id="86b0e-165">NULL array</span></span>|<span data-ttu-id="86b0e-166">[nombre de colonnes qui acceptent les valeurs NULL] / 8, arrondi à des octets entiers.</span><span class="sxs-lookup"><span data-stu-id="86b0e-166">[number of nullable columns] / 8, rounded up to full bytes.</span></span>|<span data-ttu-id="86b0e-167">La table comporte un bit pour chaque colonne pouvant avoir la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="86b0e-167">The array has one bit per nullable column.</span></span> <span data-ttu-id="86b0e-168">Cela est arrondi à des octets entiers.</span><span class="sxs-lookup"><span data-stu-id="86b0e-168">This is rounded up to full bytes.</span></span>|  
|<span data-ttu-id="86b0e-169">Remplissage du tableau NULL</span><span class="sxs-lookup"><span data-stu-id="86b0e-169">NULL array padding</span></span>|<span data-ttu-id="86b0e-170">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="86b0e-170">Possible values are:</span></span><br /><br /> <span data-ttu-id="86b0e-171">1 s'il y a des colonnes de type profond et la taille du tableau NULL a un nombre impair d'octets.</span><span class="sxs-lookup"><span data-stu-id="86b0e-171">1 if there are deep type columns and the size of the NULL array is an odd number of bytes.</span></span><br /><br /> <span data-ttu-id="86b0e-172">0 dans les autres cas</span><span class="sxs-lookup"><span data-stu-id="86b0e-172">0 otherwise</span></span>|<span data-ttu-id="86b0e-173">Les types profonds sont les types (var)binary et (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="86b0e-173">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="86b0e-174">Remplissage</span><span class="sxs-lookup"><span data-stu-id="86b0e-174">Padding</span></span>|<span data-ttu-id="86b0e-175">S'il n’y a aucune colonne de type profond : 0</span><span class="sxs-lookup"><span data-stu-id="86b0e-175">If there are no deep type columns: 0</span></span><br /><br /> <span data-ttu-id="86b0e-176">En présence de colonnes de type profond, 0-7 octets de remplissage sont ajoutés, selon le plus grand alignement requis par une colonne superficielle.</span><span class="sxs-lookup"><span data-stu-id="86b0e-176">If there are deep type columns, 0-7 bytes of padding is added, based on the largest alignment required by a shallow column.</span></span> <span data-ttu-id="86b0e-177">Chaque colonne superficielle requiert un alignement égal à sa taille, comme indiqué précédemment, mais les colonnes GUID nécessitent un alignement d'1 octet (et non de 16) et les colonnes numériques requièrent toujours un alignement de 8 octets (jamais de 16).</span><span class="sxs-lookup"><span data-stu-id="86b0e-177">Each shallow column requires alignment equal to its size as documented above, except that GUID columns need alignment of 1 byte (not 16) and numeric columns always need alignment of 8 bytes (never 16).</span></span> <span data-ttu-id="86b0e-178">La plus grande spécification d'alignement entre toutes les colonnes superficielles est utilisée, et un remplissage de 0-7 octets est ajouté de sorte que la taille totale (sans les colonnes de type profond) soit un multiple de l'alignement requis.</span><span class="sxs-lookup"><span data-stu-id="86b0e-178">The largest alignment requirement among all shallow columns is used, and 0-7 bytes of padding is added in such a way that the total size so far (without the deep type columns) is a multiple of the required alignment.</span></span>|<span data-ttu-id="86b0e-179">Les types profonds sont les types (var)binary et (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="86b0e-179">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="86b0e-180">Colonnes de type profond à longueur fixe</span><span class="sxs-lookup"><span data-stu-id="86b0e-180">Fixed-length deep type columns</span></span>|<span data-ttu-id="86b0e-181">SUM([taille des colonnes de type profond à longueur fixe])</span><span class="sxs-lookup"><span data-stu-id="86b0e-181">SUM([size of fixed length deep type columns])</span></span><br /><br /> <span data-ttu-id="86b0e-182">La taille de chaque colonne est la suivante :</span><span class="sxs-lookup"><span data-stu-id="86b0e-182">The size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="86b0e-183">i pour char(i) et binary(i).</span><span class="sxs-lookup"><span data-stu-id="86b0e-183">i for char(i) and binary(i).</span></span><br /><br /> <span data-ttu-id="86b0e-184">2 \* i pour nchar(i)</span><span class="sxs-lookup"><span data-stu-id="86b0e-184">2 \* i for nchar(i)</span></span>|<span data-ttu-id="86b0e-185">Les colonnes de type profond à longueur fixe sont des colonnes de type char(i), nchar(i) ou binary(i).</span><span class="sxs-lookup"><span data-stu-id="86b0e-185">Fixed-length deep type columns are columns of type char(i), nchar(i), or binary(i).</span></span>|  
|<span data-ttu-id="86b0e-186">Colonnes de type profond à longueur variable [taille calculée]</span><span class="sxs-lookup"><span data-stu-id="86b0e-186">Variable length deep type columns [computed size]</span></span>|<span data-ttu-id="86b0e-187">SUM ([taille calculée des colonnes de type profond à longueur variable])</span><span class="sxs-lookup"><span data-stu-id="86b0e-187">SUM([computed size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="86b0e-188">La taille calculée de chaque colonne est la suivante :</span><span class="sxs-lookup"><span data-stu-id="86b0e-188">The computed size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="86b0e-189">i pour varchar(i) et varbinary(i)</span><span class="sxs-lookup"><span data-stu-id="86b0e-189">i for varchar(i) and varbinary(i)</span></span><br /><br /> <span data-ttu-id="86b0e-190">2 \* i pour nvarchar(i)</span><span class="sxs-lookup"><span data-stu-id="86b0e-190">2 \* i for nvarchar(i)</span></span>|<span data-ttu-id="86b0e-191">Cette ligne est uniquement appliquée à la [taille calculée du corps de ligne].</span><span class="sxs-lookup"><span data-stu-id="86b0e-191">This row only applied to [computed row body size].</span></span><br /><br /> <span data-ttu-id="86b0e-192">Les colonnes de type profond à longueur variable sont des colonnes de type varchar(i), nvarchar(i), ou varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="86b0e-192">Variable-length deep type columns are columns of type varchar(i), nvarchar(i), or varbinary(i).</span></span> <span data-ttu-id="86b0e-193">La taille calculée est déterminée par la longueur maximale (i) de la colonne.</span><span class="sxs-lookup"><span data-stu-id="86b0e-193">The computed size is determined by the max length (i) of the column.</span></span>|  
|<span data-ttu-id="86b0e-194">Colonnes de type profond à longueur variable [taille réelle]</span><span class="sxs-lookup"><span data-stu-id="86b0e-194">Variable length deep type columns [actual size]</span></span>|<span data-ttu-id="86b0e-195">SUM ([taille réelle des colonnes de type profond à longueur variable])</span><span class="sxs-lookup"><span data-stu-id="86b0e-195">SUM([actual size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="86b0e-196">La taille réelle de chaque colonne est la suivante :</span><span class="sxs-lookup"><span data-stu-id="86b0e-196">The actual size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="86b0e-197">n, où n est le nombre de caractères stocké dans la colonne, pour varchar(i).</span><span class="sxs-lookup"><span data-stu-id="86b0e-197">n, where n is the number of characters stored in the column, for varchar(i).</span></span><br /><br /> <span data-ttu-id="86b0e-198">2 \* n, où n est le nombre de caractères stocké dans la colonne, pour nvarchar (i).</span><span class="sxs-lookup"><span data-stu-id="86b0e-198">2 \* n, where n is the number of characters stored in the column, for nvarchar(i).</span></span><br /><br /> <span data-ttu-id="86b0e-199">n, où n est le nombre d'octets stocké dans la colonne, pour varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="86b0e-199">n, where n is the number of bytes stored in the column, for varbinary(i).</span></span>|<span data-ttu-id="86b0e-200">Cette ligne est uniquement appliquée à la [taille réelle du corps de ligne].</span><span class="sxs-lookup"><span data-stu-id="86b0e-200">This row only applied to [actual row body size].</span></span><br /><br /> <span data-ttu-id="86b0e-201">La taille réelle est déterminée par les données stockées dans les colonnes dans la ligne.</span><span class="sxs-lookup"><span data-stu-id="86b0e-201">The actual size is determined by the data stored in the columns in the row.</span></span>|  
  
##  <a name="row-structure"></a><a name="bkmk_RowStructure"></a><span data-ttu-id="86b0e-202">Structure de ligne</span><span class="sxs-lookup"><span data-stu-id="86b0e-202">Row Structure</span></span>  
 <span data-ttu-id="86b0e-203">Les lignes de la table mémoire optimisée ont les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="86b0e-203">The rows in a memory-optimized table have the following components:</span></span>  
  
-   <span data-ttu-id="86b0e-204">L'en-tête de ligne contient l'horodateur nécessaire pour implémenter une gestion des versions de ligne.</span><span class="sxs-lookup"><span data-stu-id="86b0e-204">The row header contains the timestamp necessary to implement row versioning.</span></span> <span data-ttu-id="86b0e-205">L'en-tête de la ligne contient également le pointeur d'index pour implémenter le chaînage de ligne dans les compartiments de hachage (comme ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="86b0e-205">The row header also contains the index pointer to implement the row chaining in the hash buckets (described above).</span></span>  
  
-   <span data-ttu-id="86b0e-206">Le corps de la ligne contient les données de la colonne active, comprenant des informations auxiliaires comme le tableau « null » pour les colonnes autorisant des valeurs NULL, et le tableau « offset » pour les types de données de longueur variable.</span><span class="sxs-lookup"><span data-stu-id="86b0e-206">The row body contains the actual column data, which includes some auxiliary information like the null array for nullable columns and the offset array for variable-length data types.</span></span>  
  
 <span data-ttu-id="86b0e-207">La figure suivante illustre la structure des lignes pour une table qui comporte deux index :</span><span class="sxs-lookup"><span data-stu-id="86b0e-207">The following figure illustrates the row structure for a table that has two indexes:</span></span>  
  
 <span data-ttu-id="86b0e-208">![Structure des lignes d’une table qui comporte deux index.](../../database-engine/media/hekaton-tables-4.gif "Structure des lignes d'une table qui comporte deux index.")</span><span class="sxs-lookup"><span data-stu-id="86b0e-208">![Row structure for a table that has two indexes.](../../database-engine/media/hekaton-tables-4.gif "Row structure for a table that has two indexes.")</span></span>  
  
 <span data-ttu-id="86b0e-209">Les horodateurs de début et de fin indiquent la période pendant laquelle une version de ligne spécifique est valide.</span><span class="sxs-lookup"><span data-stu-id="86b0e-209">The begin and end timestamps indicate the period in which a particular row version is valid.</span></span> <span data-ttu-id="86b0e-210">Les transactions commençant dans cet intervalle peuvent consulter cette version de ligne.</span><span class="sxs-lookup"><span data-stu-id="86b0e-210">Transactions that start in this interval can see this row version.</span></span> <span data-ttu-id="86b0e-211">Pour plus de détails, consultez [Transactions dans les tables optimisées en mémoire](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="86b0e-211">For more details see [Transactions in Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="86b0e-212">Les pointeurs d'index pointent sur la ligne suivante dans la chaîne appartenant au compartiment de hachage.</span><span class="sxs-lookup"><span data-stu-id="86b0e-212">The index pointers point to the next row in the chain belonging to the hash bucket.</span></span> <span data-ttu-id="86b0e-213">L'illustration suivante montre la structure d'une table à deux colonnes (Nom, Ville), et deux index, l'un sur la colonne Nom, et l'autre sur la colonne Ville.</span><span class="sxs-lookup"><span data-stu-id="86b0e-213">The following figure illustrates the structure of a table with two columns (name, city), and with two indexes, one on the column name, and one on the column city.</span></span>  
  
 <span data-ttu-id="86b0e-214">![Structure d’une table qui comporte deux colonnes et index.](../../database-engine/media/hekaton-tables-5.gif "Structure d’une table qui comporte deux colonnes et index.")</span><span class="sxs-lookup"><span data-stu-id="86b0e-214">![Structure of a table with two columns and indexes.](../../database-engine/media/hekaton-tables-5.gif "Structure of a table with two columns and indexes.")</span></span>  
  
 <span data-ttu-id="86b0e-215">Dans cette illustration, les noms John et Jane sont hachés vers le premier compartiment.</span><span class="sxs-lookup"><span data-stu-id="86b0e-215">In this figure, the names John and Jane are hashed to the first bucket.</span></span> <span data-ttu-id="86b0e-216">Susan est hachée vers le deuxième compartiment.</span><span class="sxs-lookup"><span data-stu-id="86b0e-216">Susan is hashed to the second bucket.</span></span> <span data-ttu-id="86b0e-217">Pékin et Bogota sont hachés vers le premier compartiment.</span><span class="sxs-lookup"><span data-stu-id="86b0e-217">The cities Beijing and Bogota are hashed to the first bucket.</span></span> <span data-ttu-id="86b0e-218">Paris et Prague sont hachés vers le deuxième compartiment.</span><span class="sxs-lookup"><span data-stu-id="86b0e-218">Paris and Prague are hashed to the second bucket.</span></span>  
  
 <span data-ttu-id="86b0e-219">Par conséquent, les chaînes de l'index de hachage sur le nom sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="86b0e-219">Thus, the chains for the hash index on name are as follows:</span></span>  
  
-   <span data-ttu-id="86b0e-220">Première compartiment : (John, Beijing) ; (John, Paris) ; (Jane, Prague)</span><span class="sxs-lookup"><span data-stu-id="86b0e-220">First bucket: (John, Beijing); (John, Paris); (Jane, Prague)</span></span>  
  
-   <span data-ttu-id="86b0e-221">Deuxième compartiment : (Susan, Bogota)</span><span class="sxs-lookup"><span data-stu-id="86b0e-221">Second bucket: (Susan, Bogota)</span></span>  
  
 <span data-ttu-id="86b0e-222">Les chaînes de l'index de la ville sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="86b0e-222">The chains for the index on city are as follows:</span></span>  
  
-   <span data-ttu-id="86b0e-223">Première compartiment : (John, Beijing), (Susan, Bogota)</span><span class="sxs-lookup"><span data-stu-id="86b0e-223">First bucket: (John, Beijing), (Susan, Bogota)</span></span>  
  
-   <span data-ttu-id="86b0e-224">Deuxième compartiment : (John, Paris), (Jane, Prague)</span><span class="sxs-lookup"><span data-stu-id="86b0e-224">Second bucket: (John, Paris), (Jane, Prague)</span></span>  
  
 <span data-ttu-id="86b0e-225">Un horodateur de fin &#x221e; (infini) indique qu’il s’agit de la version actuellement valide de la ligne.</span><span class="sxs-lookup"><span data-stu-id="86b0e-225">An end timestamp &#x221e; (infinity) indicates that this is the currently valid version of the row.</span></span> <span data-ttu-id="86b0e-226">La ligne n'a pas été mise à jour ou n'a pas été supprimée depuis que cette version de ligne a été écrite.</span><span class="sxs-lookup"><span data-stu-id="86b0e-226">The row has not been updated or deleted since this row version was written.</span></span>  
  
 <span data-ttu-id="86b0e-227">Pour un temps supérieur à 200, la table contient les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="86b0e-227">For a time greater than 200, the table contains the following rows:</span></span>  
  
|<span data-ttu-id="86b0e-228">Nom</span><span class="sxs-lookup"><span data-stu-id="86b0e-228">Name</span></span>|<span data-ttu-id="86b0e-229">City</span><span class="sxs-lookup"><span data-stu-id="86b0e-229">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="86b0e-230">John</span><span class="sxs-lookup"><span data-stu-id="86b0e-230">John</span></span>|<span data-ttu-id="86b0e-231">Beijing</span><span class="sxs-lookup"><span data-stu-id="86b0e-231">Beijing</span></span>|  
|<span data-ttu-id="86b0e-232">Jane</span><span class="sxs-lookup"><span data-stu-id="86b0e-232">Jane</span></span>|<span data-ttu-id="86b0e-233">Prague</span><span class="sxs-lookup"><span data-stu-id="86b0e-233">Prague</span></span>|  
  
 <span data-ttu-id="86b0e-234">Toutefois, toutes les transactions actives avec une heure de début 100 verront la version de la table suivante :</span><span class="sxs-lookup"><span data-stu-id="86b0e-234">However, any active transaction with begin time 100 will see the following version of the table:</span></span>  
  
|<span data-ttu-id="86b0e-235">Nom</span><span class="sxs-lookup"><span data-stu-id="86b0e-235">Name</span></span>|<span data-ttu-id="86b0e-236">City</span><span class="sxs-lookup"><span data-stu-id="86b0e-236">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="86b0e-237">John</span><span class="sxs-lookup"><span data-stu-id="86b0e-237">John</span></span>|<span data-ttu-id="86b0e-238">Paris</span><span class="sxs-lookup"><span data-stu-id="86b0e-238">Paris</span></span>|  
|<span data-ttu-id="86b0e-239">Jane</span><span class="sxs-lookup"><span data-stu-id="86b0e-239">Jane</span></span>|<span data-ttu-id="86b0e-240">Prague</span><span class="sxs-lookup"><span data-stu-id="86b0e-240">Prague</span></span>|  
|<span data-ttu-id="86b0e-241">Susan</span><span class="sxs-lookup"><span data-stu-id="86b0e-241">Susan</span></span>|<span data-ttu-id="86b0e-242">Bogota</span><span class="sxs-lookup"><span data-stu-id="86b0e-242">Bogata</span></span>|  
  
##  <a name="example-table-and-row-size-computation"></a><a name="bkmk_ExampleComputation"></a> <span data-ttu-id="86b0e-243">Exemple : Calcul de la taille des lignes et de la table</span><span class="sxs-lookup"><span data-stu-id="86b0e-243">Example: Table and Row Size Computation</span></span>  
 <span data-ttu-id="86b0e-244">Pour les index de hachage, le nombre de compartiments réel est arrondi à la puissance de 2 la plus proche.</span><span class="sxs-lookup"><span data-stu-id="86b0e-244">For hash indexes, the actual bucket count is rounded up to the nearest power of 2.</span></span> <span data-ttu-id="86b0e-245">Par exemple, si le bucket_count spécifié est 100 000, le nombre de compartiments réel pour l'index est 131 072.</span><span class="sxs-lookup"><span data-stu-id="86b0e-245">For example, if the specified bucket_count is 100000, the actual bucket count for the index is 131072.</span></span>  
  
 <span data-ttu-id="86b0e-246">Prenons l'exemple d'une table Orders avec la définition suivante :</span><span class="sxs-lookup"><span data-stu-id="86b0e-246">Consider an Orders table with the following definition:</span></span>  
  
```sql  
CREATE TABLE dbo.Orders (  
     OrderID int NOT NULL   
           PRIMARY KEY NONCLUSTERED,  
     CustomerID int NOT NULL   
           INDEX IX_CustomerID HASH WITH (BUCKET_COUNT=10000),  
     OrderDate datetime NOT NULL,  
     OrderDescription nvarchar(1000)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
```  
  
 <span data-ttu-id="86b0e-247">Notez que cette table a un index de hachage et un index non cluster (clé primaire).</span><span class="sxs-lookup"><span data-stu-id="86b0e-247">Notice that this table has one hash index and a nonclustered index (the primary key).</span></span> <span data-ttu-id="86b0e-248">Elle a également trois colonnes de longueur fixe et une colonne de longueur variable, avec l'une des colonnes acceptant les valeurs NULL (OrderDescription).</span><span class="sxs-lookup"><span data-stu-id="86b0e-248">It also has three fixed-length columns and one variable-length column, with one of the columns being NULLable (OrderDescription).</span></span> <span data-ttu-id="86b0e-249">Supposons que la table Orders comporte 8379 lignes et que la longueur moyenne des valeurs de la colonne OrderDescription est de 78 caractères.</span><span class="sxs-lookup"><span data-stu-id="86b0e-249">Let's assume the Orders table has 8379 rows, and the average length of the values in the OrderDescription column is 78 characters.</span></span>  
  
 <span data-ttu-id="86b0e-250">Pour déterminer la taille de la table, déterminez d'abord la taille des index.</span><span class="sxs-lookup"><span data-stu-id="86b0e-250">To determine the table size, first determine the size of the indexes.</span></span> <span data-ttu-id="86b0e-251">Le bucket_count des deux index indique 10 000.</span><span class="sxs-lookup"><span data-stu-id="86b0e-251">The bucket_count for both indexes is specified as 10000.</span></span> <span data-ttu-id="86b0e-252">Il est arrondi à la puissance de 2 la plus proche : 16384.</span><span class="sxs-lookup"><span data-stu-id="86b0e-252">This is rounded up to the nearest power of 2: 16384.</span></span> <span data-ttu-id="86b0e-253">Par conséquent, la taille totale des index de la table Orders est :</span><span class="sxs-lookup"><span data-stu-id="86b0e-253">Therefore, the total size of the indexes for the Orders table is:</span></span>  
  
```  
8 * 16384 = 131072 bytes  
```  
  
 <span data-ttu-id="86b0e-254">Ce qui reste est la taille des données de la table, qui est,</span><span class="sxs-lookup"><span data-stu-id="86b0e-254">What remains is the table data size, which is,</span></span>  
  
```  
[row size] * [row count] = [row size] * 8379  
```  
  
 <span data-ttu-id="86b0e-255">(La table de l'exemple comporte 8 379 lignes.) Maintenant, nous avons :</span><span class="sxs-lookup"><span data-stu-id="86b0e-255">(The example table has 8379 rows.) Now, we have:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices] = 24 + 8 * 1 = 32 bytes  
```  
  
 <span data-ttu-id="86b0e-256">Ensuite, calculons la [taille réelle du corps de ligne] :</span><span class="sxs-lookup"><span data-stu-id="86b0e-256">Next, let's calculate [actual row body size]:</span></span>  
  
-   <span data-ttu-id="86b0e-257">Colonnes de type superficiel :</span><span class="sxs-lookup"><span data-stu-id="86b0e-257">Shallow type columns:</span></span>  
  
    ```  
    SUM([size of shallow types]) = 4 [int] + 4 [int] + 8 [datetime] = 16  
    ```  
  
-   <span data-ttu-id="86b0e-258">Le remplissage de la colonne superficielle est 0, car la taille de la colonne superficielle totale est un nombre pair.</span><span class="sxs-lookup"><span data-stu-id="86b0e-258">Shallow column padding is 0, as the total shallow column size is even.</span></span>  
  
-   <span data-ttu-id="86b0e-259">Tableau « offset » pour les colonnes de type profond :</span><span class="sxs-lookup"><span data-stu-id="86b0e-259">Offset array for deep type columns:</span></span>  
  
    ```  
    2 + 2 * [number of deep type columns] = 2 + 2 * 1 = 4  
    ```  
  
-   <span data-ttu-id="86b0e-260">Tableau NULL = 1</span><span class="sxs-lookup"><span data-stu-id="86b0e-260">NULL array = 1</span></span>  
  
-   <span data-ttu-id="86b0e-261">Remplissage du tableau NULL = 1, car la taille du tableau NULL est impaire et il existe une colonne de type profond.</span><span class="sxs-lookup"><span data-stu-id="86b0e-261">NULL array padding = 1, as the NULL array size is odd and there is a deep type column.</span></span>  
  
-   <span data-ttu-id="86b0e-262">Remplissage</span><span class="sxs-lookup"><span data-stu-id="86b0e-262">Padding</span></span>  
  
    -   <span data-ttu-id="86b0e-263">8 est la spécification d'alignement maximale.</span><span class="sxs-lookup"><span data-stu-id="86b0e-263">8 is the largest alignment requirement.</span></span>  
  
    -   <span data-ttu-id="86b0e-264">La taille est actuellement 16 + 0 + 4 + 1 + 1 = 22.</span><span class="sxs-lookup"><span data-stu-id="86b0e-264">Size so far is 16 + 0 + 4 + 1 + 1 = 22.</span></span>  
  
    -   <span data-ttu-id="86b0e-265">Le multiple le plus proche de 8 est 24.</span><span class="sxs-lookup"><span data-stu-id="86b0e-265">Nearest multiple of 8 is 24.</span></span>  
  
    -   <span data-ttu-id="86b0e-266">Le remplissage total est 24 - 22 = 2 octets.</span><span class="sxs-lookup"><span data-stu-id="86b0e-266">Total padding is 24 - 22 = 2 bytes.</span></span>  
  
-   <span data-ttu-id="86b0e-267">Aucune colonne de type profond à longueur fixe (Colonnes de type profond à longueur fixe : 0).</span><span class="sxs-lookup"><span data-stu-id="86b0e-267">There are no fixed-length deep type columns (Fixed-length deep type columns: 0.).</span></span>  
  
-   <span data-ttu-id="86b0e-268">La taille réelle de la colonne de type profond est 2 \* 78 = 156.</span><span class="sxs-lookup"><span data-stu-id="86b0e-268">The actual size of deep type column is 2 \* 78 = 156.</span></span> <span data-ttu-id="86b0e-269">La colonne de type profond OrderDescription est de type nvarchar.</span><span class="sxs-lookup"><span data-stu-id="86b0e-269">The single deep type column OrderDescription has type nvarchar.</span></span>  
  
```  
[actual row body size] = 24 + 156 = 180 bytes  
```  
  
 <span data-ttu-id="86b0e-270">Pour effectuer le calcul :</span><span class="sxs-lookup"><span data-stu-id="86b0e-270">To complete the calculation:</span></span>  
  
```  
[row size] = 32 + 180 = 212 bytes  
[table size] = 8 * 16384 + 212 * 8379 = 131072 + 1776348 = 1907420  
```  
  
 <span data-ttu-id="86b0e-271">La taille totale de la table en mémoire est donc de 2 mégaoctets environ.</span><span class="sxs-lookup"><span data-stu-id="86b0e-271">Total table size in memory is thus approximately 2 megabytes.</span></span> <span data-ttu-id="86b0e-272">Cela ne prend pas en compte le traitement potentiel de l'allocation de mémoire, ni les contrôles de version de ligne requis pour les transactions qui accèdent à cette table.</span><span class="sxs-lookup"><span data-stu-id="86b0e-272">This does not account for potential overhead incurred by memory allocation as well as any row versioning required for the transactions accessing this table.</span></span>  
  
 <span data-ttu-id="86b0e-273">La mémoire réelle allouée et utilisée par cette table et ses index peut être obtenue via la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="86b0e-273">The actual memory allocated for and used by this table and its indexes can be obtained through the following query:</span></span>  
  
```sql  
select * from sys.dm_db_xtp_table_memory_stats  
where object_id = object_id('dbo.Orders')  
```  
  
## <a name="see-also"></a><span data-ttu-id="86b0e-274">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86b0e-274">See Also</span></span>  
 [<span data-ttu-id="86b0e-275">Tables à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="86b0e-275">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
