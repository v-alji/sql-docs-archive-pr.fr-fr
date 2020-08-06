---
title: Créer des requêtes Insert Results (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- result sets [SQL Server], queries
- results [SQL Server], query
- Insert Results query
- queries [SQL Server], results
ms.assetid: 8770d630-09cc-47ec-a0e9-e9de2d7bbc89
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02643c2cf3295debe740a696941f8730d4417254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699119"
---
# <a name="create-insert-results-queries-visual-database-tools"></a><span data-ttu-id="3c7c4-102">Créer des requêtes Insert Results (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3c7c4-102">Create Insert Results Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="3c7c4-103">Vous pouvez copier des lignes d'une table à une autre ou au sein d'une même table à l'aide d'une requête Insert Results.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-103">You can copy rows from one table to another or within a table using an Insert Results query.</span></span> <span data-ttu-id="3c7c4-104">Dans une table `titles` par exemple, vous pouvez utiliser une requête Insert Results pour copier des informations sur les titres publiés par un éditeur dans une seconde table que vous pouvez mettre à la disposition de cet éditeur.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-104">For example, in a `titles` table, you can use an Insert Results query to copy information about all the titles for one publisher to a second table that you can make available to that publisher.</span></span> <span data-ttu-id="3c7c4-105">Une requête Insert Results ressemble à une requête Make Table, à la seule différence qu'elle copie des lignes dans une table existante.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-105">An Insert Results query is similar to Make Table Queries, but copies rows into an existing table.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="3c7c4-106">Vous pouvez également copier des lignes d'une table à une autre à l'aide de la fonctionnalité Couper-Coller.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-106">You can also copy rows from one table to another using cut and paste.</span></span> <span data-ttu-id="3c7c4-107">Créez une requête pour chaque table et exécutez les requêtes.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-107">Create a query for each table and run the queries.</span></span> <span data-ttu-id="3c7c4-108">Copiez les lignes de votre choix d'une grille de résultats vers une autre.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-108">Copy the rows you want from one results grid to the other.</span></span>  
  
 <span data-ttu-id="3c7c4-109">Lorsque vous créez une requête Insert Results, spécifiez :</span><span class="sxs-lookup"><span data-stu-id="3c7c4-109">When you create an Insert Results query, you specify:</span></span>  
  
-   <span data-ttu-id="3c7c4-110">la table de la base de données vers laquelle copier des lignes (la table de destination) ;</span><span class="sxs-lookup"><span data-stu-id="3c7c4-110">The database table to copy rows to (the destination table).</span></span>  
  
-   <span data-ttu-id="3c7c4-111">les tables à partir desquelles copier les lignes (les tables sources),</span><span class="sxs-lookup"><span data-stu-id="3c7c4-111">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="3c7c4-112">celles-ci devenant partie d'une sous-requête</span><span class="sxs-lookup"><span data-stu-id="3c7c4-112">The source table or tables become part of a subquery.</span></span> <span data-ttu-id="3c7c4-113">(si la copie est réalisée au sein d'une même table, la table source est la même que la table de destination) ;</span><span class="sxs-lookup"><span data-stu-id="3c7c4-113">If you are copying within a table, the source table is the same as the destination table.</span></span>  
  
-   <span data-ttu-id="3c7c4-114">les colonnes de la table source dont vous souhaitez copier le contenu ;</span><span class="sxs-lookup"><span data-stu-id="3c7c4-114">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="3c7c4-115">les colonnes cibles de la table de destination vers laquelle vous copiez les données ;</span><span class="sxs-lookup"><span data-stu-id="3c7c4-115">The target columns in the destination table to copy the data to.</span></span>  
  
-   <span data-ttu-id="3c7c4-116">les conditions de recherche pour définir les lignes à copier ;</span><span class="sxs-lookup"><span data-stu-id="3c7c4-116">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="3c7c4-117">l'ordre de tri, afin de copier, le cas échéant, les lignes dans un ordre précis ;</span><span class="sxs-lookup"><span data-stu-id="3c7c4-117">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="3c7c4-118">les options Group By, si vous ne souhaitez copier que des informations de synthèse.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-118">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="3c7c4-119">Dans l'exemple ci-dessous, la requête copie les informations de titres de la table `titles` vers une table d'archive appelée `archivetitles`.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-119">For example, the following query copies title information from the `titles` table to an archive table called `archivetitles`.</span></span> <span data-ttu-id="3c7c4-120">La requête copie le contenu des quatre colonnes de tous les titres appartenant à un éditeur donné :</span><span class="sxs-lookup"><span data-stu-id="3c7c4-120">The query copies the contents of four columns for all titles belonging to a particular publisher:</span></span>  
  
```  
INSERT INTO archivetitles   
   (title_id, title, type, pub_id)  
SELECT title_id, title, type, pub_id  
FROM titles  
WHERE (pub_id = '0766')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3c7c4-121">Pour insérer des valeurs dans une nouvelle ligne, utilisez une requête Insert Values.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-121">To insert values into a new row, use an Insert Values query.</span></span>  
  
 <span data-ttu-id="3c7c4-122">Vous pouvez copier le contenu de colonnes sélectionnées ou de toutes les colonnes dans une ligne.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-122">You can copy the contents of selected columns or of all columns in a row.</span></span> <span data-ttu-id="3c7c4-123">Dans les deux cas, les données copiées doivent être compatibles avec les colonnes des lignes de destination de la copie.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-123">In either case, the data you are copying must be compatible with the columns in the rows you are copying to.</span></span> <span data-ttu-id="3c7c4-124">Par exemple, si vous copiez le contenu d'une colonne telle que `price`, la colonne de la ligne vers laquelle vous copiez les données doit accepter les données numériques avec décimales.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-124">For example, if you copy the contents of a column such as `price`, the column in the row you are copying to must accept numeric data with decimal places.</span></span> <span data-ttu-id="3c7c4-125">Si vous copiez toute une ligne, la table de destination doit comporter des colonnes compatibles dont la position physique est identique à celle des colonnes de la table source.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-125">If you are copying an entire row, the destination table must have compatible columns in the same physical position as the source table.</span></span>  
  
 <span data-ttu-id="3c7c4-126">Lorsque vous créez une requête Insert Results, le volet Critères change afin de refléter les options de copie de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-126">When you create an Insert Results query, the Criteria pane changes to reflect options available for copying data.</span></span> <span data-ttu-id="3c7c4-127">Une colonne Ajout apparaît afin que vous puissiez spécifier les colonnes vers lesquelles copier les données.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-127">An Append column is added to allow you to specify the columns into which data should be copied.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="3c7c4-128">Il est impossible d'annuler l'action entraînée par l'exécution d'une requête Insert Results.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-128">You cannot undo the action of executing an Insert Results query.</span></span> <span data-ttu-id="3c7c4-129">Par sécurité, sauvegardez vos données avant d'exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-129">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-results-query"></a><span data-ttu-id="3c7c4-130">Pour créer une requête Insert Results</span><span class="sxs-lookup"><span data-stu-id="3c7c4-130">To create an Insert Results query</span></span>  
  
1.  <span data-ttu-id="3c7c4-131">Créez une nouvelle requête et ajoutez la table dont vous souhaitez copier les lignes (la table source).</span><span class="sxs-lookup"><span data-stu-id="3c7c4-131">Create a new query and add the table from which you want to copy rows (the source table).</span></span> <span data-ttu-id="3c7c4-132">Si vous copiez des lignes au sein d'une même table, vous pouvez ajouter la table source comme table de destination.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-132">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
2.  <span data-ttu-id="3c7c4-133">Dans le menu **Concepteur de requêtes** , pointez sur **Modifier le type**, puis cliquez sur **Insérer les résultats**.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-133">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
3.  <span data-ttu-id="3c7c4-134">Dans la boîte de dialogue [Choisir la table cible pour la requête Insérer les résultats](visual-database-tools.md), sélectionnez la table vers laquelle vous voulez copier les lignes (table de destination).</span><span class="sxs-lookup"><span data-stu-id="3c7c4-134">In the [Choose Target Table for Insert Results Dialog Box](visual-database-tools.md), select the table to copy rows to (the destination table).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3c7c4-135">Le Concepteur de requêtes et de vues ne peut pas déterminer à l'avance les tables et vues qu'il est possible de mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-135">The Query and View Designer cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="3c7c4-136">Ainsi, la liste **Nom de la table** de la boîte de dialogue **Choisir la table cible pour la requête Insérer les résultats** affiche toutes les tables et vues disponibles dans la connexion de données sur laquelle porte la requête, même celles vers lesquelles il est impossible de copier des lignes.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-136">Therefore, the **Table Name** list in the **Choose Table for Insert From Query** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
4.  <span data-ttu-id="3c7c4-137">Dans le rectangle représentant la table ou l'objet table, choisissez les noms des colonnes dont vous souhaitez copier le contenu.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-137">In the rectangle representing the table or table-valued object, choose the names of the columns whose contents you want to copy.</span></span> <span data-ttu-id="3c7c4-138">Pour copier des lignes entières, choisissez \*\* \* (toutes les colonnes)\*\*.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-138">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="3c7c4-139">Le Concepteur de requêtes et de vues ajoute les colonnes sélectionnées à la colonne **Colonne** du volet Critères.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-139">The Query and View Designer adds the columns you choose to the **Column** column of the Criteriapane.</span></span>  
  
5.  <span data-ttu-id="3c7c4-140">Dans la colonne **Ajouter** du volet Critères, sélectionnez une colonne cible dans la table de destination pour chaque colonne copiée.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-140">In the **Append** column of the Criteria pane, select a target column in the destination table for each column you are copying.</span></span> <span data-ttu-id="3c7c4-141">Choisissez \*TableName. \* \* si vous copiez des lignes entières.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-141">Choose *tablename.\** if you are copying entire rows.</span></span> <span data-ttu-id="3c7c4-142">Les colonnes de la table de destination doivent avoir des types de données identiques (ou compatibles) à ceux des colonnes de la table source.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-142">The columns in the destination table must have the same (or compatible) data types as the columns in the source table.</span></span>  
  
6.  <span data-ttu-id="3c7c4-143">Si vous souhaitez copier les lignes dans un ordre précis, spécifiez un ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-143">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="3c7c4-144">Pour plus d’informations, consultez [Trier et regrouper des résultats de requête &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c7c4-144">For details, see [Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span></span>  
  
7.  <span data-ttu-id="3c7c4-145">Spécifiez les lignes à copier en entrant des conditions de recherche dans la colonne **Filtre** .</span><span class="sxs-lookup"><span data-stu-id="3c7c4-145">Specify the rows to copy by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="3c7c4-146">Pour plus d’informations, consultez [Spécifier des critères de recherche &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c7c4-146">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="3c7c4-147">Si vous ne spécifiez pas de condition de recherche, toutes les lignes de la table source seront copiées vers la table de destination.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-147">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3c7c4-148">Lorsque vous ajoutez, dans le volet Critères, une colonne à utiliser dans une condition de recherche, le Concepteur de requêtes et de vues l'ajoute également à la liste des colonnes à copier.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-148">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="3c7c4-149">Pour utiliser une colonne dans le cadre de la recherche sans toutefois la copier, désactivez la case à cocher en regard du nom de la colonne dans le rectangle représentant la table ou l'objet table.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-149">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
8.  <span data-ttu-id="3c7c4-150">Si vous souhaitez copier des informations de synthèse, spécifiez des options Group By.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-150">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="3c7c4-151">Pour plus d’informations, consultez [Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c7c4-151">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="3c7c4-152">Quand vous exécutez une requête Insert Results, aucun résultat n’apparaît dans le [volet Résultats](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c7c4-152">When you execute an Insert Results query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="3c7c4-153">En fait, un message indiquant le nombre de lignes copiées s'affiche.</span><span class="sxs-lookup"><span data-stu-id="3c7c4-153">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7c4-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c7c4-154">See Also</span></span>  
 <span data-ttu-id="3c7c4-155">[Types de requêtes &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3c7c4-155">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3c7c4-156">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3c7c4-156">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
