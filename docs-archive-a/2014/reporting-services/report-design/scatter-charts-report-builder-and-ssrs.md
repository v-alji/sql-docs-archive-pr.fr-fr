---
title: Graphiques à nuages de points (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2520ae24-0609-4890-807d-3267018aba8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 93f9b31089eb8399c7fdfd201d3c799608f2e91e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702452"
---
# <a name="scatter-charts-report-builder-and-ssrs"></a><span data-ttu-id="6e4f1-102">Graphiques à nuages de points (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="6e4f1-102">Scatter Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6e4f1-103">Un graphique à nuages de points affiche une série sous la forme d'un ensemble de points.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-103">A scatter chart displays a series as a set of points.</span></span> <span data-ttu-id="6e4f1-104">Les valeurs sont représentées par la position des points dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-104">Values are represented by the position of the points on the chart.</span></span> <span data-ttu-id="6e4f1-105">et les catégories, par différents marqueurs dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-105">Categories are represented by different markers on the chart.</span></span> <span data-ttu-id="6e4f1-106">Un graphique à nuages de points sert généralement à comparer des données agrégées entre catégories.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-106">Scatter charts are typically used to compare aggregated data across categories.</span></span> <span data-ttu-id="6e4f1-107">Pour plus d’informations sur la façon d’ajouter des données à un nuage de points, consultez [Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="6e4f1-107">For more information on how to add data to a scatter chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="6e4f1-108">L'illustration suivante montre un exemple de graphique à nuages de points.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-108">The following illustration shows an example of a scatter chart.</span></span>  
  
 <span data-ttu-id="6e4f1-109">![Graphique à nuages de points](../media/rs-scatterchart.gif "Graphique à nuages de points")</span><span class="sxs-lookup"><span data-stu-id="6e4f1-109">![Scatter chart](../media/rs-scatterchart.gif "Scatter chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="6e4f1-110">Variantes</span><span class="sxs-lookup"><span data-stu-id="6e4f1-110">Variations</span></span>  
  
-   <span data-ttu-id="6e4f1-111">**Bulles.**</span><span class="sxs-lookup"><span data-stu-id="6e4f1-111">**Bubble.**</span></span> <span data-ttu-id="6e4f1-112">Les graphiques à bulles affichent la différence entre deux valeurs d'un point de données selon la taille de la bulle.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-112">Bubble charts display the difference between two values of a data point based on the size of the bubble.</span></span> <span data-ttu-id="6e4f1-113">Plus la bulle est grande, plus la différence entre les deux valeurs est importante.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-113">The larger the bubble, the larger the difference between the two values.</span></span>  
  
-   <span data-ttu-id="6e4f1-114">**Bulles 3D**.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-114">**3-D Bubble**.</span></span> <span data-ttu-id="6e4f1-115">Graphique à bulles affiché en 3D.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-115">A bubble chart displayed in 3-D.</span></span>  
  
## <a name="data-considerations-for-a-scatter-chart"></a><span data-ttu-id="6e4f1-116">Considérations relatives aux données pour les graphiques à nuages de points</span><span class="sxs-lookup"><span data-stu-id="6e4f1-116">Data Considerations for a Scatter Chart</span></span>  
  
-   <span data-ttu-id="6e4f1-117">Les graphiques à nuages de points servent généralement à afficher et comparer des valeurs numériques, comme des données scientifiques, statistiques et d'ingénierie.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-117">Scatter charts are commonly used for displaying and comparing numeric values, such as scientific, statistical, and engineering data.</span></span>  
  
-   <span data-ttu-id="6e4f1-118">Utilisez un graphique à nuages de points lorsque vous souhaitez comparer un grand nombre de points de données sans distinction de temps.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-118">Use the scatter chart when you want to compare large numbers of data points without regard to time.</span></span> <span data-ttu-id="6e4f1-119">Plus vous incluez de données dans un graphique à nuages de points, meilleures sont les comparaisons possibles.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-119">The more data that you include in a scatter chart, the better the comparisons that you can make.</span></span>  
  
-   <span data-ttu-id="6e4f1-120">Le graphique à bulles requiert deux valeurs (supérieure et inférieure) par point de données.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-120">The bubble chart requires two values (top and bottom) per data point.</span></span>  
  
-   <span data-ttu-id="6e4f1-121">Les graphiques à nuages de points sont idéaux pour gérer la distribution de valeurs et clusters de points de données.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-121">Scatter charts are ideal for handling the distribution of values and clusters of data points.</span></span> <span data-ttu-id="6e4f1-122">Il s'agit du type de graphique le mieux adapté si votre dataset contient de nombreux points (par exemple plusieurs milliers de points).</span><span class="sxs-lookup"><span data-stu-id="6e4f1-122">This is the best chart type if your dataset contains many points (for example, several thousand points).</span></span> <span data-ttu-id="6e4f1-123">L'affichage de plusieurs séries sur un graphique à points est visuellement gênant et doit être évité.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-123">Displaying multiple series on a point chart is visually distracting and should be avoided.</span></span> <span data-ttu-id="6e4f1-124">Dans ce cas, envisagez d'utiliser un graphique en courbes.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-124">In this scenario, consider using a line chart.</span></span>  
  
-   <span data-ttu-id="6e4f1-125">Par défaut, les graphiques à nuages de points affichent les points de données sous la forme de cercles.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-125">By default, scatter charts display data points as circles.</span></span> <span data-ttu-id="6e4f1-126">Si un graphique à nuages de points contient plusieurs séries, envisagez de modifier la forme de marqueur de chaque point pour que ce soit un carré, un triangle, un losange ou une autre forme.</span><span class="sxs-lookup"><span data-stu-id="6e4f1-126">If you have multiple series on a scatter chart, consider changing the marker shape of each point to be square, triangle, diamond, or another shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4f1-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e4f1-127">See Also</span></span>  
 <span data-ttu-id="6e4f1-128">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6e4f1-128">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6e4f1-129">[Types de graphiques &#40;Générateur de rapports et SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6e4f1-129">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6e4f1-130">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6e4f1-130">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6e4f1-131">Graphiques en courbes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6e4f1-131">Line Charts &#40;Report Builder and SSRS&#41;</span></span>](line-charts-report-builder-and-ssrs.md)  
  
  
