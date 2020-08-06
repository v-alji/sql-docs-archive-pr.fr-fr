---
title: Ajouter des effets 3D à un graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab9625d8-6557-4a4d-8123-eefa7c066ff5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f4fcd90452e32b760bc446ac5d085ed00520a2f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613328"
---
# <a name="add-3d-effects-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="2263b-102">Ajouter des effets 3D à un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="2263b-102">Add 3D Effects to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2263b-103">Des effets 3D (en trois dimensions) peuvent être utilisés pour donner de la profondeur et augmenter l'impact visuel d'un graphique.</span><span class="sxs-lookup"><span data-stu-id="2263b-103">Three-dimensional (3D) effects can be used to provide depth and add visual impact to your chart.</span></span> <span data-ttu-id="2263b-104">Par exemple, si vous voulez insister sur un secteur particulier d'un graphique à secteurs éclatés, vous pouvez faire pivoter le graphique et changer sa perspective pour que les lecteurs remarquent ce secteur en premier.</span><span class="sxs-lookup"><span data-stu-id="2263b-104">For example, if you want to emphasize a particular slice of an exploded pie chart, you can rotate and change the perspective of the chart so that people notice that slice first.</span></span> <span data-ttu-id="2263b-105">Lorsque des effets 3D sont appliqués à votre graphique, les couleurs de dégradé et les styles de hachurage sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="2263b-105">When 3D effects are applied to your chart, all gradient colors and hatching styles are disabled.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-3d-effects-to-a-range-area-line-scatter-or-polar-chart"></a><span data-ttu-id="2263b-106">Pour appliquer des effets 3D à un graphique d'étendue, en aires, en courbes, en nuage de points ou polaire</span><span class="sxs-lookup"><span data-stu-id="2263b-106">To apply 3D effects to a Range, Area, Line, Scatter or Polar chart</span></span>  
  
1.  <span data-ttu-id="2263b-107">Cliquez avec le bouton droit en un point quelconque de la zone de graphique, puis sélectionnez **Effets 3D**.</span><span class="sxs-lookup"><span data-stu-id="2263b-107">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="2263b-108">La boîte de dialogue **Propriétés de la zone de graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="2263b-108">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="2263b-109">Dans **Options 3D**, sélectionnez l’option **Afficher en 3D** .</span><span class="sxs-lookup"><span data-stu-id="2263b-109">In **3D Options**, select the **Enable 3D** option.</span></span>  
  
3.  <span data-ttu-id="2263b-110">(Facultatif) Dans **Options 3D**, vous pouvez définir diverses propriétés liées aux angles et options de scène 3D.</span><span class="sxs-lookup"><span data-stu-id="2263b-110">(Optional) In **3D Options**, you can set a variety of properties relating to 3D angles and scene options.</span></span> <span data-ttu-id="2263b-111">Pour plus d’informations sur ces propriétés, consultez [Effets 3D, de relief et autres dans un graphique &#40;Générateur de rapports et SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2263b-111">For more information about these properties, see [3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md).</span></span>  
  
4.  <span data-ttu-id="2263b-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2263b-112">Click **OK**.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-funnel-chart"></a><span data-ttu-id="2263b-113">Pour appliquer des effets 3D à un graphique en entonnoir</span><span class="sxs-lookup"><span data-stu-id="2263b-113">To apply 3D effects to a Funnel chart</span></span>  
  
1.  <span data-ttu-id="2263b-114">Cliquez avec le bouton droit en un point quelconque de la zone de graphique, puis sélectionnez **Effets 3D**.</span><span class="sxs-lookup"><span data-stu-id="2263b-114">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="2263b-115">La boîte de dialogue **Propriétés de la zone de graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="2263b-115">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="2263b-116">Dans **Options 3D**, sélectionnez l’option **Afficher en 3D** .</span><span class="sxs-lookup"><span data-stu-id="2263b-116">In **3D Options**, select the **Enable 3D** option.</span></span> <span data-ttu-id="2263b-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2263b-117">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="2263b-118">(Facultatif) Pour personnaliser l'aspect visuel d'un graphique en entonnoir, vous pouvez en modifier les propriétés dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2263b-118">(Optional) To customize the funnel chart visual appearance, you can go to the Properties pane and change properties specific to the funnel chart.</span></span>  
  
    1.  <span data-ttu-id="2263b-119">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2263b-119">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="2263b-120">Dans l'aire de conception, cliquez en un point quelconque de l'entonnoir.</span><span class="sxs-lookup"><span data-stu-id="2263b-120">On the design surface, click anywhere on the funnel.</span></span> <span data-ttu-id="2263b-121">Les propriétés de la série du graphique en entonnoir sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2263b-121">The properties for the series of the funnel chart are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="2263b-122">Dans la section **Général** , développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="2263b-122">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
    4.  <span data-ttu-id="2263b-123">Pour la propriété **Funnel3DDrawingStyle** , indiquez si l’entonnoir s’affichera sous une forme circulaire ou carrée.</span><span class="sxs-lookup"><span data-stu-id="2263b-123">For the **Funnel3DDrawingStyle** property, select whether the funnel will be shown with as circular or square.</span></span>  
  
    5.  <span data-ttu-id="2263b-124">Pour la propriété **Funnel3DRotationAngle** , définissez une valeur comprise entre -10 et 10.</span><span class="sxs-lookup"><span data-stu-id="2263b-124">For the **Funnel3DRotationAngle** property, set a value between -10 and 10.</span></span> <span data-ttu-id="2263b-125">Celle-ci déterminera l'inclinaison appliquée au graphique en entonnoir 3D.</span><span class="sxs-lookup"><span data-stu-id="2263b-125">This will determine the degree of tilt that will be displayed on the 3D funnel chart.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-pie-chart"></a><span data-ttu-id="2263b-126">Pour appliquer des effets 3D à un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="2263b-126">To apply 3D effects to a Pie chart</span></span>  
  
1.  <span data-ttu-id="2263b-127">Cliquez avec le bouton droit en un point quelconque de la zone de graphique, puis sélectionnez Effets 3D.</span><span class="sxs-lookup"><span data-stu-id="2263b-127">Right-click anywhere inside the chart area and select 3D Effects.</span></span> <span data-ttu-id="2263b-128">La boîte de dialogue **Propriétés de la zone de graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="2263b-128">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="2263b-129">Dans **Options 3D**, sélectionnez l’option **Afficher en 3D** .</span><span class="sxs-lookup"><span data-stu-id="2263b-129">In **3D Options**, select the **Enable 3D** option.</span></span> <span data-ttu-id="2263b-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2263b-130">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="2263b-131">(Facultatif) Dans **Rotation**, tapez une valeur entière qui représente la rotation horizontale du graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="2263b-131">(Optional) In **Rotation**, type an integer value that represents the horizontal rotation of the pie chart.</span></span>  
  
4.  <span data-ttu-id="2263b-132">(Facultatif) Dans **Inclinaison**, tapez une valeur entière qui représente la rotation d’inclinaison verticale du graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="2263b-132">(Optional) In **Inclination**, type an integer value that represents the vertical tilt rotation of the pie chart.</span></span>  
  
5.  <span data-ttu-id="2263b-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2263b-133">Click **OK**.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-bar-or-column-chart"></a><span data-ttu-id="2263b-134">Pour appliquer des effets 3D à un graphique à barres ou histogrammes</span><span class="sxs-lookup"><span data-stu-id="2263b-134">To apply 3D effects to a Bar or Column chart</span></span>  
  
1.  <span data-ttu-id="2263b-135">Cliquez avec le bouton droit en un point quelconque de la zone de graphique, puis sélectionnez **Effets 3D**.</span><span class="sxs-lookup"><span data-stu-id="2263b-135">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="2263b-136">La boîte de dialogue **Propriétés de la zone de graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="2263b-136">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="2263b-137">Sélectionnez l’option **Afficher en 3D** .</span><span class="sxs-lookup"><span data-stu-id="2263b-137">Select the **Enable 3D** option.</span></span> <span data-ttu-id="2263b-138">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2263b-138">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="2263b-139">(Facultatif) Sélectionnez l’option **Activer le clustering des séries** .</span><span class="sxs-lookup"><span data-stu-id="2263b-139">(Optional) Select the **Enable series clustering** option.</span></span> <span data-ttu-id="2263b-140">Si le graphique contient plusieurs séries de barres ou d'histogrammes, cette option les affiche regroupées.</span><span class="sxs-lookup"><span data-stu-id="2263b-140">If your chart contains multiple bar or column chart series, this option will display the series as clustered.</span></span> <span data-ttu-id="2263b-141">Par défaut, les différentes séries de barres ou d'histogrammes sont représentées côte à côte.</span><span class="sxs-lookup"><span data-stu-id="2263b-141">By default, multiple bar or column series are shown side-by-side.</span></span>  
  
4.  <span data-ttu-id="2263b-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2263b-142">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2263b-143">(Facultatif) Pour ajouter des effets de cylindre à un graphique à barres ou histogrammes, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2263b-143">(Optional) To add cylinder effects to a bar or column chart, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="2263b-144">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2263b-144">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="2263b-145">Dans l'aire de conception, cliquez sur l'une des barres de la série.</span><span class="sxs-lookup"><span data-stu-id="2263b-145">On the design surface, click any of the bars in the series.</span></span> <span data-ttu-id="2263b-146">Les propriétés de la série sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2263b-146">The properties for the series are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="2263b-147">Dans la section **Général** , développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="2263b-147">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
    4.  <span data-ttu-id="2263b-148">Pour la propriété **DrawingStyle** , spécifiez la valeur **Cylindre** .</span><span class="sxs-lookup"><span data-stu-id="2263b-148">For the **DrawingStyle** property, specify the **Cylinder** value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2263b-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2263b-149">See Also</span></span>  
 <span data-ttu-id="2263b-150">[Effets 3D, de relief et autres dans un graphique &#40;Générateur de rapports et SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="2263b-150">[3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md) </span></span>  
 <span data-ttu-id="2263b-151">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2263b-151">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2263b-152">Graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="2263b-152">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
