---
title: Boîte de dialogue Propriétés de la fenêtre d’affichage de la carte, Centre et zoom | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.centerandzoom.f1
- "10506"
ms.assetid: 642a06f5-293f-48e0-97a6-1489dbefa719
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 913c00773abf71ca627b8cc2a94a873484e8ab30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603304"
---
# <a name="map-viewport-properties-dialog-box-center-and-zoom"></a><span data-ttu-id="41cd5-102">Boîte de dialogue Propriétés du point de vue de la carte, Centrer et zoomer</span><span class="sxs-lookup"><span data-stu-id="41cd5-102">Map Viewport Properties Dialog Box, Center and Zoom</span></span>
  <span data-ttu-id="41cd5-103">Sélectionnez **Centrer et zoomer** dans la boîte de dialogue **Propriétés de la fenêtre d'affichage de la carte** pour définir le centre d'affichage et le facteur de zoom d'une carte.</span><span class="sxs-lookup"><span data-stu-id="41cd5-103">Select **Center and Zoom** for the **Map Viewport Properties** dialog box to set the center view and zoom factor for a map.</span></span> <span data-ttu-id="41cd5-104">Après avoir spécifié une source de données cartographiques et les limites de la carte que vous souhaitez inclure dans votre rapport, vous pouvez spécifier le centre d'affichage et le facteur de zoom pour contrôler encore davantage l'affichage de la carte.</span><span class="sxs-lookup"><span data-stu-id="41cd5-104">After you specify a map data source and the boundaries of the map that you want to include in your report, you can specify the view center and the zoom factor to further control the map display.</span></span> <span data-ttu-id="41cd5-105">Les options disponibles varient en fonction de la méthode utilisée pour spécifier le centre et les valeurs de zoom.</span><span class="sxs-lookup"><span data-stu-id="41cd5-105">Options change depending on which method you use to specify the center and zoom values.</span></span> <span data-ttu-id="41cd5-106">Cliquez sur le bouton **Expression** (*fx*) pour modifier une expression qui définit la valeur de l'option.</span><span class="sxs-lookup"><span data-stu-id="41cd5-106">Click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
## <a name="options"></a><span data-ttu-id="41cd5-107">Options</span><span class="sxs-lookup"><span data-stu-id="41cd5-107">Options</span></span>  
 <span data-ttu-id="41cd5-108">**Définir un centre d'affichage et un niveau de zoom**</span><span class="sxs-lookup"><span data-stu-id="41cd5-108">**Set a view center and zoom level**</span></span>  
 <span data-ttu-id="41cd5-109">Choisissez cette option pour spécifier des valeurs personnalisées pour le centre d'affichage et le niveau de zoom.</span><span class="sxs-lookup"><span data-stu-id="41cd5-109">Choose this option to specify custom values for the view center and the zoom level.</span></span>  
  
 <span data-ttu-id="41cd5-110">**Centrer la carte pour afficher une couche**</span><span class="sxs-lookup"><span data-stu-id="41cd5-110">**Center map to show a map layer**</span></span>  
 <span data-ttu-id="41cd5-111">Choisissez cette option pour spécifier une couche et centrer automatiquement la vue sur ses données.</span><span class="sxs-lookup"><span data-stu-id="41cd5-111">Choose this option to specify a layer and automatically center the view on its map data.</span></span> <span data-ttu-id="41cd5-112">Par exemple, centrez la vue sur LineLayer1.</span><span class="sxs-lookup"><span data-stu-id="41cd5-112">For example, center the view on LineLayer1.</span></span>  
  
 <span data-ttu-id="41cd5-113">**Centrer la carte pour afficher un élément de carte incorporé**</span><span class="sxs-lookup"><span data-stu-id="41cd5-113">**Center map to show an embedded map element**</span></span>  
 <span data-ttu-id="41cd5-114">Choisissez cette option pour centrer la vue sur un élément cartographique spécifique lié aux données.</span><span class="sxs-lookup"><span data-stu-id="41cd5-114">Choose this option to center the view on a specific data-bound map element.</span></span> <span data-ttu-id="41cd5-115">Les données spatiales doivent être en relation avec des données analytiques pour spécifier cette option.</span><span class="sxs-lookup"><span data-stu-id="41cd5-115">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="41cd5-116">Par exemple, centrez la vue sur l'élément cartographique où le nom du champ de correspondance est [City] et la valeur de correspondance est « Seattle ».</span><span class="sxs-lookup"><span data-stu-id="41cd5-116">For example, center the view on the map element where the name of the match field is [City] and the match value is "Seattle".</span></span>  
  
 <span data-ttu-id="41cd5-117">**Centrer la carte pour afficher tous les éléments de carte liés aux données**</span><span class="sxs-lookup"><span data-stu-id="41cd5-117">**Center map to show all data-bound map elements**</span></span>  
 <span data-ttu-id="41cd5-118">Choisissez cette option pour centrer la vue sur tous les éléments cartographiques de la couche.</span><span class="sxs-lookup"><span data-stu-id="41cd5-118">Choose this option to center the view on all map elements in the layer.</span></span> <span data-ttu-id="41cd5-119">Les données spatiales doivent être en relation avec des données analytiques pour spécifier cette option.</span><span class="sxs-lookup"><span data-stu-id="41cd5-119">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="41cd5-120">Par exemple, centrez la vue sur la couche à bulles de polygones qui affiche des villes et des tailles de bulle différentes en fonction de la population.</span><span class="sxs-lookup"><span data-stu-id="41cd5-120">For example, center the view on the polygon bubble layer that shows cities and the bubble size is related to population.</span></span> <span data-ttu-id="41cd5-121">Seules les villes munies d'une valeur correspondante de population seront incluses lors du calcul du centre de la fenêtre de carte.</span><span class="sxs-lookup"><span data-stu-id="41cd5-121">Only those cities with a matching population value are included when calculating the center for the viewport.</span></span>  
  
 <span data-ttu-id="41cd5-122">**Options de centre et de zoom**</span><span class="sxs-lookup"><span data-stu-id="41cd5-122">**Center and zoom options**</span></span>  
 <span data-ttu-id="41cd5-123">Sélectionnez une option pour spécifier le centre d'affichage et le niveau de zoom.</span><span class="sxs-lookup"><span data-stu-id="41cd5-123">Select an option to specify the view center and zoom level.</span></span>  
  
 <span data-ttu-id="41cd5-124">**Centre d'affichage (X) %**</span><span class="sxs-lookup"><span data-stu-id="41cd5-124">**View center (X) %**</span></span>  
 <span data-ttu-id="41cd5-125">Coordonnée horizontale.</span><span class="sxs-lookup"><span data-stu-id="41cd5-125">The horizontal coordinate.</span></span> <span data-ttu-id="41cd5-126">La valeur par défaut, 50 %,</span><span class="sxs-lookup"><span data-stu-id="41cd5-126">The default value, 50%.</span></span> <span data-ttu-id="41cd5-127">centre la vue à mi-chemin entre les valeurs horizontales minimale et maximale.</span><span class="sxs-lookup"><span data-stu-id="41cd5-127">centers the view at the midpoint between the minimum and maximum horizontal values.</span></span>  
  
 <span data-ttu-id="41cd5-128">**Centre d'affichage (Y) %**</span><span class="sxs-lookup"><span data-stu-id="41cd5-128">**View center (Y) %**</span></span>  
 <span data-ttu-id="41cd5-129">Coordonnée verticale.</span><span class="sxs-lookup"><span data-stu-id="41cd5-129">The vertical coordinate.</span></span> <span data-ttu-id="41cd5-130">La valeur par défaut, 50 %, centre la vue à mi-chemin entre les valeurs verticales minimale et maximale.</span><span class="sxs-lookup"><span data-stu-id="41cd5-130">The default value, 50%, centers the view at the midpoint between the minimum and maximum vertical values.</span></span>  
  
 <span data-ttu-id="41cd5-131">**Niveau de zoom (%)**</span><span class="sxs-lookup"><span data-stu-id="41cd5-131">**Zoom level (%)**</span></span>  
 <span data-ttu-id="41cd5-132">Facteur de zoom.</span><span class="sxs-lookup"><span data-stu-id="41cd5-132">The zoom factor.</span></span> <span data-ttu-id="41cd5-133">La valeur par défaut, 100 %, n'indique aucun agrandissement.</span><span class="sxs-lookup"><span data-stu-id="41cd5-133">The default value, 100%, indicates no magnification.</span></span>  
  
 <span data-ttu-id="41cd5-134">**Centrer l'affichage sur cette couche**</span><span class="sxs-lookup"><span data-stu-id="41cd5-134">**Center view on this layer**</span></span>  
 <span data-ttu-id="41cd5-135">Spécifiez le nom de la couche.</span><span class="sxs-lookup"><span data-stu-id="41cd5-135">Specify the name of the layer.</span></span>  
  
 <span data-ttu-id="41cd5-136">**Centrer l'affichage sur l'élément de carte correspondant à cette condition**</span><span class="sxs-lookup"><span data-stu-id="41cd5-136">**Center view on the map element that matches this condition**</span></span>  
 <span data-ttu-id="41cd5-137">Le champ en lecture seule affiché est utilisé pour faire correspondre les données cartographiques et les données analytiques.</span><span class="sxs-lookup"><span data-stu-id="41cd5-137">The read-only field that is displayed is used to match map data and analytical data.</span></span> <span data-ttu-id="41cd5-138">Spécifiez la valeur avec laquelle les données doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="41cd5-138">Specify the value that you want to match on.</span></span> <span data-ttu-id="41cd5-139">La vue est centrée automatiquement sur cet élément cartographique.</span><span class="sxs-lookup"><span data-stu-id="41cd5-139">The view automatically centers on this map element.</span></span> <span data-ttu-id="41cd5-140">Par exemple, NAME = TEXAS.</span><span class="sxs-lookup"><span data-stu-id="41cd5-140">For example, NAME = TEXAS.</span></span> <span data-ttu-id="41cd5-141">Par défaut, le type de données pour la condition est Chaîne et la correspondance respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="41cd5-141">By default, the data type for the condition is String and the match is case-sensitive.</span></span>  
  
 <span data-ttu-id="41cd5-142">Pour faire correspondre avec un champ qui a un type de données différent, vous devez écrire une expression qui prend la valeur de ce type de données.</span><span class="sxs-lookup"><span data-stu-id="41cd5-142">To match on a field that has a different data type, you must write an expression that evaluates to that data type.</span></span> <span data-ttu-id="41cd5-143">Par exemple, si le champ de correspondance est un code postal de 5 chiffres stocké comme nombre entier, pour spécifier le code postal 98053, vous devrez utiliser l'expression =98053.</span><span class="sxs-lookup"><span data-stu-id="41cd5-143">For example, if the match field is a 5 digit postal code that is stored as an integer, then to specify the postal code 98053, you must use the expression =98053.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cd5-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41cd5-144">See Also</span></span>  
 [<span data-ttu-id="41cd5-145">Cartes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="41cd5-145">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
