---
title: Boîte de dialogue Règles de couleur de la carte, général | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10541"
- sql12.rtp.rptdesigner.shared.mapcolorrulesgeneral.f1
ms.assetid: 14ff5fc1-4cf8-4a45-9d98-47a1bf1c52c4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0dffc6c0b31400cb4eb9cecbbada1a52f8f41443
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613822"
---
# <a name="map-color-rules-dialog-box-general"></a><span data-ttu-id="48ec0-102">Boîte de dialogue Règles de couleur de la carte, Général</span><span class="sxs-lookup"><span data-stu-id="48ec0-102">Map Color Rules Dialog Box, General</span></span>
  <span data-ttu-id="48ec0-103">Sélectionnez **Général** dans la boîte de dialogue **Propriétés des règles de couleur** pour définir des options de couleur pour les éléments cartographiques de cette couche.</span><span class="sxs-lookup"><span data-stu-id="48ec0-103">Select **General** on the **Color Rules Properties** dialog box to define color options for map elements on this layer.</span></span> <span data-ttu-id="48ec0-104">Les éléments cartographiques peuvent être des polygones, des lignes ou des points.</span><span class="sxs-lookup"><span data-stu-id="48ec0-104">Map elements include polygons, lines, and points.</span></span> <span data-ttu-id="48ec0-105">Les règles de couleur peuvent être appliquées lorsque vous avez créé une relation entre des éléments cartographiques basés sur des données spatiales et des données analytiques provenant d'un champ de dataset ou d'un champ de source de données spatiales.</span><span class="sxs-lookup"><span data-stu-id="48ec0-105">Color rules can be applied when you have created a relationship between map elements based on spatial data and analytical data from a dataset field or from a spatial data source field.</span></span>  
  
 <span data-ttu-id="48ec0-106">Pour afficher tous les éléments cartographiques d'une couche en spécifiant un dégradé décoratif avec des couleurs primaires et secondaires différentes, utilisez la page **Remplissage** de la boîte de dialogue Propriétés des polygones de la carte.</span><span class="sxs-lookup"><span data-stu-id="48ec0-106">To display all map elements on a layer by specifying a decorative gradient with different primary and secondary colors, use the **Fill** page of the Map Polygon Properties Dialog Box.</span></span> <span data-ttu-id="48ec0-107">Les règles de couleur ont priorité sur les propriétés d'affichage d'une couche.</span><span class="sxs-lookup"><span data-stu-id="48ec0-107">Color rules take precedence over display properties for a layer.</span></span> <span data-ttu-id="48ec0-108">Pour plus d’informations, consultez [Personnaliser des données et l’affichage d’une carte ou d’une couche &#40;Générateur de rapports et SSRS&#41;](report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="48ec0-108">For more information, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="48ec0-109">Options</span><span class="sxs-lookup"><span data-stu-id="48ec0-109">Options</span></span>  
 <span data-ttu-id="48ec0-110">**Appliquer le style de modèle**</span><span class="sxs-lookup"><span data-stu-id="48ec0-110">**Apply template style**</span></span>  
 <span data-ttu-id="48ec0-111">Sélectionnez cette option pour utiliser une couleur en fonction du thème choisi dans l'Assistant ou définie dans les propriétés de la couche de polygones, de lignes ou de points.</span><span class="sxs-lookup"><span data-stu-id="48ec0-111">Select this option to use color based on the theme that was chosen in the wizard or set in the Polygon, Line, or Point layer properties.</span></span> <span data-ttu-id="48ec0-112">Un thème définit des options par défaut pour la couleur, la police et les bordures de la carte.</span><span class="sxs-lookup"><span data-stu-id="48ec0-112">A theme sets default options for color, font, and borders for the map.</span></span> <span data-ttu-id="48ec0-113">Avec cette option, aucune règle n'est appliquée pour attribuer des couleurs à chaque élément cartographique.</span><span class="sxs-lookup"><span data-stu-id="48ec0-113">For this option, no rule is applied to assign colors to each map element.</span></span>  
  
 <span data-ttu-id="48ec0-114">**Visualiser les données à l’aide de la palette de couleurs**</span><span class="sxs-lookup"><span data-stu-id="48ec0-114">**Visualize data by using color palette**</span></span>  
 <span data-ttu-id="48ec0-115">Sélectionnez cette option pour visualiser des données analytiques en utilisant des couleurs d'une palette de couleurs spécifique.</span><span class="sxs-lookup"><span data-stu-id="48ec0-115">Select this option to visualize analytical data by using colors from a specific color palette.</span></span>  
  
 <span data-ttu-id="48ec0-116">**Visualiser les données à l’aide de plages de couleurs**</span><span class="sxs-lookup"><span data-stu-id="48ec0-116">**Visualize data by using color ranges**</span></span>  
 <span data-ttu-id="48ec0-117">Sélectionnez cette option pour visualiser des données analytiques en utilisant une plage de couleurs pour chaque élément cartographique.</span><span class="sxs-lookup"><span data-stu-id="48ec0-117">Select this option to visualize analytical data by using a range of colors for each map element.</span></span> <span data-ttu-id="48ec0-118">Par exemple, si vous spécifiez Rouge comme couleur de début, Jaune comme couleur intermédiaire et Vert comme couleur de fin, les valeurs de la plage inférieure sont Rouge, celles de la plage centrale sont Jaune et celles de la plage supérieure sont Vert.</span><span class="sxs-lookup"><span data-stu-id="48ec0-118">For example, when you specify Red as a start color, Yellow as a middle color, and Green as an end color, values in the low range are Red, values in the middle range are Yellow, and values in the top range are Green.</span></span>  
  
 <span data-ttu-id="48ec0-119">**Visualiser les données à l’aide de couleurs personnalisées**</span><span class="sxs-lookup"><span data-stu-id="48ec0-119">**Visualize data by using custom colors**</span></span>  
 <span data-ttu-id="48ec0-120">Sélectionnez cette option pour visualiser des données analytiques en spécifiant votre propre liste de couleurs.</span><span class="sxs-lookup"><span data-stu-id="48ec0-120">Select this option to visualize analytical data by specifying your own list of colors.</span></span>  
  
 <span data-ttu-id="48ec0-121">**Champ de données**</span><span class="sxs-lookup"><span data-stu-id="48ec0-121">**Data field**</span></span>  
 <span data-ttu-id="48ec0-122">Cette option s'affiche lorsque vous sélectionnez l'une des options **Visualiser les données** .</span><span class="sxs-lookup"><span data-stu-id="48ec0-122">This option appears when you select one of the **Visualize data** options.</span></span>  
  
 <span data-ttu-id="48ec0-123">Dans la liste déroulante, sélectionnez le champ de données analytiques à utiliser.</span><span class="sxs-lookup"><span data-stu-id="48ec0-123">Select the analytical data field to use from the drop-down list.</span></span> <span data-ttu-id="48ec0-124">Selon la source de données spatiales, la liste affiche les champs de la source de données spatiales et d'un dataset de rapport ayant une relation entre les données spatiales et les données analytiques.</span><span class="sxs-lookup"><span data-stu-id="48ec0-124">Depending on the source of spatial data, the list displays fields from the spatial data source and from a report dataset that has a relationship between the spatial data and analytical data.</span></span> <span data-ttu-id="48ec0-125">Pour créer une telle relation, définissez les options de données dans la page Données analytiques pour la couche sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="48ec0-125">To create such a relationship, set the data options on the Analytical Data page for the selected map layer.</span></span>  
  
 <span data-ttu-id="48ec0-126">**Palette**</span><span class="sxs-lookup"><span data-stu-id="48ec0-126">**Palette**</span></span>  
 <span data-ttu-id="48ec0-127">Tapez ou sélectionnez le nom de la palette de couleurs.</span><span class="sxs-lookup"><span data-stu-id="48ec0-127">Type or select the name of the color palette.</span></span>  
  
 <span data-ttu-id="48ec0-128">**Couleur de début**</span><span class="sxs-lookup"><span data-stu-id="48ec0-128">**Start color**</span></span>  
 <span data-ttu-id="48ec0-129">Spécifiez la couleur à utiliser pour les données comprises dans la partie inférieure de la plage de données.</span><span class="sxs-lookup"><span data-stu-id="48ec0-129">Specify the color to use for data at the low end of the data range.</span></span>  
  
 <span data-ttu-id="48ec0-130">**Couleur intermédiaire**</span><span class="sxs-lookup"><span data-stu-id="48ec0-130">**Middle color**</span></span>  
 <span data-ttu-id="48ec0-131">Spécifiez la couleur à utiliser pour les données comprises dans la partie centrale de la plage de données.</span><span class="sxs-lookup"><span data-stu-id="48ec0-131">Specify the color to use for data in the middle of the data range.</span></span> <span data-ttu-id="48ec0-132">Sélectionnez **Aucune couleur** pour supprimer cette plage.</span><span class="sxs-lookup"><span data-stu-id="48ec0-132">Select **No Color** to remove this range.</span></span>  
  
 <span data-ttu-id="48ec0-133">**Couleur de fin**</span><span class="sxs-lookup"><span data-stu-id="48ec0-133">**End color**</span></span>  
 <span data-ttu-id="48ec0-134">Spécifiez la couleur à utiliser pour les données comprises dans la partie supérieure de la plage de données.</span><span class="sxs-lookup"><span data-stu-id="48ec0-134">Specify the color to use for data at the high end of the data range.</span></span>  
  
 <span data-ttu-id="48ec0-135">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="48ec0-135">**Add**</span></span>  
 <span data-ttu-id="48ec0-136">Cliquez sur **Ajouter** pour spécifier vos propres couleurs pour la règle de couleur.</span><span class="sxs-lookup"><span data-stu-id="48ec0-136">Click **Add** to specify your own colors for the color rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ec0-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48ec0-137">See Also</span></span>  
 <span data-ttu-id="48ec0-138">[Cartes &#40;Générateur de rapports et SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="48ec0-138">[Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="48ec0-139">Modifier les légendes de carte, l’échelle de couleurs et les règles associées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="48ec0-139">Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;</span></span>](report-design/change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md)  
  
  
