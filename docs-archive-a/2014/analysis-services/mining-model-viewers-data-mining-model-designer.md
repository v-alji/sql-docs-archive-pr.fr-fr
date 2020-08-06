---
title: Visionneuses de modèles d’exploration de données (Concepteur de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.viewers.f1
ms.assetid: 4ba391d5-c97b-4848-ba7c-7d096fa4b7dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4cc1c9d72a08ef49ed2f4f466953d2ba61394178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707952"
---
# <a name="mining-model-viewers-data-mining-model-designer"></a><span data-ttu-id="3d009-102">Visionneuses de modèle d'exploration de données (Concepteur de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="3d009-102">Mining Model Viewers (Data Mining Model Designer)</span></span>
  <span data-ttu-id="3d009-103">Utilisez l’onglet **Visionneuse de modèle d’exploration de données** pour explorer les modèles d’exploration de données d’une structure associée.</span><span class="sxs-lookup"><span data-stu-id="3d009-103">Use the **Mining Model Viewer** tab to explore the mining models that a mining structure contains.</span></span>

 <span data-ttu-id="3d009-104">Vous devez sélectionner le modèle d'exploration de données, puis sélectionner une visionneuse.</span><span class="sxs-lookup"><span data-stu-id="3d009-104">First you select the mining model and then you select a viewer.</span></span> <span data-ttu-id="3d009-105">Chaque modèle comporte toujours deux visionneuses disponibles : une visionneuse personnalisée, qui peut inclure plusieurs onglets, et la visionneuse générique.</span><span class="sxs-lookup"><span data-stu-id="3d009-105">Each model always has two viewers available: a custom viewer, which can include multiple tabs, and the generic viewer.</span></span>

 <span data-ttu-id="3d009-106">Pour connaître la procédure pas à pas d’utilisation de chaque visionneuse, consultez [Visionneuses de modèle d’exploration de données](data-mining/data-mining-model-viewers.md).</span><span class="sxs-lookup"><span data-stu-id="3d009-106">For a walkthrough of how to use each viewer, see [Data Mining Model Viewers](data-mining/data-mining-model-viewers.md).</span></span>

## <a name="common-options"></a><span data-ttu-id="3d009-107">Options courantes</span><span class="sxs-lookup"><span data-stu-id="3d009-107">Common Options</span></span>
 <span data-ttu-id="3d009-108">**Actualiser le contenu de l'observateur** Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="3d009-108">**Refresh viewer content** Reload the mining model in the viewer.</span></span>

 <span data-ttu-id="3d009-109">**Modèle d'exploration de données** Choisissez un modèle d'exploration de données pour afficher le contenu de la structure d'exploration actuelle.</span><span class="sxs-lookup"><span data-stu-id="3d009-109">**Mining Model** Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="3d009-110">Le modèle d'exploration de données s'ouvre tout d'abord dans sa visionneuse personnalisée associée.</span><span class="sxs-lookup"><span data-stu-id="3d009-110">The mining model will first open in its associated custom viewer.</span></span>

 <span data-ttu-id="3d009-111">**Visionneuse** Choisissez la visionneuse à utiliser pour explorer le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3d009-111">**Viewer** Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="3d009-112">Cette liste inclut les visionneuses [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] fournies par pour chaque modèle d’exploration de données, la [!INCLUDE[msCoName](../includes/msconame-md.md)] visionneuse de contenu d’exploration de données et les visionneuses de plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d009-112">This list includes the viewers that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides for each mining model, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer, and any plug-in viewers.</span></span>

 <span data-ttu-id="3d009-113">Le diagramme suivant représente une visionneuse personnalisée et la visionneuse générique pour le même modèle.</span><span class="sxs-lookup"><span data-stu-id="3d009-113">The following diagram shows a custom viewer and the generic viewer for the same model.</span></span>

-   <span data-ttu-id="3d009-114">Le diagramme supérieur affiche la visionneuse pour un modèle d'exploration de données basé sur l'algorithme MTS (Microsoft Time Series).</span><span class="sxs-lookup"><span data-stu-id="3d009-114">The upper diagram shows the viewer for a mining model based on the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="3d009-115">Cette visionneuse personnalisée particulière crée automatiquement un graphique de la série chronologique et fournit cinq prédictions.</span><span class="sxs-lookup"><span data-stu-id="3d009-115">This particular custom viewer automatically creates a graph of the time series and provides five predictions.</span></span>

-   <span data-ttu-id="3d009-116">Le diagramme inférieur représente le même modèle affiché avec la **visionneuse de l’arborescence de contenu générique Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="3d009-116">The lower diagram shows the same model displayed using the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="3d009-117">Cette visionneuse présente le contenu du modèle d'exploration de données selon un schéma standardisé.</span><span class="sxs-lookup"><span data-stu-id="3d009-117">This viewer presents the contents of the mining model according to a standardized schema.</span></span> <span data-ttu-id="3d009-118">Pour plus d’informations, consultez [Visionneuse de l’arborescence de contenu générique Microsoft &#40;exploration de données&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3d009-118">For more information, see [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span></span>

 <span data-ttu-id="3d009-119">![Vue d'ensemble d'un concepteur de modèle d'exploration de données](media/generic-mining-model-tab1.gif "Vue d'ensemble d'un concepteur de modèle d'exploration de données")</span><span class="sxs-lookup"><span data-stu-id="3d009-119">![Overview of mining model designer](media/generic-mining-model-tab1.gif "Overview of mining model designer")</span></span>

## <a name="viewers-and-their-components"></a><span data-ttu-id="3d009-120">Visionneuses et leurs composants</span><span class="sxs-lookup"><span data-stu-id="3d009-120">Viewers and Their Components</span></span>
 <span data-ttu-id="3d009-121">Selon le modèle que vous sélectionnez, vous verrez une visionneuse personnalisée différente, adaptée à l'algorithme que vous avez utilisé pour créer le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3d009-121">Depending on the model that you select, you will see a different custom viewer, tailored to the algorithm that you used to create the selected data mining model.</span></span> <span data-ttu-id="3d009-122">Chaque visionneuse personnalisée comporte divers outils et boîtes de dialogue qui vous permettent d'explorer les statistiques et les modèles dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="3d009-122">Each custom viewer has a variety of tools and dialog boxes for helping you explore the statistics and patterns in the model.</span></span>

 <span data-ttu-id="3d009-123">La liste suivante décrit les options dans chacune des visionneuses personnalisées.</span><span class="sxs-lookup"><span data-stu-id="3d009-123">The following list describes the options in each of the custom viewers.</span></span>

### <a name="microsoft-association-rules-algorithm"></a><span data-ttu-id="3d009-124">Algorithme MAR (Microsoft Association Rules)</span><span class="sxs-lookup"><span data-stu-id="3d009-124">Microsoft Association Rules Algorithm</span></span>

-   [<span data-ttu-id="3d009-125">Explorer un modèle à l'aide de la visionneuse de l'algorithme MAR (Microsoft Association Rules)</span><span class="sxs-lookup"><span data-stu-id="3d009-125">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)

    -   [<span data-ttu-id="3d009-126">Onglet Jeux d’éléments &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-126">Itemsets Tab &#40;Mining Model Viewer&#41;</span></span>](itemsets-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-127">Onglet Règles &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-127">Rules Tab &#40;Mining Model Viewer&#41;</span></span>](rules-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-128">Onglet réseau de dépendances &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-128">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

### <a name="microsoft-clustering-algorithm"></a><span data-ttu-id="3d009-129">Algorithme de clustering Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d009-129">Microsoft Clustering Algorithm</span></span>

-   [<span data-ttu-id="3d009-130">Explorer un modèle à l’aide de Microsoft Sequence Cluster</span><span class="sxs-lookup"><span data-stu-id="3d009-130">Browse a Model Using the Microsoft Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)

    -   [<span data-ttu-id="3d009-131">Onglet diagramme de cluster &#40;visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-131">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-132">Onglet Profils du cluster &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-132">Cluster Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-133">Onglet caractéristiques du cluster &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-133">Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-134">Onglet discrimination de cluster &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-134">Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-135">Boîte de dialogue légende d’exploration de données &#40;visionneuse de modèle d’exploration&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-135">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-decision-tree-algorithm"></a><span data-ttu-id="3d009-136">Algorithme MDT (Microsoft Decision Trees)</span><span class="sxs-lookup"><span data-stu-id="3d009-136">Microsoft Decision Tree Algorithm</span></span>

-   [<span data-ttu-id="3d009-137">Explorer un modèle à l'aide de la visionneuse d'arborescences Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d009-137">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)

    -   [<span data-ttu-id="3d009-138">Onglet arbre de décision &#40;visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-138">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-139">Onglet réseau de dépendances &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-139">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-140">Boîte de dialogue légende d’exploration de données &#40;visionneuse de modèle d’exploration&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-140">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-linear-regression-algorithm"></a><span data-ttu-id="3d009-141">Algorithme MLR (Microsoft Linear Regression)</span><span class="sxs-lookup"><span data-stu-id="3d009-141">Microsoft Linear Regression Algorithm</span></span>

-   [<span data-ttu-id="3d009-142">Explorer un modèle à l'aide de la visionneuse de l'algorithme MNN (Microsoft Neural Network)</span><span class="sxs-lookup"><span data-stu-id="3d009-142">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="3d009-143">Onglet arbre de décision &#40;visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-143">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-144">Onglet réseau de dépendances &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-144">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-145">Boîte de dialogue légende d’exploration de données &#40;visionneuse de modèle d’exploration&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-145">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-logistic-regression-algorithm"></a><span data-ttu-id="3d009-146">Algorithme MLR (Microsoft Logistic Regression)</span><span class="sxs-lookup"><span data-stu-id="3d009-146">Microsoft Logistic Regression Algorithm</span></span>

-   [<span data-ttu-id="3d009-147">Explorer un modèle à l'aide de la visionneuse de l'algorithme MNN (Microsoft Neural Network)</span><span class="sxs-lookup"><span data-stu-id="3d009-147">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

### <a name="microsoft-nave-bayes-algorithm"></a><span data-ttu-id="3d009-148">Algorithme MNB (Microsoft Naïve Bayes)</span><span class="sxs-lookup"><span data-stu-id="3d009-148">Microsoft Naïve Bayes Algorithm</span></span>

-   [<span data-ttu-id="3d009-149">Explorer un modèle à l'aide de la visionneuse de l'algorithme MNB (Microsoft Naive Bayes)</span><span class="sxs-lookup"><span data-stu-id="3d009-149">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)

    -   [<span data-ttu-id="3d009-150">Onglet réseau de dépendances &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-150">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-151">Onglet Profils d’attribut &#40;visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-151">Attribute Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-152">Onglet caractéristiques d’attribut &#40;visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-152">Attribute Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-153">Onglet discrimination d’attribut &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-153">Attribute Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-discrimination-tab-mining-model-viewer.md)

### <a name="microsoft-neural-network-algorithm"></a><span data-ttu-id="3d009-154">Microsoft Neural Network Algorithm</span><span class="sxs-lookup"><span data-stu-id="3d009-154">Microsoft Neural Network Algorithm</span></span>

-   [<span data-ttu-id="3d009-155">Explorer un modèle à l'aide de la visionneuse de l'algorithme MNN (Microsoft Neural Network)</span><span class="sxs-lookup"><span data-stu-id="3d009-155">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="3d009-156">Onglet réseau de dépendances &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-156">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-157">Visionneuse de modèle d’exploration de données &#40;de réseau neuronal&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-157">Neural Network &#40;Mining Model Viewer&#41;</span></span>](neural-network-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-158">Boîte de dialogue Rechercher un nœud &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-158">Find Node Dialog Box &#40;Mining Model Viewer&#41;</span></span>](find-node-dialog-box-mining-model-viewer.md)

### <a name="microsoft-sequence-clustering-algorithm"></a><span data-ttu-id="3d009-159">Algorithme MSC (Microsoft Sequence Clustering)</span><span class="sxs-lookup"><span data-stu-id="3d009-159">Microsoft Sequence Clustering Algorithm</span></span>

-   [<span data-ttu-id="3d009-160">Explorer un modèle à l'aide de la visionneuse de l'algorithme MSC (Microsoft Sequence Cluster)</span><span class="sxs-lookup"><span data-stu-id="3d009-160">Browse a Model Using the Microsoft Sequence Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)

    -   [<span data-ttu-id="3d009-161">Onglet diagramme de cluster de séquence clustering &#40;visionneuse de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="3d009-161">Sequence Clustering Cluster Diagram Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-162">Onglet Profils de cluster de séquence clustering &#40;visionneuse de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="3d009-162">Sequence Clustering Cluster Profiles Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-163">Onglet caractéristiques du cluster Sequence Clustering &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-163">Sequence Clustering Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-164">Onglet discrimination de cluster de séquence clustering &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-164">Sequence Clustering Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="3d009-165">Onglet transition de cluster de séquence clustering &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-165">Sequence Clustering Cluster Transition Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-transition-tab-mining-model-viewer.md)

### <a name="microsoft-time-series-algorithm"></a><span data-ttu-id="3d009-166">Algorithme MTS (Microsoft Time Series)</span><span class="sxs-lookup"><span data-stu-id="3d009-166">Microsoft Time Series Algorithm</span></span>

-   [<span data-ttu-id="3d009-167">Explorer un modèle à l'aide de la visionneuse de l'algorithme MTS (Microsoft Time Series)</span><span class="sxs-lookup"><span data-stu-id="3d009-167">Browse a Model Using the Microsoft Time Series Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)

    -   [<span data-ttu-id="3d009-168">Onglet modèle &#40;visionneuses de modèles d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-168">Model Tab &#40;Mining Model Viewers&#41;</span></span>](model-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="3d009-169">Onglet graphique &#40;visionneuses de modèles d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-169">Chart Tab &#40;Mining Model Viewers&#41;</span></span>](chart-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="3d009-170">Boîte de dialogue légende d’exploration de données &#40;visionneuse de modèle d’exploration&#41;</span><span class="sxs-lookup"><span data-stu-id="3d009-170">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

## <a name="see-also"></a><span data-ttu-id="3d009-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d009-171">See Also</span></span>
 <span data-ttu-id="3d009-172">[Vue modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-models-view-data-mining-model-designer.md) [vue structure d’exploration de données &#40;concepteur de modèle d’exploration de données&#41;](mining-structure-view-data-mining-model-designer.md) [Concepteur graphique](mining-accuracy-chart-designer-data-mining.md) d’analyse de précision de l’exploration de données &#40;&#41;d’exploration de [données](prediction-query-builder-data-mining.md) générateur de requêtes</span><span class="sxs-lookup"><span data-stu-id="3d009-172">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) [Mining Structure View &#40;Data Mining Model Designer&#41;](mining-structure-view-data-mining-model-designer.md) [Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) [Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md)</span></span>


