---
title: Vue de source de données (onglet structure de cube, concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.cubebuilder.datasourcepane.f1
ms.assetid: 1e39c910-5c10-4624-be27-ca02a461b46b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c949eaa17ec9d8bf585a5d595f31779382c41ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702139"
---
# <a name="data-source-view-cube-structure-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="ac487-102">Vue de source de données (onglet Structure de cube, Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="ac487-102">Data Source View (Cube Structure Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ac487-103">Le volet **Vue de source de données** permet d'afficher les tables et colonnes de la vue de source de données associée au cube sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ac487-103">Use the **Data Source View** pane to view tables and columns from the data source view associated with the selected cube.</span></span> <span data-ttu-id="ac487-104">Il sert à créer des groupes de mesures et des mesures en faisant glisser les colonnes du volet **Vue de source de données** vers le volet **Mesures** .</span><span class="sxs-lookup"><span data-stu-id="ac487-104">This pane is used to create measure groups and measures by dragging columns from the **Data Source View** pane to the **Measures** pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac487-105">Options</span><span class="sxs-lookup"><span data-stu-id="ac487-105">Options</span></span>  
 <span data-ttu-id="ac487-106">**Vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="ac487-106">**Data Source View**</span></span>  
 <span data-ttu-id="ac487-107">Affiche la vue de source de données associée au cube sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ac487-107">Displays the data source view associated with the selected cube.</span></span>  
  
 <span data-ttu-id="ac487-108">**(Déplacer le point de vue)**</span><span class="sxs-lookup"><span data-stu-id="ac487-108">**(Move viewpoint)**</span></span>  
 <span data-ttu-id="ac487-109">Cliquez dans le coin inférieur droit du volet, entre les barres de défilement, pour sélectionner une zone du volet **Vue de source de données** à afficher.</span><span class="sxs-lookup"><span data-stu-id="ac487-109">Click the lower right corner of the pane, between the scrollbars, to select an area of the **Data Source View** pane to view.</span></span>  
  
## <a name="diagram-context-menu"></a><span data-ttu-id="ac487-110">Menu contextuel Diagramme</span><span class="sxs-lookup"><span data-stu-id="ac487-110">Diagram Context Menu</span></span>  
 <span data-ttu-id="ac487-111">Les options suivantes sont disponibles dans le menu contextuel qui s’affiche quand vous cliquez avec le bouton droit sur l’arrière-plan du diagramme du volet **Vue de source de données** :</span><span class="sxs-lookup"><span data-stu-id="ac487-111">The following options are available in the context menu displayed by right-clicking the diagram background of the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="ac487-112">**Afficher les tables**</span><span class="sxs-lookup"><span data-stu-id="ac487-112">**Show Tables**</span></span>  
 <span data-ttu-id="ac487-113">Affiche la boîte de dialogue **Afficher la table**.</span><span class="sxs-lookup"><span data-stu-id="ac487-113">Displays the **Show Table** dialog box.</span></span> <span data-ttu-id="ac487-114">Pour plus d’informations sur la boîte de dialogue **Afficher la table**, consultez [Boîte de dialogue Afficher la table &#40;Analysis Services – Données multidimensionnelles&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac487-114">For more information about the **Show Table** dialog box, see [Show Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ac487-115">**Afficher toutes les tables**</span><span class="sxs-lookup"><span data-stu-id="ac487-115">**Show All Tables**</span></span>  
 <span data-ttu-id="ac487-116">Affiche, dans le volet, toutes les tables incluses dans la vue de source de données associée au cube.</span><span class="sxs-lookup"><span data-stu-id="ac487-116">Displays in the pane all tables included in the data source view associated with the cube.</span></span>  
  
 <span data-ttu-id="ac487-117">**Afficher seulement les tables utilisées**</span><span class="sxs-lookup"><span data-stu-id="ac487-117">**Show Only Used Tables**</span></span>  
 <span data-ttu-id="ac487-118">Affiche, dans le volet, uniquement les tables utilisées par le cube et appartenant à la vue de source de données associée.</span><span class="sxs-lookup"><span data-stu-id="ac487-118">Displays in the pane only those tables used by the cube from the associated data source view.</span></span>  
  
 <span data-ttu-id="ac487-119">**Afficher les noms conviviaux**</span><span class="sxs-lookup"><span data-stu-id="ac487-119">**Show Friendly Names**</span></span>  
 <span data-ttu-id="ac487-120">Permet d'afficher les noms conviviaux des objets dans le volet.</span><span class="sxs-lookup"><span data-stu-id="ac487-120">Selects to show friendly names for the objects in the pane.</span></span>  
  
 <span data-ttu-id="ac487-121">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="ac487-121">**Select All**</span></span>  
 <span data-ttu-id="ac487-122">Sélectionne tous les objets se trouvant dans le volet.</span><span class="sxs-lookup"><span data-stu-id="ac487-122">Selects all of the objects in the pane.</span></span>  
  
 <span data-ttu-id="ac487-123">**Rechercher une table**</span><span class="sxs-lookup"><span data-stu-id="ac487-123">**Find Table**</span></span>  
 <span data-ttu-id="ac487-124">Affiche la boîte de dialogue **Rechercher une table**.</span><span class="sxs-lookup"><span data-stu-id="ac487-124">Displays the **Find Table** dialog box.</span></span> <span data-ttu-id="ac487-125">Pour plus d’informations sur la boîte de dialogue **Rechercher une table**, consultez [Boîte de dialogue Rechercher une table &#40;Analysis Services – Données multidimensionnelles&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac487-125">For more information about the **Find Table** dialog box, see [Find Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ac487-126">**Réorganiser les tables**</span><span class="sxs-lookup"><span data-stu-id="ac487-126">**Arrange Tables**</span></span>  
 <span data-ttu-id="ac487-127">Organise les objets du volet en fonction de la disposition page spécifiée en sélectionnant **Basculer en présentation diagonale** ou **Basculer en présentation rectangulaire**.</span><span class="sxs-lookup"><span data-stu-id="ac487-127">Arranges the objects in the pane according to the layout specified by selecting either **Switch to Diagonal Layout** or **Switch to Rectangular Layout**.</span></span>  
  
 <span data-ttu-id="ac487-128">**Basculer en présentation diagonale**</span><span class="sxs-lookup"><span data-stu-id="ac487-128">**Switch to Diagonal Layout**</span></span>  
 <span data-ttu-id="ac487-129">Sélectionnez cette option pour disposer les objets en diagonale.</span><span class="sxs-lookup"><span data-stu-id="ac487-129">Select to arrange objects in a diagonal pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac487-130">Cette option s’affiche seulement si **Basculer en présentation rectangulaire** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ac487-130">This option is displayed only if **Switch to Rectangular Layout** is selected.</span></span>  
  
 <span data-ttu-id="ac487-131">**Basculer en présentation rectangulaire**</span><span class="sxs-lookup"><span data-stu-id="ac487-131">**Switch to Rectangular Layout**</span></span>  
 <span data-ttu-id="ac487-132">Sélectionnez cette option pour disposer les objets en rectangle.</span><span class="sxs-lookup"><span data-stu-id="ac487-132">Select to arrange objects in a rectangular pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac487-133">Cette option s’affiche seulement si **Basculer en présentation diagonale** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ac487-133">This option is displayed only if **Switch to Diagonal Layout** is selected.</span></span>  
  
 <span data-ttu-id="ac487-134">**Modifier la vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="ac487-134">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ac487-135">Affiche le concepteur de vue de source de données pour la vue associée à l'objet.</span><span class="sxs-lookup"><span data-stu-id="ac487-135">Displays Data Source View Designer for the data source view associated with the object.</span></span> <span data-ttu-id="ac487-136">Pour plus d’informations sur le Concepteur de vue de source de données, consultez [Concepteur de vue de source de données &#40;Analysis Services – Données multidimensionnelles&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac487-136">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ac487-137">**Afficher vue de source de données dans**</span><span class="sxs-lookup"><span data-stu-id="ac487-137">**Show Data Source View In**</span></span>  
 <span data-ttu-id="ac487-138">Sélectionnez une des options suivantes pour faire passer le volet **Vue de source de données** entre les modes suivants :</span><span class="sxs-lookup"><span data-stu-id="ac487-138">Select one of the following options to toggle between viewing the **Data Source View** pane in the following modes:</span></span>  
  
-   <span data-ttu-id="ac487-139">Diagramme</span><span class="sxs-lookup"><span data-stu-id="ac487-139">Diagram</span></span>  
  
     <span data-ttu-id="ac487-140">Affiche un diagramme des tables et colonnes associées au cube actif.</span><span class="sxs-lookup"><span data-stu-id="ac487-140">Displays a diagram of the tables and columns associated with the current cube.</span></span>  
  
-   <span data-ttu-id="ac487-141">Arborescence</span><span class="sxs-lookup"><span data-stu-id="ac487-141">Tree</span></span>  
  
     <span data-ttu-id="ac487-142">Affiche une arborescence contenant les tables et colonnes associées au cube actif.</span><span class="sxs-lookup"><span data-stu-id="ac487-142">Displays a tree view containing the tables and columns associated with the current cube.</span></span>  
  
 <span data-ttu-id="ac487-143">**Copier le schéma à partir de**</span><span class="sxs-lookup"><span data-stu-id="ac487-143">**Copy Diagram From**</span></span>  
 <span data-ttu-id="ac487-144">Sélectionnez l’un des diagrammes inclus dans la vue de source de données associée au cube afin de l’afficher dans le volet **Vue de source de données** .</span><span class="sxs-lookup"><span data-stu-id="ac487-144">Select one of the diagrams included in the data source view associated with the cube to display it in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="ac487-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="ac487-145">**Zoom**</span></span>  
 <span data-ttu-id="ac487-146">Sélectionnez une option de zoom disponible.</span><span class="sxs-lookup"><span data-stu-id="ac487-146">Select an available zoom option.</span></span>  
  
 <span data-ttu-id="ac487-147">**Propriétés**</span><span class="sxs-lookup"><span data-stu-id="ac487-147">**Properties**</span></span>  
 <span data-ttu-id="ac487-148">Affiche la fenêtre **Propriétés** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour la vue de source de données associée au cube.</span><span class="sxs-lookup"><span data-stu-id="ac487-148">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the data source view associated with the cube.</span></span>  
  
## <a name="table-context-menu"></a><span data-ttu-id="ac487-149">Menu contextuel Table</span><span class="sxs-lookup"><span data-stu-id="ac487-149">Table Context Menu</span></span>  
 <span data-ttu-id="ac487-150">Les options suivantes sont disponibles dans le menu contextuel qui s’affiche quand vous cliquez avec le bouton droit sur le nom d’une table ou d’une vue dans le volet **Vue de source de données** :</span><span class="sxs-lookup"><span data-stu-id="ac487-150">The following options are available in the context menu displayed by right-clicking the name of a table or view in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="ac487-151">**Afficher les tables associées**</span><span class="sxs-lookup"><span data-stu-id="ac487-151">**Show Related Tables**</span></span>  
 <span data-ttu-id="ac487-152">Affiche dans le volet les tables relatives à la table sélectionnée dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="ac487-152">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="ac487-153">**Masquer la table**</span><span class="sxs-lookup"><span data-stu-id="ac487-153">**Hide Table**</span></span>  
 <span data-ttu-id="ac487-154">Supprime la table du volet.</span><span class="sxs-lookup"><span data-stu-id="ac487-154">Removes the table from the pane.</span></span>  
  
 <span data-ttu-id="ac487-155">**Explorer les données**</span><span class="sxs-lookup"><span data-stu-id="ac487-155">**Explore Data**</span></span>  
 <span data-ttu-id="ac487-156">Ouvre la boîte de dialogue **Explorer les données** se rapportant à la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-156">Display the **Explore Data** dialog box for the selected table.</span></span>  
  
 <span data-ttu-id="ac487-157">**Modifier la vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="ac487-157">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ac487-158">Affiche le Concepteur de vue de source de données de la vue qui contient la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-158">Displays Data Source View Designer for the data source view that contains the selected table.</span></span> <span data-ttu-id="ac487-159">Pour plus d’informations sur le Concepteur de vue de source de données, consultez [Concepteur de vue de source de données &#40;Analysis Services – Données multidimensionnelles&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac487-159">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ac487-160">**Nouveau groupe de mesures à partir de la table**</span><span class="sxs-lookup"><span data-stu-id="ac487-160">**New Measure Group from Table**</span></span>  
 <span data-ttu-id="ac487-161">Définit un nouveau groupe de mesures dans le volet **Mesures** en fonction de la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-161">Defines a new measure group in the **Measures** pane based on the selected table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac487-162">Cette option est active uniquement si la table n’est pas encore référencée par un groupe de mesures dans le volet **Mesures** .</span><span class="sxs-lookup"><span data-stu-id="ac487-162">This option is enabled only if the table is not yet referenced by a measure group in the **Measures** pane.</span></span>  
  
 <span data-ttu-id="ac487-163">**Propriétés**</span><span class="sxs-lookup"><span data-stu-id="ac487-163">**Properties**</span></span>  
 <span data-ttu-id="ac487-164">Affiche la fenêtre **Propriétés** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-164">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected table.</span></span>  
  
## <a name="column-context-menu"></a><span data-ttu-id="ac487-165">Menu contextuel Colonne</span><span class="sxs-lookup"><span data-stu-id="ac487-165">Column Context Menu</span></span>  
 <span data-ttu-id="ac487-166">Les options suivantes sont disponibles dans le menu contextuel qui s’affiche quand vous cliquez avec le bouton droit sur le nom d’une colonne ou d’une vue dans le volet **Vue de source de données** :</span><span class="sxs-lookup"><span data-stu-id="ac487-166">The following options are available in the context menu displayed by right-clicking the name of a column in a table or view in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="ac487-167">**Nouvelle mesure de la colonne**</span><span class="sxs-lookup"><span data-stu-id="ac487-167">**New Measure from Column**</span></span>  
 <span data-ttu-id="ac487-168">Définit une nouvelle mesure dans le volet **Mesures** en fonction de la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-168">Defines a new measure in the **Measures** pane based on the selected column.</span></span>  
  
 <span data-ttu-id="ac487-169">**Explorer les données**</span><span class="sxs-lookup"><span data-stu-id="ac487-169">**Explore Data**</span></span>  
 <span data-ttu-id="ac487-170">Affiche la boîte de dialogue **Explorer les données** pour la table contenant la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-170">Display the **Explore Data** dialog box for the table that contains the selected column.</span></span>  
  
 <span data-ttu-id="ac487-171">**Modifier la vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="ac487-171">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ac487-172">Affiche le Concepteur de vue de source de données de la vue qui contient la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-172">Displays Data Source View Designer for the data source view that contains the selected column.</span></span> <span data-ttu-id="ac487-173">Pour plus d’informations sur le Concepteur de vue de source de données, consultez [Concepteur de vue de source de données &#40;Analysis Services – Données multidimensionnelles&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac487-173">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ac487-174">**Propriétés**</span><span class="sxs-lookup"><span data-stu-id="ac487-174">**Properties**</span></span>  
 <span data-ttu-id="ac487-175">Affiche la fenêtre **Propriétés** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-175">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected column.</span></span>  
  
## <a name="relationship-context-menu"></a><span data-ttu-id="ac487-176">Menu contextuel Relation</span><span class="sxs-lookup"><span data-stu-id="ac487-176">Relationship Context Menu</span></span>  
 <span data-ttu-id="ac487-177">Les options suivantes sont disponibles dans le menu contextuel qui s’affiche quand vous cliquez avec le bouton droit sur une relation dans le volet **Vue de source de données** :</span><span class="sxs-lookup"><span data-stu-id="ac487-177">The following options are available in the context menu displayed by right-clicking a relationship in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="ac487-178">**Modifier la vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="ac487-178">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ac487-179">Affiche le concepteur de vue de source de données pour la vue qui contient la relation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-179">Displays Data Source View Designer for the data source view that contains the selected relationship.</span></span> <span data-ttu-id="ac487-180">Pour plus d’informations sur le Concepteur de vue de source de données, consultez [Concepteur de vue de source de données &#40;Analysis Services – Données multidimensionnelles&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac487-180">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ac487-181">**Propriétés**</span><span class="sxs-lookup"><span data-stu-id="ac487-181">**Properties**</span></span>  
 <span data-ttu-id="ac487-182">Affiche la fenêtre **Propriétés** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour la relation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac487-182">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac487-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac487-183">See Also</span></span>  
 <span data-ttu-id="ac487-184">[Barre d’outils &#40;onglet structure de cube, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ac487-184">[Toolbar &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="ac487-185">[Mesures &#40;onglet structure de cube, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ac487-185">[Measures &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="ac487-186">[Dimensions &#40;onglet structure de cube, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ac487-186">[Dimensions &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ac487-187">Structure de cube &#40;concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="ac487-187">Cube Structure &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-structure-cube-designer-analysis-services-multidimensional-data.md)  
  
  
