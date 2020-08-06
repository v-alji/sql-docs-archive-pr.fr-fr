---
title: 'Tutoriel : Rapport cartographique (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8d831356-7efa-40cc-ae95-383b3eecf833
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b737bb3fe74eb3524f2944a7458cb4837b1aeedf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706100"
---
# <a name="tutorial-map-report-report-builder"></a><span data-ttu-id="b5ad4-102">Tutoriel : Rapport cartographique (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="b5ad4-102">Tutorial: Map Report (Report Builder)</span></span>
  <span data-ttu-id="b5ad4-103">Ce didacticiel est conçu pour vous aider à découvrir les fonctionnalités cartographiques que vous pouvez utiliser pour afficher des données de rapport sur un arrière-plan géographique.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-103">This tutorial is designed to help you learn about the map features you can use to display report data against a geographic background.</span></span>  
  
 <span data-ttu-id="b5ad4-104">Les cartes sont basées sur des données spatiales qui comportent en général des points, des lignes et des polygones.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-104">Maps are based on spatial data that typically consists of points, lines, and polygons.</span></span> <span data-ttu-id="b5ad4-105">Par exemple, un polygone peut représenter le contour d'un comté, une ligne peut représenter une route, et un point peut représenter l'emplacement d'une ville.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-105">For example, a polygon can represent the outline of a county, a line can represent a road, and a point can represent the location of a city.</span></span> <span data-ttu-id="b5ad4-106">Chaque type de données spatiales est affiché sur une couche séparée sous la forme d'un jeu d'éléments cartographiques.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-106">Each type of spatial data is displayed on a separate map layer as a set of map elements.</span></span>  
  
 <span data-ttu-id="b5ad4-107">Pour faire varier l'apparence des éléments cartographiques, vous devez spécifier un champ dont les valeurs font correspondre les éléments cartographiques aux données analytiques d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-107">To vary the appearance of map elements, you specify a field that has values that match the map elements with analytical data from a dataset.</span></span> <span data-ttu-id="b5ad4-108">Vous pouvez également définir des règles qui font varier la couleur, la taille ou d'autres propriétés en fonction des plages de données.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-108">You can also define rules that vary color, size, or other properties based on ranges of data.</span></span>  
  
 <span data-ttu-id="b5ad4-109">Dans ce didacticiel, vous allez créer un rapport cartographique qui affiche les emplacements des magasins dans les comtés de l'État de New York.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-109">In this tutorial, you will build a map report that displays store locations in New York state counties.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="b5ad4-110">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="b5ad4-110">What You Will Learn</span></span>  
 <span data-ttu-id="b5ad4-111">Dans ce didacticiel, vous apprendrez à effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="b5ad4-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="b5ad4-112">Créer une carte avec une couche de polygones à partir de l'Assistant Carte</span><span class="sxs-lookup"><span data-stu-id="b5ad4-112">Create a Map with a Polygon Layer from the Map Wizard</span></span>](#Map)  
  
2.  [<span data-ttu-id="b5ad4-113">Ajouter une couche de points pour afficher des emplacements de magasins</span><span class="sxs-lookup"><span data-stu-id="b5ad4-113">Add a Map Point Layer to Display Store Locations</span></span>](#PointLayer)  
  
3.  [<span data-ttu-id="b5ad4-114">Ajouter une couche de lignes pour afficher un itinéraire</span><span class="sxs-lookup"><span data-stu-id="b5ad4-114">Add a Map Line Layer to Display a Route</span></span>](#LineLayer)  
  
4.  [<span data-ttu-id="b5ad4-115">Ajouter un arrière-plan de mosaïques Bing</span><span class="sxs-lookup"><span data-stu-id="b5ad4-115">Add a Bing Maps Tile Background</span></span>](#TileLayer)  
  
5.  [<span data-ttu-id="b5ad4-116">Rendre une couche transparente</span><span class="sxs-lookup"><span data-stu-id="b5ad4-116">Make a Layer Transparent</span></span>](#Transparent)  
  
6.  [<span data-ttu-id="b5ad4-117">Faire varier la couleur du comté selon les ventes</span><span class="sxs-lookup"><span data-stu-id="b5ad4-117">Vary County Color Based on Sales</span></span>](#Vary)  
  
    1.  [<span data-ttu-id="b5ad4-118">Créer une relation entre des données spatiales et des données analytiques</span><span class="sxs-lookup"><span data-stu-id="b5ad4-118">Build a Relationship between Spatial and Analytical Data</span></span>](#Relationship)  
  
    2.  [<span data-ttu-id="b5ad4-119">Spécifier des règles de couleur pour les polygones</span><span class="sxs-lookup"><span data-stu-id="b5ad4-119">Specify Color Rules for Polygons</span></span>](#ColorRules)  
  
    3.  [<span data-ttu-id="b5ad4-120">Mettre en forme les données de l'échelle de couleurs en tant que devises</span><span class="sxs-lookup"><span data-stu-id="b5ad4-120">Format the Data in the Color Scale as Currency</span></span>](#ColorScale)  
  
    4.  [<span data-ttu-id="b5ad4-121">Créer une légende</span><span class="sxs-lookup"><span data-stu-id="b5ad4-121">Create a New Legend</span></span>](#NewLegend)  
  
    5.  [<span data-ttu-id="b5ad4-122">Associer une légende aux règles de couleur</span><span class="sxs-lookup"><span data-stu-id="b5ad4-122">Associate Legend and Color Rules</span></span>](#Associate)  
  
    6.  [<span data-ttu-id="b5ad4-123">Supprimer la couleur des comtés sans données</span><span class="sxs-lookup"><span data-stu-id="b5ad4-123">Clear Color from Counties with No Data</span></span>](#NoData)  
  
7.  [<span data-ttu-id="b5ad4-124">Ajouter un point personnalisé</span><span class="sxs-lookup"><span data-stu-id="b5ad4-124">Add a Custom Point</span></span>](#CustomPoint)  
  
8.  [<span data-ttu-id="b5ad4-125">Centrer la vue cartographique</span><span class="sxs-lookup"><span data-stu-id="b5ad4-125">Center the Map View</span></span>](#CenterView)  
  
9. [<span data-ttu-id="b5ad4-126">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="b5ad4-126">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="b5ad4-127">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="b5ad4-127">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="b5ad4-128">Dans ce didacticiel, les étapes de l'Assistant sont consolidées sous forme de deux procédures : l'une pour créer le dataset, et l'autre pour créer une table.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-128">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="b5ad4-129">Pour obtenir des instructions pas à pas sur l’accès à un serveur de rapports, le choix d’une source de données, la création d’un dataset et l’exécution de l’Assistant, consultez le premier didacticiel de cette série : [Didacticiel : création d’un rapport de tableau de base &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b5ad4-129">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="b5ad4-130">Durée estimée pour effectuer ce didacticiel : 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-130">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5ad4-131">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b5ad4-131">Requirements</span></span>  
 <span data-ttu-id="b5ad4-132">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="b5ad4-132">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-map-with-a-polygon-layer-from-the-map-wizard"></a><a name="Map"></a><span data-ttu-id="b5ad4-133">1. créer une carte avec une couche de polygones à partir de l’Assistant carte</span><span class="sxs-lookup"><span data-stu-id="b5ad4-133">1. Create a Map with a Polygon Layer from the Map Wizard</span></span>  
 <span data-ttu-id="b5ad4-134">Ajoutez une carte à votre rapport à partir de la bibliothèque de cartes.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-134">Add a map to your report from the map gallery.</span></span> <span data-ttu-id="b5ad4-135">La carte a une couche qui affiche les comtés de l'État de New York.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-135">The map has one layer that displays the counties in New York state.</span></span> <span data-ttu-id="b5ad4-136">La forme de chaque comté est un polygone basé sur les données spatiales incorporées dans la carte de la bibliothèque de cartes.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-136">The shape of each county is a polygon based on spatial data that is embedded in the map from the map gallery.</span></span>  
  
#### <a name="to-add-a-map-with-the-map-wizard-in-a-new-report"></a><span data-ttu-id="b5ad4-137">Pour ajouter une carte dans un nouveau rapport à l'aide de l'Assistant Carte</span><span class="sxs-lookup"><span data-stu-id="b5ad4-137">To add a map with the map wizard in a new report</span></span>  
  
1.  <span data-ttu-id="b5ad4-138">Cliquez sur **Démarrer**, pointez sur **programmes**, sur [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Générateur de rapports**, puis cliquez sur **Générateur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-138">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="b5ad4-139">La boîte de dialogue Mise en route s'affiche.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-139">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5ad4-140"> Si la boîte de dialogue Mise en route ne s'affiche pas, à partir du bouton Générateur de rapports, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-140">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="b5ad4-141">Dans le volet gauche, assurez-vous que **Rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-141">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="b5ad4-142">Dans le volet droit, cliquez sur **Assistant Carte**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-142">In the right pane, click **Map Wizard**.</span></span>  
  
4.  <span data-ttu-id="b5ad4-143">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-143">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="b5ad4-144">Dans la page**Choisir une source de données spatiales** , assurez-vous que l'option **Bibliothèque de cartes** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-144">**Choose a source of spatial data** page, verify that **Map gallery** is selected.</span></span>  
  
6.  <span data-ttu-id="b5ad4-145">Dans le volet Bibliothèque de cartes, développez **States by County** sous **USA**, puis cliquez sur **New York**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-145">In the Map Gallery pane, expand **States by County** under **USA**, and click **New York**.</span></span>  
  
     <span data-ttu-id="b5ad4-146">Le volet Aperçu de la carte affiche la carte des comtés de New York.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-146">The Map Preview pane displays the New York county map.</span></span>  
  
7.  <span data-ttu-id="b5ad4-147">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-147">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="b5ad4-148">Dans la page **Choisir des options de vue cartographique et de données spatiales** , acceptez les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-148">On the **Choose spatial data and map view options** page, accept the defaults.</span></span> <span data-ttu-id="b5ad4-149">Par défaut, les éléments cartographiques d'une bibliothèque de cartes sont incorporés automatiquement dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-149">By default, map elements from a map gallery will automatically be embedded in the report definition.</span></span>  
  
9. <span data-ttu-id="b5ad4-150">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-150">Click **Next**.</span></span>  
  
10. <span data-ttu-id="b5ad4-151">Dans la page **Choisir la visualisation de la carte** , vérifiez que l'option **Carte simple** est sélectionnée et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-151">On the **Choose map visualization** page, verify **Basic Map** is selected, and click **Next**.</span></span>  
  
11. <span data-ttu-id="b5ad4-152">Dans la page **Choisir le thème de couleurs et la visualisation des données** , sélectionnez l'option **Afficher les étiquettes** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-152">On the **Choose color theme and data visualization** page, select the **Display labels** option.</span></span>  
  
12. <span data-ttu-id="b5ad4-153">Si elle est activée, désactivez l'option **Carte unicolore** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-153">If it is selected, clear the **Single color map** option.</span></span>  
  
13. <span data-ttu-id="b5ad4-154">Dans la liste déroulante **champ de données** , cliquez sur #COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-154">From the **Data field** drop-down list, click #COUNTYNAME.</span></span> <span data-ttu-id="b5ad4-155">Le volet Aperçu de la carte de l'Assistant affiche les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b5ad4-155">The Map Preview pane in the wizard displays the following items:</span></span>  
  
    -   <span data-ttu-id="b5ad4-156">un titre avec le texte **Titre de la carte**;</span><span class="sxs-lookup"><span data-stu-id="b5ad4-156">A title with the text **Map Title**.</span></span>  
  
    -   <span data-ttu-id="b5ad4-157">une carte qui affiche les comtés de l'État de New York, avec chaque comté dans une couleur différente et les noms des comtés affichés à un endroit quelconque sur la zone du comté ;</span><span class="sxs-lookup"><span data-stu-id="b5ad4-157">A map that displays counties in New York where each county is a different color and the county name appears wherever it fits over the county area.</span></span>  
  
    -   <span data-ttu-id="b5ad4-158">une légende contenant un titre et une liste d'éléments de 1 à 5 ;</span><span class="sxs-lookup"><span data-stu-id="b5ad4-158">A legend that contains a title and a list of items 1 through 5.</span></span>  
  
    -   <span data-ttu-id="b5ad4-159">une échelle de couleurs contenant les valeurs de 0 à 160 et la valeur Aucune couleur ;</span><span class="sxs-lookup"><span data-stu-id="b5ad4-159">A color scale that contains values 0 to 160 and no color.</span></span>  
  
    -   <span data-ttu-id="b5ad4-160">une échelle des distances qui affiche les kilomètres (km) et les miles (mi).</span><span class="sxs-lookup"><span data-stu-id="b5ad4-160">A distance scale that displays kilometers (km) and miles (mi).</span></span>  
  
14. <span data-ttu-id="b5ad4-161">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-161">Click **Finish**.</span></span>  
  
     <span data-ttu-id="b5ad4-162">La carte est ajoutée à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-162">The map is added to the design surface.</span></span>  
  
15. <span data-ttu-id="b5ad4-163">Cliquez sur la carte pour la sélectionner et afficher le volet **Couches**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-163">Click the map to select it and display the **Map Layers Pane**.</span></span> <span data-ttu-id="b5ad4-164">Le volet **Couches** affiche une couche de polygones du type de couche **Incorporé**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-164">The **Map Layers Pane** shows one polygon layer of layer type **Embedded**.</span></span> <span data-ttu-id="b5ad4-165">Chaque comté est un élément cartographique incorporé sur cette couche.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-165">Each county is an embedded map element on this layer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5ad4-166">Si vous ne voyez pas le volet **Couches** , celui-ci se trouve peut-être à l'extérieur de votre vue actuelle.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-166">If you do not see the **Map Layers** pane, it might be displayed outside your current view.</span></span> <span data-ttu-id="b5ad4-167">Utilisez la barre de défilement au bas de la fenêtre du mode Conception pour changer votre vue.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-167">Use the scroll bar at the bottom of the Design view window to change your view.</span></span> <span data-ttu-id="b5ad4-168">Sinon, sous l'onglet **Affichage** , désactivez l'option **Propriétés** ou **Données du rapport** pour disposer d'une plus grande surface d'exposition.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-168">Alternatively, in the **View** tab, clear the **Properties** or the **Report Data** option to provide more design surface area.</span></span>  
  
16. <span data-ttu-id="b5ad4-169">Cliquez avec le bouton droit sur le titre de la carte, puis cliquez sur **Propriétés du titre**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-169">Right-click the map title, and then click **Title Properties**.</span></span>  
  
17. <span data-ttu-id="b5ad4-170">Remplacez le texte du titre par **Ventes par magasin**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-170">Replace the title text with **Sales by Store**.</span></span>  
  
18. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
19. <span data-ttu-id="b5ad4-171">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-171">Preview the report.</span></span>  
  
 <span data-ttu-id="b5ad4-172">Le rapport rendu affiche le titre de la carte, la carte et l'échelle des distances.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-172">The rendered report displays the map title, the map, and the distance scale.</span></span> <span data-ttu-id="b5ad4-173">Les comtés sont sur une couche de polygones de la carte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-173">The counties are on a map polygon layer.</span></span> <span data-ttu-id="b5ad4-174">Chaque comté est un polygone dont la couleur varie à partir d'une palette de couleurs, mais les couleurs ne sont pas associées à des données.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-174">Each county is a polygon that varies by color from a color palette, but the colors are not associated with any data.</span></span> <span data-ttu-id="b5ad4-175">L'échelle des distances affiche les distances en kilomètres et en miles.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-175">The distance scale displays distances in both kilometers and miles.</span></span>  
  
 <span data-ttu-id="b5ad4-176">La légende de la carte et l'échelle de couleurs n'apparaissent pas encore, car il n'y a pas de données analytiques associées à chaque comté.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-176">The map legend and color scale do not yet appear because there is no analytical data associated with each county.</span></span> <span data-ttu-id="b5ad4-177">Vous ajouterez ultérieurement des données analytiques dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-177">You will add analytical data later in this tutorial.</span></span>  
  
##  <a name="2-add-a-map-point-layer-to-display-store-locations"></a><a name="PointLayer"></a><span data-ttu-id="b5ad4-178">2. Ajouter une couche de points de la carte pour afficher les emplacements des magasins</span><span class="sxs-lookup"><span data-stu-id="b5ad4-178">2. Add a Map Point Layer to Display Store Locations</span></span>  
 <span data-ttu-id="b5ad4-179">Utilisez l'Assistant Couche pour ajouter une couche de points qui affiche les emplacements des magasins.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-179">Use the map layer wizard to add a point layer that displays the locations of stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5ad4-180">Dans ce didacticiel, la requête contient les valeurs de données, afin qu'il ne soit pas nécessaire de disposer d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-180">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="b5ad4-181">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-181">This makes the query quite long.</span></span> <span data-ttu-id="b5ad4-182">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-182">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="b5ad4-183">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-183">This is for learning purposes only.</span></span>  
  
#### <a name="to-add-a-point-layer-based-on-a-sql-server-spatial-query"></a><span data-ttu-id="b5ad4-184">Pour ajouter une couche de points basée sur une requête spatiale SQL Server</span><span class="sxs-lookup"><span data-stu-id="b5ad4-184">To add a point layer based on a SQL Server spatial query</span></span>  
  
1.  <span data-ttu-id="b5ad4-185">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-185">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-186">Double-cliquez sur la carte pour afficher le volet **Couches** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-186">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="b5ad4-187">Dans la barre d’outils, cliquez sur le bouton **Assistant Nouvelle couche** ![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span><span class="sxs-lookup"><span data-stu-id="b5ad4-187">On the toolbar, click the **New layer wizard** button ![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span></span>  
  
3.  <span data-ttu-id="b5ad4-188">Dans la page **Choisir une source de données spatiales** , sélectionnez **Requête spatiale SQL Server**et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-188">On the **Choose a source of spatial data** page, select **SQL Server spatial query**, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="b5ad4-189">Dans la page **Choisir un dataset avec des données spatiales SQL Server** , cliquez sur **Ajouter un nouveau dataset avec des données spatiales SQL Server**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-189">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="b5ad4-190">Dans la page **Choisir une connexion à une source de données spatiales SQL Server** , sélectionnez une source de données existante ou naviguez jusqu'au serveur de rapports, puis sélectionnez une source de données.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-190">On the **Choose a connection to a SQL Server spatial data source** page, select an existing data source or browse to the report server and select a data source.</span></span>  
  
6.  <span data-ttu-id="b5ad4-191">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-191">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="b5ad4-192">Sur la page créer une requête, cliquez sur **modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-192">On the Design a Query page, click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="b5ad4-193">Collez le texte ci-après dans le volet Requête :</span><span class="sxs-lookup"><span data-stu-id="b5ad4-193">Paste the following text in the query pane:</span></span>  
  
    ```  
    Select 114 as StoreKey, 'Contoso Albany Store' as StoreName, 1125 as SellingArea, 'Albany' as City, 'Albany' as County,   
     CAST(1000000 as money) as Sales, CAST('POINT(-73.7472924218681 42.6564617079878)' as geography) AS SpatialLocation  
    UNION ALL SELECT 115 AS StoreKey, 'Contoso New York No.1 Store' AS  StoreName, 500 as SellingArea, 'New York' AS City, 'New York City' as County,  
     CAST('2000000' as money) as Sales, CAST('POINT(-73.9922069374483 40.7549638237402)' as geography) AS SpatialLocation  
    UNION ALL Select 116 as StoreKey, 'Contoso Rochester No.1 Store' as StoreName, 462 as SellingArea, 'Rochester' as City,  'Monroe' as County,    
     CAST(3000000 as money) as Sales, CAST('POINT(-77.624041566786 43.1547066024338)' as geography)  AS SpatialLocation  
    UNION ALL Select 117 as StoreKey, 'Contoso New York No.2 Store' as StoreName, 700 as SellingArea, 'New York' as City,'New York City' as County,    
      CAST(4000000 as money) as Sales, CAST('POINT(-73.9712488 40.7830603)' as geography) AS SpatialLocation  
    UNION ALL Select 118 as StoreKey, 'Contoso Syracuse Store' as StoreName, 680 as SellingArea, 'Syracuse' as City, 'Onondaga' as County,  
     CAST(5000000 as money) as Sales, CAST('POINT(-76.1349120532546 43.0610223535974)' as geography) AS SpatialLocation  
    UNION ALL Select 120 as StoreKey, 'Contoso Plattsburgh Store' as StoreName, 560 as SellingArea, 'Plattsburgh' as City,  'Clinton' as County,  
     CAST(6000000 as money) as Sales, CAST('POINT(-73.4728622833178 44.7028831413324)' as geography) AS SpatialLocation  
    UNION ALL Select 121 as StoreKey, 'Contoso Brooklyn Store' as StoreName, 1125 as SellingArea, 'Brooklyn' as City, 'New York City' as County,  
     CAST(7000000 as money) as Sales, CAST('POINT (-73.9638533447143 40.6785123489351)' as geography) AS SpatialLocation  
    UNION ALL Select 122 as StoreKey, 'Contoso Oswego Store' as StoreName, 500 as SellingArea, 'Oswego' as City, 'Oswego' as County,    
     CAST(8000000 as money) as Sales, CAST('POINT(-76.4602850815536 43.4353224527794)' as geography) AS SpatialLocation  
    UNION ALL Select 123 as StoreKey, 'Contoso Ithaca Store' as StoreName, 460 as SellingArea, 'Ithaca' as City, 'Tompkins' as County,  
     CAST(9000000 as money) as Sales, CAST('POINT(-76.5001866085881 42.4310489934743)' as geography) AS SpatialLocation  
    UNION ALL Select 124 as StoreKey, 'Contoso Rochester No.2 Store' as StoreName, 700 as SellingArea, 'Rochester' as City, 'Monroe' as County,    
     CAST(100000 as money) as Sales, CAST('POINT(-77.6240415667866 43.1547066024338)' as geography) AS SpatialLocation  
    UNION ALL Select 125 as StoreKey, 'Contoso Queens Store' as StoreName, 700 as SellingArea,'Queens' as City, 'New York City' as County,  
     CAST(500000 as money) as Sales, CAST('POINT(-73.7930979029883 40.7152781765927)' as geography) AS SpatialLocation  
    UNION ALL Select 126 as StoreKey, 'Contoso Elmira Store' as StoreName, 680 as SellingArea, 'Elmira' as City, 'Chemung' as County,  
     CAST(800000 as money) as Sales, CAST('POINT(-76.7397414783301 42.0736492742663)' as geography) AS SpatialLocation  
    UNION ALL Select 127 as StoreKey, 'Contoso Poestenkill Store' as StoreName, 455 as SellingArea, 'Poestenkill' as City, 'Rensselaer' as County,    
    CAST(1500000 as money) as Sales, CAST('POINT(-73.5626737425063 42.6940551238618)' as geography) AS SpatialLocation  
    ```  
  
9. <span data-ttu-id="b5ad4-194">Dans la barre d’outils du concepteur de requêtes, cliquez sur **exécuter** (**!**).</span><span class="sxs-lookup"><span data-stu-id="b5ad4-194">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="b5ad4-195">Le jeu de résultats affiche sept colonnes : StoreKey, StoreName, SellingArea, City, County, Sales et SpatialLocation.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-195">The result set displays seven columns: StoreKey, StoreName, SellingArea, City, County, Sales, and SpatialLocation.</span></span> <span data-ttu-id="b5ad4-196">Ces données représentent un ensemble de magasins de l'État de New York qui vendent des biens de consommation.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-196">This data represents a set of stores in New York State that sell consumer goods.</span></span> <span data-ttu-id="b5ad4-197">Chaque ligne du jeu de résultats contient un identificateur de magasin, le nom du magasin, la zone disponible pour l'affichage des produits, la ville et le comté dans lesquels il se trouve, le chiffre d'affaires total et l'emplacement spatial en longitude et en latitude.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-197">Each row in the result set contains a store identifier, store name, the area available for product display, the city and county where the store is located, the sales total, and the spatial location in longitude and latitude.</span></span> <span data-ttu-id="b5ad4-198">La surface d'exposition varie entre 455 pieds carrés (environ 42 mètres carrés) et 1 125 pieds carrés (environ 104 mètres carrés).</span><span class="sxs-lookup"><span data-stu-id="b5ad4-198">The display area ranges from 455 square feet to 1125 square feet.</span></span>  
  
10. <span data-ttu-id="b5ad4-199">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-199">Click **Next**.</span></span>  
  
     <span data-ttu-id="b5ad4-200">Le dataset de rapport nommé DataSet1 est créé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-200">The report dataset named DataSet1 is created for you.</span></span> <span data-ttu-id="b5ad4-201">Après avoir terminé l'exécution de l'Assistant, vous pouvez utiliser le volet des données de rapport pour afficher la collection de champs correspondante.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-201">After you complete the wizard, you can use the Report Data to its field collection.</span></span>  
  
11. <span data-ttu-id="b5ad4-202">Dans la page **choisir des options de vue cartographique et de données spatiales** , vérifiez que le **champ spatial** est `SpatialLocation` et que le **type de couche** est **point**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-202">On the **Choose a spatial data and map view options** page, verify that the **Spatial field** is `SpatialLocation` and that the **Layer type** is **Point**.</span></span> <span data-ttu-id="b5ad4-203">Acceptez les autres valeurs par défaut dans cette page.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-203">Accept the other defaults on this page.</span></span>  
  
     <span data-ttu-id="b5ad4-204">La vue cartographique affiche des cercles pour marquer l'emplacement de chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-204">The map view displays circles that mark the location of each store.</span></span>  
  
12. <span data-ttu-id="b5ad4-205">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-205">Click **Next**.</span></span>  
  
13. <span data-ttu-id="b5ad4-206">Spécifiez un type de carte qui affiche des marqueurs variant en fonction des données analytiques.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-206">Specify a map type that displays markers that vary by analytic data.</span></span> <span data-ttu-id="b5ad4-207">Dans la page Choisir la visualisation de la carte, cliquez sur **Carte à marqueurs analytique**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-207">On the Choose map visualization page, click **Analytical Marker Map**, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="b5ad4-208">Dans la page **Choisir le dataset analytique** , cliquez sur DataSet1.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-208">On the **Choose the analytical dataset** page, click DataSet1.</span></span> <span data-ttu-id="b5ad4-209">Ce dataset contient à la fois les données analytiques et les données spatiales à afficher sur la nouvelle couche de points.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-209">This dataset contains both analytical data and spatial data that will be displayed on the new point layer.</span></span>  
  
15. <span data-ttu-id="b5ad4-210">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-210">Click **Next**.</span></span>  
  
16. <span data-ttu-id="b5ad4-211">Dans la page **Choisir le thème de couleurs et la visualisation des données** , désactivez l'option **Utiliser les couleurs de marqueur pour visualiser les données** , puis sélectionnez l'option **Utiliser les types de marqueur pour visualiser les données**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-211">On the **Choose color theme and data visualization** page, clear the **Use marker colors to visualize data** option, and then select the option **Use marker types to visualize data**.</span></span>  
  
17. <span data-ttu-id="b5ad4-212">Dans **Champ de données**, sélectionnez `[Sum(SellingArea)]` pour faire varier les types de marqueurs en fonction de la taille qu'un magasin réserve à l'affichage des produits.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-212">In **Data field**, select `[Sum(SellingArea)]` to vary marker types by the size of the area a store sets aside to display the products.</span></span>  
  
18. <span data-ttu-id="b5ad4-213">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-213">Click **Finish**.</span></span>  
  
     <span data-ttu-id="b5ad4-214">La couche est ajoutée au rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-214">The map layer is added to the report.</span></span> <span data-ttu-id="b5ad4-215">La légende affiche les types de marqueur en fonction des valeurs de SellingArea.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-215">The legend displays marker types based on SellingArea values.</span></span>  
  
     <span data-ttu-id="b5ad4-216">Double-cliquez sur la carte pour afficher le volet **Couches** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-216">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="b5ad4-217">Le volet **Couche** affiche une nouvelle couche, PointLayer1, avec comme type de source de données spatiales **DataRegion**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-217">The **Map Layer** pane displays a new layer, PointLayer1, with spatial data source type **DataRegion**.</span></span>  
  
19. <span data-ttu-id="b5ad4-218">Ajoutez un titre de légende.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-218">Add a legend title.</span></span> <span data-ttu-id="b5ad4-219">Cliquez avec le bouton droit sur le titre de légende, puis cliquez sur **Propriétés du titre de légende**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-219">Right-click the legend title, and then click **Legend Title Properties**.</span></span>  
  
20. <span data-ttu-id="b5ad4-220">Supprimez le titre, puis tapez **Surface d'exposition (en pieds carrés)**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-220">Delete the title, and type **Display Area (Square Feet)**.</span></span>  
  
21. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
22. <span data-ttu-id="b5ad4-221">Consultez les valeurs par défaut définies par l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-221">View the default values that were set by the wizard.</span></span> <span data-ttu-id="b5ad4-222">Dans le volet **Couches**, cliquez avec le bouton droit sur la couche de points, puis cliquez sur **Règle de type de marqueur**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-222">In the **Map Layers Pane**, right-click the point layer, and then click **Marker Type Rule**.</span></span>  
  
     <span data-ttu-id="b5ad4-223">Sous l'onglet **Général** , les marqueurs sont répertoriés dans l'ordre dans lequel ils apparaissent dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-223">On the **General** tab, the markers are listed in the order in which they appear in the legend.</span></span> <span data-ttu-id="b5ad4-224">Sous l'onglet **Distribution** , le nombre de sous-plages est 5.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-224">On the **Distribution** tab, the number of subranges is 5.</span></span> <span data-ttu-id="b5ad4-225">Sous l'onglet **Légende** , le texte de la légende est défini pour afficher la valeur de début et de fin de chaque plage.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-225">On the **Legend** tab, the legend text is set to display the start and end value in each range.</span></span>  
  
23. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
24. <span data-ttu-id="b5ad4-226">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-226">Preview the report.</span></span>  
  
 <span data-ttu-id="b5ad4-227">La carte affiche les emplacements des magasins dans l'État de New York.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-227">The map displays the locations of stores in New York state.</span></span> <span data-ttu-id="b5ad4-228">Le type de marqueur de chaque magasin est basé sur la surface d'exposition.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-228">The marker type for each store is based on the display area.</span></span> <span data-ttu-id="b5ad4-229">Cinq plages de surface d'exposition ont été calculées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-229">Five ranges of display area were automatically calculated for you.</span></span>  
  
##  <a name="3-add-a-map-line-layer-to-display-a-route"></a><a name="LineLayer"></a><span data-ttu-id="b5ad4-230">3. Ajouter une couche de lignes pour afficher un itinéraire</span><span class="sxs-lookup"><span data-stu-id="b5ad4-230">3. Add a Map Line Layer to Display a Route</span></span>  
 <span data-ttu-id="b5ad4-231">Utilisez l'Assistant Couche pour ajouter une couche qui affiche un itinéraire entre deux magasins.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-231">Use the map layer wizard to add a map layer that displays a route between two stores.</span></span> <span data-ttu-id="b5ad4-232">Dans ce didacticiel, l'itinéraire est créé à partir de trois emplacements de magasin.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-232">In this tutorial, the path is created from three store locations.</span></span> <span data-ttu-id="b5ad4-233">Dans une application d'entreprise, l'itinéraire choisi peut être le meilleur itinéraire entre des magasins.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-233">In a business application, the path might be the best route between stores.</span></span>  
  
#### <a name="to-add-a-line-layer-to-map"></a><span data-ttu-id="b5ad4-234">Pour ajouter une couche de lignes à une carte</span><span class="sxs-lookup"><span data-stu-id="b5ad4-234">To add a line layer to map</span></span>  
  
1.  <span data-ttu-id="b5ad4-235">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-235">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-236">Double-cliquez sur la carte pour afficher le volet **Couches** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-236">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="b5ad4-237">Dans la barre d'outils, cliquez sur **Assistant Nouvelle couche**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-237">On the toolbar, click **New layer wizard**.</span></span>  
  
3.  <span data-ttu-id="b5ad4-238">Dans la page **choisir une source de données spatiales** , sélectionnez **SQL Server requête spatiale** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-238">On the **Choose a source of spatial data** page, select **SQL Server spatial query** and click **Next**.</span></span>  
  
4.  <span data-ttu-id="b5ad4-239">Dans la page **Choisir un dataset avec des données spatiales SQL Server** , cliquez sur **Ajouter un nouveau dataset avec des données spatiales SQL Server** , puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-239">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data** and click **Next**.</span></span>  
  
5.  <span data-ttu-id="b5ad4-240">Dans **Choisir une connexion à une source de données spatiales SQL Server**, sélectionnez DataSource1, la source de données que vous avez créée dans la première procédure.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-240">On the **Choose a connection to a SQL Server spatial data source**, select DataSource1, the data source that you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="b5ad4-241">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-241">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="b5ad4-242">Sur la page **créer une requête** , cliquez sur **modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-242">On the **Design a Query** page, click **Edit as Text**.</span></span> <span data-ttu-id="b5ad4-243">Le concepteur de requêtes bascule en mode texte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-243">The query designer switches to text-based mode.</span></span>  
  
8.  <span data-ttu-id="b5ad4-244">Collez le texte ci-après dans le volet Requête :</span><span class="sxs-lookup"><span data-stu-id="b5ad4-244">Paste the following text in the query pane:</span></span>  
  
    ```  
    SELECT N'Path' AS Name, CAST('LINESTRING(  
       -76.5001866085881 42.4310489934743,  
       -76.4602850815536 43.4353224527794,  
       -73.4728622833178 44.7028831413324)' AS geography) as Route  
    ```  
  
9. <span data-ttu-id="b5ad4-245">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-245">Click **Next**.</span></span>  
  
     <span data-ttu-id="b5ad4-246">Un itinéraire qui relie les trois magasins apparaît sur la carte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-246">A path appears on the map that connects three stores.</span></span>  
  
10. <span data-ttu-id="b5ad4-247">Dans la page **Choisir des options de vue cartographique et de données spatiales** , vérifiez que le **Champ spatial** est **Route** et que le **Type de couche** est **Ligne**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-247">On the **Choose spatial data and map view options** page, verify that the **Spatial field** is **Route** and that the **Layer type** is **Line**.</span></span> <span data-ttu-id="b5ad4-248">Acceptez les autres valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-248">Accept the other defaults.</span></span>  
  
     <span data-ttu-id="b5ad4-249">La vue cartographique affiche un itinéraire allant d'un magasin situé dans la partie nord de l'État de New York à un magasin situé dans la partie sud de l'État de New York.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-249">The map view displays a path from a store in the northern part of New York state to a store in the southern part of New York state.</span></span>  
  
11. <span data-ttu-id="b5ad4-250">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-250">Click **Next**.</span></span>  
  
12. <span data-ttu-id="b5ad4-251">Dans la page **Choisir la visualisation de la carte** , cliquez sur l'option **Carte linéaire simple**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-251">On the **Choose map visualization** page, click **Basic Line Map**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="b5ad4-252">Dans la page **Choisir le thème de couleurs et la visualisation des données**, sélectionnez l'option **Carte unicolore**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-252">On the **Choose color theme and data visualization**, select the option **Single color map**.</span></span> <span data-ttu-id="b5ad4-253">L'itinéraire s'affiche dans une couleur unique selon le thème sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-253">The path appears as a single color based on the selected theme.</span></span>  
  
14. <span data-ttu-id="b5ad4-254">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-254">Click **Finish**.</span></span>  
  
 <span data-ttu-id="b5ad4-255">La carte affiche une nouvelle couche de lignes avec **DataSet**comme type de source de données spatiales.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-255">The map displays a new line layer with spatial data source type **DataSet**.</span></span> <span data-ttu-id="b5ad4-256">Dans cet exemple, les données spatiales proviennent d'un dataset mais aucune donnée analytique n'est associée à la ligne.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-256">In this example, the spatial data comes from a dataset but no analytical data is associated with the line.</span></span>  
  
##  <a name="4-add-a-bing-maps-tile-background"></a><a name="TileLayer"></a><span data-ttu-id="b5ad4-257">4. Ajouter un arrière-plan de mosaïques Bing Maps</span><span class="sxs-lookup"><span data-stu-id="b5ad4-257">4. Add a Bing Maps Tile Background</span></span>  
 <span data-ttu-id="b5ad4-258">Ajoutez une couche qui affiche un arrière-plan de mosaïques Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-258">Add a map layer that displays a Bing Maps tile background.</span></span>  
  
#### <a name="to-add-a-virtual-earth-tile-background"></a><span data-ttu-id="b5ad4-259">Pour ajouter un arrière-plan de mosaïques Virtual Earth</span><span class="sxs-lookup"><span data-stu-id="b5ad4-259">To add a Virtual Earth tile background</span></span>  
  
1.  <span data-ttu-id="b5ad4-260">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-260">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-261">Double-cliquez sur la carte pour afficher le volet **Couches** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-261">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="b5ad4-262">Dans la barre d’outils, cliquez sur **Ajouter une couche**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span><span class="sxs-lookup"><span data-stu-id="b5ad4-262">On the toolbar, click **Add Layer**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span></span>  
  
3.  <span data-ttu-id="b5ad4-263">Dans la liste déroulante, cliquez sur **Couche de mosaïques**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-263">From the drop-down list, click **Tile Layer**.</span></span>  
  
     <span data-ttu-id="b5ad4-264">La dernière couche du volet **Couche** est TileLayer1.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-264">The last layer in the **Map Layer** pane is TileLayer1.</span></span> <span data-ttu-id="b5ad4-265">Par défaut, la couche de mosaïques affiche le style de carte routière.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-265">By default, the tile layer displays the road map style.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5ad4-266">Dans l'Assistant, vous pouvez également ajouter une couche de mosaïques dans la page **Choisir des options de vue cartographique et de données spatiales** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-266">In the wizard, you can also add a tile layer on the **Choose spatial data and map view options** page.</span></span> <span data-ttu-id="b5ad4-267">Pour ce faire, sélectionnez **Ajouter un arrière-plan Bing Maps pour cette vue cartographique**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-267">To do this, select **Add a Bing Maps background for this map view**.</span></span> <span data-ttu-id="b5ad4-268">Dans un rapport rendu, l'arrière-plan de mosaïques affiche des mosaïques Bing Maps pour le centre et le niveau de zoom du point de vue de la carte actuels.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-268">In a rendered report, the tile background displays Bing Maps tiles for the current map viewport center and zoom level.</span></span>  
  
4.  <span data-ttu-id="b5ad4-269">Cliquez sur la flèche bas sur TileLayer1, puis sur **Propriétés des mosaïques**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-269">Click the down arrow on TileLayer1, and then click **Tile Properties**.</span></span>  
  
5.  <span data-ttu-id="b5ad4-270">Dans la zone **Type**, sélectionnez **Aérien**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-270">In **Type**, select **Aerial**.</span></span> <span data-ttu-id="b5ad4-271">La vue aérienne ne contient pas de texte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-271">The aerial view does not contain text.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="5-make-a-layer-transparent"></a><a name="Transparent"></a><span data-ttu-id="b5ad4-272">5. rendre une couche transparente</span><span class="sxs-lookup"><span data-stu-id="b5ad4-272">5. Make a Layer Transparent</span></span>  
 <span data-ttu-id="b5ad4-273">Pour permettre aux éléments d'une couche de laisser transparaître une autre couche, vous pouvez ajuster l'ordre des couches et la transparence de chaque couche afin d'obtenir l'effet souhaité.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-273">To let the items on one layer show through another layer, you can adjust the order of layers and the transparency of each layer to get the effect that you want.</span></span>  
  
#### <a name="to-set-the-transparency-of-a-layer"></a><span data-ttu-id="b5ad4-274">Pour définir la transparence d'une couche</span><span class="sxs-lookup"><span data-stu-id="b5ad4-274">To set the transparency of a layer</span></span>  
  
1.  <span data-ttu-id="b5ad4-275">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-275">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-276">Double-cliquez sur la carte pour afficher le volet **Couches** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-276">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="b5ad4-277">Cliquez sur la flèche bas sur PolygonLayer1, puis sur **Données de la couche**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-277">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="b5ad4-278">La boîte de dialogue **Propriétés des couches de polygones de la carte** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-278">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="b5ad4-279">Cliquez sur **Visibilité**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-279">Click **Visibility**.</span></span>  
  
5.  <span data-ttu-id="b5ad4-280">Dans l'option **Transparence (%)**, tapez **30**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-280">In **Transparency (%)**, type **30**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="b5ad4-281">L'aire de conception affiche les comtés en couleurs translucides.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-281">The design surface displays the counties as semi-transparent.</span></span>  
  
##  <a name="6-vary-county-color-based-on-sales"></a><a name="Vary"></a><span data-ttu-id="b5ad4-282">6. faire varier la couleur du comté en fonction des ventes</span><span class="sxs-lookup"><span data-stu-id="b5ad4-282">6. Vary County Color Based on Sales</span></span>  
 <span data-ttu-id="b5ad4-283">Chaque comté de la couche de polygones a une couleur différente car le processeur de rapports attribue automatiquement une valeur de couleur de la palette de couleurs selon le thème que vous avez choisi dans la dernière page de l'Assistant Carte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-283">Each county on the polygon layer has a different color because the report processor automatically assigns a color value from the color palette based on the theme that you chose on the last page of the map wizard.</span></span>  
  
 <span data-ttu-id="b5ad4-284">Dans les étapes suivantes, spécifiez une règle de couleur pour associer des couleurs spécifiques à une plage de ventes des magasins pour chaque comté.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-284">In the following steps, specify a color rule to associate specific colors with a range of store sales for each county.</span></span> <span data-ttu-id="b5ad4-285">Les couleurs rouge-jaune-vert indiquent des chiffres d'affaires relatifs élevés-moyens-bas.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-285">The colors red-yellow-green indicate relative high-middle-low sales.</span></span> <span data-ttu-id="b5ad4-286">Mettez en forme l'échelle de couleurs pour afficher la devise.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-286">Format the color scale to show currency.</span></span> <span data-ttu-id="b5ad4-287">Affichez les plages de chiffres d'affaires annuels dans une nouvelle légende.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-287">Display the annual sales ranges in a new legend.</span></span> <span data-ttu-id="b5ad4-288">Pour les comtés qui ne contiennent pas de magasins, utilisez la valeur Aucune couleur pour indiquer qu'il n'existe pas de données associées.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-288">For counties that do not contain stores, use no color to show that there is no associated data.</span></span>  
  
###  <a name="6a-build-a-relationship-between-spatial-and-analytical-data"></a><a name="Relationship"></a><span data-ttu-id="b5ad4-289">6A.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-289">6a.</span></span> <span data-ttu-id="b5ad4-290">Créer une relation entre des données spatiales et des données analytiques</span><span class="sxs-lookup"><span data-stu-id="b5ad4-290">Build a Relationship between Spatial and Analytical Data</span></span>  
 <span data-ttu-id="b5ad4-291">Pour faire varier les formes de comté par couleur en fonction des données analytiques, vous devez tout d'abord associer des données analytiques aux données spatiales.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-291">To vary the county shapes by color based on analytical data, you first must associate the analytical data with the spatial data.</span></span> <span data-ttu-id="b5ad4-292">Dans ce didacticiel, vous utiliserez une correspondance basée sur le nom du comté.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-292">In this tutorial, you will use the county name to match on.</span></span>  
  
##### <a name="to-build-a-relationship-between-spatial-data-and-analytical-data"></a><span data-ttu-id="b5ad4-293">Pour générer une relation entre des données spatiales et des données analytiques</span><span class="sxs-lookup"><span data-stu-id="b5ad4-293">To build a relationship between spatial data and analytical data</span></span>  
  
1.  <span data-ttu-id="b5ad4-294">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-294">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-295">Double-cliquez sur la carte pour afficher le volet **Couches** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-295">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="b5ad4-296">Cliquez sur la flèche bas sur PolygonLayer1, puis sur **Données de la couche**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-296">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="b5ad4-297">La boîte de dialogue **Propriétés des couches de polygones de la carte** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-297">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="b5ad4-298">Cliquez sur **Données analytiques**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-298">Click **Analytical data**.</span></span>  
  
5.  <span data-ttu-id="b5ad4-299">Dans la zone de liste déroulante, sélectionnez DataSet1.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-299">From the drop-down list, select DataSet1.</span></span> <span data-ttu-id="b5ad4-300">Ce dataset a été créé par l'Assistant lorsque vous avez spécifié la requête de données spatiales pour les comtés.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-300">This dataset was created by the wizard when you specified the spatial data query for the counties.</span></span>  
  
6.  <span data-ttu-id="b5ad4-301">Dans **Champs à mettre en correspondance**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-301">In **Fields to match on**, click **Add**.</span></span> <span data-ttu-id="b5ad4-302">Une nouvelle ligne est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-302">A new row is added.</span></span>  
  
7.  <span data-ttu-id="b5ad4-303">Dans **Depuis un dataset spatial**, dans la liste déroulante, cliquez sur COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-303">In **From spatial dataset**, from the drop-down list, click COUNTYNAME.</span></span>  
  
8.  <span data-ttu-id="b5ad4-304">Dans **Depuis un dataset analytique**, dans la liste déroulante, cliquez sur [County].</span><span class="sxs-lookup"><span data-stu-id="b5ad4-304">In **From analytical dataset**, from the drop-down list, click [County].</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="b5ad4-305">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-305">Preview the report.</span></span>  
  
 <span data-ttu-id="b5ad4-306">En spécifiant un champ de correspondance de la source de données spatiales et du dataset analytique, vous permettez au processeur de regrouper les données analytiques en fonction des éléments cartographiques.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-306">By specifying a match field from the spatial data source and from the analytical dataset, you enable the report processor to group analytical data based on the map elements.</span></span> <span data-ttu-id="b5ad4-307">Un élément cartographique lié aux données a une correspondance valide pour les valeurs que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-307">A data-bound map element has a successful match for the values that you specified.</span></span>  
  
 <span data-ttu-id="b5ad4-308">Chaque comté qui contient un magasin a une couleur basée sur la palette de couleurs du style que vous avez choisi dans l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-308">Each county that contains a store has a color that is based on the color palette for the style that you chose in the wizard.</span></span>  
  
###  <a name="6b-specify-color-rules-for-polygons"></a><a name="ColorRules"></a><span data-ttu-id="b5ad4-309">6B.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-309">6b.</span></span> <span data-ttu-id="b5ad4-310">Spécifier des règles de couleur pour les polygones</span><span class="sxs-lookup"><span data-stu-id="b5ad4-310">Specify Color Rules for Polygons</span></span>  
 <span data-ttu-id="b5ad4-311">Pour créer une règle qui fait varier la couleur de chaque comté en fonction des ventes des magasins, vous devez spécifier les valeurs de plage, le nombre de divisions dans la plage que vous souhaitez afficher, ainsi que les couleurs à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-311">To create a rule that varies the color of each county based store sales, you must specify the range values, the number of divisions within that range that you want to display, and the colors to use.</span></span>  
  
##### <a name="to-specify-color-rules-for-all-polygons-that-have-associated-data"></a><span data-ttu-id="b5ad4-312">Pour spécifier des règles de couleur pour tous les polygones ayant des données associées</span><span class="sxs-lookup"><span data-stu-id="b5ad4-312">To specify color rules for all polygons that have associated data</span></span>  
  
1.  <span data-ttu-id="b5ad4-313">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-313">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-314">Cliquez sur la flèche bas sur PolygonLayer1, puis sur **Règle de couleur de polygone**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-314">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="b5ad4-315">La boîte de dialogue **Propriétés des règles de couleur de la carte** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-315">The **Map Color Rules Properties** dialog box opens.</span></span> <span data-ttu-id="b5ad4-316">Remarquez que l'option de la règle de couleur **Visualiser les données à l'aide de la palette de couleurs** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-316">Notice that the color rule option **Visualize data by using color palette** is selected.</span></span> <span data-ttu-id="b5ad4-317">Cette option a été définie par l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-317">This option was set by the wizard.</span></span>  
  
3.  <span data-ttu-id="b5ad4-318">Sélectionnez **Visualiser les données à l'aide de plages de couleurs**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-318">Select **Visualize data by using color ranges**.</span></span> <span data-ttu-id="b5ad4-319">L'option de palette est remplacée par les options de couleur de début, intermédiaire et de fin.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-319">The palette option is replaced by start color, middle color, and end color options.</span></span>  
  
4.  <span data-ttu-id="b5ad4-320">Définissez des valeurs de plage pour le chiffre d'affaires par comté.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-320">Define range values for sales per county.</span></span> <span data-ttu-id="b5ad4-321">Dans **Champ de données**, dans la liste déroulante, sélectionnez `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-321">In **Data field**, from the drop-down list, select `[Sum(Sales)]`.</span></span>  
  
5.  <span data-ttu-id="b5ad4-322">Pour modifier le format afin d'afficher la devise en milliers, remplacez l'expression par ce qui suit : `=Sum(Fields!Sales.Value)/1000`</span><span class="sxs-lookup"><span data-stu-id="b5ad4-322">To change the format to display currency in thousands, change the expression to the following: `=Sum(Fields!Sales.Value)/1000`</span></span>  
  
6.  <span data-ttu-id="b5ad4-323">Modifiez **Couleur de début** en choisissant la valeur **Rouge**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-323">Change **Start color** to **Red**.</span></span>  
  
7.  <span data-ttu-id="b5ad4-324">Modifiez **Couleur de fin** en choisissant la valeur **Vert**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-324">Change **End color** to **Green**.</span></span>  
  
     <span data-ttu-id="b5ad4-325">**Rouge** représente les chiffres de ventes bas, **Jaune** les chiffres de ventes moyens et **Vert** les chiffres de ventes élevés.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-325">**Red** represents low sales values, **Yellow** represents middle sales values, and **Green** represents high sales values.</span></span> <span data-ttu-id="b5ad4-326">Le processeur de rapports calcule une plage de couleurs en fonction de ces valeurs et des options sélectionnées dans la page **Distribution** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-326">The report processor calculates a range of colors based on these values and the options that you choose on the **Distribution** page.</span></span>  
  
8.  <span data-ttu-id="b5ad4-327">Cliquez sur **Distribution**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-327">Click **Distribution**.</span></span>  
  
9. <span data-ttu-id="b5ad4-328">Vérifiez que le type de distribution est **Optimal**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-328">Verify that the distribution type is **Optimal**.</span></span> <span data-ttu-id="b5ad4-329">Pour l'expression de l'étape 5, la distribution optimale divise les valeurs en sous-plages présentant un équilibre entre le nombre d'éléments dans chaque plage et l'étendue de chaque plage.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-329">For the expression from step 5, optimal distribution divides the values into subranges that balance the number of items in each range and the span for each range.</span></span>  
  
10. <span data-ttu-id="b5ad4-330">Acceptez les valeurs par défaut pour les autres options de cette page.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-330">Accept the default values for other options on this page.</span></span> <span data-ttu-id="b5ad4-331">Lorsque vous sélectionnez le type de distribution optimal, le nombre de sous-plages est calculé lors de l'exécution du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-331">When you select the optimal distribution type, the number of subranges are calculated when the report runs.</span></span>  
  
11. <span data-ttu-id="b5ad4-332">Cliquez sur **Légende**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-332">Click **Legend**.</span></span>  
  
12. <span data-ttu-id="b5ad4-333">Dans **Options d'échelle de couleurs**, vérifiez que l'option **Afficher dans l'échelle de couleurs** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-333">In **Color scale options**, verify that **Show in color scale** is selected.</span></span>  
  
13. <span data-ttu-id="b5ad4-334">Dans **Afficher dans cette légende**, dans la liste déroulante, sélectionnez la ligne vierge.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-334">In **Show in this legend**, from the drop-down list, select the blank line.</span></span> <span data-ttu-id="b5ad4-335">Pour le moment, vous afficherez uniquement les plages de couleurs dans l'échelle de couleurs.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-335">For now, you will show the color ranges only in the color scale.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="b5ad4-336">L'échelle de couleurs affiche cinq couleurs : rouge, orange, jaune, jaune vert et vert.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-336">The color scale displays five colors: red, orange, yellow, yellow green, and green.</span></span> <span data-ttu-id="b5ad4-337">Chaque couleur représente une plage de ventes calculée automatiquement selon les ventes par comté.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-337">Each color represents a sales range that is automatically calculated based on the sales by county.</span></span>  
  
###  <a name="6c-format-the-data-in-the-color-scale-as-currency"></a><a name="ColorScale"></a><span data-ttu-id="b5ad4-338">6C.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-338">6c.</span></span> <span data-ttu-id="b5ad4-339">Mettre en forme les données de l'échelle de couleurs en tant que devises</span><span class="sxs-lookup"><span data-stu-id="b5ad4-339">Format the Data in the Color Scale as Currency</span></span>  
 <span data-ttu-id="b5ad4-340">Par défaut, les données ont un format général.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-340">By default, data has a general format.</span></span> <span data-ttu-id="b5ad4-341">Vous pouvez appliquer des formats personnalisés.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-341">You can apply custom formats.</span></span>  
  
##### <a name="to-set-the-format-for-the-color-scale"></a><span data-ttu-id="b5ad4-342">Pour définir la mise en forme de l'échelle de couleurs</span><span class="sxs-lookup"><span data-stu-id="b5ad4-342">To set the format for the color scale</span></span>  
  
1.  <span data-ttu-id="b5ad4-343">Cliquez avec le bouton droit sur l'échelle de couleurs, puis cliquez sur **Propriétés de l'échelle de couleurs**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-343">Right-click the color scale, and then click **Color Scale Properties**.</span></span>  
  
2.  <span data-ttu-id="b5ad4-344">Cliquez sur **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-344">Click **Number**.</span></span>  
  
3.  <span data-ttu-id="b5ad4-345">Dans **Catégorie**, cliquez sur **Devise**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-345">In **Category**, click **Currency**.</span></span>  
  
4.  <span data-ttu-id="b5ad4-346">Dans **Nombre de décimales**, tapez **0**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-346">In **Decimal places**, type **0**.</span></span> <span data-ttu-id="b5ad4-347">Cette mise en forme ne spécifie pas de décimales pour les valeurs monétaires.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-347">This format specifies no decimal places for currency.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="b5ad4-348">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-348">Preview the report.</span></span>  
  
 <span data-ttu-id="b5ad4-349">L'échelle de couleurs affiche les chiffres d'affaires annuels au format monétaire pour chaque plage.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-349">The color scale displays annual sales in currency format for each range.</span></span>  
  
###  <a name="6d-create-a-new-legend"></a><a name="NewLegend"></a><span data-ttu-id="b5ad4-350">6D.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-350">6d.</span></span> <span data-ttu-id="b5ad4-351">Créer une légende</span><span class="sxs-lookup"><span data-stu-id="b5ad4-351">Create a New Legend</span></span>  
 <span data-ttu-id="b5ad4-352">Par défaut, toutes les règles s'affichent dans la première légende.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-352">By default, all rules display in the first legend.</span></span> <span data-ttu-id="b5ad4-353">Pour améliorer l'affichage d'une carte, vous pouvez ajouter des légendes.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-353">To improve the display for a map, you can add legends.</span></span>  
  
 <span data-ttu-id="b5ad4-354">Pour modifier l'affichage par défaut, il y a deux étapes : créez une légende, puis associez les résultats des règles d'une couche à la nouvelle légende.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-354">To change the default display, there are two steps: create a new legend and then associate the rule results for a map layer with the new legend.</span></span>  
  
##### <a name="to-create-a-new-legend"></a><span data-ttu-id="b5ad4-355">Pour créer une légende</span><span class="sxs-lookup"><span data-stu-id="b5ad4-355">To create a new legend</span></span>  
  
1.  <span data-ttu-id="b5ad4-356">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-356">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-357">Cliquez avec le bouton droit sur la carte à l'extérieur de la fenêtre d'affichage, puis cliquez sur **Ajouter une légende**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-357">Right-click the map outside the viewport, and then click **Add Legend**.</span></span> <span data-ttu-id="b5ad4-358">Une nouvelle légende est ajoutée à la carte à un emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-358">A new legend is added to the map at a default location.</span></span>  
  
3.  <span data-ttu-id="b5ad4-359">Cliquez avec le bouton droit sur la légende, puis cliquez sur **Propriétés de la légende**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-359">Right-click the legend, and then click **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="b5ad4-360">Dans **Options de position**, cliquez sur l'emplacement qui spécifie où vous souhaitez afficher la légende par rapport à la fenêtre d'affichage.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-360">In **Position options**, click the location that specifies where you want the legend to appear relative to the viewport.</span></span> <span data-ttu-id="b5ad4-361">La carte sur l'aire de conception est mise à jour pour afficher vos sélections.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-361">The map on the design surface changes to show the effect of your selections.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="b5ad4-362">Cliquez sur **Titre** sur la légende pour sélectionner le titre de légende.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-362">Click **Title** on the legend to select the legend title.</span></span>  
  
7.  <span data-ttu-id="b5ad4-363">Cliquez encore sur **Titre** pour passer en mode d'insertion pour le texte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-363">Click **Title** again to enter insert mode for the text.</span></span> <span data-ttu-id="b5ad4-364">Remplacez **Titre** par **Ventes (en milliers)**, puis cliquez à l'extérieur du texte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-364">Replace **Title** by **Sales (Thousands)**, and then click outside the text.</span></span>  
  
 <span data-ttu-id="b5ad4-365">La légende est développée pour afficher le titre.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-365">The legend expands to display the title.</span></span>  
  
###  <a name="6e-associate-legend-and-color-rules"></a><a name="Associate"></a><span data-ttu-id="b5ad4-366">6e.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-366">6e.</span></span> <span data-ttu-id="b5ad4-367">Associer une légende aux règles de couleur</span><span class="sxs-lookup"><span data-stu-id="b5ad4-367">Associate Legend and Color Rules</span></span>  
 <span data-ttu-id="b5ad4-368">Chaque légende peut afficher un ou plusieurs jeux de résultats des règles.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-368">Each legend can display one or more sets of rule results.</span></span>  
  
##### <a name="to-associate-a-legend-with-color-rules"></a><span data-ttu-id="b5ad4-369">Pour associer une légende à des règles de couleur</span><span class="sxs-lookup"><span data-stu-id="b5ad4-369">To associate a legend with color rules</span></span>  
  
1.  <span data-ttu-id="b5ad4-370">Double-cliquez sur la carte pour afficher le volet **Couches** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-370">Double-click the map to display the **Map Layer** pane.</span></span>  
  
2.  <span data-ttu-id="b5ad4-371">Cliquez sur la flèche bas sur PolygonLayer1, puis sur **Règle de couleur de polygone**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-371">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="b5ad4-372">La boîte de dialogue **Propriétés des règles de couleur de la carte** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-372">The **Map Color Rules Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b5ad4-373">Cliquez sur **Légende**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-373">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="b5ad4-374">Dans **Options d'échelle de couleurs**, désactivez **Afficher dans l'échelle de couleurs**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-374">In **Color scale options**, clear **Show in color scale**.</span></span>  
  
5.  <span data-ttu-id="b5ad4-375">Dans **Options de légende**, sélectionnez Legend2 dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-375">In **Legend options**, from the drop-down list, select Legend2.</span></span> <span data-ttu-id="b5ad4-376">L'option de texte de légende s'affiche.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-376">The legend text option appears.</span></span> <span data-ttu-id="b5ad4-377">Par défaut, le texte de la légende est mis en forme avec une chaîne de format [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] générale.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-377">By default, legend text is formatted with a general [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] format string.</span></span> <span data-ttu-id="b5ad4-378">Le 0 dans N0 indique l'absence de chiffres décimaux.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-378">The 0 in N0 specifies no decimal digits.</span></span>  
  
6.  <span data-ttu-id="b5ad4-379">Dans **texte de légende**, utilisez le format suivant pour spécifier une devise sans chiffres décimaux :`#FROMVALUE {C0} - #TOVALUE {C0}`</span><span class="sxs-lookup"><span data-stu-id="b5ad4-379">In **Legend text**, use the following format to specify currency with no decimal digits: `#FROMVALUE {C0} - #TOVALUE {C0}`</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="b5ad4-380">Dans l'aire de conception, la légende affiche les plages de couleurs avec des exemples de données mises en forme en tant que devises.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-380">On the design surface, the legend displays the color ranges with sample data formatted as currency.</span></span>  
  
8.  <span data-ttu-id="b5ad4-381">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-381">Preview the report.</span></span>  
  
 <span data-ttu-id="b5ad4-382">Les comtés qui ont des magasins et des ventes associés s'affichent en fonction des règles de couleur.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-382">The counties that have associated stores and sales display according to the color rules.</span></span> <span data-ttu-id="b5ad4-383">Les comtés qui n'ont pas de ventes n'ont aucune couleur.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-383">Counties that have no sales have no color.</span></span>  
  
###  <a name="6f-change-color-for-counties-with-no-data"></a><a name="NoData"></a><span data-ttu-id="b5ad4-384">6f.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-384">6f.</span></span> <span data-ttu-id="b5ad4-385">Modifier la couleur des comtés sans données</span><span class="sxs-lookup"><span data-stu-id="b5ad4-385">Change Color for Counties with No Data</span></span>  
 <span data-ttu-id="b5ad4-386">Vous pouvez définir les options d'affichage par défaut pour tous les éléments cartographiques d'une couche.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-386">You can set the default display options for all map elements on a layer.</span></span> <span data-ttu-id="b5ad4-387">Les règles de couleur ont priorité sur ces options d'affichage.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-387">Color rules take precedence over these display options.</span></span>  
  
##### <a name="to-set-the-display-properties-for-all-elements-on-a-layer"></a><span data-ttu-id="b5ad4-388">Pour définir les propriétés d'affichage de tous les éléments d'une couche</span><span class="sxs-lookup"><span data-stu-id="b5ad4-388">To set the display properties for all elements on a layer</span></span>  
  
1.  <span data-ttu-id="b5ad4-389">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-389">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-390">Double-cliquez sur la carte pour afficher le volet **Couches** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-390">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="b5ad4-391">Cliquez sur la flèche bas sur PolygonLayer1, puis sur **Propriétés des polygones**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-391">Click the down arrow on PolygonLayer1, and then click **Polygon Properties**.</span></span> <span data-ttu-id="b5ad4-392">La boîte de dialogue **Propriétés des polygones de la carte** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-392">The **Map Polygon Properties** dialog box opens.</span></span> <span data-ttu-id="b5ad4-393">Les options d'affichage définies dans cette boîte de dialogue s'appliquent à tous les polygones de la couche avant les options d'affichage basées sur les règles.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-393">Display options set in this dialog box apply to all polygons on the layer before rule-based display options are applied.</span></span>  
  
4.  <span data-ttu-id="b5ad4-394">Cliquez sur **Remplir**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-394">Click **Fill**.</span></span>  
  
5.  <span data-ttu-id="b5ad4-395">Vérifiez que le style de remplissage est **Plein.**</span><span class="sxs-lookup"><span data-stu-id="b5ad4-395">Verify that the fill style is **Solid.**</span></span> <span data-ttu-id="b5ad4-396">Les dégradés et les motifs s'appliquent à toutes les couleurs.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-396">Gradients and patterns apply to all colors.</span></span>  
  
6.  <span data-ttu-id="b5ad4-397">Dans **Couleur**, cliquez sur la flèche bas, puis sur **Bleu acier clair**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-397">In **Color**, click the down arrow, and then click **Light Steel Blue**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="b5ad4-398">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-398">Preview the report.</span></span>  
  
 <span data-ttu-id="b5ad4-399">Les comtés sans données associées s'affichent en bleu.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-399">Counties that have no associated data display as blue.</span></span> <span data-ttu-id="b5ad4-400">Seuls les comtés qui ont des données analytiques associées s'affichent dans les couleurs allant du **Rouge** au **Vert** en fonction des règles de couleur que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-400">Only counties that have associated analytical data appear in the **Red** through **Green** colors from the color rules that you specified.</span></span>  
  
##  <a name="7-add-a-custom-point"></a><a name="CustomPoint"></a><span data-ttu-id="b5ad4-401">7. Ajouter un point personnalisé</span><span class="sxs-lookup"><span data-stu-id="b5ad4-401">7. Add a Custom Point</span></span>  
 <span data-ttu-id="b5ad4-402">Pour représenter un nouveau magasin qui n'a pas encore été construit, spécifiez un point et utilisez le type de marqueur **Punaise** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-402">To represent a new store that has not yet been built, specify a point and use the **PushPin** marker type.</span></span>  
  
#### <a name="to-add-a-custom-point"></a><span data-ttu-id="b5ad4-403">Pour ajouter un point personnalisé</span><span class="sxs-lookup"><span data-stu-id="b5ad4-403">To add a custom point</span></span>  
  
1.  <span data-ttu-id="b5ad4-404">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-404">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-405">Double-cliquez sur la carte pour afficher le volet **Couches** .</span><span class="sxs-lookup"><span data-stu-id="b5ad4-405">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="b5ad4-406">Dans la barre d'outils, cliquez sur **Ajouter une couche**, puis sur **Couche de points**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-406">On the toolbar, click **Add Layer**, and then click **Point Layer**.</span></span>  
  
     <span data-ttu-id="b5ad4-407">Une nouvelle couche de points est ajoutée à la carte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-407">A new point layer is added to the map.</span></span> <span data-ttu-id="b5ad4-408">Par défaut, le type de données spatiales de la couche de points est **Incorporé**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-408">By default, the point layer has spatial data type **Embedded**.</span></span>  
  
3.  <span data-ttu-id="b5ad4-409">Cliquez sur la flèche bas sur PointLayer2, puis sur **Ajouter un point**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-409">Click the down arrow on PointLayer2, and then click **Add Point**.</span></span>  
  
4.  <span data-ttu-id="b5ad4-410">Déplacez le pointeur sur le point de vue de la carte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-410">Move the pointer over the map viewport.</span></span> <span data-ttu-id="b5ad4-411">Le curseur se transforme en croix.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-411">The cursor changes to crosshairs.</span></span>  
  
5.  <span data-ttu-id="b5ad4-412">Cliquez sur l'emplacement de la carte où vous souhaitez ajouter un point.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-412">Click the location on the map where you want to add a point.</span></span> <span data-ttu-id="b5ad4-413">Dans ce didacticiel, cliquez sur un emplacement d'un comté, près du début de l'itinéraire.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-413">In this tutorial, click a location in a county next to the start of the route.</span></span> <span data-ttu-id="b5ad4-414">Un point marqué par un cercle est ajouté à la couche à l'emplacement où vous avez cliqué.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-414">A point marked by a circle is added to the layer at the location where you clicked.</span></span> <span data-ttu-id="b5ad4-415">Par défaut, le point est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-415">By default, the point is selected.</span></span>  
  
6.  <span data-ttu-id="b5ad4-416">Cliquez avec le bouton droit sur le point que vous avez ajouté, puis cliquez sur **Propriétés des points incorporés**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-416">Right-click the point you added, and then click **Embedded Point Properties**.</span></span>  
  
7.  <span data-ttu-id="b5ad4-417">Sélectionnez l'option **Remplacer les options de point pour cette couche**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-417">Select the option **Override point options for this layer**.</span></span> <span data-ttu-id="b5ad4-418">Des pages supplémentaires s'affichent dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-418">Additional pages appear in the dialog box.</span></span> <span data-ttu-id="b5ad4-419">Les valeurs que vous définissez ici ont priorité sur les options d'affichage de la couche et sur les règles de couleur.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-419">Values that you set here take precedence over display options for the layer or for color rules.</span></span>  
  
8.  <span data-ttu-id="b5ad4-420">Cliquez sur **Marqueur**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-420">Click **Marker**.</span></span>  
  
9. <span data-ttu-id="b5ad4-421">Pour **Type de marqueur**, sélectionnez **Étoile**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-421">For **Marker type**, select **Star**.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="b5ad4-422">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-422">Preview the report.</span></span>  
  
 <span data-ttu-id="b5ad4-423">Le nouveau point que vous avez ajouté est affiché sous forme d' **Étoile**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-423">The new point you added appears as a **Star**.</span></span>  
  
#### <a name="to-add-a-label-for-the-custom-point"></a><span data-ttu-id="b5ad4-424">Pour ajouter une étiquette au point personnalisé</span><span class="sxs-lookup"><span data-stu-id="b5ad4-424">To add a label for the custom point</span></span>  
  
1.  <span data-ttu-id="b5ad4-425">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-425">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-426">Cliquez avec le bouton droit sur le point que vous venez d'ajouter, puis cliquez sur **Propriétés du point incorporé**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-426">Right-click the point you just added, and then click **Embedded Point Properties**.</span></span>  
  
3.  <span data-ttu-id="b5ad4-427">Cliquez sur **Étiquettes**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-427">Click **Labels**.</span></span>  
  
4.  <span data-ttu-id="b5ad4-428">Dans **Texte d'étiquette**, tapez **Nouveau magasin**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-428">In **Label text**, type **New Store**.</span></span>  
  
5.  <span data-ttu-id="b5ad4-429">Dans **Emplacement**, cliquez sur **Haut**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-429">In **Placement**, click **Top**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="b5ad4-430">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-430">Preview the report.</span></span>  
  
 <span data-ttu-id="b5ad4-431">L'étiquette s'affiche au-dessus de l'emplacement du magasin.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-431">The label appears above the store location.</span></span>  
  
##  <a name="center-the-map-view"></a><a name="CenterView"></a><span data-ttu-id="b5ad4-432">Centrer la vue cartographique</span><span class="sxs-lookup"><span data-stu-id="b5ad4-432">Center the Map View</span></span>  
 <span data-ttu-id="b5ad4-433">Modifiez le centre et le niveau de zoom du point de vue de la carte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-433">Change the map viewport center and zoom level.</span></span>  
  
#### <a name="to-change-the-viewport"></a><span data-ttu-id="b5ad4-434">Pour modifier la fenêtre de carte</span><span class="sxs-lookup"><span data-stu-id="b5ad4-434">To change the viewport</span></span>  
  
1.  <span data-ttu-id="b5ad4-435">Cliquez avec le bouton droit sur le point de vue de la carte, puis cliquez sur **Propriétés de la fenêtre de carte**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-435">Right-click the map viewport, and then click **Viewport Properties**.</span></span>  
  
2.  <span data-ttu-id="b5ad4-436">Cliquez sur **Centrer et zoomer**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-436">Click **Center and Zoom**.</span></span>  
  
3.  <span data-ttu-id="b5ad4-437">Assurez-vous que l'option **Définir un centre d'affichage et un niveau de zoom** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-437">Verify that the option **Set a view center and zoom level** is selected.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="b5ad4-438">Cliquez avec le bouton gauche de la souris sur le point de vue de la carte, puis faites glisser le centre de la fenêtre d'affichage vers l'emplacement de votre choix.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-438">Left-click the map viewport, and drag the center of the viewport to the location that you want.</span></span>  
  
6.  <span data-ttu-id="b5ad4-439">Utilisez la roulette de la souris pour modifier le niveau de zoom de la fenêtre d'affichage.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-439">Use the mouse wheel to change the zoom level of the viewport.</span></span>  
  
7.  <span data-ttu-id="b5ad4-440">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-440">Preview the report.</span></span>  
  
 <span data-ttu-id="b5ad4-441">En mode Conception, la carte apparaît sur la surface d'affichage et la vue est basée sur les exemples de données.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-441">In Design view, the map on the display surface and the view is based on sample data.</span></span> <span data-ttu-id="b5ad4-442">Dans le rapport rendu, la vue cartographique est centrée dans la vue que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-442">In the rendered report, the map view is centered on the view that you specified.</span></span>  
  
##  <a name="add-a-report-title"></a><a name="Title"></a><span data-ttu-id="b5ad4-443">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="b5ad4-443">Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="b5ad4-444">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="b5ad4-444">To add a report title</span></span>  
  
1.  <span data-ttu-id="b5ad4-445">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-445">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="b5ad4-446">Tapez **Ventes des magasins de New York** , puis cliquez à l'extérieur de la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-446">Type **Sales in New York Stores** and then click outside the text box.</span></span>  
  
 <span data-ttu-id="b5ad4-447">Ce titre s'affiche alors dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-447">This title will appear at the top of the report.</span></span> <span data-ttu-id="b5ad4-448">En l'absence d'en-tête de page défini, les éléments situés au-dessus du corps du rapport font office d'en-tête de rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-448">Items at the top of the report body when there is no page header defined are the equivalent of a report header.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="b5ad4-449">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="b5ad4-449">Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="b5ad4-450">Pour enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="b5ad4-450">To save the report</span></span>  
  
1.  <span data-ttu-id="b5ad4-451">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-451">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="b5ad4-452">À partir du bouton Générateur de rapports , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-452">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="b5ad4-453">Dans **Nom**, tapez **Ventes des magasins de New York**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-453">In **Name**, type **Store Sales in New York**.</span></span>  
  
 <span data-ttu-id="b5ad4-454">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-454">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b5ad4-455">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="b5ad4-455">Next Steps</span></span>  
 <span data-ttu-id="b5ad4-456">Ceci conclut la procédure pas à pas décrivant comment ajouter une carte à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-456">This concludes the walkthrough for how to add a map to your report.</span></span>  
  
 <span data-ttu-id="b5ad4-457">Pour plus d’informations, consultez [Maps &#40;générateur de rapports et SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) et l’entrée [de blog adaptation cartographique des données spatiales pour SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="b5ad4-457">For more information, see [Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) and the blog entry [Cartographic Adjustment of Spatial Data for SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) on blogs.msdn.com.</span></span>  
  
 <span data-ttu-id="b5ad4-458">Pour obtenir d’autres didacticiels, consultez [didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="b5ad4-458">For more tutorials, see [Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5ad4-459">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5ad4-459">See Also</span></span>  
 <span data-ttu-id="b5ad4-460">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="b5ad4-460">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="b5ad4-461">[Générateur de rapports SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="b5ad4-461">[Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="b5ad4-462">[Assistant Carte et Assistant couche &#40;Générateur de rapports et SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b5ad4-462">[Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b5ad4-463">Modifier l’affichage des polygones, des lignes et des points à l’aide de règles et de données analytiques &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b5ad4-463">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
