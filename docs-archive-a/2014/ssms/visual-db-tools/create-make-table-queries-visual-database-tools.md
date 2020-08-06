---
title: Créer des requêtes Make Table (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- table creation [SQL Server], Make Table query
- inserting tables
- Make Table query
- adding tables
ms.assetid: 4493cffa-7b2d-4c24-8ef0-d49329198972
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91c4a3bf45935053789d6e884b1af5b338b4c7c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699114"
---
# <a name="create-make-table-queries-visual-database-tools"></a><span data-ttu-id="26aae-102">Créer des requêtes Make Table (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="26aae-102">Create Make Table Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="26aae-103">Vous pouvez copier des lignes dans une nouvelle table à l'aide d'une requête Make Table, très utile pour créer des sous-ensembles de données que vous pouvez par la suite manipuler ou pour copier le contenu d'une table d'une base de données vers une autre.</span><span class="sxs-lookup"><span data-stu-id="26aae-103">You can copy rows into a new table using a Make Table query, which is useful for creating subsets of data to work with or copying the contents of a table from one database to another.</span></span> <span data-ttu-id="26aae-104">Une requête Make Table ressemble à une requête Insert Results à cette différence près qu'elle crée une nouvelle table vers laquelle copier les lignes.</span><span class="sxs-lookup"><span data-stu-id="26aae-104">A Make Table query is similar to an Insert Results query but creates a new table to copy rows into.</span></span>  
  
 <span data-ttu-id="26aae-105">Lorsque vous créez une requête Make Table, spécifiez :</span><span class="sxs-lookup"><span data-stu-id="26aae-105">When you create a Make Table query, you specify:</span></span>  
  
-   <span data-ttu-id="26aae-106">le nom de la nouvelle table de base de données (table de destination) ;</span><span class="sxs-lookup"><span data-stu-id="26aae-106">The name of the new database table (the destination table).</span></span>  
  
-   <span data-ttu-id="26aae-107">les tables à partir desquelles copier les lignes (les tables sources),</span><span class="sxs-lookup"><span data-stu-id="26aae-107">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="26aae-108">la copie pouvant être réalisée à partir d'une seule table ou de tables jointes ;</span><span class="sxs-lookup"><span data-stu-id="26aae-108">You can copy from a single table or from joined tables.</span></span>  
  
-   <span data-ttu-id="26aae-109">les colonnes de la table source dont vous souhaitez copier le contenu ;</span><span class="sxs-lookup"><span data-stu-id="26aae-109">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="26aae-110">l'ordre de tri, afin de copier, le cas échéant, les lignes dans un ordre précis ;</span><span class="sxs-lookup"><span data-stu-id="26aae-110">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="26aae-111">les conditions de recherche pour définir les lignes à copier ;</span><span class="sxs-lookup"><span data-stu-id="26aae-111">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="26aae-112">les options Group By, si vous ne souhaitez copier que des informations de synthèse.</span><span class="sxs-lookup"><span data-stu-id="26aae-112">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="26aae-113">Dans l'exemple suivant, la requête crée une nouvelle table appelée `uk`_`customers` et copie les informations de la table `customers` vers celle-ci :</span><span class="sxs-lookup"><span data-stu-id="26aae-113">For example, the following query creates a new table called `uk`_`customers` and copies information from the `customers` table to it:</span></span>  
  
```  
SELECT *   
INTO uk_customers  
FROM customers  
WHERE country = 'UK'  
```  
  
 <span data-ttu-id="26aae-114">Il existe deux conditions préalables à l'exécution correcte d'une requête Make Table :</span><span class="sxs-lookup"><span data-stu-id="26aae-114">In order to use a Make Table query successfully:</span></span>  
  
-   <span data-ttu-id="26aae-115">Votre base de données doit prendre en charge la syntaxe SELECT...INTO.</span><span class="sxs-lookup"><span data-stu-id="26aae-115">Your database must support the SELECT...INTO syntax.</span></span>  
  
-   <span data-ttu-id="26aae-116">Vous devez disposer d'une autorisation pour créer une table dans la base de données cible.</span><span class="sxs-lookup"><span data-stu-id="26aae-116">You must have permission to create a table in the target database.</span></span>  
  
### <a name="to-create-a-make-table-query"></a><span data-ttu-id="26aae-117">Pour créer une requête Make Table</span><span class="sxs-lookup"><span data-stu-id="26aae-117">To create a Make Table query</span></span>  
  
1.  <span data-ttu-id="26aae-118">Ajoutez la ou les tables sources dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="26aae-118">Add the source table or tables to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="26aae-119">Dans le menu **Concepteur de requêtes** , pointez sur **Modifier le type**, puis cliquez sur **Créer une table**.</span><span class="sxs-lookup"><span data-stu-id="26aae-119">From the **Query Designer** menu, point to **Change Type**, and then click **Make Table**.</span></span>  
  
3.  <span data-ttu-id="26aae-120">Dans la boîte de dialogue **Création de table** , tapez le nom de la table de destination.</span><span class="sxs-lookup"><span data-stu-id="26aae-120">In the **Make Table** dialog box, type the name of the destination table.</span></span> <span data-ttu-id="26aae-121">Le Concepteur de requêtes et de vues ne vérifie pas si le nom existe déjà ou si vous êtes autorisé à créer la table.</span><span class="sxs-lookup"><span data-stu-id="26aae-121">The Query and View Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
     <span data-ttu-id="26aae-122">Pour créer une table de destination dans une autre base de données, spécifiez un nom de table complet avec le nom de la base de données cible, le propriétaire (si nécessaire) ainsi que le nom de la table.</span><span class="sxs-lookup"><span data-stu-id="26aae-122">To create a destination table in another database, specify a fully qualified table name including the name of the target database, the owner (if required), and the name of the table.</span></span>  
  
4.  <span data-ttu-id="26aae-123">Spécifiez les colonnes à copier en les ajoutant à la requête.</span><span class="sxs-lookup"><span data-stu-id="26aae-123">Specify the columns to copy by adding them to the query.</span></span> <span data-ttu-id="26aae-124">Pour plus d’informations, consultez [Ajouter des colonnes à des requêtes &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="26aae-124">For details, see [Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="26aae-125">Les colonnes ne sont copiées que si vous les ajoutez à la requête.</span><span class="sxs-lookup"><span data-stu-id="26aae-125">Columns will be copied only if you add them to the query.</span></span> <span data-ttu-id="26aae-126">Pour copier des lignes entières, choisissez \*\* \* (toutes les colonnes)\*\*.</span><span class="sxs-lookup"><span data-stu-id="26aae-126">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="26aae-127">Le Concepteur de requêtes et de vues ajoute les colonnes sélectionnées à la colonne **Colonne** du volet Critères.</span><span class="sxs-lookup"><span data-stu-id="26aae-127">The Query and View Designer adds the columns you choose to the **Column** column of the Criteria pane.</span></span>  
  
5.  <span data-ttu-id="26aae-128">Si vous souhaitez copier les lignes dans un ordre précis, spécifiez un ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="26aae-128">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="26aae-129">Pour plus d’informations, consultez **Tri et regroupement des résultats de la requête**.</span><span class="sxs-lookup"><span data-stu-id="26aae-129">For details, see **Sorting and Grouping Query Results**.</span></span>  
  
6.  <span data-ttu-id="26aae-130">Spécifiez les lignes à copier en entrant des conditions de recherche.</span><span class="sxs-lookup"><span data-stu-id="26aae-130">Specify the rows to copy by entering search conditions.</span></span> <span data-ttu-id="26aae-131">Pour plus d’informations, consultez [Spécifier des critères de recherche &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="26aae-131">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="26aae-132">Si vous ne spécifiez pas de condition de recherche, toutes les lignes de la table source seront copiées vers la table de destination.</span><span class="sxs-lookup"><span data-stu-id="26aae-132">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26aae-133">Lorsque vous ajoutez, dans le volet Critères, une colonne à utiliser dans une condition de recherche, le Concepteur de requêtes et de vues l'ajoute également à la liste des colonnes à copier.</span><span class="sxs-lookup"><span data-stu-id="26aae-133">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="26aae-134">Pour utiliser une colonne dans le cadre de la recherche sans toutefois la copier, désactivez la case à cocher en regard du nom de la colonne dans le rectangle représentant la table ou l'objet de type table.</span><span class="sxs-lookup"><span data-stu-id="26aae-134">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-structured object.</span></span>  
  
7.  <span data-ttu-id="26aae-135">Si vous souhaitez copier des informations de synthèse, spécifiez des options Group By.</span><span class="sxs-lookup"><span data-stu-id="26aae-135">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="26aae-136">Pour plus d’informations, consultez [Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="26aae-136">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="26aae-137">Quand vous exécutez une requête Make Table, aucun résultat n’apparaît dans le [volet Résultats](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="26aae-137">When you execute a Make Table query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="26aae-138">En fait, un message indiquant le nombre de lignes copiées s'affiche.</span><span class="sxs-lookup"><span data-stu-id="26aae-138">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26aae-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26aae-139">See Also</span></span>  
 <span data-ttu-id="26aae-140">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="26aae-140">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="26aae-141">Types de requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="26aae-141">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
