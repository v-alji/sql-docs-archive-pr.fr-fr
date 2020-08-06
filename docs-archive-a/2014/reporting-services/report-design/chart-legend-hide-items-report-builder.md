---
title: Masquer des éléments de légende dans le graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92256240-0cd5-4be4-8904-d1e3b93cb6b3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 20444432f580ffaf1c5f4de1320b06319f973a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613313"
---
# <a name="hide-legend-items-on-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="c4eaa-102">Masquer des éléments de légende dans le graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="c4eaa-102">Hide Legend Items on the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c4eaa-103">Par défaut, toute série ajoutée à un graphique qui n'est pas à base de formes sera ajoutée en tant qu'élément à la légende.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-103">By default, any series added to a non-Shape chart will be added as an item in the legend.</span></span> <span data-ttu-id="c4eaa-104">Pour les graphiques à secteurs, en anneau, en entonnoir et en pyramide, toute série ajoutée au graphique ajoutera des points de données individuels à la légende.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-104">For pie, doughnut, funnel, and pyramid charts, any series added to the chart will add individual data points in the legend.</span></span>  
  
 <span data-ttu-id="c4eaa-105">Vous pouvez masquer tout élément de la légende.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-105">You can hide any item on the legend.</span></span> <span data-ttu-id="c4eaa-106">Lorsque vous masquez un élément de légende, celui-ci continuera à figurer dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-106">When you hide a legend item, it will still appear in the chart.</span></span> <span data-ttu-id="c4eaa-107">Cela peut s'avérer utile dans les cas où vous ne souhaiteriez pas afficher plus d'informations sur une série ajoutée au graphique.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-107">This is useful in situations where you do not want to show more information for a series that is added to the chart.</span></span> <span data-ttu-id="c4eaa-108">Par exemple, si vous avez ajouté une série calculée comme une moyenne mobile au graphique, vous pouvez masquer cette entrée dans la légende de manière à afficher davantage d'informations sur la série d'origine uniquement.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-108">For example, if you have added a calculated series like a moving average to the chart, you may want to hide this entry in the legend so that more information is only shown for the original series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-an-item-from-display-in-the-legend"></a><span data-ttu-id="c4eaa-109">Pour masquer un élément dans la légende</span><span class="sxs-lookup"><span data-stu-id="c4eaa-109">To hide an item from display in the legend</span></span>  
  
1.  <span data-ttu-id="c4eaa-110">Cliquez avec le bouton droit sur la série que vous souhaitez masquer et sélectionnez **Propriétés de la série**.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-110">Right-click on the series you want to hide and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="c4eaa-111">Cliquez sur **Légende**.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-111">Click **Legend**.</span></span> <span data-ttu-id="c4eaa-112">Sélectionnez l'option **Ne pas afficher cette série dans une légende** .</span><span class="sxs-lookup"><span data-stu-id="c4eaa-112">Select the **Do not show this series in a legend** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4eaa-113">Vous ne pouvez pas masquer une série d'un groupe et pas des autres.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-113">You cannot hide a series for one group and not for the others.</span></span> <span data-ttu-id="c4eaa-114">Si vous avez ajouté un champ à la zone **Groupes de séries** , toutes les séries qui appartiennent à ce groupe seront masquées.</span><span class="sxs-lookup"><span data-stu-id="c4eaa-114">If you have added a field to the **Series Groups** area, all series belonging to this group will be hidden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4eaa-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4eaa-115">See Also</span></span>  
 <span data-ttu-id="c4eaa-116">[Mise en forme de la légende sur un graphique &#40;Générateur de rapports et SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c4eaa-116">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="c4eaa-117">[Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4eaa-117">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c4eaa-118">[Modifier le texte d’un élément de légende &#40;Générateur de rapports et SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c4eaa-118">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="c4eaa-119">[Ajouter une moyenne mobile à un graphique &#40;Générateur de rapports et SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4eaa-119">[Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c4eaa-120">Boîte de dialogue Propriétés de la légende, Général &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c4eaa-120">Legend Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../legend-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
