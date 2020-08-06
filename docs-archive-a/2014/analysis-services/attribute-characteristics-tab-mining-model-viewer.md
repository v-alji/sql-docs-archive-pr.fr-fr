---
title: Onglet caractéristiques d’attribut (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.characteristics.f1
ms.assetid: f0c3350d-84c0-4ab8-9fb8-1527c2647299
author: minewiskan
ms.author: owend
ms.openlocfilehash: b29ba482c21bb674a10bc4c9e6c6eccdf30905dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602626"
---
# <a name="attribute-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="397a1-102">Onglet Caractéristiques d'attribut (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="397a1-102">Attribute Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="397a1-103">Le volet **Caractéristiques d’attribut** permet d’explorer les relations entre les résultats et les attributs d’entrée dans un modèle Naïve Bayes.</span><span class="sxs-lookup"><span data-stu-id="397a1-103">Use the **Attribute Characteristics** pane to explore the relationships between outcomes and input attributes in a Naïve Bayes model.</span></span> <span data-ttu-id="397a1-104">Vous pouvez choisir la valeur de l'attribut cible, puis consulter la liste des attributs d'entrée qui ont l'effet le plus important sur les résultats.</span><span class="sxs-lookup"><span data-stu-id="397a1-104">You can choose the value of the target attribute, and then see a list of the input attributes that have the strongest effect on the outcomes.</span></span>  
  
 <span data-ttu-id="397a1-105">**Pour plus d’informations :** [Algorithme MNB (Microsoft Naive Bayes)](data-mining/microsoft-naive-bayes-algorithm.md), [Explorer un modèle à l’aide de la visionneuse de l’algorithme MNB (Microsoft Naive Bayes)](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="397a1-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="397a1-106">Options</span><span class="sxs-lookup"><span data-stu-id="397a1-106">Options</span></span>  
 <span data-ttu-id="397a1-107">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="397a1-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="397a1-108">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="397a1-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="397a1-109">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="397a1-109">**Mining Model**</span></span>  
 <span data-ttu-id="397a1-110">Choisissez un modèle d'exploration de données à afficher, parmi ceux de la structure d'exploration actuelle.</span><span class="sxs-lookup"><span data-stu-id="397a1-110">Choose a mining model to view, from the models in the current mining structure.</span></span> <span data-ttu-id="397a1-111">Le modèle d'exploration de données s'ouvre automatiquement dans une visionneuse personnalisée qui est la mieux adaptée pour le type particulier de modèle que vous avez choisi.</span><span class="sxs-lookup"><span data-stu-id="397a1-111">The mining model will automatically open in a custom viewer that is best for the particular type of model you chose.</span></span>  
  
 <span data-ttu-id="397a1-112">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="397a1-112">**Viewer**</span></span>  
 <span data-ttu-id="397a1-113">Choisissez la visionneuse à utiliser pour explorer le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="397a1-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="397a1-114">Pour chaque modèle, vous avez le choix entre une visionneuse personnalisée ou la visionneuse de contenu d’exploration de données ( [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer).</span><span class="sxs-lookup"><span data-stu-id="397a1-114">For each model, you have the choice of a custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="397a1-115">Les visionneuses de plug-in apparaissent également dans cette liste, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="397a1-115">Plug-in viewers also appear in this list if available.</span></span>  
  
 <span data-ttu-id="397a1-116">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="397a1-116">**Attribute**</span></span>  
 <span data-ttu-id="397a1-117">Choisissez l'attribut prédictible que vous souhaitez analyser.</span><span class="sxs-lookup"><span data-stu-id="397a1-117">Choose the predictable attribute that you want to analyze.</span></span>  
  
 <span data-ttu-id="397a1-118">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="397a1-118">**Value**</span></span>  
 <span data-ttu-id="397a1-119">Choisissez un état pour l’attribut prédictible que vous avez défini dans **Attribut**.</span><span class="sxs-lookup"><span data-stu-id="397a1-119">Choose a state for the predictable attribute that you set in **Attribute**.</span></span> <span data-ttu-id="397a1-120">Étant donné que les modèles Naïve Bayes ne prennent pas en charge les variables continues, tous les attributs cibles possèdent des résultats discrets ou discrétisés.</span><span class="sxs-lookup"><span data-stu-id="397a1-120">Because Naïve Bayes models do not support continuous variables, all target attributes have discrete or discretized outcomes.</span></span> <span data-ttu-id="397a1-121">L'attribut manquant est toujours ajouté automatiquement à la liste.</span><span class="sxs-lookup"><span data-stu-id="397a1-121">The Missing attribute is always automatically added to the list.</span></span>  
  
 <span data-ttu-id="397a1-122">**Caractéristiques pour\<predictable state>**</span><span class="sxs-lookup"><span data-stu-id="397a1-122">**Characteristics for \<predictable state>**</span></span>  
 <span data-ttu-id="397a1-123">Ce graphique contient les colonnes suivantes, qui décrivent la relation des états des attributs d'entrée par rapport à l'état de l'attribut prédictible sélectionné.</span><span class="sxs-lookup"><span data-stu-id="397a1-123">The graph contains the following columns, which describe how states of the input attributes are related to the selected predictable attribute state.</span></span>  
  
|<span data-ttu-id="397a1-124">Valeur</span><span class="sxs-lookup"><span data-stu-id="397a1-124">Value</span></span>|<span data-ttu-id="397a1-125">Description</span><span class="sxs-lookup"><span data-stu-id="397a1-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="397a1-126">**Variable**</span><span class="sxs-lookup"><span data-stu-id="397a1-126">**Variable**</span></span>|<span data-ttu-id="397a1-127">Répertorie les attributs d'entrée du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="397a1-127">Lists the input attributes in the mining model.</span></span>|  
|<span data-ttu-id="397a1-128">**Valeurs**</span><span class="sxs-lookup"><span data-stu-id="397a1-128">**Values**</span></span>|<span data-ttu-id="397a1-129">Répertorie chaque état de l’attribut d’entrée dans **Variable**.</span><span class="sxs-lookup"><span data-stu-id="397a1-129">Lists each state of the input attribute in **Variable**.</span></span>|  
|<span data-ttu-id="397a1-130">**Risque**</span><span class="sxs-lookup"><span data-stu-id="397a1-130">**Probability**</span></span>|<span data-ttu-id="397a1-131">La barre représente la probabilité que l'attribut et la valeur de cette ligne soient associés à l'état sélectionné de l'attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="397a1-131">The bar represents the probability that the attribute and value in that row are associated with the selected state of the predictable attribute.</span></span> <span data-ttu-id="397a1-132">Pointez la souris sur la barre afin d'afficher la probabilité en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="397a1-132">Hover the mouse over the bar to view the probability as a percentage.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="397a1-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="397a1-133">See Also</span></span>  
 <span data-ttu-id="397a1-134">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="397a1-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="397a1-135">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="397a1-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="397a1-136">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="397a1-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
