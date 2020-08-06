---
title: Onglet Profils du cluster (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.profiles.f1
ms.assetid: 1ebafa1f-74e9-4c05-b278-a690fa8543bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7ec1ce5b5204ae81a9313ca7b7e5df58c98c5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603135"
---
# <a name="cluster-profiles-tab-mining-model-viewer"></a><span data-ttu-id="6b0db-102">Onglet Profils du cluster (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="6b0db-102">Cluster Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="6b0db-103">Utilisez l’onglet **Profils du cluster** pour obtenir une vue globale des clusters détectés par l’algorithme au sein d’un modèle de clustering.</span><span class="sxs-lookup"><span data-stu-id="6b0db-103">Use the **Cluster Profiles** tab for an overall view of the clusters that the algorithm discovered within a clustering model.</span></span> <span data-ttu-id="6b0db-104">L'onglet affiche chaque attribut, accompagné de sa répartition dans chaque cluster.</span><span class="sxs-lookup"><span data-stu-id="6b0db-104">The tab displays each attribute, together with the distribution of the attribute in each cluster.</span></span>  
  
 <span data-ttu-id="6b0db-105">**Pour plus d’informations :** [Algorithme de gestion de clusters Microsoft](data-mining/microsoft-clustering-algorithm.md), [Explorer un modèle à l’aide de Microsoft Sequence Cluster](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="6b0db-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="6b0db-106">Options</span><span class="sxs-lookup"><span data-stu-id="6b0db-106">Options</span></span>  
 <span data-ttu-id="6b0db-107">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="6b0db-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="6b0db-108">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="6b0db-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="6b0db-109">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="6b0db-109">**Mining Model**</span></span>  
 <span data-ttu-id="6b0db-110">Choisissez un modèle d'exploration de données parmi ceux de la structure d'exploration de données active.</span><span class="sxs-lookup"><span data-stu-id="6b0db-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="6b0db-111">Le modèle d'exploration de données s'ouvre dans sa visionneuse associée.</span><span class="sxs-lookup"><span data-stu-id="6b0db-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="6b0db-112">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="6b0db-112">**Viewer**</span></span>  
 <span data-ttu-id="6b0db-113">Choisissez la visionneuse à utiliser pour afficher le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6b0db-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="6b0db-114">Vous pouvez utiliser la visionneuse personnalisée pour le modèle d'exploration de données, ou la visionneuse de contenu d'exploration de données ( [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer).</span><span class="sxs-lookup"><span data-stu-id="6b0db-114">You can use the custom viewer for the mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="6b0db-115">Vous pouvez également utiliser les visionneuses de plug-in, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="6b0db-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="6b0db-116">**Afficher la légende**</span><span class="sxs-lookup"><span data-stu-id="6b0db-116">**Show Legend**</span></span>  
 <span data-ttu-id="6b0db-117">Sélectionnez cette option pour afficher une clé qui indique le mappage de couleurs dans la visionneuse aux valeurs de la colonne **États** .</span><span class="sxs-lookup"><span data-stu-id="6b0db-117">Select this option to display a key that shows the mapping of colors in the viewer to values in the **States** column.</span></span>  
  
 <span data-ttu-id="6b0db-118">**Barres de l’histogramme**</span><span class="sxs-lookup"><span data-stu-id="6b0db-118">**Histogram Bars**</span></span>  
 <span data-ttu-id="6b0db-119">Modifiez cette valeur pour contrôler le nombre d'états inclus dans chaque histogramme.</span><span class="sxs-lookup"><span data-stu-id="6b0db-119">Change this value to control how many states are included in each histogram.</span></span> <span data-ttu-id="6b0db-120">S’il existe davantage d’états que le nombre que vous choisissez d’afficher, les états avec la plus grande probabilité sont affichés dans l’histogramme et les états restants sont regroupés dans **Autre**.</span><span class="sxs-lookup"><span data-stu-id="6b0db-120">If there are more states than you choose to display, the states with the highest probability are shown in the histogram, and the remaining states are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="6b0db-121">**Attributs**</span><span class="sxs-lookup"><span data-stu-id="6b0db-121">**Attributes**</span></span>  
 <span data-ttu-id="6b0db-122">Répertorie les colonnes figurant dans le modèle de clustering.</span><span class="sxs-lookup"><span data-stu-id="6b0db-122">Lists the columns that are in the clustering model.</span></span> <span data-ttu-id="6b0db-123">Les histogrammes de chaque attribut montrent la manière dont l'attribut est distribué entre les clusters identifiés par l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="6b0db-123">The histograms for each attribute show how the attribute is distributed among the clusters identified by the algorithm.</span></span>  
  
 <span data-ttu-id="6b0db-124">**États**</span><span class="sxs-lookup"><span data-stu-id="6b0db-124">**States**</span></span>  
 <span data-ttu-id="6b0db-125">Fournit une clé qui indique quelle couleur représente chaque état dans la ligne correspondante de clusters, ou un curseur avec un losange qui indique la distribution des valeurs numériques continues.</span><span class="sxs-lookup"><span data-stu-id="6b0db-125">Provides a key that either denotes what color represents each state in the corresponding row of clusters, or a slider with diamond that indicates the distribution of continuous numeric values.</span></span> <span data-ttu-id="6b0db-126">Vous pouvez afficher ou masquer cette colonne en utilisant la case à cocher **Afficher la légende** .</span><span class="sxs-lookup"><span data-stu-id="6b0db-126">You can show or hide this column by using the **Show Legend** check box.</span></span>  
  
 <span data-ttu-id="6b0db-127">**Profils du cluster**</span><span class="sxs-lookup"><span data-stu-id="6b0db-127">**Cluster Profiles**</span></span>  
 <span data-ttu-id="6b0db-128">Cette section contient une colonne pour chaque cluster du modèle.</span><span class="sxs-lookup"><span data-stu-id="6b0db-128">This section contains a column for each cluster in the model.</span></span> <span data-ttu-id="6b0db-129">Pour chaque attribut, l'histogramme affiche la distribution des valeurs de l'attribut uniquement pour ce cluster.</span><span class="sxs-lookup"><span data-stu-id="6b0db-129">For each attribute, the histogram shows the distribution of the values in the attribute for just that cluster.</span></span> <span data-ttu-id="6b0db-130">Le graphique contient également une colonne pour **Remplissage**, qui utilise également les histogrammes pour afficher la distribution des valeurs pour chaque attribut, mais pour tous les cas du modèle.</span><span class="sxs-lookup"><span data-stu-id="6b0db-130">The chart also has a column for **Population**, which also uses histograms to display the distribution of values for each attribute, but for all cases in the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b0db-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b0db-131">See Also</span></span>  
 <span data-ttu-id="6b0db-132">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6b0db-132">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="6b0db-133">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="6b0db-133">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="6b0db-134">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="6b0db-134">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
