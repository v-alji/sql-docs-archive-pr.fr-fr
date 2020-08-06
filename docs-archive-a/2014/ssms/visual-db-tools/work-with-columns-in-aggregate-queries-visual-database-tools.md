---
title: Utiliser des colonnes dans des requêtes d’agrégation (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query summary results
- GROUP BY clause, query summary results
- aggregate queries [SQL Server]
- WHERE clause, query summary results
ms.assetid: 1b82681f-3d4f-4b9a-bb1d-2060e44f2577
author: stevestein
ms.author: sstein
ms.openlocfilehash: 880f7529cebd7f51951e62952e3b5f13190f99b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695075"
---
# <a name="work-with-columns-in-aggregate-queries-visual-database-tools"></a><span data-ttu-id="7c51a-102">Utiliser des colonnes dans des requêtes d'agrégation (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7c51a-102">Work with Columns in Aggregate Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="7c51a-103">Quand vous créez des requêtes d’agrégation, le [Concepteur de requêtes et de vues](visual-database-tools.md) fait certaines suppositions afin de construire une requête valide.</span><span class="sxs-lookup"><span data-stu-id="7c51a-103">When you create aggregate queries the [Query and View Designer](visual-database-tools.md) makes certain assumptions so that it can construct a valid query.</span></span> <span data-ttu-id="7c51a-104">Par exemple, si vous créez une requête d'agrégation puis placez un marqueur de sortie sur une colonne de données, cette dernière est automatiquement intégrée à la clause GROUP BY par le Concepteur de requêtes et de vues pour éviter l'affichage accidentel du contenu d'une ligne individuelle dans une synthèse.</span><span class="sxs-lookup"><span data-stu-id="7c51a-104">For example, if you are creating an aggregate query and mark a data column for output, the Query and View Designer automatically makes the column part of the GROUP BY clause so that you do not inadvertently attempt to display the contents of an individual row in a summary.</span></span>  
  
## <a name="using-group-by"></a><span data-ttu-id="7c51a-105">Utilisation de Regrouper par</span><span class="sxs-lookup"><span data-stu-id="7c51a-105">Using Group By</span></span>  
 <span data-ttu-id="7c51a-106">Le Concepteur de requêtes et de vues suit les instructions ci-dessous lorsque vous utilisez des colonnes :</span><span class="sxs-lookup"><span data-stu-id="7c51a-106">The Query and View Designer uses the following guidelines for working with columns:</span></span>  
  
-   <span data-ttu-id="7c51a-107">Si vous choisissez l'option Regrouper par ou lorsque vous ajoutez une fonction d'agrégation à une requête, toutes les colonnes ayant reçu un marqueur de sortie ou utilisées dans des tris s'ajoutent automatiquement à la clause GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="7c51a-107">When you choose the Group By option or add an aggregate function to a query, all columns marked for output or used for sorting are automatically added to the GROUP BY clause.</span></span> <span data-ttu-id="7c51a-108">Les colonnes ne s'ajoutent pas automatiquement à la clause GROUP BY si elles font déjà partie d'une fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="7c51a-108">Columns are not automatically added to the GROUP BY clause if they are already part of an aggregate function.</span></span>  
  
     <span data-ttu-id="7c51a-109">Si vous ne souhaitez pas qu'une colonne particulière fasse partie de la clause GROUP BY, sélectionnez manuellement une autre option dans la colonne Regrouper par du volet Critères.</span><span class="sxs-lookup"><span data-stu-id="7c51a-109">If you do not want a particular column to be part of the GROUP BY clause, you must manually change it by selecting a different option in the Group By column of the Criteria pane.</span></span> <span data-ttu-id="7c51a-110">Cependant, le Concepteur de requêtes et de vues ne vous interdit pas de choisir une option qui risque d'empêcher l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="7c51a-110">However, the Query and View Designer will not prevent you from choosing an option that can result in a query that will not run.</span></span>  
  
-   <span data-ttu-id="7c51a-111">Si vous ajoutez manuellement à une fonction d'agrégation une colonne de sortie de la requête, que ce soit dans le volet Critères ou le volet SQL, le Concepteur de requêtes et de vues ne supprime pas automatiquement les autres colonnes de sortie de la requête.</span><span class="sxs-lookup"><span data-stu-id="7c51a-111">If you manually add a query output column to an aggregate function in either the Criteria or SQL pane, the Query and View Designer does not automatically remove other output columns from the query.</span></span> <span data-ttu-id="7c51a-112">Par conséquent, vous devez supprimer du résultat de la requête les colonnes restantes ou les intégrer à la clause GROUP BY ou à une fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="7c51a-112">Therefore, you must remove the remaining columns from the query output or make them part of the GROUP BY clause or of an aggregate function.</span></span>  
  
 <span data-ttu-id="7c51a-113">Lorsque vous entrez une condition de recherche dans la colonne Filtre du volet Critères, le Concepteur de requêtes et de vues respecte les règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="7c51a-113">When you enter a search condition into the Filter column of the Criteria pane, the Query and View Designer follows these rules:</span></span>  
  
-   <span data-ttu-id="7c51a-114">Si la colonne **Regrouper par** de la grille ne s’affiche pas (car vous n’avez pas encore spécifié de requête d’agrégation), la condition de recherche se place dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="7c51a-114">If the **Group By** column of the grid is not displayed (because you have not yet specified an aggregate query), the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="7c51a-115">Si vous vous trouvez déjà dans une requête d’agrégation et avez sélectionné, dans la colonne **Regrouper par** , l’option **Où** , la condition de recherche se place dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="7c51a-115">If you are already in an aggregate query and have selected the option **Where** in the **Group By** column, the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="7c51a-116">Si la colonne **Regrouper par** contient une autre valeur que la valeur **Où**, la condition de recherche se place dans la clause HAVING.</span><span class="sxs-lookup"><span data-stu-id="7c51a-116">If the **Group By** column contains any value other than **Where**, the search condition is placed in the HAVING clause.</span></span>  
  
## <a name="using-the-having-and-where-clauses"></a><span data-ttu-id="7c51a-117">Utilisation des clauses HAVING et WHERE</span><span class="sxs-lookup"><span data-stu-id="7c51a-117">Using the HAVING and WHERE Clauses</span></span>  
 <span data-ttu-id="7c51a-118">Les principes suivants décrivent comment, dans une requête d'agrégation, référencer des colonnes dans des conditions de recherche :</span><span class="sxs-lookup"><span data-stu-id="7c51a-118">The following principles describe how you can reference columns in an aggregate query in search conditions.</span></span> <span data-ttu-id="7c51a-119">en général, dans une condition de recherche, une colonne sert à filtrer les lignes dont vous souhaitez faire la synthèse (clause WHERE) ou à déterminer quels résultats groupés apparaîtront dans la sortie finale (clause HAVING).</span><span class="sxs-lookup"><span data-stu-id="7c51a-119">In general, you can use a column in a search condition to filter the rows that should be summarized (a WHERE clause) or to determine which grouped results appear in the final output (a HAVING clause).</span></span>  
  
-   <span data-ttu-id="7c51a-120">Des colonnes de données individuelles peuvent apparaître dans la clause WHERE ou HAVING, selon la façon dont elles sont utilisées ailleurs dans la requête.</span><span class="sxs-lookup"><span data-stu-id="7c51a-120">Individual data columns can appear in either the WHERE or HAVING clause, depending on how they are used elsewhere in the query.</span></span>  
  
-   <span data-ttu-id="7c51a-121">Comme les clauses WHERE sélectionnent un sous-ensemble de lignes faisant l'objet de la synthèse ou du regroupement, elles s'appliquent avant tout regroupement.</span><span class="sxs-lookup"><span data-stu-id="7c51a-121">WHERE clauses are used to select a subset of rows for summarizing and grouping and are thus applied before any grouping is done.</span></span> <span data-ttu-id="7c51a-122">Par conséquent, vous pouvez utiliser une colonne de données dans une clause WHERE même si elle ne fait pas partie de la clause GROUP BY ou si elle n'est pas incluse dans une fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="7c51a-122">Therefore, you can use a data column in a WHERE clause even if it is not part of the GROUP BY clause or contained in an aggregate function.</span></span> <span data-ttu-id="7c51a-123">Par exemple, l'instruction suivante sélectionne tous les titres dépassant 10 dollars et donne le prix moyen :</span><span class="sxs-lookup"><span data-stu-id="7c51a-123">For example, the following statement selects all titles that cost more than $10.00 and averages the price:</span></span>  
  
    ```  
    SELECT AVG(price)  
    FROM titles  
    WHERE price > 10  
    ```  
  
-   <span data-ttu-id="7c51a-124">Selon ce que vous décidez lorsque vous créez une condition de recherche impliquant une colonne également utilisée dans une clause GROUP BY ou dans une fonction d’agrégation, cette condition peut apparaître soit sous la forme d’une clause WHERE, soit sous la forme d’une clause HAVING.</span><span class="sxs-lookup"><span data-stu-id="7c51a-124">If you create a search condition that involves a column also used in a GROUP BY clause or aggregate function, the search condition can appear as either a WHERE clause or a HAVING clause - you can decide which when you create the condition.</span></span> <span data-ttu-id="7c51a-125">Par exemple, l'instruction suivante calcule le prix moyen des titres par éditeur, puis affiche la moyenne globale des prix pratiqués par les éditeurs dont le prix moyen est supérieur à 10 dollars :</span><span class="sxs-lookup"><span data-stu-id="7c51a-125">For example, the following statement creates an average price for the titles for each publisher, then displays the average for the publishers in which the average price is greater than $10.00:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
    ```  
  
-   <span data-ttu-id="7c51a-126">Si vous utilisez une fonction d'agrégation dans une condition de recherche, cette dernière implique une synthèse. Par conséquent, elle doit faire partie de la clause HAVING.</span><span class="sxs-lookup"><span data-stu-id="7c51a-126">If you use an aggregate function in a search condition, the condition involves a summary and must therefore be part of the HAVING clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c51a-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c51a-127">See Also</span></span>  
 <span data-ttu-id="7c51a-128">[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7c51a-128">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7c51a-129">Trier et regrouper des résultats de requête &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7c51a-129">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
