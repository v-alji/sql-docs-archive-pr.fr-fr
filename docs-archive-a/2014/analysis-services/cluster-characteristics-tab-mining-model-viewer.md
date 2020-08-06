---
title: Onglet caractéristiques du cluster (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.characteristics.f1
ms.assetid: 8e33ed1d-1ce4-405d-895b-7e995b2c910d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 959d94767b6cb27d9ebb6e06c592034fca20ac89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602515"
---
# <a name="cluster-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="7577e-102">Onglet Caractéristiques du cluster (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="7577e-102">Cluster Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="7577e-103">L’onglet **Caractéristiques du cluster** vous permet d’explorer les caractéristiques d’un cluster dans un modèle de clustering, ou l’ensemble de tous les cas du modèle.</span><span class="sxs-lookup"><span data-stu-id="7577e-103">The **Cluster Characteristics** tab lets you explore the characteristics of a cluster in a clustering model, or the set of all cases in the model.</span></span> <span data-ttu-id="7577e-104">Le graphique affiche l'importance de chaque paire attribut-valeur comme caractéristique qui définit le cluster, en comparaison avec d'autres clusters.</span><span class="sxs-lookup"><span data-stu-id="7577e-104">The graph shows the importance of each attribute-value pair as a characteristic that defines the cluster, in comparison with other clusters.</span></span>  
  
 <span data-ttu-id="7577e-105">**Pour plus d’informations :** [Algorithme de gestion de clusters Microsoft](data-mining/microsoft-clustering-algorithm.md), [Explorer un modèle à l’aide de Microsoft Sequence Cluster](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="7577e-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="7577e-106">Options</span><span class="sxs-lookup"><span data-stu-id="7577e-106">Options</span></span>  
 <span data-ttu-id="7577e-107">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="7577e-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="7577e-108">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="7577e-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="7577e-109">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="7577e-109">**Mining Model**</span></span>  
 <span data-ttu-id="7577e-110">Choisissez un modèle d'exploration de données parmi ceux de la structure d'exploration de données active.</span><span class="sxs-lookup"><span data-stu-id="7577e-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="7577e-111">Le modèle d'exploration de données s'ouvre dans la visionneuse personnalisée.</span><span class="sxs-lookup"><span data-stu-id="7577e-111">The mining model will open in the custom viewer.</span></span>  
  
 <span data-ttu-id="7577e-112">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="7577e-112">**Viewer**</span></span>  
 <span data-ttu-id="7577e-113">Choisissez la visionneuse à utiliser pour explorer le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7577e-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="7577e-114">Vous pouvez utiliser la visionneuse personnalisée associée à ce type de modèle, ou la visionneuse de contenu d’exploration de données ( [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer).</span><span class="sxs-lookup"><span data-stu-id="7577e-114">You can use the custom viewer associated with this model type, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="7577e-115">Vous pouvez également utiliser les éventuelles visionneuses de plug-in disponibles.</span><span class="sxs-lookup"><span data-stu-id="7577e-115">You can also use any plug-in viewers that are available.</span></span>  
  
 <span data-ttu-id="7577e-116">**Cluster**</span><span class="sxs-lookup"><span data-stu-id="7577e-116">**Cluster**</span></span>  
 <span data-ttu-id="7577e-117">Choisissez le cluster à afficher, ou choisissez **Remplissage (tout)** pour voir la distribution des attributs du modèle dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="7577e-117">Choose the cluster you want to view, or choose **Population (All)** to see the distribution of attributes for the model as a whole.</span></span>  
  
 <span data-ttu-id="7577e-118">**Caractéristiques pour\<cluster>**</span><span class="sxs-lookup"><span data-stu-id="7577e-118">**Characteristics for \<cluster>**</span></span>  
 <span data-ttu-id="7577e-119">Le graphique contient les colonnes suivantes, qui décrivent les caractéristiques du cluster sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7577e-119">The graph contains the following columns, which describe the characteristics of the selected cluster.</span></span>  
  
|<span data-ttu-id="7577e-120">Valeur</span><span class="sxs-lookup"><span data-stu-id="7577e-120">Value</span></span>|<span data-ttu-id="7577e-121">Description</span><span class="sxs-lookup"><span data-stu-id="7577e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7577e-122">**Variable**</span><span class="sxs-lookup"><span data-stu-id="7577e-122">**Variable**</span></span>|<span data-ttu-id="7577e-123">Répertorie les attributs du modèle d'exploration de données qui se trouvent dans le cluster sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7577e-123">Lists the attributes from the mining model that are found in the selected cluster.</span></span>|  
|<span data-ttu-id="7577e-124">**Valeurs**</span><span class="sxs-lookup"><span data-stu-id="7577e-124">**Values**</span></span>|<span data-ttu-id="7577e-125">Répertorie les valeurs des attributs actuels qui se trouvent dans le cluster sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7577e-125">Lists the values of the current attributes that are found in the currently selected cluster.</span></span>|  
|<span data-ttu-id="7577e-126">**Risque**</span><span class="sxs-lookup"><span data-stu-id="7577e-126">**Probability**</span></span>|<span data-ttu-id="7577e-127">La barre indique la puissance de la paire attribut-valeur comme fonctionnalité de distinction de ce cluster.</span><span class="sxs-lookup"><span data-stu-id="7577e-127">The bar indicates the strength of the attribute-value pair as a distinguishing feature of this cluster.</span></span> <span data-ttu-id="7577e-128">Si vous pointez la souris sur la barre, vous pouvez consulter la valeur de probabilité, représentée en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="7577e-128">If you hover the mouse over the bar, you can see the probability value, represented as a percentage.</span></span> <span data-ttu-id="7577e-129">Elle indique, étant donné cette combinaison d'attributs et de valeurs dans un cas particulier, la probabilité d'appartenance du cas à ce cluster.</span><span class="sxs-lookup"><span data-stu-id="7577e-129">What this indicates is, given this attribute and value combination in any particular case, what is the probability that the case would belong in this cluster.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7577e-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7577e-130">See Also</span></span>  
 <span data-ttu-id="7577e-131">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7577e-131">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="7577e-132">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7577e-132">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="7577e-133">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="7577e-133">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
