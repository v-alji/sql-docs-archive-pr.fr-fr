---
title: Éditeur de formulaire d’action d’extraction (onglet actions, concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.actionexpression.drillthroughaction.f1
ms.assetid: 225fd818-b5ea-494f-b67b-66e09798274a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 546448bd05f3af45b7093acb2dbb9d1e1a8f1bd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613200"
---
# <a name="drillthrough-action-form-editor-actions-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="bb8c4-102">Éditeur de formulaire d'action d'extraction (onglet Actions, Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="bb8c4-102">Drillthrough Action Form Editor (Actions Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="bb8c4-103">Utilisez le volet **Éditeur de formulaire d’action d’extraction** sous l’onglet **Actions** du Concepteur de cube pour modifier l’action d’extraction sélectionnée dans le volet **Organisateur d’action** .</span><span class="sxs-lookup"><span data-stu-id="bb8c4-103">Use the **Drillthrough Action Form Editor** pane on the **Actions** tab in Cube Designer to modify the drillthrough action selected in the **Action Organizer** pane.</span></span> <span data-ttu-id="bb8c4-104">Pour plus d’informations sur les actions d’extraction, consultez [Actions &#40;Analysis Services - Données multidimensionnelles&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bb8c4-104">For more information about drillthrough actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb8c4-105">Les actions d'extraction ne descendent plus vers la banque de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-105">Drillthrough actions no longer drill down to the underlying data store.</span></span> <span data-ttu-id="bb8c4-106">Les informations auxquelles accèdent les actions d'extraction doivent être façonnées dans le cube à l'aide de membres de la dimension ou la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-106">The information that drillthrough actions access must be modeled within the cube by using dimension or hierarchy members.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bb8c4-107">Options</span><span class="sxs-lookup"><span data-stu-id="bb8c4-107">Options</span></span>  
 <span data-ttu-id="bb8c4-108">**name**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-108">**name**</span></span>  
 <span data-ttu-id="bb8c4-109">Tapez le nom de l'action.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-109">Type the name of the action.</span></span>  
  
 <span data-ttu-id="bb8c4-110">**Cible d'action**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-110">**Action Target**</span></span>  
 <span data-ttu-id="bb8c4-111">Développez pour afficher l’option **Membres de groupe de mesures** .</span><span class="sxs-lookup"><span data-stu-id="bb8c4-111">Expand to view the **Measure group members** option.</span></span>  
  
 <span data-ttu-id="bb8c4-112">**Membres de groupe de mesures**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-112">**Measure group members**</span></span>  
 <span data-ttu-id="bb8c4-113">Sélectionnez le groupe de mesures auquel l'action d'extraction doit être associée.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-113">Select the measure group to which the drillthrough action is to be associated.</span></span>  
  
 <span data-ttu-id="bb8c4-114">**Condition (facultatif)**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-114">**Condition (Optional)**</span></span>  
 <span data-ttu-id="bb8c4-115">Entrez la syntaxe MDX (Multidimensional Expressions) qui décrit une condition facultative utilisée conjointement avec l’option **Membres de groupe de mesures**, pour restreindre davantage quand l’action est disponible.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-115">Enter the Multidimensional Expressions (MDX) expression that describes an optional condition, used in conjunction with **Measure group members**, which further restricts when the action is available.</span></span> <span data-ttu-id="bb8c4-116">L'expression doit retourner une valeur booléenne qui, si elle est vraie, indique que l'action est disponible.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-116">The expression must return a Boolean value that, if true, indicates the action is available.</span></span>  
  
 <span data-ttu-id="bb8c4-117">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-117">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="bb8c4-118">**Colonnes d'extraction**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-118">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="bb8c4-119">Développez afin d'afficher une grille qui mentionne les attributs renvoyés lorsque l'utilisateur exécute cette action.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-119">Expand to display a grid in which to indicate the attributes that are returned when the user runs this action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb8c4-120">Vous pouvez sélectionner plusieurs dimensions, mais chaque dimension ne peut être utilisée qu'une seule fois dans une action d'extraction.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-120">You can select more than one dimension, but no dimension can be used more than once in a drillthrough action.</span></span>  
  
 <span data-ttu-id="bb8c4-121">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="bb8c4-121">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="bb8c4-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="bb8c4-122">Column</span></span>|<span data-ttu-id="bb8c4-123">Description</span><span class="sxs-lookup"><span data-stu-id="bb8c4-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bb8c4-124">**Dimensions**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-124">**Dimensions**</span></span>|<span data-ttu-id="bb8c4-125">Sélectionnez la dimension dont est dérivé l'attribut renvoyé.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-125">Select the dimension from which the returned attribute is derived.</span></span> <span data-ttu-id="bb8c4-126">Sélectionnez MEASURES pour réaliser une extraction sur les mesures.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-126">Select MEASURES to drillthrough on measures.</span></span>|  
|<span data-ttu-id="bb8c4-127">**Colonnes de retour**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-127">**Return Columns**</span></span>|<span data-ttu-id="bb8c4-128">Sélectionnez l'attribut ou la mesure à partir de la dimension choisie et qui doit être renvoyé(e) lors de l'exécution de l'action.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-128">Select the attribute or measure from the selected dimension to be returned when the action is run.</span></span>|  
  
 <span data-ttu-id="bb8c4-129">**Propriétés supplémentaires**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-129">**Additional Properties**</span></span>  
 <span data-ttu-id="bb8c4-130">Développez pour afficher les options **Par défaut**, **Lignes au maximum**, **Invocation**, **Application**, **Description**, **Légende**et **La légende est MDX** .</span><span class="sxs-lookup"><span data-stu-id="bb8c4-130">Expand to view the **Default**, **Maximum rows**, **Invocation**, **Application**, **Description**, **Caption**, and **Caption Is MDX** options.</span></span>  
  
 <span data-ttu-id="bb8c4-131">**Par défaut**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-131">**Default**</span></span>  
 <span data-ttu-id="bb8c4-132">Sélectionnez **True** pour définir cette action d’extraction comme valeur par défaut. Sinon, sélectionnez **False**.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-132">Select **True** to include this drillthrough action as a default drillthrough action, otherwise, select **False**.</span></span>  
  
 <span data-ttu-id="bb8c4-133">Si la `RETURN` clause est omise dans une `DRILLTHROUGH` instruction MDX exécutée par une application cliente, l' [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance évalue toutes les actions d’extraction par défaut et exécute la première action d’extraction par défaut qui retourne un jeu non vide.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-133">If the `RETURN` clause is omitted from an MDX `DRILLTHROUGH` statement executed by a client application, the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance evaluates all default drillthrough actions and runs the first default drillthrough action that returns a non-empty set.</span></span> <span data-ttu-id="bb8c4-134">Pour plus d’informations sur l' `DRILLTHROUGH` instruction MDX, consultez [instruction d’extraction &#40;&#41;MDX ](/sql/mdx/mdx-data-manipulation-drillthrough).</span><span class="sxs-lookup"><span data-stu-id="bb8c4-134">For more information about the MDX `DRILLTHROUGH` statement, see [DRILLTHROUGH Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-drillthrough).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb8c4-135">Cette option est utilisée à des fins de compatibilité ascendante.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-135">This option is used for backwards compatibility purposes.</span></span>  
  
 <span data-ttu-id="bb8c4-136">**Lignes au maximum**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-136">**Maximum rows**</span></span>  
 <span data-ttu-id="bb8c4-137">Tapez le nombre maximum de lignes à retourner par l'action d'extraction.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-137">Type the maximum number of rows to be returned by the drillthrough action.</span></span> <span data-ttu-id="bb8c4-138">Si vous attribuez la valeur zéro à cette option ou que vous la laissez vide, l'action d'extraction retourne toutes les lignes à l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-138">Setting this option to zero or an empty value indicates that the drillthrough action returns all rows retrieved by the action to the client application.</span></span>  
  
 <span data-ttu-id="bb8c4-139">**Invocation**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-139">**Invocation**</span></span>  
 <span data-ttu-id="bb8c4-140">Sélectionnez le paramètre qui indique le moment où l'action doit être effectuée.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-140">Select the setting that indicates when the action should be carried out.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb8c4-141">Cette option ne fournit qu'une recommandation à une application cliente quant au moment d'exécution d'une action ; elle ne commande pas directement l'appel de l'action.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-141">This option only provides a recommendation to a client application as to when to execute an action, and does not directly control the invocation of the action.</span></span>  
  
 <span data-ttu-id="bb8c4-142">Le tableau suivant décrit les paramètres disponibles.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-142">The following table describes the available settings.</span></span>  
  
|<span data-ttu-id="bb8c4-143">Valeur</span><span class="sxs-lookup"><span data-stu-id="bb8c4-143">Value</span></span>|<span data-ttu-id="bb8c4-144">Description</span><span class="sxs-lookup"><span data-stu-id="bb8c4-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb8c4-145">Batch</span><span class="sxs-lookup"><span data-stu-id="bb8c4-145">Batch</span></span>|<span data-ttu-id="bb8c4-146">L’action doit s’exécuter dans le cadre d’une opération par lot ou d’une tâche [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb8c4-146">The action should run as part of a batch operation or an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] task.</span></span>|  
|<span data-ttu-id="bb8c4-147">Interactive</span><span class="sxs-lookup"><span data-stu-id="bb8c4-147">Interactive</span></span>|<span data-ttu-id="bb8c4-148">L'action s'exécute lorsque l'utilisateur l'invoque.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-148">The action runs when the user invokes the action.</span></span>|  
|<span data-ttu-id="bb8c4-149">À l’ouverture</span><span class="sxs-lookup"><span data-stu-id="bb8c4-149">On Open</span></span>|<span data-ttu-id="bb8c4-150">L'action s'exécute à la première ouverture du cube.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-150">The action runs when the cube is first opened.</span></span>|  
  
 <span data-ttu-id="bb8c4-151">**Application**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-151">**Application**</span></span>  
 <span data-ttu-id="bb8c4-152">Tapez le nom de l'application qui peut exécuter l'action d'extraction.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-152">Type the name of the application that can execute the drillthrough action.</span></span>  
  
 <span data-ttu-id="bb8c4-153">Vous pouvez également utiliser cette option pour identifier l'application cliente qui utilise le plus souvent cette action, ainsi que pour afficher les icônes appropriées dans un menu contextuel à côté de l'action.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-153">You can also use this option to identify which client application most commonly uses this action, as well as to display appropriate icons next to the action in a pop-up menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb8c4-154">Cette option ne fournit qu'une recommandation à une application cliente quant à l'application cliente qui doit exécuter une action ; elle ne commande pas directement l'accès à l'action.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-154">This option only provides a recommendation to a client application as to what client application should execute an action, and does not directly control access to the action.</span></span> <span data-ttu-id="bb8c4-155">Les applications clientes doivent masquer toute action associée à d'autres applications clientes.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-155">Client applications should hide any actions that are associated with other client applications.</span></span>  
  
 <span data-ttu-id="bb8c4-156">**Description**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-156">**Description**</span></span>  
 <span data-ttu-id="bb8c4-157">Tapez une description facultative de l'action.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-157">Type the optional description of the action.</span></span>  
  
 <span data-ttu-id="bb8c4-158">**Caption**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-158">**Caption**</span></span>  
 <span data-ttu-id="bb8c4-159">Entrez la légende à afficher pour l’action dans l’application cliente si l’option **La légende est MDX** a la valeur **False**.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-159">Type the caption to be displayed for the action in the client application if **Caption Is MDX** is set to **False**.</span></span>  
  
 <span data-ttu-id="bb8c4-160">Entrez l’expression MDX (Multidimensional Expressions) qui retourne une chaîne pour la légende si l’option **La légende est MDX** a la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-160">Type the Multidimensional Expressions (MDX) expression that returns a string for the caption if **Caption Is MDX** is set to **True**.</span></span>  
  
 <span data-ttu-id="bb8c4-161">**La légende est MDX**</span><span class="sxs-lookup"><span data-stu-id="bb8c4-161">**Caption Is MDX**</span></span>  
 <span data-ttu-id="bb8c4-162">Sélectionnez **False** pour indiquer que la **Légende** contient une chaîne littérale qui représente une légende à afficher pour l’action dans l’application cliente.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-162">Select **False** to indicate that **Caption** contains a literal string representing a caption to be displayed for the action in the client application.</span></span>  
  
 <span data-ttu-id="bb8c4-163">Sélectionnez **True** pour indiquer que la **Légende** contient une expression MDX qui retourne une chaîne représentant une légende à afficher pour l’action dans l’application cliente.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-163">Select **True** to indicate that **Caption** contains an MDX expression that returns a string representing a caption to be displayed for the action in the client application.</span></span> <span data-ttu-id="bb8c4-164">L'expression MDX doit être résolue avant que l'action soit retournée à l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="bb8c4-164">The MDX expression must be resolved before the action is returned to the client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb8c4-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb8c4-165">See Also</span></span>  
 <span data-ttu-id="bb8c4-166">[Expressions multidimensionnelles &#40;référence de&#41; MDX](/sql/mdx/multidimensional-expressions-mdx-reference) </span><span class="sxs-lookup"><span data-stu-id="bb8c4-166">[Multidimensional Expressions &#40;MDX&#41; Reference](/sql/mdx/multidimensional-expressions-mdx-reference) </span></span>  
 <span data-ttu-id="bb8c4-167">[Actions &#40;le concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bb8c4-167">[Actions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="bb8c4-168">[Barre d’outils &#40;onglet actions, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bb8c4-168">[Toolbar &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="bb8c4-169">[Organisateur d’action &#40;onglet actions, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bb8c4-169">[Action Organizer &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="bb8c4-170">[Outils de calcul &#40;onglet actions, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bb8c4-170">[Calculation Tools &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="bb8c4-171">[Éditeur de formulaire d’action &#40;onglet actions, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bb8c4-171">[Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="bb8c4-172">Éditeur de formulaire d’action de rapport &#40;onglet actions, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="bb8c4-172">Report Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](report-action-form-editor-cube-designer-analysis-services-multidimensional-data.md)  
  
  
