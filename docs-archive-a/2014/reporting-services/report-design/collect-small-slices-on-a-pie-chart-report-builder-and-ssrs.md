---
title: Regrouper des petits secteurs sur un graphique à secteurs (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 21c2b8cb-b9ca-4bc0-bf49-50ba432562f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2302217843864115847aeb544d1c64727b8ad3a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610455"
---
# <a name="collect-small-slices-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="07d19-102">Regrouper des petits secteurs sur un graphique à secteurs (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="07d19-102">Collect Small Slices on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="07d19-103">Lorsqu'un graphique à secteurs présente de nombreux points de données, son aspect devient rapidement confus.</span><span class="sxs-lookup"><span data-stu-id="07d19-103">When pie charts display too many points of data, they begin to look cluttered.</span></span> <span data-ttu-id="07d19-104">Pour résoudre ce problème, vous pouvez afficher toutes les données inférieures à une certaine valeur dans un même secteur du graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="07d19-104">To resolve this issue, you can show all data that falls beneath a certain value as one slice on the pie chart.</span></span>  
  
 <span data-ttu-id="07d19-105">Pour regrouper plusieurs petits secteurs en un, vous devez en premier lieu décider si le seuil de regroupement des petits secteurs est exprimé sous forme de pourcentage du graphique à secteurs ou sous forme de valeur fixe.</span><span class="sxs-lookup"><span data-stu-id="07d19-105">To collect small slices into one slice, first decide whether your threshold for collecting small slices is measured as a percentage of the pie chart or as a fixed value.</span></span> <span data-ttu-id="07d19-106">Ensuite, définissez les propriétés CollectedThreshold et CollectedThresholdUsePercent. Définissez la propriété soit sur le pourcentage du graphique en-dessous duquel une valeur doit être regroupée, soit sur la valeur de données de seuil réel pour le regroupement.</span><span class="sxs-lookup"><span data-stu-id="07d19-106">Then set the CollectedThreshold and CollectedThresholdUsePercent properties.Set the CollectedThreshold property to either the percentage of the chart that a value must fall below to be collected, or the actual threshold data value for collection.</span></span> <span data-ttu-id="07d19-107">Affectez à la propriété CollectedThresholdUsePercent la `True` valeur pour utiliser un pourcentage ou `False` pour utiliser une valeur réelle.</span><span class="sxs-lookup"><span data-stu-id="07d19-107">Set the CollectedThresholdUsePercent property to `True` to use a percentage or `False` to use an actual value.</span></span>  
  
 <span data-ttu-id="07d19-108">Vous pouvez également regrouper des petits secteurs en un deuxième graphique à secteurs appelé à partir d'un secteur regroupé du premier graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="07d19-108">You can also collect small slices into a second pie chart that is called out from a collected slice of the first pie chart.</span></span> <span data-ttu-id="07d19-109">Le deuxième graphique à secteurs est alors tracé à droite du graphique à secteurs d'origine.</span><span class="sxs-lookup"><span data-stu-id="07d19-109">The second pie chart is drawn to the right of the original pie chart.</span></span>  
  
 <span data-ttu-id="07d19-110">Le regroupement de plusieurs secteurs en un n'est pas possible pour les graphiques en entonnoir ou en pyramide.</span><span class="sxs-lookup"><span data-stu-id="07d19-110">You cannot combine slices of funnel or pyramid charts into one slice.</span></span>  
  
 <span data-ttu-id="07d19-111">Un exemple de ce graphique est disponible sous forme d'exemple de rapport.</span><span class="sxs-lookup"><span data-stu-id="07d19-111">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="07d19-112">Pour plus d'informations sur le téléchargement de cet exemple de rapport et d'autres rapports, consultez [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Exemples de rapports du Générateur de rapports et du Concepteur de rapports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="07d19-112">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
### <a name="to-collect-small-slices-into-a-single-slice-on-a-pie-chart"></a><span data-ttu-id="07d19-113">Pour regrouper plusieurs petits secteurs en un sur un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="07d19-113">To collect small slices into a single slice on a pie chart</span></span>  
  
1.  <span data-ttu-id="07d19-114">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="07d19-114">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="07d19-115">Dans l'aire de conception, cliquez sur un secteur du graphique.</span><span class="sxs-lookup"><span data-stu-id="07d19-115">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="07d19-116">Les propriétés de la série sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="07d19-116">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="07d19-117">Dans la section **Général** , développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="07d19-117">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="07d19-118">Définissez la propriété CollectedStyle sur **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="07d19-118">Set the CollectedStyle property to **SingleSlice**.</span></span>  
  
5.  <span data-ttu-id="07d19-119">Définissez la valeur de seuil de regroupement et le type de seuil.</span><span class="sxs-lookup"><span data-stu-id="07d19-119">Set the collected threshold value and type of threshold.</span></span> <span data-ttu-id="07d19-120">Vous trouverez ci-dessous quelques manières parmi les plus courantes de définir des seuils de regroupement.</span><span class="sxs-lookup"><span data-stu-id="07d19-120">The following examples are common ways of setting collected thresholds.</span></span>  
  
    -   <span data-ttu-id="07d19-121">**Par pourcentage.**</span><span class="sxs-lookup"><span data-stu-id="07d19-121">**By percentage.**</span></span> <span data-ttu-id="07d19-122">Par exemple, pour regrouper en un secteur les secteurs de votre graphique inférieurs à 10 %, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="07d19-122">For example, to collect any slice on your pie chart that is less than 10% into a single slice:</span></span>  
  
         <span data-ttu-id="07d19-123">Affectez à la propriété CollectedThresholdUsePercent la valeur `True` .</span><span class="sxs-lookup"><span data-stu-id="07d19-123">Set the CollectedThresholdUsePercent property to `True`.</span></span>  
  
         <span data-ttu-id="07d19-124">Définissez la propriété CollectedThreshold sur **10**.</span><span class="sxs-lookup"><span data-stu-id="07d19-124">Set the CollectedThreshold property to **10**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="07d19-125">Si vous définissez CollectedStyle sur **valeur SingleSlice**, CollectedThreshold sur une valeur supérieure à **100**, et CollectedThresholdUsePercent est `True` , le graphique lèvera une exception, car il ne peut pas calculer un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="07d19-125">If you set CollectedStyle to **SingleSlice**, CollectedThreshold to a value greater than **100**, and CollectedThresholdUsePercent is `True`, the chart will throw an exception because it cannot calculate a percentage.</span></span> <span data-ttu-id="07d19-126">Pour résoudre ce problème, définissez la propriété CollectedThreshold sur une valeur inférieure à **100**.</span><span class="sxs-lookup"><span data-stu-id="07d19-126">To resolve this issue, set the CollectedThreshold to a value less than **100**.</span></span>  
  
    -   <span data-ttu-id="07d19-127">**Par valeur des données.**</span><span class="sxs-lookup"><span data-stu-id="07d19-127">**By data value.**</span></span> <span data-ttu-id="07d19-128">Par exemple, pour regrouper en un secteur les secteurs de votre graphique inférieurs à 5000, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="07d19-128">For example, to collect any slice on your pie chart that is less than 5000 into a single slice:</span></span>  
  
         <span data-ttu-id="07d19-129">Affectez à la propriété CollectedThresholdUsePercent la valeur `False` .</span><span class="sxs-lookup"><span data-stu-id="07d19-129">Set the CollectedThresholdUsePercent property to `False`.</span></span>  
  
         <span data-ttu-id="07d19-130">Définissez la propriété CollectedThreshold sur **5000**.</span><span class="sxs-lookup"><span data-stu-id="07d19-130">Set the CollectedThreshold property to **5000**.</span></span>  
  
6.  <span data-ttu-id="07d19-131">Définissez la propriété CollectedLabel sur une chaîne représentant l’étiquette de texte à afficher dans le secteur regroupé.</span><span class="sxs-lookup"><span data-stu-id="07d19-131">Set the CollectedLabel property to a string that represents the text label that will be shown on the collected slice.</span></span>  
  
7.  <span data-ttu-id="07d19-132">(Facultatif) Définissez les propriétés CollectedSliceExploded, CollectedColor, CollectedLegendText et CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="07d19-132">(Optional) Set the CollectedSliceExploded, CollectedColor, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="07d19-133">Ces propriétés modifient l'apparence, la couleur, le texte de l'étiquette, le texte de la légende et l'aspect des info-bulles du secteur obtenu.</span><span class="sxs-lookup"><span data-stu-id="07d19-133">These properties change the appearance, color, label text, legend text and tooltip aspects of the single slice.</span></span>  
  
### <a name="to-collect-small-slices-into-a-secondary-callout-pie-chart"></a><span data-ttu-id="07d19-134">Pour regrouper des petits secteurs dans un deuxième graphique à secteurs secondaire</span><span class="sxs-lookup"><span data-stu-id="07d19-134">To collect small slices into a secondary, callout pie chart</span></span>  
  
1.  <span data-ttu-id="07d19-135">Suivez les étapes 1 à 3 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="07d19-135">Follow Steps 1-3 from above.</span></span>  
  
2.  <span data-ttu-id="07d19-136">Définissez la propriété CollectedStyle sur **CollectedPie**.</span><span class="sxs-lookup"><span data-stu-id="07d19-136">Set the CollectedStyle property to **CollectedPie**.</span></span>  
  
3.  <span data-ttu-id="07d19-137">Définissez la propriété CollectedThresholdproperty sur une valeur représentant le seuil de regroupement des petits secteurs en un seul secteur.</span><span class="sxs-lookup"><span data-stu-id="07d19-137">Set the CollectedThresholdproperty to a value that represents the threshold at which small slices will be collected into one slice.</span></span> <span data-ttu-id="07d19-138">Lorsque la propriété CollectedStyle est définie sur **CollectedPie**, CollectedThresholdUsePercentproperty a toujours la valeur `True` , et le seuil collecté est toujours mesuré en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="07d19-138">When the CollectedStyle property is set to **CollectedPie**, the CollectedThresholdUsePercentproperty is always set to `True`, and the collected threshold is always measured in percent.</span></span>  
  
4.  <span data-ttu-id="07d19-139">(Facultatif) Définissez les propriétés CollectedColor, CollectedLabel, CollectedLegendText et CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="07d19-139">(Optional) Set the CollectedColor, CollectedLabel, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="07d19-140">Toutes les autres propriétés nommées « Collected » ne s'appliquent pas au regroupement de secteurs.</span><span class="sxs-lookup"><span data-stu-id="07d19-140">All other properties named "Collected" do not apply to the collected pie.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07d19-141">Le graphique à secteurs secondaire étant calculé selon les petits secteurs, il s'affiche uniquement sous forme d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="07d19-141">The secondary pie chart is calculated based on the small slices in your data so it will only appear in Preview.</span></span> <span data-ttu-id="07d19-142">Il n'apparaît pas dans l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="07d19-142">It does not appear on the design surface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07d19-143">Vous ne pouvez pas mettre en forme le graphique à secteurs secondaire.</span><span class="sxs-lookup"><span data-stu-id="07d19-143">You cannot format the secondary pie chart.</span></span> <span data-ttu-id="07d19-144">C'est pourquoi il est fortement recommandé de privilégier la première approche pour le regroupement de secteurs.</span><span class="sxs-lookup"><span data-stu-id="07d19-144">For this reason, it is strongly recommended to use the first approach when collecting pie slices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d19-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07d19-145">See Also</span></span>  
 <span data-ttu-id="07d19-146">[Graphiques à secteurs &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07d19-146">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07d19-147">[Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07d19-147">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07d19-148">[Afficher des étiquettes de points de données à l’extérieur d’un graphique à secteurs &#40;Générateur de rapports et SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07d19-148">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07d19-149">[Afficher des valeurs en pourcentage sur un graphique à secteurs &#40;Générateur de rapports et SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07d19-149">[Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="07d19-150">Ajouter des effets 3D à un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="07d19-150">Add 3D Effects to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-3d-effects-report-builder.md)  
  
  
