---
title: Graphiques polaires (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c9402d8f-202a-4cdf-949e-50f5b1d2b885
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b8c4dd9394fab3e076c4a714375954a616e081f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695295"
---
# <a name="polar-charts-report-builder-and-ssrs"></a><span data-ttu-id="2a42d-102">Graphiques polaires (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="2a42d-102">Polar Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2a42d-103">Un graphique polaire affiche une série sous la forme d'un ensemble de points groupés en catégorie sur un cercle de 360 degrés.</span><span class="sxs-lookup"><span data-stu-id="2a42d-103">A polar chart displays a series as a set of points that are grouped by category on a 360-degree circle.</span></span> <span data-ttu-id="2a42d-104">Les valeurs sont représentées par la longueur du point mesurée à partir du centre du cercle.</span><span class="sxs-lookup"><span data-stu-id="2a42d-104">Values are represented by the length of the point as measured from the center of the circle.</span></span> <span data-ttu-id="2a42d-105">Plus le point est loin du centre, plus la valeur est grande.</span><span class="sxs-lookup"><span data-stu-id="2a42d-105">The farther the point is from the center, the greater its value.</span></span> <span data-ttu-id="2a42d-106">Les étiquettes de catégorie sont affichées sur le périmètre du graphique.</span><span class="sxs-lookup"><span data-stu-id="2a42d-106">Category labels are displayed on the perimeter of the chart.</span></span> <span data-ttu-id="2a42d-107">Pour plus d’informations sur l’ajout de données à un graphique polaire, consultez [Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a42d-107">For more information on how to add data to a polar chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="2a42d-108">Variantes</span><span class="sxs-lookup"><span data-stu-id="2a42d-108">Variations</span></span>  
  
-   <span data-ttu-id="2a42d-109">**Graphique en radar**.</span><span class="sxs-lookup"><span data-stu-id="2a42d-109">**Radar chart**.</span></span> <span data-ttu-id="2a42d-110">Un graphique en radar affiche une série sous la forme d'une ligne ou zone circulaire.</span><span class="sxs-lookup"><span data-stu-id="2a42d-110">A radar chart displays a series as a circular line or area.</span></span> <span data-ttu-id="2a42d-111">Contrairement au graphique polaire, le graphique en radar n'affiche pas les données sous la forme de polaires.</span><span class="sxs-lookup"><span data-stu-id="2a42d-111">Unlike the polar chart, the radar chart does not display data in terms of polar coordinates.</span></span>  
  
## <a name="data-considerations-for-polar-charts"></a><span data-ttu-id="2a42d-112">Considérations relatives aux données pour les graphiques polaires</span><span class="sxs-lookup"><span data-stu-id="2a42d-112">Data Considerations for Polar Charts</span></span>  
  
-   <span data-ttu-id="2a42d-113">Le graphique en radar est utile pour les comparaisons entre plusieurs séries de données de catégorie.</span><span class="sxs-lookup"><span data-stu-id="2a42d-113">The radar chart is useful for comparisons between multiple series of category data.</span></span>  
  
-   <span data-ttu-id="2a42d-114">Les graphiques polaires sont utilisés le plus souvent pour tracer des données polaires, où chaque point de données est défini par un angle et une distance.</span><span class="sxs-lookup"><span data-stu-id="2a42d-114">Polar charts are most commonly used to graph polar data, where each data point is determined by an angle and a distance.</span></span>  
  
-   <span data-ttu-id="2a42d-115">Les graphiques polaires ne peuvent pas être associés avec un autre type de graphique dans la même zone de graphique.</span><span class="sxs-lookup"><span data-stu-id="2a42d-115">Polar charts cannot be combined with any other chart type in the same chart area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a42d-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="2a42d-116">Example</span></span>  
 <span data-ttu-id="2a42d-117">L'exemple suivant montre l'utilisation d'un graphique en radar.</span><span class="sxs-lookup"><span data-stu-id="2a42d-117">The following example shows how a radar chart can be used.</span></span> <span data-ttu-id="2a42d-118">Le tableau ci-dessous fournit les données d'exemple pour le graphique.</span><span class="sxs-lookup"><span data-stu-id="2a42d-118">The table below provides sample data for the chart.</span></span>  
  
|<span data-ttu-id="2a42d-119">Name</span><span class="sxs-lookup"><span data-stu-id="2a42d-119">Name</span></span>|<span data-ttu-id="2a42d-120">Ventes</span><span class="sxs-lookup"><span data-stu-id="2a42d-120">Sales</span></span>|  
|----------|-----------|  
|<span data-ttu-id="2a42d-121">Arbrisseaux</span><span class="sxs-lookup"><span data-stu-id="2a42d-121">Shrubs</span></span>|<span data-ttu-id="2a42d-122">61</span><span class="sxs-lookup"><span data-stu-id="2a42d-122">61</span></span>|  
|<span data-ttu-id="2a42d-123">Graines</span><span class="sxs-lookup"><span data-stu-id="2a42d-123">Seeds</span></span>|<span data-ttu-id="2a42d-124">78</span><span class="sxs-lookup"><span data-stu-id="2a42d-124">78</span></span>|  
|<span data-ttu-id="2a42d-125">Bulbes</span><span class="sxs-lookup"><span data-stu-id="2a42d-125">Bulbs</span></span>|<span data-ttu-id="2a42d-126">60</span><span class="sxs-lookup"><span data-stu-id="2a42d-126">60</span></span>|  
|<span data-ttu-id="2a42d-127">Arborescences</span><span class="sxs-lookup"><span data-stu-id="2a42d-127">Trees</span></span>|<span data-ttu-id="2a42d-128">38</span><span class="sxs-lookup"><span data-stu-id="2a42d-128">38</span></span>|  
|<span data-ttu-id="2a42d-129">Fleurs</span><span class="sxs-lookup"><span data-stu-id="2a42d-129">Flowers</span></span>|<span data-ttu-id="2a42d-130">81</span><span class="sxs-lookup"><span data-stu-id="2a42d-130">81</span></span>|  
  
 <span data-ttu-id="2a42d-131">Dans cet exemple, le champ Nom est placé dans la zone Groupes de catégories.</span><span class="sxs-lookup"><span data-stu-id="2a42d-131">In this example, the Name field is placed in the Category Groups area.</span></span> <span data-ttu-id="2a42d-132">Le champ Ventes est placé dans la zone Valeurs.</span><span class="sxs-lookup"><span data-stu-id="2a42d-132">The Sales field is placed in the Values area.</span></span> <span data-ttu-id="2a42d-133">Le champ Ventes est automatiquement agrégé pour le graphique lorsque vous l'ajoutez.</span><span class="sxs-lookup"><span data-stu-id="2a42d-133">The Sales field is automatically aggregated for the chart when you drop it.</span></span> <span data-ttu-id="2a42d-134">Le graphique en radar calcule où placer les étiquettes en fonction du nombre de valeurs dans le champ Ventes, qui contient cinq valeurs et place les étiquettes à cinq points équidistants sur un cercle.</span><span class="sxs-lookup"><span data-stu-id="2a42d-134">The radar chart calculates where to place the labels based on the number of values in the Sales field, which contains five values and places labels at five equidistant points on a circle.</span></span> <span data-ttu-id="2a42d-135">Si le champ Ventes contient trois valeurs, les étiquettes sont placées à trois points équidistants sur un cercle.</span><span class="sxs-lookup"><span data-stu-id="2a42d-135">If the Sales field contained three values, the labels would be placed at three equidistant points on a circle.</span></span>  
  
 <span data-ttu-id="2a42d-136">L'illustration suivante montre un exemple de graphique en radar basé sur les données présentées.</span><span class="sxs-lookup"><span data-stu-id="2a42d-136">The following illustration shows an example of a radar chart based on the data presented.</span></span>  
  
 <span data-ttu-id="2a42d-137">![Graphique en radar](../media/rs-radarchart.gif "Graphique en radar")</span><span class="sxs-lookup"><span data-stu-id="2a42d-137">![Radar chart](../media/rs-radarchart.gif "Radar chart")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a42d-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a42d-138">See Also</span></span>  
 <span data-ttu-id="2a42d-139">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2a42d-139">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2a42d-140">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2a42d-140">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2a42d-141">[Types de graphiques &#40;Générateur de rapports et SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2a42d-141">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2a42d-142">[Graphiques en courbes &#40;Générateur de rapports et SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2a42d-142">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2a42d-143">Points de données vides et Null dans les graphiques &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2a42d-143">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
