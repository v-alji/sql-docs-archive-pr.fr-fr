---
title: Procédure pas à pas sur le diagramme de cluster (compléments d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, cluster
- diagram, cluster
- shapes, data mining
- shapes, cluster
- data mining layout toolbar
ms.assetid: 761bef6a-37d4-4b19-944e-f2aadc75a242
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ee8cce3cd2498d765c9b69e7f352b49cb0f115
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603138"
---
# <a name="cluster-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="9cee8-102">Procédure pas à pas Diagramme de cluster (Compléments d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="9cee8-102">Cluster Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="9cee8-103">Une fois que vous avez créé un modèle de clustering, vous pouvez l’importer dans Visio à l’aide de la forme **cluster** , puis continuer à personnaliser et améliorer la disposition.</span><span class="sxs-lookup"><span data-stu-id="9cee8-103">After you have created a clustering model, you can import it into Visio using the **Cluster** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="9cee8-104">Les **formes d’exploration de données pour Visio** incluent les contrôles personnalisés suivants pour l’utilisation des diagrammes d’exploration de données :</span><span class="sxs-lookup"><span data-stu-id="9cee8-104">The **Data Mining Shapes for Visio** include the following custom controls for working with data mining diagrams:</span></span>  
  
-   <span data-ttu-id="9cee8-105">Contrôles de rendu du diagramme de cluster</span><span class="sxs-lookup"><span data-stu-id="9cee8-105">Rendering controls for the cluster diagram</span></span>  
  
     <span data-ttu-id="9cee8-106">Ces options font partie de l' **Assistant cluster** qui est lancé lorsque vous déposez une forme dans l’espace de travail Visio.</span><span class="sxs-lookup"><span data-stu-id="9cee8-106">These options are part of the **Cluster Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="9cee8-107">Barre d’outils de **disposition d’exploration de données**</span><span class="sxs-lookup"><span data-stu-id="9cee8-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="9cee8-108">Ces options sont ajoutées à l'espace de travail Visio pour vous aider à interagir avec la forme d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="9cee8-108">These options are added to the Visio workspace to help you interact with the data mining shape.</span></span> <span data-ttu-id="9cee8-109">Ces options diffèrent selon le type de modèle d'exploration de données que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="9cee8-109">The options are different depending on which type of data mining model you are using.</span></span>  
  
## <a name="build-a-cluster-diagram"></a><span data-ttu-id="9cee8-110">Créer un diagramme de cluster</span><span class="sxs-lookup"><span data-stu-id="9cee8-110">Build a Cluster Diagram</span></span>  
 <span data-ttu-id="9cee8-111">Cette procédure pas à pas montre comment créer et personnaliser un diagramme de clustering dans Visio.</span><span class="sxs-lookup"><span data-stu-id="9cee8-111">This walkthrough demonstrates how to build and customize a clustering diagram in Visio.</span></span>  
  
 <span data-ttu-id="9cee8-112">Pour pouvoir la suivre, vous devez disposer d'un modèle de clustering.</span><span class="sxs-lookup"><span data-stu-id="9cee8-112">To follow along, you should have a clustering model already available.</span></span> <span data-ttu-id="9cee8-113">Si vous n’avez pas de modèle, utilisez l' [Assistant Cluster &#40;les compléments d’exploration de données pour Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) Assistant et créez un modèle à l’aide du jeu de données d’apprentissage dans l’exemple de classeur, en utilisant toutes les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="9cee8-113">If you do not have a model, use the [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) wizard and create a model using the Training data set in the sample workbook, using all the defaults.</span></span>  
  
#### <a name="use-the-cluster-visio-shape-wizard"></a><span data-ttu-id="9cee8-114">Utiliser l'Assistant Création de forme Cluster Visio</span><span class="sxs-lookup"><span data-stu-id="9cee8-114">Use the Cluster Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="9cee8-115">Si les **formes d’exploration de données Microsoft** ne s’affichent pas dans la liste **formes** , cliquez sur **autres formes**, sélectionnez **ouvrir le stencil**, puis ouvrez le modèle à partir de l’emplacement d’installation par défaut.</span><span class="sxs-lookup"><span data-stu-id="9cee8-115">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="9cee8-116">\<drive>: \Program files\Microsoft SQL Server 2012 DM Add-ins</span><span class="sxs-lookup"><span data-stu-id="9cee8-116">\<drive>:\Program files\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="9cee8-117">Faites glisser la forme **cluster** sur la page.</span><span class="sxs-lookup"><span data-stu-id="9cee8-117">Drag the **Cluster** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="9cee8-118">Sur la page d’accueil de l' **Assistant Création de forme cluster Visio**, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="9cee8-118">On the welcome page of the **Cluster Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="9cee8-119">Dans la page **Sélectionner une source de données** de l' **Assistant cluster**, choisissez une connexion à un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] serveur qui contient les modèles d’exploration de données que vous souhaitez visualiser.</span><span class="sxs-lookup"><span data-stu-id="9cee8-119">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that contains the data mining models you want to visualize.</span></span>  
  
5.  <span data-ttu-id="9cee8-120">Sélectionnez un modèle d’exploration de données approprié, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="9cee8-120">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="9cee8-121">Pour vous assurer que vous choisissez un modèle de clustering, passez en revue la description dans le volet **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="9cee8-121">To make sure you choose a clustering model, review the description in the **Properties** pane.</span></span>  
  
6.  <span data-ttu-id="9cee8-122">Si la connexion réussit, sur la page **Options du diagramme de cluster**, vous décidez du type de diagramme de cluster à inclure dans votre présentation Visio :</span><span class="sxs-lookup"><span data-stu-id="9cee8-122">If the connection is successful, on the page, **Options for cluster diagram**, you decide which type of cluster diagram to include in your Visio presentation:</span></span>  
  
     <span data-ttu-id="9cee8-123">**Afficher uniquement les formes de cluster**</span><span class="sxs-lookup"><span data-stu-id="9cee8-123">**Show cluster shapes only**</span></span>  
     <span data-ttu-id="9cee8-124">Cette option crée un diagramme de cluster simple, chaque cluster étant représenté par un rectangle ou une autre forme que vous choisissez</span><span class="sxs-lookup"><span data-stu-id="9cee8-124">This option creates a simple cluster diagram, with each cluster represented by a rectangle or other shape you choose</span></span>  
  
     <span data-ttu-id="9cee8-125">**Afficher les clusters avec le graphique des caractéristiques**</span><span class="sxs-lookup"><span data-stu-id="9cee8-125">**Show clusters with characteristics chart**</span></span>  
     <span data-ttu-id="9cee8-126">Cette option crée le même graphique que précédemment, mais des histogrammes se trouvent à l'intérieur des formes pour décrire les caractéristiques du cluster.</span><span class="sxs-lookup"><span data-stu-id="9cee8-126">This option creates the same chart as above, but inside the shapes are histograms that describe the characteristics of the cluster.</span></span>  
  
     <span data-ttu-id="9cee8-127">![Exemple de graphique des caractéristiques de cluster dans Visio](media/dm13-visio-cluster-samplecharshape.gif "Exemple de graphique des caractéristiques de cluster dans Visio")</span><span class="sxs-lookup"><span data-stu-id="9cee8-127">![Example of cluster characteristics chart in Visio](media/dm13-visio-cluster-samplecharshape.gif "Example of cluster characteristics chart in Visio")</span></span>  
  
     <span data-ttu-id="9cee8-128">**Afficher les clusters avec le graphique de discrimination**</span><span class="sxs-lookup"><span data-stu-id="9cee8-128">**Show clusters with discrimination chart**</span></span>  
     <span data-ttu-id="9cee8-129">Cette option permet de créer le même graphique que le diagramme de cluster, mais elle répertorie les caractéristiques du cluster actuel qui le distinguent le plus fortement d'autres clusters.</span><span class="sxs-lookup"><span data-stu-id="9cee8-129">This option creates the same chart as the cluster diagram, but instead lists the characteristics of the current cluster that most strongly distinguish it from other clusters.</span></span>  
  
     <span data-ttu-id="9cee8-130">Vous pouvez passer à un autre type de graphique une fois que l'Assistant a créé le diagramme. Pour cela, cliquez avec le bouton droit sur un cluster et sélectionnez un nouveau type de graphique.</span><span class="sxs-lookup"><span data-stu-id="9cee8-130">You can switch to another chart type after the wizard has built the diagram, by right-clicking a cluster and selecting a new chart type.</span></span> <span data-ttu-id="9cee8-131">Pour le moment, choisissez l’option **afficher les clusters avec le graphique des caractéristiques**.</span><span class="sxs-lookup"><span data-stu-id="9cee8-131">For now, choose the option, **Show clusters with characteristics chart**.</span></span>  
  
7.  <span data-ttu-id="9cee8-132">Laissez l’option, **nombre de lignes dans le graphique**, en tant que 5.</span><span class="sxs-lookup"><span data-stu-id="9cee8-132">Leave the option, **Number of rows in the chart**, as 5.</span></span>  
  
     <span data-ttu-id="9cee8-133">Cette option ne change pas le nombre de clusters dans le modèle ; Il limite simplement le nombre d’attributs pouvant être affichés en tant que fonctionnalités de chaque cluster.</span><span class="sxs-lookup"><span data-stu-id="9cee8-133">This option doesn't change the number of clusters in the model; it simply limits the number of attributes that can be displayed as features of each cluster.</span></span>  
  
     <span data-ttu-id="9cee8-134">Toutefois, l’option agit comme un filtre sur les données du graphique. vous ne pouvez donc pas augmenter le nombre d’éléments ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="9cee8-134">However, the option acts as a filter on the chart data, so you can't increase the number of items later.</span></span>  
  
8.  <span data-ttu-id="9cee8-135">Cliquez sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="9cee8-135">Click **Advanced**.</span></span>  
  
     <span data-ttu-id="9cee8-136">La boîte de dialogue **options de cluster** vous permet de personnaliser l’apparence visuelle des formes utilisées dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="9cee8-136">The **Cluster Options** dialog box is where you customize the visual appearance of shapes used in the diagram.</span></span> <span data-ttu-id="9cee8-137">Vous pouvez modifier les couleurs utilisées dans le graphique et la forme utilisée pour les clusters.</span><span class="sxs-lookup"><span data-stu-id="9cee8-137">You can change the colors used in the graph, and the shape used for clusters.</span></span>  
  
     <span data-ttu-id="9cee8-138">Le contrôle de **variable d’ombrage** ne fonctionne pas dans Office 2013.</span><span class="sxs-lookup"><span data-stu-id="9cee8-138">The **Shading Variable** control does not work in Office 2013.</span></span>  
  
     <span data-ttu-id="9cee8-139">![cliquez Avancées pour choisir les couleurs des formes](media/dm13-visio-clusteroptions-advanced.gif "cliquez Avancées pour choisir les couleurs des formes")</span><span class="sxs-lookup"><span data-stu-id="9cee8-139">![click Advanced to choose shape colors](media/dm13-visio-clusteroptions-advanced.gif "click Advanced to choose shape colors")</span></span>  
  
     <span data-ttu-id="9cee8-140">**Conseil :** Certaines couleurs peuvent être modifiées ultérieurement à l’aide des thèmes Visio et des contrôles d’édition de forme.</span><span class="sxs-lookup"><span data-stu-id="9cee8-140">**Tip:** Some colors can be altered later by using Visio themes and shape editing controls.</span></span> <span data-ttu-id="9cee8-141">Toutefois, les thèmes Visio remplaceront également certaines de ces sélections de couleurs ; par conséquent, nous recommandons de commencer par les couleurs par défaut et d'appliquer les modifications progressivement.</span><span class="sxs-lookup"><span data-stu-id="9cee8-141">However, Visio themes will also override some of these color selections, so we recommend starting with the default colors and gradually applying changes.</span></span>  
  
9. <span data-ttu-id="9cee8-142">Cliquez sur **Terminer** pour créer le graphique.</span><span class="sxs-lookup"><span data-stu-id="9cee8-142">Click **Finish** to create the graph.</span></span>  
  
     <span data-ttu-id="9cee8-143">L'Assistant récupère les informations du modèle d'exploration de données, génère un rendu des formes et remplit chaque cluster avec des attributs et des valeurs.</span><span class="sxs-lookup"><span data-stu-id="9cee8-143">The wizard retrieves information from the data mining model, renders the shapes, and populates each cluster with attributes and values.</span></span>  
  
     <span data-ttu-id="9cee8-144">![un réseau de dépendances](media/dm13-visiodepnet-defaultgraph.gif "un réseau de dépendances")</span><span class="sxs-lookup"><span data-stu-id="9cee8-144">![a dependency network](media/dm13-visiodepnet-defaultgraph.gif "a dependency network")</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="9cee8-145">Explorer et modifier le diagramme terminé</span><span class="sxs-lookup"><span data-stu-id="9cee8-145">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="9cee8-146">Une fois le diagramme terminé, vous pouvez continuer à personnaliser son apparence avec les contrôles Visio, comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="9cee8-146">After the diagram is complete, you can continue to customize the appearance using the Visio controls, as shown in the following example.</span></span>  
  
 <span data-ttu-id="9cee8-147">![diagramme de cluster personnalisé avec Visio](media/dm13-visio-clustercomplete1.gif "diagramme de cluster personnalisé avec Visio")</span><span class="sxs-lookup"><span data-stu-id="9cee8-147">![cluster diagram customized using Visio](media/dm13-visio-clustercomplete1.gif "cluster diagram customized using Visio")</span></span>  
  
 <span data-ttu-id="9cee8-148">Toutes les formes de cluster de base sont générées par l'Assistant ; utilisez les outils suivants pour mettre à jour et personnaliser le diagramme :</span><span class="sxs-lookup"><span data-stu-id="9cee8-148">All of the basic cluster shapes are generated by the wizard; use the following tools to update and personalize the diagram:</span></span>  
  
1.  <span data-ttu-id="9cee8-149">Faites glisser le curseur dans le contrôle **options de cluster** pour filtrer les relations plus faibles et simplifier le diagramme.</span><span class="sxs-lookup"><span data-stu-id="9cee8-149">Drag the slider in the **Cluster Options** control, to filter out weaker relationships and simplify the diagram.</span></span>  
  
2.  <span data-ttu-id="9cee8-150">Utilisez l’option de **page nouvelle disposition** de Visio pour expérimenter différentes dispositions de cluster.</span><span class="sxs-lookup"><span data-stu-id="9cee8-150">Use the Visio **Re-Layout Page** option to experiment with different cluster layouts.</span></span>  
  
3.  <span data-ttu-id="9cee8-151">Utilisez l’option **connecteurs** sous l’onglet **conception** pour modifier le style de connecteur afin que les lignes ne traversent pas les clusters.</span><span class="sxs-lookup"><span data-stu-id="9cee8-151">Use the **Connectors** option on the **Design** tab to change the connector style to keep lines from crossing over clusters.</span></span>  
  
4.  <span data-ttu-id="9cee8-152">Cliquez sur le ruban **compléments** , puis affichez l’une des barres d’outils personnalisées utilisées pour travailler avec les diagrammes d’exploration de données :</span><span class="sxs-lookup"><span data-stu-id="9cee8-152">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="9cee8-153">**Disposition**</span><span class="sxs-lookup"><span data-stu-id="9cee8-153">**Layout**</span></span>  
     <span data-ttu-id="9cee8-154">Optimise la disposition des clusters pour qu'ils tiennent sur la page active.</span><span class="sxs-lookup"><span data-stu-id="9cee8-154">Optimizes the arrangement of clusters to fit in the current page.</span></span>  
  
     <span data-ttu-id="9cee8-155">**Redimensionner la page**</span><span class="sxs-lookup"><span data-stu-id="9cee8-155">**Resize Page**</span></span>  
     <span data-ttu-id="9cee8-156">Ce contrôle a été conçu pour les versions HTML antérieures.</span><span class="sxs-lookup"><span data-stu-id="9cee8-156">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="9cee8-157">Utilisez plutôt les contrôles de redimensionnement de page Visio.</span><span class="sxs-lookup"><span data-stu-id="9cee8-157">Use the Visio page resizing controls instead.</span></span>  
  
     <span data-ttu-id="9cee8-158">**Description**</span><span class="sxs-lookup"><span data-stu-id="9cee8-158">**Description**</span></span>  
     <span data-ttu-id="9cee8-159">Si un cluster est sélectionné, cliquez sur cette option pour afficher des détails sur le cluster.</span><span class="sxs-lookup"><span data-stu-id="9cee8-159">If a cluster is selected, click this option to display details about the cluster.</span></span>  
  
     <span data-ttu-id="9cee8-160">![cliquez sur Description pour obtenir des informations sur le cluster](media/dm13-visio-cluster-description-control.gif "cliquez sur Description pour obtenir des informations sur le cluster")</span><span class="sxs-lookup"><span data-stu-id="9cee8-160">![click Description to get details about the cluster](media/dm13-visio-cluster-description-control.gif "click Description to get details about the cluster")</span></span>  
  
     <span data-ttu-id="9cee8-161">**Résistance du bord**</span><span class="sxs-lookup"><span data-stu-id="9cee8-161">**Edge Strength**</span></span>  
     <span data-ttu-id="9cee8-162">Affiche les scores de confiance sur les lignes reliant les clusters.</span><span class="sxs-lookup"><span data-stu-id="9cee8-162">Displays confidence scores on the lines connecting clusters.</span></span>  
  
     <span data-ttu-id="9cee8-163">Cependant, si vous appliquez une mise en forme spéciale autre que la valeur par défaut générée par l'Assistant, y compris certains arrière-plans, ces valeurs peuvent ne pas être visibles.</span><span class="sxs-lookup"><span data-stu-id="9cee8-163">However, if you apply any special formatting other than the default generated by the wizard, including some backgrounds, these numbers might not be visible.</span></span>  
  
     <span data-ttu-id="9cee8-164">**Curseur**</span><span class="sxs-lookup"><span data-stu-id="9cee8-164">**Slider**</span></span>  
     <span data-ttu-id="9cee8-165">Filtre les lignes entre les clusters.</span><span class="sxs-lookup"><span data-stu-id="9cee8-165">Filters the lines between clusters.</span></span> <span data-ttu-id="9cee8-166">Le fait de déplacer le curseur vers le haut supprime toutes les associations, sauf les plus importantes.</span><span class="sxs-lookup"><span data-stu-id="9cee8-166">Moving the slider up removes all but the most important associations.</span></span>  
  
     <span data-ttu-id="9cee8-167">**Ombrage**</span><span class="sxs-lookup"><span data-stu-id="9cee8-167">**Shading**</span></span>  
     <span data-ttu-id="9cee8-168">Ce contrôle ne fonctionne pas dans Office 2013.</span><span class="sxs-lookup"><span data-stu-id="9cee8-168">This control does not work in Office 2013.</span></span>  
  
5.  <span data-ttu-id="9cee8-169">Utilisez le contrôle **panoramique et zoom** , dans la zone **volet de tâches** du ruban **affichage** Visio, pour vous concentrer sur un ensemble de clusters et vous déplacer dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="9cee8-169">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a set of clusters and move around the diagram.</span></span>  
  
6.  <span data-ttu-id="9cee8-170">Cliquez avec le bouton droit sur un cluster pour afficher les options spécifiques à la forme du cluster :</span><span class="sxs-lookup"><span data-stu-id="9cee8-170">Right-click any cluster to see options specific to the cluster shape:</span></span>  
  
    -   <span data-ttu-id="9cee8-171">Modifiez le style du graphique.</span><span class="sxs-lookup"><span data-stu-id="9cee8-171">Change the chart style.</span></span>  
  
    -   <span data-ttu-id="9cee8-172">Ajoutez un graphique des caractéristiques du cluster.</span><span class="sxs-lookup"><span data-stu-id="9cee8-172">Add a cluster characteristics chart.</span></span>  
  
    -   <span data-ttu-id="9cee8-173">Ajoutez un graphique de discrimination de cluster.</span><span class="sxs-lookup"><span data-stu-id="9cee8-173">Add a cluster discrimination chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cee8-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9cee8-174">See Also</span></span>  
 [<span data-ttu-id="9cee8-175">Dépannage des diagrammes d’exploration de données Visio &#40;SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="9cee8-175">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
