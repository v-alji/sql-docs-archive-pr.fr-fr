---
title: Onglet discrimination de cluster de séquence clustering (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.sequenceclustering.discrimination.f1
ms.assetid: 7dd16479-2633-4f4b-83bf-cf55972a2241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9839a6185933fd87929331558ed63c1d81c6a748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710884"
---
# <a name="sequence-clustering-cluster-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="db4ae-102">Onglet Discrimination de cluster du modèle Sequence Clustering (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="db4ae-102">Sequence Clustering Cluster Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="db4ae-103">L’onglet  **Discrimination de cluster** de la **Visionneuse de l’algorithme MSC** (Microsoft Sequence Clustering) compare les clusters sélectionnés à partir d’un modèle Sequence Clustering.</span><span class="sxs-lookup"><span data-stu-id="db4ae-103">The  **Cluster Discrimination** tab in the **Microsoft Sequence Clustering Viewer** compares selected clusters from a sequence clustering model.</span></span>  
  
 <span data-ttu-id="db4ae-104">Utilisez cette vue d'un modèle Sequence Clustering pour comparer deux clusters et déterminer les états et les transitions qui sont différents.</span><span class="sxs-lookup"><span data-stu-id="db4ae-104">Use this view of a sequence clustering model to compare two clusters and see which states and transitions are different.</span></span>  
  
 <span data-ttu-id="db4ae-105">**Pour plus d’informations :** [Algorithme MSC (Microsoft Sequence Clustering)](data-mining/microsoft-sequence-clustering-algorithm.md), [Explorer un modèle à l’aide de la visionneuse de l’algorithme MSC (Microsoft Sequence Cluster)](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="db4ae-105">**For More Information:** [Microsoft Sequence Clustering Algorithm](data-mining/microsoft-sequence-clustering-algorithm.md), [Browse a Model Using the Microsoft Sequence Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="db4ae-106">Options</span><span class="sxs-lookup"><span data-stu-id="db4ae-106">Options</span></span>  
 <span data-ttu-id="db4ae-107">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="db4ae-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="db4ae-108">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="db4ae-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="db4ae-109">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="db4ae-109">**Mining Model**</span></span>  
 <span data-ttu-id="db4ae-110">Choisissez un modèle d'exploration de données pour afficher le contenu de la structure d'exploration actuelle.</span><span class="sxs-lookup"><span data-stu-id="db4ae-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="db4ae-111">Le modèle d'exploration de données s'ouvre dans sa visionneuse associée.</span><span class="sxs-lookup"><span data-stu-id="db4ae-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="db4ae-112">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="db4ae-112">**Viewer**</span></span>  
 <span data-ttu-id="db4ae-113">Choisissez la visionneuse à utiliser pour consulter le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="db4ae-113">Choose a viewer to use in exploring the selected mining model.</span></span> <span data-ttu-id="db4ae-114">Vous pouvez utiliser la visionneuse personnalisée ou la **Visionneuse de l'arborescence de contenu générique Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="db4ae-114">You can use the custom viewer, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="db4ae-115">Vous pouvez également utiliser les visionneuses de plug-in, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="db4ae-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="db4ae-116">**Cluster 1**</span><span class="sxs-lookup"><span data-stu-id="db4ae-116">**Cluster 1**</span></span>  
 <span data-ttu-id="db4ae-117">Sélectionnez un cluster parmi ceux du modèle.</span><span class="sxs-lookup"><span data-stu-id="db4ae-117">Select a cluster from those in the model.</span></span>  
  
 <span data-ttu-id="db4ae-118">**Cluster 2**</span><span class="sxs-lookup"><span data-stu-id="db4ae-118">**Cluster 2**</span></span>  
 <span data-ttu-id="db4ae-119">Sélectionnez un deuxième cluster dans le modèle d’exploration des données pour le comparer au **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="db4ae-119">Select a second cluster in the mining model, to compare to **Cluster 1**.</span></span>  
  
 <span data-ttu-id="db4ae-120">Si vous ne sélectionnez pas un autre cluster, par défaut le cluster sélectionné est comparé à son complément, ce qui correspond à tous les cas du modèle qui ne figurent pas dans le cluster 1.</span><span class="sxs-lookup"><span data-stu-id="db4ae-120">If you do not select another cluster, by default the selected cluster is compared to its complement, meaning all cases in the model that are not in Cluster 1.</span></span>  
  
 <span data-ttu-id="db4ae-121">**Scores de discrimination pour \<cluster 1> et\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="db4ae-121">**Discrimination scores for \<cluster 1> and \<cluster 2>**</span></span>  
 <span data-ttu-id="db4ae-122">Ce graphique fournit la comparaison détaillée des clusters que vous avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="db4ae-122">This chart provides the detailed comparison of the clusters that you selected.</span></span> <span data-ttu-id="db4ae-123">En général, un modèle de clustering affecte rarement des états ou des valeurs exclusivement à un seul cluster.</span><span class="sxs-lookup"><span data-stu-id="db4ae-123">In general, a clustering model rarely assigns states or values exclusively to a single cluster.</span></span> <span data-ttu-id="db4ae-124">Par conséquent, la visionneuse indique uniquement qu’un attribut ou un état particulier *privilégie* un cluster particulier.</span><span class="sxs-lookup"><span data-stu-id="db4ae-124">Therefore, the viewer indicates only that a particular attribute or state *favors* a particular cluster.</span></span>  
  
 <span data-ttu-id="db4ae-125">De façon générale, un cluster particulier peut contenir plusieurs états : par exemple, un état courant peut être l'achat d'une bouteille d'eau et d'un porte-bidon, dans l'ordre.</span><span class="sxs-lookup"><span data-stu-id="db4ae-125">Overall, a certain cluster might contain more of one state: for example, a common state might be the purchase of a Water Bottle and Water Bottle Cage in sequence.</span></span> <span data-ttu-id="db4ae-126">Toutefois, la séquence peut être présente dans d'autres clusters qui ont des caractéristiques de définition plus importantes.</span><span class="sxs-lookup"><span data-stu-id="db4ae-126">However, the sequence might be present in other clusters that have more important defining characteristics.</span></span> <span data-ttu-id="db4ae-127">Par exemple, un autre cluster peut être caractérisé de manière plus importante par des temps de transaction très courts, et une analyse indiquerait que les éléments « bouteille d'eau » et « porte-bidon » sont positionnés de manière à pouvoir généralement, mais pas systématiquement, être regroupés dans ce cluster.</span><span class="sxs-lookup"><span data-stu-id="db4ae-127">For example, another cluster might be characterized most strongly by very short transaction times, and an analysis would reveal that [Water Bottle and Waterthe items are positioned to might usually be grouped in this cluster, but not always.</span></span>  
  
|<span data-ttu-id="db4ae-128">Valeur</span><span class="sxs-lookup"><span data-stu-id="db4ae-128">Value</span></span>|<span data-ttu-id="db4ae-129">Description</span><span class="sxs-lookup"><span data-stu-id="db4ae-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="db4ae-130">**Variables**</span><span class="sxs-lookup"><span data-stu-id="db4ae-130">**Variables**</span></span>|<span data-ttu-id="db4ae-131">Attribut du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="db4ae-131">An attribute in the mining model.</span></span>|  
|<span data-ttu-id="db4ae-132">**Valeurs**</span><span class="sxs-lookup"><span data-stu-id="db4ae-132">**Values**</span></span>|<span data-ttu-id="db4ae-133">État de l’attribut répertorié dans **Variables**.</span><span class="sxs-lookup"><span data-stu-id="db4ae-133">A state of the attribute that is listed in **Variables**.</span></span>|  
|<span data-ttu-id="db4ae-134">**Privilégie\<cluster 1>**</span><span class="sxs-lookup"><span data-stu-id="db4ae-134">**Favors \<cluster 1>**</span></span>|<span data-ttu-id="db4ae-135">Contient une barre ombragée qui indique dans quelle proportion l’attribut et l’état répertoriés dans **Variables** et **Valeur** privilégient le cluster sélectionné dans **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="db4ae-135">Contains a shaded bar that indicates how strongly the attribute and the state that are listed in **Variables** and **Value** favor the cluster that is selected in **Cluster 1**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db4ae-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db4ae-136">See Also</span></span>  
 <span data-ttu-id="db4ae-137">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="db4ae-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="db4ae-138">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="db4ae-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="db4ae-139">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="db4ae-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
