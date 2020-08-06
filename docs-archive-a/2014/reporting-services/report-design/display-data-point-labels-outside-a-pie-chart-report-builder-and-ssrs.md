---
title: Afficher des étiquettes de points de données à l’extérieur d’un graphique à secteurs (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 959b7574-cf43-470b-b592-4944d8a9948f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dd4f38f24d2729acacfa3520635b93d8af2e9433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704928"
---
# <a name="display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="6884f-102">Afficher des étiquettes de points de données à l'extérieur d'un graphique à secteurs (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="6884f-102">Display Data Point Labels Outside a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6884f-103">Dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], l'étiquetage de graphiques à secteurs est optimisé pour afficher des étiquettes uniquement sur plusieurs tranches de données.</span><span class="sxs-lookup"><span data-stu-id="6884f-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], pie chart labeling is optimized to display labels on only several slices of data.</span></span> <span data-ttu-id="6884f-104">Les étiquettes peuvent se chevaucher si le graphique à secteurs contient trop de secteurs.</span><span class="sxs-lookup"><span data-stu-id="6884f-104">Labels may overlap if the pie chart contains too many slices.</span></span> <span data-ttu-id="6884f-105">Une solution consiste à afficher les étiquettes à l'extérieur du graphique à secteurs, ce qui peut libérer de l'espace pour de plus longues étiquettes de données.</span><span class="sxs-lookup"><span data-stu-id="6884f-105">One solution is to display the labels outside the pie chart, which may create more room for longer data labels.</span></span> <span data-ttu-id="6884f-106">Si les étiquettes continuent de se chevaucher, vous pouvez créer davantage d'espace pour elles en activant l'affichage 3D.</span><span class="sxs-lookup"><span data-stu-id="6884f-106">If you find that your labels still overlap, you can create more space for them by enabling 3D.</span></span> <span data-ttu-id="6884f-107">Le diamètre du graphique à secteurs est ainsi réduit, ce qui libère de l'espace autour du graphique.</span><span class="sxs-lookup"><span data-stu-id="6884f-107">This reduces the diameter of the pie chart, creating more space around the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-data-point-labels-inside-a-pie-chart"></a><span data-ttu-id="6884f-108">Pour afficher des étiquettes de points de données à l'intérieur d'un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="6884f-108">To display data point labels inside a pie chart</span></span>  
  
1.  <span data-ttu-id="6884f-109">Ajoutez un graphique à secteurs à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="6884f-109">Add a pie chart to your report.</span></span> <span data-ttu-id="6884f-110">Pour plus d’informations, consultez [Ajouter un graphique à un rapport &#40;Générateur de rapports et SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6884f-110">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="6884f-111">Sur l’aire de conception, cliquez avec le bouton droit sur le graphique et sélectionnez **Afficher les étiquettes de données**.</span><span class="sxs-lookup"><span data-stu-id="6884f-111">On the design surface, right-click on the chart and select **Show Data Labels**.</span></span>  
  
### <a name="to-display-data-point-labels-outside-a-pie-chart"></a><span data-ttu-id="6884f-112">Pour afficher des étiquettes de points de données à l'extérieur d'un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="6884f-112">To display data point labels outside a pie chart</span></span>  
  
1.  <span data-ttu-id="6884f-113">Créez un graphique à secteurs et affichez les étiquettes de données.</span><span class="sxs-lookup"><span data-stu-id="6884f-113">Create a pie chart and display the data labels.</span></span>  
  
2.  <span data-ttu-id="6884f-114">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="6884f-114">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="6884f-115">Dans l’aire de conception, cliquez sur le graphique à secteurs lui-même pour afficher les propriétés de **Catégorie** dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="6884f-115">On the design surface, click on the pie itself to display the **Category** properties in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="6884f-116">Développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="6884f-116">Expand the **CustomAttributes** node.</span></span> <span data-ttu-id="6884f-117">Une liste des attributs du graphique à secteurs s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6884f-117">A list of attributes for the pie chart is displayed.</span></span>  
  
5.  <span data-ttu-id="6884f-118">Affectez à la propriété **PieLabelStyle** la valeur **Extérieur**.</span><span class="sxs-lookup"><span data-stu-id="6884f-118">Set the **PieLabelStyle** property to **Outside**.</span></span>  
  
6.  <span data-ttu-id="6884f-119">Affectez la valeur `PieLineColor` **Black**à la propriété.</span><span class="sxs-lookup"><span data-stu-id="6884f-119">Set the `PieLineColor` property to **Black**.</span></span> <span data-ttu-id="6884f-120">La propriété PieLineColor définit les lignes de légende de chaque étiquette de point de données.</span><span class="sxs-lookup"><span data-stu-id="6884f-120">The PieLineColor property defines callout lines for each data point label.</span></span>  
  
### <a name="to-prevent-overlapping-labels-displayed-outside-a-pie-chart"></a><span data-ttu-id="6884f-121">Pour empêcher les étiquettes qui se chevauchent de s'afficher à l'extérieur d'un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="6884f-121">To prevent overlapping labels displayed outside a pie chart</span></span>  
  
1.  <span data-ttu-id="6884f-122">Créez un graphique à secteurs avec des étiquettes externes.</span><span class="sxs-lookup"><span data-stu-id="6884f-122">Create a pie chart with external labels.</span></span>  
  
2.  <span data-ttu-id="6884f-123">Dans l’aire de conception, cliquez avec le bouton droit à l’extérieur du graphique à secteurs, mais à l’intérieur des bordures du graphique, puis sélectionnez **Propriétés de la zone de graphique**. La boîte de dialogue **Propriétés de la zone de graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="6884f-123">On the design surface, right-click outside the pie chart but inside the chart borders and select **Chart Area Properties**.The **Chart AreaProperties** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="6884f-124">Sous l’onglet **Options 3D** , sélectionnez **Afficher en 3D**.</span><span class="sxs-lookup"><span data-stu-id="6884f-124">On the **3D Options** tab, select **Enable 3D**.</span></span>  
  
4.  <span data-ttu-id="6884f-125">Si vous souhaitez que le graphique dispose de davantage d’espace pour les étiquettes tout en s’affichant en deux dimensions, affectez aux propriétés **Rotation** et **Inclinaison** la valeur **0**.</span><span class="sxs-lookup"><span data-stu-id="6884f-125">If you want the chart to have more room for labels but still appear two-dimensional, set the **Rotation** and **Inclination** properties to **0**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6884f-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6884f-126">See Also</span></span>  
 <span data-ttu-id="6884f-127">[Graphiques à secteurs &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6884f-127">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6884f-128">[Regrouper des petits secteurs sur un graphique à secteurs &#40;Générateur de rapports et SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6884f-128">[Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6884f-129">Afficher des valeurs en pourcentage dans un graphique à secteurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6884f-129">Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
