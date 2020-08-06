---
title: Ajouter des points vides au graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2b056119-439f-494f-83cf-ee0c05dc6487
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 53d891c58210bcd51cd4e49f2f9a691a7729c884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706216"
---
# <a name="add-empty-points-to-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="4dc61-102">Ajouter des points vides au graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="4dc61-102">Add Empty Points to the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4dc61-103">Les valeurs Null sont affichées sur un graphique sous la forme d'espaces ou d'intervalles vides entre les points de données d'une série.</span><span class="sxs-lookup"><span data-stu-id="4dc61-103">Null values are shown on the chart as empty spaces or gaps between data points in a series.</span></span> <span data-ttu-id="4dc61-104">Les points vides sont des points de données qui peuvent être insérés dans l'espace vide créé par des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="4dc61-104">Empty points are data points that can be inserted in the empty space created by null values.</span></span>  
  
 <span data-ttu-id="4dc61-105">Par défaut, les points vides sont calculés en faisant la moyenne des points de données précédent et suivant qui contiennent une valeur.</span><span class="sxs-lookup"><span data-stu-id="4dc61-105">By default, empty points are calculated by taking the average of the previous and next data points that contain a value.</span></span> <span data-ttu-id="4dc61-106">Vous pouvez modifier ce comportement afin que tous les points vides soient insérés à zéro.</span><span class="sxs-lookup"><span data-stu-id="4dc61-106">You can change this so that all empty points are inserted at zero.</span></span>  
  
 <span data-ttu-id="4dc61-107">Pour plus d’informations, consultez [Points de données vides et Null dans les graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4dc61-107">For more information, see [Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-empty-points-on-a-chart"></a><span data-ttu-id="4dc61-108">Pour spécifier des points vides sur un graphique</span><span class="sxs-lookup"><span data-stu-id="4dc61-108">To specify empty points on a chart</span></span>  
  
1.  <span data-ttu-id="4dc61-109">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="4dc61-109">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="4dc61-110">Sur l'aire de conception, cliquez avec le bouton droit sur la série qui contient des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="4dc61-110">On the design surface, right-click the series that contains null values.</span></span> <span data-ttu-id="4dc61-111">Les propriétés de la série sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="4dc61-111">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="4dc61-112">Développez le nœud **EmptyPoint** .</span><span class="sxs-lookup"><span data-stu-id="4dc61-112">Expand the **EmptyPoint** node.</span></span>  
  
4.  <span data-ttu-id="4dc61-113">Sélectionnez une valeur de couleur pour la propriété Color.</span><span class="sxs-lookup"><span data-stu-id="4dc61-113">Select a color value for the Color property.</span></span>  
  
5.  <span data-ttu-id="4dc61-114">Dans le nœud **EmptyPoint** , développez le nœud Marqueur.</span><span class="sxs-lookup"><span data-stu-id="4dc61-114">In the **EmptyPoint** node, expand the Marker node.</span></span>  
  
6.  <span data-ttu-id="4dc61-115">Sélectionnez un type de marqueur pour la propriété MarkerType.</span><span class="sxs-lookup"><span data-stu-id="4dc61-115">Select a marker type for the MarkerType property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4dc61-116">Vous devez sélectionner un type de marqueur pour ajouter des points vides à un graphique à barres, à un histogramme ou un graphique à nuages de points.</span><span class="sxs-lookup"><span data-stu-id="4dc61-116">You must select a marker type to add empty points to a bar, column or scatter chart.</span></span> <span data-ttu-id="4dc61-117">Toutefois, la sélection d'un type de marqueur est facultative pour les graphiques en aires, en courbes et en radar, car le graphique remplit l'espace ou intervalle vide sans nécessiter la spécification d'un marqueur.</span><span class="sxs-lookup"><span data-stu-id="4dc61-117">However, for area, line and radar charts, selecting a marker type is optional because the chart fills in the empty space or gap without requiring a marker to be specified.</span></span>  
  
7.  <span data-ttu-id="4dc61-118">Définissez la valeur du point vide.</span><span class="sxs-lookup"><span data-stu-id="4dc61-118">Set the value of the empty point.</span></span>  
  
    1.  <span data-ttu-id="4dc61-119">Dans le volet Propriétés, développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="4dc61-119">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
    2.  <span data-ttu-id="4dc61-120">Définissez la propriété EmptyPointValue.</span><span class="sxs-lookup"><span data-stu-id="4dc61-120">Set the EmptyPointValue property.</span></span> <span data-ttu-id="4dc61-121">Pour insérer des points vides à une moyenne des points de données précédent et suivant, sélectionnez **Moyenne**.</span><span class="sxs-lookup"><span data-stu-id="4dc61-121">To insert empty points at an average of the previous and next data points, select **Average**.</span></span> <span data-ttu-id="4dc61-122">Pour insérer des points vides à zéro, sélectionnez **Zéro**.</span><span class="sxs-lookup"><span data-stu-id="4dc61-122">To insert empty points at zero, select **Zero**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc61-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4dc61-123">See Also</span></span>  
 <span data-ttu-id="4dc61-124">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupes &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="4dc61-124">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="4dc61-125">[Types de graphiques &#40;Générateur de rapports et SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4dc61-125">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4dc61-126">[Ajouter des séparateurs d’échelle à un graphique &#40;Générateur de rapports et SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4dc61-126">[Add Scale Breaks to a Chart &#40;Report Builder and SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4dc61-127">Graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="4dc61-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
