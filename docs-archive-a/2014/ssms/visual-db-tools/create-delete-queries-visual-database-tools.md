---
title: Créer des requêtes Delete (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- row removal [SQL Server], Delete query
- Delete query
- queries [SQL Server], types
- removing rows
- removing data
- data deletions [SQL Server]
- deleting rows
- deleting data
ms.assetid: 0db3af43-1ec4-48c8-b769-2bb9c76d3434
author: stevestein
ms.author: sstein
ms.openlocfilehash: a76c3aaef623365e419f40f3058308f6217d75d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614282"
---
# <a name="create-delete-queries-visual-database-tools"></a><span data-ttu-id="329fb-102">Créer des requêtes Delete (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="329fb-102">Create Delete Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="329fb-103">Vous pouvez supprimer toutes les lignes d'une table à l'aide d'une requête Delete.</span><span class="sxs-lookup"><span data-stu-id="329fb-103">You can delete all rows in a table by using a Delete query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="329fb-104">La suppression de toutes les lignes d'une table supprime les données de la table, mais ne supprime pas la table elle-même.</span><span class="sxs-lookup"><span data-stu-id="329fb-104">Deleting all rows from a table clears the data in the table but does not delete the table itself.</span></span> <span data-ttu-id="329fb-105">Pour supprimer une table d’une base de données, cliquez avec le bouton droit sur la table dans l’Explorateur d’objets et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="329fb-105">To delete a table from a database, right-click the table in Object Explorer and click **Delete**.</span></span>  
  
 <span data-ttu-id="329fb-106">Lorsque vous créez une requête Delete, le volet Critères change afin de refléter les options de suppression de lignes disponibles.</span><span class="sxs-lookup"><span data-stu-id="329fb-106">When you create a Delete query, the Criteria pane changes to reflect the options available for deleting rows.</span></span> <span data-ttu-id="329fb-107">Dans la mesure où vous n'affichez pas de données dans une requête Delete, les colonnes Sortie, Trier par et Ordre de tri sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="329fb-107">Because you do not display data in a Delete query, the Output, Sort By, and Sort Order columns are removed.</span></span> <span data-ttu-id="329fb-108">En outre, les cases à cocher en regard des noms de colonnes dans le rectangle représentant la table ou l'objet table sont supprimées puisqu'il est impossible de spécifier des colonnes individuelles à supprimer.</span><span class="sxs-lookup"><span data-stu-id="329fb-108">In addition, the check boxes next to the column names in the rectangle representing the table or table-valued object are removed because you cannot specify individual columns to delete.</span></span>  
  
 <span data-ttu-id="329fb-109">Si le Concepteur de requêtes et de vues ne peut pas supprimer une ou plusieurs lignes, aucune ligne n'est supprimée et un message s'affiche pour indiquer la ligne contenant les informations qui ne peuvent pas être supprimées de la base de données.</span><span class="sxs-lookup"><span data-stu-id="329fb-109">If the Query and View Designer can't delete one or more of the rows none of them will be deleted and you will receive a message telling you which row(s) contain information that can't be deleted from the database.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="329fb-110">Il est impossible d'annuler l'action entraînée par l'exécution d'une requête Delete.</span><span class="sxs-lookup"><span data-stu-id="329fb-110">You cannot undo the action of executing a Delete query.</span></span> <span data-ttu-id="329fb-111">Par sécurité, sauvegardez vos données avant d'exécuter une requête Delete.</span><span class="sxs-lookup"><span data-stu-id="329fb-111">As a precaution, back up your data before executing a Delete query.</span></span>  
  
### <a name="to-create-a-delete-query"></a><span data-ttu-id="329fb-112">Pour créer une requête Delete</span><span class="sxs-lookup"><span data-stu-id="329fb-112">To create a Delete query</span></span>  
  
1.  <span data-ttu-id="329fb-113">Ajoutez la table dont vous souhaitez supprimer des lignes dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="329fb-113">Add the table to delete rows from to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="329fb-114">Dans le menu **Concepteur de requêtes** , pointez sur **Modifier le type**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="329fb-114">From the **Query Designer** menu, point to **Change Type**, and then click **Delete**.</span></span> <span data-ttu-id="329fb-115">**Remarque** Si plusieurs tables sont affichées dans le volet Schéma quand vous commencez la requête Delete, le Concepteur de requêtes et de vues affiche la [boîte de dialogue Supprimer une table](visual-database-tools.md) en vous invitant à indiquer le nom de la table dont vous souhaitez supprimer des lignes.</span><span class="sxs-lookup"><span data-stu-id="329fb-115">**Note** If more than one table is displayed in the Diagram pane when you start the Delete query, the Query and View Designer displays the [Delete Table Dialog Box](visual-database-tools.md) to prompt you for the name of the table to delete rows from.</span></span>  
  
 <span data-ttu-id="329fb-116">Quand vous exécutez la requête Delete, aucun résultat n’apparaît dans le [volet Résultats](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="329fb-116">When you execute the Delete query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="329fb-117">En fait, un message indiquant le nombre de lignes supprimées s'affiche.</span><span class="sxs-lookup"><span data-stu-id="329fb-117">Instead, a message appears indicating how many rows were deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329fb-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="329fb-118">See Also</span></span>  
 <span data-ttu-id="329fb-119">[Types de requêtes pris en charge &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="329fb-119">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="329fb-120">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="329fb-120">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
