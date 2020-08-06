---
title: Mise en forme d’un graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10214"
- sql12.rtp.rptdesigner.calculatedseriesproperties.fill.f1
- sql12.rtp.rptdesigner.serieslabelproperties.fill.f1
- sql12.rtp.rptdesigner.legendproperties.fill.f1
- "10149"
- sql12.rtp.rptdesigner.seriesproperties.shadow.f1
- sql12.rtp.rptdesigner.seriesproperties.markers.f1
- "10255"
- sql12.rtp.rptdesigner.charttitleproperties.fill.f1
- "10154"
- "10170"
- "10173"
- sql12.rtp.rptdesigner.seriesproperties.fill.f1
- "10169"
- "10158"
- sql12.rtp.rptdesigner.chartareaproperties.fill.f1
- sql12.rtp.rptdesigner.charttitleproperties.shadow.f1
- "10246"
- "10150"
- sql12.rtp.rptdesigner.calculatedseriesproperties.borders.f1
- sql12.rtp.rptdesigner.chartproperties.fill.f1
- "10159"
- sql12.rtp.rptdesigner.majorgridlineproperties.gridlineoptions.f1
- "10160"
- sql12.rtp.rptdesigner.serieslabelproperties.font.f1
- "10182"
- "10163"
- "10164"
- "10253"
- "10216"
- "10171"
- "10257"
- sql12.rtp.rptdesigner.chartareaproperties.border.f1
- sql12.rtp.rptdesigner.calculatedseriesproperties.shadow.f1
- sql12.rtp.rptdesigner.chartproperties.border.f1
- sql12.rtp.rptdesigner.minorgridlineproperties.gridlineoptions.f1
- sql12.rtp.rptdesigner.chartareaproperties.shadow.f1
- sql12.rtp.rptdesigner.charttitleproperties.borders.f1
- sql12.rtp.rptdesigner.charttitleproperties.font.f1
- "10247"
ms.assetid: d3984300-c766-42f8-b7c4-863123d67c99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af164d4db9b6439f0634d113652b95939827b0f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603834"
---
# <a name="formatting-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="9243b-102">Mise en forme d'un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="9243b-102">Formatting a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9243b-103">Après avoir défini les données et l'aspect de votre graphique, vous pouvez ajouter une mise en forme pour améliorer l'apparence globale et mettre en évidence les principaux points de données.</span><span class="sxs-lookup"><span data-stu-id="9243b-103">After you have defined the data for your chart and it is appearing the way you want, you can add formatting to improve the overall appearance and highlight key data points.</span></span> <span data-ttu-id="9243b-104">Les options de mise en forme les plus courantes peuvent être modifiées dans la boîte de dialogue Propriétés qui apparaît lorsque vous cliquez avec le bouton droit sur un élément de graphique pour afficher son menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="9243b-104">The most common formatting options can be modified from the Properties dialog box that are found when you right-click a chart element to display its shortcut menu.</span></span> <span data-ttu-id="9243b-105">Chaque élément de graphique possède sa propre boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9243b-105">Each chart element has its own dialog box.</span></span> <span data-ttu-id="9243b-106">Pour plus d’informations sur les éléments des graphiques, consultez [Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9243b-106">For more information about chart elements, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="9243b-107">Toutes les propriétés qui sont en rapport avec le graphique figurent dans le volet Propriétés, mais un grand nombre de ces propriétés peuvent également être définies dans une boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9243b-107">All properties that relate to the chart are located in the Properties pane, but many of these properties can also be set from a dialog box.</span></span> <span data-ttu-id="9243b-108">Si vous mettez en forme la série, vous pouvez spécifier des propriétés spécifiques à la série en utilisant des attributs personnalisés, qui se trouvent uniquement dans la catégorie de propriétés **CustomAttributes** , dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="9243b-108">If you are formatting the series, you can specify series-specific properties using custom attributes, which can only be found in the **CustomAttributes** category of properties, located in the Properties pane.</span></span>  
  
 <span data-ttu-id="9243b-109">Pour mettre en forme efficacement le graphique en un minimum d'étapes, modifiez le style de bordure, la palette et style de dessin par défaut.</span><span class="sxs-lookup"><span data-stu-id="9243b-109">To effectively format the chart using a minimal number of steps, change the default border style, palette and drawing style.</span></span> <span data-ttu-id="9243b-110">Ces trois fonctionnalités produisent la modification la plus visible sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="9243b-110">These three features produce the largest visible change on the chart.</span></span> <span data-ttu-id="9243b-111">Les styles de dessin s'appliquent uniquement aux histogrammes, graphiques à barres, graphiques en anneau et graphiques à secteurs.</span><span class="sxs-lookup"><span data-stu-id="9243b-111">Drawing styles are only applicable to pie, doughnut, bar and column charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="9243b-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9243b-112">In This Section</span></span>  
 [<span data-ttu-id="9243b-113">Mise en forme des couleurs des séries sur un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9243b-113">Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="9243b-114">Explique comment les couleurs sont définies à l'aide d'une palette, comment vous pouvez définir votre propre palette de couleurs et comment définir des couleurs selon une expression.</span><span class="sxs-lookup"><span data-stu-id="9243b-114">Discusses how colors are defined using a palette, how you can define your own color palette, and how to define colors based on an expression.</span></span>  
  
 [<span data-ttu-id="9243b-115">Mise en forme des étiquettes des axes sur un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9243b-115">Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="9243b-116">Explique comment afficher un quadrillage, des graduations et des titres, et comment mettre en forme des nombres et des dates sur l'échelle des axes.</span><span class="sxs-lookup"><span data-stu-id="9243b-116">Discusses how to display gridlines, tick marks, and titles, and how to format numbers and dates on the axis scale.</span></span>  
  
 [<span data-ttu-id="9243b-117">Mise en forme de la légende sur un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9243b-117">Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-formatting-report-builder.md)  
 <span data-ttu-id="9243b-118">Explique comment reclasser et mettre en forme des éléments dans la légende de graphique.</span><span class="sxs-lookup"><span data-stu-id="9243b-118">Discusses how to re-order and format items in the chart legend.</span></span>  
  
 [<span data-ttu-id="9243b-119">Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9243b-119">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="9243b-120">Explique comment placer des étiquettes de points de données et mettre en forme des marqueurs de points de données pour chaque série sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="9243b-120">Discusses how to position data point labels and format data point markers for every series on the chart.</span></span>  
  
 [<span data-ttu-id="9243b-121">Effets 3D, de biseau et autres dans un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9243b-121">3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-3d-bevel-and-other-report-builder.md)  
 <span data-ttu-id="9243b-122">Décrit différents effets 3D que vous pouvez appliquer à un graphique.</span><span class="sxs-lookup"><span data-stu-id="9243b-122">Discusses various 3D effects that you can apply to a chart.</span></span>  
  
 [<span data-ttu-id="9243b-123">Ajouter un cadre de bordure à un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9243b-123">Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="9243b-124">Explique comment ajouter un cadre de bordure à un graphique.</span><span class="sxs-lookup"><span data-stu-id="9243b-124">Explains how to add a border frame to a chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9243b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9243b-125">See Also</span></span>  
 <span data-ttu-id="9243b-126">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9243b-126">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9243b-127">[Ajouter un cadre de bordure à un graphique &#40;Générateur de rapports et SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9243b-127">[Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9243b-128">[Définir les couleurs d’un graphique à l’aide d’une palette &#40;Générateur de rapports et SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9243b-128">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9243b-129">Ajouter des styles de biseau, de relief et de texture à un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9243b-129">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
