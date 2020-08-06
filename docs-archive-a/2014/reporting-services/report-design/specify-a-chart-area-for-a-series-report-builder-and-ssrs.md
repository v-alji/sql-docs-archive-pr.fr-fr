---
title: Spécifier une zone de graphique pour une série (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10157"
- sql12.rtp.rptdesigner.chartareaproperties.alignment.f1
ms.assetid: dc3c365b-c263-402a-bf6f-c2a7081db073
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 483bc6d2fa4aa079c95e9dbd03e18c71d7b13abf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600521"
---
# <a name="specify-a-chart-area-for-a-series-report-builder-and-ssrs"></a><span data-ttu-id="28f93-102">Spécifier une zone de graphique pour une série (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="28f93-102">Specify a Chart Area for a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="28f93-103">Le graphique est le conteneur de niveau supérieur qui inclut la bordure externe, le titre du graphique et la légende.</span><span class="sxs-lookup"><span data-stu-id="28f93-103">The chart is the top-level container that includes the outer border, the chart title, and the legend.</span></span> <span data-ttu-id="28f93-104">Par défaut, le graphique contient une zone de graphique par défaut.</span><span class="sxs-lookup"><span data-stu-id="28f93-104">By default, the chart contains one default chart area.</span></span> <span data-ttu-id="28f93-105">La zone de graphique n'est pas visible à la surface du graphique, mais vous pouvez la considérer comme un conteneur qui comprend uniquement les étiquettes d'axe, le titre de l'axe et la zone de traçage d'une ou plusieurs série(s).</span><span class="sxs-lookup"><span data-stu-id="28f93-105">The chart area is not visible on the chart surface, but you can think of the chart area as a container that encompasses only the axis labels, the axis title and the plotting area of one or more series.</span></span> <span data-ttu-id="28f93-106">L'illustration suivante montre le concept de zones de graphique dans un unique graphique.</span><span class="sxs-lookup"><span data-stu-id="28f93-106">The following illustration shows the concept of chart areas within a single chart.</span></span>  
  
 <span data-ttu-id="28f93-107">![Affiche un diagramme d'une zone de graphique](../media/chartareasdiagram.gif "Affiche un diagramme d'une zone de graphique")</span><span class="sxs-lookup"><span data-stu-id="28f93-107">![Shows a diagram of a chart area](../media/chartareasdiagram.gif "Shows a diagram of a chart area")</span></span>  
  
 <span data-ttu-id="28f93-108">Par défaut, toutes les séries sont ajoutées à la zone de graphique par défaut.</span><span class="sxs-lookup"><span data-stu-id="28f93-108">By default, all series are added to the default chart area.</span></span> <span data-ttu-id="28f93-109">Lorsque vous utilisez des graphiques en aires, des histogrammes, des graphiques en courbes ou à nuages de points, vous pouvez afficher n'importe quelle combinaison de ces séries sur la même zone de graphique.</span><span class="sxs-lookup"><span data-stu-id="28f93-109">When using area, column, line, and scatter charts, any combination of these series can be displayed on the same chart area.</span></span> <span data-ttu-id="28f93-110">Plusieurs séries dans une même zone de graphique réduit la lisibilité du graphique.</span><span class="sxs-lookup"><span data-stu-id="28f93-110">If you have several series in the same chart area, the readability of the chart is reduced.</span></span> <span data-ttu-id="28f93-111">Il est donc recommandé de séparer les différents types de graphique en différentes zones.</span><span class="sxs-lookup"><span data-stu-id="28f93-111">You may want to separate the chart types into multiple chart areas.</span></span> <span data-ttu-id="28f93-112">L'utilisation de plusieurs zones de graphique améliore la lisibilité et facilite les comparaisons.</span><span class="sxs-lookup"><span data-stu-id="28f93-112">Using multiple chart areas will increase readability for easier comparisons.</span></span> <span data-ttu-id="28f93-113">Par exemple, les graphiques boursiers de type volume-prix présentent souvent des plages de valeurs différentes, mais des comparaisons peuvent être faites entre les données de prix et de volume sur une même période.</span><span class="sxs-lookup"><span data-stu-id="28f93-113">For example, price-volume stock charts often have different ranges of values, but comparisons can be made between the price and volume data over the same period of time.</span></span>  
  
 <span data-ttu-id="28f93-114">Une série de graphiques à barres, polaires ou à base de formes peut être combinée uniquement avec des graphiques de type identique dans une même zone de graphique.</span><span class="sxs-lookup"><span data-stu-id="28f93-114">The bar, polar, or shape series can only be combined with series of the same chart types in the same chart area.</span></span> <span data-ttu-id="28f93-115">Si vous utilisez un graphique polaire ou à base de formes, pensez à utiliser une région de données de graphique distincte pour chaque champ que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="28f93-115">If you are using a Polar or Shape chart, consider using a separate chart data region for each field that you wish to show.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-series-with-a-new-chart-area"></a><span data-ttu-id="28f93-116">Pour associer une série à une nouvelle zone de graphique</span><span class="sxs-lookup"><span data-stu-id="28f93-116">To associate a series with a new chart area</span></span>  
  
1.  <span data-ttu-id="28f93-117">Cliquez avec le bouton droit sur le graphique et sélectionnez **Ajouter une nouvelle zone graphique**.</span><span class="sxs-lookup"><span data-stu-id="28f93-117">Right-click anywhere on the chart and select **Add New Chart Area**.</span></span> <span data-ttu-id="28f93-118">Une nouvelle zone de graphique vide apparaît sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="28f93-118">A new, blank chart area appears on the chart.</span></span>  
  
2.  <span data-ttu-id="28f93-119">Cliquez avec le bouton droit sur la série dans le graphique, ou sur une série ou un champ de données dans la zone appropriée du volet Données du graphique, puis cliquez sur **Propriétés de la série**.</span><span class="sxs-lookup"><span data-stu-id="28f93-119">Right-click the series on the chart or right-click a series or data field in the appropriate area in the Chart Data pane, and then click **Series Properties**.</span></span>  
  
3.  <span data-ttu-id="28f93-120">Dans **Axes et zone de graphique**, sélectionnez la zone de graphique dans laquelle vous souhaitez afficher la série.</span><span class="sxs-lookup"><span data-stu-id="28f93-120">In **Axes and Chart Areas**, select the chart area that you want the series to be shown in.</span></span>  
  
4.  <span data-ttu-id="28f93-121">(Facultatif) Alignez les zones de graphique verticalement.</span><span class="sxs-lookup"><span data-stu-id="28f93-121">(Optional) Align the chart areas vertically.</span></span> <span data-ttu-id="28f93-122">Pour ce faire, cliquez avec le bouton droit sur le graphique et sélectionnez **Propriétés de la zone de graphique**.</span><span class="sxs-lookup"><span data-stu-id="28f93-122">To do this, right-click the chart and select **Chart Area Properties**.</span></span> <span data-ttu-id="28f93-123">Dans **Alignement**, sélectionnez une autre autre zone de graphique avec laquelle vous souhaitez aligner la zone de graphique sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28f93-123">In **Alignment**, select another chart area that you want to align the selected chart area with.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f93-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28f93-124">See Also</span></span>  
 <span data-ttu-id="28f93-125">[Plusieurs séries sur un graphique &#40;Générateur de rapports et SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28f93-125">[Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="28f93-126">[Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28f93-126">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="28f93-127">[Définir les couleurs d’un graphique à l’aide d’une palette &#40;Générateur de rapports et SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28f93-127">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="28f93-128">[Graphiques polaires &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28f93-128">[Polar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="28f93-129">[Graphiques à base de formes &#40;Générateur de rapports et SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28f93-129">[Shape Charts &#40;Report Builder and SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="28f93-130">Graphiques à secteurs (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="28f93-130">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](pie-charts-report-builder-and-ssrs.md)  
  
  
