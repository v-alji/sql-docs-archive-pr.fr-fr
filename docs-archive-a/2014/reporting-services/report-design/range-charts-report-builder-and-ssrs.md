---
title: Graphiques d’étendue (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48e351d3-ac5b-4eda-a4bd-32a0de206a30
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 76a9723bc55030da59d22c945a40ce4418b84ab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702451"
---
# <a name="range-charts-report-builder-and-ssrs"></a><span data-ttu-id="18a06-102">Graphiques d'étendue (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="18a06-102">Range Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="18a06-103">Un type de graphique d'étendue affiche un ensemble de points de données qui sont chacun définis par plusieurs valeurs pour la même catégorie.</span><span class="sxs-lookup"><span data-stu-id="18a06-103">A range chart type displays a set of data points that are each defined by multiple values for the same category.</span></span> <span data-ttu-id="18a06-104">Les valeurs sont représentées par la hauteur du marqueur, telle que mesurée par l'axe des ordonnées.</span><span class="sxs-lookup"><span data-stu-id="18a06-104">Values are represented by the height of the marker as measured by the value axis.</span></span> <span data-ttu-id="18a06-105">Les étiquettes de catégorie sont affichées sur l'axe des abscisses.</span><span class="sxs-lookup"><span data-stu-id="18a06-105">Category labels are displayed on the category axis.</span></span> <span data-ttu-id="18a06-106">Le graphique d'étendue ordinaire remplit la zone située entre les valeurs supérieure et inférieure de chaque point de données.</span><span class="sxs-lookup"><span data-stu-id="18a06-106">The plain range chart fills in the area between the top and bottom value for each data point.</span></span>  
  
 <span data-ttu-id="18a06-107">L'illustration suivante montre un graphique d'étendue ordinaire comportant trois séries.</span><span class="sxs-lookup"><span data-stu-id="18a06-107">The following illustration shows a plain range chart with three series.</span></span>  
  
 <span data-ttu-id="18a06-108">![Graphique d'étendue](../media/rs-rangechart.gif "Graphique d'étendue")</span><span class="sxs-lookup"><span data-stu-id="18a06-108">![Range chart](../media/rs-rangechart.gif "Range chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="18a06-109">Variantes</span><span class="sxs-lookup"><span data-stu-id="18a06-109">Variations</span></span>  
  
-   <span data-ttu-id="18a06-110">**Étendue lissée**.</span><span class="sxs-lookup"><span data-stu-id="18a06-110">**Smooth range**.</span></span> <span data-ttu-id="18a06-111">Un graphique d'étendue lissée affiche des courbes plutôt que des droites.</span><span class="sxs-lookup"><span data-stu-id="18a06-111">A smooth range chart displays curved lines rather than straight.</span></span>  
  
-   <span data-ttu-id="18a06-112">**Étendue en colonnes**.</span><span class="sxs-lookup"><span data-stu-id="18a06-112">**Column range**.</span></span> <span data-ttu-id="18a06-113">Un graphique d'étendue en colonnes utilise des colonnes à la place des aires pour afficher les étendues.</span><span class="sxs-lookup"><span data-stu-id="18a06-113">A column range chart uses columns instead of areas to display the ranges.</span></span>  
  
-   <span data-ttu-id="18a06-114">**Étendue à barres**.</span><span class="sxs-lookup"><span data-stu-id="18a06-114">**Bar range**.</span></span> <span data-ttu-id="18a06-115">Un graphique d'étendue à barres utilise des barres à la place des aires pour afficher les étendues.</span><span class="sxs-lookup"><span data-stu-id="18a06-115">A bar range chart uses bars instead of areas to display the ranges.</span></span>  
  
## <a name="data-considerations-for-range-charts"></a><span data-ttu-id="18a06-116">Considérations relatives aux données pour les graphiques d'étendue</span><span class="sxs-lookup"><span data-stu-id="18a06-116">Data Considerations for Range Charts</span></span>  
  
-   <span data-ttu-id="18a06-117">Les types de graphique d'étendue nécessitent deux valeurs par point de données.</span><span class="sxs-lookup"><span data-stu-id="18a06-117">Range chart types require two values per data point.</span></span> <span data-ttu-id="18a06-118">Ces valeurs correspondent à une valeur supérieure et une valeur inférieure qui définissent l'étendue de chaque point de données.</span><span class="sxs-lookup"><span data-stu-id="18a06-118">These values correspond with a high value and a low value that defines the range for each data point.</span></span>  
  
-   <span data-ttu-id="18a06-119">Les graphiques d'étendue ne sont utiles pour l'analyse que si les valeurs supérieures sont toujours plus élevées que les valeurs inférieures.</span><span class="sxs-lookup"><span data-stu-id="18a06-119">Range charts are useful for analysis only if the top values are always higher than the bottom values.</span></span> <span data-ttu-id="18a06-120">Si ce n'est pas le cas, pensez plutôt à utiliser un graphique en courbes.</span><span class="sxs-lookup"><span data-stu-id="18a06-120">If this is not the case, consider using a line chart.</span></span> <span data-ttu-id="18a06-121">Si la valeur supérieure est moins élevée que la valeur inférieure, le graphique d'étendue affichera la valeur absolue de la différence entre ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="18a06-121">If the high value is lower the low value, the range chart will display the absolute value of the difference between these values.</span></span>  
  
-   <span data-ttu-id="18a06-122">Si une seule valeur est spécifiée, le graphique d'étendue s'affichera comme un graphique en aires normal, avec une valeur par point de données.</span><span class="sxs-lookup"><span data-stu-id="18a06-122">If only one value is specified, the range chart will display as if it were a regular area chart, with one value per data point.</span></span>  
  
-   <span data-ttu-id="18a06-123">Les graphiques d'étendue sont souvent utilisés pour représenter des données qui contiennent des valeurs minimales et maximales pour chaque groupe de catégories dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="18a06-123">Range charts are often used to graph data that contains minimum and maximum values for each category group in the dataset.</span></span>  
  
-   <span data-ttu-id="18a06-124">L'affichage de marqueurs sur chaque point de données n'est pas pris en charge dans les graphiques d'étendue.</span><span class="sxs-lookup"><span data-stu-id="18a06-124">Displaying markers on each data point is not supported on the range chart.</span></span>  
  
-   <span data-ttu-id="18a06-125">Comme pour un graphique en aires, si dans un graphique d'étendue ordinaire, les valeurs de plusieurs séries sont similaires, celles-ci se chevaucheront.</span><span class="sxs-lookup"><span data-stu-id="18a06-125">Like the area chart, in a plain range chart, if the values in multiple series are similar, the series will overlap.</span></span> <span data-ttu-id="18a06-126">Dans ce cas, vous pouvez utiliser un graphique d'étendue en colonnes ou à barres au lieu d'un graphique d'étendue ordinaire.</span><span class="sxs-lookup"><span data-stu-id="18a06-126">In this scenario, you may want to use a column range or bar range chart instead of a plain range chart.</span></span>  
  
-   <span data-ttu-id="18a06-127">Les diagrammes de Gantt peuvent être créés à l'aide d'un graphique d'étendue à barres.</span><span class="sxs-lookup"><span data-stu-id="18a06-127">Gantt charts can be created using a range bar chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a06-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="18a06-128">See Also</span></span>  
 <span data-ttu-id="18a06-129">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18a06-129">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="18a06-130">[Types de graphiques &#40;Générateur de rapports et SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18a06-130">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="18a06-131">Mise en forme d’un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="18a06-131">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
