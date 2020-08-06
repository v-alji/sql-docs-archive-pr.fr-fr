---
title: Ajouter des emplacements personnalisés à une carte (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- MICROSOFT.REPORTDESIGNER.MAPPOINT.POINTTEMPLATE
ms.assetid: 7d36faae-5bcc-446a-9eba-f42349cafacb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 167558534280f08d576205b5ff1b94d0588fcb78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706244"
---
# <a name="add-custom-locations-to-a-map-report-builder-and-ssrs"></a><span data-ttu-id="ba37d-102">Ajouter des emplacements personnalisés à une carte (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ba37d-102">Add Custom Locations to a Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ba37d-103">Après avoir ajouté une carte à un rapport, vous pouvez ajouter vos propres emplacements de points.</span><span class="sxs-lookup"><span data-stu-id="ba37d-103">After you add a map to a report, you can add your own point locations.</span></span>  
  
 <span data-ttu-id="ba37d-104">Les propriétés d'affichage de tous les points d'une couche sont contrôlées en définissant des options pour les propriétés des points de la couche.</span><span class="sxs-lookup"><span data-stu-id="ba37d-104">Display properties for all points on a layer are controlled by setting options for the point properties for the layer.</span></span> <span data-ttu-id="ba37d-105">Pour un point incorporé sélectionné, vous pouvez remplacer les propriétés d'affichage.</span><span class="sxs-lookup"><span data-stu-id="ba37d-105">For a selected embedded point, you can override the display properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba37d-106">Lorsque vous remplacez les propriétés d'affichage de couche pour le point incorporé, les modifications que vous apportez ne sont pas réversibles.</span><span class="sxs-lookup"><span data-stu-id="ba37d-106">When you override the layer display properties for the embedded point, the changes that you make are not reversible.</span></span>  
  
 <span data-ttu-id="ba37d-107">Pour plus d’informations, consultez [Modifier l’affichage des polygones, des lignes et des points à l’aide de règles et de données analytiques &#40;Générateur de rapports et SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="ba37d-107">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-point-layer"></a><span data-ttu-id="ba37d-108">Pour ajouter une couche de points</span><span class="sxs-lookup"><span data-stu-id="ba37d-108">To add a point layer</span></span>  
  
1.  <span data-ttu-id="ba37d-109">Sur l'aire de conception du rapport, cliquez sur la carte pour la sélectionner et afficher le volet Carte.</span><span class="sxs-lookup"><span data-stu-id="ba37d-109">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="ba37d-110">Dans la barre d’outils, cliquez sur **Ajouter une couche**.</span><span class="sxs-lookup"><span data-stu-id="ba37d-110">On the toolbar, click **Add Layer**.</span></span>  
  
3.  <span data-ttu-id="ba37d-111">Dans la liste déroulante, cliquez sur **Ajouter une couche de points**.</span><span class="sxs-lookup"><span data-stu-id="ba37d-111">From the drop-down list, click **Add Point Layer**.</span></span> <span data-ttu-id="ba37d-112">Une couche de points sans points est ajoutée à la carte.</span><span class="sxs-lookup"><span data-stu-id="ba37d-112">A point layer with no points is added to the map.</span></span> <span data-ttu-id="ba37d-113">Par défaut, la couche de points est prête pour que vous ajoutiez des points incorporés.</span><span class="sxs-lookup"><span data-stu-id="ba37d-113">By default, the point layer is ready for embedded points.</span></span>  
  
### <a name="to-add-a-custom-point"></a><span data-ttu-id="ba37d-114">Pour ajouter un point personnalisé</span><span class="sxs-lookup"><span data-stu-id="ba37d-114">To add a custom point</span></span>  
  
1.  <span data-ttu-id="ba37d-115">Sur l'aire de conception du rapport, cliquez sur la carte pour la sélectionner et afficher le volet Carte.</span><span class="sxs-lookup"><span data-stu-id="ba37d-115">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="ba37d-116">Dans le volet Carte, cliquez avec le bouton droit sur une couche de points de type **Incorporé**, puis cliquez sur **Ajouter un point**.</span><span class="sxs-lookup"><span data-stu-id="ba37d-116">In the Map pane, right-click a point layer that has type **Embedded**, and then click **Add Point**.</span></span> <span data-ttu-id="ba37d-117">Le curseur se transforme en croix.</span><span class="sxs-lookup"><span data-stu-id="ba37d-117">The cursor changes to crosshairs.</span></span>  
  
3.  <span data-ttu-id="ba37d-118">Pour ajouter un point, cliquez sur un emplacement sur la carte.</span><span class="sxs-lookup"><span data-stu-id="ba37d-118">To add a point, click a location on the map.</span></span> <span data-ttu-id="ba37d-119">Un point incorporé est ajouté à la couche sélectionnée à l'emplacement où vous cliquez.</span><span class="sxs-lookup"><span data-stu-id="ba37d-119">An embedded point is added to the selected layer at the location where you click.</span></span>  
  
### <a name="to-customize-the-display-for-an-embedded-point"></a><span data-ttu-id="ba37d-120">Pour personnaliser l'affichage pour un point incorporé</span><span class="sxs-lookup"><span data-stu-id="ba37d-120">To customize the display for an embedded point</span></span>  
  
1.  <span data-ttu-id="ba37d-121">Cliquez avec le bouton droit sur le point, puis cliquez sur **Propriétés des points**.</span><span class="sxs-lookup"><span data-stu-id="ba37d-121">Right-click the point, and then click **Point Properties**.</span></span> <span data-ttu-id="ba37d-122">La boîte de dialogue **Propriétés des points incorporés de la carte** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="ba37d-122">The **Map Embedded Point Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="ba37d-123">Cliquez sur **Remplacer les options de point pour cette couche**.</span><span class="sxs-lookup"><span data-stu-id="ba37d-123">Click **Override point options for this layer**.</span></span> <span data-ttu-id="ba37d-124">Plusieurs pages de propriétés s'affichent dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="ba37d-124">Multiple property pages appear in the left pane.</span></span>  
  
3.  <span data-ttu-id="ba37d-125">Cliquez sur les pages et définissez les propriétés d'affichage que vous souhaitez appliquer à ce point.</span><span class="sxs-lookup"><span data-stu-id="ba37d-125">Click the pages and set the display properties that you want to apply to this point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba37d-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba37d-126">See Also</span></span>  
 <span data-ttu-id="ba37d-127">[Cartes &#40;Générateur de rapports et SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ba37d-127">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ba37d-128">Modifier l’affichage des polygones, des lignes et des points à l’aide de règles et de données analytiques &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ba37d-128">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
