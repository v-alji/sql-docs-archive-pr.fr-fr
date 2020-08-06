---
title: Graphiques en courbes (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 194e6679-890d-4a3e-a756-130d32ef7e29
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 44e7a011186e66e6b8bdc8b5dd31939c883e320b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707088"
---
# <a name="line-charts-report-builder-and-ssrs"></a><span data-ttu-id="68fc0-102">Graphiques en courbes (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="68fc0-102">Line Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="68fc0-103">Un graphique en courbes affiche une série sous la forme d'un ensemble de points reliés par une ligne.</span><span class="sxs-lookup"><span data-stu-id="68fc0-103">A line chart displays a series as a set of points connected by a single line.</span></span> <span data-ttu-id="68fc0-104">Les graphiques en courbes sont utilisés pour représenter de grands volumes de données qui se produisent sur une période de temps continue.</span><span class="sxs-lookup"><span data-stu-id="68fc0-104">Line charts are used to representing large amounts of data that occur over a continuous period of time.</span></span> <span data-ttu-id="68fc0-105">Pour plus d’informations sur l’ajout de données à un graphique en courbes, consultez [Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="68fc0-105">For more information about how to add data to a line chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="68fc0-106">L'illustration suivante montre un graphique en courbes qui contient trois séries.</span><span class="sxs-lookup"><span data-stu-id="68fc0-106">The following illustration shows a line chart that contains three series.</span></span>  
  
 <span data-ttu-id="68fc0-107">![Graphique en courbes](../media/rs-linechart.gif "Graphique en courbes")</span><span class="sxs-lookup"><span data-stu-id="68fc0-107">![Line chart](../media/rs-linechart.gif "Line chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="68fc0-108">Variantes</span><span class="sxs-lookup"><span data-stu-id="68fc0-108">Variations</span></span>  
  
-   <span data-ttu-id="68fc0-109">**Courbes lissées**.</span><span class="sxs-lookup"><span data-stu-id="68fc0-109">**Smooth line**.</span></span> <span data-ttu-id="68fc0-110">Graphique en courbes qui utilise une ligne courbée au lieu d'une ligne normale.</span><span class="sxs-lookup"><span data-stu-id="68fc0-110">A line chart that uses a curved line instead of a regular line.</span></span>  
  
-   <span data-ttu-id="68fc0-111">**Courbes en escalier**.</span><span class="sxs-lookup"><span data-stu-id="68fc0-111">**Stepped line**.</span></span> <span data-ttu-id="68fc0-112">Graphique en courbes qui utilise une ligne en escalier au lieu d'une ligne normale.</span><span class="sxs-lookup"><span data-stu-id="68fc0-112">A line chart that uses a stepped line instead of a regular line.</span></span> <span data-ttu-id="68fc0-113">La ligne en escalier connecte les points à l'aide d'une ligne qui ressemble aux barreaux d'une échelle ou aux marches d'un escalier.</span><span class="sxs-lookup"><span data-stu-id="68fc0-113">The stepped line connects points by using a line that makes it look like steps on a ladder or staircase.</span></span>  
  
-   <span data-ttu-id="68fc0-114">**Graphiques sparkline**.</span><span class="sxs-lookup"><span data-stu-id="68fc0-114">**Sparkline charts**.</span></span> <span data-ttu-id="68fc0-115">Variations du graphique en courbes qui affichent uniquement la série dans la cellule d'une table ou matrice.</span><span class="sxs-lookup"><span data-stu-id="68fc0-115">Variations of the line chart that show only the line series in the cell of a table or matrix.</span></span> <span data-ttu-id="68fc0-116">Pour plus d’informations, consultez [Graphiques sparkline et barres de données &#40;Générateur de rapports et SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="68fc0-116">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="data-considerations-for-line-charts"></a><span data-ttu-id="68fc0-117">Considérations relatives aux données pour les graphiques en courbes</span><span class="sxs-lookup"><span data-stu-id="68fc0-117">Data Considerations for Line Charts</span></span>  
  
-   <span data-ttu-id="68fc0-118">Pour améliorer l'impact visuel du graphique en courbes par défaut, pensez à modifier la largeur de la bordure de la série à 3 et à ajouter un décalage de l'ombre de 1.</span><span class="sxs-lookup"><span data-stu-id="68fc0-118">To improve the visual impact of the default line chart, consider changing the width of the series border to 3, and adding a shadow offset of 1.</span></span> <span data-ttu-id="68fc0-119">Cela créera un graphique en courbes plus grasses.</span><span class="sxs-lookup"><span data-stu-id="68fc0-119">This will create a much bolder line chart.</span></span> <span data-ttu-id="68fc0-120">Vous devrez rétablir ces propriétés à leurs valeurs d'origine si vous changez de type de graphique.</span><span class="sxs-lookup"><span data-stu-id="68fc0-120">You will need to revert these properties to their original values if you change the chart type from Line to another type.</span></span>  
  
-   <span data-ttu-id="68fc0-121">Si votre dataset comprend des valeurs vides, le graphique en courbes ajoutera des points vides, sous forme de lignes d'espace réservé, afin de maintenir la continuité sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="68fc0-121">If your dataset includes empty values, the line chart will add empty points, in the form of placeholder lines, in order to maintain continuity on the chart.</span></span> <span data-ttu-id="68fc0-122">Si vous souhaitez ne pas voir ces lignes, affichez votre dataset avec un type de graphique non contigu tel qu'un graphique à barres ou un histogramme.</span><span class="sxs-lookup"><span data-stu-id="68fc0-122">If you would rather not see these lines, consider displaying your dataset using a non-contiguous chart type such as a bar or column chart.</span></span>  
  
-   <span data-ttu-id="68fc0-123">Un graphique en courbes requiert au moins deux points pour dessiner une ligne.</span><span class="sxs-lookup"><span data-stu-id="68fc0-123">A line chart requires at least two points to draw a line.</span></span>  <span data-ttu-id="68fc0-124">Si votre dataset ne contient qu'un point de données, le graphique en courbes s'affichera sous la forme d'un marqueur de point de données unique.</span><span class="sxs-lookup"><span data-stu-id="68fc0-124">If your dataset has only one data point, the line chart will display as a single data point marker.</span></span>  
  
-   <span data-ttu-id="68fc0-125">Une série dessinée sous la forme d'une ligne ne prendra pas beaucoup d'espace dans une zone de graphique.</span><span class="sxs-lookup"><span data-stu-id="68fc0-125">A series that is drawn as a line will not take up much space within a chart area.</span></span>  <span data-ttu-id="68fc0-126">C'est pourquoi, les graphiques en courbes sont souvent associés à d'autres types de graphiques, tels que les histogrammes.</span><span class="sxs-lookup"><span data-stu-id="68fc0-126">For this reason, line charts are frequently combined with other chart types such as column charts.</span></span> <span data-ttu-id="68fc0-127">Cependant, vous ne pouvez pas associer un graphique en courbes avec un graphique à barres, en secteurs ou à base de formes.</span><span class="sxs-lookup"><span data-stu-id="68fc0-127">However, you cannot combine a line chart with bar, polar, pie or shape chart types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68fc0-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68fc0-128">See Also</span></span>  
 <span data-ttu-id="68fc0-129">[Graphiques à barres &#40;Générateur de rapports et SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="68fc0-129">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="68fc0-130">[Histogrammes &#40;Générateur de rapports et SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="68fc0-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="68fc0-131">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="68fc0-131">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="68fc0-132">[Types de graphiques &#40;Générateur de rapports et SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="68fc0-132">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="68fc0-133">[Graphiques en aires &#40;Générateur de rapports et SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="68fc0-133">[Area Charts &#40;Report Builder and SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="68fc0-134">[Points de données vides et Null dans les graphiques &#40;Générateur de rapports et SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="68fc0-134">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="68fc0-135">Graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="68fc0-135">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
