---
title: Mettre en surbrillance des données de graphique en ajoutant des franges (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: addd6137-4b6e-4e88-a7e8-9600fcd1ccce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01b0bb41a71daf9ac558ce8d8bb84480426870c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601889"
---
# <a name="highlight-chart-data-by-adding-strip-lines-report-builder-and-ssrs"></a><span data-ttu-id="90a54-102">Mettre en surbrillance des données de graphique en ajoutant des bandes (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="90a54-102">Highlight Chart Data by Adding Strip Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="90a54-103">Les franges sont des plages horizontales ou verticales qui assombrissent l'arrière-plan du graphique à intervalles réguliers ou personnalisés.</span><span class="sxs-lookup"><span data-stu-id="90a54-103">Strip lines, or strips, are horizontal or vertical ranges that shade the background of the chart in regular or custom intervals.</span></span> <span data-ttu-id="90a54-104">Vous pouvez utiliser des bandes pour obtenir les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="90a54-104">You can use strip lines to:</span></span>  
  
-   <span data-ttu-id="90a54-105">Améliorer la lisibilité des valeurs individuelles sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="90a54-105">Improve readability for looking up individual values on the chart.</span></span> <span data-ttu-id="90a54-106">Spécifiez des bandes à des intervalles réguliers pour séparer les points de données lors de la lecture du graphique.</span><span class="sxs-lookup"><span data-stu-id="90a54-106">Specify strip lines at regular intervals to help separate data points when reading the chart.</span></span>  
  
-   <span data-ttu-id="90a54-107">Mettre en surbrillance les dates qui arrivent à des intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="90a54-107">Highlight dates that occur at regular intervals.</span></span> <span data-ttu-id="90a54-108">Par exemple, dans un état des ventes, vous pouvez utiliser des bandes pour identifier les points des données indiquant les week-ends.</span><span class="sxs-lookup"><span data-stu-id="90a54-108">For example, in a sales report you might use strip lines to identify weekend data points.</span></span>  
  
-   <span data-ttu-id="90a54-109">Mettre en surbrillance une plage clé spécifique.</span><span class="sxs-lookup"><span data-stu-id="90a54-109">Highlight a specific key range.</span></span> <span data-ttu-id="90a54-110">À l'aide de l'exemple précédent, vous pouvez utiliser une bande pour mettre en surbrillance la plage la plus élevée des ventes qui se trouve entre 80 et 100 $.</span><span class="sxs-lookup"><span data-stu-id="90a54-110">Using the previous example, you can use one strip line to highlight the highest range of sales that is between $80-100.</span></span>  
  
 <span data-ttu-id="90a54-111">Les bandes ne sont pas applicables aux types de graphiques à base de forme ou polaires.</span><span class="sxs-lookup"><span data-stu-id="90a54-111">Strip lines are not applicable to Shape or Polar chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-interlaced-strip-lines-at-regular-intervals-on-a-chart"></a><span data-ttu-id="90a54-112">Pour afficher des franges entrelacées à des intervalles réguliers sur un graphique</span><span class="sxs-lookup"><span data-stu-id="90a54-112">To display interlaced strip lines at regular intervals on a chart</span></span>  
  
1.  <span data-ttu-id="90a54-113">Pour afficher des franges horizontales, cliquez avec le bouton droit sur l’axe vertical du graphique, puis cliquez sur **Propriétés de l’axe vertical**.</span><span class="sxs-lookup"><span data-stu-id="90a54-113">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="90a54-114">Pour afficher des franges verticales, cliquez avec le bouton droit sur l’axe horizontal du graphique, puis cliquez sur **Propriétés de l’axe horizontal**.</span><span class="sxs-lookup"><span data-stu-id="90a54-114">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="90a54-115">Sélectionnez l'option **Utiliser l'entrelacement** .</span><span class="sxs-lookup"><span data-stu-id="90a54-115">Select the **Use interlacing** option.</span></span> <span data-ttu-id="90a54-116">Des franges grises apparaîtront sur votre graphique.</span><span class="sxs-lookup"><span data-stu-id="90a54-116">Grey strip lines will appear on your chart.</span></span>  
  
3.  <span data-ttu-id="90a54-117">(Facultatif) Spécifiez une couleur pour les franges à l’aide de la liste déroulante **Couleur** adjacente.</span><span class="sxs-lookup"><span data-stu-id="90a54-117">(Optional) Specify a color for the strip lines using the adjacent **Color** drop-down list.</span></span>  
  
### <a name="to-display-interlaced-strip-lines-at-custom-intervals-on-a-chart"></a><span data-ttu-id="90a54-118">Pour afficher des franges entrelacées à des intervalles personnalisés sur un graphique</span><span class="sxs-lookup"><span data-stu-id="90a54-118">To display interlaced strip lines at custom intervals on a chart</span></span>  
  
1.  <span data-ttu-id="90a54-119">Pour afficher des franges horizontales, cliquez avec le bouton droit sur l’axe vertical du graphique, puis cliquez sur **Propriétés de l’axe vertical**.</span><span class="sxs-lookup"><span data-stu-id="90a54-119">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="90a54-120">Pour afficher des franges verticales, cliquez avec le bouton droit sur l’axe horizontal du graphique, puis cliquez sur **Propriétés de l’axe horizontal**.</span><span class="sxs-lookup"><span data-stu-id="90a54-120">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
     <span data-ttu-id="90a54-121">Les propriétés de l'axe s'affichent dans la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="90a54-121">The axis properties are displayed in the Properties window.</span></span>  
  
2.  <span data-ttu-id="90a54-122">Dans la section **Apparence** du volet Propriétés, pour la propriété StripLines, cliquez sur le bouton Modifier la collection (...) pour ouvrir l’**Éditeur de collections ChartStripLine**.</span><span class="sxs-lookup"><span data-stu-id="90a54-122">In the **Appearance** section of the Properties pane, for the StripLines property, click the Edit Collection (...) button to open the **ChartStripLine Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="90a54-123">Cliquez sur **Ajouter** pour ajouter une nouvelle bande à la collection.</span><span class="sxs-lookup"><span data-stu-id="90a54-123">Click **Add** to add a new strip line to the collection.</span></span>  
  
4.  <span data-ttu-id="90a54-124">Cliquez sur StripWidth pour spécifier la largeur de la bande, mesurée en pouces sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="90a54-124">Click StripWidth to specify the width of the strip line, measured in inches on the report.</span></span> <span data-ttu-id="90a54-125">Si vous mettez en surbrillance des dates ou des heures, cliquez sur StripWidthType, puis sélectionnez un intervalle de temps.</span><span class="sxs-lookup"><span data-stu-id="90a54-125">If you are highlighting dates or times, click StripWidthType and select a time interval.</span></span>  
  
5.  <span data-ttu-id="90a54-126">Tapez une valeur ou une expression pour Intervalle afin de spécifier la fréquence à laquelle la bande se répétera.</span><span class="sxs-lookup"><span data-stu-id="90a54-126">Type a value or expression for the Interval to specify how often the strip line will repeat.</span></span>  <span data-ttu-id="90a54-127">Par exemple, si vous spécifiez un intervalle de 10, et que votre largeur de bande est de 5, les bandes s'afficheront aux valeurs 0 à 5, 15 à 20, 30 à 35, etc.</span><span class="sxs-lookup"><span data-stu-id="90a54-127">For example, if you specify an interval of 10, and your strip line width is 5, strip lines will display at values of 0 to 5, 15 to 20, 30 to 35, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90a54-128">Par défaut, Intervalle a la valeur Auto, ce qui signifie que le graphique ne calculera pas d’intervalle pour les bandes personnalisées.</span><span class="sxs-lookup"><span data-stu-id="90a54-128">By default, Interval is set to Auto, which means the chart will not calculate an interval for custom strip lines.</span></span> <span data-ttu-id="90a54-129">Le graphique ne calcule des intervalles pour les bandes que si une valeur d'intervalle est définie.</span><span class="sxs-lookup"><span data-stu-id="90a54-129">The chart only calculates intervals for strip lines if an interval value is set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a54-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90a54-130">See Also</span></span>  
 <span data-ttu-id="90a54-131">[Mise en forme des étiquettes des axes sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="90a54-131">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="90a54-132">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="90a54-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="90a54-133">Ajouter une moyenne mobile à un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="90a54-133">Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md)  
  
  
