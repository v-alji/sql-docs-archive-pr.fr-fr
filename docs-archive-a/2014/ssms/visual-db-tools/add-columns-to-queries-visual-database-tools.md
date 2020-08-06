---
title: Ajouter des colonnes à des requêtes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- queries [SQL Server], columns
- adding columns
ms.assetid: 82f3ba72-3d72-4fb1-8179-2a953a782787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 49c6e575eea2d4437be1f16b400ca22120471fcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603216"
---
# <a name="add-columns-to-queries-visual-database-tools"></a><span data-ttu-id="93463-102">Ajouter des colonnes à des requêtes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="93463-102">Add Columns to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="93463-103">Pour pouvoir utiliser une colonne dans une requête, vous devez l'ajouter à cette requête.</span><span class="sxs-lookup"><span data-stu-id="93463-103">To use a column in a query, you must add it to the query.</span></span> <span data-ttu-id="93463-104">Vous pouvez ajouter une colonne pour l'afficher dans le résultat d'une requête, l'utiliser à des fins de tri, y effectuer des recherches ou encore totaliser ses données.</span><span class="sxs-lookup"><span data-stu-id="93463-104">You might add a column to display it in query output, to use it for sorting, to search the contents of the column, or to summarize its contents.</span></span> <span data-ttu-id="93463-105">Vous pouvez spécifier les colonnes de la requête qui doivent être comprises dans le volet Résultats lors de l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="93463-105">You can decide which of the columns you use in the query are included in the results pane when the query is run.</span></span> <span data-ttu-id="93463-106">Pour plus d’informations, consultez [Supprimer des colonnes des résultats d’une requête &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="93463-106">For more information see [Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93463-107">Pour afficher le type de données d’une colonne dans le Concepteur de requêtes et de vues, sélectionnez la table ou l’objet table dans le **Volet Schéma** puis cliquez sur Liste des colonnes dans la fenêtre de propriétés.</span><span class="sxs-lookup"><span data-stu-id="93463-107">To view the data type of a column in Query and View Designer; select the table or table-valued object in the **Diagram Pane** and in the properties window click Column List.</span></span> <span data-ttu-id="93463-108">Ensuite, cliquez sur le **bouton de sélection (...)** pour ouvrir la boîte de dialogue **Liste des colonnes**.</span><span class="sxs-lookup"><span data-stu-id="93463-108">Then click the **ellipses (...)** to open the **Column List** dialog box.</span></span>  
  
 <span data-ttu-id="93463-109">Chaque fois que vous utilisez une colonne dans une requête, vous pouvez également utiliser une expression composée de toute association de colonnes, de littéraux, d'opérateurs et de fonctions.</span><span class="sxs-lookup"><span data-stu-id="93463-109">Wherever you use a column in a query, you can also use an expression that can consist of any combination of columns, literals, operators, and functions.</span></span>  
  
### <a name="to-add-an-individual-column"></a><span data-ttu-id="93463-110">Pour ajouter une colonne individuelle</span><span class="sxs-lookup"><span data-stu-id="93463-110">To add an individual column</span></span>  
  
-   <span data-ttu-id="93463-111">Dans le **Volet Schéma**, cochez la case située à côté de la colonne que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="93463-111">In the **Diagram Pane**, select the check box next to the column that you want to include.</span></span>  
  
     <span data-ttu-id="93463-112">-ou-</span><span class="sxs-lookup"><span data-stu-id="93463-112">-or-</span></span>  
  
-   <span data-ttu-id="93463-113">Dans le **Volet Critères**, accédez à la première ligne vierge de la grille, cliquez sur le champ de la colonne **Colonne** et sélectionnez un nom de colonne dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="93463-113">In the **Criteria Pane**, move to the first blank grid row, click the field in the **Column** column, and select a column name from the drop-down list.</span></span>  
  
### <a name="to-add-all-columns-for-one-table-or-table-valued-object"></a><span data-ttu-id="93463-114">Pour ajouter toutes les colonnes d'une table ou d'un objet table</span><span class="sxs-lookup"><span data-stu-id="93463-114">To add all columns for one table or table-valued object</span></span>  
  
-   <span data-ttu-id="93463-115">Dans le **volet Schéma**, activez la case à cocher en regard de \*\* \* (toutes les colonnes)\*\*.</span><span class="sxs-lookup"><span data-stu-id="93463-115">In the **Diagram Pane**, select the check box next to **\*(All Columns)**.</span></span>  
  
### <a name="to-add-all-columns-for-all-tables-and-table-structured-objects"></a><span data-ttu-id="93463-116">Pour ajouter toutes les colonnes de l'ensemble des tables ou des objets structurés comme des tables</span><span class="sxs-lookup"><span data-stu-id="93463-116">To add all columns for all tables and table-structured objects</span></span>  
  
1.  <span data-ttu-id="93463-117">Vérifiez qu’aucune ligne de jointure n’est sélectionnée dans le volet **Table Operations** (Opérations sur les tables).</span><span class="sxs-lookup"><span data-stu-id="93463-117">Make sure no join lines in the **Table Operations Pane** are selected.</span></span>  
  
2.  <span data-ttu-id="93463-118">Cliquez avec le bouton droit dans l’espace vide de la fenêtre Design et sélectionnez **Propriétés** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="93463-118">Right-click in the empty space of the Design window and choose **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="93463-119">Dans la fenêtre Propriétés, cliquez sur **Sélectionne toutes les colonnes** et choisissez **Oui** ou **Non** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="93463-119">In the Properties window click **Output all columns** and choose **Yes** or **No** from the dropdown list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93463-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93463-120">See Also</span></span>  
 <span data-ttu-id="93463-121">[Supprimer des colonnes des résultats de la requête &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="93463-121">[Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="93463-122">[Supprimer des colonnes des requêtes &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="93463-122">[Remove Columns from Queries &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="93463-123">[Spécifier les critères de recherche &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="93463-123">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="93463-124">[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="93463-124">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="93463-125">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="93463-125">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
