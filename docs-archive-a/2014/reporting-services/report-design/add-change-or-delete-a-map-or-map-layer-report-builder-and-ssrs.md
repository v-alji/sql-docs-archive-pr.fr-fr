---
title: Ajouter, modifier ou supprimer une carte ou une couche (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10526"
- sql12.rtp.rptdesigner.maptilelayerproperties.general.f1
- "10529"
- "10525"
- "10535"
- sql12.rtp.rptdesigner.mappolygonlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layervisibility.f1
- sql12.rtp.rptdesigner.mappointlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layerfilters.f1
- "10524"
- sql12.rtp.rptdesigner.maplayerproperties.general.f1
- sql12.rtp.rptdesigner.maplinelayerproperties.general.f1
- "10532"
- "10528"
- "10527"
- sql12.rtp.rptdesigner.maplayerproperties.analyticaldata.f1
ms.assetid: 6e89815e-187e-45bf-bf63-3d5c4a246360
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4e9fd178d36ee3322c0bd94dd44d621439139b71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605216"
---
# <a name="add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs"></a><span data-ttu-id="0f812-102">Ajouter, modifier ou supprimer une carte ou une couche (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="0f812-102">Add, Change, or Delete a Map or Map Layer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0f812-103">Une carte est un ensemble de couches.</span><span class="sxs-lookup"><span data-stu-id="0f812-103">A map is a collection of layers.</span></span> <span data-ttu-id="0f812-104">Lorsque vous ajoutez une carte à un rapport, vous définissez la première couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-104">When you add a map to a report, you define the first layer.</span></span> <span data-ttu-id="0f812-105">Vous pouvez créer des couches supplémentaires à l'aide de l'Assistant Couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-105">You can create additional layers by using the map layer wizard.</span></span>  
  
 <span data-ttu-id="0f812-106">Pour ajouter, supprimer ou modifier des options pour une couche, la méthode la plus simple consiste à utiliser l'Assistant Couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-106">The easiest way to add, remove, or change options for a layer is to use the map layer wizard.</span></span> <span data-ttu-id="0f812-107">Vous pouvez également modifier manuellement des options dans le volet Carte.</span><span class="sxs-lookup"><span data-stu-id="0f812-107">You can also change options manually from the Map pane.</span></span> <span data-ttu-id="0f812-108">Pour afficher le volet **Carte** , cliquez dans la carte sur l’aire de conception du rapport.</span><span class="sxs-lookup"><span data-stu-id="0f812-108">To display the **Map** pane, click in the map on the report design surface.</span></span> <span data-ttu-id="0f812-109">L'illustration suivante affiche les différentes parties du volet :</span><span class="sxs-lookup"><span data-stu-id="0f812-109">The following figure displays the parts of the pane:</span></span>  
  
 <span data-ttu-id="0f812-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span><span class="sxs-lookup"><span data-stu-id="0f812-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span></span>  
  
 <span data-ttu-id="0f812-111">Les couches sont dessinées de bas en haut, dans l'ordre dans lequel elles apparaissent dans le volet Carte.</span><span class="sxs-lookup"><span data-stu-id="0f812-111">Map layers are drawn from bottom to top in the order that they appear in the Map pane.</span></span> <span data-ttu-id="0f812-112">Dans l'illustration ci-dessus, la couche de mosaïques est dessinée en premier et la couche de polygones en dernier.</span><span class="sxs-lookup"><span data-stu-id="0f812-112">In the previous figure, the tile layer is drawn first and the polygon layer is drawn last.</span></span> <span data-ttu-id="0f812-113">Les couches dessinées ultérieurement peuvent masquer des éléments cartographiques de couches dessinées antérieurement.</span><span class="sxs-lookup"><span data-stu-id="0f812-113">Layers that are drawn later might hide map elements on layers that are drawn earlier.</span></span> <span data-ttu-id="0f812-114">Vous pouvez modifier l'ordre des couches à l'aide des touches de direction de la barre d'outils du volet Carte.</span><span class="sxs-lookup"><span data-stu-id="0f812-114">You can change the order of layers by using the arrow keys on the Map pane toolbar.</span></span> <span data-ttu-id="0f812-115">Pour afficher ou masquer des couches, activez ou désactivez l'icône de visibilité.</span><span class="sxs-lookup"><span data-stu-id="0f812-115">To show or hide layers, toggle the visibility icon.</span></span> <span data-ttu-id="0f812-116">Vous pouvez modifier la transparence d’une couche dans la `Visibility` page de la boîte de dialogue Propriétés des **données de couche** .</span><span class="sxs-lookup"><span data-stu-id="0f812-116">You can change the transparency of a layer on the `Visibility` page of the **Layer Data** properties dialog box.</span></span>  
  
 <span data-ttu-id="0f812-117">Le tableau suivant présente les icônes de la barre d’outils du volet **Carte** .</span><span class="sxs-lookup"><span data-stu-id="0f812-117">The following table displays the toolbar icons for the **Map** pane.</span></span>  
  
|<span data-ttu-id="0f812-118">Symbole</span><span class="sxs-lookup"><span data-stu-id="0f812-118">Symbol</span></span>|<span data-ttu-id="0f812-119">Description</span><span class="sxs-lookup"><span data-stu-id="0f812-119">Description</span></span>|<span data-ttu-id="0f812-120">Quand l’utiliser</span><span class="sxs-lookup"><span data-stu-id="0f812-120">When to use</span></span>|  
|------------|-----------------|-----------------|  
|<span data-ttu-id="0f812-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span><span class="sxs-lookup"><span data-stu-id="0f812-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span></span>|<span data-ttu-id="0f812-122">Assistant Couche</span><span class="sxs-lookup"><span data-stu-id="0f812-122">Map Layer Wizard</span></span>|<span data-ttu-id="0f812-123">Pour ajouter une couche à l'aide d’un Assistant, cliquez sur **Assistant Nouvelle couche**.</span><span class="sxs-lookup"><span data-stu-id="0f812-123">To add a layer by using a wizard, click **New layer wizard**.</span></span>|  
|<span data-ttu-id="0f812-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span><span class="sxs-lookup"><span data-stu-id="0f812-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span></span>|<span data-ttu-id="0f812-125">Ajouter une couche</span><span class="sxs-lookup"><span data-stu-id="0f812-125">Add Layer</span></span>|<span data-ttu-id="0f812-126">Pour ajouter une couche manuellement, cliquez sur **Ajouter une couche**, puis sur le type de couche à ajouter.</span><span class="sxs-lookup"><span data-stu-id="0f812-126">To manually add a layer, click **Add Layer**, and then click the type of map layer to add.</span></span>|  
|<span data-ttu-id="0f812-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span><span class="sxs-lookup"><span data-stu-id="0f812-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span></span>|<span data-ttu-id="0f812-128">Couche de polygones</span><span class="sxs-lookup"><span data-stu-id="0f812-128">Polygon Layer</span></span>|<span data-ttu-id="0f812-129">Ajoutez une couche qui affiche des zones ou des formes basées sur des jeux de coordonnées de polygones.</span><span class="sxs-lookup"><span data-stu-id="0f812-129">Add a map layer that displays areas or shapes that are based sets of polygon coordinates.</span></span>|  
|<span data-ttu-id="0f812-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span><span class="sxs-lookup"><span data-stu-id="0f812-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span></span>|<span data-ttu-id="0f812-131">Couche de lignes</span><span class="sxs-lookup"><span data-stu-id="0f812-131">Line Layer</span></span>|<span data-ttu-id="0f812-132">Ajoutez une couche qui affiche des chemins ou des itinéraires basés sur des jeux de coordonnées de lignes.</span><span class="sxs-lookup"><span data-stu-id="0f812-132">Add a map layer that displays paths or routes that are based on sets of line coordinates.</span></span>|  
|<span data-ttu-id="0f812-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span><span class="sxs-lookup"><span data-stu-id="0f812-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span></span>|<span data-ttu-id="0f812-134">Couche de points</span><span class="sxs-lookup"><span data-stu-id="0f812-134">Point Layer</span></span>|<span data-ttu-id="0f812-135">Ajoutez une couche qui affiche des emplacements basés sur des jeux de coordonnées de points.</span><span class="sxs-lookup"><span data-stu-id="0f812-135">Add a map layer that displays locations that are based on sets of point coordinates.</span></span>|  
|<span data-ttu-id="0f812-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span><span class="sxs-lookup"><span data-stu-id="0f812-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span></span>|<span data-ttu-id="0f812-137">Couche de mosaïques</span><span class="sxs-lookup"><span data-stu-id="0f812-137">Tile Layer</span></span>|<span data-ttu-id="0f812-138">Ajoutez une couche qui affiche des mosaïques Bing correspondant à la zone de la vue cartographique actuelle telle que définie par la fenêtre d'affichage.</span><span class="sxs-lookup"><span data-stu-id="0f812-138">Add a map layer that displays Bing Map tiles that correspond to the current map view area that is defined by the viewport.</span></span>|  
  
 <span data-ttu-id="0f812-139">La zone de la vue cartographique est affichée au bas du volet Carte.</span><span class="sxs-lookup"><span data-stu-id="0f812-139">At the bottom of the Map pane is the Map view area.</span></span> <span data-ttu-id="0f812-140">Pour modifier le centre ou les options de zoom de la carte, utilisez les touches de direction pour ajuster le centre d'affichage et le curseur pour ajuster le niveau de zoom.</span><span class="sxs-lookup"><span data-stu-id="0f812-140">To change the center or zoom options for the map, use the arrow keys to adjust the view center and the slider to adjust the zoom level.</span></span>  
  
 <span data-ttu-id="0f812-141">Pour plus d’informations sur les couches, consultez [Cartes &#40;Générateur de rapports et SSRS&#41;](maps-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f812-141">For more information about layers, see [Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-add-a-layer-from-the-map-layer-wizard"></a><a name="AddLayer"></a> <span data-ttu-id="0f812-142">Pour ajouter une couche à partir de l’Assistant Couche</span><span class="sxs-lookup"><span data-stu-id="0f812-142">To add a layer from the map layer wizard</span></span>  
  
-   <span data-ttu-id="0f812-143">Dans le ruban, dans le menu **Insérer** , cliquez sur **Carte**, puis sur **Carte Wizard**.</span><span class="sxs-lookup"><span data-stu-id="0f812-143">From the Ribbon, on the **Insert** menu, click **Map**, and then click **Map Wizard.**</span></span> <span data-ttu-id="0f812-144">L'Assistant vous permet d'ajouter une couche à la carte existante.</span><span class="sxs-lookup"><span data-stu-id="0f812-144">The wizard enables you to add a layer to the existing map.</span></span> <span data-ttu-id="0f812-145">La plupart des pages des Assistants Carte et Couche sont identiques.</span><span class="sxs-lookup"><span data-stu-id="0f812-145">Most wizard pages are identical between the map wizard and the map layer wizard.</span></span>  
  
     <span data-ttu-id="0f812-146">Pour plus d’informations, consultez [Assistant Carte et Assistant Couche &#40;Générateur de rapports et SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f812-146">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-change-options-for-a-layer-by-using-the-map-layer-wizard"></a><a name="ChangeLayer"></a> <span data-ttu-id="0f812-147">Pour modifier les options d’une couche à l’aide de l’Assistant Couche</span><span class="sxs-lookup"><span data-stu-id="0f812-147">To change options for a layer by using the map layer wizard</span></span>  
  
-   <span data-ttu-id="0f812-148">Exécutez l'Assistant Couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-148">Run the map layer wizard.</span></span> <span data-ttu-id="0f812-149">Cet Assistant vous permet de modifier des options pour une couche que vous avez créée à l'aide de l'Assistant Couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-149">This wizard enables you to change options for a layer that you created by using the map layer wizard.</span></span> <span data-ttu-id="0f812-150">Dans le volet Carte, cliquez avec le bouton droit sur la couche, puis dans la barre d’outils, cliquez sur le bouton de l’Assistant Couche (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="0f812-150">In the Map pane, right-click the layer, and on the toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
     <span data-ttu-id="0f812-151">Pour plus d’informations, consultez [Assistant Carte et Assistant Couche &#40;Générateur de rapports et SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f812-151">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-add-a-point-line-or-polygon-layer-from-the-map-pane-toolbar"></a><a name="AddVectorLayer"></a> <span data-ttu-id="0f812-152">Pour ajouter une couche de points, de lignes ou de polygones à partir de la barre d'outils du volet Carte</span><span class="sxs-lookup"><span data-stu-id="0f812-152">To add a point, line, or polygon layer from the Map pane toolbar</span></span>  
  
1.  <span data-ttu-id="0f812-153">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-153">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-154">Dans la barre d’outils, cliquez sur le bouton **Ajouter une couche** puis, dans la liste déroulante, cliquez sur le type de couche que vous voulez ajouter : **Point**, **Ligne**, ou **Polygone**.</span><span class="sxs-lookup"><span data-stu-id="0f812-154">On the toolbar, click the **Add Layer** button, and from the drop-down list, click the type of layer that you want to add: **Point**, **Line**, or **Polygon**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f812-155">Bien qu'il soit possible d'ajouter une couche et de la configurer manuellement, nous vous recommandons d'utiliser l'Assistant Couche pour ajouter de nouvelles couches.</span><span class="sxs-lookup"><span data-stu-id="0f812-155">Although you can add a map layer and configure it manually, we recommend that you use the map layer wizard to add new layers.</span></span> <span data-ttu-id="0f812-156">Pour lancer l’Assistant à partir de la barre d’outils du volet Carte, cliquez sur le bouton de l’Assistant Couche (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="0f812-156">To launch the wizard from the Map pane toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
3.  <span data-ttu-id="0f812-157">Cliquez avec le bouton droit sur la couche, puis cliquez sur **Données de couche**.</span><span class="sxs-lookup"><span data-stu-id="0f812-157">Right-click the layer, and then click **Layer Data**.</span></span>  
  
4.  <span data-ttu-id="0f812-158">Dans **Utiliser les données spatiales de**, sélectionnez la source de données spatiales.</span><span class="sxs-lookup"><span data-stu-id="0f812-158">In **Use spatial data from**, select the source of spatial data.</span></span> <span data-ttu-id="0f812-159">Les options varient selon votre sélection.</span><span class="sxs-lookup"><span data-stu-id="0f812-159">Options vary based on your selection.</span></span>  
  
     <span data-ttu-id="0f812-160">Si vous souhaitez visualiser des données analytiques de votre rapport sur cette couche, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0f812-160">If you want to visualize analytical from your report on this layer, do the following:</span></span>  
  
    1.  <span data-ttu-id="0f812-161">Cliquez sur **Données analytiques**.</span><span class="sxs-lookup"><span data-stu-id="0f812-161">Click **Analytical data**.</span></span>  
  
    2.  <span data-ttu-id="0f812-162">Dans **Dataset analytique**, cliquez sur le nom du dataset qui contient les données analytiques et les champs de correspondance pour générer une relation entre des données analytiques et spatiales.</span><span class="sxs-lookup"><span data-stu-id="0f812-162">In **Analytical dataset**, click the name of the dataset that contains analytical data and the match fields to build a relationship between analytical and spatial data.</span></span>  
  
    3.  <span data-ttu-id="0f812-163">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="0f812-163">Click **Add**.</span></span>  
  
    4.  <span data-ttu-id="0f812-164">Tapez le nom du champ de correspondance du dataset spatial.</span><span class="sxs-lookup"><span data-stu-id="0f812-164">Type the name of the match field from the spatial dataset.</span></span>  
  
    5.  <span data-ttu-id="0f812-165">Tapez le nom du champ de correspondance du dataset analytique.</span><span class="sxs-lookup"><span data-stu-id="0f812-165">Type the name of the match field from the analytical dataset.</span></span>  
  
     <span data-ttu-id="0f812-166">Pour plus d’informations sur la liaison des données spatiales et analytiques, consultez [Personnaliser des données et l’affichage d’une carte ou d’une couche &#40;Générateur de rapports et SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f812-166">For more information about linking spatial and analytical data, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-filter-analytical-data-for-the-layer"></a><a name="FilterAnalyticalData"></a> <span data-ttu-id="0f812-167">Pour filtrer des données analytiques pour la couche</span><span class="sxs-lookup"><span data-stu-id="0f812-167">To filter analytical data for the layer</span></span>  
  
1.  <span data-ttu-id="0f812-168">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-168">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-169">Dans le volet Carte, cliquez avec le bouton droit sur la couche, puis cliquez sur  **Données de couche**.</span><span class="sxs-lookup"><span data-stu-id="0f812-169">Right-click the layer in the Map pane, and then click  **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0f812-170">Cliquez sur **Filtres**.</span><span class="sxs-lookup"><span data-stu-id="0f812-170">Click **Filters**.</span></span>  
  
4.  <span data-ttu-id="0f812-171">Définissez une équation de filtre pour limiter les données analytiques utilisées dans l'affichage de la carte.</span><span class="sxs-lookup"><span data-stu-id="0f812-171">Define a filter equation to limit the analytical data that is used in the map display.</span></span> <span data-ttu-id="0f812-172">Pour plus d’informations, consultez [Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f812-172">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-control-point-properties-for-a-point-layer-or-for-polygon-center-points"></a><a name="PointProperties"></a> <span data-ttu-id="0f812-173">Pour contrôler les propriétés des points d'une couche de points ou pour les points centraux de polygones</span><span class="sxs-lookup"><span data-stu-id="0f812-173">To control point properties for a point layer or for polygon center points</span></span>  
  
1.  <span data-ttu-id="0f812-174">Sélectionnez **Général** dans la boîte de dialogue **Propriétés des points de la carte** pour modifier les options d’étiquette, d’info-bulle et de type de marqueur pour les éléments cartographiques suivants :</span><span class="sxs-lookup"><span data-stu-id="0f812-174">Select **General** on the **Map Point Properties** dialog box to change label, tooltip, and marker type options for the following map elements:</span></span>  
  
    -   <span data-ttu-id="0f812-175">Tous les points dynamiques ou incorporés sur une couche de points.</span><span class="sxs-lookup"><span data-stu-id="0f812-175">All dynamic or embedded points on a point layer.</span></span> <span data-ttu-id="0f812-176">Les règles de couleur, de taille et de type de marqueur relatives aux points remplacent ces options.</span><span class="sxs-lookup"><span data-stu-id="0f812-176">Color rules, size rules, and marker type rules for points override these options.</span></span> <span data-ttu-id="0f812-177">Pour remplacer les options d’un point incorporé spécifique, utilisez la page [Boîte de dialogue Propriétés des points incorporés de la carte, Marqueur](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="0f812-177">To override options for a specific embedded point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  
  
    -   <span data-ttu-id="0f812-178">Le point central de tous les polygones dynamiques ou incorporés sur une couche de polygones.</span><span class="sxs-lookup"><span data-stu-id="0f812-178">The center point for all dynamic or embedded polygons on a polygon layer.</span></span> <span data-ttu-id="0f812-179">Les règles de couleur, de taille et de type de marqueur relatives aux points centraux remplacent ces options.</span><span class="sxs-lookup"><span data-stu-id="0f812-179">Color rules, size rules, and marker type rules for center points override these options.</span></span> <span data-ttu-id="0f812-180">Pour remplacer les options d’un point central spécifique, utilisez la page [Boîte de dialogue Propriétés des points incorporés de la carte, Marqueur](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="0f812-180">To override options for a specific center point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  

##  <a name="to-specify-embedded-data-as-a-source-of-spatial-data"></a><a name="Embedded"></a> <span data-ttu-id="0f812-181">Pour spécifier des données incorporées comme source de données spatiales</span><span class="sxs-lookup"><span data-stu-id="0f812-181">To specify embedded data as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="0f812-182">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-182">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-183">Cliquez avec le bouton droit sur la couche, puis cliquez sur **Données de couche**.</span><span class="sxs-lookup"><span data-stu-id="0f812-183">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0f812-184">Dans **Utiliser les données spatiales de**, sélectionnez **Données incorporées dans le rapport**.</span><span class="sxs-lookup"><span data-stu-id="0f812-184">In **Use spatial data from**, select **Data embedded in report**.</span></span>  
  
4.  <span data-ttu-id="0f812-185">Pour charger les éléments cartographiques d’un rapport existant ou pour créer des éléments cartographiques à partir d’un fichier ESRI, cliquez sur **Parcourir**, pointez sur le fichier, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="0f812-185">To load map elements from an existing report or to create map elements based on an ESRI file, click **Browse**, point to the file, and then click **Open**.</span></span> <span data-ttu-id="0f812-186">Les éléments cartographiques sont incorporés dans cette définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="0f812-186">The map elements are embedded in this report definition.</span></span> <span data-ttu-id="0f812-187">Les données spatiales sur lesquelles vous pointez doivent correspondre au type de couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-187">The spatial data that you point to must match the layer type.</span></span> <span data-ttu-id="0f812-188">Par exemple, pour une couche de points, vous devez pointer sur les données spatiales qui spécifient des jeux de coordonnées de points.</span><span class="sxs-lookup"><span data-stu-id="0f812-188">For example, for a point layer, you must point to spatial data that specifies sets of point coordinates.</span></span>  
  
5.  <span data-ttu-id="0f812-189">Dans **Champ spatial**, spécifiez le nom du champ qui contient les données spatiales.</span><span class="sxs-lookup"><span data-stu-id="0f812-189">In **Spatial field**, specify the name of the field that contains spatial data.</span></span> <span data-ttu-id="0f812-190">Vous devrez peut-être déterminer ce nom à partir de la source de données spatiales.</span><span class="sxs-lookup"><span data-stu-id="0f812-190">You might need to determine this name from the source of spatial data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f812-191">Si vous ne connaissez pas le nom du champ et que vous avez ouvert un fichier de forme ESRI, utilisez plutôt l’option **Lien vers le fichier de forme ESRI** .</span><span class="sxs-lookup"><span data-stu-id="0f812-191">If you do not know the name of the field and you browsed to an ESRI Shapefile, use the **Link to ESRI shape file option** instead of this option.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-an-esri-shapefile-as-a-source-of-spatial-data"></a><a name="ESRI"></a> <span data-ttu-id="0f812-192">Pour spécifier un fichier de forme ESRI comme source de données spatiales</span><span class="sxs-lookup"><span data-stu-id="0f812-192">To specify an ESRI Shapefile as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="0f812-193">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-193">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-194">Cliquez avec le bouton droit sur la couche, puis cliquez sur **Données de couche**.</span><span class="sxs-lookup"><span data-stu-id="0f812-194">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0f812-195">Dans **Utiliser les données spatiales de**, sélectionnez **Lien vers le fichier de forme ESRI**.</span><span class="sxs-lookup"><span data-stu-id="0f812-195">In **Use spatial data from**, select **Link to ESRI Shapefile**.</span></span>  
  
4.  <span data-ttu-id="0f812-196">Dans **Nom de fichier**, tapez l’emplacement d’un fichier de forme ESRI ou cliquez sur **Parcourir** pour sélectionner un fichier de forme ESRI.</span><span class="sxs-lookup"><span data-stu-id="0f812-196">In **File name**, type the location of an ESRI Shapefile, or click **Browse** to select an ESRI Shapefile.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f812-197">Si le fichier de forme se trouve sur votre ordinateur local, les données spatiales sont incorporées dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="0f812-197">If the Shapefile is on your local computer, the spatial data is embedded in the report definition.</span></span> <span data-ttu-id="0f812-198">Pour récupérer les données dynamiquement lors du traitement du rapport, vous devez télécharger le fichier ESRI .shp et son fichier de support .dbf sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0f812-198">To retrieve the data dynamically when the report is processed, you must upload the ESRI .shp file and its .dbf support file to the report server.</span></span> <span data-ttu-id="0f812-199">Pour plus d’informations, consultez « Procédure : télécharger un fichier ou un rapport (Gestionnaire de rapports) » dans la [section Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) de la documentation en ligne SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f812-199">For more information, see " How to: Upload a File or Report (Report Manager)" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-report-dataset-field-as-a-source-of-spatial-data"></a><a name="DatasetField"></a> <span data-ttu-id="0f812-200">Pour spécifier un champ de dataset de rapport comme source de données spatiales</span><span class="sxs-lookup"><span data-stu-id="0f812-200">To specify a report dataset field as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="0f812-201">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-201">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-202">Cliquez avec le bouton droit sur la couche, puis cliquez sur **Données de couche**.</span><span class="sxs-lookup"><span data-stu-id="0f812-202">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0f812-203">Dans **Utiliser les données spatiales de**, sélectionnez **Champ spatial dans un dataset**.</span><span class="sxs-lookup"><span data-stu-id="0f812-203">In **Use spatial data from**, select **Spatial field in a dataset**.</span></span>  
  
4.  <span data-ttu-id="0f812-204">Dans **Nom du dataset**, cliquez sur le nom d’un dataset du rapport qui contient les données spatiales souhaitées.</span><span class="sxs-lookup"><span data-stu-id="0f812-204">In **Dataset name**, click the name of a dataset in the report that contains that spatial data that you want.</span></span>  
  
5.  <span data-ttu-id="0f812-205">Dans **Nom du champ spatial**, cliquez sur le nom du champ du dataset qui contient les données spatiales.</span><span class="sxs-lookup"><span data-stu-id="0f812-205">In **Spatial field name**, click the name of the field in the dataset that contains spatial data.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-add-a-tile-layer"></a><a name="TileLayer"></a> <span data-ttu-id="0f812-206">Pour ajouter une couche de mosaïques</span><span class="sxs-lookup"><span data-stu-id="0f812-206">To add a tile layer</span></span>  
  
1.  <span data-ttu-id="0f812-207">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-207">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-208">Dans la barre d’outils, cliquez sur le bouton **Ajouter une couche** puis, dans la liste déroulante, cliquez sur **Couche de mosaïques**.</span><span class="sxs-lookup"><span data-stu-id="0f812-208">On the toolbar, click the **Add Layer** button, and from the drop-down list, click **Tile Layer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f812-209"> Pour plus d'informations sur l'utilisation de mosaïques Bing dans votre rapport, consultez [Conditions supplémentaires d'utilisation](https://go.microsoft.com/fwlink/?LinkId=151371) et [Déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=151372)(éventuellement en anglais).</span><span class="sxs-lookup"><span data-stu-id="0f812-209">For more information about the use of Bing map tiles in your report, see [Additional Terms of Use](https://go.microsoft.com/fwlink/?LinkId=151371) and [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=151372).</span></span>  
  
3.  <span data-ttu-id="0f812-210">Cliquez avec le bouton droit sur la couche de mosaïques dans le volet Carte, puis sélectionnez **Propriétés des mosaïques**.</span><span class="sxs-lookup"><span data-stu-id="0f812-210">Right-click the tile layer in the Map pane, and then click **Tile Properties**.</span></span>  
  
4.  <span data-ttu-id="0f812-211">Dans **Options de mosaïque**, sélectionnez un style de mosaïque.</span><span class="sxs-lookup"><span data-stu-id="0f812-211">In **Tile options**, select a tile style.</span></span> <span data-ttu-id="0f812-212">Si les mosaïques Bing sont disponibles, la couche sur l'aire de conception est mise à jour avec le style que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="0f812-212">If the Bing map tiles are available, the layer on the design surface updates with the style that you select.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f812-213">Une couche de mosaïques peut également être ajoutée lorsque vous ajoutez une couche de polygones, de lignes ou de points dans l'Assistant Carte ou Couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-213">A tile layer can also be added when you add a polygon, line, or point layer in the Map or Map Layer wizard.</span></span> <span data-ttu-id="0f812-214">Dans la page **Choisir des options de vue cartographique et de données spatiales** , sélectionnez l’option **Ajouter un arrière-plan Bing Maps pour cette vue cartographique**.</span><span class="sxs-lookup"><span data-stu-id="0f812-214">On the **Choose spatial data and map view options** page, select the option **Add a Bing Maps background for this map view**.</span></span>  

##  <a name="to-change-the-drawing-order-of-a-layer"></a><a name="DrawingOrder"></a> <span data-ttu-id="0f812-215">Pour modifier l'ordre de dessin d'une couche</span><span class="sxs-lookup"><span data-stu-id="0f812-215">To change the drawing order of a layer</span></span>  
  
1.  <span data-ttu-id="0f812-216">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-216">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-217">Cliquez sur la couche dans le volet Carte pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="0f812-217">Click the layer in the Map pane to select it.</span></span>  
  
3.  <span data-ttu-id="0f812-218">Dans la barre d'outils du volet Carte, cliquez sur la flèche Haut ou Bas pour modifier l'ordre de dessin de chaque couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-218">On the Map pane toolbar, click the up or down arrow to change the drawing order of each layer.</span></span>  

##  <a name="to-change-the-transparency-of-a-polygon-line-or-point-layer"></a><a name="Transparency"></a> <span data-ttu-id="0f812-219">Pour modifier la transparence d'une couche de polygones, de lignes ou de points</span><span class="sxs-lookup"><span data-stu-id="0f812-219">To change the transparency of a polygon, line, or point layer</span></span>  
  
1.  <span data-ttu-id="0f812-220">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-220">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-221">Cliquez avec le bouton droit sur la couche, puis cliquez sur **Données de couche**.</span><span class="sxs-lookup"><span data-stu-id="0f812-221">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0f812-222">Cliquez sur `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="0f812-222">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="0f812-223">Dans **Options de transparence**, tapez une valeur qui représente le pourcentage de transparence, par exemple **40**.</span><span class="sxs-lookup"><span data-stu-id="0f812-223">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span> <span data-ttu-id="0f812-224">Un facteur de transparence de zéro (0 %) signifie que la couche est opaque.</span><span class="sxs-lookup"><span data-stu-id="0f812-224">Zero (0) % transparency means that the layer is opaque.</span></span> <span data-ttu-id="0f812-225">Un facteur de transparence de 100 % signifie que vous ne verrez pas la couche dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="0f812-225">100% transparency means that you will not see the layer in the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-change-the-transparency-of-a-tile-layer"></a><a name="TileTransparency"></a> <span data-ttu-id="0f812-226">Pour modifier la transparence d'une couche de mosaïques</span><span class="sxs-lookup"><span data-stu-id="0f812-226">To change the transparency of a tile layer</span></span>  
  
1.  <span data-ttu-id="0f812-227">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-227">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-228">Cliquez avec le bouton droit sur la couche, puis cliquez sur **Propriétés des mosaïques**.</span><span class="sxs-lookup"><span data-stu-id="0f812-228">Right-click the layer, and then click **Tile Properties**.</span></span>  
  
3.  <span data-ttu-id="0f812-229">Cliquez sur `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="0f812-229">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="0f812-230">Dans **Options de transparence**, tapez une valeur qui représente le pourcentage de transparence, par exemple **40**.</span><span class="sxs-lookup"><span data-stu-id="0f812-230">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-secure-connection-for-a-tile-layer"></a><a name="Secure"></a> <span data-ttu-id="0f812-231">Pour spécifier une connexion sécurisée pour une couche de mosaïques</span><span class="sxs-lookup"><span data-stu-id="0f812-231">To specify a secure connection for a tile layer</span></span>  
  
1.  <span data-ttu-id="0f812-232">Cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0f812-232">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0f812-233">Dans le volet Carte, cliquez sur la couche de mosaïques pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="0f812-233">In the Map pane, click the tile layer to select it.</span></span> <span data-ttu-id="0f812-234">Le volet Propriétés affiche les propriétés de la couche de mosaïques.</span><span class="sxs-lookup"><span data-stu-id="0f812-234">The Properties pane displays the tile layer properties.</span></span>  
  
3.  <span data-ttu-id="0f812-235">Dans le volet Propriétés, attribuez à UseSecureConnection la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="0f812-235">In the Properties pane, set UseSecureConnection to **True**.</span></span>  
  
 <span data-ttu-id="0f812-236">La connexion au service Web Bing Maps utilise le service HTTP SSL (Secure Sockets Layer) pour récupérer des mosaïques Bing pour cette couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-236">The connection for the Bing Maps Web service will use the HTTP SSL (Secure Sockets Layer) service to retrieve Bing map tiles for this layer.</span></span>  

##  <a name="to-specify-the-language-for-tile-labels"></a><a name="Language"></a> <span data-ttu-id="0f812-237">Pour spécifier la langue des étiquettes de mosaïque</span><span class="sxs-lookup"><span data-stu-id="0f812-237">To specify the language for tile labels</span></span>  
  
1.  <span data-ttu-id="0f812-238">Par défaut, pour les styles de mosaïque qui affichent des étiquettes, la langue est déterminée en fonction des paramètres régionaux par défaut définis pour le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0f812-238">By default, for tile styles that display labels, the language is determined from the default locale for Report Builder.</span></span> <span data-ttu-id="0f812-239">Vous pouvez personnaliser le paramètre de langue pour les étiquettes de mosaïque des façons suivantes.</span><span class="sxs-lookup"><span data-stu-id="0f812-239">You can customize the language setting for tile labels in the following ways.</span></span>  
  
    -   <span data-ttu-id="0f812-240">Cliquez sur la carte à l'extérieur de la fenêtre d'affichage afin de sélectionner la carte.</span><span class="sxs-lookup"><span data-stu-id="0f812-240">Click the map outside the viewport to select the map.</span></span> <span data-ttu-id="0f812-241">Dans le volet Propriétés, pour la propriété TileLanguage, sélectionnez une valeur de culture dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="0f812-241">In the Properties pane, for the TileLanguage property, select a culture value from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="0f812-242">Cliquez sur l'arrière-plan du rapport pour sélectionner le rapport.</span><span class="sxs-lookup"><span data-stu-id="0f812-242">Click the report background to select the report.</span></span> <span data-ttu-id="0f812-243">Dans le volet Propriétés, pour la propriété Language, sélectionnez une valeur de culture dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="0f812-243">In the Properties pane, from for the Language property, select a culture value from the drop-down list.</span></span>  
  
     <span data-ttu-id="0f812-244">L’ordre de priorité pour la définition de la langue des étiquettes de mosaïque est le suivant : propriété de rapport Language, paramètres régionaux par défaut définis pour le Générateur de rapports et propriété de carte TileLanguage.</span><span class="sxs-lookup"><span data-stu-id="0f812-244">The order of precedence for setting the tile label language is: report property Language, default locale for Report Builder, and map property TileLanguage.</span></span>  

##  <a name="to-conditionally-hide-a-layer-based-on-viewport-zoom-level"></a><a name="ConditionalHide"></a> <span data-ttu-id="0f812-245">Pour masquer de manière conditionnelle une couche en fonction du niveau de zoom de la fenêtre d'affichage</span><span class="sxs-lookup"><span data-stu-id="0f812-245">To conditionally hide a layer based on viewport zoom level</span></span>  
  
1.  <span data-ttu-id="0f812-246">Définissez `Visibility` les options de contrôle de l’affichage d’une couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-246">Set `Visibility` options to control the display for a map layer.</span></span>  
  
    -   <span data-ttu-id="0f812-247">Dans le volet Couches, cliquez avec le bouton droit sur une couche pour la sélectionner puis, dans la barre d’outils Couches, cliquez sur Propriétés pour ouvrir **Propriétés de la couche**.</span><span class="sxs-lookup"><span data-stu-id="0f812-247">In the Map Layers pane, right-click a layer to select it, and on the Map Layers toolbar, click Properties to open **Map Layer Properties**.</span></span>  
  
    -   <span data-ttu-id="0f812-248">Cliquez sur `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="0f812-248">Click `Visibility`.</span></span>  
  
    -   <span data-ttu-id="0f812-249">Dans Visibilité de la couche, sélectionnez **Afficher ou masquer en fonction d’une valeur de zoom**.</span><span class="sxs-lookup"><span data-stu-id="0f812-249">In Layer visibility, select **Show or hide based on zoom value**.</span></span>  
  
    -   <span data-ttu-id="0f812-250">Entrez les valeurs de zoom maximale et minimale pour l'affichage de la couche.</span><span class="sxs-lookup"><span data-stu-id="0f812-250">Enter minimum and maximum zoom values for when display the layer.</span></span>  
  
    -   <span data-ttu-id="0f812-251">facultatif.</span><span class="sxs-lookup"><span data-stu-id="0f812-251">Optional.</span></span> <span data-ttu-id="0f812-252">Entrez une valeur pour la transparence.</span><span class="sxs-lookup"><span data-stu-id="0f812-252">Enter a value for transparency.</span></span>  
  
     <span data-ttu-id="0f812-253">Vous pouvez également masquer la couche de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="0f812-253">You can also conditionally hide the layer.</span></span> <span data-ttu-id="0f812-254">Pour plus d’informations, consultez [Masquer un élément &#40;Générateur de rapports et SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f812-254">For more information, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="0f812-255">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f812-255">See Also</span></span>  
 <span data-ttu-id="0f812-256">[Cartes &#40;Générateur de rapports et SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0f812-256">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0f812-257">Résoudre les problèmes liés aux rapports : rapports cartographiques &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0f812-257">Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;</span></span>](troubleshoot-reports-map-reports-report-builder-and-ssrs.md)  
