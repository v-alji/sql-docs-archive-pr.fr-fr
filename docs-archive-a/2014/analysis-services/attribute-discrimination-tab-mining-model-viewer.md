---
title: Onglet discrimination d’attribut (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.discrimination.f1
ms.assetid: 68323f23-121e-44fc-be85-6f9915d6d3c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: a8b0d4bc99b1c8f1c5de0269312f02eeb09df022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602621"
---
# <a name="attribute-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="79128-102">Onglet Discrimination d'attribut (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="79128-102">Attribute Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="79128-103">Utilisez l’onglet **Discrimination d’attribut** pour comparer les états des attributs d’entrée et examiner leur relation avec l’attribut de résultat.</span><span class="sxs-lookup"><span data-stu-id="79128-103">Use the **Attribute Discrimination** tab to compare the states of the input attributes and see how they are related to the outcome attribute.</span></span> <span data-ttu-id="79128-104">Les valeurs d'attribut qui présentent la plus grande différence entre les deux états d'attribut prédictible sélectionnés sont répertoriées en premier.</span><span class="sxs-lookup"><span data-stu-id="79128-104">The attribute values that make the most difference between the two selected predictable attribute states are listed first.</span></span>  
  
 <span data-ttu-id="79128-105">**Pour plus d’informations :** [Algorithme MNB (Microsoft Naive Bayes)](data-mining/microsoft-naive-bayes-algorithm.md), [Explorer un modèle à l’aide de la visionneuse de l’algorithme MNB (Microsoft Naive Bayes)](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="79128-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="79128-106">Options</span><span class="sxs-lookup"><span data-stu-id="79128-106">Options</span></span>  
 <span data-ttu-id="79128-107">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="79128-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="79128-108">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="79128-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="79128-109">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="79128-109">**Mining Model**</span></span>  
 <span data-ttu-id="79128-110">Choisissez un modèle d'exploration de données parmi ceux de la structure d'exploration de données active.</span><span class="sxs-lookup"><span data-stu-id="79128-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="79128-111">Le modèle d'exploration de données s'ouvre automatiquement dans la visionneuse personnalisée correcte.</span><span class="sxs-lookup"><span data-stu-id="79128-111">The mining model automatically opens in the correct custom viewer.</span></span>  
  
 <span data-ttu-id="79128-112">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="79128-112">**Viewer**</span></span>  
 <span data-ttu-id="79128-113">Choisissez la visionneuse à utiliser pour explorer le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="79128-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="79128-114">Pour chaque modèle, vous pouvez choisir la visionneuse personnalisée ou [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span><span class="sxs-lookup"><span data-stu-id="79128-114">For each model, you can choose either the custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="79128-115">Vous pouvez également utiliser les visionneuses de plug-in, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="79128-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="79128-116">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="79128-116">**Attribute**</span></span>  
 <span data-ttu-id="79128-117">Choisissez un attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="79128-117">Choose a predictable attribute.</span></span>  
  
 <span data-ttu-id="79128-118">**Valeur 1**</span><span class="sxs-lookup"><span data-stu-id="79128-118">**Value 1**</span></span>  
 <span data-ttu-id="79128-119">Choisissez l’état de l’attribut prédictible à comparer à l’état contenu dans **Valeur 2**.</span><span class="sxs-lookup"><span data-stu-id="79128-119">Choose a state of the predictable attribute to compare to the state that is contained in **Value 2**.</span></span>  
  
 <span data-ttu-id="79128-120">**Valeur 2**</span><span class="sxs-lookup"><span data-stu-id="79128-120">**Value 2**</span></span>  
 <span data-ttu-id="79128-121">Choisissez l’état de l’attribut prédictible à comparer à l’état contenu dans **Valeur 1**.</span><span class="sxs-lookup"><span data-stu-id="79128-121">Select a state of the predictable attribute to compare to the state that is contained in **Value 1**.</span></span> <span data-ttu-id="79128-122">Vous pouvez également sélectionner **tous les autres États** pour comparer la valeur de la **valeur 1** avec son complément, autrement dit, toutes les autres valeurs à l’exception de la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="79128-122">You can also select **All Other States** to compare the value in **Value 1** with its complement-that is, all other values except Value 1.</span></span>  
  
 <span data-ttu-id="79128-123">**Scores de discrimination pour \<Value 1> et\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="79128-123">**Discrimination scores for \<Value 1> and \<Value 2>**</span></span>  
 <span data-ttu-id="79128-124">Le graphique contient les colonnes suivantes, qui décrivent comment l'attribut cible est lié aux états spécifiques de l'attribut d'entrée.</span><span class="sxs-lookup"><span data-stu-id="79128-124">The graph contains the following columns, which describe how the target attribute is related to specific states of the input attribute.</span></span>  
  
|<span data-ttu-id="79128-125">Valeur</span><span class="sxs-lookup"><span data-stu-id="79128-125">Value</span></span>|<span data-ttu-id="79128-126">Description</span><span class="sxs-lookup"><span data-stu-id="79128-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="79128-127">**Attributs**</span><span class="sxs-lookup"><span data-stu-id="79128-127">**Attributes**</span></span>|<span data-ttu-id="79128-128">Attribut d'entrée du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="79128-128">An input attribute in the mining model.</span></span>|  
|<span data-ttu-id="79128-129">**Valeurs**</span><span class="sxs-lookup"><span data-stu-id="79128-129">**Values**</span></span>|<span data-ttu-id="79128-130">État de l’attribut répertorié dans **Attributs**.</span><span class="sxs-lookup"><span data-stu-id="79128-130">A state of the attribute that is listed in **Attributes**.</span></span>|  
|<span data-ttu-id="79128-131">**Privilégie\<Value 1>**</span><span class="sxs-lookup"><span data-stu-id="79128-131">**Favors \<Value 1>**</span></span>|<span data-ttu-id="79128-132">La barre indique si l’attribut actuel et la valeur favorisent les résultats cibles sélectionnés dans **Valeur 1**.</span><span class="sxs-lookup"><span data-stu-id="79128-132">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 1**.</span></span>|  
|<span data-ttu-id="79128-133">**Privilégie\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="79128-133">**Favors \<Value 2>**</span></span>|<span data-ttu-id="79128-134">La barre indique si l’attribut actuel et la valeur favorisent les résultats cibles sélectionnés dans **Valeur 2**.</span><span class="sxs-lookup"><span data-stu-id="79128-134">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79128-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79128-135">See Also</span></span>  
 <span data-ttu-id="79128-136">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="79128-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="79128-137">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="79128-137">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="79128-138">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="79128-138">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
