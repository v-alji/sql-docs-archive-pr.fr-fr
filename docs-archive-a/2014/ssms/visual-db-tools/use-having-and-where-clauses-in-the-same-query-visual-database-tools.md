---
title: Utilisation des clauses HAVING et WHERE dans la même requête (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- search conditions [SQL Server], HAVING clause
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- HAVING clause, search criteria
- search conditions [SQL Server], WHERE clause
- WHERE clause, search criteria
- excluding rows
ms.assetid: 1e07cf56-b4b7-4c49-8ddd-c276812a7148
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f6b471a60bf225ee61bdbbf0ecec30f21a92cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696367"
---
# <a name="use-having-and-where-clauses-in-the-same-query-visual-database-tools"></a><span data-ttu-id="92988-102">Utiliser les clauses HAVING et WHERE dans la même requête (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="92988-102">Use HAVING and WHERE Clauses in the Same Query (Visual Database Tools)</span></span>
  <span data-ttu-id="92988-103">Il peut arriver que vous souhaitiez exclure des lignes individuelles de groupes (à l'aide d'une clause WHERE) avant d'appliquer une condition aux groupes dans leur ensemble (à l'aide d'une clause HAVING).</span><span class="sxs-lookup"><span data-stu-id="92988-103">In some instances, you might want to exclude individual rows from groups (using a WHERE clause) before applying a condition to groups as a whole (using a HAVING clause).</span></span>  
  
 <span data-ttu-id="92988-104">Une clause HAVING est similaire à une clause WHERE si ce n'est qu'elle s'applique uniquement aux groupes dans leur ensemble (c'est-à-dire aux lignes du jeu de résultats qui représentent des groupes), tandis que la clause WHERE s'applique aux lignes individuelles.</span><span class="sxs-lookup"><span data-stu-id="92988-104">A HAVING clause is like a WHERE clause, but applies only to groups as a whole (that is, to the rows in the result set representing groups), whereas the WHERE clause applies to individual rows.</span></span> <span data-ttu-id="92988-105">Une requête peut comporter à la fois une clause WHERE et une clause HAVING.</span><span class="sxs-lookup"><span data-stu-id="92988-105">A query can contain both a WHERE clause and a HAVING clause.</span></span> <span data-ttu-id="92988-106">Dans ce cas :</span><span class="sxs-lookup"><span data-stu-id="92988-106">In that case:</span></span>  
  
-   <span data-ttu-id="92988-107">La clause WHERE est d'abord appliquée aux lignes individuelles dans les tables ou les objets table du volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="92988-107">The WHERE clause is applied first to the individual rows in the tables or table-valued objects in the Diagram pane.</span></span> <span data-ttu-id="92988-108">Seules les lignes répondant aux conditions précisées dans la clause WHERE sont groupées.</span><span class="sxs-lookup"><span data-stu-id="92988-108">Only the rows that meet the conditions in the WHERE clause are grouped.</span></span>  
  
-   <span data-ttu-id="92988-109">La clause HAVING est ensuite appliquée aux lignes du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="92988-109">The HAVING clause is then applied to the rows in the result set.</span></span> <span data-ttu-id="92988-110">Seuls les groupes qui répondent aux conditions HAVING figurent dans le résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="92988-110">Only the groups that meet the HAVING conditions appear in the query output.</span></span> <span data-ttu-id="92988-111">Vous ne pouvez appliquer une clause HAVING qu'aux colonnes qui apparaissent également dans la clause GROUP BY ou dans une fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="92988-111">You can apply a HAVING clause only to columns that also appear in the GROUP BY clause or in an aggregate function.</span></span>  
  
 <span data-ttu-id="92988-112">Imaginons, par exemple, que vous décidiez de joindre les tables `titles` et `publishers` pour créer une requête affichant le prix moyen d'un livre pour un ensemble d'éditeurs.</span><span class="sxs-lookup"><span data-stu-id="92988-112">For example, imagine that you are joining the `titles` and `publishers` tables to create a query showing the average book price for a set of publishers.</span></span> <span data-ttu-id="92988-113">Seul le prix moyen d’un ensemble donné d’éditeurs vous intéresse, en l’occurrence ceux répertoriés en Californie.</span><span class="sxs-lookup"><span data-stu-id="92988-113">You want to see the average price for only a specific set of publishers - perhaps only the publishers in the state of California.</span></span> <span data-ttu-id="92988-114">Par ailleurs, vous ne souhaitez afficher le prix moyen que si ce dernier est supérieur à 10 $.</span><span class="sxs-lookup"><span data-stu-id="92988-114">And even then, you want to see the average price only if it is over $10.00.</span></span>  
  
 <span data-ttu-id="92988-115">Vous définissez la première condition en incluant une clause WHERE qui rejette tous les éditeurs non répertoriés en Californie, avant de calculer les prix moyens.</span><span class="sxs-lookup"><span data-stu-id="92988-115">You can establish the first condition by including a WHERE clause, which discards any publishers that are not in California, before calculating average prices.</span></span> <span data-ttu-id="92988-116">La seconde condition nécessite une clause HAVING dans la mesure où elle est fondée sur les résultats du regroupement et de la synthèse des données.</span><span class="sxs-lookup"><span data-stu-id="92988-116">The second condition requires a HAVING clause, because the condition is based on the results of grouping and summarizing the data.</span></span> <span data-ttu-id="92988-117">L’instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="92988-117">The resulting SQL statement might look like this:</span></span>  
  
```  
SELECT titles.pub_id, AVG(titles.price)  
FROM titles INNER JOIN publishers  
   ON titles.pub_id = publishers.pub_id  
WHERE publishers.state = 'CA'  
GROUP BY titles.pub_id  
HAVING AVG(price) > 10  
```  
  
 <span data-ttu-id="92988-118">Vous pouvez créer à la fois une clause HAVING et une clause WHERE dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="92988-118">You can create both HAVING and WHERE clauses in the Criteria pane.</span></span> <span data-ttu-id="92988-119">Par défaut, si vous spécifiez une condition de recherche pour une colonne, la condition fait alors partie de la clause HAVING.</span><span class="sxs-lookup"><span data-stu-id="92988-119">By default, if you specify a search condition for a column, the condition becomes part of the HAVING clause.</span></span> <span data-ttu-id="92988-120">Toutefois, vous pouvez modifier la condition de sorte qu'elle devienne une clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="92988-120">However, you can change the condition to be a WHERE clause.</span></span>  
  
 <span data-ttu-id="92988-121">Il est possible de créer une clause WHERE et une clause HAVING qui s'appliquent à une même colonne.</span><span class="sxs-lookup"><span data-stu-id="92988-121">You can create a WHERE clause and HAVING clause involving the same column.</span></span> <span data-ttu-id="92988-122">Pour cela, vous devez ajouter deux fois la colonne au volet Critères, puis spécifier qu'une instance doit faire partie de la clause HAVING et l'autre de la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="92988-122">To do so, you must add the column twice to the Criteria pane, then specify one instance as part of the HAVING clause and the other instance as part of the WHERE clause.</span></span>  
  
### <a name="to-specify-a-where-condition-in-an-aggregate-query"></a><span data-ttu-id="92988-123">Pour spécifier une condition WHERE dans une requête d'agrégation</span><span class="sxs-lookup"><span data-stu-id="92988-123">To specify a WHERE condition in an aggregate query</span></span>  
  
1.  <span data-ttu-id="92988-124">Spécifiez les groupes de votre requête.</span><span class="sxs-lookup"><span data-stu-id="92988-124">Specify the groups for your query.</span></span> <span data-ttu-id="92988-125">Pour plus d’informations, consultez [Regrouper des lignes dans les résultats de requête &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="92988-125">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="92988-126">Si elle ne figure pas encore dans le volet Critères, ajoutez la colonne sur laquelle vous souhaitez baser la condition WHERE.</span><span class="sxs-lookup"><span data-stu-id="92988-126">If it is not already in the Criteria pane, add the column on which you want to base the WHERE condition.</span></span>  
  
3.  <span data-ttu-id="92988-127">Supprimez la colonne **Sortie** à moins que la colonne de données fasse partie de la clause GROUP BY ou soit incluse dans une fonction d’agrégation.</span><span class="sxs-lookup"><span data-stu-id="92988-127">Clear the **Output** column unless the data column is part of the GROUP BY clause or included in an aggregate function.</span></span>  
  
4.  <span data-ttu-id="92988-128">Dans la colonne **Filtre** , spécifiez la condition WHERE.</span><span class="sxs-lookup"><span data-stu-id="92988-128">In the **Filter** column, specify the WHERE condition.</span></span> <span data-ttu-id="92988-129">Le Concepteur de requêtes et de vues ajoute la condition à la clause HAVING de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="92988-129">The Query and View Designer adds the condition to the HAVING clause of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92988-130">La requête illustrée dans cet exemple de procédure joint deux tables, `titles` et `publishers`.</span><span class="sxs-lookup"><span data-stu-id="92988-130">The query shown in the example for this procedure joins two tables, `titles` and `publishers`.</span></span>  
  
     <span data-ttu-id="92988-131">À ce stade de la requête, l'instruction SQL contient une clause HAVING :</span><span class="sxs-lookup"><span data-stu-id="92988-131">At this point in the query, the SQL statement contains a HAVING clause:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    GROUP BY titles.pub_id  
    HAVING publishers.state = 'CA'  
    ```  
  
5.  <span data-ttu-id="92988-132">Dans la colonne **Grouper par** , sélectionnez **Where** dans la liste des options de synthèse et de groupe.</span><span class="sxs-lookup"><span data-stu-id="92988-132">In the **Group By** column, select **Where** from the list of group and summary options.</span></span> <span data-ttu-id="92988-133">Le Concepteur de requêtes et de vues supprime la condition de la clause HAVING dans l'instruction SQL et l'ajoute à la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="92988-133">The Query and View Designer removes the condition from the HAVING clause in the SQL statement and adds it to the WHERE clause.</span></span>  
  
     <span data-ttu-id="92988-134">L'instruction SQL est modifiée afin d'inclure à la place une clause WHERE :</span><span class="sxs-lookup"><span data-stu-id="92988-134">The SQL statement changes to include a WHERE clause instead:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    WHERE publishers.state = 'CA'  
    GROUP BY titles.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="92988-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92988-135">See Also</span></span>  
 <span data-ttu-id="92988-136">[Trier et regrouper les résultats des requêtes &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="92988-136">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="92988-137">Résumer les résultats de la requête &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="92988-137">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
