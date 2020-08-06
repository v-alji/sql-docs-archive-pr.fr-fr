---
title: Onglet Jeux d’éléments (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.itemsets.f1
ms.assetid: 95b2b805-b142-4064-9c80-4b1b3fe2fe63
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b99b62b01b196fd62e1ef264e530487018f6a60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602409"
---
# <a name="itemsets-tab-mining-model-viewer"></a><span data-ttu-id="fceb9-102">Onglet Jeux d'éléments (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="fceb9-102">Itemsets Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="fceb9-103">Vous pouvez utiliser le volet **Jeux d’éléments** pour afficher les jeux d’éléments fréquents contenus dans un modèle d’exploration de données de règles d’association.</span><span class="sxs-lookup"><span data-stu-id="fceb9-103">You can use the **Itemsets** pane to view the frequent itemsets that an association rules mining model contains.</span></span> <span data-ttu-id="fceb9-104">Étant donné qu'un modèle d'association peut contenir un grand nombre de jeux d'éléments, des contrôles sont fournis dans la visionneuse pour vous aider à filtrer les jeux d'éléments affichés dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="fceb9-104">Because an association model can contain many itemsets, controls are provided in the viewer to help you filter the itemsets that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="fceb9-105">**Pour plus d’informations :** [Algorithme Microsoft Association](data-mining/microsoft-association-algorithm.md), [Explorer un modèle à l’aide de la visionneuse de l’algorithme MAR (Microsoft Association Rules)](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="fceb9-105">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="fceb9-106">Options</span><span class="sxs-lookup"><span data-stu-id="fceb9-106">Options</span></span>  
 <span data-ttu-id="fceb9-107">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="fceb9-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="fceb9-108">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="fceb9-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="fceb9-109">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="fceb9-109">**Mining Model**</span></span>  
 <span data-ttu-id="fceb9-110">Choisissez un modèle d'exploration de données pour afficher le contenu de la structure d'exploration actuelle.</span><span class="sxs-lookup"><span data-stu-id="fceb9-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="fceb9-111">Le modèle d'exploration de données s'ouvre dans sa visionneuse associée.</span><span class="sxs-lookup"><span data-stu-id="fceb9-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="fceb9-112">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="fceb9-112">**Viewer**</span></span>  
 <span data-ttu-id="fceb9-113">Choisissez la visionneuse à utiliser pour afficher le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="fceb9-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="fceb9-114">Vous pouvez utiliser la visionneuse personnalisée pour les modèles d'association ou la visionneuse de l'arborescence de contenu générique [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fceb9-114">You can use either the custom viewer for association models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="fceb9-115">Vous pouvez également utiliser les visionneuses de plug-in, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="fceb9-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="fceb9-116">**Prise en charge minimale**</span><span class="sxs-lookup"><span data-stu-id="fceb9-116">**Minimum support**</span></span>  
 <span data-ttu-id="fceb9-117">Modifiez cette valeur pour définir la prise en charge minimale que doit contenir un jeu d'éléments pour être affiché dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="fceb9-117">Change this value to set the minimum support that an itemset must contain to appear in the viewer.</span></span> <span data-ttu-id="fceb9-118">La valeur par défaut affichée à l'ouverture du modèle est calculée par le modèle, mais vous pouvez la modifier pour afficher plus ou moins de jeux d'éléments.</span><span class="sxs-lookup"><span data-stu-id="fceb9-118">The default value that is displayed when you first open the model is calculated by the model, but you can change it to see more or fewer itemsets.</span></span>  
  
 <span data-ttu-id="fceb9-119">**Taille minimale du jeu d'éléments**</span><span class="sxs-lookup"><span data-stu-id="fceb9-119">**Minimum itemset size**</span></span>  
 <span data-ttu-id="fceb9-120">Modifiez cette valeur pour définir le nombre minimal d'éléments qui doivent être inclus dans un jeu d'éléments avant que ce dernier puisse être affiché dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="fceb9-120">Change this value to set the minimum number of items that must be included in an itemset before the itemset can be displayed in the viewer.</span></span>  
  
 <span data-ttu-id="fceb9-121">**Filtrer le jeu d'éléments**</span><span class="sxs-lookup"><span data-stu-id="fceb9-121">**Filter Itemset**</span></span>  
 <span data-ttu-id="fceb9-122">Tapez une valeur de chaîne pour filtrer le nombre de jeux d'éléments affichés dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="fceb9-122">Type a string value to filter the number of itemsets that appear in the viewer.</span></span>  
  
 <span data-ttu-id="fceb9-123">Vous pouvez également taper des expressions régulières .NET comme critères de filtre.</span><span class="sxs-lookup"><span data-stu-id="fceb9-123">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="fceb9-124">Par exemple, l'expression suivante retourne tous les jeux d'éléments qui contiennent « Road Bottle Cage » :</span><span class="sxs-lookup"><span data-stu-id="fceb9-124">For example, the following expression returns all itemsets that contain 'Road Bottle Cage':</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*`  
  
 <span data-ttu-id="fceb9-125">Notez que vous devrez peut-être actualiser la vue pour voir les critères de filtre appliqués.</span><span class="sxs-lookup"><span data-stu-id="fceb9-125">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="fceb9-126">Vous pouvez également activer et désactiver l'option **Afficher le nom long** afin d'actualiser la liste.</span><span class="sxs-lookup"><span data-stu-id="fceb9-126">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="fceb9-127">Par défaut, les critères de filtre s'appliquent au nom complet de la combinaison attribut-valeur ; par conséquent, si vous affichez le nom de l'attribut uniquement, il n'est pas évident de savoir si les critères de filtre ont été appliqués correctement.</span><span class="sxs-lookup"><span data-stu-id="fceb9-127">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="fceb9-128">Utilisez la liste déroulante **Afficher** pour sélectionner **Afficher le nom et la valeur de l'attribut**et vérifiez que la liste des jeux d'éléments est filtrée correctement.</span><span class="sxs-lookup"><span data-stu-id="fceb9-128">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="fceb9-129">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="fceb9-129">**Show**</span></span>  
 <span data-ttu-id="fceb9-130">Ajustez le mode d'affichage du jeu d'éléments dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="fceb9-130">Adjust how the itemset is displayed in the viewer.</span></span> <span data-ttu-id="fceb9-131">Vous pouvez sélectionner l'une des trois options suivantes :</span><span class="sxs-lookup"><span data-stu-id="fceb9-131">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="fceb9-132">Afficher le nom et la valeur de l'attribut</span><span class="sxs-lookup"><span data-stu-id="fceb9-132">Show attribute name and value</span></span>  
  
-   <span data-ttu-id="fceb9-133">Afficher la valeur de l'attribut uniquement</span><span class="sxs-lookup"><span data-stu-id="fceb9-133">Show attribute value only</span></span>  
  
-   <span data-ttu-id="fceb9-134">Afficher le nom de l'attribut uniquement</span><span class="sxs-lookup"><span data-stu-id="fceb9-134">Show attribute name only</span></span>  
  
 <span data-ttu-id="fceb9-135">Notez que cette option n'interroge pas de nouveau le modèle ; elle filtre uniquement les attributs ou les valeurs qui sont affichés.</span><span class="sxs-lookup"><span data-stu-id="fceb9-135">Note that this option does not requery the model; it only filters the attributes or values that are displayed.</span></span>  
  
 <span data-ttu-id="fceb9-136">**Afficher le nom long**</span><span class="sxs-lookup"><span data-stu-id="fceb9-136">**Show long name**</span></span>  
 <span data-ttu-id="fceb9-137">Sélectionnez cette option pour afficher le nom complet du jeu d'éléments tel qu'il apparaît dans le contenu du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fceb9-137">Select this option to display the full name of the itemset as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="fceb9-138">**Lignes au maximum**</span><span class="sxs-lookup"><span data-stu-id="fceb9-138">**Maximum rows**</span></span>  
 <span data-ttu-id="fceb9-139">Limitez le nombre de jeux d'éléments affichés dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="fceb9-139">Limit the number of itemsets that are displayed in the viewer.</span></span> <span data-ttu-id="fceb9-140">Par défaut, les jeux d'éléments sont classés selon la prise en charge, par ordre décroissant ; une valeur plus faible limite ainsi la liste aux jeux d'éléments les plus courants.</span><span class="sxs-lookup"><span data-stu-id="fceb9-140">By default, itemsets are ordered by support in descending order, so lowering this value restricts the list to the most common itemsets.</span></span>  
  
 <span data-ttu-id="fceb9-141">**Support**</span><span class="sxs-lookup"><span data-stu-id="fceb9-141">**Support**</span></span>  
 <span data-ttu-id="fceb9-142">Affiche la prise en charge de chaque jeu d'éléments.</span><span class="sxs-lookup"><span data-stu-id="fceb9-142">Displays the support for each itemset.</span></span>  
  
 <span data-ttu-id="fceb9-143">**Taille**</span><span class="sxs-lookup"><span data-stu-id="fceb9-143">**Size**</span></span>  
 <span data-ttu-id="fceb9-144">Affiche le nombre d'éléments présents dans chaque jeu d'éléments.</span><span class="sxs-lookup"><span data-stu-id="fceb9-144">Displays the number of items that exist in each itemset.</span></span>  
  
 <span data-ttu-id="fceb9-145">**Jeu d'éléments**</span><span class="sxs-lookup"><span data-stu-id="fceb9-145">**Itemset**</span></span>  
 <span data-ttu-id="fceb9-146">Affiche la description de chaque jeu d'éléments.</span><span class="sxs-lookup"><span data-stu-id="fceb9-146">Displays the description of each itemset.</span></span> <span data-ttu-id="fceb9-147">Par défaut, les jeux d'éléments sont présentés sous forme de liste d'attributs et de leurs valeurs séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="fceb9-147">By default, itemsets are presented as a comma-delimited list of attributes and their values.</span></span> <span data-ttu-id="fceb9-148">Vous pouvez modifier la façon dont ils sont affichés à l’aide de l’option **Afficher** .</span><span class="sxs-lookup"><span data-stu-id="fceb9-148">You can change the way they are displayed by using the **Show** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fceb9-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fceb9-149">See Also</span></span>  
 <span data-ttu-id="fceb9-150">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="fceb9-150">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="fceb9-151">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="fceb9-151">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="fceb9-152">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="fceb9-152">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
