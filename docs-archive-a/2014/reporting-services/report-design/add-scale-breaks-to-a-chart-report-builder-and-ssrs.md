---
title: Ajouter des séparations d’échelle à un graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 84d66436-ed62-4967-bbbd-b457593ee787
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1c081debd1e0a84158615edebdb6b84705c10e5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703856"
---
# <a name="add-scale-breaks-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="f2ab3-102">Ajouter des séparations d'échelle à un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="f2ab3-102">Add Scale Breaks to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f2ab3-103">Une séparation d'échelle est une ligne dessinée sur la zone de traçage d'un graphique pour indiquer une rupture dans la continuité entre les valeurs haute et basse d'un axe des ordonnées (en général, l'axe vertical ou axe des Y).</span><span class="sxs-lookup"><span data-stu-id="f2ab3-103">A scale break is a stripe drawn across the plotting area of a chart to denote a break in continuity between the high and low values on a value axis (usually the vertical, or y-axis).</span></span> <span data-ttu-id="f2ab3-104">Utilisez une séparation d'échelle pour afficher deux plages distinctes dans la même zone de graphique.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-104">Use a scale break to display two distinct ranges in the same chart area.</span></span>  
  
 <span data-ttu-id="f2ab3-105">![Graphique avec changement d'échelle](../media/rs-multipledatarangeschart-scalebreak.gif "Graphique avec changement d'échelle")</span><span class="sxs-lookup"><span data-stu-id="f2ab3-105">![Chart with scale break](../media/rs-multipledatarangeschart-scalebreak.gif "Chart with scale break")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2ab3-106">Vous ne pouvez pas spécifier où placer une séparation d'échelle sur votre graphique.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-106">You cannot specify where to place a scale break on your chart.</span></span> <span data-ttu-id="f2ab3-107">Le graphique utilise ses propres calculs en fonction des valeurs de votre dataset pour déterminer si l'écart entre les différentes plages de données est suffisant pour dessiner une séparation d'échelle sur l'axe des ordonnées (axe Y) au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-107">The chart uses its own calculations based on the values in your dataset to determine whether there is sufficient separation between data ranges to draw a scale break on the value axis (y-axis) at run time.</span></span>  
  
 <span data-ttu-id="f2ab3-108">Un exemple de graphique avec séparations d’échelle est disponible sous forme d’exemple de rapport.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-108">An example of a chart with scale breaks is available as a sample report.</span></span> <span data-ttu-id="f2ab3-109">Pour plus d'informations sur le téléchargement de cet exemple de rapport et d'autres rapports, consultez [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Exemples de rapports du Générateur de rapports et du Concepteur de rapports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="f2ab3-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-scale-breaks-on-the-chart"></a><span data-ttu-id="f2ab3-110">Pour activer les séparations d'échelle sur le graphique</span><span class="sxs-lookup"><span data-stu-id="f2ab3-110">To enable scale breaks on the chart</span></span>  
  
1.  <span data-ttu-id="f2ab3-111">Cliquez avec le bouton droit sur l’axe vertical, puis cliquez sur **Propriétés de l’axe**.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-111">Right-click the vertical axis and then click **Axis Properties**.</span></span> <span data-ttu-id="f2ab3-112">La boîte de dialogue **Propriétés de l’axe vertical** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-112">The **VerticalAxis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="f2ab3-113">Cochez la case **Activer les séparateurs d’échelle** .</span><span class="sxs-lookup"><span data-stu-id="f2ab3-113">Select the **Enable scale breaks** check box.</span></span>  
  
### <a name="to-change-the-style-of-the-scale-break"></a><span data-ttu-id="f2ab3-114">Pour modifier le style de la séparation d'échelle</span><span class="sxs-lookup"><span data-stu-id="f2ab3-114">To change the style of the scale break</span></span>  
  
1.  <span data-ttu-id="f2ab3-115">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-115">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="f2ab3-116">Dans l'aire de conception, cliquez avec le bouton droit sur l'axe Y du graphique.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-116">On the design surface, right-click on the y-axis of the chart.</span></span> <span data-ttu-id="f2ab3-117">Les propriétés de l'objet de l'axe Y (nommé Axe de graphique par défaut) sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-117">The properties for the y-axis object (named Chart Axis by default) are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="f2ab3-118">Dans la section **Échelle** , développez la propriété ScaleBreakStyle.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-118">In the **Scale** section, expand the ScaleBreakStyle property.</span></span>  
  
4.  <span data-ttu-id="f2ab3-119">Modifier les valeurs de la propriété ScaleBreakStyle, telles que BreakLineType et Spacing.</span><span class="sxs-lookup"><span data-stu-id="f2ab3-119">Change the values for ScaleBreakStyle properties, such as BreakLineType and Spacing.</span></span> <span data-ttu-id="f2ab3-120">Pour plus d’informations sur les propriétés des séparations d’échelle, consultez, [Affichage d’une série avec plusieurs plages de données sur un graphique &#40;Générateur de rapports et SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span><span class="sxs-lookup"><span data-stu-id="f2ab3-120">For more information about scale break properties, see [Displaying a Series with Multiple Data Ranges on a Chart &#40;Report Builder and SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ab3-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2ab3-121">See Also</span></span>  
 <span data-ttu-id="f2ab3-122">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2ab3-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f2ab3-123">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2ab3-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f2ab3-124">Boîte de dialogue Propriétés de l’axe, Options de l’axe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f2ab3-124">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
