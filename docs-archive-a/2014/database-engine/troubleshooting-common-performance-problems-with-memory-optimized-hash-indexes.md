---
title: Résolution des problèmes de performances courants avec les index de hachage mémoire optimisés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 1954a997-7585-4713-81fd-76d429b8d095
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cef98571edd7736bc45ba8caf17451007a74cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696031"
---
# <a name="troubleshooting-common-performance-problems-with-memory-optimized-hash-indexes"></a><span data-ttu-id="19037-102">Résoudre les problèmes de performance courants avec les index de hachage mémoire optimisés</span><span class="sxs-lookup"><span data-stu-id="19037-102">Troubleshooting Common Performance Problems with Memory-Optimized Hash Indexes</span></span>
  <span data-ttu-id="19037-103">Cette rubrique traite du dépannage et des solutions de contournement des problèmes couramment rencontrés avec les index de hachage.</span><span class="sxs-lookup"><span data-stu-id="19037-103">This topic will focus on troubleshooting and working around common issues with hash indexes.</span></span>  
  
## <a name="search-requires-a-subset-of-hash-index-key-columns"></a><span data-ttu-id="19037-104">La recherche nécessite un sous-ensemble de colonnes clés d'index de hachage</span><span class="sxs-lookup"><span data-stu-id="19037-104">Search Requires a Subset of Hash Index Key Columns</span></span>  
 <span data-ttu-id="19037-105">**Problème :** Les index de hachage requièrent des valeurs pour toutes les colonnes de clés d’index afin de calculer la valeur de hachage et de rechercher les lignes correspondantes dans la table de hachage.</span><span class="sxs-lookup"><span data-stu-id="19037-105">**Issue:** Hash indexes require values for all index key columns in order to compute the hash value, and locate the corresponding rows in the hash table.</span></span> <span data-ttu-id="19037-106">Par conséquent, si une requête contient des prédicats d'égalité pour un seul sous-ensemble de clés d'index dans la clause WHERE, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ne peut pas utiliser la recherche d'index pour trouver les lignes correspondant aux prédicats dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="19037-106">Therefore, if a query includes equality predicates for only a subset of the index keys in the WHERE clause, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot use an index seek to locate the rows corresponding to the predicates in the WHERE clause.</span></span>  
  
 <span data-ttu-id="19037-107">Par opposition, les index triés comme les index non cluster sur disque et les index non cluster mémoire optimisés, prennent en charge la recherche d'index sur un sous-ensemble de colonnes clés d'index, tant qu'il s'agit des premières colonnes de l'index.</span><span class="sxs-lookup"><span data-stu-id="19037-107">In contrast, ordered indexes like the disk-based nonclustered indexes and the memory-optimized nonclustered indexes support index seek on a subset of the index key columns, as long as they are the leading columns in the index.</span></span>  
  
 <span data-ttu-id="19037-108">**Symptôme :** Cela entraîne une dégradation des performances, car elle [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] doit exécuter des analyses de tables complètes plutôt qu’une recherche d’index, ce qui est généralement plus rapide.</span><span class="sxs-lookup"><span data-stu-id="19037-108">**Symptom:** This results in a performance degradation, as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] needs to execute full table scans rather than an index seek, which is typically a faster operation.</span></span>  
  
 <span data-ttu-id="19037-109">**Comment résoudre les problèmes :** Outre la dégradation des performances, l’inspection des plans de requête présente une analyse au lieu d’une recherche d’index.</span><span class="sxs-lookup"><span data-stu-id="19037-109">**How to troubleshoot:** Besides the performance degradation, inspection of the query plans will show a scan instead of an index seek.</span></span> <span data-ttu-id="19037-110">Si la requête est relativement simple, l'inspection du texte de la requête et de la définition d'index montrera également si la recherche nécessite un sous-ensemble de colonnes clés d'index.</span><span class="sxs-lookup"><span data-stu-id="19037-110">If the query is fairly simple, inspection of the query text and index definition will also show whether the search requires a subset of the index key columns.</span></span>  
  
 <span data-ttu-id="19037-111">Prenons l'exemple de la table et de la requête suivantes :</span><span class="sxs-lookup"><span data-stu-id="19037-111">Consider the following table and query:</span></span>  
  
```sql  
CREATE TABLE [dbo].[od]  
(  
     o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
     CONSTRAINT PK_od PRIMARY KEY NONCLUSTERED HASH (o_id, od_id) WITH (BUCKET_COUNT = 10000)  
)  
WITH (MEMORY_OPTIMIZED = ON)  
  
 SELECT p_id  
 FROM dbo.od  
 WHERE o_id=1  
```  
  
 <span data-ttu-id="19037-112">La table a un index de hachage sur les deux colonnes (o_id, od_id), tandis que la requête a un prédicat d'égalité sur (o_id).</span><span class="sxs-lookup"><span data-stu-id="19037-112">The table has a hash index on the two columns (o_id, od_id), while the query has an equality predicate on (o_id).</span></span> <span data-ttu-id="19037-113">Étant donné que la requête possède des prédicats d'égalité uniquement sur un sous-ensemble de colonnes clés d'index, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ne peut pas effectuer d'opération de recherche d'index à l'aide de PK_od ; à la place, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] doit revenir à une analyse complète d'index.</span><span class="sxs-lookup"><span data-stu-id="19037-113">As the query has equality predicates on only a subset of the index key columns, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot perform an index seek operation using PK_od; instead, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has to revert to a full index scan.</span></span>  
  
 <span data-ttu-id="19037-114">**Solutions de contournement :** Il existe plusieurs solutions possibles.</span><span class="sxs-lookup"><span data-stu-id="19037-114">**Workarounds:** There are a number of possible workarounds.</span></span> <span data-ttu-id="19037-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="19037-115">For example:</span></span>  
  
-   <span data-ttu-id="19037-116">Recréez l'index en tant que type non cluster au lieu d'un hachage non cluster.</span><span class="sxs-lookup"><span data-stu-id="19037-116">Recreate the index as type nonclustered instead of nonclustered hash.</span></span> <span data-ttu-id="19037-117">L'index mémoire optimisé non cluster est trié, et [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] peut effectuer une recherche d'index sur les colonnes clés d'index.</span><span class="sxs-lookup"><span data-stu-id="19037-117">The memory-optimized nonclustered index is ordered, and thus [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can perform an index seek on the leading index key columns.</span></span> <span data-ttu-id="19037-118">La définition de clé primaire de l'exemple serait `constraint PK_od primary key nonclustered`.</span><span class="sxs-lookup"><span data-stu-id="19037-118">The resulting primary key definition for the example would be `constraint PK_od primary key nonclustered`.</span></span>  
  
-   <span data-ttu-id="19037-119">Modifiez la clé d'index actuelle pour correspondre aux colonnes dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="19037-119">Change the current index key to match the columns in the WHERE clause.</span></span>  
  
-   <span data-ttu-id="19037-120">Ajoutez un nouvel index de hachage qui correspond aux colonnes dans la clause WHERE de la requête.</span><span class="sxs-lookup"><span data-stu-id="19037-120">Add a new hash index that matches with the columns in the WHERE clause of the query.</span></span> <span data-ttu-id="19037-121">Dans l'exemple, la définition de table s'apparenterait à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="19037-121">In the example, the resulting table definition would look at follows:</span></span>  
  
    ```sql  
    CREATE TABLE dbo.od  
     ( o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
  
     CONSTRAINT PK_od PRIMARY KEY   
     NONCLUSTERED HASH (o_id,od_id) WITH (BUCKET_COUNT=10000),  
  
     INDEX ix_o_id NONCLUSTERED HASH (o_id) WITH (BUCKET_COUNT=10000)  
  
     ) WITH (MEMORY_OPTIMIZED=ON)  
    ```  
  
 <span data-ttu-id="19037-122">Notez qu'un index de hachage mémoire optimisé ne fonctionne pas de façon optimale s'il existe de nombreuses lignes dupliquées pour une valeur de clé d'index donnée : dans l'exemple, si le nombre de valeurs uniques pour la colonne o_id est beaucoup plus petit que le nombre de lignes dans la table, il n'est pas conseillé d'ajouter un index sur (o_id) ; à la place, changer le type de l'index PK_od en le modifiant d'index de hachage en index non cluster est la meilleure solution.</span><span class="sxs-lookup"><span data-stu-id="19037-122">Note that a memory-optimized hash index does not perform optimally if there are a lot of duplicate rows for a given index key value: in the example, if the number of unique values for the column o_id is much smaller than the number of rows in the table, it would not be optimal to add an index on (o_id); instead, changing the type of the index PK_od from hash to nonclustered would be the better solution.</span></span> <span data-ttu-id="19037-123">Pour plus d'informations, consultez [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="19037-123">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19037-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19037-124">See Also</span></span>  
 [<span data-ttu-id="19037-125">Index sur des tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="19037-125">Indexes on Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
