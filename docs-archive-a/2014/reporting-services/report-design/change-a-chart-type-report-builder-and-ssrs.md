---
title: Modifier un type de graphique (Générateur de rapports version et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fff24978-e3bd-4fac-8cd7-d6aa81f3cc25
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb466bed475b27206bf6837a60d0867f5fb745be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695407"
---
# <a name="change-a-chart-type-report-builder-and-ssrs"></a><span data-ttu-id="5c430-102">Modifier un type de graphique (Générateur de rapports version et SSRS)</span><span class="sxs-lookup"><span data-stu-id="5c430-102">Change a Chart Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5c430-103">Lorsque vous insérez un graphique dans un rapport pour la première fois, la boîte de dialogue **Sélectionner le type de graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="5c430-103">When you first insert a chart into a report, the **Select Chart Type** dialog appears.</span></span> <span data-ttu-id="5c430-104">Si vous annulez cette boîte de dialogue, un type d'histogramme est ajouté par défaut.</span><span class="sxs-lookup"><span data-stu-id="5c430-104">If you cancel this dialog, a Column chart type is added by default.</span></span>  
  
 <span data-ttu-id="5c430-105">À tout moment lors de la conception du rapport, vous pouvez remplacer le type de graphique par un type plus approprié au rapport.</span><span class="sxs-lookup"><span data-stu-id="5c430-105">At any point when designing the report, you can change the chart type to something more suitable to the report.</span></span> <span data-ttu-id="5c430-106">Il est important de sélectionner le type de graphique correct pour vos données afin qu'il puisse être interprété correctement.</span><span class="sxs-lookup"><span data-stu-id="5c430-106">It is important to select the correct chart type for your data so that it can be interpreted correctly.</span></span> <span data-ttu-id="5c430-107">Vous devez comprendre les caractéristiques de chaque type de graphique pour déterminer celui qui est le mieux adapté à vos données.</span><span class="sxs-lookup"><span data-stu-id="5c430-107">You should understand each chart type's characteristics to determine what chart type is best suited for your data.</span></span> <span data-ttu-id="5c430-108">Pour plus d’informations, consultez [Types de graphiques &#40;Générateur de rapports et SSRS&#41;](chart-types-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5c430-108">For more information, see [Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="5c430-109">Lorsque plusieurs séries sont affichées sur un graphique, vous pouvez modifier le type de graphique d'une série individuelle.</span><span class="sxs-lookup"><span data-stu-id="5c430-109">When multiple series are displayed on a chart, you may want to change the chart type of an individual series.</span></span> <span data-ttu-id="5c430-110">Vous ne pouvez modifier le type de graphique d'une série individuelle que s'il s'agit d'un graphique en aires, d'un histogramme, d'un graphique en courbes ou d'un graphique à nuages de points.</span><span class="sxs-lookup"><span data-stu-id="5c430-110">You can only change the chart type of an individual series if the chart type is Area, Column, Line, or Scatter.</span></span> <span data-ttu-id="5c430-111">Pour tous les autres types de graphiques, toutes les séries dans votre graphique sont remplacées par le type de graphique sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5c430-111">For all other chart types, all series in your chart will be changed to the selected chart type.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-chart-type"></a><span data-ttu-id="5c430-112">Pour modifier le type de graphique</span><span class="sxs-lookup"><span data-stu-id="5c430-112">To change the chart type</span></span>  
  
1.  <span data-ttu-id="5c430-113">En mode Conception, cliquez avec le bouton droit sur le graphique, puis cliquez sur **Modifier le type du graphique**.</span><span class="sxs-lookup"><span data-stu-id="5c430-113">In Design view, right-click the chart and then click **Change Chart Type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c430-114">Lorsque plusieurs séries sont affichées sur un graphique, vous devez cliquer avec le bouton droit sur la série, et non sur le graphique, à modifier.</span><span class="sxs-lookup"><span data-stu-id="5c430-114">When there are multiple series on a chart, you must right-click on the series, not the chart, which you want to change.</span></span>  
  
2.  <span data-ttu-id="5c430-115">Dans la boîte de dialogue **Sélectionner un type de graphique** , sélectionnez un type de graphique dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5c430-115">In the **SelectChart Type** dialog box, select a chart type from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c430-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c430-116">See Also</span></span>  
 <span data-ttu-id="5c430-117">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5c430-117">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5c430-118">[Jauges &#40;Générateur de rapports et SSRS&#41;](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5c430-118">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5c430-119">Ajouter un graphique à un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5c430-119">Add a Chart to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-chart-to-a-report-report-builder-and-ssrs.md)  
  
  
