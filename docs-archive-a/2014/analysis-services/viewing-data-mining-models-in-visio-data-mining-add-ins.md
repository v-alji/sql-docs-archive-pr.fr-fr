---
title: Affichage des modèles d’exploration de données dans Visio (compléments d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- diagram, modifying
- templates [Visio]
- shapes, data mining
- diagram
ms.assetid: 5841adea-6650-4fae-8526-26af33edbede
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3c1e63c058295b93e2562c64a6df90a30273a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603645"
---
# <a name="viewing-data-mining-models-in-visio-data-mining-add-ins"></a><span data-ttu-id="446ca-102">Affichage de modèles d'exploration de données dans Visio (Compléments d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="446ca-102">Viewing Data Mining Models in Visio (Data Mining Add-ins)</span></span>
  <span data-ttu-id="446ca-103">Les formes Visio pour l'exploration de données vous permettent de vous connecter à un serveur et de créer un diagramme représentant un modèle d'exploration de données existant.</span><span class="sxs-lookup"><span data-stu-id="446ca-103">The Visio shapes for data mining let you connect to a server and create a diagram representing an existing data mining model.</span></span> <span data-ttu-id="446ca-104">Les diagrammes peuvent alors être personnalisés à l'aide de contrôles Visio, mais vous pouvez également explorer plus en détail les données, exposer une partie des statistiques sous-jacentes et utiliser le modèle sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="446ca-104">The diagrams can then be customized using Visio controls, but you can also drill down into data, expose some of the underlying statistics, and work with the underlying model.</span></span>  
  
## <a name="building-a-model-diagram"></a><span data-ttu-id="446ca-105">Génération d'un diagramme de modèle</span><span class="sxs-lookup"><span data-stu-id="446ca-105">Building a Model Diagram</span></span>  
 <span data-ttu-id="446ca-106">Lorsque vous ouvrez le fichier contenant les formes Visio pour l’exploration de données, le volet **formes** affiche les formes suivantes.</span><span class="sxs-lookup"><span data-stu-id="446ca-106">When you open the file containing the Visio shapes for data mining, the **Shapes** pane shows the following shapes.</span></span>  
  
 <span data-ttu-id="446ca-107">Si vous ne voyez pas les formes d'exploration de données en ouvrant Visio, ouvrez le fichier modèle dans le dossier d'installation.</span><span class="sxs-lookup"><span data-stu-id="446ca-107">If you do not see the data mining shapes when you open Visio, open the template file from the installation folder.</span></span>  
  
 <span data-ttu-id="446ca-108">![DM](media/dm-stencil.gif "DM")</span><span class="sxs-lookup"><span data-stu-id="446ca-108">![DM](media/dm-stencil.gif "DM")</span></span>  
  
 <span data-ttu-id="446ca-109">Pour utiliser une forme, faites-la glisser vers la page.</span><span class="sxs-lookup"><span data-stu-id="446ca-109">To use a shape, drag it to the page.</span></span> <span data-ttu-id="446ca-110">Chaque forme ouvre un Assistant différent qui vous permet de sélectionner des données sources, de définir des options pour le type de graphique spécifique et de spécifier l'ombrage et d'autres options d'affichage.</span><span class="sxs-lookup"><span data-stu-id="446ca-110">Each of the shapes opens a different wizard, which helps you select source data, set options for the specific diagram type, and specify shading and other display options.</span></span>  
  
 <span data-ttu-id="446ca-111">Le tableau ci-dessous répertorie les types de modèles qu'il est possible d'utiliser avec chaque type de diagramme.</span><span class="sxs-lookup"><span data-stu-id="446ca-111">The following table lists the types of models that you can use with each type of diagram.</span></span>  
  
|<span data-ttu-id="446ca-112">Forme Visio</span><span class="sxs-lookup"><span data-stu-id="446ca-112">Visio shape</span></span>|<span data-ttu-id="446ca-113">Modèles pris en charge</span><span class="sxs-lookup"><span data-stu-id="446ca-113">Supported models</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="446ca-114">Arbre de décision</span><span class="sxs-lookup"><span data-stu-id="446ca-114">Decision Tree</span></span>|<span data-ttu-id="446ca-115">Utilisez cette forme pour les modèles basés sur les algorithmes d'arbre de décision ou de régression linéaire.</span><span class="sxs-lookup"><span data-stu-id="446ca-115">Use this shape for models based on the decision tree or linear regression algorithms.</span></span>|  
|<span data-ttu-id="446ca-116">Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="446ca-116">Dependency Network</span></span>|<span data-ttu-id="446ca-117">Utilisez cette forme pour les modèles basés sur l'un des algorithmes suivants : Naive Bayes, Decision Trees ou Association Rules.</span><span class="sxs-lookup"><span data-stu-id="446ca-117">Use this shape for models based on any of the following algorithms: Naive Bayes, Decision Trees, or Association Rules.</span></span>|  
|<span data-ttu-id="446ca-118">Cluster</span><span class="sxs-lookup"><span data-stu-id="446ca-118">Cluster</span></span>|<span data-ttu-id="446ca-119">Utilisez cette forme pour les modèles basés sur les algorithmes de clustering.</span><span class="sxs-lookup"><span data-stu-id="446ca-119">Use this shape for models based on clustering algorithms.</span></span>|  
  
 <span data-ttu-id="446ca-120">Selon le type de données figurant dans votre modèle d'exploration de données, l'Assistant peut proposer des options différentes.</span><span class="sxs-lookup"><span data-stu-id="446ca-120">Depending on the type of data in your mining model, the wizard may offer different options.</span></span> <span data-ttu-id="446ca-121">Par exemple, les colonnes qui contiennent des nombres continus sont visualisées différemment des variables catégorielles.</span><span class="sxs-lookup"><span data-stu-id="446ca-121">For example, columns that contain continuous numbers are visualized differently than categorical variables.</span></span>  
  
## <a name="working-with-completed-shapes"></a><span data-ttu-id="446ca-122">Utilisation des formes achevées</span><span class="sxs-lookup"><span data-stu-id="446ca-122">Working with Completed Shapes</span></span>  
 <span data-ttu-id="446ca-123">Une fois le diagramme terminé, utilisez-le pour parcourir le modèle d'exploration de données ou améliorez-le pour l'utiliser dans des présentations.</span><span class="sxs-lookup"><span data-stu-id="446ca-123">After the diagram is complete, you can use it to browse the data mining model or enhance the diagram for use in presentations.</span></span>  
  
### <a name="visio-menus"></a><span data-ttu-id="446ca-124">Menus Visio</span><span class="sxs-lookup"><span data-stu-id="446ca-124">Visio Menus</span></span>  
 <span data-ttu-id="446ca-125">Visio fournit une variété de contrôles de rendu, de thèmes et de menus contextuels pour vous aider à améliorer un diagramme.</span><span class="sxs-lookup"><span data-stu-id="446ca-125">Visio provides a variety of rendering controls, themes, and shortcut menus to help enhance a diagram.</span></span>  
  
-   <span data-ttu-id="446ca-126">Utilisez les thèmes Visio pour modifier les couleurs d'un diagramme.</span><span class="sxs-lookup"><span data-stu-id="446ca-126">Use Visio themes to alter diagram colors.</span></span>  
  
-   <span data-ttu-id="446ca-127">Modifiez les connecteurs ou la disposition du diagramme.</span><span class="sxs-lookup"><span data-stu-id="446ca-127">Change connectors or diagram layout.</span></span>  
  
### <a name="data-mining-menus"></a><span data-ttu-id="446ca-128">Menus d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="446ca-128">Data Mining Menus</span></span>  
 <span data-ttu-id="446ca-129">Ces barres d'outils et éléments de menu sont fournis par les compléments qui sont spécifiques à chaque forme ou type de modèle</span><span class="sxs-lookup"><span data-stu-id="446ca-129">These toolbars and menu items are provided by the add-ins that are specific to each shape or model type</span></span>  
  
-   <span data-ttu-id="446ca-130">Chaque type de diagramme possède un menu contextuel pour la forme qui vous permet d'accéder aux options spéciales.</span><span class="sxs-lookup"><span data-stu-id="446ca-130">Each diagram type has a shortcut menu for the shape that lets you access special options.</span></span> <span data-ttu-id="446ca-131">Même si la plupart des options de ce menu sont communes à toutes les formes Visio, certaines sont spécifiques aux modèles d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="446ca-131">Although many options in this menu are common to all Visio shapes, some options are unique to the data mining templates</span></span>  
  
     <span data-ttu-id="446ca-132">Par exemple, dans un diagramme Arbre de décision, vous pouvez cliquer sur un nœud individuel puis réduire les nœuds enfants pour simplifier le diagramme ou déplacer les nœuds enfants vers une page séparée.</span><span class="sxs-lookup"><span data-stu-id="446ca-132">For example, in a decision tree diagram, you can click an individual node and then collapse the child nodes to make the diagram simpler, or move child nodes to a separate page.</span></span>  
  
-   <span data-ttu-id="446ca-133">Dans la mesure où la forme est liée aux données de modèle, vous pouvez également procéder à une exploration à l'aide du diagramme :</span><span class="sxs-lookup"><span data-stu-id="446ca-133">Because the shape is bound to the model data, you can also do some amount of exploration using the diagram:</span></span>  
  
     <span data-ttu-id="446ca-134">Filtrer les nœuds affichés, ou modifier le niveau de l'arbre ou la profondeur du graphique.</span><span class="sxs-lookup"><span data-stu-id="446ca-134">Filter the nodes that are displayed, or change the level of the tree or depth of the graph.</span></span>  
  
     <span data-ttu-id="446ca-135">Effectuer un zoom avant sur des sections spécifiques, rechercher les nœuds qui contiennent un attribut, ou filtrer un graphique de dépendances par ses bords (probabilité).</span><span class="sxs-lookup"><span data-stu-id="446ca-135">Zoom in on specific sections, search for nodes that contain a certain attribute, or filter a dependency graph by its edges (probability).</span></span>  
  
## <a name="walkthroughs"></a><span data-ttu-id="446ca-136">Procédures pas à pas</span><span class="sxs-lookup"><span data-stu-id="446ca-136">Walkthroughs</span></span>  
 <span data-ttu-id="446ca-137">Pour obtenir des exemples d'utilisation et d'interprétation d'un diagramme fini, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="446ca-137">For examples of how to work with and interpret a completed diagram, see these topics:</span></span>  
  
 [<span data-ttu-id="446ca-138">Procédure pas à pas Diagramme de cluster</span><span class="sxs-lookup"><span data-stu-id="446ca-138">Cluster Diagram Walkthrough</span></span>](cluster-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="446ca-139">Procédure pas à pas Diagramme de réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="446ca-139">Dependency Net Diagram Walkthrough</span></span>](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="446ca-140">Procédure pas à pas Diagramme d'arbre de décision</span><span class="sxs-lookup"><span data-stu-id="446ca-140">Decision Tree Diagram Walkthrough</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
## <a name="see-also"></a><span data-ttu-id="446ca-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="446ca-141">See Also</span></span>  
 [<span data-ttu-id="446ca-142">Exploration des modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="446ca-142">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
