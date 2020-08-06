---
title: Tracer des données sur un axe secondaire (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 094f39bf-3634-4852-9fc3-3adec4b266e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cec58820e0373bb1e9ef2d50d022e5b4ef7e962b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695292"
---
# <a name="plot-data-on-a-secondary-axis-report-builder-and-ssrs"></a><span data-ttu-id="d92ba-102">Tracer des données sur un axe secondaire (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="d92ba-102">Plot Data on a Secondary Axis (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d92ba-103">Le graphique a deux types d'axes : principal et secondaire.</span><span class="sxs-lookup"><span data-stu-id="d92ba-103">The chart has two axis types: primary and secondary.</span></span> <span data-ttu-id="d92ba-104">L'axe secondaire est utile lors de la comparaison de deux jeux de valeurs avec deux plages de données distinctes qui partagent une catégorie commune.</span><span class="sxs-lookup"><span data-stu-id="d92ba-104">The secondary axis is useful when comparing two value sets with two distinct data ranges that share a common category.</span></span>  
  
 <span data-ttu-id="d92ba-105">Par exemple, supposons que vous ayez un graphique qui calcule vos revenus et impôts pour l'année 2008.</span><span class="sxs-lookup"><span data-stu-id="d92ba-105">For example, suppose you have a chart that calculates Revenue vs. Tax for the year 2008.</span></span> <span data-ttu-id="d92ba-106">Dans ce cas, la période 2008 est commune aux deux jeux de valeurs.</span><span class="sxs-lookup"><span data-stu-id="d92ba-106">In this case, the 2008 time period is common to both value sets.</span></span> <span data-ttu-id="d92ba-107">Toutefois, lorsque les deux séries sont tracées sur le même axe des Y, nous ne pouvons pas établir de comparaison utile, car l'échelle de l'axe des Y est optimisée pour les plus grandes valeurs du dataset.</span><span class="sxs-lookup"><span data-stu-id="d92ba-107">However, when both series are plotted on the same y-axis, we cannot make a useful comparison because the scale of the y-axis is optimized for the largest values in the dataset.</span></span> <span data-ttu-id="d92ba-108">Si nous affichons les revenus sur l'axe principal et les impôts sur l'axe secondaire, nous pouvons afficher chaque série sur son propre axe des Y avec sa propre échelle de valeurs.</span><span class="sxs-lookup"><span data-stu-id="d92ba-108">If we show Revenue on the primary axis, and Tax on the secondary axis, we can display each series on its own y-axis with its own scale of values.</span></span> <span data-ttu-id="d92ba-109">Les séries partagent encore un axe des abscisses commun.</span><span class="sxs-lookup"><span data-stu-id="d92ba-109">The series still share a common x-axis.</span></span>  
  
 <span data-ttu-id="d92ba-110">Dans les cas où plus de deux séries doivent être comparées, envisagez une approche différente pour comparer et afficher plusieurs séries dans un graphique.</span><span class="sxs-lookup"><span data-stu-id="d92ba-110">In situations where there are more than two series to be compared, consider a different approach for comparing and displaying multiple series in a chart.</span></span> <span data-ttu-id="d92ba-111">Pour plus d’informations, consultez [Plusieurs séries sur un graphique &#40;Générateur de rapports et SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d92ba-111">For more information, see [Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="d92ba-112">Un exemple de ce graphique est disponible sous forme d'exemple de rapport.</span><span class="sxs-lookup"><span data-stu-id="d92ba-112">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="d92ba-113">Pour plus d'informations sur le téléchargement de cet exemple de rapport et d'autres rapports, consultez [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Exemples de rapports du Générateur de rapports et du Concepteur de rapports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="d92ba-113">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-plot-a-series-on-the-secondary-axis"></a><span data-ttu-id="d92ba-114">Pour tracer une série sur l'axe secondaire</span><span class="sxs-lookup"><span data-stu-id="d92ba-114">To plot a series on the secondary axis</span></span>  
  
1.  <span data-ttu-id="d92ba-115">Cliquez avec le bouton droit sur la série dans le graphique ou sur un champ dans la zone **Valeurs** que vous souhaitez afficher sur l’axe secondaire, puis cliquez sur **Propriétés de la série**.</span><span class="sxs-lookup"><span data-stu-id="d92ba-115">Right-click the series in the chart or right-click on a field in the **Values** area that you want to display on the secondary axis and click **Series Properties**.</span></span> <span data-ttu-id="d92ba-116">La boîte de dialogue **Propriétés de la série** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="d92ba-116">The **Series Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="d92ba-117">Cliquez sur **Axes et zone de graphique**, et sélectionnez l'axe secondaire que vous voulez activer, l'axe des ordonnées ou l'axe des abscisses.</span><span class="sxs-lookup"><span data-stu-id="d92ba-117">Click **Axes and Chart Area**, and select which of the secondary axes you want to enable, the value axis or the category axis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92ba-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d92ba-118">See Also</span></span>  
 <span data-ttu-id="d92ba-119">[Mise en forme des étiquettes d’axe sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d92ba-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d92ba-120">Spécifier un intervalle d’axe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d92ba-120">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
