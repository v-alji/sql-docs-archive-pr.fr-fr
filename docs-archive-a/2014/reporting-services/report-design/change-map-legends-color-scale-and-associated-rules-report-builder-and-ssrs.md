---
title: Modifier les légendes de carte, l’échelle de couleurs et les règles associées (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.maprulesdistribution.f1
- "10512"
- "10539"
- "10533"
- sql12.rtp.rptdesigner.mappointlayerproperties.typerules.f1
- "10534"
- sql12.rtp.rptdesigner.maplegendproperties.general.f1
- sql12.rtp.rptdesigner.mapdistancescaleproperties.general.f1
- "10516"
- sql12.rtp.rptdesigner.mapcolorscaleproperties.labels.f1
- sql12.rtp.rptdesigner.maplegendtitleproperties.general.f1
- "10514"
- sql12.rtp.rptdesigner.shared.mapruleslegend.f1
- sql12.rtp.rptdesigner.mapcolorscaleproperties.general.f1
- sql12.rtp.rptdesigner.shared.embeddedlabels.f1
- "10513"
- sql12.rtp.rptdesigner.mappointlayerproperties.sizerules.f1
- sql12.rtp.rptdesigner.mapcolorscaletitleproperties.general.f1
- "10510"
- "10509"
- "10540"
- "10517"
ms.assetid: a1d691b2-c5ae-420f-af60-b7c54a7385a4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 17220c12e672ce49d3c5b1023f2a00db04e7613e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603253"
---
# <a name="change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs"></a><span data-ttu-id="bad20-102">Modifier les légendes de carte, l'échelle de couleurs et les règles associées (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="bad20-102">Change Map Legends, Color Scale, and Associated Rules (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bad20-103">Une carte peut contenir des légendes de carte, une échelle de couleurs et une échelle des distances.</span><span class="sxs-lookup"><span data-stu-id="bad20-103">A map can contain map legends, a color scale, and a distance scale.</span></span> <span data-ttu-id="bad20-104">Ces parties d'une carte aident les utilisateurs à interpréter la visualisation des données sur la carte.</span><span class="sxs-lookup"><span data-stu-id="bad20-104">These parts of a map help users interpret the data visualization on the map.</span></span>  
  
 <span data-ttu-id="bad20-105">Les légendes incluent les parties suivantes d'une carte :</span><span class="sxs-lookup"><span data-stu-id="bad20-105">Legends include the following parts of a map:</span></span>  
  
-   <span data-ttu-id="bad20-106">**Légende de carte** Affiche un guide pour faciliter l'interprétation des données analytiques qui font varier l'affichage d'un élément cartographique sur une couche.</span><span class="sxs-lookup"><span data-stu-id="bad20-106">**Map legend** Displays a guide to help interpret the analytical data that varies the display of a map elements on a map layer.</span></span> <span data-ttu-id="bad20-107">Une carte peut avoir plusieurs légendes.</span><span class="sxs-lookup"><span data-stu-id="bad20-107">A map can have multiple legends.</span></span> <span data-ttu-id="bad20-108">Pour chaque couche, vous devez spécifier la légende à utiliser.</span><span class="sxs-lookup"><span data-stu-id="bad20-108">For each map layer, you A specify which legend to use.</span></span> <span data-ttu-id="bad20-109">Une légende peut fournir un guide pour plusieurs couches.</span><span class="sxs-lookup"><span data-stu-id="bad20-109">A legend can provide a guide to more than one map layer.</span></span>  
  
-   <span data-ttu-id="bad20-110">**Échelle de couleurs** Affiche un guide pour faciliter l'interprétation des couleurs sur la carte.</span><span class="sxs-lookup"><span data-stu-id="bad20-110">**Color scale** Displays a guide to help interpret colors on the map.</span></span> <span data-ttu-id="bad20-111">Une carte a une seule échelle de couleurs.</span><span class="sxs-lookup"><span data-stu-id="bad20-111">A map has one color scale.</span></span> <span data-ttu-id="bad20-112">Plusieurs couches peuvent fournir les données de l'échelle de couleurs.</span><span class="sxs-lookup"><span data-stu-id="bad20-112">Multiple layers can provide the data for the color scale.</span></span>  
  
-   <span data-ttu-id="bad20-113">**Échelle des distances** Affiche un guide pour faciliter l'interprétation de l'échelle de la carte.</span><span class="sxs-lookup"><span data-stu-id="bad20-113">**Distance scale** Displays a guide to help interpret the scale of the map.</span></span> <span data-ttu-id="bad20-114">Une carte a une seule échelle des distances.</span><span class="sxs-lookup"><span data-stu-id="bad20-114">A map has one distance scale.</span></span> <span data-ttu-id="bad20-115">La valeur de zoom du point de vue de la carte active détermine l'échelle des distances.</span><span class="sxs-lookup"><span data-stu-id="bad20-115">The current map viewport zoom value determines the distance scale.</span></span>  
  
 <span data-ttu-id="bad20-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span><span class="sxs-lookup"><span data-stu-id="bad20-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><a name="Viewport"></a> <span data-ttu-id="bad20-117">Pour modifier la position d'une légende par rapport à la fenêtre d'affichage</span><span class="sxs-lookup"><span data-stu-id="bad20-117">To change the position of a legend relative to the viewport</span></span>  
  
#### <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><span data-ttu-id="bad20-118">Pour modifier la position d'une légende par rapport à la fenêtre d'affichage</span><span class="sxs-lookup"><span data-stu-id="bad20-118">To change the position of a legend relative to the viewport</span></span>  
  
1.  <span data-ttu-id="bad20-119">Dans Mode Création, cliquez avec le bouton droit sur la légende et ouvrez la _\<report item->_ page **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="bad20-119">In Design view, right-click the legend and open the _\<report item->_**Properties** page.</span></span>  
  
2.  <span data-ttu-id="bad20-120">Dans **Position**, cliquez sur l'emplacement qui spécifie où afficher la légende par rapport à la fenêtre d'affichage.</span><span class="sxs-lookup"><span data-stu-id="bad20-120">In **Position**, click the location that specifies where to display the legend relative to the viewport.</span></span>  
  
3.  <span data-ttu-id="bad20-121">Pour afficher la légende en dehors de la fenêtre d’affichage, sélectionnez **afficher l' \<report item> extérieur**de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="bad20-121">To display the legend outside the viewport, select **Show \<report item> outside viewport**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="bad20-122">Dans l'aperçu, les légendes de carte et l'échelle de couleurs s'affichent uniquement lorsqu'il existe des résultats des règles connexes à cette légende.</span><span class="sxs-lookup"><span data-stu-id="bad20-122">In preview, map legends and the color scale appear only when there are results from the rules related to that legend.</span></span> <span data-ttu-id="bad20-123">S'il n'y a pas d'éléments à afficher, la légende ne s'affiche pas dans le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="bad20-123">If there are no items to display, the legend does not appear in the rendered report.</span></span>  
  
  
  
##  <a name="to-change-the-layout-of-a-map-legend"></a><a name="MapLegend"></a> <span data-ttu-id="bad20-124">Pour modifier la disposition d'une légende de carte</span><span class="sxs-lookup"><span data-stu-id="bad20-124">To change the layout of a map legend</span></span>  
  
#### <a name="to-change-the-layout-of-a-map-legend"></a><span data-ttu-id="bad20-125">Pour modifier la disposition d'une légende de carte</span><span class="sxs-lookup"><span data-stu-id="bad20-125">To change the layout of a map legend</span></span>  
  
1.  <span data-ttu-id="bad20-126">En mode Conception, cliquez avec le bouton droit sur la légende et ouvrez la page **Propriétés de la légende** .</span><span class="sxs-lookup"><span data-stu-id="bad20-126">In Design view, right-click the legend and open the **Legend Properties** page.</span></span>  
  
2.  <span data-ttu-id="bad20-127">Dans **Disposition de la légende**, cliquez sur la disposition de table que vous souhaitez utiliser pour la légende.</span><span class="sxs-lookup"><span data-stu-id="bad20-127">In **Legend layout**, click the table layout that you want to use for the legend.</span></span> <span data-ttu-id="bad20-128">Lorsque vous cliquez sur différentes options, la disposition sur l'aire de conception change.</span><span class="sxs-lookup"><span data-stu-id="bad20-128">As you click different options, the layout on the design surface changes.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-show-or-hide-a-map-legend-title"></a><a name="MapLegendTitle"></a> <span data-ttu-id="bad20-129">Pour afficher ou masquer un titre de légende de carte</span><span class="sxs-lookup"><span data-stu-id="bad20-129">To show or hide a map legend title</span></span>  
  
#### <a name="to-show-or-hide-a-map-legend-title"></a><span data-ttu-id="bad20-130">Pour afficher ou masquer un titre de légende de carte</span><span class="sxs-lookup"><span data-stu-id="bad20-130">To show or hide a map legend title</span></span>  
  
-   <span data-ttu-id="bad20-131">Cliquez avec le bouton droit sur la légende de carte sur l’aire de conception, puis cliquez sur **Afficher le titre de la légende**.</span><span class="sxs-lookup"><span data-stu-id="bad20-131">Right-click the map legend on the design surface, and then click **Show Legend Title**.</span></span>  
  
  
  
##  <a name="to-show-or-hide-a-color-scale-title"></a><a name="ColorScaleTitle"></a> <span data-ttu-id="bad20-132">Pour afficher ou masquer un titre d'échelle de couleurs</span><span class="sxs-lookup"><span data-stu-id="bad20-132">To show or hide a color scale title</span></span>  
  
#### <a name="to-show-or-hide-a-color-scale-title"></a><span data-ttu-id="bad20-133">Pour afficher ou masquer un titre d'échelle de couleurs</span><span class="sxs-lookup"><span data-stu-id="bad20-133">To show or hide a color scale title</span></span>  
  
-   <span data-ttu-id="bad20-134">Cliquez avec le bouton droit sur l’échelle de couleurs sur l’aire de conception, puis cliquez sur **Afficher le titre de l’échelle de couleurs**.</span><span class="sxs-lookup"><span data-stu-id="bad20-134">Right-click the color scale on the design surface, and then click **Show Color Scale Title**.</span></span>  
  
  
  
##  <a name="to-move-items-out-of-the-first-legend"></a><a name="MoveItems"></a> <span data-ttu-id="bad20-135">Pour déplacer des éléments hors de la première légende</span><span class="sxs-lookup"><span data-stu-id="bad20-135">To move items out of the first legend</span></span>  
 <span data-ttu-id="bad20-136">Créez autant de légendes supplémentaires que nécessaire, puis mettez à jour les règles de chaque couche en spécifiant la légende dans laquelle afficher les résultats des règles.</span><span class="sxs-lookup"><span data-stu-id="bad20-136">Create as many additional legends as you need and then update the rules for each map layer specify which legend to display the rule results in.</span></span>  
  
#### <a name="to-create-a-new-legend"></a><span data-ttu-id="bad20-137">Pour créer une légende</span><span class="sxs-lookup"><span data-stu-id="bad20-137">To create a new legend</span></span>  
  
-   <span data-ttu-id="bad20-138">En mode Conception, cliquez avec le bouton droit sur la carte à l’extérieur du point de vue de la carte, puis cliquez sur **Ajouter une légende**.</span><span class="sxs-lookup"><span data-stu-id="bad20-138">In Design view, right-click the map outside the map viewport, and then click **Add Legend**.</span></span>  
  
     <span data-ttu-id="bad20-139">Une nouvelle légende apparaît sur la carte.</span><span class="sxs-lookup"><span data-stu-id="bad20-139">A new legend appears on the map.</span></span>  
  
#### <a name="to-display-rule-results-in-a-legend"></a><span data-ttu-id="bad20-140">Pour afficher des résultats des règles dans une légende</span><span class="sxs-lookup"><span data-stu-id="bad20-140">To display rule results in a legend</span></span>  
  
1.  <span data-ttu-id="bad20-141">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-141">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-142">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle de couleur**.</span><span class="sxs-lookup"><span data-stu-id="bad20-142">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-143">Cliquez sur **Légende**.</span><span class="sxs-lookup"><span data-stu-id="bad20-143">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="bad20-144">Dans la liste déroulante **Afficher dans cette légende** , cliquez sur le nom de la légende dans laquelle afficher les résultats des règles.</span><span class="sxs-lookup"><span data-stu-id="bad20-144">In the **Show in this legend** drop-down list, click the name of the legend to display the rule results in.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-a-template-style"></a><a name="TemplateStyle"></a> <span data-ttu-id="bad20-145">Pour faire varier les couleurs d'éléments cartographiques en fonction d'un style de modèle</span><span class="sxs-lookup"><span data-stu-id="bad20-145">To vary map element colors based on a template style</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-a-template-style"></a><span data-ttu-id="bad20-146">Pour faire varier les couleurs d'éléments cartographiques en fonction d'un style de modèle</span><span class="sxs-lookup"><span data-stu-id="bad20-146">To vary map element colors based on a template style</span></span>  
  
1.  <span data-ttu-id="bad20-147">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-147">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-148">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle de couleur**.</span><span class="sxs-lookup"><span data-stu-id="bad20-148">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-149">Cliquez sur **Appliquer le style du modèle**.</span><span class="sxs-lookup"><span data-stu-id="bad20-149">Click **Apply template style**.</span></span>  
  
     <span data-ttu-id="bad20-150">Un style de modèle spécifie la police, le style de bordure et la palette de couleurs.</span><span class="sxs-lookup"><span data-stu-id="bad20-150">A template style specifies font, border style, and color palette.</span></span> <span data-ttu-id="bad20-151">À chaque élément cartographique est attribuée une couleur différente de la palette de couleurs correspondant au thème spécifié dans l'Assistant Carte ou Couche.</span><span class="sxs-lookup"><span data-stu-id="bad20-151">Each map element is assigned a different color from the color palette for the theme that was specified in the Map Wizard or Map Layer Wizard.</span></span> <span data-ttu-id="bad20-152">Il s'agit de la seule option s'appliquant aux couches qui n'ont pas de données analytiques associées.</span><span class="sxs-lookup"><span data-stu-id="bad20-152">This is the only option that applies to layers that do not have associated analytical data.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-palette"></a><a name="ColorPalette"></a> <span data-ttu-id="bad20-153">Pour faire varier les couleurs d'éléments cartographiques en fonction de la palette de couleurs</span><span class="sxs-lookup"><span data-stu-id="bad20-153">To vary map element colors based on color palette</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-palette"></a><span data-ttu-id="bad20-154">Pour faire varier les couleurs d'éléments cartographiques en fonction de la palette de couleurs</span><span class="sxs-lookup"><span data-stu-id="bad20-154">To vary map element colors based on color palette</span></span>  
  
1.  <span data-ttu-id="bad20-155">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-155">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-156">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle de couleur**.</span><span class="sxs-lookup"><span data-stu-id="bad20-156">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-157">Cliquez sur **Visualiser les données à l'aide de la palette de couleurs**.</span><span class="sxs-lookup"><span data-stu-id="bad20-157">Click **Visualize data by using color palette**.</span></span>  
  
     <span data-ttu-id="bad20-158">Cette option utilise une palette intégrée ou personnalisée que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="bad20-158">This option uses a built-in or custom palette that you specify.</span></span> <span data-ttu-id="bad20-159">En fonction des données analytiques connexes, une couleur différente ou un ton de couleur différent de la palette est attribué à chaque élément cartographique.</span><span class="sxs-lookup"><span data-stu-id="bad20-159">Based on related analytical data, each map element is assigned a different color or shade of color from the palette.</span></span>  
  
4.  <span data-ttu-id="bad20-160">Dans **Champ de données**, tapez le nom du champ contenant les données analytiques que vous souhaitez visualiser à l'aide de couleurs.</span><span class="sxs-lookup"><span data-stu-id="bad20-160">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="bad20-161">Dans **Palette**, sélectionnez le nom de la palette à utiliser dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="bad20-161">In **Palette**, from the drop-down list, select the name of the palette to use.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-ranges"></a><a name="ColorRanges"></a> <span data-ttu-id="bad20-162">Pour faire varier les couleurs d'éléments cartographiques en fonction des plages de couleurs</span><span class="sxs-lookup"><span data-stu-id="bad20-162">To vary map element colors based on color ranges</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-ranges"></a><span data-ttu-id="bad20-163">Pour faire varier les couleurs d'éléments cartographiques en fonction des plages de couleurs</span><span class="sxs-lookup"><span data-stu-id="bad20-163">To vary map element colors based on color ranges</span></span>  
  
1.  <span data-ttu-id="bad20-164">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-164">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-165">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle de couleur**.</span><span class="sxs-lookup"><span data-stu-id="bad20-165">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-166">Cliquez sur **Visualiser les données à l'aide de plages de couleurs**.</span><span class="sxs-lookup"><span data-stu-id="bad20-166">Click **Visualize data by using color ranges**.</span></span>  
  
     <span data-ttu-id="bad20-167">Cette option, combinée aux couleurs de début, intermédiaire et de fin que vous spécifiez dans cette page et aux options que vous spécifiez dans la page **Distribution** , divise les données analytiques connexes en plages.</span><span class="sxs-lookup"><span data-stu-id="bad20-167">This option, combined with the start, middle, and end colors that you specify on this page and the options that you specify on the **Distribution** page, divide the related analytical data into ranges.</span></span> <span data-ttu-id="bad20-168">Le processeur de rapports attribue la couleur appropriée à chaque élément cartographique en fonction de ses données associées et de la plage dans laquelle il est situé.</span><span class="sxs-lookup"><span data-stu-id="bad20-168">The report processor assigns the appropriate color to each map element based on the its associated data and the range that it falls into.</span></span>  
  
4.  <span data-ttu-id="bad20-169">Dans **Champ de données**, tapez le nom du champ contenant les données analytiques que vous souhaitez visualiser à l'aide de couleurs.</span><span class="sxs-lookup"><span data-stu-id="bad20-169">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="bad20-170">Dans **Couleur de début**, spécifiez la couleur à utiliser pour la plage la plus basse.</span><span class="sxs-lookup"><span data-stu-id="bad20-170">In **Start color**, specify the color to use for the lowest range.</span></span>  
  
6.  <span data-ttu-id="bad20-171">Dans **Couleur intermédiaire**, spécifiez la couleur à utiliser pour la plage centrale.</span><span class="sxs-lookup"><span data-stu-id="bad20-171">In **Middle color**, specify the color to use for the middle range.</span></span>  
  
7.  <span data-ttu-id="bad20-172">Dans **Couleur de fin**, spécifiez la couleur à utiliser pour la plage la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="bad20-172">In **End color**, specify the color to use for the highest range.</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-custom-colors"></a><a name="CustomColors"></a> <span data-ttu-id="bad20-173">Pour faire varier les couleurs d'éléments cartographiques en fonction de couleurs personnalisées</span><span class="sxs-lookup"><span data-stu-id="bad20-173">To vary map element colors based on custom colors</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-custom-colors"></a><span data-ttu-id="bad20-174">Pour faire varier les couleurs d'éléments cartographiques en fonction de couleurs personnalisées</span><span class="sxs-lookup"><span data-stu-id="bad20-174">To vary map element colors based on custom colors</span></span>  
  
1.  <span data-ttu-id="bad20-175">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-175">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-176">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle de couleur**.</span><span class="sxs-lookup"><span data-stu-id="bad20-176">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-177">Cliquez sur **Visualiser les données à l'aide de couleurs personnalisées**.</span><span class="sxs-lookup"><span data-stu-id="bad20-177">Click **Visualize data by using custom colors**.</span></span>  
  
     <span data-ttu-id="bad20-178">Cette option utilise une liste de couleurs que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="bad20-178">This option uses the list of colors that you specify.</span></span> <span data-ttu-id="bad20-179">En fonction des données analytiques connexes, une couleur de la liste est affectée à chaque élément cartographique.</span><span class="sxs-lookup"><span data-stu-id="bad20-179">Based on related analytical data, each map element is assigned a color from the list.</span></span> <span data-ttu-id="bad20-180">S'il y a plus d'éléments cartographiques que de couleurs, aucune couleur n'est attribuée.</span><span class="sxs-lookup"><span data-stu-id="bad20-180">If there are more map elements than colors, no color is assigned.</span></span>  
  
4.  <span data-ttu-id="bad20-181">Dans **Champ de données**, tapez le nom du champ contenant les données analytiques que vous souhaitez visualiser à l'aide de couleurs.</span><span class="sxs-lookup"><span data-stu-id="bad20-181">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="bad20-182">Dans **Couleurs personnalisées**, cliquez sur **Ajouter** pour spécifier chaque couleur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="bad20-182">In **Custom colors**, click **Add** to specify each custom color.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-set-distribution-options-for-a-legend"></a><a name="DistributionOptions"></a> <span data-ttu-id="bad20-183">Pour définir des options de distribution pour une légende</span><span class="sxs-lookup"><span data-stu-id="bad20-183">To set distribution options for a legend</span></span>  
  
#### <a name="to-set-distribution-options-for-a-legend"></a><span data-ttu-id="bad20-184">Pour définir des options de distribution pour une légende</span><span class="sxs-lookup"><span data-stu-id="bad20-184">To set distribution options for a legend</span></span>  
  
1.  <span data-ttu-id="bad20-185">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-185">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-186">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle de couleur**.</span><span class="sxs-lookup"><span data-stu-id="bad20-186">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-187">Sélectionnez l’option **visualiser les données à l’aide de** \<rule type\> .</span><span class="sxs-lookup"><span data-stu-id="bad20-187">Select the **Visualize data by using** \<rule type\> option.</span></span> <span data-ttu-id="bad20-188">Pour utiliser des options de distribution, vous devez créer des plages dans la page **Distribution** en fonction des données analytiques associées à la couche.</span><span class="sxs-lookup"><span data-stu-id="bad20-188">To use distribution options, you must create ranges on the **Distribution** page based on analytical data that is associated with the layer.</span></span>  
  
4.  <span data-ttu-id="bad20-189">Cliquez sur **Distribution**.</span><span class="sxs-lookup"><span data-stu-id="bad20-189">Click **Distribution**.</span></span>  
  
5.  <span data-ttu-id="bad20-190">Sélectionnez l'un des types de distribution suivants :</span><span class="sxs-lookup"><span data-stu-id="bad20-190">Select one of the following distribution types:</span></span>  
  
    -   <span data-ttu-id="bad20-191">**EqualInterval**.</span><span class="sxs-lookup"><span data-stu-id="bad20-191">**EqualInterval**.</span></span> <span data-ttu-id="bad20-192">Spécifie des plages qui divisent les données en intervalles de plages égaux.</span><span class="sxs-lookup"><span data-stu-id="bad20-192">Specifies ranges that divide the data into equal range intervals.</span></span>  
  
    -   <span data-ttu-id="bad20-193">**EqualDistribution**.</span><span class="sxs-lookup"><span data-stu-id="bad20-193">**EqualDistribution**.</span></span> <span data-ttu-id="bad20-194">Spécifie des plages qui divisent les données de sorte que toutes les plages ont le même nombre d'éléments.</span><span class="sxs-lookup"><span data-stu-id="bad20-194">Specifies ranges that divide that data so that each range has an equal number of items.</span></span>  
  
    -   <span data-ttu-id="bad20-195">**Optimal**.</span><span class="sxs-lookup"><span data-stu-id="bad20-195">**Optimal**.</span></span> <span data-ttu-id="bad20-196">Spécifie des plages qui ajustent automatiquement la distribution pour créer des sous-plages équilibrées.</span><span class="sxs-lookup"><span data-stu-id="bad20-196">Specifies ranges that automatically adjust distribution to create balanced subranges.</span></span>  
  
    -   <span data-ttu-id="bad20-197">**Personnalisez**.</span><span class="sxs-lookup"><span data-stu-id="bad20-197">**Custom**.</span></span> <span data-ttu-id="bad20-198">Spécifiez votre propre nombre de plages pour contrôler la distribution de valeurs.</span><span class="sxs-lookup"><span data-stu-id="bad20-198">Specify your own number of ranges to control the distribution of values.</span></span>  
  
     <span data-ttu-id="bad20-199">Pour plus d’informations sur les options de distribution, consultez [Modifier l’affichage des polygones, des lignes et des points à l’aide de règles et de données analytiques &#40;Générateur de rapports et SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="bad20-199">For more information about distribution options, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
6.  <span data-ttu-id="bad20-200">Dans **Nombre de sous-plages**, tapez le nombre de sous-plages à utiliser.</span><span class="sxs-lookup"><span data-stu-id="bad20-200">In **Number of subranges**, type the number of subranges to use.</span></span> <span data-ttu-id="bad20-201">Lorsque le type de distribution est **Optimal**, le nombre de sous-plages est calculé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="bad20-201">When the distribution type is **Optimal**, the number of subranges is automatically calculated.</span></span>  
  
7.  <span data-ttu-id="bad20-202">Dans **Début de plage**, tapez une valeur de plage minimale.</span><span class="sxs-lookup"><span data-stu-id="bad20-202">In **Range start**, type a minimum range value.</span></span> <span data-ttu-id="bad20-203">Toutes les valeurs inférieures à ce nombre sont égales à la valeur de plage minimale.</span><span class="sxs-lookup"><span data-stu-id="bad20-203">All values less than this number are the same as the range minimum.</span></span>  
  
8.  <span data-ttu-id="bad20-204">Dans **Fin de plage**, tapez une valeur de plage maximale.</span><span class="sxs-lookup"><span data-stu-id="bad20-204">In **Range end**, type a maximum range value.</span></span> <span data-ttu-id="bad20-205">Toutes les valeurs supérieures à ce nombre sont égales à la valeur de plage maximale.</span><span class="sxs-lookup"><span data-stu-id="bad20-205">All values larger than this number are the same as the range maximum.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-a-rule-legend"></a><a name="RuleLegend"></a> <span data-ttu-id="bad20-206">Pour modifier le contenu d'une légende de règle</span><span class="sxs-lookup"><span data-stu-id="bad20-206">To change the contents of a rule legend</span></span>  
  
#### <a name="to-change-the-contents-of-a-color-size-width-or-marker-type-legend"></a><span data-ttu-id="bad20-207">Pour modifier le contenu d'une légende de couleur, de taille, de largeur ou de type de marqueur</span><span class="sxs-lookup"><span data-stu-id="bad20-207">To change the contents of a color, size, width, or marker type legend</span></span>  
  
1.  <span data-ttu-id="bad20-208">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-208">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-209">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle**.</span><span class="sxs-lookup"><span data-stu-id="bad20-209">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-210">Vérifiez que **l’option visualiser les données à l’aide de** \<*rule type*> est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bad20-210">Verify that **Visualize data by using** \<*rule type*> is selected.</span></span>  
  
4.  <span data-ttu-id="bad20-211">Dans **Champ de données**, vérifiez que les données analytiques que vous visualisez sur la couche sont sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="bad20-211">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bad20-212">Si aucun champ ne s’affiche dans la liste déroulante, cliquez avec le bouton droit sur la couche, puis cliquez sur **Données de la couche** pour ouvrir la boîte de dialogue Propriétés des données de la couche de la carte à la page Données analytiques et vérifier que vous avez spécifié des données analytiques pour cette couche.</span><span class="sxs-lookup"><span data-stu-id="bad20-212">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="bad20-213">Cliquez sur **Légende**.</span><span class="sxs-lookup"><span data-stu-id="bad20-213">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="bad20-214">Dans **Afficher dans cette légende**, sélectionnez la légende de carte à utiliser pour afficher les résultats des règles.</span><span class="sxs-lookup"><span data-stu-id="bad20-214">In **Show in this legend**, select the map legend to use to display the rule results.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-the-color-scale"></a><a name="ColorScale"></a> <span data-ttu-id="bad20-215">Pour modifier le contenu de l'échelle de couleurs</span><span class="sxs-lookup"><span data-stu-id="bad20-215">To change the contents of the color scale</span></span>  
  
#### <a name="to-change-the-contents-of-the-color-scale-or-a-color-legend"></a><span data-ttu-id="bad20-216">Pour modifier le contenu de l'échelle de couleurs ou d'une légende de couleur</span><span class="sxs-lookup"><span data-stu-id="bad20-216">To change the contents of the color scale or a color legend</span></span>  
  
1.  <span data-ttu-id="bad20-217">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-217">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-218">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle de couleur**.</span><span class="sxs-lookup"><span data-stu-id="bad20-218">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-219">Sélectionnez l'option de règle de couleur à utiliser.</span><span class="sxs-lookup"><span data-stu-id="bad20-219">Select the color rule option to use.</span></span> <span data-ttu-id="bad20-220">Pour afficher des éléments dans une légende de carte ou une échelle de couleurs, vous devez sélectionner l’une des options **visualiser les données à l’aide des** \<rule type> options.</span><span class="sxs-lookup"><span data-stu-id="bad20-220">To display items in a map legend or color scale, you must select one of the **Visualize data by using** \<rule type> options.</span></span>  
  
4.  <span data-ttu-id="bad20-221">Dans **Champ de données**, vérifiez que les données analytiques que vous visualisez sur la couche sont sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="bad20-221">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bad20-222">Si aucun champ ne s’affiche dans la liste déroulante, cliquez avec le bouton droit sur la couche, puis cliquez sur **Données de la couche** pour ouvrir la boîte de dialogue Propriétés des données de la couche de la carte à la page Données analytiques et vérifier que vous avez spécifié des données analytiques pour cette couche.</span><span class="sxs-lookup"><span data-stu-id="bad20-222">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="bad20-223">Cliquez sur **Légende**.</span><span class="sxs-lookup"><span data-stu-id="bad20-223">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="bad20-224">Dans **Options d'échelle de couleurs**, sélectionnez **Afficher dans l'échelle de couleurs** pour afficher les résultats de la règle dans l'échelle de couleurs.</span><span class="sxs-lookup"><span data-stu-id="bad20-224">In **Color scale options**, select **Show in color scale** to display the rule results in the color scale.</span></span> <span data-ttu-id="bad20-225">Vous pouvez spécifier cette option pour plusieurs règles de couleur.</span><span class="sxs-lookup"><span data-stu-id="bad20-225">You can specify this option for more than one color rule.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-remove-all-items-from-a-legend"></a><a name="HideItems"></a> <span data-ttu-id="bad20-226">Pour supprimer tous les éléments d'une légende</span><span class="sxs-lookup"><span data-stu-id="bad20-226">To remove all items from a legend</span></span>  
  
#### <a name="to-hide-items-based-on-a-rule"></a><span data-ttu-id="bad20-227">Pour masquer des éléments en fonction d'une règle</span><span class="sxs-lookup"><span data-stu-id="bad20-227">To hide items based on a rule</span></span>  
  
1.  <span data-ttu-id="bad20-228">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-228">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-229">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle**.</span><span class="sxs-lookup"><span data-stu-id="bad20-229">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-230">Cliquez sur **Légende**.</span><span class="sxs-lookup"><span data-stu-id="bad20-230">Click **Legend**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-format-of-content-in-a-legend"></a><a name="ChangeFormatItems"></a> <span data-ttu-id="bad20-231">Pour modifier le format de contenu d'une légende</span><span class="sxs-lookup"><span data-stu-id="bad20-231">To change the format of content in a legend</span></span>  
 <span data-ttu-id="bad20-232">Définissez les options de légende pour la règle associée à la légende de la carte.</span><span class="sxs-lookup"><span data-stu-id="bad20-232">Set legend options for the rule that is associated with the map legend.</span></span>  
  
#### <a name="to-change-the-format-of-content-in-a-legend"></a><span data-ttu-id="bad20-233">Pour modifier le format de contenu d'une légende</span><span class="sxs-lookup"><span data-stu-id="bad20-233">To change the format of content in a legend</span></span>  
  
1.  <span data-ttu-id="bad20-234">En mode Conception, cliquez sur la carte jusqu'à ce que le volet Carte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bad20-234">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="bad20-235">Cliquez avec le bouton droit sur la couche qui contient les données souhaitées, puis cliquez sur _\<map element type\>_ **règle**.</span><span class="sxs-lookup"><span data-stu-id="bad20-235">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="bad20-236">Cliquez sur **Légende**.</span><span class="sxs-lookup"><span data-stu-id="bad20-236">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="bad20-237">**Texte de légende** affiche des mots clés qui spécifient les données qui doivent apparaître dans la légende.</span><span class="sxs-lookup"><span data-stu-id="bad20-237">**Legend text** displays keywords that specify which data appears in the legend.</span></span> <span data-ttu-id="bad20-238">Utilisez des mots clés de carte et des formats personnalisés pour contrôler le format du texte de légende.</span><span class="sxs-lookup"><span data-stu-id="bad20-238">Use map keywords and custom formats to help control the format of legend text.</span></span> <span data-ttu-id="bad20-239">Par exemple, #FROMVALUE {C2} spécifie un format de devise à deux décimales.</span><span class="sxs-lookup"><span data-stu-id="bad20-239">For example, #FROMVALUE {C2} specifies a currency format with two decimal places.</span></span> <span data-ttu-id="bad20-240">Pour plus d’informations, consultez [Modifier l’affichage des polygones, des lignes et des points à l’aide de règles et de données analytiques &#40;Générateur de rapports et SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="bad20-240">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="bad20-241">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bad20-241">See Also</span></span>  
 <span data-ttu-id="bad20-242">[Cartes &#40;Générateur de rapports et SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bad20-242">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bad20-243">[Ajouter, changer ou supprimer une carte ou une couche &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bad20-243">[Add, Change, or Delete a Map or Map Layer &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bad20-244">[Personnaliser des données et l’affichage d’une carte ou d’une couche &#40;Générateur de rapports et SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bad20-244">[Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bad20-245">[Résoudre les problèmes liés aux rapports : rapports cartographiques &#40;Générateur de rapports et SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bad20-245">[Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bad20-246">Assistant Carte et Assistant Couche &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bad20-246">Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;</span></span>](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)  
  
  
