---
title: Inclure ou exclure des lignes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- included rows
- search conditions [SQL Server], HAVING clause
- search criteria [SQL Server], including rows
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- search conditions [SQL Server], WHERE clause
- row included in search [SQL Server]
- excluding rows
ms.assetid: ba4e1202-31a2-444d-8365-c68a530ef223
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7b2d31c51296fa73a503e59a14adb60d79a61178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610920"
---
# <a name="include-or-exclude-rows-visual-database-tools"></a><span data-ttu-id="3fcfa-102">Inclure ou exclure des lignes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3fcfa-102">Include or Exclude Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="3fcfa-103">Pour limiter le nombre de lignes qu'une requête SELECT doit renvoyer, créez des conditions de recherche ou des critères de filtre.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-103">To restrict the number of rows a SELECT query should return, you create search conditions or filter criteria.</span></span> <span data-ttu-id="3fcfa-104">Dans SQL, les conditions de recherche apparaissent dans la clause WHERE de l'instruction ou, si vous créez une requête d'agrégation, dans la clause HAVING.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-104">In SQL, search conditions appear in the WHERE clause of the statement, or if you are creating an aggregate query, in the HAVING clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fcfa-105">Les conditions de recherche permettent également d'indiquer quelles lignes sont affectées par une requête appartenant à un des types suivants : Update, Insert Results, Insert Values, Delete ou Make Table.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-105">You can also use search conditions to indicate which rows are affected by an Update, Insert Results, Insert Values, Delete, or Make Table query.</span></span>  
  
 <span data-ttu-id="3fcfa-106">Lors de l'exécution de la requête, [!INCLUDE[ssDE](../../includes/ssde-md.md)] examine et applique la condition de recherche à chacune des tables dans lesquelles vous demandez une recherche.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-106">When the query runs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] examines and applies the search condition to each row in the tables you are searching.</span></span> <span data-ttu-id="3fcfa-107">Si la ligne remplit la condition, elle est incluse dans la requête.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-107">If the row meets the condition, it is included in the query.</span></span> <span data-ttu-id="3fcfa-108">Voici un exemple d'une condition de recherche de tous les employés d'une région particulière :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-108">For example, a search condition that would find all the employees in a particular region might be:</span></span>  
  
```  
region = 'UK'  
```  
  
 <span data-ttu-id="3fcfa-109">Pour établir les critères d'inclusion d'une ligne dans un résultat, vous pouvez utiliser plusieurs conditions de recherche.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-109">To establish the criteria for including a row in a result, you can use multiple search conditions.</span></span> <span data-ttu-id="3fcfa-110">Par exemple, le critère de recherche suivant se compose de deux conditions de recherche.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-110">For example, the following search criterion consists of two search conditions.</span></span> <span data-ttu-id="3fcfa-111">La requête n'inclut une ligne dans l'ensemble des résultats que si elle remplit les deux conditions.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-111">The query includes a row in the result set only if that row satisfies both of the conditions.</span></span>  
  
```  
region = 'UK' AND product_line = 'Housewares'  
```  
  
 <span data-ttu-id="3fcfa-112">Vous pouvez combiner ces conditions par AND ou OR.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-112">You can combine these conditions with AND or OR.</span></span> <span data-ttu-id="3fcfa-113">L'exemple ci-dessus utilise AND.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-113">The previous example uses AND.</span></span> <span data-ttu-id="3fcfa-114">Le critère suivant utilise OR.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-114">In contrast, the following criterion uses OR.</span></span> <span data-ttu-id="3fcfa-115">Le jeu de résultats inclut toutes les lignes remplissant l'une des conditions de recherche, ou les deux :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-115">The result set will include any row that satisfies either or both of the search conditions:</span></span>  
  
```  
region = 'UK' OR product_line = 'Housewares'  
```  
  
 <span data-ttu-id="3fcfa-116">Vous pouvez même combiner plusieurs conditions de recherche dans une seule et même colonne.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-116">You can even combine search conditions on a single column.</span></span> <span data-ttu-id="3fcfa-117">Par exemple, le critère suivant combine deux conditions dans la colonne region :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-117">For example, the following criterion combines two conditions on the region column:</span></span>  
  
```  
region = 'UK' OR region = 'US'  
```  
  
 <span data-ttu-id="3fcfa-118">Pour plus de détails sur la combinaison de conditions de recherche, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-118">For details about combining search conditions, see the following topics:</span></span>  
  
-   [<span data-ttu-id="3fcfa-119">Conventions pour la combinaison de conditions de recherche dans le volet Critères &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3fcfa-119">Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;</span></span>](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
  
-   [<span data-ttu-id="3fcfa-120">Spécifier plusieurs conditions de recherche pour une colonne &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3fcfa-120">Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
-   [<span data-ttu-id="3fcfa-121">Spécifier plusieurs conditions de recherche pour plusieurs colonnes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3fcfa-121">Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;</span></span>](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md)  
  
-   [<span data-ttu-id="3fcfa-122">Associer des conditions avec priorité à l'opérateur AND &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3fcfa-122">Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-and-has-precedence-visual-database-tools.md)  
  
-   [<span data-ttu-id="3fcfa-123">Associer des conditions avec priorité à l'opérateur OR &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3fcfa-123">Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-or-has-precedence-visual-database-tools.md)  
  
## <a name="examples"></a><span data-ttu-id="3fcfa-124">Exemples</span><span class="sxs-lookup"><span data-stu-id="3fcfa-124">Examples</span></span>  
 <span data-ttu-id="3fcfa-125">Voici quelques exemples des requêtes utilisant plusieurs opérateurs et critères de lignes :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-125">Here are some examples of queries using various operators and row criteria:</span></span>  
  
-   <span data-ttu-id="3fcfa-126">**Littéral** Valeur logique, date, numérique ou de type texte.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-126">**Literal** A single text, numeric, date, or logical value.</span></span> <span data-ttu-id="3fcfa-127">Dans l'exemple suivant, un littéral recherche toutes les lignes contenant des employés de la société travaillant au Royaume-Uni :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-127">The following example uses a literal to find all rows for employees in the United Kingdom:</span></span>  
  
    ```  
    WHERE region = 'UK'  
    ```  
  
-   <span data-ttu-id="3fcfa-128">**Référence de colonne** Compare les valeurs contenues dans une colonne avec celles contenues dans une autre.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-128">**Column reference** Compares the values in one column with the values in another.</span></span> <span data-ttu-id="3fcfa-129">L'exemple suivant recherche dans une table `products` toutes les lignes dont le coût de production est inférieur au coût d'expédition :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-129">The following example searches a `products` table for all rows in which the value of the production cost is lower than the shipping cost:</span></span>  
  
    ```  
    WHERE prod_cost < ship_cost  
    ```  
  
-   <span data-ttu-id="3fcfa-130">**Fonction** Référence à une fonction que la base de données principale peut résoudre pour calculer une valeur à rechercher.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-130">**Function** A reference to a function that the database back-end can resolve to calculate a value for the search.</span></span> <span data-ttu-id="3fcfa-131">La fonction peut être définie par le serveur de base de données ou par l'utilisateur et renvoyer une valeur scalaire.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-131">The function can be a function defined by the database server or a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="3fcfa-132">L'exemple suivant recherche les commandes passées aujourd'hui (la fonction GETDATE( ) retourne la date du jour) :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-132">The following example searches for orders placed today (the GETDATE( ) function returns the current date):</span></span>  
  
    ```  
    WHERE order_date = GETDATE()  
    ```  
  
-   <span data-ttu-id="3fcfa-133">**NULL** L'exemple suivant recherche dans une table `authors` tous les auteurs dont le prénom a été renseigné :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-133">**NULL** The following example searches an `authors` table for all authors who have a first name on file:</span></span>  
  
    ```  
    WHERE au_fname IS NOT NULL  
    ```  
  
-   <span data-ttu-id="3fcfa-134">**Calcul** Résultat d'un calcul impliquant des littéraux, des références de colonnes ou d'autres expressions.</span><span class="sxs-lookup"><span data-stu-id="3fcfa-134">**Calculation** The result of a calculation that can involve literals, column references, or other expressions.</span></span> <span data-ttu-id="3fcfa-135">L'exemple suivant recherche dans une table `products` toutes les lignes dont le prix de vente au détail dépasse le double du coût de production :</span><span class="sxs-lookup"><span data-stu-id="3fcfa-135">The following example searches a `products` table to find all rows in which the retail sales price is more than twice the production cost:</span></span>  
  
    ```  
    WHERE sales_price > (prod_cost * 2)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3fcfa-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3fcfa-136">See Also</span></span>  
 <span data-ttu-id="3fcfa-137">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3fcfa-137">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="3fcfa-138">[Spécifier les critères de recherche &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3fcfa-138">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3fcfa-139">Requête avec des paramètres &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3fcfa-139">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
