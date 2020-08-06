---
title: Trier avec ORDER BY (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ORDER BY clause [Visual Database Tools]
ms.assetid: 459f5640-8058-4c24-97e7-7bbd6168bc39
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93bdb9ed01c7935c5b9dae543804fca758a9262d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705816"
---
# <a name="sort-with-order-by-visual-database-tools"></a><span data-ttu-id="2d95a-102">Trier avec ORDER BY (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2d95a-102">Sort with ORDER BY (Visual Database Tools)</span></span>
  <span data-ttu-id="2d95a-103">Vous pouvez trier les résultats d'une requête sur la base d'une ou plusieurs colonnes des lignes retournées à l'aide d'une clause ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="2d95a-103">You can sort query results by one or more of the columns in the returned rows by using an ORDER BY clause.</span></span> <span data-ttu-id="2d95a-104">Vous pouvez définir une clause ORDER BY en choisissant des options dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="2d95a-104">You can define an ORDER BY clause by choosing options in the Criteria Details pane.</span></span>  
  
### <a name="to-sort-a-query-using-an-order-by-clause"></a><span data-ttu-id="2d95a-105">Pour trier une requête à l'aide d'une clause ORDER BY</span><span class="sxs-lookup"><span data-stu-id="2d95a-105">To sort a query using an ORDER BY clause</span></span>  
  
1.  <span data-ttu-id="2d95a-106">Ouvrez une requête ou créez-en une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="2d95a-106">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="2d95a-107">Dans le [volet Critères](visual-database-tools.md), cliquez sur la colonne **Type de tri** pour la ligne correspondant à la colonne que vous souhaitez utiliser pour trier les résultats de votre requête.</span><span class="sxs-lookup"><span data-stu-id="2d95a-107">In the [Criteria Pane](visual-database-tools.md), click the **Sort Type** column for the row corresponding to the column that you want to use to sort your query results.</span></span>  
  
3.  <span data-ttu-id="2d95a-108">Choisissez *Croissant* ou *Décroissant* dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="2d95a-108">Choose *Ascending* or *Descending* from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d95a-109">Si vous désactivez l’entrée **Type de tri** d’une colonne, celle-ci est supprimée de la clause ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="2d95a-109">Clearing the **Sort Type** entry for a column removes that column from the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="2d95a-110">Remarquez qu'au fur et à mesure que vous travaillez dans le volet Critères, la clause UNION de votre requête se modifie pour correspondre à vos actions les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="2d95a-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d95a-111">Quand vous triez des résultats par plusieurs colonnes, spécifiez l’ordre dans lequel la recherche doit être effectuée à l’aide de la colonne **Ordre de tri** .</span><span class="sxs-lookup"><span data-stu-id="2d95a-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the **Sort Order** column.</span></span> <span data-ttu-id="2d95a-112">Pour plus d’informations, consultez **Procédure : tri de plusieurs colonnes dans des requêtes**.</span><span class="sxs-lookup"><span data-stu-id="2d95a-112">For more information, see **How to: Sort Multiple Columns in Queries**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d95a-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d95a-113">See Also</span></span>  
 <span data-ttu-id="2d95a-114">[Trier et regrouper les résultats des requêtes &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2d95a-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2d95a-115">[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2d95a-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="2d95a-116">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2d95a-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
