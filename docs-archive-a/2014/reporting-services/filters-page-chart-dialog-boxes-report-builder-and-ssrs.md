---
title: Page filtres, boîtes de dialogue graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.categorygroupproperties.filters.f1
- "10409"
- sql12.rtp.rptdesigner.seriesgroupproperties.filters.f1
- "10401"
- sql12.rtp.rptdesigner.chartproperties.filters.f1
- "10165"
ms.assetid: fab97b2f-d53f-42f2-900c-c159653d89ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01d5054ce7d0c3e02d960885f149bd0ef209dc34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700854"
---
# <a name="filters-page-chart-dialog-boxes-report-builder-and-ssrs"></a><span data-ttu-id="7f391-102">Page Filtres, boîtes de dialogue Graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="7f391-102">Filters page, Chart Dialog Boxes (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7f391-103">Cliquez sur **filtres** dans :</span><span class="sxs-lookup"><span data-stu-id="7f391-103">Click **Filters** in the:</span></span>  
  
-   <span data-ttu-id="7f391-104">la boîte de dialogue**Propriétés du groupe de catégories** pour filtrer les points de données dans une série regroupée par catégorie ;</span><span class="sxs-lookup"><span data-stu-id="7f391-104">**Category Group Properties** dialog box to filter data points in a series that has been grouped by category.</span></span>  
  
-   <span data-ttu-id="7f391-105">la boîte de dialogue**Propriétés du graphique** pour définir les options de filtrage du graphique ;</span><span class="sxs-lookup"><span data-stu-id="7f391-105">**Chart Properties** dialog box to define filtering options for the chart.</span></span>  
  
-   <span data-ttu-id="7f391-106">la boîte de dialogue**Propriétés du groupe de séries** pour limiter le nombre de séries dans le groupe sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7f391-106">**Series Group Properties** dialog box to limit the number of series in the selected group.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f391-107">Options</span><span class="sxs-lookup"><span data-stu-id="7f391-107">Options</span></span>  
 <span data-ttu-id="7f391-108">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="7f391-108">**Add**</span></span>  
 <span data-ttu-id="7f391-109">Cliquez pour ajouter une nouvelle clause de filtre à la liste.</span><span class="sxs-lookup"><span data-stu-id="7f391-109">Click to add a new filter clause to the list.</span></span>  
  
 <span data-ttu-id="7f391-110">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="7f391-110">**Delete**</span></span>  
 <span data-ttu-id="7f391-111">Cliquez pour supprimer la clause de filtre sélectionnée de la liste.</span><span class="sxs-lookup"><span data-stu-id="7f391-111">Click to delete the selected filter clause from the list.</span></span>  
  
 <span data-ttu-id="7f391-112">**Flèche haut**</span><span class="sxs-lookup"><span data-stu-id="7f391-112">**Up arrow**</span></span>  
 <span data-ttu-id="7f391-113">Cliquez pour déplacer le filtre sélectionné vers le haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="7f391-113">Click to move the selected filter up in the list.</span></span>  
  
 <span data-ttu-id="7f391-114">**Flèche bas**</span><span class="sxs-lookup"><span data-stu-id="7f391-114">**Down arrow**</span></span>  
 <span data-ttu-id="7f391-115">Cliquez pour déplacer le filtre sélectionné vers le bas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="7f391-115">Click to move the selected filter down in the list.</span></span>  
  
 <span data-ttu-id="7f391-116">**Expression**</span><span class="sxs-lookup"><span data-stu-id="7f391-116">**Expression**</span></span>  
 <span data-ttu-id="7f391-117">Tapez ou choisissez l'expression à laquelle vous souhaitez appliquer un filtre.</span><span class="sxs-lookup"><span data-stu-id="7f391-117">Type or choose the expression to which you want to apply a filter.</span></span> <span data-ttu-id="7f391-118">Cliquez sur le bouton Expression (**fx**) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="7f391-118">Click the Expression (**fx**) button to edit the expression.</span></span>  
  
 <span data-ttu-id="7f391-119">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="7f391-119">**Data type**</span></span>  
 <span data-ttu-id="7f391-120">Sélectionnez le type de données du champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="7f391-120">Choose the data type for **Value**.</span></span> <span data-ttu-id="7f391-121">Lorsque cela est possible, sélectionnez un type de données correspondant à celui du champ **Expression**.</span><span class="sxs-lookup"><span data-stu-id="7f391-121">When possible, choose a data type that matches the data type for **Expression**.</span></span>  
  
 <span data-ttu-id="7f391-122">Les valeurs dans **Expression** et **Valeur** doivent s’évaluer au même type de données.</span><span class="sxs-lookup"><span data-stu-id="7f391-122">The values in **Expression** and **Value** must evaluate to the same data type.</span></span> <span data-ttu-id="7f391-123">Par exemple, si **Expression** a pour valeur un champ du type de données System.Int32 et que **Valeur** a pour valeur 7, sélectionnez **Entier**dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="7f391-123">For example, if **Expression** is set to a field that has the data type System.Int32 and **Value** is set to 7, from the drop-down list, choose **Integer**.</span></span>  
  
 <span data-ttu-id="7f391-124">Si le type de données recherché ne figure pas dans la liste déroulante, écrivez une expression permettant de convertir la valeur en type de données correct.</span><span class="sxs-lookup"><span data-stu-id="7f391-124">If the data type option you need is not in the drop-down list, write an expression to convert the value to the correct data type.</span></span> <span data-ttu-id="7f391-125">Pour plus d’informations, consultez [Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7f391-125">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="7f391-126">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="7f391-126">**Operator**</span></span>  
 <span data-ttu-id="7f391-127">Choisissez l'opérateur à utiliser pour comparer l'expression et la valeur.</span><span class="sxs-lookup"><span data-stu-id="7f391-127">Choose the operator to use to compare the expression and the value.</span></span>  
  
 <span data-ttu-id="7f391-128">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="7f391-128">**Value**</span></span>  
 <span data-ttu-id="7f391-129">Tapez l’expression ou la valeur à comparer au contenu de l’expression dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="7f391-129">Type the expression or value against which to evaluate the expression in **Expression**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f391-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f391-130">See Also</span></span>  
 <span data-ttu-id="7f391-131">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupe &#40;Générateur de rapports et SSRS&#41;](report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="7f391-131">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="7f391-132">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f391-132">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7f391-133">[Expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f391-133">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7f391-134">Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7f391-134">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
