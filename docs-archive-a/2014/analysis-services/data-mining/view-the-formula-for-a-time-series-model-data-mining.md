---
title: Afficher la formule d’un modèle de série chronologique (exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- ARTXP
- time series algorithms [Analysis Services]
- ARIMA
- time series [Analysis Services]
- Time Series Viewer [Analysis Services]
ms.assetid: 825ef719-2f44-4979-be01-5a81f54e1a53
author: minewiskan
ms.author: owend
ms.openlocfilehash: eff61c469d34f084e6a0eb11c49a1c37c7cc97c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600324"
---
# <a name="view-the-formula-for-a-time-series-model-data-mining"></a><span data-ttu-id="5f0f6-102">Afficher la formule d'un modèle de série chronologique (exploration de données)</span><span class="sxs-lookup"><span data-stu-id="5f0f6-102">View the Formula for a Time Series Model (Data Mining)</span></span>
  <span data-ttu-id="5f0f6-103">Le [!INCLUDE[msCoName](../../includes/msconame-md.md)] Concepteur d’exploration de données de la visionneuse de série chronologique fournit le moyen le plus simple d’afficher les détails de l’équation de régression utilisée dans un modèle de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series viewer inData Mining Designer provides the easiest way to view the details of the regression equation used in a time series model.</span></span>  
  
 <span data-ttu-id="5f0f6-104">Vous pouvez extraire la formule de régression d'un modèle de série chronologique en interrogeant le contenu du modèle.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-104">You can extract the regression formula for a time series model by querying the model content.</span></span> <span data-ttu-id="5f0f6-105">Toutefois, pour afficher la formule complète ARTXP ou ARIMA, nous vous recommandons d’utiliser la **légende d’exploration de données** de la [visionneuse MTS (Microsoft Time Series](browse-a-model-using-the-microsoft-time-series-viewer.md)), qui présente toutes les constantes dans un format lisible.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-105">However, to view the complete ARTXP or ARIMA formula, we recommend that you use the **Mining Legend** of the [Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md), which presents all the constants in a readable format.</span></span>  
  
 <span data-ttu-id="5f0f6-106">Si vous créez un modèle mixte, les analyses ARIMA et ARTXP sont créées dans des arborescences séparées, jointes au nœud racine qui représente le modèle.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-106">If you create a mixed model, the ARIMA and ARTXP analyses are created in separate trees, joined at the root node representing the model.</span></span> <span data-ttu-id="5f0f6-107">Les structures des arbres ARIMA et ARTXP sont très différentes.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-107">The structures of the ARIMA and ARTXP trees are very different.</span></span> <span data-ttu-id="5f0f6-108">Par exemple, l'arbre ARTXP est en fait une arborescence, comme un arbre de décision, alors que l'arbre ARIMA représente une série de moyennes mobiles.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-108">For example, the ARTXP tree is in fact a tree structure, like a decision tree, whereas the ARIMA tree represents a series of moving averages.</span></span> <span data-ttu-id="5f0f6-109">Par conséquent, bien que les deux représentations soient présentées dans un seul modèle pour des raisons de commodité, elles doivent être considérées comme deux modèles indépendants.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-109">Therefore, although the two representations are presented in one model for convenience, they should be treated as two independent models.</span></span> <span data-ttu-id="5f0f6-110">Les équations sont également complètement différentes et ne peuvent pas être associées ou comparées.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-110">The equations are also completely different and cannot be combined or compared.</span></span>  
  
 <span data-ttu-id="5f0f6-111">Vous pouvez également afficher des modèles de série chronologique à l’aide de la [visionneuse de l’arborescence de contenu générique Microsoft](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="5f0f6-111">You can also view time series models by using the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="5f0f6-112">Pour plus d’informations sur le contenu d’un modèle de série chronologique, consultez [contenu du modèle d’exploration de données pour les modèles de série chronologique &#40;Analysis Services d’exploration de données&#41;](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="5f0f6-112">For more information about the content of a time series model, see [Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-view-the-artxp-regression-formula-for-a-time-series-model"></a><span data-ttu-id="5f0f6-113">Pour consulter la formule de régression ARTXP d'un modèle de série chronologique</span><span class="sxs-lookup"><span data-stu-id="5f0f6-113">To view the ARTXP regression formula for a time series model</span></span>  
  
1.  <span data-ttu-id="5f0f6-114">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], sélectionnez le modèle de série chronologique à afficher, puis cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-114">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="5f0f6-115">- ou -</span><span class="sxs-lookup"><span data-stu-id="5f0f6-115">-- or --</span></span>  
  
     <span data-ttu-id="5f0f6-116">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sélectionnez le modèle de série chronologique, puis cliquez sur l’onglet **Visionneuse de modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="5f0f6-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="5f0f6-117">Cliquez sur l’onglet **Modéliser** .</span><span class="sxs-lookup"><span data-stu-id="5f0f6-117">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="5f0f6-118">Si le modèle contient plusieurs arborescences, sélectionnez une arborescence unique dans la liste déroulante **Arborescence** .</span><span class="sxs-lookup"><span data-stu-id="5f0f6-118">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f0f6-119">Un modèle aura toujours plusieurs arborescences si vous avez plusieurs séries de données.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-119">A model will always have multiple trees if you have more than one data series.</span></span> <span data-ttu-id="5f0f6-120">Toutefois, vous ne verrez pas autant d’arborescences dans la **visionneuse de l’algorithme MTS** que dans la [Visionneuse de l’arborescence de contenu générique Microsoft](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="5f0f6-120">However, you will not see as many trees in the **Time Series viewer** as you will see in the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="5f0f6-121">Cela s'explique par le fait que la visionneuse de l'algorithme MTS associe les informations ARIMA et ARTXP de chaque série de données dans une représentation unique.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-121">That is because the Time Series viewer combines the ARIMA and ARTXP information for each data series into a single representation.</span></span>  
  
4.  <span data-ttu-id="5f0f6-122">Cliquez sur n'importe quel nœud terminal de l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-122">Click any leaf node in the tree.</span></span>  
  
     <span data-ttu-id="5f0f6-123">Les nœuds étiquetés comme **Série de données** sont toujours des nœuds terminaux et peuvent contenir une équation.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-123">Nodes that are labeled as **Data Series** are always leaf nodes and can contain an equation.</span></span> <span data-ttu-id="5f0f6-124">Si un nœud **(Tout)** n’a pas de nœuds enfants, il peut également contenir une équation.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-124">If an **(All)** node has no child nodes, it can also contain an equation.</span></span>  
  
5.  <span data-ttu-id="5f0f6-125">Si la **Légende d’exploration de données** n’est pas disponible, cliquez avec le bouton droit sur le nœud, puis sélectionnez **Afficher la légende**.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-125">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
     <span data-ttu-id="5f0f6-126">La formule ARTXP est affichée dans la première moitié de la **Légende d’exploration de données**, comme **l’équation du nœud d’arbre**.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-126">The ARTXP formula is displayed in the first half of the **Mining Legend**, as the **Tree node equation**.</span></span>  
  
### <a name="to-view-the-arima-formula-for-a-time-series-model"></a><span data-ttu-id="5f0f6-127">Pour consulter la formule ARIMA d'un modèle de série chronologique</span><span class="sxs-lookup"><span data-stu-id="5f0f6-127">To view the ARIMA formula for a time series model</span></span>  
  
1.  <span data-ttu-id="5f0f6-128">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], sélectionnez le modèle de série chronologique à afficher, puis cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-128">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="5f0f6-129">- ou -</span><span class="sxs-lookup"><span data-stu-id="5f0f6-129">-- or --</span></span>  
  
     <span data-ttu-id="5f0f6-130">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sélectionnez le modèle de série chronologique, puis cliquez sur l’onglet **Visionneuse de modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="5f0f6-130">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="5f0f6-131">Cliquez sur l’onglet **Modéliser** .</span><span class="sxs-lookup"><span data-stu-id="5f0f6-131">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="5f0f6-132">Si le modèle contient plusieurs arborescences, sélectionnez une arborescence unique dans la liste déroulante **Arborescence** .</span><span class="sxs-lookup"><span data-stu-id="5f0f6-132">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f0f6-133">Le modèle aura toujours plusieurs arborescences si vous incluez plusieurs séries de données.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-133">The model will always have multiple trees if you include more than one data series.</span></span>  
  
4.  <span data-ttu-id="5f0f6-134">Cliquez sur n'importe quel nœud de l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-134">Click any node in the tree.</span></span>  
  
     <span data-ttu-id="5f0f6-135">La formule ARIMA est affichée dans la seconde moitié de la **Légende d’exploration de données**, comme **Équation ARIMA**.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-135">The ARIMA formula is displayed in the second half of the **Mining Legend**, as the **ARIMA equation**.</span></span>  
  
5.  <span data-ttu-id="5f0f6-136">Si la **Légende d’exploration de données** n’est pas disponible, cliquez avec le bouton droit sur le nœud, puis sélectionnez **Afficher la légende**.</span><span class="sxs-lookup"><span data-stu-id="5f0f6-136">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f0f6-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f0f6-137">See Also</span></span>  
 <span data-ttu-id="5f0f6-138">[Tâches de la visionneuse de modèle d’exploration de données et procédures](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="5f0f6-138">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="5f0f6-139">[Parcourir un modèle à l’aide de la visionneuse MTS (Microsoft Time Series)](browse-a-model-using-the-microsoft-time-series-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="5f0f6-139">[Browse a Model Using the Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md) </span></span>  
 [<span data-ttu-id="5f0f6-140">Time Series Model Query Examples</span><span class="sxs-lookup"><span data-stu-id="5f0f6-140">Time Series Model Query Examples</span></span>](time-series-model-query-examples.md)  
  
  
