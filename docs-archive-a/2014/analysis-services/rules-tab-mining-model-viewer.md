---
title: Onglet Règles (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.rules.f1
ms.assetid: 705d5492-b58f-45d9-94d7-ed57b7025823
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0d86931865fd9352074669de93b14dacfc84537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602375"
---
# <a name="rules-tab-mining-model-viewer"></a><span data-ttu-id="a04d8-102">Onglet Règles (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="a04d8-102">Rules Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="a04d8-103">Utilisez le volet **Règles** dans un modèle d'association pour afficher les règles que l'algorithme a extraites des données.</span><span class="sxs-lookup"><span data-stu-id="a04d8-103">Use the **Rules** pane in an association model to view the rules that the algorithm extracted from the data.</span></span> <span data-ttu-id="a04d8-104">Les règles décrivent comment les éléments sont liés entre eux et peuvent être utilisées pour créer des recommandations.</span><span class="sxs-lookup"><span data-stu-id="a04d8-104">Rules describe how items are related to each other, and can be used to create recommendations.</span></span>  
  
 <span data-ttu-id="a04d8-105">Vous pouvez utiliser les options de la visionneuse pour filtrer le nombre de règles qui y sont affichées.</span><span class="sxs-lookup"><span data-stu-id="a04d8-105">You can use the options in the viewer to filter the number of rules that are displayed in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a04d8-106">Par défaut, seules les règles qui se trouvent au-dessus du seuil de probabilité défini dans **Probabilité minimale** sont affichées dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="a04d8-106">By default, only the rules that are above the probability threshold defined in **Minimum probability** are displayed in the viewer.</span></span> <span data-ttu-id="a04d8-107">Vous ne pouvez pas réduire cette valeur à l'aide de la visionneuse, car le seuil de probabilité pour la sortie de règle est déterminé lors de la création du modèle.</span><span class="sxs-lookup"><span data-stu-id="a04d8-107">You cannot make this value any smaller by using the viewer, because the probability threshold for rule output is determined when the model is created.</span></span> <span data-ttu-id="a04d8-108">Pour plus d’informations, consultez [Références techniques relatives à l’algorithme Microsoft Association](data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a04d8-108">For more information, see [Microsoft Association Algorithm Technical Reference](data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="a04d8-109">**Pour plus d’informations :** [Algorithme Microsoft Association](data-mining/microsoft-association-algorithm.md), [Explorer un modèle à l’aide de la visionneuse de l’algorithme MAR (Microsoft Association Rules)](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="a04d8-109">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="a04d8-110">Options</span><span class="sxs-lookup"><span data-stu-id="a04d8-110">Options</span></span>  
 <span data-ttu-id="a04d8-111">**Actualiser le contenu de l'observateur**</span><span class="sxs-lookup"><span data-stu-id="a04d8-111">**Refresh viewer content**</span></span>  
 <span data-ttu-id="a04d8-112">Recharge le modèle d'exploration de données dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="a04d8-112">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="a04d8-113">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="a04d8-113">**Mining Model**</span></span>  
 <span data-ttu-id="a04d8-114">Choisissez un modèle d'exploration de données pour afficher le contenu de la structure d'exploration actuelle.</span><span class="sxs-lookup"><span data-stu-id="a04d8-114">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="a04d8-115">Le modèle d'exploration de données s'ouvre dans sa visionneuse associée.</span><span class="sxs-lookup"><span data-stu-id="a04d8-115">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="a04d8-116">**Visionneuse**</span><span class="sxs-lookup"><span data-stu-id="a04d8-116">**Viewer**</span></span>  
 <span data-ttu-id="a04d8-117">Choisissez la visionneuse à utiliser pour afficher le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a04d8-117">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="a04d8-118">Vous pouvez utiliser la visionneuse personnalisée pour chaque modèle d'exploration de données, ou la **Visionneuse de l'arborescence de contenu générique Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a04d8-118">You can use the custom viewer for each mining model, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="a04d8-119">Vous pouvez également utiliser les visionneuses de plug-in, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="a04d8-119">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="a04d8-120">**Probabilité minimale**</span><span class="sxs-lookup"><span data-stu-id="a04d8-120">**Minimum probability**</span></span>  
 <span data-ttu-id="a04d8-121">Modifiez cette valeur pour définir la probabilité minimale requise pour qu'une règle soit affichée dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="a04d8-121">Change this value to set the minimum probability required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="a04d8-122">L'augmentation de la valeur de probabilité réduira le nombre de règles affichées.</span><span class="sxs-lookup"><span data-stu-id="a04d8-122">Increasing the value for probability will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="a04d8-123">**Importance minimale**</span><span class="sxs-lookup"><span data-stu-id="a04d8-123">**Minimum importance**</span></span>  
 <span data-ttu-id="a04d8-124">Modifiez cette valeur pour définir l'importance minimale requise pour qu'une règle soit affichée dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="a04d8-124">Change this value to set the minimum importance required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="a04d8-125">L'augmentation de la valeur d'importance réduira le nombre de règles affichées.</span><span class="sxs-lookup"><span data-stu-id="a04d8-125">Increasing the value for importance will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="a04d8-126">**Filtrer la règle**</span><span class="sxs-lookup"><span data-stu-id="a04d8-126">**Filter Rule**</span></span>  
 <span data-ttu-id="a04d8-127">Tapez une valeur de chaîne pour filtrer le nombre de règles affichées dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="a04d8-127">Type a string value to filter the number of rules that appear in the viewer.</span></span>  
  
 <span data-ttu-id="a04d8-128">Vous pouvez également taper des expressions régulières .NET comme critères de filtre.</span><span class="sxs-lookup"><span data-stu-id="a04d8-128">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="a04d8-129">Par exemple, l'expression suivante retourne toutes les règles qui contiennent « Road Bottle Cage » du côté gauche de la règle :</span><span class="sxs-lookup"><span data-stu-id="a04d8-129">For example, the following expression returns all rules that contain 'Road Bottle Cage' on the left side of the rule:</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*->.*`  
  
 <span data-ttu-id="a04d8-130">Notez que vous devrez peut-être actualiser la vue pour voir les critères de filtre appliqués.</span><span class="sxs-lookup"><span data-stu-id="a04d8-130">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="a04d8-131">Vous pouvez également activer et désactiver l'option **Afficher le nom long** afin d'actualiser la liste.</span><span class="sxs-lookup"><span data-stu-id="a04d8-131">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="a04d8-132">Par défaut, les critères de filtre s'appliquent au nom complet de la combinaison attribut-valeur ; par conséquent, si vous affichez le nom de l'attribut uniquement, il n'est pas évident de savoir si les critères de filtre ont été appliqués correctement.</span><span class="sxs-lookup"><span data-stu-id="a04d8-132">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="a04d8-133">Utilisez la liste déroulante **Afficher** pour sélectionner **Afficher le nom et la valeur de l'attribut**et vérifiez que la liste des jeux d'éléments est filtrée correctement.</span><span class="sxs-lookup"><span data-stu-id="a04d8-133">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="a04d8-134">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="a04d8-134">**Show**</span></span>  
 <span data-ttu-id="a04d8-135">Ajustez le mode d'affichage de la règle dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="a04d8-135">Adjust the way that the rule is displayed in the viewer.</span></span> <span data-ttu-id="a04d8-136">Vous pouvez sélectionner l'une des trois options suivantes :</span><span class="sxs-lookup"><span data-stu-id="a04d8-136">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="a04d8-137">Afficher le nom et la valeur de l'attribut</span><span class="sxs-lookup"><span data-stu-id="a04d8-137">Show the attribute name and value</span></span>  
  
-   <span data-ttu-id="a04d8-138">Afficher la valeur de l'attribut uniquement</span><span class="sxs-lookup"><span data-stu-id="a04d8-138">Show the attribute value only</span></span>  
  
-   <span data-ttu-id="a04d8-139">Afficher le nom de l'attribut uniquement</span><span class="sxs-lookup"><span data-stu-id="a04d8-139">Show the attribute name only</span></span>  
  
 <span data-ttu-id="a04d8-140">**Afficher le nom long**</span><span class="sxs-lookup"><span data-stu-id="a04d8-140">**Show long name**</span></span>  
 <span data-ttu-id="a04d8-141">Affichez le nom complet de la règle tel qu'il apparaît dans le contenu du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="a04d8-141">Show the full name of the rule as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="a04d8-142">**Lignes au maximum**</span><span class="sxs-lookup"><span data-stu-id="a04d8-142">**Maximum rows**</span></span>  
 <span data-ttu-id="a04d8-143">Limitez le nombre de règles affichées dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="a04d8-143">Limit the number of rules that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="a04d8-144">**Risque**</span><span class="sxs-lookup"><span data-stu-id="a04d8-144">**Probability**</span></span>  
 <span data-ttu-id="a04d8-145">Cette colonne dans le graphique affiche la probabilité de chaque règle.</span><span class="sxs-lookup"><span data-stu-id="a04d8-145">This column in the chart displays the probability for each rule.</span></span>  
  
 <span data-ttu-id="a04d8-146">Vous pouvez cliquer sur l'en-tête de colonne pour effectuer le tri d'après la probabilité.</span><span class="sxs-lookup"><span data-stu-id="a04d8-146">You can click the column heading to sort by probability.</span></span>  
  
 <span data-ttu-id="a04d8-147">**Importance**</span><span class="sxs-lookup"><span data-stu-id="a04d8-147">**Importance**</span></span>  
 <span data-ttu-id="a04d8-148">Cette colonne dans le graphique affiche l'importance de chaque règle.</span><span class="sxs-lookup"><span data-stu-id="a04d8-148">This column in the chart displays the importance for each rule.</span></span>  
  
 <span data-ttu-id="a04d8-149">Vous pouvez cliquer sur l'en-tête de colonne pour effectuer le tri d'après l'importance.</span><span class="sxs-lookup"><span data-stu-id="a04d8-149">You can click the column heading to sort by importance.</span></span>  
  
 <span data-ttu-id="a04d8-150">**Règle**</span><span class="sxs-lookup"><span data-stu-id="a04d8-150">**Rule**</span></span>  
 <span data-ttu-id="a04d8-151">Cette colonne du graphique affiche la description textuelle de chaque règle, selon le format spécifié à l’aide des options **Afficher** et **Afficher le nom long**.</span><span class="sxs-lookup"><span data-stu-id="a04d8-151">This column in the chart displays the text description for each rule, according to the format specified by using the options, **Show** and **Show long name**.</span></span>  
  
 <span data-ttu-id="a04d8-152">Vous pouvez cliquer sur l'en-tête de colonne pour effectuer le tri d'après le texte de la règle.</span><span class="sxs-lookup"><span data-stu-id="a04d8-152">You can click the column heading to sort by the text of the rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a04d8-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a04d8-153">See Also</span></span>  
 <span data-ttu-id="a04d8-154">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a04d8-154">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="a04d8-155">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a04d8-155">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="a04d8-156">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="a04d8-156">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
