---
title: Spécifier plusieurs conditions de recherche pour une colonne (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 2c006e36-56b1-4992-89b4-c6c0b19808f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a07322120bd3b3f543e6f54fa50cdf75aa32be59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604803"
---
# <a name="specify-multiple-search-conditions-for-one-column-visual-database-tools"></a><span data-ttu-id="9dd19-102">Spécifier plusieurs conditions de recherche pour une colonne (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9dd19-102">Specify Multiple Search Conditions for One Column (Visual Database Tools)</span></span>
  <span data-ttu-id="9dd19-103">Dans certains cas, vous pouvez souhaiter appliquer plusieurs conditions de recherche à une même colonne de données.</span><span class="sxs-lookup"><span data-stu-id="9dd19-103">In some instances, you might want to apply a number of search conditions to the same data column.</span></span> <span data-ttu-id="9dd19-104">Vous pouvez, par exemple, souhaiter effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9dd19-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="9dd19-105">Rechercher plusieurs noms différents dans une table `employee` ou des employés compris dans différentes fourchettes salariales.</span><span class="sxs-lookup"><span data-stu-id="9dd19-105">Search for several different names in an `employee` table or for employees who are in different salary ranges.</span></span> <span data-ttu-id="9dd19-106">Ce type de recherche nécessite une condition OR.</span><span class="sxs-lookup"><span data-stu-id="9dd19-106">This type of search requires an OR condition.</span></span>  
  
-   <span data-ttu-id="9dd19-107">Rechercher un titre de livre commençant par le mot « La » et comportant le mot « Cuisine ».</span><span class="sxs-lookup"><span data-stu-id="9dd19-107">Search for a book title that both starts with the word "The" and contains the word "Cook."</span></span> <span data-ttu-id="9dd19-108">Ce type de recherche nécessite une condition AND.</span><span class="sxs-lookup"><span data-stu-id="9dd19-108">This type of search requires an AND condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9dd19-109">Les informations figurant dans cette rubrique s'appliquent aux conditions de recherche des clauses WHERE et HAVING d'une requête.</span><span class="sxs-lookup"><span data-stu-id="9dd19-109">The information in this topic applies to search conditions in both the WHERE and HAVING clauses of a query.</span></span> <span data-ttu-id="9dd19-110">Les exemples sont concentrés sur la création de clauses WHERE, mais les principes s'appliquent aux deux types de conditions de recherche.</span><span class="sxs-lookup"><span data-stu-id="9dd19-110">The examples focus on creating WHERE clauses, but the principles apply to both types of search conditions.</span></span>  
  
 <span data-ttu-id="9dd19-111">Pour rechercher d'autres valeurs dans une même colonne de données, spécifiez une condition OR.</span><span class="sxs-lookup"><span data-stu-id="9dd19-111">To search for alternative values in the same data column, you specify an OR condition.</span></span> <span data-ttu-id="9dd19-112">Pour rechercher des valeurs répondant à plusieurs conditions, spécifiez une condition AND.</span><span class="sxs-lookup"><span data-stu-id="9dd19-112">To search for values that meet several conditions, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="9dd19-113">Spécification d'une condition OR</span><span class="sxs-lookup"><span data-stu-id="9dd19-113">Specifying an OR Condition</span></span>  
 <span data-ttu-id="9dd19-114">Une condition OR vous permet de spécifier plusieurs autres valeurs à rechercher dans une colonne.</span><span class="sxs-lookup"><span data-stu-id="9dd19-114">Using an OR condition enables you to specify several alternative values to search for in a column.</span></span> <span data-ttu-id="9dd19-115">Cette option élargit la portée de la recherche et peut par conséquent retourner plus de lignes que lors de la recherche d'une seule valeur.</span><span class="sxs-lookup"><span data-stu-id="9dd19-115">This option expands the scope of the search and can return more rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="9dd19-116">Vous pouvez souvent utiliser l'opérateur IN à la place de l'opérateur OR pour rechercher plusieurs valeurs dans une même colonne de données.</span><span class="sxs-lookup"><span data-stu-id="9dd19-116">You can often use the IN operator instead to search for multiple values in the same data column.</span></span>  
  
#### <a name="to-specify-an-or-condition"></a><span data-ttu-id="9dd19-117">Pour spécifier une condition OR</span><span class="sxs-lookup"><span data-stu-id="9dd19-117">To specify an OR condition</span></span>  
  
1.  <span data-ttu-id="9dd19-118">Dans le volet [Critères](visual-database-tools.md), ajoutez la colonne dans laquelle vous souhaitez effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="9dd19-118">In the [Criteria Pane](visual-database-tools.md), add the column to search.</span></span>  
  
2.  <span data-ttu-id="9dd19-119">Dans la colonne **Filtre** de la colonne de données que vous venez d’ajouter, spécifiez la première condition.</span><span class="sxs-lookup"><span data-stu-id="9dd19-119">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="9dd19-120">Dans la colonne **Ou...** de cette même colonne de données, spécifiez la deuxième condition.</span><span class="sxs-lookup"><span data-stu-id="9dd19-120">In the **Or...** column for the same data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="9dd19-121">Le Concepteur de requêtes et de vues crée une clause WHERE comportant une condition OR de ce type :</span><span class="sxs-lookup"><span data-stu-id="9dd19-121">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
```  
SELECT fname, lname  
FROM employees  
WHERE (salary < 30000) OR (salary > 100000)  
```  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="9dd19-122">Spécification d'une condition AND</span><span class="sxs-lookup"><span data-stu-id="9dd19-122">Specifying an AND Condition</span></span>  
 <span data-ttu-id="9dd19-123">Grâce à une condition AND, vous pouvez spécifier que les valeurs d'une colonne doivent répondre à deux conditions (voire plus) concernant la ligne à inclure au jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="9dd19-123">Using an AND condition enables you to specify that values in a column must meet two (or more) conditions for the row to be included in the result set.</span></span> <span data-ttu-id="9dd19-124">Cette option restreint la portée de la recherche et retourne généralement moins de lignes que lors de la recherche d'une seule valeur.</span><span class="sxs-lookup"><span data-stu-id="9dd19-124">This option narrows the scope of the search and usually returns fewer rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="9dd19-125">Si vous formulez une requête sur une plage de valeurs, vous pouvez utiliser l'opérateur BETWEEN plutôt que de relier deux conditions à l'aide de l'opérateur AND.</span><span class="sxs-lookup"><span data-stu-id="9dd19-125">If you are searching for a range of values, you can use the BETWEEN operator instead of linking two conditions with AND.</span></span>  
  
#### <a name="to-specify-an-and-condition"></a><span data-ttu-id="9dd19-126">Pour spécifier une condition AND</span><span class="sxs-lookup"><span data-stu-id="9dd19-126">To specify an AND condition</span></span>  
  
1.  <span data-ttu-id="9dd19-127">Dans le volet Critères, ajoutez la colonne dans laquelle vous souhaitez effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="9dd19-127">In the Criteria pane, add the column to search.</span></span>  
  
2.  <span data-ttu-id="9dd19-128">Dans la colonne **Filtre** de la colonne de données que vous venez d’ajouter, spécifiez la première condition.</span><span class="sxs-lookup"><span data-stu-id="9dd19-128">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="9dd19-129">Ajoutez de nouveau cette même colonne de données au volet Critères, en la plaçant sur une ligne vide de la grille.</span><span class="sxs-lookup"><span data-stu-id="9dd19-129">Add the same data column to the Criteria pane again, placing it in an empty row of the grid.</span></span>  
  
4.  <span data-ttu-id="9dd19-130">Dans la colonne **Filtre** de la deuxième instance de la colonne de données, spécifiez la deuxième condition.</span><span class="sxs-lookup"><span data-stu-id="9dd19-130">In the **Filter** column for the second instance of the data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="9dd19-131">Le Concepteur de requêtes crée une clause WHERE comportant une condition AND de ce type :</span><span class="sxs-lookup"><span data-stu-id="9dd19-131">The Query Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
```  
SELECT title_id, title  
FROM titles  
WHERE (title LIKE '%Cook%') AND   
  (title LIKE '%Recipe%')  
```  
  
## <a name="see-also"></a><span data-ttu-id="9dd19-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9dd19-132">See Also</span></span>  
 <span data-ttu-id="9dd19-133">[Conventions pour la combinaison de conditions de recherche dans le volet critères &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9dd19-133">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="9dd19-134">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9dd19-134">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
