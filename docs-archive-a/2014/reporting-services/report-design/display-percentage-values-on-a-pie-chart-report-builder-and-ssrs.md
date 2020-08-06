---
title: Afficher des valeurs en pourcentage sur un graphique à secteurs (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb905fc1-5235-4773-a27e-b07be9318be5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2dee9017d34f2751b790b2e4928571160b597f1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605184"
---
# <a name="display-percentage-values-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="361ca-102">Afficher des valeurs en pourcentage dans un graphique à secteurs (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="361ca-102">Display Percentage Values on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="361ca-103">Par défaut, des catégories sont indiquées dans la légende pour identifier chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="361ca-103">By default, categories are shown in the legend to identify each value.</span></span> <span data-ttu-id="361ca-104">Si vous avez créé des étiquettes de catégories pour le graphique à secteurs, vous avez la possibilité d'afficher des pourcentages dans la légende.</span><span class="sxs-lookup"><span data-stu-id="361ca-104">If you have labeled the pie chart using category labels, you may want show percentages in the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="361ca-105">Pour afficher des valeurs en pourcentage sous forme d'étiquettes sur un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="361ca-105">To display percentage values as labels on a pie chart</span></span>  
  
1.  <span data-ttu-id="361ca-106">Ajoutez un graphique à secteurs à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="361ca-106">Add a pie chart to your report.</span></span> <span data-ttu-id="361ca-107">Pour plus d’informations, consultez [Ajouter un graphique à un rapport &#40;Générateur de rapports et SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="361ca-107">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="361ca-108">Dans l’aire de conception, cliquez avec le bouton droit sur le secteur, puis sélectionnez **Afficher les étiquettes de données**.</span><span class="sxs-lookup"><span data-stu-id="361ca-108">On the design surface, right-click on the pie and select **Show Data Labels**.</span></span> <span data-ttu-id="361ca-109">Les étiquettes de données doivent apparaître dans chaque secteur du graphique.</span><span class="sxs-lookup"><span data-stu-id="361ca-109">The data labels should appear within each slice on the pie chart.</span></span>  
  
3.  <span data-ttu-id="361ca-110">Dans l’aire de conception, cliquez avec le bouton droit sur les étiquettes, puis sélectionnez **Propriétés de l’étiquette de la série**.</span><span class="sxs-lookup"><span data-stu-id="361ca-110">On the design surface, right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="361ca-111">La boîte de dialogue **Propriétés de l'étiquette de la série** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="361ca-111">The **Series Label Properties** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="361ca-112">Type `#PERCENT` de l’option des **données d’étiquette** .</span><span class="sxs-lookup"><span data-stu-id="361ca-112">Type `#PERCENT` for the **Label data** option.</span></span>  
  
5.  <span data-ttu-id="361ca-113">(Facultatif) Pour indiquer le nombre de décimales affichées sur l’étiquette, tapez « #PERCENT{P*n*} », où *n* correspond au nombre de décimales à afficher.</span><span class="sxs-lookup"><span data-stu-id="361ca-113">(Optional) To specify how many decimal places the label shows, type "#PERCENT{P*n*}" where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="361ca-114">Par exemple, pour ne pas afficher de décimale, tapez « #PERCENT{P0} ».</span><span class="sxs-lookup"><span data-stu-id="361ca-114">For example, to display no decimal places, type "#PERCENT{P0}".</span></span>  
  
### <a name="to-display-percentage-values-in-the-legend-of-a-pie-chart"></a><span data-ttu-id="361ca-115">Pour afficher des valeurs en pourcentage dans la légende d'un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="361ca-115">To display percentage values in the legend of a pie chart</span></span>  
  
1.  <span data-ttu-id="361ca-116">Dans l’aire de conception, cliquez avec le bouton droit sur le graphique à secteurs, puis sélectionnez **Propriétés de la série**.</span><span class="sxs-lookup"><span data-stu-id="361ca-116">On the design surface, right-click on the pie chart and select **Series Properties**.</span></span> <span data-ttu-id="361ca-117">La boîte de dialogue **Propriétés de la série** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="361ca-117">The **Series Properties** dialog box displays.</span></span>  
  
2.  <span data-ttu-id="361ca-118">Dans **légende**, tapez `#PERCENT` pour la propriété **texte de légende personnalisé** .</span><span class="sxs-lookup"><span data-stu-id="361ca-118">In **Legend**, type `#PERCENT` for the **Custom legend text** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="361ca-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="361ca-119">See Also</span></span>  
 <span data-ttu-id="361ca-120">[Graphiques à secteurs &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="361ca-120">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="361ca-121">[Mise en forme de la légende sur un graphique &#40;Générateur de rapports et SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="361ca-121">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="361ca-122">[Afficher des étiquettes de points de données à l’extérieur d’un graphique à secteurs &#40;Générateur de rapports et SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="361ca-122">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="361ca-123">Regrouper des petits secteurs sur un graphique à secteurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="361ca-123">Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
