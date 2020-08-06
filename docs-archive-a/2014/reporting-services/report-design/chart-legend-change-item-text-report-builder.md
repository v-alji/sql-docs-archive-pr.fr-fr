---
title: Modifier le texte d’un élément de légende (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9e82fa34-17ed-494f-b25d-03dcc353a21f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d0bb721aa0ff03a5211065111c98605cd86e971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613320"
---
# <a name="change-the-text-of-a-legend-item-report-builder-and-ssrs"></a><span data-ttu-id="28fb5-102">Modifier le texte d'un élément de légende (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="28fb5-102">Change the Text of a Legend Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="28fb5-103">Lorsqu'un champ est placé dans la zone Valeurs du graphique, un élément de légende contenant le nom de ce champ est automatiquement généré.</span><span class="sxs-lookup"><span data-stu-id="28fb5-103">When a field is placed in the Values area of the chart, a legend item is automatically generated that contains the name of this field.</span></span> <span data-ttu-id="28fb5-104">Chaque élément de légende est relié à une série individuelle sur le graphique, à l’exception des graphiques à base de formes, pour lesquels la légende est reliée à des points de données individuels et non à des séries individuelles.</span><span class="sxs-lookup"><span data-stu-id="28fb5-104">Every legend item is connected to an individual series on the chart, with the exception of shape charts, where the legend is connected to individual data points instead of individual series.</span></span>  
  
 <span data-ttu-id="28fb5-105">Sur les graphiques à base de formes, vous pouvez modifier le texte d'un élément de légende pour afficher davantage d'informations sur des points de données individuels.</span><span class="sxs-lookup"><span data-stu-id="28fb5-105">On shape charts, you can change the text of a legend item to show more information about the individual data points.</span></span> <span data-ttu-id="28fb5-106">Par exemple, si vous souhaitez afficher les valeurs des points de données sous forme de pourcentages dans la légende, vous pouvez utiliser un mot clé tel que `#PERCENT`).</span><span class="sxs-lookup"><span data-stu-id="28fb5-106">For example, if you want to show the values of the data points as percentages in the legend, you can use a keyword such as `#PERCENT`.</span></span> <span data-ttu-id="28fb5-107">Vous pouvez ajouter des codes de format .NET Framework en plus des mots clés pour appliquer des formats de nombre et de date.</span><span class="sxs-lookup"><span data-stu-id="28fb5-107">You can append .NET Framework format codes in conjunction with keywords to apply numeric and date formats.</span></span> <span data-ttu-id="28fb5-108">Pour plus d’informations sur les mots clés, consultez [Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="28fb5-108">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="28fb5-109">![Graphique pointu](../media/sharpchart.png "Graphique pointu")</span><span class="sxs-lookup"><span data-stu-id="28fb5-109">![Sharp Chart](../media/sharpchart.png "Sharp Chart")</span></span>  
  
 <span data-ttu-id="28fb5-110">Sur les graphiques qui ne sont pas à base de formes, vous pouvez modifier le texte d'un élément de légende.</span><span class="sxs-lookup"><span data-stu-id="28fb5-110">On non-shape charts, you can change the text of a legend item.</span></span> <span data-ttu-id="28fb5-111">Par exemple, si votre nom de série est « Série1 », vous pouvez être amené à modifier le texte de manière à le rendre plus descriptif (« Ventes pour 2008 », par exemple).</span><span class="sxs-lookup"><span data-stu-id="28fb5-111">For example, if your series name is "Series1", you may want to change the text to something more descriptive like "Sales for 2008".</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-shape-chart"></a><span data-ttu-id="28fb5-112">Pour modifier le texte qui apparaît dans la légende sur un graphique à base de formes</span><span class="sxs-lookup"><span data-stu-id="28fb5-112">To modify the text that appears in the legend on a Shape chart</span></span>  
  
1.  <span data-ttu-id="28fb5-113">Cliquez avec le bouton droit sur une série ou sur un champ de la zone **Valeurs** et sélectionnez **Propriétés de la série**.</span><span class="sxs-lookup"><span data-stu-id="28fb5-113">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="28fb5-114">Cliquez sur **Légende** et tapez un mot clé dans la zone **Texte de légende personnalisé** .</span><span class="sxs-lookup"><span data-stu-id="28fb5-114">Click **Legend** and in the **Custom legend text** box, type a keyword.</span></span>  
  
 <span data-ttu-id="28fb5-115">Le tableau suivant donne des exemples de mots clés spécifiques aux graphiques à utiliser avec la propriété **Texte de légende personnalisé** .</span><span class="sxs-lookup"><span data-stu-id="28fb5-115">The following table provides examples of chart-specific keywords to use for the **Custom Legend Text** property.</span></span> <span data-ttu-id="28fb5-116">Pour plus d’informations sur les mots clés, consultez [Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="28fb5-116">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
|<span data-ttu-id="28fb5-117">Mot clé</span><span class="sxs-lookup"><span data-stu-id="28fb5-117">Keyword</span></span>|<span data-ttu-id="28fb5-118">Description</span><span class="sxs-lookup"><span data-stu-id="28fb5-118">Description</span></span>|<span data-ttu-id="28fb5-119">Exemple de texte apparaissant dans la légende</span><span class="sxs-lookup"><span data-stu-id="28fb5-119">Example of what appears as text in the legend</span></span>|  
|-------------|-----------------|---------------------------------------------------|  
|`#PERCENT{P1}`|<span data-ttu-id="28fb5-120">Affiche le pourcentage de la valeur totale à une décimale après la virgule.</span><span class="sxs-lookup"><span data-stu-id="28fb5-120">Displays the percentage of the total value to one decimal place.</span></span>|<span data-ttu-id="28fb5-121">85.0%</span><span class="sxs-lookup"><span data-stu-id="28fb5-121">85.0%</span></span>|  
|`#VALY`|<span data-ttu-id="28fb5-122">Affiche la valeur numérique réelle du champ de données.</span><span class="sxs-lookup"><span data-stu-id="28fb5-122">Displays the actual numeric value of the data field.</span></span>|<span data-ttu-id="28fb5-123">17000</span><span class="sxs-lookup"><span data-stu-id="28fb5-123">17000</span></span>|  
|`#VALY{C2}`|<span data-ttu-id="28fb5-124">Affiche la valeur numérique réelle du champ de données sous forme de devise avec deux décimales après la virgule.</span><span class="sxs-lookup"><span data-stu-id="28fb5-124">Displays the actual numeric value of the data field as a currency to two decimal places.</span></span>|<span data-ttu-id="28fb5-125">$17000.00</span><span class="sxs-lookup"><span data-stu-id="28fb5-125">$17000.00</span></span>|  
|`#AXISLABEL (#PERCENT{P0})`|<span data-ttu-id="28fb5-126">Affiche la représentation textuelle du champ de catégorie, suivie du pourcentage affiché par chaque catégorie sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="28fb5-126">Displays the text representation of the category field, followed by the percentage that each category displays on the chart.</span></span>|<span data-ttu-id="28fb5-127">Michael Blythe (85 %)</span><span class="sxs-lookup"><span data-stu-id="28fb5-127">Michael Blythe (85%)</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="28fb5-128">Le mot clé #AXISLABEL ne peut être évalué qu’au moment de l’exécution quand aucun champ n’est spécifié dans la zone **Groupes de séries** .</span><span class="sxs-lookup"><span data-stu-id="28fb5-128">The #AXISLABEL keyword can only be evaluated at run time when there is not a field specified in the **Series Groups** area.</span></span>  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-non-shape-chart"></a><span data-ttu-id="28fb5-129">Pour modifier le texte qui apparaît dans la légende sur un graphique qui n'est pas à base de formes</span><span class="sxs-lookup"><span data-stu-id="28fb5-129">To modify the text that appears in the legend on a non-Shape chart</span></span>  
  
1.  <span data-ttu-id="28fb5-130">Cliquez avec le bouton droit sur une série ou sur un champ de la zone **Valeurs** et sélectionnez **Propriétés de la série**.</span><span class="sxs-lookup"><span data-stu-id="28fb5-130">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="28fb5-131">Cliquez sur **Légende** et tapez une étiquette de légende dans la zone **Texte de légende personnalisé** .</span><span class="sxs-lookup"><span data-stu-id="28fb5-131">Click **Legend** and in the **Custom legend text** box, type a legend label.</span></span> <span data-ttu-id="28fb5-132">La série est actualisée en même temps que le texte.</span><span class="sxs-lookup"><span data-stu-id="28fb5-132">The series is updated with your text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28fb5-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28fb5-133">See Also</span></span>  
 <span data-ttu-id="28fb5-134">[Mise en forme de la légende sur un graphique &#40;Générateur de rapports et SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="28fb5-134">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="28fb5-135">[Mise en forme des couleurs des séries sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28fb5-135">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="28fb5-136">Masquer des éléments de légende sur le graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="28fb5-136">Hide Legend Items on the Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-hide-items-report-builder.md)  
  
  
