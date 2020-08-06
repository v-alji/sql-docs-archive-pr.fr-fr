---
title: Outils du Concepteur de requêtes et de vues (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.querydesigner
- vdt.pane.diagram
- vdt.pane.grid
- vdt.dlgbox.querybuilder
- vdt.pane.sql
- vdt.pane.results
helpviewer_keywords:
- Query Designer [SQL Server], panes
- View Designer, panes
- Query Designer [SQL Server], components
- View Designer, components
ms.assetid: 12e4b5a5-b793-4b6c-a0e5-c450c49bf26f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 29bd3fa9e171551197927aae0d1bc00446df6e7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704663"
---
# <a name="query-and-view-designer-tools-visual-database-tools"></a><span data-ttu-id="0175b-102">Outils du concepteur de requêtes et de vues (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0175b-102">Query and View Designer Tools (Visual Database Tools)</span></span>
  <span data-ttu-id="0175b-103">Lors de la création d'une requête, d'une vue, d'une fonction inline ou d'une procédure stockée à une seule instruction, le concepteur que vous utilisez se compose de quatre volet : le volet Schéma, le volet Critères, le volet SQL et le volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="0175b-103">When you design a query, view, in-line function, or single-statement stored procedure, the designer you use consists of four panes: the Diagram pane, the Criteria pane, the SQL pane, and the Results pane.</span></span>  
  
 <span data-ttu-id="0175b-104">![Concepteur de requêtes](../../database-engine/media//vs-queryviewdsgpanes.gif "Concepteur de requêtes")</span><span class="sxs-lookup"><span data-stu-id="0175b-104">![Query Designer](../../database-engine/media//vs-queryviewdsgpanes.gif "Query Designer")</span></span>  
  
-   <span data-ttu-id="0175b-105">Le volet Schéma affiche les tables ainsi que les autres objets table que vous interrogez.</span><span class="sxs-lookup"><span data-stu-id="0175b-105">The Diagram pane displays the tables and other table-valued objects that you are querying.</span></span> <span data-ttu-id="0175b-106">Chaque rectangle représente une table ou un objet table et affiche les colonnes de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="0175b-106">Each rectangle represents a table or table-valued object and shows the available data columns.</span></span> <span data-ttu-id="0175b-107">Les jointures sont indiquées par des traits reliant les rectangles.</span><span class="sxs-lookup"><span data-stu-id="0175b-107">Joins are indicated by lines between the rectangles.</span></span> <span data-ttu-id="0175b-108">Pour plus d’informations, consultez [Volet Schéma &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0175b-108">For more information, see [Diagram Pane &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="0175b-109">Le volet Critères contient un quadrillage similaire à celui d'une feuille de calcul, dans lequel vous pouvez spécifier des options, telles que les colonnes de données à afficher, les lignes à sélectionner, la façon de grouper les lignes, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="0175b-109">The Criteria pane contains a spreadsheet-like grid in which you specify options, such as which data columns to display, what rows to select, how to group rows, and so on.</span></span> <span data-ttu-id="0175b-110">Pour plus d’informations, consultez [Volet Critères &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0175b-110">For more information, see [Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="0175b-111">Le volet SQL affiche l'instruction SQL de la requête ou de la vue.</span><span class="sxs-lookup"><span data-stu-id="0175b-111">The SQL pane displays the SQL statement for the query or view.</span></span> <span data-ttu-id="0175b-112">Vous pouvez modifier l'instruction SQL créée par le Concepteur ou entrer la vôtre.</span><span class="sxs-lookup"><span data-stu-id="0175b-112">You can edit the SQL statement created by the Designer or you can enter your own SQL statement.</span></span> <span data-ttu-id="0175b-113">Cela s'avère particulièrement utile lorsque vous devez entrer des instructions SQL impossibles à créer avec les volets Schéma et Critères, telles que des requêtes Union.</span><span class="sxs-lookup"><span data-stu-id="0175b-113">It is particularly useful for entering SQL statements that cannot be created using the Diagram and Criteria panes, such as union queries.</span></span> <span data-ttu-id="0175b-114">Pour plus d’informations, consultez [Volet SQL &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0175b-114">For more information, see [SQL Pane &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="0175b-115">Le volet Résultats montre une grille affichant les données extraites par la requête ou la vue.</span><span class="sxs-lookup"><span data-stu-id="0175b-115">The Results pane shows a grid with data retrieved by the query or view.</span></span> <span data-ttu-id="0175b-116">Dans le Concepteur de requêtes et de vues, le volet montre les résultats de la dernière requête SELECT exécutée.</span><span class="sxs-lookup"><span data-stu-id="0175b-116">In the Query and View Designer, the pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="0175b-117">Pour modifier la base de données, vous pouvez changer des valeurs dans les cellules de la grille, ajouter des lignes ou en supprimer.</span><span class="sxs-lookup"><span data-stu-id="0175b-117">You can modify the database by editing values in the cells of the grid, and you can add or delete rows.</span></span> <span data-ttu-id="0175b-118">Pour plus d’informations, consultez [Volet Résultats &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0175b-118">For more information, see [Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="0175b-119">Pour créer une requête ou une vue, utilisez un ou plusieurs de ces trois volets : pour spécifier une colonne à afficher, vous pouvez la choisir dans le volet Schéma, l'entrer dans le volet Critères ou l'inclure dans une instruction SQL dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="0175b-119">You can create a query or view by working in any of the panes: you can specify a column to display by choosing it in the Diagram pane, entering it into the Criteria pane, or making it part of the SQL statement in the SQL pane.</span></span>  
  
## <a name="displaying-and-hiding-panes"></a><span data-ttu-id="0175b-120">Affichage et masquage des volets</span><span class="sxs-lookup"><span data-stu-id="0175b-120">Displaying and Hiding Panes</span></span>  
 <span data-ttu-id="0175b-121">Pour masquer ou afficher un volet, cliquez avec le bouton droit sur la surface de design, pointez sur **Volet**, puis cliquez sur le nom du volet.</span><span class="sxs-lookup"><span data-stu-id="0175b-121">To hide a pane or display a pane that is not visible, right-click the design surface, point to **Pane**, and then click the name of the pane.</span></span> <span data-ttu-id="0175b-122">Si le Concepteur de requêtes et de vues est ouvert en mode Concepteur de requêtes, le volet **Résultats** n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="0175b-122">If the Query and View Designer is opened in Query Designer mode, the **Results** pane is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0175b-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0175b-123">See Also</span></span>  
 <span data-ttu-id="0175b-124">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0175b-124">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0175b-125">[Ouvrez le concepteur de requêtes et de vues &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0175b-125">[Open the Query and View Designer &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0175b-126">Éditeur SQL &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0175b-126">SQL Editor &#40;Visual Database Tools&#41;</span></span>](sql-editor-visual-database-tools.md)  
  
  
