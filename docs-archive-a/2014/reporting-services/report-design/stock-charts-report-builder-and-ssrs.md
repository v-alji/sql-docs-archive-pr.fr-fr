---
title: Graphiques boursiers (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f75ca11e-b7f5-4ac0-ba17-fe6f82742dad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0f8c9c7dbc750bdb477f2ea1d96aa03f7ad022f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600510"
---
# <a name="stock-charts-report-builder-and-ssrs"></a><span data-ttu-id="1a3c2-102">Graphiques boursiers (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="1a3c2-102">Stock Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1a3c2-103">Un graphique boursier est conçu spécialement pour les données financières ou scientifiques qui utilisent jusqu'à quatre valeurs par point de données.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-103">A stock chart is specifically designed for financial or scientific data that uses up to four values per data point.</span></span> <span data-ttu-id="1a3c2-104">Ces valeurs sont alignées avec les valeurs maximales, minimales, d'ouverture et de clôture utilisées pour tracer des données boursières financières.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-104">These values align with the high, low, open and close values that are used to plot financial stock data.</span></span> <span data-ttu-id="1a3c2-105">Ce type de graphique affiche les valeurs d'ouverture et de clôture à l'aide de marqueurs, en règle générale des lignes ou des triangles.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-105">This chart type displays opening and closing values by using markers, which are typically lines or triangles.</span></span> <span data-ttu-id="1a3c2-106">Dans l'exemple suivant, les valeurs d'ouverture sont indiquées par les marqueurs sur la gauche, et les valeurs de clôture sont indiquées par les marqueurs sur la droite.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-106">In the following example, the opening values are shown by the markers on the left, and the closing values are shown by the markers on the right.</span></span>  
  
 <span data-ttu-id="1a3c2-107">![Graphique boursier](../media/rs-stockchart.gif "Graphique boursier")</span><span class="sxs-lookup"><span data-stu-id="1a3c2-107">![Stock chart](../media/rs-stockchart.gif "Stock chart")</span></span>  
  
 <span data-ttu-id="1a3c2-108">Un exemple de graphique boursier est disponible sous forme d'exemple de rapport du Générateur de rapports de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a3c2-108">An example of a stock chart is available as a sample [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="1a3c2-109">Pour plus d'informations sur le téléchargement de cet exemple de rapport et d'autres rapports, consultez [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][Exemples de rapports du Générateur de rapports et du Concepteur de rapports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="1a3c2-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="1a3c2-110">Variantes</span><span class="sxs-lookup"><span data-stu-id="1a3c2-110">Variations</span></span>  
  
-   <span data-ttu-id="1a3c2-111">**Bougies**.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-111">**Candlestick**.</span></span> <span data-ttu-id="1a3c2-112">Le graphique en bougies est un type spécial de graphique boursier, où des zones sont utilisées pour afficher la plage entre les valeurs d'ouverture et de clôture.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-112">The candlestick chart is a specialized form of the stock chart, wherein boxes are used to show the range between the open and close values.</span></span> <span data-ttu-id="1a3c2-113">Comme le graphique boursier, le graphique en bougies peut afficher jusqu'à quatre valeurs par point de données.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-113">Like the stock chart, the candlestick chart can display up to four values per data point.</span></span>  
  
## <a name="data-considerations-for-stock-charts"></a><span data-ttu-id="1a3c2-114">Considérations relatives aux données pour les graphiques boursiers</span><span class="sxs-lookup"><span data-stu-id="1a3c2-114">Data Considerations for Stock Charts</span></span>  
  
-   <span data-ttu-id="1a3c2-115">Lors de la présentation de nombreux points de données boursiers, tels que la tendance du cours de l'action annuelle, il est difficile de distinguer chaque valeur d'ouverture, de clôture, maximale et minimale pour chaque point de données.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-115">When presenting many stock data points, such as annual stock price trend, it is difficult to distinguish each open, close, high and low value of each data point.</span></span> <span data-ttu-id="1a3c2-116">Dans ce scénario, pensez à utiliser un graphique en courbes au lieu d'un graphique boursier.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-116">In this scenario, consider using a line chart instead of a stock chart.</span></span>  
  
-   <span data-ttu-id="1a3c2-117">Lorsque les étiquettes d'axe sont générées, l'étiquetage commence à zéro.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-117">When axis labels are generated, labeling usually begins at zero.</span></span>  <span data-ttu-id="1a3c2-118">En règle générale, les cours de l'action ne fluctuent pas de la même façon que d'autres datasets.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-118">In general, stock prices do not fluctuate to the same degree as other data sets.</span></span> <span data-ttu-id="1a3c2-119">C'est pourquoi, vous pouvez empêcher le démarrage des étiquettes d'axe à zéro, afin d'obtenir une meilleure vue de vos données.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-119">For this reason, you may want to disable the axis labels from starting at zero, in order to get a better view of your data.</span></span> <span data-ttu-id="1a3c2-120">Pour ce faire, définissez **IncludeZero** à **false** dans la boîte de dialogue **Propriétés de l'axe** ou dans la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-120">To do this, set **IncludeZero** to **false** in the **Axis Properties** dialog box or the Properties window.</span></span> <span data-ttu-id="1a3c2-121">Pour plus d’informations sur la façon dont le graphique génère les étiquettes de l’axe, consultez [Mise en forme des étiquettes des axes sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1a3c2-121">For more information about how the chart generates axis labels, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1a3c2-122">fournit de nombreuses formules calculées à utiliser avec des graphiques boursiers, notamment un indicateur de prix, un indicateur de force relative, MACD, etc.</span><span class="sxs-lookup"><span data-stu-id="1a3c2-122">provides many calculated formulas for use with stock charts, including Price Indicator, Relative Strength Index, MACD and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a3c2-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a3c2-123">See Also</span></span>  
 <span data-ttu-id="1a3c2-124">[Graphiques d’étendue &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1a3c2-124">[Range Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1a3c2-125">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1a3c2-125">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1a3c2-126">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1a3c2-126">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1a3c2-127">Boîte de dialogue Propriétés de l’axe, Options de l’axe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1a3c2-127">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
