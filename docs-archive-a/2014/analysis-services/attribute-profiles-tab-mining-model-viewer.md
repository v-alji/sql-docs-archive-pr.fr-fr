---
title: Onglet Profils d’attribut (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.profiles.f1
ms.assetid: 17c7e7ae-273c-4a6b-9a35-e8b9b8e65999
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61c81b95f030bf1a69aed165bd64e58ff9af8339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602616"
---
# <a name="attribute-profiles-tab-mining-model-viewer"></a><span data-ttu-id="8dafb-102">Onglet Profils d'attribut (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="8dafb-102">Attribute Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="8dafb-103">Utilisez l’onglet **Profils d’attribut** pour voir comment la distribution des valeurs d’entrée dans un état de modèle Naive Bayes contribue à chaque état de l’attribut de résultat.</span><span class="sxs-lookup"><span data-stu-id="8dafb-103">Use the **Attribute Profiles** tab to see how the distribution of input values in a Naive Bayes model state contribute to each state of the outcome attribute.</span></span> <span data-ttu-id="8dafb-104">La distribution de valeurs est affichée sous la forme d'un histogramme coloré, toutes les distributions étant présentées dans un format tabulaire, afin de faciliter la comparaison des valeurs.</span><span class="sxs-lookup"><span data-stu-id="8dafb-104">The distribution of values is shown as a colored histogram, all distributions presented in a tabular format, to make it easier to compare values.</span></span>  
  
 <span data-ttu-id="8dafb-105">**Pour plus d’informations :** [Algorithme MNB (Microsoft Naive Bayes)](data-mining/microsoft-naive-bayes-algorithm.md), [Explorer un modèle à l’aide de la visionneuse de l’algorithme MNB (Microsoft Naive Bayes)](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="8dafb-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="8dafb-106">Options</span><span class="sxs-lookup"><span data-stu-id="8dafb-106">Options</span></span>  
 <span data-ttu-id="8dafb-107">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="8dafb-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="8dafb-108">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8dafb-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="8dafb-109">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="8dafb-109">**Mining Model**</span></span>  
 <span data-ttu-id="8dafb-110">Choisissez un modèle d'exploration de données à afficher, parmi ceux de la structure d'exploration de données active.</span><span class="sxs-lookup"><span data-stu-id="8dafb-110">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="8dafb-111">Le modèle d'exploration de données s'ouvre dans sa visionneuse associée.</span><span class="sxs-lookup"><span data-stu-id="8dafb-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="8dafb-112">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="8dafb-112">**Viewer**</span></span>  
 <span data-ttu-id="8dafb-113">Choisissez la visionneuse à utiliser pour explorer le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="8dafb-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="8dafb-114">Vous pouvez choisir la visionneuse personnalisée fournie pour chaque modèle d’exploration de données ou [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span><span class="sxs-lookup"><span data-stu-id="8dafb-114">You can choose the custom viewer provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="8dafb-115">Vous pouvez également utiliser les visionneuses de plug-in, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="8dafb-115">You can also use plug-in viewers if they are available.</span></span>  
  
 <span data-ttu-id="8dafb-116">**Afficher la légende**</span><span class="sxs-lookup"><span data-stu-id="8dafb-116">**Show Legend**</span></span>  
 <span data-ttu-id="8dafb-117">Sélectionnez cette option pour afficher une clé qui fait correspondre chaque valeur dans **États** à l’une des couleurs utilisées dans le graphique de distribution.</span><span class="sxs-lookup"><span data-stu-id="8dafb-117">Select this option to display a key that matches each value in **States** to one of the colors used in the distribution chart.</span></span>  
  
 <span data-ttu-id="8dafb-118">**Barres de l’histogramme**</span><span class="sxs-lookup"><span data-stu-id="8dafb-118">**Histogram bars**</span></span>  
 <span data-ttu-id="8dafb-119">Sélectionnez le nombre de barres à inclure dans l'histogramme.</span><span class="sxs-lookup"><span data-stu-id="8dafb-119">Select how many bars to include in the histogram.</span></span> <span data-ttu-id="8dafb-120">S’il existe davantage de barres que le nombre que vous choisissez d’afficher, les barres de la plus grande importance sont conservées et les barres restantes sont regroupées dans **Autre**.</span><span class="sxs-lookup"><span data-stu-id="8dafb-120">If more bars exist than you choose to display, the bars of highest importance are retained, and the remaining bars are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="8dafb-121">**Prédictible**</span><span class="sxs-lookup"><span data-stu-id="8dafb-121">**Predictable**</span></span>  
 <span data-ttu-id="8dafb-122">Sélectionnez une colonne prédictible dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="8dafb-122">Select a predictable column from the mining model.</span></span>  
  
 <span data-ttu-id="8dafb-123">**Profils d'attribut**</span><span class="sxs-lookup"><span data-stu-id="8dafb-123">**Attribute Profiles**</span></span>  
 <span data-ttu-id="8dafb-124">Le tableau contient les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8dafb-124">The table contains the following columns:</span></span>  
  
|<span data-ttu-id="8dafb-125">Valeur</span><span class="sxs-lookup"><span data-stu-id="8dafb-125">Value</span></span>|<span data-ttu-id="8dafb-126">Description</span><span class="sxs-lookup"><span data-stu-id="8dafb-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8dafb-127">**Attributs**</span><span class="sxs-lookup"><span data-stu-id="8dafb-127">**Attributes**</span></span>|<span data-ttu-id="8dafb-128">Affiche la liste des colonnes contenues dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="8dafb-128">Lists the mining model columns contained within the mining model.</span></span>|  
|<span data-ttu-id="8dafb-129">**États**</span><span class="sxs-lookup"><span data-stu-id="8dafb-129">**States**</span></span>|<span data-ttu-id="8dafb-130">Colonne facultative qui décrit l'état que représente la couleur de la ligne correspondante d'attributs.</span><span class="sxs-lookup"><span data-stu-id="8dafb-130">An optional column that describes what state the color in the corresponding row of attributes represents.</span></span> <span data-ttu-id="8dafb-131">Ajoutez-la ou supprimez-la à l’aide de la case à cocher **Afficher la légende** .</span><span class="sxs-lookup"><span data-stu-id="8dafb-131">Add or remove by using the **Show Legend** check box.</span></span>|  
|<span data-ttu-id="8dafb-132">**Habitants**</span><span class="sxs-lookup"><span data-stu-id="8dafb-132">**Population**</span></span>|<span data-ttu-id="8dafb-133">Affiche la répartition de l'attribut dans l'ensemble du dataset.</span><span class="sxs-lookup"><span data-stu-id="8dafb-133">Displays the distribution of the attribute across the whole dataset.</span></span>|  
|<span data-ttu-id="8dafb-134">**Colonne pour les états d'attribut prédictible**</span><span class="sxs-lookup"><span data-stu-id="8dafb-134">**Column for states of predictable attribute**</span></span>|<span data-ttu-id="8dafb-135">Affiche une colonne pour chaque état de la colonne prédictible, chaque ligne correspondant à un attribut d'entrée du modèle.</span><span class="sxs-lookup"><span data-stu-id="8dafb-135">Displays a column for each state of the predictable column, with each row corresponding to an input attribute in the model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8dafb-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8dafb-136">See Also</span></span>  
 <span data-ttu-id="8dafb-137">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="8dafb-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="8dafb-138">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="8dafb-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="8dafb-139">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="8dafb-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
