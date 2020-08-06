---
title: Onglet réseau de dépendances (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.dependencynetwork.f1
ms.assetid: e58ce1b7-20d6-42cb-ade5-916da8471e09
author: minewiskan
ms.author: owend
ms.openlocfilehash: 94ce82524445ffb8999c671c736087362ef0adfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696295"
---
# <a name="dependency-network-tab-mining-model-viewer"></a><span data-ttu-id="9bd30-102">Onglet Réseau de dépendances (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="9bd30-102">Dependency Network Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="9bd30-103">L'onglet **Réseau de dépendances** affiche sous forme graphique tous les attributs contenus dans le modèle d'exploration de données et illustre les relations qu'il existe entre eux.</span><span class="sxs-lookup"><span data-stu-id="9bd30-103">The **Dependency Net** tab provides a graphical view of all attributes that the mining model contains, and shows how the attributes are related.</span></span>  
  
 <span data-ttu-id="9bd30-104">L'onglet **Réseau de dépendances**  est utilisé pour plusieurs types de modèles d'exploration de données, y compris les modèles Naïve Bayes, les modèles d'arbre de décision et les modèles d'association.</span><span class="sxs-lookup"><span data-stu-id="9bd30-104">The **Dependency Net**  tab is used for several types of mining models, including Naïve Bayes models, decision tree models, and association models.</span></span> <span data-ttu-id="9bd30-105">Pour plus d'informations sur la manière d'interpréter le contenu de l'onglet **Réseau de dépendances**  dans le contexte de ces modèles, consultez les liens suivants :</span><span class="sxs-lookup"><span data-stu-id="9bd30-105">For more information about how to interpret the contents of the **Dependency Net**  tab in the context of these models, see the following links:</span></span>  
  
 [<span data-ttu-id="9bd30-106">Explorer un modèle à l'aide de la visionneuse d'arborescences Microsoft</span><span class="sxs-lookup"><span data-stu-id="9bd30-106">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
 [<span data-ttu-id="9bd30-107">Explorer un modèle à l'aide de la visionneuse de l'algorithme MNB (Microsoft Naive Bayes)</span><span class="sxs-lookup"><span data-stu-id="9bd30-107">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)  
  
 [<span data-ttu-id="9bd30-108">Explorer un modèle à l'aide de la visionneuse de l'algorithme MAR (Microsoft Association Rules)</span><span class="sxs-lookup"><span data-stu-id="9bd30-108">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)  
  
## <a name="options"></a><span data-ttu-id="9bd30-109">Options</span><span class="sxs-lookup"><span data-stu-id="9bd30-109">Options</span></span>  
 <span data-ttu-id="9bd30-110">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="9bd30-110">**Refresh viewer content**</span></span>  
 <span data-ttu-id="9bd30-111">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="9bd30-111">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="9bd30-112">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="9bd30-112">**Mining Model**</span></span>  
 <span data-ttu-id="9bd30-113">Choisissez un modèle d'exploration de données à afficher, parmi ceux de la structure d'exploration de données active.</span><span class="sxs-lookup"><span data-stu-id="9bd30-113">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="9bd30-114">Le modèle d'exploration de données s'ouvre dans une visionneuse personnalisée.</span><span class="sxs-lookup"><span data-stu-id="9bd30-114">The mining model will open in a custom viewer.</span></span> <span data-ttu-id="9bd30-115">Le type de visionneuse personnalisée qui est utilisée pour chaque modèle est déterminé par l'algorithme que vous avez utilisé pour créer le modèle.</span><span class="sxs-lookup"><span data-stu-id="9bd30-115">The type of custom viewer that is used for each model is determined by the algorithm that you used to create the model.</span></span>  
  
 <span data-ttu-id="9bd30-116">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="9bd30-116">**Viewer**</span></span>  
 <span data-ttu-id="9bd30-117">Choisissez la visionneuse à utiliser pour explorer le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9bd30-117">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="9bd30-118">Pour chaque modèle, vous pouvez utiliser la visionneuse personnalisée fournie pour chaque modèle d'exploration de données ou la visionneuse de contenu d'exploration de données ( [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer).</span><span class="sxs-lookup"><span data-stu-id="9bd30-118">For each model, you can use either the custom viewer is provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="9bd30-119">Vous pouvez également utiliser les visionneuses de plug-in, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="9bd30-119">You can also use plug-in viewers if available.</span></span> <span data-ttu-id="9bd30-120">La visionneuse de l'arborescence de contenu Microsoft peut être utilisée avec tous les modèles, et représente le contenu du modèle dans une table HTML.</span><span class="sxs-lookup"><span data-stu-id="9bd30-120">The Microsoft Content Tree Viewer can be used with all models, and represents the model content in an HTML table.</span></span>  
  
 <span data-ttu-id="9bd30-121">**Zoom avant**</span><span class="sxs-lookup"><span data-stu-id="9bd30-121">**Zoom In**</span></span>  
 <span data-ttu-id="9bd30-122">Permet d'effectuer un zoom avant sur le schéma afin que vous puissiez voir les attributs plus en détail.</span><span class="sxs-lookup"><span data-stu-id="9bd30-122">Zoom in to the diagram, so that you can see the attributes in more detail.</span></span>  
  
 <span data-ttu-id="9bd30-123">**Zoom arrière**</span><span class="sxs-lookup"><span data-stu-id="9bd30-123">**Zoom Out**</span></span>  
 <span data-ttu-id="9bd30-124">Permet d'effectuer un zoom arrière sur le schéma, afin que vous puissiez voir plus d'attributs et les liens entre eux.</span><span class="sxs-lookup"><span data-stu-id="9bd30-124">Zoom out from the diagram, so that you can see more attributes and the links between them.</span></span>  
  
 <span data-ttu-id="9bd30-125">**Copier la vue du graphique**</span><span class="sxs-lookup"><span data-stu-id="9bd30-125">**Copy Graph View**</span></span>  
 <span data-ttu-id="9bd30-126">Copie la partie visible du diagramme dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="9bd30-126">Copy the visible section of the diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="9bd30-127">**Copier le graphique entier**</span><span class="sxs-lookup"><span data-stu-id="9bd30-127">**Copy Entire Graph**</span></span>  
 <span data-ttu-id="9bd30-128">Copie la totalité du diagramme dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="9bd30-128">Copy the complete diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="9bd30-129">**Liens**</span><span class="sxs-lookup"><span data-stu-id="9bd30-129">**Links**</span></span>  
 <span data-ttu-id="9bd30-130">Ajustez le nombre de liens (arêtes) et de nœuds affichés par la visionneuse en déplaçant le curseur à droite des attributs.</span><span class="sxs-lookup"><span data-stu-id="9bd30-130">Adjust how many links (edges) and nodes the viewer shows by adjusting the slider to the right of the attributes.</span></span> <span data-ttu-id="9bd30-131">Faites glisser la barre de curseur vers le bas pour augmenter la valeur de seuil, afin que seuls les liens les plus forts soient affichés.</span><span class="sxs-lookup"><span data-stu-id="9bd30-131">Dragging the slider bar down increases the threshold value, so that only the strongest links are shown.</span></span> <span data-ttu-id="9bd30-132">Pour chaque type de modèle, une valeur légèrement différente est utilisée pour représenter les liens dans le graphique :</span><span class="sxs-lookup"><span data-stu-id="9bd30-132">For each model type, a slightly different value is used to represent the links in the graph:</span></span>  
  
-   <span data-ttu-id="9bd30-133">Dans un modèle d' **arbre de décision** , les arêtes représentent la force prédictive de la connexion, déterminée en partie par le score de fractionnement.</span><span class="sxs-lookup"><span data-stu-id="9bd30-133">In a **decision tree** model, the edges represent the predictive strength of the connection, determined partly by the split score.</span></span>  
  
-   <span data-ttu-id="9bd30-134">Dans un modèle **Naïve Bayes** , les liens entre deux nœuds peuvent s'appliquer dans l'une ou l'autre direction : autrement dit, le nœud A peut prédire le nœud B, et inversement.</span><span class="sxs-lookup"><span data-stu-id="9bd30-134">In a **Naïve Bayes** model, the links between two nodes can go either way: that is, node A can predict the node B, and vice versa.</span></span> <span data-ttu-id="9bd30-135">Le score associé à l'arête représente la force prédictive de la connexion.</span><span class="sxs-lookup"><span data-stu-id="9bd30-135">The score associated with the edge represents the predictive strength of the connection.</span></span>  
  
-   <span data-ttu-id="9bd30-136">Dans un **modèle d'association**, les arêtes entre les nœuds représentent le score d'importance de la règle qui connecte deux jeux d'éléments.</span><span class="sxs-lookup"><span data-stu-id="9bd30-136">In an **association model**, the edges between nodes represent the importance score of the rule that connects two itemsets.</span></span>  
  
 <span data-ttu-id="9bd30-137">Règle générale pour tous les types de modèle : plus le lien est fort, plus la relation prédictive entre les deux attributs est forte.</span><span class="sxs-lookup"><span data-stu-id="9bd30-137">A general rule for all model types is that the stronger the link, the stronger the predictive relationship between the two attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd30-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9bd30-138">See Also</span></span>  
 <span data-ttu-id="9bd30-139">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="9bd30-139">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="9bd30-140">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9bd30-140">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="9bd30-141">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="9bd30-141">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
