---
title: Ajouter des styles de biseau, du relief et des textures à un graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 737cfc80-b39e-497c-817b-b46693deb58f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 92c5d4af47b7889b9ba5ec421706848f8822075b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613325"
---
# <a name="add-bevel-emboss-and-texture-styles-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="e6038-102">Ajouter des styles de biseau, du relief et des textures à un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="e6038-102">Add Bevel, Emboss, and Texture Styles to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e6038-103">Lorsque vous utilisez certains types de graphiques, vous pouvez spécifier un effet de dessin pour augmenter l'impact visuel de votre graphique.</span><span class="sxs-lookup"><span data-stu-id="e6038-103">When using certain chart types, you can specify a drawing effect to increase the visual impact of your chart.</span></span> <span data-ttu-id="e6038-104">Ces effets de dessins ne sont appliquées qu'aux series de votre graphique.</span><span class="sxs-lookup"><span data-stu-id="e6038-104">These drawing effects are only applied to the series of your chart.</span></span> <span data-ttu-id="e6038-105">Ils n'ont pas d'effet sur les autres éléments d'un graphique.</span><span class="sxs-lookup"><span data-stu-id="e6038-105">They have no effect on any other chart element.</span></span>  
  
 <span data-ttu-id="e6038-106">Lorsque vous utilisez une variante d'un graphique en secteurs ou d'un graphique en anneau, vous pouvez spécifier une bordure arrondie ou un style de dessin concave semblable à des effets de biseau ou de relief qui peuvent être appliqués à une image.</span><span class="sxs-lookup"><span data-stu-id="e6038-106">When you are using any variant of a pie or doughnut chart, you can specify a soft edge or concave drawing style, similar to bevel or emboss effects that can be applied to an image.</span></span>  
  
 <span data-ttu-id="e6038-107">Lorsque vous utilisez une variante d'un graphique à barres ou d'un histogramme, vous pouvez appliquer des styles de texture, tels que cylindre, coin et clair à sombre, aux barres ou colonnes individuelles.</span><span class="sxs-lookup"><span data-stu-id="e6038-107">When you are using any variant of a bar or column chart, you can apply texture styles, such as cylinder, wedge, and light-to-dark, to the individual bars or columns.</span></span>  
  
 <span data-ttu-id="e6038-108">En plus de ces styles de dessin, vous pouvez ajouter des bordures et des ombres à de nombreux éléments de graphique pour donner une impression de profondeur.</span><span class="sxs-lookup"><span data-stu-id="e6038-108">In addition to these drawing styles, you can add borders and shadows to many chart elements to give the illusion of depth.</span></span> <span data-ttu-id="e6038-109">Pour plus d’informations sur d’autres méthodes de mise en forme du graphique, consultez [Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e6038-109">For more information on other ways to format the chart, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-bevel-or-emboss-styles-to-a-pie-or-doughnut-chart"></a><span data-ttu-id="e6038-110">Pour ajouter un style de biseau ou de relief à un graphique en secteurs ou un graphique en anneau</span><span class="sxs-lookup"><span data-stu-id="e6038-110">To add bevel or emboss styles to a pie or doughnut chart</span></span>  
  
1.  <span data-ttu-id="e6038-111">Sous l'onglet **Affichage** , sélectionnez **Propriétés** pour ouvrir le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="e6038-111">On the **View** tab, select **Properties** to open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="e6038-112">Sélectionnez le graphique à secteurs ou en anneau que vous souhaitez améliorer.</span><span class="sxs-lookup"><span data-stu-id="e6038-112">Select the pie or doughnut chart that you want to enhance.</span></span> <span data-ttu-id="e6038-113">Sélectionnez un champ de données dans le graphique, et pas le graphique entier.</span><span class="sxs-lookup"><span data-stu-id="e6038-113">Select a data field in the chart, not the entire chart.</span></span>  
  
3.  <span data-ttu-id="e6038-114">Dans le volet Propriétés, développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="e6038-114">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="e6038-115">Pour PieDrawingStyle, sélectionnez un style dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="e6038-115">For PieDrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6038-116">Vous ne pouvez pas avoir les styles 3D et de biseau ou de relief sur le même graphique.</span><span class="sxs-lookup"><span data-stu-id="e6038-116">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="e6038-117">Si vous avez activé le style 3D pour le graphique, la propriété PieDrawingStyle n’y figure pas.</span><span class="sxs-lookup"><span data-stu-id="e6038-117">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="e6038-118">![Graphique à secteurs avec style de dessin concave](../media/rs-piedrawingeffects-concave.gif "Graphique à secteurs avec style de dessin concave")</span><span class="sxs-lookup"><span data-stu-id="e6038-118">![Pie chart with concave drawing style](../media/rs-piedrawingeffects-concave.gif "Pie chart with concave drawing style")</span></span>  
  
### <a name="to-add-texture-styles-to-a-bar-or-column-chart"></a><span data-ttu-id="e6038-119">Pour ajouter des styles de texture à un graphique à barres ou un histogramme</span><span class="sxs-lookup"><span data-stu-id="e6038-119">To add texture styles to a bar or column chart</span></span>  
  
1.  <span data-ttu-id="e6038-120">Sélectionnez le graphique à barres ou l'histogramme que vous souhaitez améliorer.</span><span class="sxs-lookup"><span data-stu-id="e6038-120">Select the bar or column chart that you want to enhance.</span></span> <span data-ttu-id="e6038-121">Sélectionnez un champ de données dans le graphique, et pas le graphique entier.</span><span class="sxs-lookup"><span data-stu-id="e6038-121">Select a data field in the chart, not the entire chart.</span></span>  
  
2.  <span data-ttu-id="e6038-122">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="e6038-122">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="e6038-123">Développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="e6038-123">Expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="e6038-124">Pour DrawingStyle, sélectionnez un style dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="e6038-124">For DrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6038-125">Vous ne pouvez pas avoir les styles 3D et de biseau ou de relief sur le même graphique.</span><span class="sxs-lookup"><span data-stu-id="e6038-125">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="e6038-126">Si vous avez activé le style 3D pour le graphique, la propriété PieDrawingStyle n’y figure pas.</span><span class="sxs-lookup"><span data-stu-id="e6038-126">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="e6038-127">![Graphique à barres avec effet de dessin LightToDark](../media/rs-bardrawingeffects-lighttodark.gif "Graphique à barres avec effet de dessin LightToDark")</span><span class="sxs-lookup"><span data-stu-id="e6038-127">![Bar chart with LightToDark drawing effect](../media/rs-bardrawingeffects-lighttodark.gif "Bar chart with LightToDark drawing effect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6038-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6038-128">See Also</span></span>  
 <span data-ttu-id="e6038-129">[Graphiques à barres &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6038-129">[Bar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e6038-130">[Histogrammes &#40;Générateur de rapports et SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6038-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e6038-131">[Graphiques à secteurs &#40;Générateur de rapports et SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6038-131">[Pie Charts &#40;Report Builder and SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e6038-132">Mise en forme d’un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="e6038-132">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
