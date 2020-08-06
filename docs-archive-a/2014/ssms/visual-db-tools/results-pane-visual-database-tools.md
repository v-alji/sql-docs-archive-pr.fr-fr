---
title: Volet Résultats (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- result sets [SQL Server], queries
- synchronization [SQL Server], query results with definition
- displaying query results in grid
- grid showing query results [SQL Server]
- showing query results in grid
- Query Designer [SQL Server], Results pane
- results [SQL Server], query
- viewing query results
- queries [SQL Server], results
- Results pane
ms.assetid: 6309a1bc-a628-4141-8bb5-b35924bd19f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: f0db32336931f74777be56befcde9501dc484b69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600442"
---
# <a name="results-pane-visual-database-tools"></a><span data-ttu-id="d12dc-102">Volet Résultats (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d12dc-102">Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="d12dc-103">Le volet Résultats montre les résultats de la dernière requête SELECT exécutée.</span><span class="sxs-lookup"><span data-stu-id="d12dc-103">The Results pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="d12dc-104">(Les résultats des autres types de requêtes sont affichés dans des boîtes de messages.) Pour ouvrir le volet Résultats, ouvrez ou créez une requête ou encore une vue, ou retournez les données d'une table.</span><span class="sxs-lookup"><span data-stu-id="d12dc-104">(The results of other query types are displayed in message boxes.) To open the results pane, open or create a query or view or return a table's data.</span></span> <span data-ttu-id="d12dc-105">Si le volet Résultats ne s'affiche pas par défaut, dans le menu **Concepteur de requêtes** , pointez sur **Volet**, puis cliquez sur **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="d12dc-105">If the results pane doesn't show by default, from the **Query Designer** menu, point to **Pane**, and then click **Results**.</span></span>  
  
## <a name="what-you-can-do-in-the-results-pane"></a><span data-ttu-id="d12dc-106">Actions autorisées dans le volet Résultats</span><span class="sxs-lookup"><span data-stu-id="d12dc-106">What You Can Do in the Results Pane</span></span>  
  
-   <span data-ttu-id="d12dc-107">Afficher l'ensemble des résultats de la dernière requête SELECT exécutée dans une grille de type feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="d12dc-107">View the result set for the most recently executed SELECT query in a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="d12dc-108">Pour les requêtes ou les vues affichant des données qui proviennent d'une table ou vue unique, vous pouvez modifier les valeurs dans les différentes colonnes du jeu de résultats, ajouter de nouvelles lignes et supprimer des lignes existantes.</span><span class="sxs-lookup"><span data-stu-id="d12dc-108">For queries or views that show data from a single table or view, you can edit the values in individual columns in the result set, add new rows, and delete existing rows.</span></span>  
  
## <a name="limitations-in-the-results-pane"></a><span data-ttu-id="d12dc-109">Limitations dans le volet Résultats</span><span class="sxs-lookup"><span data-stu-id="d12dc-109">Limitations in the Results Pane</span></span>  
  
-   <span data-ttu-id="d12dc-110">Les résultats retournés par les fonctions table ne peuvent être mis à jour que dans certains cas.</span><span class="sxs-lookup"><span data-stu-id="d12dc-110">Results returned by table-valued functions can only be updated in some cases.</span></span>  
  
-   <span data-ttu-id="d12dc-111">Les requêtes ou vues qui comprennent des colonnes provenant de plusieurs tables ou vues ne peuvent pas être mises à jour.</span><span class="sxs-lookup"><span data-stu-id="d12dc-111">Queries or views that include columns from more than one table or view cannot be updated.</span></span>  
  
-   <span data-ttu-id="d12dc-112">Les résultats retournés par une procédure stockée ne peuvent pas être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="d12dc-112">Results returned by a stored procedure cannot be updated.</span></span>  
  
-   <span data-ttu-id="d12dc-113">Les requêtes ou vues utilisant des clauses GROUP BY or DISTINCT ne peuvent pas être mises à jour.</span><span class="sxs-lookup"><span data-stu-id="d12dc-113">Queries or views using the GROUP BY or DISTINCT clauses are not updatable.</span></span>  
  
## <a name="navigating-in-the-results-pane"></a><span data-ttu-id="d12dc-114">Navigation dans le volet Résultats</span><span class="sxs-lookup"><span data-stu-id="d12dc-114">Navigating in the Results Pane</span></span>  
 <span data-ttu-id="d12dc-115">Vous pouvez naviguer rapidement au sein des enregistrements à l'aide de la barre de navigation située au bas du volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="d12dc-115">You can quickly navigate through the records using the navigation bar at the bottom of the Results pane.</span></span>  
  
 <span data-ttu-id="d12dc-116">Vous disposez de boutons permettant d'accéder aux premiers et aux derniers enregistrements, aux enregistrements suivants et précédents, ainsi qu'à un enregistrement particulier.</span><span class="sxs-lookup"><span data-stu-id="d12dc-116">There are buttons for going to the first and last records, the next and previous records, and for going to a particular record.</span></span>  
  
 <span data-ttu-id="d12dc-117">Pour accéder à un enregistrement particulier, tapez le numéro de la ligne dans la zone de texte située dans la barre de navigation, puis appuyez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="d12dc-117">To go to a particular record, type the number of the row in the text box in the navigation bar and then press ENTER.</span></span>  
  
 <span data-ttu-id="d12dc-118">Pour plus d’informations sur l’utilisation des raccourcis clavier dans le Concepteur de requêtes et de vues, consultez [Naviguer dans le Concepteur de requêtes et de vues &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d12dc-118">For information about using keyboard shortcuts in the Query and View Designer see [Navigate in the Query and View Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="keeping-the-results-set-synchronized-with-the-query-definition"></a><span data-ttu-id="d12dc-119">Préserver la synchronisation du jeu de résultats avec la définition de la requête</span><span class="sxs-lookup"><span data-stu-id="d12dc-119">Keeping the Results Set Synchronized with the Query Definition</span></span>  
 <span data-ttu-id="d12dc-120">Lorsque vous travaillez sur les résultats d'une requête ou d'une vue, il est possible que les enregistrements du volet Résultats ne soient plus synchronisés avec la définition de la requête.</span><span class="sxs-lookup"><span data-stu-id="d12dc-120">While you are working on the results of a query or view it is possible for the records in the results pane to get out of synchronization with the query's definition.</span></span> <span data-ttu-id="d12dc-121">Par exemple, si vous exécutez une requête pour quatre des cinq colonnes dans une table, puis utilisez le volet Schéma pour ajouter la cinquième colonne à la définition de la requête, les données de cette cinquième colonne ne seront pas automatiquement ajoutées au volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="d12dc-121">For example, if you run a query for four out of five columns in a table, and then use the Diagram pane to add the fifth column to the definition of the query, that fifth column's data will not automatically be added to the Results pane.</span></span> <span data-ttu-id="d12dc-122">Pour que le volet Résultats reflète la nouvelle définition de requête, exécutez à nouveau la requête.</span><span class="sxs-lookup"><span data-stu-id="d12dc-122">To make the results pane reflect the new query definition, run the query again.</span></span>  
  
 <span data-ttu-id="d12dc-123">Si une requête est modifiée, une icône d'alerte avec le texte « Requête modifiée » apparaît dans le coin inférieur droit du volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="d12dc-123">If a query changes, an alert icon and the text "Query Changed" appears in the lower-right corner of the results pane.</span></span> <span data-ttu-id="d12dc-124">L'icône apparaît également dans le coin supérieur gauche du volet.</span><span class="sxs-lookup"><span data-stu-id="d12dc-124">The icon is repeated in the upper-left corner of the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d12dc-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d12dc-125">See Also</span></span>  
 <span data-ttu-id="d12dc-126">[Créer des requêtes &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d12dc-126">[Create Queries &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="d12dc-127">[Exécuter des requêtes &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d12dc-127">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="d12dc-128">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d12dc-128">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="d12dc-129">[Volet Schéma &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d12dc-129">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="d12dc-130">[Volet critères &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d12dc-130">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="d12dc-131">Utiliser des données du volet de résultats &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d12dc-131">Work with Data in the Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
