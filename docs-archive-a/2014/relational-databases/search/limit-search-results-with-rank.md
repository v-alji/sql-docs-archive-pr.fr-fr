---
title: Limiter les résultats de la recherche avec RANK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- row ranking [full-text search]
- relevance ranking values [full-text search]
- full-text search [SQL Server], rankings
- index rankings [full-text search]
- ranked results [full-text search]
- rankings [full-text search]
- per-row rank values [full-text search]
ms.assetid: 06a776e6-296c-4ec7-9fa5-0794709ccb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab1b930b3238cb541965e1984d1561f1a1c22d87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702608"
---
# <a name="limit-search-results-with-rank"></a><span data-ttu-id="b02b4-102">Limiter les résultats de la recherche avec RANK</span><span class="sxs-lookup"><span data-stu-id="b02b4-102">Limit Search Results with RANK</span></span>
  <span data-ttu-id="b02b4-103">Les fonctions [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) et [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) retournent une colonne appelée RANK qui contient des valeurs ordinales comprises entre 0 et 1000 (valeurs de classement).</span><span class="sxs-lookup"><span data-stu-id="b02b4-103">The [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) and [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) functions return a column named RANK that contains ordinal values from 0 through 1000 (rank values).</span></span> <span data-ttu-id="b02b4-104">Ces valeurs servent à établir le rang des lignes retournées en fonction de leur correspondance par rapport aux critères de sélection.</span><span class="sxs-lookup"><span data-stu-id="b02b4-104">These values are used to rank the rows returned according to how well they match the selection criteria.</span></span> <span data-ttu-id="b02b4-105">Les valeurs de classement indiquent uniquement un ordre relatif de pertinence pour les lignes du jeu de résultats. Une valeur inférieure indique une pertinence plus faible.</span><span class="sxs-lookup"><span data-stu-id="b02b4-105">The rank values indicate only a relative order of relevance of the rows in the result set, with a lower value indicating lower relevance.</span></span> <span data-ttu-id="b02b4-106">Les valeurs réelles sont sans importance et sont généralement différentes d'une exécution de requête à une autre.</span><span class="sxs-lookup"><span data-stu-id="b02b4-106">The actual values are unimportant and typically differ each time the query is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b02b4-107">Les prédicats CONTAINS et FREETEXT ne retournent aucune valeur de rang.</span><span class="sxs-lookup"><span data-stu-id="b02b4-107">The CONTAINS and FREETEXT predicates do not return any rank values.</span></span>  
  
 <span data-ttu-id="b02b4-108">Le nombre d'éléments répondant à une condition de recherche est souvent très élevé.</span><span class="sxs-lookup"><span data-stu-id="b02b4-108">The number of items matching a search condition is often very large.</span></span> <span data-ttu-id="b02b4-109">Pour éviter que les requêtes CONTAINSTABLE ou FREETEXTTABLE ne retournent un trop grand nombre de correspondances, utilisez le paramètre facultatif *top_n_by_rank* , qui retourne uniquement un sous-ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="b02b4-109">To prevent CONTAINSTABLE or FREETEXTTABLE queries from returning too many matches, use the optional *top_n_by_rank* parameter, which returns only a subset of rows.</span></span> <span data-ttu-id="b02b4-110">*top_n_by_rank* est une valeur entière, *n*, qui spécifie que seules les *n* correspondances de classement le plus élevé doivent être retournées, par ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="b02b4-110">*top_n_by_rank* is an integer value, *n*, that specifies that only the *n* highest ranked matches are to be returned, in descending order.</span></span> <span data-ttu-id="b02b4-111">Si *top_n_by_rank* est associé à d’autres paramètres, la requête peut retourner moins de lignes que le nombre de lignes correspondant effectivement à tous les prédicats.</span><span class="sxs-lookup"><span data-stu-id="b02b4-111">If *top_n_by_rank* is combined with other parameters, the query could return fewer rows than the number of rows that actually match all the predicates.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="b02b4-112">classe les correspondances par rang et ne retourne au maximum que le nombre de lignes spécifié.</span><span class="sxs-lookup"><span data-stu-id="b02b4-112">orders the matches by rank and returns only up to the specified number of rows.</span></span> <span data-ttu-id="b02b4-113">Ce choix peut considérablement améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="b02b4-113">This choice can result in a dramatic increase in performance.</span></span> <span data-ttu-id="b02b4-114">Par exemple, une requête qui doit normalement retourner 100 000 lignes d'une table en comprenant 1 million est traitée plus rapidement si seules les 100 premières lignes sont demandées.</span><span class="sxs-lookup"><span data-stu-id="b02b4-114">For example, a query that would normally return 100,000 rows from a table of one million rows are processed more quickly if only the top 100 rows are requested.</span></span>  
  
##  <a name="examples-of-using-rank-to-limit-search-results"></a><a name="examples"></a> <span data-ttu-id="b02b4-115">Exemples d'utilisation de RANK pour limiter les résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="b02b4-115">Examples of Using RANK to Limit Search Results</span></span>  
  
### <a name="example-a-searching-for-only-the-top-three-matches"></a><span data-ttu-id="b02b4-116">Exemple A : recherche des trois premières correspondances uniquement</span><span class="sxs-lookup"><span data-stu-id="b02b4-116">Example A: Searching for only the top three matches</span></span>  
 <span data-ttu-id="b02b4-117">L'exemple suivant utilise CONTAINSTABLE pour retourner uniquement les trois premières correspondances.</span><span class="sxs-lookup"><span data-stu-id="b02b4-117">The following example uses CONTAINSTABLE to return only the top three matches.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT K.RANK, AddressLine1, City  
FROM Person.Address AS A  
  INNER JOIN  
  CONTAINSTABLE(Person.Address, AddressLine1, 'ISABOUT ("des*",  
    Rue WEIGHT(0.5),  
    Bouchers WEIGHT(0.9))',  
    3) AS K  
  ON A.AddressID = K.[KEY]  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
RANK        Address                          City  
----------- -------------------------------- ------------------------------  
172         9005, rue des Bouchers           Paris  
172         5, rue des Bouchers              Orleans  
172         5, rue des Bouchers              Metz  
  
(3 row(s) affected)  
```  
  
  
### <a name="example-b-searching-for-the-top-ten-matches"></a><span data-ttu-id="b02b4-118">Exemple B : recherche des dix premières correspondances</span><span class="sxs-lookup"><span data-stu-id="b02b4-118">Example B: Searching for the top ten matches</span></span>  
 <span data-ttu-id="b02b4-119">L'exemple suivant utilise CONTAINSTABLE pour retourner la description des 5 premiers produits dont la colonne `Description` contient les mots « aluminum » à proximité du mot « light » ou « lightweight ».</span><span class="sxs-lookup"><span data-stu-id="b02b4-119">The following example uses CONTAINSTABLE to return the description of the top 5 products where the `Description` column contains the word "aluminum" near either the word "light" or the word "lightweight".</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT FT_TBL.ProductDescriptionID,  
   FT_TBL.Description,   
   KEY_TBL.RANK  
FROM Production.ProductDescription AS FT_TBL INNER JOIN  
   CONTAINSTABLE (Production.ProductDescription,  
      Description,   
      '(light NEAR aluminum) OR  
      (lightweight NEAR aluminum)',  
      5  
   ) AS KEY_TBL  
   ON FT_TBL.ProductDescriptionID = KEY_TBL.[KEY]  
GO  
```  
  
  
##  <a name="how-search-query-results-are-ranked"></a><a name="how"></a> <span data-ttu-id="b02b4-120">Classement des résultats d'une requête de recherche</span><span class="sxs-lookup"><span data-stu-id="b02b4-120">How Search Query Results Are Ranked</span></span>  
 <span data-ttu-id="b02b4-121">Une recherche en texte intégral dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] peut générer un score facultatif (ou valeur de classement) qui indique la pertinence des données retournées par une requête de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="b02b4-121">Full-text search in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can generate an optional score (or rank value) that indicates the relevance of the data returned by a full-text query.</span></span> <span data-ttu-id="b02b4-122">Cette valeur de classement est calculée sur chaque ligne et peut être utilisée comme critère de tri pour trier le jeu de résultats d'une requête donnée par pertinence.</span><span class="sxs-lookup"><span data-stu-id="b02b4-122">This rank value is calculated on every row and can be used as an ordering criteria to sort the result set of a given query by relevance.</span></span> <span data-ttu-id="b02b4-123">Les valeurs de classement indiquent uniquement un ordre relatif de pertinence pour les lignes contenues dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="b02b4-123">The rank values indicate only a relative order of relevance of the rows in the result set.</span></span> <span data-ttu-id="b02b4-124">Les valeurs réelles sont sans importance et sont généralement différentes d'une exécution de requête à une autre.</span><span class="sxs-lookup"><span data-stu-id="b02b4-124">The actual values are unimportant and typically differ each time the query is run.</span></span> <span data-ttu-id="b02b4-125">La valeur de classement n'a pas de signification entre les requêtes.</span><span class="sxs-lookup"><span data-stu-id="b02b4-125">The rank value does not hold any significance across queries.</span></span>  
  
### <a name="statistics-for-ranking"></a><span data-ttu-id="b02b4-126">Statistiques de classement</span><span class="sxs-lookup"><span data-stu-id="b02b4-126">Statistics for Ranking</span></span>  
 <span data-ttu-id="b02b4-127">Lors de la création d'un index, des statistiques sont recueillies à des fins de classement.</span><span class="sxs-lookup"><span data-stu-id="b02b4-127">When an index is built, statistics are collected for use in ranking.</span></span> <span data-ttu-id="b02b4-128">Le processus de création d'un catalogue de texte intégral n'aboutit pas directement à une structure d'index unique.</span><span class="sxs-lookup"><span data-stu-id="b02b4-128">The process of building a full-text catalog does not directly result in a single index structure.</span></span> <span data-ttu-id="b02b4-129">À la place, le Moteur d'indexation et de recherche en texte intégral Microsoft pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] crée des index intermédiaires au fur et à mesure de l'indexation des données.</span><span class="sxs-lookup"><span data-stu-id="b02b4-129">Instead, the Full-Text Engine for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] creates intermediate indexes as data is indexed.</span></span> <span data-ttu-id="b02b4-130">Il fusionne ensuite ces index dans un index de plus grande taille en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b02b4-130">The Full-Text Engine then merges these indexes into a larger index as needed.</span></span> <span data-ttu-id="b02b4-131">Ce processus peut se répéter à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="b02b4-131">This process can be repeated many times.</span></span> <span data-ttu-id="b02b4-132">Le Moteur d'indexation et de recherche en texte intégral mène ensuite une « fusion principale » qui associe tous les index intermédiaires dans un index principal de plus grande taille.</span><span class="sxs-lookup"><span data-stu-id="b02b4-132">The Full-Text Engine then conducts a "master merge" that combines all of the intermediate indexes into one large master index.</span></span>  
  
 <span data-ttu-id="b02b4-133">Des statistiques sont recueillies à chaque niveau d'index intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="b02b4-133">Statistics are collected at each intermediate index level.</span></span> <span data-ttu-id="b02b4-134">Elles fusionnent en même temps que les index.</span><span class="sxs-lookup"><span data-stu-id="b02b4-134">The statistics are merged when the indexes are merged.</span></span> <span data-ttu-id="b02b4-135">Certaines valeurs statistiques ne peuvent être générées que durant la fusion principale.</span><span class="sxs-lookup"><span data-stu-id="b02b4-135">Some statistical values can only be generated during the master merging process.</span></span>  
  
 <span data-ttu-id="b02b4-136">Lorsqu'il classe le jeu de résultats d'une requête, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilise des statistiques provenant du plus grand index intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="b02b4-136">While ranking a query result set, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses statistics from the largest intermediate index.</span></span> <span data-ttu-id="b02b4-137">Cela dépend de la fusion ou non des index intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="b02b4-137">This depends on whether intermediate indexes have been merged or not.</span></span> <span data-ttu-id="b02b4-138">Par conséquent, les statistiques de classement peuvent varier en précision si les index intermédiaires n'ont pas été fusionnés.</span><span class="sxs-lookup"><span data-stu-id="b02b4-138">As a result, ranking statistics can vary in accuracy if the intermediate indexes have not been merged.</span></span> <span data-ttu-id="b02b4-139">C'est la raison pour laquelle la même requête peut retourner différents résultats dans le temps en fonction de l'ajout, de la modification et de la suppression des données indexées en texte intégral, et en fonction de la fusion des index plus petits.</span><span class="sxs-lookup"><span data-stu-id="b02b4-139">This explains why the same query can return different rank results over time as full-text indexed data is added, modified, and deleted, and as the smaller indexes are merged.</span></span>  
  
 <span data-ttu-id="b02b4-140">Pour réduire la taille des index et la complexité des calculs, les statistiques sont souvent arrondies.</span><span class="sxs-lookup"><span data-stu-id="b02b4-140">To minimize the size of the index and computational complexity, statistics are often rounded.</span></span>  
  
 <span data-ttu-id="b02b4-141">La liste ci-dessous comprend des termes et des valeurs statistiques fréquemment utilisés, qui sont d'une grande importance dans le calcul du classement.</span><span class="sxs-lookup"><span data-stu-id="b02b4-141">The list below includes some commonly used terms and statistical values that are important in calculating rank.</span></span>  
  
 <span data-ttu-id="b02b4-142">Propriété</span><span class="sxs-lookup"><span data-stu-id="b02b4-142">Property</span></span>  
 <span data-ttu-id="b02b4-143">Colonne indexée en texte intégral de la ligne.</span><span class="sxs-lookup"><span data-stu-id="b02b4-143">A full-text indexed column of the row.</span></span>  
  
 <span data-ttu-id="b02b4-144">Document</span><span class="sxs-lookup"><span data-stu-id="b02b4-144">Document</span></span>  
 <span data-ttu-id="b02b4-145">Entité retournée dans les requêtes.</span><span class="sxs-lookup"><span data-stu-id="b02b4-145">The entity that is returned in queries.</span></span> <span data-ttu-id="b02b4-146">Dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , cela correspond à une ligne.</span><span class="sxs-lookup"><span data-stu-id="b02b4-146">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] this corresponds to a row.</span></span> <span data-ttu-id="b02b4-147">Un document peut avoir plusieurs propriétés, de même qu'une ligne peut avoir plusieurs colonnes indexées en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="b02b4-147">A document can have multiple properties, just as a row can have multiple full-text indexed columns.</span></span>  
  
 <span data-ttu-id="b02b4-148">Index</span><span class="sxs-lookup"><span data-stu-id="b02b4-148">Index</span></span>  
 <span data-ttu-id="b02b4-149">Index inversé unique d'un ou de plusieurs documents.</span><span class="sxs-lookup"><span data-stu-id="b02b4-149">A single inverted index of one or more documents.</span></span> <span data-ttu-id="b02b4-150">Il peut se trouver entièrement en mémoire ou sur disque.</span><span class="sxs-lookup"><span data-stu-id="b02b4-150">This may be entirely in memory or on disk.</span></span> <span data-ttu-id="b02b4-151">De nombreuses statistiques de requêtes sont relatives à l'index individuel où la correspondance s'est produite.</span><span class="sxs-lookup"><span data-stu-id="b02b4-151">Many query statistics are relative to the individual index where the match occurred.</span></span>  
  
 <span data-ttu-id="b02b4-152">Catalogue de texte intégral</span><span class="sxs-lookup"><span data-stu-id="b02b4-152">Full-Text Catalog</span></span>  
 <span data-ttu-id="b02b4-153">Collection d'index intermédiaires traités en tant qu'entité unique pour les requêtes.</span><span class="sxs-lookup"><span data-stu-id="b02b4-153">A collection of intermediate indexes treated as one entity for queries.</span></span> <span data-ttu-id="b02b4-154">Les catalogues sont l'unité d'organisation visible par l'administrateur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b02b4-154">Catalogs are the unit of organization visible to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="b02b4-155">Mot, jeton ou élément</span><span class="sxs-lookup"><span data-stu-id="b02b4-155">Word, token or item</span></span>  
 <span data-ttu-id="b02b4-156">Unité de correspondance dans le moteur de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="b02b4-156">The unit of matching in the full-text engine.</span></span> <span data-ttu-id="b02b4-157">Les flux de texte des documents sont convertis en mots ; ils peuvent également être convertis en jetons par des analyseurs lexicaux spécifiques aux langues.</span><span class="sxs-lookup"><span data-stu-id="b02b4-157">Streams of text from documents are tokenized into words, or tokens by language-specific word breakers.</span></span>  
  
 <span data-ttu-id="b02b4-158">Occurrence</span><span class="sxs-lookup"><span data-stu-id="b02b4-158">Occurrence</span></span>  
 <span data-ttu-id="b02b4-159">Décalage de mot dans une propriété de document conformément à la définition établie par l'analyseur lexical.</span><span class="sxs-lookup"><span data-stu-id="b02b4-159">The word offset in a document property as determined by the word breaker.</span></span> <span data-ttu-id="b02b4-160">Le premier mot se trouve à l'occurrence 1, le suivant se trouve à l'occurrence 2, etc.</span><span class="sxs-lookup"><span data-stu-id="b02b4-160">The first word is at occurrence 1, the next at 2, and so on.</span></span> <span data-ttu-id="b02b4-161">Pour éviter les affirmations incorrectes dans les requêtes d'expression et de proximité, les fins de phrases et les fins de paragraphes introduisent des écarts d'occurrence plus importants.</span><span class="sxs-lookup"><span data-stu-id="b02b4-161">In order to avoid false positives in phrase and proximity queries, end-of-sentence and end-of-paragraph introduce larger occurrence gaps.</span></span>  
  
 <span data-ttu-id="b02b4-162">TermFrequency</span><span class="sxs-lookup"><span data-stu-id="b02b4-162">TermFrequency</span></span>  
 <span data-ttu-id="b02b4-163">Nombre d'occurrences de la valeur de clé dans une ligne.</span><span class="sxs-lookup"><span data-stu-id="b02b4-163">The number times the key value occurs in a row.</span></span>  
  
 <span data-ttu-id="b02b4-164">IndexedRowCount</span><span class="sxs-lookup"><span data-stu-id="b02b4-164">IndexedRowCount</span></span>  
 <span data-ttu-id="b02b4-165">Nombre total de lignes indexées.</span><span class="sxs-lookup"><span data-stu-id="b02b4-165">Total number of rows indexed.</span></span> <span data-ttu-id="b02b4-166">Cette valeur est calculée à partir des nombres conservés dans les index intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="b02b4-166">This is computed, based on counts maintained in the intermediate indexes.</span></span> <span data-ttu-id="b02b4-167">La précision du résultat peut varier.</span><span class="sxs-lookup"><span data-stu-id="b02b4-167">This number can vary in accuracy.</span></span>  
  
 <span data-ttu-id="b02b4-168">KeyRowCount</span><span class="sxs-lookup"><span data-stu-id="b02b4-168">KeyRowCount</span></span>  
 <span data-ttu-id="b02b4-169">Nombre total de lignes du catalogue de texte intégral contenant une clé donnée.</span><span class="sxs-lookup"><span data-stu-id="b02b4-169">Total number of rows in the full-text catalog that contain a given key.</span></span>  
  
 <span data-ttu-id="b02b4-170">MaxOccurrence</span><span class="sxs-lookup"><span data-stu-id="b02b4-170">MaxOccurrence</span></span>  
 <span data-ttu-id="b02b4-171">Occurrence la plus importante stockée dans un catalogue de texte intégral pour une propriété donnée dans une ligne.</span><span class="sxs-lookup"><span data-stu-id="b02b4-171">The largest occurrence stored in a full-text catalog for a given property in a row.</span></span>  
  
 <span data-ttu-id="b02b4-172">MaxQueryRank</span><span class="sxs-lookup"><span data-stu-id="b02b4-172">MaxQueryRank</span></span>  
 <span data-ttu-id="b02b4-173">Rang maximal, 1000, retourné par le Moteur d'indexation et de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="b02b4-173">The maximum rank, 1000, returned by the Full-Text Engine.</span></span>  
  
  
### <a name="rank-computation-issues"></a><span data-ttu-id="b02b4-174">Problèmes de calcul de rang</span><span class="sxs-lookup"><span data-stu-id="b02b4-174">Rank Computation Issues</span></span>  
 <span data-ttu-id="b02b4-175">Le processus de calcul du rang dépend d'un certain nombre de facteurs.</span><span class="sxs-lookup"><span data-stu-id="b02b4-175">The process of computing rank, depends on a number of factors.</span></span>  <span data-ttu-id="b02b4-176">Les analyseurs lexicaux des diverses langues créent des jetons de texte de manière différente.</span><span class="sxs-lookup"><span data-stu-id="b02b4-176">Different language word breakers tokenize text differently.</span></span> <span data-ttu-id="b02b4-177">Par exemple, la chaîne « après-midi » peut être décomposée en « après » « midi » par un analyseur lexical et en « après-midi » par un autre.</span><span class="sxs-lookup"><span data-stu-id="b02b4-177">For example, the string "dog-house" could be broken into "dog" "house" by one word breaker and into "dog-house" by another.</span></span> <span data-ttu-id="b02b4-178">En d'autres termes, la correspondance et le classement varient en fonction de la langue spécifiée, car les mots sont différents et la longueur du document l'est également.</span><span class="sxs-lookup"><span data-stu-id="b02b4-178">This means that matching and ranking will vary based on the language specified, because not only are the words different, but so is the document length.</span></span> <span data-ttu-id="b02b4-179">La différence de longueur d'un document peut affecter le classement pour toutes les requêtes.</span><span class="sxs-lookup"><span data-stu-id="b02b4-179">The document length difference can affect ranking for all queries.</span></span>  
  
 <span data-ttu-id="b02b4-180">Les statistiques telles que `IndexRowCount` peuvent fortement varier.</span><span class="sxs-lookup"><span data-stu-id="b02b4-180">Statistics such as `IndexRowCount` can vary widely.</span></span> <span data-ttu-id="b02b4-181">Par exemple, si un catalogue a 2 milliards de lignes dans l'index principal, un nouveau document est indexé dans un index intermédiaire en mémoire ; par ailleurs, les rangs de ce document qui sont basés sur le nombre de documents dans l'index en mémoire peuvent être incorrects par rapport aux rangs des documents de l'index principal.</span><span class="sxs-lookup"><span data-stu-id="b02b4-181">For example, if a catalog has 2 billion rows in the master index, then one new document is indexed into an in-memory intermediate index, and ranks for that document based on the number of documents in the in-memory index could be skewed compared with ranks for documents from the master index.</span></span> <span data-ttu-id="b02b4-182">Par conséquent, lorsqu'un remplissage entraîne l'indexation ou la réindexation d'un grand nombre de lignes, il est recommandé de fusionner les index dans un index principal via l'instruction ALTER FULLTEXT CATALOG ... Instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="b02b4-182">For this reason, it is recommended that after any population that results in large number of rows being indexed or re-indexed the indexes be merged into a master index using the ALTER FULLTEXT CATALOG ... REORGANIZE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="b02b4-183">Le Moteur d'indexation et de recherche en texte intégral fusionne automatiquement les index en fonction de paramètres tels que le nombre et la taille des index intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="b02b4-183">The Full-Text Engine will also automatically merge the indexes based on parameters such as the number and size of intermediate indexes.</span></span>  
  
 <span data-ttu-id="b02b4-184">Les valeurs `MaxOccurrence` sont normalisées sous forme de 32 plages individuelles.</span><span class="sxs-lookup"><span data-stu-id="b02b4-184">`MaxOccurrence` values are normalized into 1 of 32 ranges.</span></span> <span data-ttu-id="b02b4-185">Par exemple, un document de 50 mots est traité de la même façon qu'un document de 100 mots.</span><span class="sxs-lookup"><span data-stu-id="b02b4-185">This means, for example, that a document 50 words long is treated the same as a document 100 words long.</span></span> <span data-ttu-id="b02b4-186">Vous trouverez ci-dessous le tableau de normalisation utilisé.</span><span class="sxs-lookup"><span data-stu-id="b02b4-186">Below is the table used for normalization.</span></span> <span data-ttu-id="b02b4-187">Étant donné que les longueurs de document sont comprises entre les valeurs de table adjacentes 32 et 128, elles sont effectivement traitées comme ayant la même longueur, 128 (32 < `docLength` <= 128).</span><span class="sxs-lookup"><span data-stu-id="b02b4-187">Because the document lengths are in the range between adjacent table values 32 and 128, they are effectively treated as having the same length, 128 (32 < `docLength` <= 128).</span></span>  
  
```  
{ 16, 32, 128, 256, 512, 725, 1024, 1450, 2048, 2896, 4096, 5792, 8192, 11585,   
16384, 23170, 28000, 32768, 39554, 46340, 55938, 65536, 92681, 131072, 185363,   
262144, 370727, 524288, 741455, 1048576, 2097152, 4194304 };  
  
```  
  
  
### <a name="ranking-of-containstable"></a><span data-ttu-id="b02b4-188">Classement de CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="b02b4-188">Ranking of CONTAINSTABLE</span></span>  
 <span data-ttu-id="b02b4-189">Le classement de[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) utilise l’algorithme suivant :</span><span class="sxs-lookup"><span data-stu-id="b02b4-189">[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) ranking uses the following algorithm:</span></span>  
  
```  
StatisticalWeight = Log2( ( 2 + IndexedRowCount ) / KeyRowCount )  
Rank = min( MaxQueryRank, HitCount * 16 * StatisticalWeight / MaxOccurrence )  
```  
  
 <span data-ttu-id="b02b4-190">Les correspondances d'expressions sont classées comme des clés individuelles. Toutefois, `KeyRowCount` (nombre de lignes contenant l'expression) étant estimé, il peut être inexact et supérieur au nombre réel.</span><span class="sxs-lookup"><span data-stu-id="b02b4-190">Phrase matches are ranked just like individual keys except that `KeyRowCount` (the number of rows containing the phrase) is estimated and can be inaccurate and higher than the actual number.</span></span>  
  
 <span data-ttu-id="b02b4-191">**Classement de NEAR**</span><span class="sxs-lookup"><span data-stu-id="b02b4-191">**Ranking of NEAR**</span></span>  
  
 <span data-ttu-id="b02b4-192">CONTAINSTABLE prend en charge l'interrogation de plusieurs termes de recherche à proximité l'un de l'autre à l'aide de l'option NEAR.</span><span class="sxs-lookup"><span data-stu-id="b02b4-192">CONTAINSTABLE supports querying for two or more search terms in proximity to each other by using the NEAR option.</span></span> <span data-ttu-id="b02b4-193">La valeur de classement de chaque ligne retournée est basée sur plusieurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="b02b4-193">The rank value of each returned row is based on several parameters.</span></span> <span data-ttu-id="b02b4-194">Un facteur majeur du classement est le nombre total de correspondances (ou *résultats*) par rapport à la longueur du document.</span><span class="sxs-lookup"><span data-stu-id="b02b4-194">One major ranking factor is the total number of matches (or *hits*) relative to the length of the document.</span></span> <span data-ttu-id="b02b4-195">Par exemple, si un document de 100 mots et un document de 900 mots contiennent des correspondances identiques, le document de 100 mots a un classement supérieur.</span><span class="sxs-lookup"><span data-stu-id="b02b4-195">Thus, for example, if a 100-word document and a 900-word document contain identical matches, the 100-word document is ranked higher.</span></span>  
  
 <span data-ttu-id="b02b4-196">La longueur totale de chaque résultat dans une ligne contribue également au classement de cette ligne en fonction de la distance entre le premier et le dernier terme de recherche de ce résultat.</span><span class="sxs-lookup"><span data-stu-id="b02b4-196">The total length of each hit in a row will also contribute to the ranking of that row based on the distance between the first and last search terms of that hit.</span></span> <span data-ttu-id="b02b4-197">Plus la distance est faible, plus le résultat contribue à la valeur du classement de la ligne.</span><span class="sxs-lookup"><span data-stu-id="b02b4-197">The smaller the distance, the more the hit contributes to the rank value of the row.</span></span> <span data-ttu-id="b02b4-198">Si une requête de texte intégral ne spécifie pas d'entier comme distance maximale, un document qui contient uniquement des résultats séparés de distances supérieures à 100 termes logiques, aura un classement de 0.</span><span class="sxs-lookup"><span data-stu-id="b02b4-198">If a full-text query does not specify an integer as the maximum distance, a document that contains only hits whose distances are greater than 100 logical terms apart, will have a ranking of 0.</span></span>  
  
 <span data-ttu-id="b02b4-199">**Classement de ISABOUT**</span><span class="sxs-lookup"><span data-stu-id="b02b4-199">**Ranking of ISABOUT**</span></span>  
  
 <span data-ttu-id="b02b4-200">CONTAINSTABLE prend en charge les requêtes de recherche de termes pondérés à l'aide de l'option ISABOUT.</span><span class="sxs-lookup"><span data-stu-id="b02b4-200">CONTAINSTABLE supports querying for weighted terms by using the ISABOUT option.</span></span> <span data-ttu-id="b02b4-201">ISABOUT est une requête d'espace vectoriel dans la terminologie traditionnelle de récupération d'informations.</span><span class="sxs-lookup"><span data-stu-id="b02b4-201">ISABOUT is a vector-space query in traditional information retrieval terminology.</span></span> <span data-ttu-id="b02b4-202">L'algorithme de classement par défaut utilisé est celui de Jaccard, une formule très connue.</span><span class="sxs-lookup"><span data-stu-id="b02b4-202">The default ranking algorithm used is Jaccard, a widely known formula.</span></span> <span data-ttu-id="b02b4-203">Le classement est calculé pour chaque nouveau terme de la requête et est ensuite combiné comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b02b4-203">The ranking is computed for each term in the query and then combined as described below.</span></span>  
  
```  
ContainsRank = same formula used for CONTAINSTABLE ranking of a single term (above).  
Weight = the weight specified in the query for each term. Default weight is 1.  
WeightedSum = ??[key=1 to n] ContainsRankKey * WeightKey  
Rank =  ( MaxQueryRank * WeightedSum ) / ( ( ??[key=1 to n] ContainsRankKey^2 )   
      + ( ??[key=1 to n] WeightKey^2 ) - ( WeightedSum ) )  
  
```  
  
  
### <a name="ranking-of-freetexttable"></a><span data-ttu-id="b02b4-204">Classement de FREETEXTTABLE</span><span class="sxs-lookup"><span data-stu-id="b02b4-204">Ranking of FREETEXTTABLE</span></span>  
 <span data-ttu-id="b02b4-205">Le classement de[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) est basé sur la formule de classement OKAPI BM25.</span><span class="sxs-lookup"><span data-stu-id="b02b4-205">[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) ranking is based on the OKAPI BM25 ranking formula.</span></span> <span data-ttu-id="b02b4-206">Les requêtes FREETEXTTABLE ajoutent des mots à la requête via une génération flexionnelle (formes flexionnelles des mots de la requête d'origine) ; ces mots sont traités comme des mots distincts, sans relation particulière avec les mots à partir desquels ils ont été générés.</span><span class="sxs-lookup"><span data-stu-id="b02b4-206">FREETEXTTABLE queries will add words to the query via inflectional generation (inflected forms of the original query words); these words are treated as separate words with no special relationship to the words from which they were generated.</span></span> <span data-ttu-id="b02b4-207">Les synonymes générés à partir de la fonctionnalité du dictionnaire des synonymes sont traités comme des termes distincts, de même pondération.</span><span class="sxs-lookup"><span data-stu-id="b02b4-207">Synonyms generated from the Thesaurus feature are treated as separate, equally weighted terms.</span></span> <span data-ttu-id="b02b4-208">Chaque mot de la requête contribue au rang.</span><span class="sxs-lookup"><span data-stu-id="b02b4-208">Each word in the query contributes to the rank.</span></span>  
  
```  
Rank = ??[Terms in Query] w ( ( ( k1 + 1 ) tf ) / ( K + tf ) ) * ( ( k3 + 1 ) qtf / ( k3 + qtf ) ) )  
Where:   
w is the Robertson-Sparck Jones weight.   
In simplified form, w is defined as:   
w = log10 ( ( ( r + 0.5 ) * ( N - R + r + 0.5 ) ) / ( ( R - r + 0.5 ) * ( n - r + 0.5 ) )  
N is the number of indexed rows for the property being queried.   
n is the number of rows containing the word.   
K is ( k1 * ( ( 1 - b ) + ( b * dl / avdl ) ) ).   
dl is the property length, in word occurrences.   
avdl is the average length of the property being queried, in word occurrences.   
k1, b, and k3 are the constants 1.2, 0.75, and 8.0, respectively.   
tf is the frequency of the word in the queried property in a specific row.   
qtf is the frequency of the term in the query.   
```  
  
  
## <a name="see-also"></a><span data-ttu-id="b02b4-209">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b02b4-209">See Also</span></span>  
 [<span data-ttu-id="b02b4-210">Exécuter une requête avec une recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="b02b4-210">Query with Full-Text Search</span></span>](query-with-full-text-search.md)  
  
  
