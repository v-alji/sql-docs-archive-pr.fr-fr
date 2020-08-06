---
title: Onglet discrimination de cluster (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.discrimination.f1
ms.assetid: ae7cfff7-ab1c-4cf5-9a91-97b21d15d85f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 35435736bcdf1b1962de6babace2def953bbfff0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603139"
---
# <a name="cluster-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="5a14c-102">Onglet Discrimination de cluster (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="5a14c-102">Cluster Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="5a14c-103">Utilisez l’onglet **Discrimination de cluster** pour comparer deux clusters qui existent dans un modèle Sequence Clustering.</span><span class="sxs-lookup"><span data-stu-id="5a14c-103">Use the **Cluster Discrimination** tab to compare two clusters that exist in a clustering model.</span></span> <span data-ttu-id="5a14c-104">Vous pouvez voir comment différentes combinaisons d'attributs et de valeurs sont représentées dans les clusters.</span><span class="sxs-lookup"><span data-stu-id="5a14c-104">You can see how different combinations of attributes and values are represented within the clusters.</span></span>  
  
 <span data-ttu-id="5a14c-105">**Pour plus d’informations :** [Algorithme de gestion de clusters Microsoft](data-mining/microsoft-clustering-algorithm.md), [Explorer un modèle à l’aide de Microsoft Sequence Cluster](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="5a14c-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="5a14c-106">Options</span><span class="sxs-lookup"><span data-stu-id="5a14c-106">Options</span></span>  
 <span data-ttu-id="5a14c-107">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="5a14c-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="5a14c-108">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="5a14c-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="5a14c-109">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="5a14c-109">**Mining Model**</span></span>  
 <span data-ttu-id="5a14c-110">Choisissez un modèle d'exploration de données parmi ceux de la structure d'exploration de données active.</span><span class="sxs-lookup"><span data-stu-id="5a14c-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="5a14c-111">Le modèle d'exploration de données s'ouvre dans sa visionneuse associée.</span><span class="sxs-lookup"><span data-stu-id="5a14c-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="5a14c-112">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="5a14c-112">**Viewer**</span></span>  
 <span data-ttu-id="5a14c-113">Choisissez la visionneuse à utiliser pour explorer le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5a14c-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="5a14c-114">Vous pouvez utiliser la visionneuse personnalisée pour les modèles de clustering, ou la visionneuse de contenu d’exploration de données ( [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer).</span><span class="sxs-lookup"><span data-stu-id="5a14c-114">You can use the custom viewer for clustering models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="5a14c-115">Vous pouvez également utiliser les visionneuses de plug-in, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="5a14c-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="5a14c-116">**Cluster 1**</span><span class="sxs-lookup"><span data-stu-id="5a14c-116">**Cluster 1**</span></span>  
 <span data-ttu-id="5a14c-117">Sélectionnez un cluster afin de le comparer à un autre cluster.</span><span class="sxs-lookup"><span data-stu-id="5a14c-117">Select a cluster, so that you can compare it to another cluster.</span></span>  
  
 <span data-ttu-id="5a14c-118">**Cluster 2**</span><span class="sxs-lookup"><span data-stu-id="5a14c-118">**Cluster 2**</span></span>  
 <span data-ttu-id="5a14c-119">Sélectionnez un deuxième cluster dans la liste de clusters du modèle d’exploration des données pour le comparer au **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="5a14c-119">Select a second cluster from the list of clusters in the mining model, to compare to **Cluster 1**.</span></span> <span data-ttu-id="5a14c-120">Vous pouvez également comparer un cluster à son complément, ce qui correspond à tous les cas du modèle à l'exception de ceux du cluster sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5a14c-120">You can also compare a cluster to its complement, meaning all cases in the model except those in the selected cluster.</span></span>  
  
 <span data-ttu-id="5a14c-121">**Scores de discrimination pour \<cluster 1> et\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="5a14c-121">**Discrimination scores for \<cluster 1> and \<cluster 2>**</span></span>  
 <span data-ttu-id="5a14c-122">Les colonnes dans le graphique fournissent des informations sur la façon dont chaque paire attribut-valeur se rapporte aux deux clusters sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="5a14c-122">The columns in the graph provide information about how each attribute-value pair is related to the two selected clusters.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a14c-123">**Variables**</span><span class="sxs-lookup"><span data-stu-id="5a14c-123">**Variables**</span></span>|<span data-ttu-id="5a14c-124">Attribut du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="5a14c-124">An attribute in the mining model.</span></span>|  
|<span data-ttu-id="5a14c-125">**Valeurs**</span><span class="sxs-lookup"><span data-stu-id="5a14c-125">**Values**</span></span>|<span data-ttu-id="5a14c-126">Valeur de l’attribut sélectionné dans **Variables**.</span><span class="sxs-lookup"><span data-stu-id="5a14c-126">A value of the attribute selected in **Variables**.</span></span>|  
|<span data-ttu-id="5a14c-127">**Privilégie\<cluster 1>**</span><span class="sxs-lookup"><span data-stu-id="5a14c-127">**Favors \<cluster 1>**</span></span>|<span data-ttu-id="5a14c-128">Le graphique à barres à gauche représente la probabilité que la paire attribut-valeur sélectionnée soit représentative du cluster sélectionné dans **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="5a14c-128">The bar graph on the left represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 1**.</span></span> <span data-ttu-id="5a14c-129">Vous pouvez positionner la souris sur la barre pour afficher la valeur, représentée en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="5a14c-129">You can pause the mouse over the bar to see the value, represented as a percentage.</span></span> <span data-ttu-id="5a14c-130">Notez que même si la valeur est égale à zéro, cela ne signifie pas que la valeur d’attribut est nécessairement manquante dans le cluster, mais que la distribution privilégie fortement un cluster par rapport à l’autre.</span><span class="sxs-lookup"><span data-stu-id="5a14c-130">Note that even if the value is zero, it doesn't mean the attribute-value is necessarily missing from the cluster, just that the distribution strongly favors one cluster over the other.</span></span>|  
|<span data-ttu-id="5a14c-131">**Privilégie\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="5a14c-131">**Favors \<cluster 2>**</span></span>|<span data-ttu-id="5a14c-132">Le graphique à barres à droite représente la probabilité que la paire attribut-valeur sélectionnée soit représentative du cluster sélectionné dans **Cluster 2**.</span><span class="sxs-lookup"><span data-stu-id="5a14c-132">The bar graph on the right represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a14c-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a14c-133">See Also</span></span>  
 <span data-ttu-id="5a14c-134">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5a14c-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="5a14c-135">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="5a14c-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="5a14c-136">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="5a14c-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
