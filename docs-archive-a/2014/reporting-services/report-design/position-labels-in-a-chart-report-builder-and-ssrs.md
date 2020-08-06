---
title: Placer des étiquettes dans un graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5db74e0b-8be8-4b47-b386-faab56dffa9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e90cbf04e0282454658e6324f0ba6600a99cb718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695288"
---
# <a name="position-labels-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="f72e1-102">Placer des étiquettes dans un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="f72e1-102">Position Labels in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f72e1-103">Chaque type de graphique ayant une forme différente, les étiquettes de point de données sont positionnées de manière optimale de façon à ne pas interférer sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="f72e1-103">Because each chart type has a different shape, data point labels are placed in an optimal location so as not to interfere on the chart.</span></span> <span data-ttu-id="f72e1-104">La position par défaut des étiquettes varie en fonction du type de graphique :</span><span class="sxs-lookup"><span data-stu-id="f72e1-104">The default position of the labels depends varies with the chart type:</span></span>  
  
-   <span data-ttu-id="f72e1-105">Sur les graphiques empilés, les étiquettes peuvent être uniquement être positionnées à l'intérieur de la série.</span><span class="sxs-lookup"><span data-stu-id="f72e1-105">On stacked charts, labels can only be positioned inside the series.</span></span>  
  
-   <span data-ttu-id="f72e1-106">Sur les graphiques en entonnoir ou en pyramide, les étiquettes sont placées à l'extérieur d'une colonne.</span><span class="sxs-lookup"><span data-stu-id="f72e1-106">On funnel or pyramid charts, labels are placed on the outside in a column.</span></span>  
  
-   <span data-ttu-id="f72e1-107">Sur les graphiques à secteurs, les étiquettes sont placées à l'intérieur des différents secteurs.</span><span class="sxs-lookup"><span data-stu-id="f72e1-107">On pie charts, labels are placed inside the individual slices on a pie chart.</span></span>  
  
-   <span data-ttu-id="f72e1-108">Sur les graphiques à barres, les étiquettes sont placées en dehors des barres qui représentent les points de données.</span><span class="sxs-lookup"><span data-stu-id="f72e1-108">On bar charts, labels are placed outside of the bars that represent data points.</span></span>  
  
-   <span data-ttu-id="f72e1-109">Sur les graphiques polaires, les étiquettes sont placées en dehors de la zone circulaire qui représente les points de données.</span><span class="sxs-lookup"><span data-stu-id="f72e1-109">On polar charts, labels are placed outside of the circular area that represents data points.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-position-of-point-labels-in-a-pie-chart"></a><span data-ttu-id="f72e1-110">Pour modifier la position des étiquettes de point dans un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="f72e1-110">To change the position of point labels in a Pie chart</span></span>  
  
1.  <span data-ttu-id="f72e1-111">Créez un graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="f72e1-111">Create a pie chart.</span></span>  
  
2.  <span data-ttu-id="f72e1-112">Dans l’aire de conception, cliquez avec le bouton droit sur le graphique et sélectionnez **Afficher les étiquettes de données**.</span><span class="sxs-lookup"><span data-stu-id="f72e1-112">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="f72e1-113">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f72e1-113">Open the Properties pane.</span></span> <span data-ttu-id="f72e1-114">Sous l'onglet **Affichage** , cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f72e1-114">On the **View** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f72e1-115">Dans l'aire de conception, cliquez sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="f72e1-115">On the design surface, click the chart.</span></span> <span data-ttu-id="f72e1-116">Les propriétés du graphique sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f72e1-116">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="f72e1-117">Dans la section **Général** , développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="f72e1-117">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="f72e1-118">Une liste des attributs du graphique à secteurs s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f72e1-118">A list of attributes for the pie chart is displayed.</span></span>  
  
6.  <span data-ttu-id="f72e1-119">Sélectionnez une valeur pour la propriété PieLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="f72e1-119">Select a value for the PieLabelStyle property.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-funnel-or-pyramid-chart"></a><span data-ttu-id="f72e1-120">Pour modifier la position des étiquettes de point dans un graphique en entonnoir ou en pyramide</span><span class="sxs-lookup"><span data-stu-id="f72e1-120">To change the position of point labels in a Funnel or Pyramid chart</span></span>  
  
1.  <span data-ttu-id="f72e1-121">Créez un graphique en entonnoir ou en pyramide.</span><span class="sxs-lookup"><span data-stu-id="f72e1-121">Create a funnel or pyramid chart.</span></span>  
  
2.  <span data-ttu-id="f72e1-122">Dans l’aire de conception, cliquez avec le bouton droit sur le graphique et sélectionnez **Afficher les étiquettes de données**.</span><span class="sxs-lookup"><span data-stu-id="f72e1-122">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="f72e1-123">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f72e1-123">Open the Properties pane.</span></span> <span data-ttu-id="f72e1-124">Sous l'onglet **Affichage** , cliquez sur **Propriétés**</span><span class="sxs-lookup"><span data-stu-id="f72e1-124">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="f72e1-125">Dans l'aire de conception, cliquez sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="f72e1-125">On the design surface, click the chart.</span></span> <span data-ttu-id="f72e1-126">Les propriétés du graphique sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f72e1-126">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="f72e1-127">Dans la section **Général** , développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="f72e1-127">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="f72e1-128">Une liste des attributs du graphique en entonnoir s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f72e1-128">A list of attributes for the funnel chart is displayed.</span></span>  
  
6.  <span data-ttu-id="f72e1-129">Pour un graphique en entonnoir, sélectionnez une valeur pour la propriété FunnelLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="f72e1-129">For a funnel chart, select a value for the FunnelLabelStyle property.</span></span> <span data-ttu-id="f72e1-130">Pour un graphique en pyramide, sélectionnez une valeur pour la propriété PyramidLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="f72e1-130">For a pyramid chart, select a value for the PyramidLabelStyle property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f72e1-131">Quand cette propriété a une valeur `OutsideInColumn`, les étiquettes sont dessinées dans une colonne verticale.</span><span class="sxs-lookup"><span data-stu-id="f72e1-131">When this property is set to a value `OutsideInColumn`, the labels are drawn in a vertical column.</span></span> <span data-ttu-id="f72e1-132">Il est impossible de modifier la position de la colonne.</span><span class="sxs-lookup"><span data-stu-id="f72e1-132">There is no way to change the position of the column.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-bar-chart"></a><span data-ttu-id="f72e1-133">Pour modifier la position des étiquettes de point dans un graphique à barres</span><span class="sxs-lookup"><span data-stu-id="f72e1-133">To change the position of point labels in a Bar chart</span></span>  
  
1.  <span data-ttu-id="f72e1-134">Créez un graphique à barres.</span><span class="sxs-lookup"><span data-stu-id="f72e1-134">Create a bar chart.</span></span>  
  
2.  <span data-ttu-id="f72e1-135">Dans l’aire de conception, cliquez avec le bouton droit sur le graphique et sélectionnez **Afficher les étiquettes de données**.</span><span class="sxs-lookup"><span data-stu-id="f72e1-135">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="f72e1-136">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f72e1-136">Open the Properties pane.</span></span> <span data-ttu-id="f72e1-137">Sous l'onglet **Affichage** , cliquez sur **Propriétés**</span><span class="sxs-lookup"><span data-stu-id="f72e1-137">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="f72e1-138">Dans l'aire de conception, cliquez sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="f72e1-138">On the design surface, click the chart.</span></span> <span data-ttu-id="f72e1-139">Les propriétés du graphique sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f72e1-139">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="f72e1-140">Dans la section **Général** , développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="f72e1-140">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="f72e1-141">Une liste des attributs du graphique à barres s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f72e1-141">A list of attributes for the bar chart is displayed.</span></span>  
  
6.  <span data-ttu-id="f72e1-142">Sélectionnez une valeur pour la propriété BarLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="f72e1-142">Select a value for the BarLabelStyle property.</span></span>  
  
 <span data-ttu-id="f72e1-143">Quand le style de l’étiquette de la barre a la valeur `Outside`, les étiquettes sont placées en dehors de la barre, dans la mesure où elles s’ajustent à la zone du graphique.</span><span class="sxs-lookup"><span data-stu-id="f72e1-143">When the bar label style is set to `Outside`, the labels will be placed outside of the bar, as long as it fits in the chart area.</span></span> <span data-ttu-id="f72e1-144">Si l'étiquette ne peut pas être placée en dehors de barre mais dans la zone du graphique, elle est placée à l'intérieur de la barre à la position la plus proche de l'extrémité de la barre.</span><span class="sxs-lookup"><span data-stu-id="f72e1-144">If the label cannot be placed outside of the bar but inside of the chart area, the label is placed inside the bar at the position closest to the end of the bar.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-an-area-column-line-or-scatter-chart"></a><span data-ttu-id="f72e1-145">Pour modifier la position des étiquettes de point dans un graphique à secteurs, un histogramme, un graphique en courbes ou un graphique à nuage de points</span><span class="sxs-lookup"><span data-stu-id="f72e1-145">To change the position of point labels in an Area, Column, Line or Scatter chart</span></span>  
  
1.  <span data-ttu-id="f72e1-146">Créez un graphique à secteurs, un histogramme, un graphique en courbes ou un graphique à nuage de points.</span><span class="sxs-lookup"><span data-stu-id="f72e1-146">Create an Area, Column, Line or Scatter chart.</span></span>  
  
2.  <span data-ttu-id="f72e1-147">Dans l’aire de conception, cliquez avec le bouton droit sur le graphique et sélectionnez **Afficher les étiquettes de données**.</span><span class="sxs-lookup"><span data-stu-id="f72e1-147">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="f72e1-148">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f72e1-148">Open the Properties pane.</span></span> <span data-ttu-id="f72e1-149">Sous l'onglet **Affichage** , cliquez sur **Propriétés**</span><span class="sxs-lookup"><span data-stu-id="f72e1-149">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="f72e1-150">Sur l'aire de conception, cliquez sur la série.</span><span class="sxs-lookup"><span data-stu-id="f72e1-150">On the design surface, click the series.</span></span> <span data-ttu-id="f72e1-151">Les propriétés de la série sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f72e1-151">The properties for the series are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="f72e1-152">Dans la section **Données** , développez le nœud **DataPoint** , puis le nœud **Étiquette**.</span><span class="sxs-lookup"><span data-stu-id="f72e1-152">In the **Data** section, expand the **DataPoint** node, then expand the **Label**node.</span></span>  
  
6.  <span data-ttu-id="f72e1-153">Sélectionnez une valeur pour la propriété Position.</span><span class="sxs-lookup"><span data-stu-id="f72e1-153">Select a value for the Position property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72e1-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f72e1-154">See Also</span></span>  
 <span data-ttu-id="f72e1-155">[Graphiques à secteurs &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f72e1-155">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f72e1-156">[Graphiques à barres &#40;Générateur de rapports et SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f72e1-156">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f72e1-157">[Mise en forme des étiquettes des axes sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f72e1-157">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f72e1-158">[Mettre en forme les étiquettes des axes en tant que dates ou devises &#40;Générateur de rapports et SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f72e1-158">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f72e1-159">[Afficher des étiquettes de points de données à l’extérieur d’un graphique à secteurs &#40;Générateur de rapports et SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f72e1-159">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f72e1-160">Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f72e1-160">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
  
  
