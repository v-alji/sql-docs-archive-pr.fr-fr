---
title: Regrouper des lignes dans les résultats de requête (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing table subsets
- grouping rows
- grouping query results
ms.assetid: b07082d5-4d55-4903-9af9-4c470554c6d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52de25c86425d95f5917d89c8a3f4fec8939fb16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610936"
---
# <a name="group-rows-in-query-results-visual-database-tools"></a><span data-ttu-id="8119d-102">Regrouper des lignes dans les résultats de requête (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8119d-102">Group Rows in Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="8119d-103">Pour créer des sous-totaux ou afficher d'autres informations de synthèse pour les sous-ensembles d'une table, créez des groupes à l'aide d'une requête d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="8119d-103">If you want to create subtotals or show other summary information for subsets of a table, you create groups using an aggregate query.</span></span> <span data-ttu-id="8119d-104">Chaque groupe synthétise les données pour toutes les lignes de la table qui ont la même valeur.</span><span class="sxs-lookup"><span data-stu-id="8119d-104">Each group summarizes the data for all the rows in the table that have the same value.</span></span>  
  
 <span data-ttu-id="8119d-105">Imaginons, par exemple, que vous souhaitiez voir le prix moyen d'un livre dans la table `titles` , en détaillant toutefois les résultats par éditeur.</span><span class="sxs-lookup"><span data-stu-id="8119d-105">For example, you might want to see the average price of a book in the `titles` table, but break the results down by publisher.</span></span> <span data-ttu-id="8119d-106">Pour ce faire, groupez la requête par éditeur (par exemple, `pub_id`).</span><span class="sxs-lookup"><span data-stu-id="8119d-106">To do so, you group the query by publisher (for example, `pub_id`).</span></span> <span data-ttu-id="8119d-107">La requête donnera, par exemple, le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="8119d-107">The resulting query output might look like this:</span></span>  
  
 <span data-ttu-id="8119d-108">![Résultats de la requête : prix moyen groupé par éditeur](../../database-engine/media//dv3w9e1.gif "Résultats de la requête : prix moyen groupé par éditeur")</span><span class="sxs-lookup"><span data-stu-id="8119d-108">![Query results: average price grouped by publisher](../../database-engine/media//dv3w9e1.gif "Query results: average price grouped by publisher")</span></span>  
  
 <span data-ttu-id="8119d-109">Lorsque vous groupez des données, vous pouvez uniquement afficher des données groupées ou des données de synthèse, dont notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="8119d-109">When you group data, you can display only summary or grouped data, such as:</span></span>  
  
-   <span data-ttu-id="8119d-110">Valeurs des colonnes groupées (celles qui apparaissent dans la clause GROUP BY).</span><span class="sxs-lookup"><span data-stu-id="8119d-110">The values of the grouped columns (those that appear in the GROUP BY clause).</span></span> <span data-ttu-id="8119d-111">Dans l'exemple ci-dessus, `pub_id` est la colonne groupée.</span><span class="sxs-lookup"><span data-stu-id="8119d-111">In the example above, `pub_id` is the grouped column.</span></span>  
  
-   <span data-ttu-id="8119d-112">Valeurs générées par des fonctions d’agrégation comme une somme SUM( ) et une moyenne AVG( ).</span><span class="sxs-lookup"><span data-stu-id="8119d-112">Values produced by aggregate functions such as SUM( ) and AVG( ).</span></span> <span data-ttu-id="8119d-113">Dans l’exemple ci-dessus, la deuxième colonne est obtenue par l’utilisation de la fonction AVG( ) avec la colonne `price` .</span><span class="sxs-lookup"><span data-stu-id="8119d-113">In the example above, the second column is produced by using the AVG( ) function with the `price` column.</span></span>  
  
 <span data-ttu-id="8119d-114">Il est impossible d'afficher des valeurs issues de lignes individuelles.</span><span class="sxs-lookup"><span data-stu-id="8119d-114">You cannot display values from individual rows.</span></span> <span data-ttu-id="8119d-115">Par exemple, si vous effectuez un regroupement uniquement par éditeur, vous ne pouvez pas afficher en plus les titres individuels dans la requête.</span><span class="sxs-lookup"><span data-stu-id="8119d-115">For example, if you group only by publisher, you cannot also display individual titles in the query.</span></span> <span data-ttu-id="8119d-116">Ainsi, si vous ajoutez des colonnes au résultat de la requête, le [Concepteur de requêtes et de vues](visual-database-tools.md) les ajoute automatiquement à la clause GROUP BY de l’instruction dans le [volet SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8119d-116">Therefore, if you add columns to the query output, the [Query and View Designer](visual-database-tools.md) automatically adds them to the GROUP BY clause of the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="8119d-117">Si en revanche vous souhaitez agréger une colonne, spécifiez une fonction d'agrégation pour cette colonne.</span><span class="sxs-lookup"><span data-stu-id="8119d-117">If you want a column to be aggregated instead, you can specify an aggregate function for that column.</span></span>  
  
 <span data-ttu-id="8119d-118">Si vous groupez par plusieurs colonnes, chaque groupe de la requête affiche les valeurs d'agrégation pour toutes les colonnes de regroupement.</span><span class="sxs-lookup"><span data-stu-id="8119d-118">If you group by more than one column, each group in the query shows the aggregate values for all grouping columns.</span></span>  
  
 <span data-ttu-id="8119d-119">Ainsi, la requête suivante exécutée sur la table `titles` regroupe par éditeur (`pub_id`) et par type de livre (`type`).</span><span class="sxs-lookup"><span data-stu-id="8119d-119">For example, the following query against the `titles` table groups by publisher (`pub_id`) and also by book type (`type`).</span></span> <span data-ttu-id="8119d-120">Les résultats de la requête sont classés par éditeur et affichent des informations de synthèse pour chaque type de livre publié par l'éditeur :</span><span class="sxs-lookup"><span data-stu-id="8119d-120">The query results are ordered by publisher and show summary information for each different type of book that the publisher produces:</span></span>  
  
```  
SELECT pub_id, type, SUM(price) Total_price  
FROM titles  
GROUP BY pub_id, type  
```  
  
 <span data-ttu-id="8119d-121">Le résultat obtenu peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="8119d-121">The resulting output might look like this:</span></span>  
  
 <span data-ttu-id="8119d-122">![Résultats de la requête : prix groupé par éditeur et par type](../../database-engine/media//dv3w9e2.gif "Résultats de la requête : prix groupé par éditeur et par type")</span><span class="sxs-lookup"><span data-stu-id="8119d-122">![Query results: price grouped by publisher and type](../../database-engine/media//dv3w9e2.gif "Query results: price grouped by publisher and type")</span></span>  
  
### <a name="to-group-rows"></a><span data-ttu-id="8119d-123">Pour grouper des lignes</span><span class="sxs-lookup"><span data-stu-id="8119d-123">To group rows</span></span>  
  
1.  <span data-ttu-id="8119d-124">Commencez la requête en ajoutant les tables à synthétiser dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="8119d-124">Start the query by adding the tables you want to summarize to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="8119d-125">Cliquez avec le bouton droit sur un point de l’arrière-plan du volet Schéma, puis choisissez **Ajouter un groupe par** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="8119d-125">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="8119d-126">Le Concepteur de requêtes et de vues ajoute une colonne **Group By** à la grille dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="8119d-126">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="8119d-127">Ajoutez la ou les colonnes à grouper dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="8119d-127">Add the column or columns you want to group to the Criteria pane.</span></span> <span data-ttu-id="8119d-128">Si la colonne doit apparaître dans le résultat de la requête, vérifiez que la colonne **Sortie** est sélectionnée pour la sortie.</span><span class="sxs-lookup"><span data-stu-id="8119d-128">If you want the column to appear in the query output, be sure that the **Output** column is selected for output.</span></span>  
  
     <span data-ttu-id="8119d-129">Le Concepteur de requêtes et de vues ajoute une clause GROUP BY à l'instruction dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="8119d-129">The Query and View Designer adds a GROUP BY clause to the statement in the SQL pane.</span></span> <span data-ttu-id="8119d-130">Par exemple, l'instruction SQL peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="8119d-130">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT pub_id  
    FROM titles  
    GROUP BY pub_id  
    ```  
  
4.  <span data-ttu-id="8119d-131">Ajoutez la ou les colonnes à agréger dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="8119d-131">Add the column or columns you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="8119d-132">Assurez-vous que la colonne est marquée pour la sortie.</span><span class="sxs-lookup"><span data-stu-id="8119d-132">Be sure that the column is marked for output.</span></span>  
  
5.  <span data-ttu-id="8119d-133">Dans la cellule de la grille **Grouper par** de la colonne à agréger, sélectionnez la fonction d’agrégation appropriée.</span><span class="sxs-lookup"><span data-stu-id="8119d-133">In the **Group By** grid cell for the column that is going to be aggregated, select the appropriate aggregate function.</span></span>  
  
     <span data-ttu-id="8119d-134">Le Concepteur de requêtes et de vues assigne automatiquement un alias de colonne à la colonne que vous agrégez.</span><span class="sxs-lookup"><span data-stu-id="8119d-134">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="8119d-135">Il est possible de remplacer l'alias généré automatiquement par un autre, plus significatif.</span><span class="sxs-lookup"><span data-stu-id="8119d-135">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="8119d-136">Pour plus d’informations, consultez [Créer des alias de colonnes &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8119d-136">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="8119d-137">![Ajout d'un alias de colonne au jeu de résultats de la requête](../../database-engine/media//dv3w9e3.gif "Ajout d'un alias de colonne au jeu de résultats de la requête")</span><span class="sxs-lookup"><span data-stu-id="8119d-137">![Adding a column alias to the query result set](../../database-engine/media//dv3w9e3.gif "Adding a column alias to the query result set")</span></span>  
  
     <span data-ttu-id="8119d-138">L’instruction correspondante affichée dans le volet **SQL** peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="8119d-138">The corresponding statement in the **SQL** pane might look like this:</span></span>  
  
    ```  
    SELECT   pub_id, SUM(price) AS Totalprice  
    FROM     titles  
    GROUP BY pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8119d-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8119d-139">See Also</span></span>  
 [<span data-ttu-id="8119d-140">Trier et regrouper des résultats de requête &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8119d-140">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
