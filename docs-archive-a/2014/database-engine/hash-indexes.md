---
title: Index de hachage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f4bdc9c1-7922-4fac-8183-d11ec58fec4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8d1e3a5d92078cc2ec3fe7cd5b6d3fb5b47c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708588"
---
# <a name="hash-indexes"></a><span data-ttu-id="2c919-102">Index de hachage</span><span class="sxs-lookup"><span data-stu-id="2c919-102">Hash Indexes</span></span>
  <span data-ttu-id="2c919-103">Les index sont utilisés comme points d'entrée pour les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="2c919-103">Indexes are used as entry points for memory-optimized tables.</span></span> <span data-ttu-id="2c919-104">La lecture de lignes dans une table requiert un index pour localiser les données en mémoire.</span><span class="sxs-lookup"><span data-stu-id="2c919-104">Reading rows from a table requires an index to locate the data in memory.</span></span>  
  
 <span data-ttu-id="2c919-105">Un index de hachage se compose d'une collection de compartiments organisés dans un tableau.</span><span class="sxs-lookup"><span data-stu-id="2c919-105">A hash index consists of a collection of buckets organized in an array.</span></span> <span data-ttu-id="2c919-106">Une fonction de hachage mappe les clés d'index aux compartiments correspondants dans l'index de hachage.</span><span class="sxs-lookup"><span data-stu-id="2c919-106">A hash function maps index keys to corresponding buckets in the hash index.</span></span> <span data-ttu-id="2c919-107">L'illustration suivante montre trois clés d'index qui sont mappées à trois compartiments différents dans l'index de hachage.</span><span class="sxs-lookup"><span data-stu-id="2c919-107">The following figure shows three index keys that are mapped to three different buckets in the hash index.</span></span> <span data-ttu-id="2c919-108">Dans l'illustration, le nom de fonction de hachage est f (x).</span><span class="sxs-lookup"><span data-stu-id="2c919-108">For illustration purposes the hash function name is f(x).</span></span>  
  
 <span data-ttu-id="2c919-109">![Clés d'index mappées à des compartiments.](../../2014/database-engine/media/hekaton-tables-2.gif "Clés d'index mappées à des compartiments.")</span><span class="sxs-lookup"><span data-stu-id="2c919-109">![Index keys mapped to different buckets.](../../2014/database-engine/media/hekaton-tables-2.gif "Index keys mapped to different buckets.")</span></span>  
  
 <span data-ttu-id="2c919-110">La fonction de hachage utilisée pour les index de hachage présente les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="2c919-110">The hashing function used for hash indexes has the following characteristics:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="2c919-111">possède une fonction de hachage utilisée pour tous les index de hachage.</span><span class="sxs-lookup"><span data-stu-id="2c919-111">has one hash function that is used for all hash indexes.</span></span>  
  
-   <span data-ttu-id="2c919-112">La fonction de hachage est déterministe.</span><span class="sxs-lookup"><span data-stu-id="2c919-112">The hash function is deterministic.</span></span> <span data-ttu-id="2c919-113">La même clé d'index est toujours mappée vers le même compartiment dans l'index de hachage.</span><span class="sxs-lookup"><span data-stu-id="2c919-113">The same index key is always mapped to the same bucket in the hash index.</span></span>  
  
-   <span data-ttu-id="2c919-114">Plusieurs clés d'index peuvent être mappées au même compartiment de hachage.</span><span class="sxs-lookup"><span data-stu-id="2c919-114">Multiple index keys may be mapped to the same hash bucket.</span></span>  
  
-   <span data-ttu-id="2c919-115">La fonction de hachage est équilibrée, ce qui signifie que la distribution des valeurs de clé d'index sur les compartiments de hachage suit généralement une distribution Poisson.</span><span class="sxs-lookup"><span data-stu-id="2c919-115">The hash function is balanced, meaning that the distribution of index key values over hash buckets typically follows a Poisson distribution.</span></span>  
  
     <span data-ttu-id="2c919-116">La distribution Poisson n'est pas une distribution uniforme.</span><span class="sxs-lookup"><span data-stu-id="2c919-116">Poisson distribution is not an even distribution.</span></span> <span data-ttu-id="2c919-117">Les valeurs de clé d'index ne sont pas distribuées uniformément dans les compartiments de hachage.</span><span class="sxs-lookup"><span data-stu-id="2c919-117">Index key values are not evenly distributed in the hash buckets.</span></span> <span data-ttu-id="2c919-118">Par exemple, une distribution Poisson de *n* clés distinctes sur *n* compartiments de hachage résulte dans environ un tiers de compartiments vides, un tiers de compartiments contenant une clé d'index, et le dernier tiers contenant deux clés d'index.</span><span class="sxs-lookup"><span data-stu-id="2c919-118">For example, a Poisson distribution of *n* distinct index keys over *n* hash buckets results in approximately one third empty buckets, one third of the buckets containing one index key, and the other third containing two index keys.</span></span> <span data-ttu-id="2c919-119">Un petit nombre de compartiments contiendra plus de deux clés.</span><span class="sxs-lookup"><span data-stu-id="2c919-119">A small number of buckets will contain more than two keys.</span></span>  
  
 <span data-ttu-id="2c919-120">Si deux clés d'index sont mappées au même compartiment de hachage, il existe une collision de hachage.</span><span class="sxs-lookup"><span data-stu-id="2c919-120">If two index keys are mapped to the same hash bucket, there is a hash collision.</span></span> <span data-ttu-id="2c919-121">Un grand nombre de collisions de hachage peut avoir un impact sur les performances des opérations de lecture.</span><span class="sxs-lookup"><span data-stu-id="2c919-121">A large number of hash collisions can have a performance impact on read operations.</span></span>  
  
 <span data-ttu-id="2c919-122">La structure de l'index de hachage en mémoire comporte un tableau de pointeurs de mémoire.</span><span class="sxs-lookup"><span data-stu-id="2c919-122">The in-memory hash index structure consists of an array of memory pointers.</span></span> <span data-ttu-id="2c919-123">Chaque compartiment mappe à un décalage dans ce tableau.</span><span class="sxs-lookup"><span data-stu-id="2c919-123">Each bucket maps to an offset in this array.</span></span> <span data-ttu-id="2c919-124">Chaque compartiment dans le tableau pointe sur la première ligne dans ce compartiment de hachage.</span><span class="sxs-lookup"><span data-stu-id="2c919-124">Each bucket in the array points to the first row in that hash bucket.</span></span> <span data-ttu-id="2c919-125">Chaque ligne dans le compartiment pointe sur la ligne suivante, ce qui résulte dans une chaîne de lignes pour chaque compartiment de hachage, comme illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2c919-125">Each row in the bucket points to the next row, thus resulting in a chain of rows for each hash bucket, as illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="2c919-126">![Structure de l'index de hachage en mémoire.](../../2014/database-engine/media/hekaton-tables-3.gif "Structure de l'index de hachage en mémoire.")</span><span class="sxs-lookup"><span data-stu-id="2c919-126">![The in-memory hash index structure.](../../2014/database-engine/media/hekaton-tables-3.gif "The in-memory hash index structure.")</span></span>  
  
 <span data-ttu-id="2c919-127">L'illustration comprend trois compartiments avec des lignes.</span><span class="sxs-lookup"><span data-stu-id="2c919-127">The figure has three buckets with rows.</span></span> <span data-ttu-id="2c919-128">Le deuxième compartiment supérieur contient les trois lignes rouges.</span><span class="sxs-lookup"><span data-stu-id="2c919-128">The second bucket from the top contains the three red rows.</span></span> <span data-ttu-id="2c919-129">La quatrième compartiment contient une seule ligne bleue.</span><span class="sxs-lookup"><span data-stu-id="2c919-129">The fourth bucket contains the single blue row.</span></span> <span data-ttu-id="2c919-130">Le compartiment inférieur contient les deux lignes vertes.</span><span class="sxs-lookup"><span data-stu-id="2c919-130">The bottom bucket contains the two green rows.</span></span> <span data-ttu-id="2c919-131">Il peut s'agir de versions différentes de la même ligne.</span><span class="sxs-lookup"><span data-stu-id="2c919-131">These could be different versions of the same row.</span></span>  
  
 <span data-ttu-id="2c919-132">Pour plus d'informations sur les index des tables mémoire optimisées, consultez [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2c919-132">For more information about indexes for memory-optimized tables, see [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c919-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c919-133">See Also</span></span>  
 [<span data-ttu-id="2c919-134">Index sur des tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="2c919-134">Indexes on Memory-Optimized Tables</span></span>](../../2014/database-engine/indexes-on-memory-optimized-tables.md)  
  
  
