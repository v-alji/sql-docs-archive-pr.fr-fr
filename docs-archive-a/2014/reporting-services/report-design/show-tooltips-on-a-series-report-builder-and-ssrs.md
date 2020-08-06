---
title: Afficher des info-bulles dans une série (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4c9606ff-e1c3-4cf7-a4e7-bb16f1a9e8ab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9113ec843b3b9255f380b17ee1ab6b360fa1f60d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613300"
---
# <a name="show-tooltips-on-a-series-report-builder-and-ssrs"></a><span data-ttu-id="c8730-102">Afficher des info-bulles dans une série (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="c8730-102">Show ToolTips on a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c8730-103">Vous pouvez ajouter une info-bulle à chaque point de données sur la série d'un graphique pour afficher des informations en rapport avec le point de données, par exemple, le nom du groupe, la valeur du point de données ou le pourcentage du point de données par rapport au total de la série lorsque les utilisateurs placent le pointeur sur le point de données dans un rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="c8730-103">You can add a ToolTip to each data point on the series of a chart to display information related to the data point, such as the group name, the value of the data point, or the percentage of the data point relative to the series total when users hover over the data point in a rendered report.</span></span>  
  
 <span data-ttu-id="c8730-104">Vous ne pouvez pas ajouter d'info-bulle à une série calculée.</span><span class="sxs-lookup"><span data-stu-id="c8730-104">You cannot add a ToolTip to a calculated series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-tooltip-on-each-data-point"></a><span data-ttu-id="c8730-105">Pour spécifier une info-bulle sur chaque point de données</span><span class="sxs-lookup"><span data-stu-id="c8730-105">To specify a ToolTip on each data point</span></span>  
  
1.  <span data-ttu-id="c8730-106">Cliquez avec le bouton droit sur la série ou sur le champ de la zone **Valeurs** et cliquez sur **Propriétés de la série**.</span><span class="sxs-lookup"><span data-stu-id="c8730-106">Right-click on the series or right-click on the field in the **Values** area, and click **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="c8730-107">Cliquez sur **Données de la série** puis, pour la propriété **ToolTip** , tapez une chaîne ou une expression.</span><span class="sxs-lookup"><span data-stu-id="c8730-107">Click **Series Data** and, for the **ToolTip** property, type in a string or expression.</span></span> <span data-ttu-id="c8730-108">Vous pouvez utiliser n'importe quel mot clé spécifique au graphique pour représenter un autre élément sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="c8730-108">You can use any chart-specific keyword to represent another element on the chart.</span></span> <span data-ttu-id="c8730-109">Pour plus d’informations, consultez [Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c8730-109">For more information, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8730-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c8730-110">See Also</span></span>  
 <span data-ttu-id="c8730-111">[Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c8730-111">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c8730-112">[Modifier le texte d’un élément de légende &#40;Générateur de rapports et SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c8730-112">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="c8730-113">[Mise en forme des couleurs des séries sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c8730-113">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c8730-114">Ajouter une action d’extraction à un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c8730-114">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
