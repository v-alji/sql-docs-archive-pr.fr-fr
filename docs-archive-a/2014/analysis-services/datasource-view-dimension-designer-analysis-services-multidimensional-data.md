---
title: Vue de source de données (onglet structure de dimension, concepteur de dimensions) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.datasourcepane.f1
ms.assetid: c4bd3c5e-8986-448f-b9db-3551f50f0696
author: minewiskan
ms.author: owend
ms.openlocfilehash: fb2529e1835829bc84eec77c18b7ec05da5c4220
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614240"
---
# <a name="data-source-view-dimension-structure-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="73a3f-102">Vue de source de données (onglet Structure de dimension, Concepteur de dimensions) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="73a3f-102">Data Source View (Dimension Structure Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="73a3f-103">Utilisez le volet **Vue de source de données** pour afficher les tables et les colonnes associées à la dimension sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-103">Use the **Data Source View** pane to view tables and columns from the data source view associated with the selected dimension.</span></span> <span data-ttu-id="73a3f-104">Ce volet sert à créer des attributs, des propriétés de membres, des hiérarchies et des niveaux. Pour cela, faites glisser des colonnes du volet **Vue de source de données** dans le volet **Attributs** ou **Hiérarchies et niveaux** .</span><span class="sxs-lookup"><span data-stu-id="73a3f-104">This pane is used to create attributes, member properties, hierarchies, and levels, by dragging columns from the **Data Source View** pane to the **Attributes** or **Hierarchies and Levels** pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="73a3f-105">Options</span><span class="sxs-lookup"><span data-stu-id="73a3f-105">Options</span></span>  
 <span data-ttu-id="73a3f-106">**Vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="73a3f-106">**Data Source View**</span></span>  
 <span data-ttu-id="73a3f-107">Affiche la vue de source de données associée à la dimension sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-107">Displays the data source view associated with the selected dimension.</span></span>  
  
 <span data-ttu-id="73a3f-108">**(Déplacer le point de vue)**</span><span class="sxs-lookup"><span data-stu-id="73a3f-108">**(Move viewpoint)**</span></span>  
 <span data-ttu-id="73a3f-109">Cliquez dans le coin inférieur droit du volet, entre les barres de défilement, pour sélectionner une zone du volet **Vue de source de données** à afficher.</span><span class="sxs-lookup"><span data-stu-id="73a3f-109">Click the lower right corner of the pane, between the scrollbars, to select an area of the **Data Source View** pane to view.</span></span>  
  
## <a name="diagram-context-menu"></a><span data-ttu-id="73a3f-110">Menu contextuel Diagramme</span><span class="sxs-lookup"><span data-stu-id="73a3f-110">Diagram Context Menu</span></span>  
 <span data-ttu-id="73a3f-111">Les options répertoriées dans le tableau suivant sont disponibles dans le menu contextuel qui s’affiche en cliquant avec le bouton droit sur l’arrière-plan du schéma du volet **Vue de source de données** .</span><span class="sxs-lookup"><span data-stu-id="73a3f-111">The options listed in the following table are available in the context menu displayed by right-clicking the diagram background of the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="73a3f-112">**Afficher les tables**</span><span class="sxs-lookup"><span data-stu-id="73a3f-112">**Show Tables**</span></span>  
 <span data-ttu-id="73a3f-113">Affiche la boîte de dialogue **Afficher la table**.</span><span class="sxs-lookup"><span data-stu-id="73a3f-113">Displays the **Show Table** dialog box.</span></span> <span data-ttu-id="73a3f-114">Pour plus d’informations sur la boîte de dialogue **Afficher la table**, consultez [Boîte de dialogue Afficher la table &#40;Analysis Services – Données multidimensionnelles&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="73a3f-114">For more information about the **Show Table** dialog box, see [Show Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="73a3f-115">**Afficher toutes les tables**</span><span class="sxs-lookup"><span data-stu-id="73a3f-115">**Show All Tables**</span></span>  
 <span data-ttu-id="73a3f-116">Affiche dans le volet toutes les tables figurant dans la vue de source de données associées à la dimension.</span><span class="sxs-lookup"><span data-stu-id="73a3f-116">Displays in the pane all tables included in the data source view associated with the dimension.</span></span>  
  
 <span data-ttu-id="73a3f-117">**Afficher seulement les tables utilisées**</span><span class="sxs-lookup"><span data-stu-id="73a3f-117">**Show Only Used Tables**</span></span>  
 <span data-ttu-id="73a3f-118">Affiche dans le volet toutes les tables utilisées par la dimension à partir de la vue de source de données associée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-118">Displays in the pane only those tables used by the dimension from the associated data source view.</span></span>  
  
 <span data-ttu-id="73a3f-119">**Afficher les noms conviviaux**</span><span class="sxs-lookup"><span data-stu-id="73a3f-119">**Show Friendly Names**</span></span>  
 <span data-ttu-id="73a3f-120">Sélectionnez cette option pour afficher les noms conviviaux des objets du volet.</span><span class="sxs-lookup"><span data-stu-id="73a3f-120">Select to show friendly names for the objects in the pane.</span></span>  
  
 <span data-ttu-id="73a3f-121">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="73a3f-121">**Select All**</span></span>  
 <span data-ttu-id="73a3f-122">Sélectionne tous les objets se trouvant dans le volet.</span><span class="sxs-lookup"><span data-stu-id="73a3f-122">Selects all of the objects in the pane.</span></span>  
  
 <span data-ttu-id="73a3f-123">**Rechercher une table**</span><span class="sxs-lookup"><span data-stu-id="73a3f-123">**Find Table**</span></span>  
 <span data-ttu-id="73a3f-124">Affiche la boîte de dialogue **Rechercher une table**.</span><span class="sxs-lookup"><span data-stu-id="73a3f-124">Displays the **Find Table** dialog box.</span></span> <span data-ttu-id="73a3f-125">Pour plus d’informations sur la boîte de dialogue **Rechercher une table**, consultez [Boîte de dialogue Rechercher une table &#40;Analysis Services – Données multidimensionnelles&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="73a3f-125">For more information about the **Find Table** dialog box, see [Find Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="73a3f-126">**Réorganiser les tables**</span><span class="sxs-lookup"><span data-stu-id="73a3f-126">**Arrange Tables**</span></span>  
 <span data-ttu-id="73a3f-127">Organise les objets du volet en fonction de la disposition page spécifiée en sélectionnant **Basculer en présentation diagonale** ou **Basculer en présentation rectangulaire**.</span><span class="sxs-lookup"><span data-stu-id="73a3f-127">Arranges the objects in the pane according to the layout specified by selecting either **Switch to Diagonal Layout** or **Switch to Rectangular Layout**.</span></span>  
  
 <span data-ttu-id="73a3f-128">**Basculer en présentation diagonale**</span><span class="sxs-lookup"><span data-stu-id="73a3f-128">**Switch to Diagonal Layout**</span></span>  
 <span data-ttu-id="73a3f-129">Sélectionnez cette option pour disposer les objets en diagonale.</span><span class="sxs-lookup"><span data-stu-id="73a3f-129">Select to arrange objects in a diagonal pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73a3f-130">Cette option s’affiche seulement si **Basculer en présentation rectangulaire** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="73a3f-130">This option is displayed only if **Switch to Rectangular Layout** is selected.</span></span>  
  
 <span data-ttu-id="73a3f-131">**Basculer en présentation rectangulaire**</span><span class="sxs-lookup"><span data-stu-id="73a3f-131">**Switch to Rectangular Layout**</span></span>  
 <span data-ttu-id="73a3f-132">Sélectionnez cette option pour disposer les objets en rectangle.</span><span class="sxs-lookup"><span data-stu-id="73a3f-132">Select to arrange objects in a rectangular pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73a3f-133">Cette option s’affiche seulement si **Basculer en présentation diagonale** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="73a3f-133">This option is displayed only if **Switch to Diagonal Layout** is selected.</span></span>  
  
 <span data-ttu-id="73a3f-134">**Modifier la vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="73a3f-134">**Edit Data Source View**</span></span>  
 <span data-ttu-id="73a3f-135">Affiche le **Concepteur de vue de source de données** pour la vue de source de données associée à la dimension.</span><span class="sxs-lookup"><span data-stu-id="73a3f-135">Displays **Data Source View Designer** for the data source view associated with the dimension.</span></span> <span data-ttu-id="73a3f-136">Pour plus d’informations sur le **Concepteur de vue de source de données**, consultez [Concepteur de vue de source de données &#40;Analysis Services – Données multidimensionnelles&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="73a3f-136">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="73a3f-137">**Afficher vue de source de données dans**</span><span class="sxs-lookup"><span data-stu-id="73a3f-137">**Show Data Source View In**</span></span>  
 <span data-ttu-id="73a3f-138">Sélectionnez une des options suivantes pour faire passer le volet **Vue de source de données** entre les modes suivants :</span><span class="sxs-lookup"><span data-stu-id="73a3f-138">Select one of the following options to toggle between viewing the **Data Source View** pane in the following modes:</span></span>  
  
-   <span data-ttu-id="73a3f-139">Diagramme</span><span class="sxs-lookup"><span data-stu-id="73a3f-139">Diagram</span></span>  
  
     <span data-ttu-id="73a3f-140">Affiche un diagramme des tables et des colonnes associées à la dimension active.</span><span class="sxs-lookup"><span data-stu-id="73a3f-140">Displays a diagram of the tables and columns associated with the current dimension.</span></span>  
  
-   <span data-ttu-id="73a3f-141">Arborescence</span><span class="sxs-lookup"><span data-stu-id="73a3f-141">Tree</span></span>  
  
     <span data-ttu-id="73a3f-142">Affiche une arborescence des tables et des colonnes associées à la dimension active.</span><span class="sxs-lookup"><span data-stu-id="73a3f-142">Displays a tree view that contains the tables and columns associated with the current dimension.</span></span>  
  
 <span data-ttu-id="73a3f-143">**Copier le schéma à partir de**</span><span class="sxs-lookup"><span data-stu-id="73a3f-143">**Copy Diagram From**</span></span>  
 <span data-ttu-id="73a3f-144">Sélectionnez un des diagrammes de la vue de source de données associée à la dimension pour l’afficher dans le volet **Vue de source de données** .</span><span class="sxs-lookup"><span data-stu-id="73a3f-144">Select one of the diagrams included in the data source view associated with the dimension to display it in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="73a3f-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="73a3f-145">**Zoom**</span></span>  
 <span data-ttu-id="73a3f-146">Sélectionnez une option de zoom disponible.</span><span class="sxs-lookup"><span data-stu-id="73a3f-146">Select an available zoom option.</span></span>  
  
 <span data-ttu-id="73a3f-147">**Propriétés**</span><span class="sxs-lookup"><span data-stu-id="73a3f-147">**Properties**</span></span>  
 <span data-ttu-id="73a3f-148">Affiche la fenêtre **Propriétés** dans **SQL Server Data Tools** pour la vue de source de données associée à la dimension.</span><span class="sxs-lookup"><span data-stu-id="73a3f-148">Displays the **Properties** window in **SQL Server Data Tools** for the data source view associated with the dimension.</span></span>  
  
## <a name="table-context-menu"></a><span data-ttu-id="73a3f-149">Menu contextuel Table</span><span class="sxs-lookup"><span data-stu-id="73a3f-149">Table Context Menu</span></span>  
 <span data-ttu-id="73a3f-150">Les options répertoriées dans le tableau suivant sont disponibles dans le menu contextuel qui s’affiche en cliquant le bouton droit sur le nom d’une table ou d’une vue dans le volet **Vue de source de données** .</span><span class="sxs-lookup"><span data-stu-id="73a3f-150">The options listed in the following table are available in the context menu displayed by right-clicking the name of a table or view in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="73a3f-151">**Afficher les tables associées**</span><span class="sxs-lookup"><span data-stu-id="73a3f-151">**Show Related Tables**</span></span>  
 <span data-ttu-id="73a3f-152">Affiche dans le volet les tables relatives à la table sélectionnée dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="73a3f-152">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="73a3f-153">**Masquer la table**</span><span class="sxs-lookup"><span data-stu-id="73a3f-153">**Hide Table**</span></span>  
 <span data-ttu-id="73a3f-154">Supprime la table du volet.</span><span class="sxs-lookup"><span data-stu-id="73a3f-154">Removes the table from the pane.</span></span>  
  
 <span data-ttu-id="73a3f-155">**Explorer les données**</span><span class="sxs-lookup"><span data-stu-id="73a3f-155">**Explore Data**</span></span>  
 <span data-ttu-id="73a3f-156">Ouvre la boîte de dialogue **Explorer les données** pour la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-156">Displays the **Explore Data** dialog box for the selected table.</span></span>  
  
 <span data-ttu-id="73a3f-157">**Modifier la vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="73a3f-157">**Edit Data Source View**</span></span>  
 <span data-ttu-id="73a3f-158">Affiche le **Concepteur de vue de source** de données pour la vue de source de données qui contient la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-158">Displays **Data Source View Designer** for the data source view that contains the selected table.</span></span> <span data-ttu-id="73a3f-159">Pour plus d’informations sur le **Concepteur de vue de source de données**, consultez [Concepteur de vue de source de données &#40;Analysis Services – Données multidimensionnelles&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="73a3f-159">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="73a3f-160">**Propriétés**</span><span class="sxs-lookup"><span data-stu-id="73a3f-160">**Properties**</span></span>  
 <span data-ttu-id="73a3f-161">Affiche la fenêtre **Propriétés** dans **SQL Server Data Tools** pour la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-161">Displays the **Properties** window in **SQL Server Data Tools** for the selected table.</span></span>  
  
## <a name="column-context-menu"></a><span data-ttu-id="73a3f-162">Menu contextuel Colonne</span><span class="sxs-lookup"><span data-stu-id="73a3f-162">Column Context Menu</span></span>  
 <span data-ttu-id="73a3f-163">Les options répertoriées dans le tableau suivant sont disponibles dans le menu contextuel qui s’affiche en cliquant avec le bouton droit sur le nom de la colonne d’une table ou d’une vue dans le volet **Vue de source de données** .</span><span class="sxs-lookup"><span data-stu-id="73a3f-163">The options listed in the following table are available in the context menu displayed by right-clicking the name of a column in a table or view in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="73a3f-164">**Nouvel attribut de colonne**</span><span class="sxs-lookup"><span data-stu-id="73a3f-164">**New Attribute from Column**</span></span>  
 <span data-ttu-id="73a3f-165">Affiche dans le volet les tables relatives à la table sélectionnée dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="73a3f-165">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="73a3f-166">**Explorer les données**</span><span class="sxs-lookup"><span data-stu-id="73a3f-166">**Explore Data**</span></span>  
 <span data-ttu-id="73a3f-167">Affiche la boîte de dialogue **Explorer les données** pour la table contenant la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-167">Display the **Explore Data** dialog box for the table that contains the selected column.</span></span>  
  
 <span data-ttu-id="73a3f-168">**Modifier la vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="73a3f-168">**Edit Data Source View**</span></span>  
 <span data-ttu-id="73a3f-169">Affiche le **Concepteur de vue de source** de données pour la vue de source de données qui contient la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-169">Displays **Data Source View Designer** for the data source view that contains the selected column.</span></span> <span data-ttu-id="73a3f-170">Pour plus d’informations sur le **Concepteur de vue de source de données**, consultez [Concepteur de vue de source de données &#40;Analysis Services – Données multidimensionnelles&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="73a3f-170">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="73a3f-171">**Propriétés**</span><span class="sxs-lookup"><span data-stu-id="73a3f-171">**Properties**</span></span>  
 <span data-ttu-id="73a3f-172">Affiche la fenêtre **Propriétés** dans **SQL Server Data Tools** pour la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-172">Displays the **Properties** window in **SQL Server Data Tools** for the selected column.</span></span>  
  
## <a name="relationship-context-menu"></a><span data-ttu-id="73a3f-173">Menu contextuel Relation</span><span class="sxs-lookup"><span data-stu-id="73a3f-173">Relationship Context Menu</span></span>  
 <span data-ttu-id="73a3f-174">Les options répertoriées dans le tableau suivant sont disponibles dans le menu contextuel qui s’affiche en cliquant avec le bouton droit sur une relation dans le volet **Vue de source de données** .</span><span class="sxs-lookup"><span data-stu-id="73a3f-174">The options listed in the following table are available in the context menu displayed by right-clicking a relationship in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="73a3f-175">**Modifier la vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="73a3f-175">**Edit Data Source View**</span></span>  
 <span data-ttu-id="73a3f-176">Affiche le **Concepteur de vue de source** de données pour la vue de source de données qui contient la relation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-176">Displays **Data Source View Designer** for the data source view that contains the selected relationship.</span></span> <span data-ttu-id="73a3f-177">Pour plus d’informations sur le **Concepteur de vue de source de données**, consultez [Concepteur de vue de source de données &#40;Analysis Services – Données multidimensionnelles&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="73a3f-177">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="73a3f-178">**Propriétés**</span><span class="sxs-lookup"><span data-stu-id="73a3f-178">**Properties**</span></span>  
 <span data-ttu-id="73a3f-179">Affiche la fenêtre **Propriétés** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour la relation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="73a3f-179">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a3f-180">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="73a3f-180">See Also</span></span>  
 <span data-ttu-id="73a3f-181">[Structure de dimension &#40;concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;](dimension-structure-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="73a3f-181">[Dimension Structure &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](dimension-structure-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="73a3f-182">[Barre d’outils &#40;onglet structure de dimension, concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;](toolbar-dimension-structure-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="73a3f-182">[Toolbar &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-dimension-structure-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="73a3f-183">[Attributs &#40;onglet structure de dimension, concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;](attributes-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="73a3f-183">[Attributes &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](attributes-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="73a3f-184">Hiérarchies &#40;onglet structure de dimension, concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="73a3f-184">Hierarchies &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](hierarchies-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
