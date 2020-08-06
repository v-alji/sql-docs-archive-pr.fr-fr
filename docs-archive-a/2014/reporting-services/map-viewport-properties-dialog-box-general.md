---
title: Boîte de dialogue Propriétés de la fenêtre d’affichage de la carte, général | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.general.f1
- "10505"
ms.assetid: 6c9c773e-5c56-4571-95ed-8a157cfdfe52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d760d6a0572cbbd1bd948eab382c0727eb276c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600632"
---
# <a name="map-viewport-properties-dialog-box-general"></a><span data-ttu-id="eeaac-102">Boîte de dialogue Propriétés du point de vue de la carte, Général</span><span class="sxs-lookup"><span data-stu-id="eeaac-102">Map Viewport Properties Dialog Box, General</span></span>
  <span data-ttu-id="eeaac-103">Sélectionnez **Général** dans la boîte de dialogue **Propriétés de la fenêtre d'affichage de la carte** pour modifier le système de coordonnées, la projection et les options de limite.</span><span class="sxs-lookup"><span data-stu-id="eeaac-103">Select **General** on the **Map Viewport Properties** dialog box to change the coordinate system, the projection, and the boundary options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="eeaac-104">Options</span><span class="sxs-lookup"><span data-stu-id="eeaac-104">Options</span></span>  
 <span data-ttu-id="eeaac-105">**Système de coordonnées**</span><span class="sxs-lookup"><span data-stu-id="eeaac-105">**Coordinate system**</span></span>  
 <span data-ttu-id="eeaac-106">Indiquez le type de système de coordonnées utilisé par les données de la carte.</span><span class="sxs-lookup"><span data-stu-id="eeaac-106">Indicate the type of coordinate system that the map data uses.</span></span>  
  
-   <span data-ttu-id="eeaac-107">**Planaire** Choisissez cette option lorsque les données cartographiques sont des coordonnées X et Y, par exemple pour des plans de bâtiment.</span><span class="sxs-lookup"><span data-stu-id="eeaac-107">**Planar** Choose this option when map data is in X and Y coordinates, for example, for building plans.</span></span>  
  
-   <span data-ttu-id="eeaac-108">**Géographique** Choisissez cette option lorsque les données cartographiques sont des coordonnées de longitude et de latitude, par exemple pour l'emplacement des villes.</span><span class="sxs-lookup"><span data-stu-id="eeaac-108">**Geographic** Choose this option when map data is in longitude and latitude coordinates, for example, for city locations.</span></span>  
  
 <span data-ttu-id="eeaac-109">**Projection**</span><span class="sxs-lookup"><span data-stu-id="eeaac-109">**Projection**</span></span>  
 <span data-ttu-id="eeaac-110">Spécifiez la méthode à utiliser pour projeter des coordonnées géographiques sur une surface à deux dimensions.</span><span class="sxs-lookup"><span data-stu-id="eeaac-110">Specify the method to use to project geographic coordinates onto a two-dimensional surface.</span></span> <span data-ttu-id="eeaac-111">Choisissez une projection compatible avec les données que vous visualisez.</span><span class="sxs-lookup"><span data-stu-id="eeaac-111">Choose a projection that is compatible with the data that you are visualizing.</span></span> <span data-ttu-id="eeaac-112">Les quatre propriétés spatiales affectées par la projection sont la zone, la forme, la distance et la direction.</span><span class="sxs-lookup"><span data-stu-id="eeaac-112">The four spatial properties that are affected by projection are area, shape, distance, and direction.</span></span> <span data-ttu-id="eeaac-113">Pour des vues du monde, le choix de projection approprié dépend du centre d'affichage, des limites de la carte et du facteur de zoom.</span><span class="sxs-lookup"><span data-stu-id="eeaac-113">For views of the earth, a good choice of projection depends on the center view, the map boundaries, and the zoom factor.</span></span>  
  
 <span data-ttu-id="eeaac-114">Chacune des projections suivantes conserve une ou plusieurs de ces propriétés spatiales :</span><span class="sxs-lookup"><span data-stu-id="eeaac-114">Each of the following projections preserves one or more of these spatial properties:</span></span>  
  
-   <span data-ttu-id="eeaac-115">**Équirectangulaire** Choisissez cette option pour utiliser la longitude et la latitude comme coordonnées rectangulaires.</span><span class="sxs-lookup"><span data-stu-id="eeaac-115">**Equirectangular** Choose this option to use longitude and latitude as rectangular coordinates.</span></span>  
  
-   <span data-ttu-id="eeaac-116">**Mercator** Choisissez cette projection couramment utilisée pour les zones peu étendues, pour réduire la distorsion autour de l'équateur ou lorsque vous souhaitez ajouter une couche à une couche de mosaïques existante utilisant la projection Mercator.</span><span class="sxs-lookup"><span data-stu-id="eeaac-116">**Mercator** Choose this popular projection for smaller areas, for less distortion around the equator, or when you want to add a map layer with an existing tile layer that uses the Mercator projection.</span></span>  
  
-   <span data-ttu-id="eeaac-117">**Robinson** Choisissez cette option pour réduire la distorsion de zones étendues allant de l'équateur jusqu'aux pôles.</span><span class="sxs-lookup"><span data-stu-id="eeaac-117">**Robinson** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="eeaac-118">Développée par Arthur H. Robinson en 1963.</span><span class="sxs-lookup"><span data-stu-id="eeaac-118">Developed by Arthur H. Robinson in 1963.</span></span>  
  
-   <span data-ttu-id="eeaac-119">**Fahey** Choisissez cette option pour réduire la distorsion des zones étendues allant de l'équateur jusqu'aux pôles.</span><span class="sxs-lookup"><span data-stu-id="eeaac-119">**Fahey** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="eeaac-120">Développée par Lawrence Fahey en 1975.</span><span class="sxs-lookup"><span data-stu-id="eeaac-120">Developed by Lawrence Fahey in 1975.</span></span>  
  
-   <span data-ttu-id="eeaac-121">**Eckert1** Choisissez cette option pour utiliser des parallèles à intervalles réguliers en latitude et des lignes droites pour les méridiens en longitude.</span><span class="sxs-lookup"><span data-stu-id="eeaac-121">**Eckert1** Choose this option to use equally spaced parallels in latitude and straight lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="eeaac-122">**Eckert3** Choisissez cette option pour utiliser des parallèles à intervalles réguliers en latitude et des lignes courbes pour les méridiens en longitude.</span><span class="sxs-lookup"><span data-stu-id="eeaac-122">**Eckert3** Choose this option to use equally spaced parallels in latitude and curved lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="eeaac-123">**HammerAitoff** Choisissez cette option pour les cartes polaires ou mondiales.</span><span class="sxs-lookup"><span data-stu-id="eeaac-123">**HammerAitoff** Choose this option for polar maps or world maps.</span></span>  
  
-   <span data-ttu-id="eeaac-124">**Wagner3** Choisissez cette option pour les cartes mondiales.</span><span class="sxs-lookup"><span data-stu-id="eeaac-124">**Wagner3** Choose this option for world maps.</span></span>  
  
-   <span data-ttu-id="eeaac-125">**Bonne** Choisissez cette option pour afficher le monde tel qu'il est présenté dans un atlas.</span><span class="sxs-lookup"><span data-stu-id="eeaac-125">**Bonne** Choose this option to view the world as it appears in an atlas.</span></span>  
  
 <span data-ttu-id="eeaac-126">**Options des sauts de page**</span><span class="sxs-lookup"><span data-stu-id="eeaac-126">**Page break options**</span></span>  
 <span data-ttu-id="eeaac-127">Sélectionnez des options pour indiquer comment le contenu sera ajusté à une page du rapport.</span><span class="sxs-lookup"><span data-stu-id="eeaac-127">Select options to indicate how content is fitted to a report page.</span></span>  
  
 <span data-ttu-id="eeaac-128">**Options de limite**</span><span class="sxs-lookup"><span data-stu-id="eeaac-128">**Boundary options**</span></span>  
 <span data-ttu-id="eeaac-129">Spécifiez les limites inférieure et supérieure des coordonnées pour contrôler quelle partie de la carte s'affiche dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="eeaac-129">Specify the lower and upper boundaries for coordinates to control which part of the map appears in the report.</span></span>  
  
 <span data-ttu-id="eeaac-130">**X minimal**</span><span class="sxs-lookup"><span data-stu-id="eeaac-130">**Minimum X**</span></span>  
 <span data-ttu-id="eeaac-131">Valeur X la plus basse.</span><span class="sxs-lookup"><span data-stu-id="eeaac-131">Lowest X value.</span></span> <span data-ttu-id="eeaac-132">Disponible uniquement pour l'option **Planaire** .</span><span class="sxs-lookup"><span data-stu-id="eeaac-132">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="eeaac-133">**X maximal**</span><span class="sxs-lookup"><span data-stu-id="eeaac-133">**Maximum X**</span></span>  
 <span data-ttu-id="eeaac-134">Valeur X la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="eeaac-134">Highest X value.</span></span> <span data-ttu-id="eeaac-135">Disponible uniquement pour l'option **Planaire** .</span><span class="sxs-lookup"><span data-stu-id="eeaac-135">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="eeaac-136">**Y minimum**</span><span class="sxs-lookup"><span data-stu-id="eeaac-136">**Minimum Y**</span></span>  
 <span data-ttu-id="eeaac-137">Valeur Y la plus basse.</span><span class="sxs-lookup"><span data-stu-id="eeaac-137">Lowest Y value.</span></span> <span data-ttu-id="eeaac-138">Disponible uniquement pour l'option **Planaire** .</span><span class="sxs-lookup"><span data-stu-id="eeaac-138">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="eeaac-139">**Y maximal**</span><span class="sxs-lookup"><span data-stu-id="eeaac-139">**Maximum Y**</span></span>  
 <span data-ttu-id="eeaac-140">Valeur Y la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="eeaac-140">Highest Y value.</span></span> <span data-ttu-id="eeaac-141">Disponible uniquement pour l'option **Planaire** .</span><span class="sxs-lookup"><span data-stu-id="eeaac-141">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="eeaac-142">**Longitude minimale**</span><span class="sxs-lookup"><span data-stu-id="eeaac-142">**Minimum Longitude**</span></span>  
 <span data-ttu-id="eeaac-143">Valeur de longitude la plus basse.</span><span class="sxs-lookup"><span data-stu-id="eeaac-143">Lowest longitude value.</span></span> <span data-ttu-id="eeaac-144">Disponible uniquement pour l'option **Géographique** .</span><span class="sxs-lookup"><span data-stu-id="eeaac-144">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="eeaac-145">**Longitude maximale**</span><span class="sxs-lookup"><span data-stu-id="eeaac-145">**Maximum Longitude**</span></span>  
 <span data-ttu-id="eeaac-146">Valeur de longitude la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="eeaac-146">Highest longitude value.</span></span> <span data-ttu-id="eeaac-147">Disponible uniquement pour l'option **Géographique** .</span><span class="sxs-lookup"><span data-stu-id="eeaac-147">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="eeaac-148">**Latitude minimale**</span><span class="sxs-lookup"><span data-stu-id="eeaac-148">**Minimum Latitude**</span></span>  
 <span data-ttu-id="eeaac-149">Valeur de latitude la plus basse.</span><span class="sxs-lookup"><span data-stu-id="eeaac-149">Lowest latitude value.</span></span> <span data-ttu-id="eeaac-150">Disponible uniquement pour l'option **Géographique** .</span><span class="sxs-lookup"><span data-stu-id="eeaac-150">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="eeaac-151">**Latitude maximale**</span><span class="sxs-lookup"><span data-stu-id="eeaac-151">**Maximum Latitude**</span></span>  
 <span data-ttu-id="eeaac-152">Valeur de latitude la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="eeaac-152">Highest latitude value.</span></span> <span data-ttu-id="eeaac-153">Disponible uniquement pour l'option **Géographique** .</span><span class="sxs-lookup"><span data-stu-id="eeaac-153">Available for **Geographic** only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeaac-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eeaac-154">See Also</span></span>  
 [<span data-ttu-id="eeaac-155">Cartes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eeaac-155">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
