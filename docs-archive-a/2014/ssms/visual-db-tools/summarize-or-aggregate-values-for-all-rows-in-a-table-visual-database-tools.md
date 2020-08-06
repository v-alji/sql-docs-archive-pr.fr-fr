---
title: Synthétiser ou agréger des valeurs pour toutes les lignes d’une table (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- aggregate functions [SQL Server], summarizing query results
ms.assetid: f5af876e-f937-4110-ba09-07999c35a699
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5c4d80c8ab2b811b8e796f0a37b2180a2866c332
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704627"
---
# <a name="summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="fc3d9-102">Synthétiser ou regrouper des valeurs de toutes les lignes d'une table (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fc3d9-102">Summarize or Aggregate Values for All Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="fc3d9-103">À l'aide d'une fonction d'agrégation, vous pouvez créer une synthèse pour toutes les valeurs d'une table.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-103">Using an aggregate function, you can create a summary for all the values in a table.</span></span> <span data-ttu-id="fc3d9-104">Ainsi, vous pouvez, comme dans l'exemple illustré ci-dessous, créer une requête qui affiche le prix total de tous les livres de la table `titles` :</span><span class="sxs-lookup"><span data-stu-id="fc3d9-104">For example, you can create a query such as the following to display the total price for all books in the `titles` table:</span></span>  
  
```  
SELECT SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="fc3d9-105">Vous pouvez créer plusieurs agrégations dans la même requête en utilisant des fonctions d'agrégation avec plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-105">You can create multiple aggregations in the same query by using aggregate functions with more than one column.</span></span> <span data-ttu-id="fc3d9-106">Il est par exemple possible de créer une requête qui calcule le total de la colonne `price` et la moyenne de la colonne `discount` .</span><span class="sxs-lookup"><span data-stu-id="fc3d9-106">For example, you can create a query that calculates the total of the `price` column and the average of the `discount` column.</span></span>  
  
 <span data-ttu-id="fc3d9-107">Vous pouvez par ailleurs agréger la même colonne de différentes façons (total, comptage et moyenne) dans la même requête.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-107">You can also aggregate the same column in different ways (such as totaling, counting, and averaging) in the same query.</span></span> <span data-ttu-id="fc3d9-108">Ainsi, la requête ci-dessous établit la moyenne et totalise la colonne `price` de la table `titles` :</span><span class="sxs-lookup"><span data-stu-id="fc3d9-108">For example, the following query averages and summarizes the `price` column from the `titles` table:</span></span>  
  
```  
SELECT AVG(price), SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="fc3d9-109">Si vous ajoutez une condition de recherche, vous pouvez agréger le sous-ensemble de lignes qui répond à cette condition.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-109">If you add a search condition, you can aggregate the subset of rows that meet that condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc3d9-110">Vous pouvez aussi compter toutes les lignes de la table ou celles qui répondent à une condition spécifique.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-110">You can also count all the rows in the table or the ones that meet a specific condition.</span></span> <span data-ttu-id="fc3d9-111">Pour plus d’informations, consultez [Compter les lignes d’une table &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc3d9-111">For details, see [Count Rows in a Table &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="fc3d9-112">Lorsque vous créez une seule valeur d'agrégation pour toutes les lignes d'une table, seules les valeurs agrégées s'affichent.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-112">When you create a single aggregation value for all rows in a table, you display only the aggregate values themselves.</span></span> <span data-ttu-id="fc3d9-113">Par exemple, si vous totalisez la valeur de la colonne `price` de la table `titles` , les titres individuels, les noms des éditeurs, etc. ne sont pas affichés.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-113">For example, if you are totaling the value of the `price` column of the `titles` table, you would not also display individual titles, publisher names, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc3d9-114">Si vous calculez des sous-totaux, en d’autres termes si vous créez des groupes, vous pouvez afficher des valeurs de colonne pour chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-114">If you are subtotaling - that is, creating groups - you can display column values for each group.</span></span> <span data-ttu-id="fc3d9-115">Pour plus d’informations, consultez [Regrouper des lignes dans les résultats de requête &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc3d9-115">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
### <a name="to-aggregate-values-for-all-rows"></a><span data-ttu-id="fc3d9-116">Pour agréger les valeurs de toutes les lignes</span><span class="sxs-lookup"><span data-stu-id="fc3d9-116">To aggregate values for all rows</span></span>  
  
1.  <span data-ttu-id="fc3d9-117">Assurez-vous que la table à agréger figure déjà dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-117">Be sure the table you want to aggregate is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="fc3d9-118">Cliquez avec le bouton droit sur un point de l’arrière-plan du volet Schéma, puis choisissez **Grouper par** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-118">Right-click the background of the Diagram pane, then choose **Group By** from the shortcut menu.</span></span> <span data-ttu-id="fc3d9-119">Le [Concepteur de requêtes et de vues](query-and-view-designer-tools-visual-database-tools.md) ajoute une colonne **Group by** à la grille dans le volet critères.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-119">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="fc3d9-120">Ajoutez la colonne à agréger dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-120">Add the column you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="fc3d9-121">Assurez-vous que la colonne est marquée pour la sortie.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-121">Be sure that the column is marked for output.</span></span>  
  
     <span data-ttu-id="fc3d9-122">Le Concepteur de requêtes et de vues assigne automatiquement un alias de colonne à la colonne que vous agrégez.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-122">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="fc3d9-123">Il est possible de remplacer cet alias par un autre plus significatif.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-123">You can replace this alias with a more meaningful one.</span></span> <span data-ttu-id="fc3d9-124">Pour plus d’informations, consultez [Créer des alias de colonnes &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc3d9-124">For details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="fc3d9-125">Dans la colonne de la grille **Group By**, sélectionnez la fonction d’agrégation adéquate, par exemple : **Sum**, **Avg**, **Min**, **Max**, **Count**.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-125">In the **Group By** grid column, select the appropriate aggregate function, such as: **Sum**, **Avg**, **Min**, **Max**, **Count**.</span></span> <span data-ttu-id="fc3d9-126">Pour n’agréger que des lignes uniques dans le jeu de résultats, choisissez une fonction d’agrégation avec l’option DISTINCT, telle que **Min Distinct**.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-126">If you want to aggregate only unique rows in the result set, choose an aggregate function with the DISTINCT options, such as **Min Distinct**.</span></span> <span data-ttu-id="fc3d9-127">Évitez des options comme **Group By**, **Expression**ou **Where**, car ces options ne s’appliquent pas quand vous agrégez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-127">Do not choose **Group By**, **Expression**, or **Where**, because those options do not apply when you are aggregating all rows.</span></span>  
  
     <span data-ttu-id="fc3d9-128">Le Concepteur de requêtes et de vues remplace le nom de colonne dans l’instruction figurant dans le [volet SQL](sql-pane-visual-database-tools.md) par le nom de la fonction d’agrégation que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-128">The Query and View Designer replaces the column name in the statement in the [SQL pane](sql-pane-visual-database-tools.md) with the aggregate function that you specify.</span></span> <span data-ttu-id="fc3d9-129">Par exemple, l'instruction SQL peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="fc3d9-129">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT SUM(price)  
    FROM titles  
    ```  
  
5.  <span data-ttu-id="fc3d9-130">Si vous souhaitez créer plusieurs agrégations dans la requête, répétez les étapes 3 et 4.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-130">If you want to create more than one aggregation in the query, repeat steps 3 and 4.</span></span>  
  
     <span data-ttu-id="fc3d9-131">Quand vous ajoutez une autre colonne à la liste de résultats de la requête ou à la liste Order by, le Concepteur de requêtes et de vues ajoute automatiquement le terme **Group By** dans la colonne **Group By** de la grille.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-131">When you add another column to the query output list or order by list, the Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span> <span data-ttu-id="fc3d9-132">Sélectionnez la fonction d'agrégation appropriée.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-132">Select the appropriate aggregate function.</span></span>  
  
6.  <span data-ttu-id="fc3d9-133">Ajoutez des conditions de recherche, le cas échéant, afin de spécifier les sous-ensembles de lignes que vous voulez synthétiser.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-133">Add search conditions, if any, to specify the subset of rows you want to summarize.</span></span>  
  
 <span data-ttu-id="fc3d9-134">Quand vous exécutez la requête, le volet Résultats affiche les agrégations que vous avez définies.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-134">When you execute the query, the Results pane displays the aggregations that you specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc3d9-135">Le Concepteur de requêtes et de vues conserve les fonctions d'agrégation dans l'instruction SQL du volet SQL jusqu'à ce que vous désactiviez explicitement le mode Grouper par.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-135">The Query and View Designer maintains aggregate functions as part of the SQL statement in the SQL pane until you explicitly turn off Group By mode.</span></span> <span data-ttu-id="fc3d9-136">Par conséquent, si vous modifiez votre requête en changeant son type, les tables ou autres objets table présents dans le volet Schéma, la requête obtenue peut comporter des fonctions d'agrégation non valides.</span><span class="sxs-lookup"><span data-stu-id="fc3d9-136">Therefore, if you modify your query by changing its type or by changing which tables or table-valued objects are present in the Diagram pane, the resulting query might include invalid aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3d9-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc3d9-137">See Also</span></span>  
 <span data-ttu-id="fc3d9-138">[Trier et regrouper les résultats des requêtes &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fc3d9-138">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="fc3d9-139">Résumer les résultats de la requête &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fc3d9-139">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
