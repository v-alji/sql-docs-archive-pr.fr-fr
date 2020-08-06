---
title: Trier par ordre croissant ou décroissant (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- descending sorts
- ascending sorts
ms.assetid: d61cc55b-9ee8-4ecf-a32f-6459ae43910b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b5e6b00f62cfc297cc5930bc8cf3a41314a2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613736"
---
# <a name="sort-in-ascending-or-descending-order-visual-database-tools"></a><span data-ttu-id="40641-102">Trier par ordre croissant ou décroissant (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="40641-102">Sort in Ascending or Descending Order (Visual Database Tools)</span></span>
  <span data-ttu-id="40641-103">Vous pouvez trier des résultats de requête par ordre croissant ou décroissant sur une ou plusieurs des colonnes dans le jeu de résultats en utilisant les mots clés `ASC` ou `DESC` avec la clause `ORDER BY`</span><span class="sxs-lookup"><span data-stu-id="40641-103">You can sort query results in ascending or descending order on one or more of the columns in the result set by using the `ASC` or `DESC` keywords with the `ORDER BY` clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40641-104">L'ordre de tri est déterminé en partie par la séquence de classement de la colonne.</span><span class="sxs-lookup"><span data-stu-id="40641-104">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="40641-105">Vous pouvez modifier cette séquence dans la [boîte de dialogue Classement](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="40641-105">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="40641-106">La procédure suivante suppose que vous ayez une requête ouverte dans le Concepteur de requêtes et de vues qui utilise la clause ORDER BY pour trier une ou plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="40641-106">The following procedure assumes that you have a query open in Query and View Designer that uses the ORDER BY clause to sort one or more columns.</span></span>  
  
### <a name="to-specify-or-change-the-order-in-which-results-are-sorted"></a><span data-ttu-id="40641-107">Pour spécifier ou modifier l'ordre dans lequel les résultats sont triés</span><span class="sxs-lookup"><span data-stu-id="40641-107">To specify or change the order in which results are sorted</span></span>  
  
1.  <span data-ttu-id="40641-108">Dans le [volet Critères](criteria-pane-visual-database-tools.md), cliquez sur le champ **Type de tri** pour la colonne que vous souhaitez réorganiser.</span><span class="sxs-lookup"><span data-stu-id="40641-108">In the [Criteria pane](criteria-pane-visual-database-tools.md), click the **Sort Type** field for the column that you want to reorder.</span></span>  
  
2.  <span data-ttu-id="40641-109">Choisissez **Croissant** ou **Décroissant** pour spécifier l'ordre de tri pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="40641-109">Choose **Ascending** or **Descending** to specify the sort order for the column.</span></span>  
  
 <span data-ttu-id="40641-110">Remarquez qu'au fur et à mesure que vous travaillez dans le volet Critères, la clause UNION de votre requête se modifie pour correspondre à vos actions les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="40641-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40641-111">Lorsque vous triez des résultats par plusieurs colonnes, spécifiez l'ordre dans lequel la recherche doit être effectuée à l'aide de la colonne Ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="40641-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the Sort Order column.</span></span> <span data-ttu-id="40641-112">Pour plus d’informations, consultez [Trier plusieurs colonnes dans des requêtes &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="40641-112">For more information, see [Sort Multiple Columns in Queries &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40641-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40641-113">See Also</span></span>  
 <span data-ttu-id="40641-114">[Trier et regrouper les résultats des requêtes &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="40641-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="40641-115">[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="40641-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="40641-116">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="40641-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
