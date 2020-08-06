---
title: Synthétiser ou agréger des valeurs à l’aide d’expressions personnalisées (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- custom expressions to aggregate values [SQL Server]
ms.assetid: 34130ac1-0106-4766-b324-acb0b7bb6f6e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9f03f82842178a68c8a3d04ebc1bd738c0ab0b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704623"
---
# <a name="summarize-or-aggregate-values-using-custom-expressions-visual-database-tools"></a><span data-ttu-id="ced0d-102">Synthétiser ou regrouper des valeurs à l'aide d'expressions personnalisées (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ced0d-102">Summarize or Aggregate Values Using Custom Expressions (Visual Database Tools)</span></span>
  <span data-ttu-id="ced0d-103">Si vous pouvez utiliser des fonctions d'agrégation pour agréger des données, vous pouvez également créer des expressions personnalisées afin de générer des valeurs agrégées.</span><span class="sxs-lookup"><span data-stu-id="ced0d-103">In addition to using aggregate functions to aggregate data, you can create custom expressions to produce aggregate values.</span></span> <span data-ttu-id="ced0d-104">Il est possible d'utiliser des expressions personnalisées à la place de fonctions d'agrégation dans une requête Agrégation.</span><span class="sxs-lookup"><span data-stu-id="ced0d-104">You can use custom expressions in place of aggregate functions anywhere in an aggregate query.</span></span>  
  
 <span data-ttu-id="ced0d-105">Imaginons que, dans la table `titles` , vous souhaitiez créer une requête qui affiche non seulement le prix moyen mais aussi ce même prix assorti d'une ristourne.</span><span class="sxs-lookup"><span data-stu-id="ced0d-105">For example, in the `titles` table you might want to create a query that shows not just the average price, but what the average price would be if it were discounted.</span></span>  
  
 <span data-ttu-id="ced0d-106">Il est impossible d'inclure une expression basée sur des calculs portant sur des lignes individuelles de la table ; l'expression doit être fondée sur une valeur agrégée dans la mesure où seules les valeurs agrégées sont disponibles au moment du calcul de l'expression.</span><span class="sxs-lookup"><span data-stu-id="ced0d-106">You cannot include an expression that is based on calculations involving only individual rows in the table; the expression must be based on an aggregate value, because only the aggregate values are available at the time the expression is calculated.</span></span>  
  
### <a name="to-specify-a-custom-expression-for-a-summary-value"></a><span data-ttu-id="ced0d-107">Pour spécifier une expression personnalisée pour une valeur de synthèse</span><span class="sxs-lookup"><span data-stu-id="ced0d-107">To specify a custom expression for a summary value</span></span>  
  
1.  <span data-ttu-id="ced0d-108">Spécifiez les groupes de votre requête.</span><span class="sxs-lookup"><span data-stu-id="ced0d-108">Specify the groups for your query.</span></span> <span data-ttu-id="ced0d-109">Pour plus d’informations, consultez [Regrouper des lignes dans les résultats de requête &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ced0d-109">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="ced0d-110">Placez-vous dans une ligne vide du volet Critères et tapez ensuite l’expression dans la colonne **Colonnes**.</span><span class="sxs-lookup"><span data-stu-id="ced0d-110">Move to a blank row of the Criteria pane, and then type the expression in the **Columns** column.</span></span>  
  
     <span data-ttu-id="ced0d-111">Le [Concepteur de requêtes et de vues](query-and-view-designer-tools-visual-database-tools.md) assigne automatiquement un alias de colonne à l’expression afin de créer un en-tête de colonne pertinent dans le résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="ced0d-111">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically assigns a column alias to the expression to create a useful column heading in query output.</span></span> <span data-ttu-id="ced0d-112">Pour plus d’informations, consultez [Créer des alias de colonnes &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ced0d-112">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
3.  <span data-ttu-id="ced0d-113">Dans la colonne **Grouper par** de l’expression, sélectionnez **Expression**.</span><span class="sxs-lookup"><span data-stu-id="ced0d-113">In the **Group By** column for the expression, select **Expression**.</span></span>  
  
4.  <span data-ttu-id="ced0d-114">Exécute la requête.</span><span class="sxs-lookup"><span data-stu-id="ced0d-114">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced0d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ced0d-115">See Also</span></span>  
 <span data-ttu-id="ced0d-116">[Trier et regrouper les résultats des requêtes &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ced0d-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ced0d-117">Résumer les résultats de la requête &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ced0d-117">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
