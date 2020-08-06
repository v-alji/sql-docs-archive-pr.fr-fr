---
title: Compter les lignes d’une table (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- totals [SQL Server], row counts
- row counts [SQL Server]
- column values [SQL Server]
- number of rows
- number of values
- counting rows
ms.assetid: dda4296a-1d16-4e77-8d6f-e295f6dd4e87
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6dca92fb955b776f56d9b51f28b1a486b89f18f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700512"
---
# <a name="count-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="c6b46-102">Compter les lignes d'une table (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c6b46-102">Count Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="c6b46-103">Vous pouvez compter les lignes d'une table afin de déterminer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c6b46-103">You can count rows in a table to determine:</span></span>  
  
-   <span data-ttu-id="c6b46-104">le nombre total de lignes dans une table, par exemple le décompte de tous les livres d'une table `titles` ;</span><span class="sxs-lookup"><span data-stu-id="c6b46-104">The total number of rows in a table, for example, a count of all the books in a `titles` table.</span></span>  
  
-   <span data-ttu-id="c6b46-105">le nombre de lignes d'une table qui répondent à une condition spécifique, par exemple, le nombre de livres publiés par un éditeur dans une table `titles` ;</span><span class="sxs-lookup"><span data-stu-id="c6b46-105">The number of rows in a table that meet a specific condition, for example, the number of books by one publisher in a `titles` table.</span></span>  
  
-   <span data-ttu-id="c6b46-106">le nombre de valeurs d'une colonne donnée.</span><span class="sxs-lookup"><span data-stu-id="c6b46-106">The number of values in a particular column.</span></span>  
  
 <span data-ttu-id="c6b46-107">Lorsque vous comptez les valeurs d'une colonne, les valeurs null ne sont pas reprises dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="c6b46-107">When you count values in a column, nulls are not included in the count.</span></span> <span data-ttu-id="c6b46-108">Vous pouvez, par exemple, compter le nombre de livres d'une table `titles` qui affichent des valeurs dans la colonne `advance` .</span><span class="sxs-lookup"><span data-stu-id="c6b46-108">For example, you might count the number of books in a `titles` table that have values in the `advance` column.</span></span> <span data-ttu-id="c6b46-109">Par défaut, le nombre inclut toutes les valeurs, et pas seulement les valeurs uniques.</span><span class="sxs-lookup"><span data-stu-id="c6b46-109">By default, the count includes all values, not just unique values.</span></span>  
  
 <span data-ttu-id="c6b46-110">Les procédures associées aux trois types de nombres sont similaires.</span><span class="sxs-lookup"><span data-stu-id="c6b46-110">The procedures for all three types of counts are similar.</span></span>  
  
### <a name="to-count-all-the-rows-in-a-table"></a><span data-ttu-id="c6b46-111">Pour compter toutes les lignes d'une table</span><span class="sxs-lookup"><span data-stu-id="c6b46-111">To count all the rows in a table</span></span>  
  
1.  <span data-ttu-id="c6b46-112">Assurez-vous que la table à synthétiser figure déjà dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="c6b46-112">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="c6b46-113">Cliquez avec le bouton droit sur un point de l’arrière-plan du volet Schéma, puis choisissez **Ajouter un groupe par** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="c6b46-113">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="c6b46-114">Le [Concepteur de requêtes et de vues](visual-database-tools.md) ajoute une colonne **Group By** à la grille dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="c6b46-114">The [Query and View Designer](visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="c6b46-115">Sélectionnez \*\* \* (toutes les colonnes)\*\* dans le rectangle représentant la table ou l’objet table.</span><span class="sxs-lookup"><span data-stu-id="c6b46-115">Select **\* (All Columns)** in the rectangle representing the table or table-valued object.</span></span>  
  
     <span data-ttu-id="c6b46-116">Le Concepteur de requêtes et de vues insère automatiquement le terme **Count** dans la colonne **Group By** du volet Critères et assigne un alias de colonne à la colonne que vous synthétisez.</span><span class="sxs-lookup"><span data-stu-id="c6b46-116">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="c6b46-117">Il est possible de remplacer l'alias généré automatiquement par un autre, plus significatif.</span><span class="sxs-lookup"><span data-stu-id="c6b46-117">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="c6b46-118">Pour plus d’informations, consultez [Créer des alias de colonnes &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c6b46-118">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="c6b46-119">Exécute la requête.</span><span class="sxs-lookup"><span data-stu-id="c6b46-119">Run the query.</span></span>  
  
### <a name="to-count-all-the-rows-that-meet-a-condition"></a><span data-ttu-id="c6b46-120">Pour compter toutes les lignes répondant à une condition</span><span class="sxs-lookup"><span data-stu-id="c6b46-120">To count all the rows that meet a condition</span></span>  
  
1.  <span data-ttu-id="c6b46-121">Assurez-vous que la table à synthétiser figure déjà dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="c6b46-121">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="c6b46-122">Cliquez avec le bouton droit sur un point de l’arrière-plan du volet Schéma, puis choisissez **Ajouter un groupe par** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="c6b46-122">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="c6b46-123">Le Concepteur de requêtes et de vues ajoute une colonne **Group By** à la grille dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="c6b46-123">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="c6b46-124">Sélectionnez \*\* \* (toutes les colonnes)\*\* dans le rectangle représentant la table ou l’objet structuré en table.</span><span class="sxs-lookup"><span data-stu-id="c6b46-124">Select **\*(All Columns)** in the rectangle representing the table or table-structured object.</span></span>  
  
     <span data-ttu-id="c6b46-125">Le Concepteur de requêtes et de vues insère automatiquement le terme **Count** dans la colonne **Group By** du volet Critères et assigne un alias de colonne à la colonne que vous synthétisez.</span><span class="sxs-lookup"><span data-stu-id="c6b46-125">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="c6b46-126">Pour créer un en-tête de colonne plus significatif dans le résultat de la requête, consultez [Créer des alias de colonnes &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c6b46-126">To create a more useful column heading in query output, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="c6b46-127">Ajoutez la colonne de données sur laquelle doit porter la recherche et décochez ensuite la case dans la colonne **Sortie**.</span><span class="sxs-lookup"><span data-stu-id="c6b46-127">Add the data column that you want to search, and then clear the check box in the **Output** column.</span></span>  
  
     <span data-ttu-id="c6b46-128">Le Concepteur de requêtes et de vues insère automatiquement le terme **Group By** dans la colonne **Group By** de la grille.</span><span class="sxs-lookup"><span data-stu-id="c6b46-128">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
5.  <span data-ttu-id="c6b46-129">Remplacez le terme **Group By** par **Where** dans la colonne **Group By**.</span><span class="sxs-lookup"><span data-stu-id="c6b46-129">Change **Group By** in the **Group By** column to **Where**.</span></span>  
  
6.  <span data-ttu-id="c6b46-130">Dans la colonne **Filter** pour la colonne de données sur laquelle doit porter la recherche, entrez la condition de la recherche.</span><span class="sxs-lookup"><span data-stu-id="c6b46-130">In the **Filter** column for the data column to search, enter the search condition.</span></span>  
  
7.  <span data-ttu-id="c6b46-131">Exécute la requête.</span><span class="sxs-lookup"><span data-stu-id="c6b46-131">Run the query.</span></span>  
  
### <a name="to-count-the-values-in-a-column"></a><span data-ttu-id="c6b46-132">Pour compter les valeurs d'une colonne</span><span class="sxs-lookup"><span data-stu-id="c6b46-132">To count the values in a column</span></span>  
  
1.  <span data-ttu-id="c6b46-133">Assurez-vous que la table à synthétiser figure déjà dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="c6b46-133">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="c6b46-134">Cliquez avec le bouton droit sur un point de l’arrière-plan du volet Schéma, puis choisissez **Ajouter un groupe par** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="c6b46-134">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="c6b46-135">Le Concepteur de requêtes et de vues ajoute une colonne **Group By** à la grille dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="c6b46-135">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="c6b46-136">Ajoutez la colonne sur laquelle porte le comptage dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="c6b46-136">Add the column that you want to count to the Criteria pane.</span></span>  
  
     <span data-ttu-id="c6b46-137">Le Concepteur de requêtes et de vues insère automatiquement le terme **Group By** dans la colonne **Group By** de la grille.</span><span class="sxs-lookup"><span data-stu-id="c6b46-137">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
4.  <span data-ttu-id="c6b46-138">Remplacez le terme **Group By** par **Count** dans la colonne **Group By**.</span><span class="sxs-lookup"><span data-stu-id="c6b46-138">Change **Group By** in the **Group By** column to **Count**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6b46-139">Pour compter exclusivement des valeurs uniques, choisissez **Count Distinct**.</span><span class="sxs-lookup"><span data-stu-id="c6b46-139">To count only unique values, choose **Count Distinct**.</span></span>  
  
5.  <span data-ttu-id="c6b46-140">Exécute la requête.</span><span class="sxs-lookup"><span data-stu-id="c6b46-140">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6b46-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6b46-141">See Also</span></span>  
 <span data-ttu-id="c6b46-142">[Trier et regrouper les résultats des requêtes &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c6b46-142">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="c6b46-143">Résumer les résultats de la requête &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c6b46-143">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
