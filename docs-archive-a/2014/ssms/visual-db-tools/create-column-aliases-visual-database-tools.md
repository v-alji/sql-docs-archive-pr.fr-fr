---
title: Créer des alias de colonnes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], aliases
- aliases [SQL Server], columns
ms.assetid: e2e1c166-8ea7-47a2-b6a7-e419bf0fa3bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: febe7ed27ed10a283cab549bc65299577d69761c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603200"
---
# <a name="create-column-aliases-visual-database-tools"></a><span data-ttu-id="db380-102">Créer des alias de colonnes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="db380-102">Create Column Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="db380-103">Vous pouvez créer des alias pour les noms de colonnes, afin de faciliter l'utilisation des noms de colonnes, des calculs et des valeurs totalisées.</span><span class="sxs-lookup"><span data-stu-id="db380-103">You can create aliases for column names to make it easier to work with column names, calculations, and summary values.</span></span> <span data-ttu-id="db380-104">Vous pouvez, par exemple, créer un alias de colonne pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="db380-104">For example, you can create a column alias to:</span></span>  
  
-   <span data-ttu-id="db380-105">Créer un nom de colonne, tel que « Total Amount », pour une expression de type `(quantity * unit_price)` ou pour une fonction d'agrégation</span><span class="sxs-lookup"><span data-stu-id="db380-105">Create a column name, such as "Total Amount," for an expression such as `(quantity * unit_price)` or for an aggregate function.</span></span>  
  
-   <span data-ttu-id="db380-106">Créer un nom de colonne abrégé, tel que `"d_id"` pour `"discounts.stor_id."`</span><span class="sxs-lookup"><span data-stu-id="db380-106">Create a shortened form of a column name, such as `"d_id"` for `"discounts.stor_id."`</span></span>  
  
 <span data-ttu-id="db380-107">Lorsque vous avez défini un alias de colonne, vous pouvez utiliser cet alias dans une requête Select pour spécifier le résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="db380-107">After you have defined a column alias, you can use the alias in a Select query to specify query output.</span></span>  
  
### <a name="to-create-a-column-alias"></a><span data-ttu-id="db380-108">Pour créer un alias de colonne</span><span class="sxs-lookup"><span data-stu-id="db380-108">To create a column alias</span></span>  
  
1.  <span data-ttu-id="db380-109">Dans le **volet Critères**, recherchez la ligne comportant la colonne de données pour laquelle vous souhaitez créer un alias et spécifiez, si nécessaire, si vous souhaitez qu’elle figure dans les résultats.</span><span class="sxs-lookup"><span data-stu-id="db380-109">In the **Criteria Pane**, locate the row containing the data column for which you want to create an alias, and if necessary, mark it for output.</span></span> <span data-ttu-id="db380-110">Si la colonne de données ne figure pas encore dans la grille, ajoutez-la.</span><span class="sxs-lookup"><span data-stu-id="db380-110">If the data column is not already in the grid, add it.</span></span>  
  
2.  <span data-ttu-id="db380-111">Entrez l’alias dans la colonne **Alias** de cette ligne.</span><span class="sxs-lookup"><span data-stu-id="db380-111">In the **Alias** column for that row, enter the alias.</span></span> <span data-ttu-id="db380-112">L'alias doit respecter les conventions d'appellation du langage SQL.</span><span class="sxs-lookup"><span data-stu-id="db380-112">The alias must follow all naming conventions for SQL.</span></span> <span data-ttu-id="db380-113">Si le nom de l'alias entré comporte des espaces, le Concepteur de requêtes et de vues les entoure automatiquement à l'aide de délimiteurs.</span><span class="sxs-lookup"><span data-stu-id="db380-113">If the alias name you enter contains spaces, the Query and View Designer automatically puts delimiters around it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db380-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db380-114">See Also</span></span>  
 <span data-ttu-id="db380-115">[Ajouter des colonnes à des requêtes &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="db380-115">[Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="db380-116">[Trier et regrouper les résultats des requêtes &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="db380-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="db380-117">[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="db380-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="db380-118">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="db380-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
