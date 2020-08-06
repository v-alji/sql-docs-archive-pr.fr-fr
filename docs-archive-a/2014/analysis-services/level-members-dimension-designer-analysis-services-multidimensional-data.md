---
title: Niveau et membres (onglet navigateur, concepteur de dimensions) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.browsertab.levelsandmembers.f1
ms.assetid: 3f61e384-5b4e-4480-a7ed-b408de2fdea7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 21680f00b82b5410e2c7a67122fdcfeb78c999dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710944"
---
# <a name="level-and-members-browser-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="543c5-102">Niveau et membres (onglet Navigateur, Concepteur de dimensions) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="543c5-102">Level and Members (Browser Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="543c5-103">Utilisez ce volet pour parcourir les membres correspondant à la hiérarchie et à la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="543c5-103">Use this pane to browse the members of the currently selected hierarchy and language.</span></span> <span data-ttu-id="543c5-104">Pour sélectionner une hiérarchie ou une langue à consulter, utilisez les options **Hiérarchie** et **Langue** du volet **Barre d'outils** .</span><span class="sxs-lookup"><span data-stu-id="543c5-104">To select a hierarchy or language to browse, use the **Hierarchy** and **Language** options on the **Toolbar** pane.</span></span> <span data-ttu-id="543c5-105">Pour plus d’informations sur le volet Barre d’outils, consultez [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="543c5-105">For more information about the Toolbar pane, see [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="writeback-mode"></a><span data-ttu-id="543c5-106">Mode Écriture différée</span><span class="sxs-lookup"><span data-stu-id="543c5-106">Writeback Mode</span></span>  
 <span data-ttu-id="543c5-107">La fonctionnalité de ce volet change si vous activez le mode d'écriture différé.</span><span class="sxs-lookup"><span data-stu-id="543c5-107">The functionality of this pane changes if writeback mode is enabled.</span></span> <span data-ttu-id="543c5-108">L'écriture doit être activée sur la dimension sélectionnée (en d'autres termes, la propriété `WriteEnabled` de la dimension doit être affectée de la valeur true) et la dimension doit être déployée sur une instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] pour pouvoir activer le mode d'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="543c5-108">The selected dimension must be write-enabled (in other words, the `WriteEnabled` property of the dimension must be set to true) and the dimension must be deployed to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance in order to enable writeback mode.</span></span>  
  
 <span data-ttu-id="543c5-109">Pour activer le mode d’écriture différée, vous pouvez sélectionner **Écriture différée** dans le volet **Barre d’outils** ou cliquer avec le bouton droit sur le volet **Niveau et membres** et sélectionner **Écriture différée** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="543c5-109">To enable writeback mode, you can either select **Writeback** from the **Toolbar** pane, or right-click the **Level and Members** pane and select **Writeback** from the context menu.</span></span>  
  
 <span data-ttu-id="543c5-110">Si le mode d'écriture différée est activé, vous pouvez exécuter les actions supplémentaires suivantes dans le volet **Niveau et membres** :</span><span class="sxs-lookup"><span data-stu-id="543c5-110">If writeback mode is enabled, you can perform the following additional actions in the **Level and Members** pane:</span></span>  
  
|<span data-ttu-id="543c5-111">Actions à effectuer</span><span class="sxs-lookup"><span data-stu-id="543c5-111">To do</span></span>|<span data-ttu-id="543c5-112">Action</span><span class="sxs-lookup"><span data-stu-id="543c5-112">Perform</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="543c5-113">Créer des membres frères et enfants dans la hiérarchie sélectionnée</span><span class="sxs-lookup"><span data-stu-id="543c5-113">Create sibling and child members within the selected hierarchy.</span></span>|<span data-ttu-id="543c5-114">Cliquez avec le bouton droit sur le membre sélectionné et sélectionnez **Créer frères**pour créer un membre frère, ou sur **Créer enfant**pour créer un membre enfant à partir du menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="543c5-114">Right-click the selected member and select either **Create Sibling**, to create a sibling member, or **Create Child**, to create a child member, from the context menu.</span></span>|  
|<span data-ttu-id="543c5-115">Remonter ou descendre un membre sélectionné dans la hiérarchie</span><span class="sxs-lookup"><span data-stu-id="543c5-115">Move a selected member up or down the hierarchy.</span></span>|<span data-ttu-id="543c5-116">Faites glisser le membre sélectionné vers le membre parent ou enfant approprié, ou cliquez sur **Augmenter le retrait** ou sur **Réduire le retrait** dans le volet **Barre d'outils** pour monter ou descendre le membre sélectionné dans les niveaux de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="543c5-116">Either drag the selected member to the appropriate parent or child member, or click **Increase Indent** or **Decrease Indent** on the **Toolbar** pane to move the selected member up or down the levels of the hierarchy.</span></span>|  
|<span data-ttu-id="543c5-117">Renommer un membre sélectionné</span><span class="sxs-lookup"><span data-stu-id="543c5-117">Rename a selected member.</span></span>|<span data-ttu-id="543c5-118">Cliquez avec le bouton droit sur le membre sélectionné et sélectionnez **Renommer**ou cliquez sur un membre déjà sélectionné.</span><span class="sxs-lookup"><span data-stu-id="543c5-118">Either right-click the selected member and select **Rename**, or click an already-selected member.</span></span>|  
|<span data-ttu-id="543c5-119">Modifier les valeurs des propriétés du membre</span><span class="sxs-lookup"><span data-stu-id="543c5-119">Edit member property values</span></span>|<span data-ttu-id="543c5-120">Double-cliquez sur la valeur dans la propriété du membre sélectionné pour modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="543c5-120">Double-click the value in the selected member property for the selected member to edit the value.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="543c5-121">Options</span><span class="sxs-lookup"><span data-stu-id="543c5-121">Options</span></span>  
 <span data-ttu-id="543c5-122">**Niveau actuel**</span><span class="sxs-lookup"><span data-stu-id="543c5-122">**Current level**</span></span>  
 <span data-ttu-id="543c5-123">Affiche le niveau auquel appartient le membre sélectionné dans **Arborescence** .</span><span class="sxs-lookup"><span data-stu-id="543c5-123">Displays the level to which the currently selected member in **Tree** belongs.</span></span>  
  
 <span data-ttu-id="543c5-124">**Arbres**</span><span class="sxs-lookup"><span data-stu-id="543c5-124">**Tree**</span></span>  
 <span data-ttu-id="543c5-125">Affiche les membres correspondant à la hiérarchie et à la langue sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="543c5-125">Displays the members of the currently selected hierarchy and language.</span></span>  
  
 <span data-ttu-id="543c5-126">Si les propriétés du membre sont sélectionnées depuis l'option **Propriétés de membre** du volet Barre d'outils, chaque propriété du membre s'affiche dans une colonne.</span><span class="sxs-lookup"><span data-stu-id="543c5-126">If member properties are selected from the **Member Properties** option of the Toolbar pane, each member property is displayed as a column.</span></span>  
  
 <span data-ttu-id="543c5-127">Si le mode d'écriture différée est activé, une colonne s'affiche pour chaque colonne clé associée à l'attribut de clé dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="543c5-127">If writeback mode is enabled, one column for each key column associated with the key attribute in the dimension is displayed.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="543c5-128">Menu contextuel</span><span class="sxs-lookup"><span data-stu-id="543c5-128">Context Menu</span></span>  
 <span data-ttu-id="543c5-129">Les options suivantes sont disponibles dans le menu contextuel qui s’affiche en cliquant avec le bouton droit sur n’importe quelle partie du volet **Niveau et membres** du membre sélectionné :</span><span class="sxs-lookup"><span data-stu-id="543c5-129">The following options are available in the context menu displayed by right-clicking any part of the **Level and Members** pane for the selected member:</span></span>  
  
 <span data-ttu-id="543c5-130">**Créer frères**</span><span class="sxs-lookup"><span data-stu-id="543c5-130">**Create sibling**</span></span>  
 <span data-ttu-id="543c5-131">Crée un membre au même niveau que le membre sélectionné.</span><span class="sxs-lookup"><span data-stu-id="543c5-131">Creates a new member at the same level as the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-132">Cette option est activée uniquement si un membre est sélectionné dans un niveau autre que le niveau (Tout).</span><span class="sxs-lookup"><span data-stu-id="543c5-132">This option is enabled only if a member at a level other than the (All) level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-133">Cette option n'est disponible que si le mode d'écriture différée est activé.</span><span class="sxs-lookup"><span data-stu-id="543c5-133">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="543c5-134">**Créer enfant**</span><span class="sxs-lookup"><span data-stu-id="543c5-134">**Create child**</span></span>  
 <span data-ttu-id="543c5-135">Crée un membre enfant dans le niveau inférieur suivant du membre sélectionné.</span><span class="sxs-lookup"><span data-stu-id="543c5-135">Creates a new member at the next lower level as the selected member, as a child of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-136">Cette option est activée uniquement si un membre est sélectionné dans un niveau autre que le niveau le plus bas.</span><span class="sxs-lookup"><span data-stu-id="543c5-136">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-137">Cette option n'est disponible que si le mode d'écriture différée est activé.</span><span class="sxs-lookup"><span data-stu-id="543c5-137">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="543c5-138">**Couper**</span><span class="sxs-lookup"><span data-stu-id="543c5-138">**Cut**</span></span>  
 <span data-ttu-id="543c5-139">Copie les membres sélectionnés vers le Presse-papiers et les supprime de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="543c5-139">Copies the selected members to the clipboard and removes them from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-140">Cette option est activée uniquement si un membre est sélectionné dans un niveau autre que le membre Tout.</span><span class="sxs-lookup"><span data-stu-id="543c5-140">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-141">Cette option n'est disponible que si le mode d'écriture différée est activé.</span><span class="sxs-lookup"><span data-stu-id="543c5-141">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="543c5-142">**Coller**</span><span class="sxs-lookup"><span data-stu-id="543c5-142">**Paste**</span></span>  
 <span data-ttu-id="543c5-143">Colle les membres supprimés avec **Couper** , immédiatement après le membre sélectionné.</span><span class="sxs-lookup"><span data-stu-id="543c5-143">Pastes members previously removed using **Cut** immediately after the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-144">Cette option n'est disponible que si le mode d'écriture différée est activé.</span><span class="sxs-lookup"><span data-stu-id="543c5-144">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="543c5-145">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="543c5-145">**Delete**</span></span>  
 <span data-ttu-id="543c5-146">Supprime les membres sélectionnés de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="543c5-146">Removes the selected members from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-147">Cette option est activée uniquement si un membre est sélectionné dans un niveau autre que le membre Tout.</span><span class="sxs-lookup"><span data-stu-id="543c5-147">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-148">Cette option n'est disponible que si le mode d'écriture différée est activé.</span><span class="sxs-lookup"><span data-stu-id="543c5-148">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="543c5-149">**Renommer**</span><span class="sxs-lookup"><span data-stu-id="543c5-149">**Rename**</span></span>  
 <span data-ttu-id="543c5-150">Sélectionnez cette option pour modifier le nom du membre sélectionné.</span><span class="sxs-lookup"><span data-stu-id="543c5-150">Select to edit the name of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-151">Cette option est activée uniquement si un membre est sélectionné dans un niveau autre que le membre Tout.</span><span class="sxs-lookup"><span data-stu-id="543c5-151">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-152">Cette option n'est disponible que si le mode d'écriture différée est activé.</span><span class="sxs-lookup"><span data-stu-id="543c5-152">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="543c5-153">**Filtrer les membres**</span><span class="sxs-lookup"><span data-stu-id="543c5-153">**Filter Members**</span></span>  
 <span data-ttu-id="543c5-154">Affiche la boîte de dialogue **Filtrer les membres** pour filtrer les membres figurant dans **Niveau et membres** pour la hiérarchie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="543c5-154">Displays the **Filter Members** dialog box to filter members displayed in **Level and Members** for the selected hierarchy.</span></span> <span data-ttu-id="543c5-155">Pour plus d’informations sur la boîte de dialogue **Filtrer les membres**, consultez [Boîte de dialogue Filtrer les membres &#40;Analysis Services - Données multidimensionnelles&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="543c5-155">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="543c5-156">**Développer tout**</span><span class="sxs-lookup"><span data-stu-id="543c5-156">**Expand All**</span></span>  
 <span data-ttu-id="543c5-157">Développe tous les membres dans **Arborescence**.</span><span class="sxs-lookup"><span data-stu-id="543c5-157">Expands all members in **Tree**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="543c5-158">Cette option est activée uniquement si un membre est sélectionné dans un niveau autre que le niveau le plus bas.</span><span class="sxs-lookup"><span data-stu-id="543c5-158">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
 <span data-ttu-id="543c5-159">**Réduire tout**</span><span class="sxs-lookup"><span data-stu-id="543c5-159">**Collapse All**</span></span>  
 <span data-ttu-id="543c5-160">Réduit tous les membres dans **Arborescence**.</span><span class="sxs-lookup"><span data-stu-id="543c5-160">Collapse all members in **Tree**.</span></span>  
  
 <span data-ttu-id="543c5-161">**Développer le membre**</span><span class="sxs-lookup"><span data-stu-id="543c5-161">**Expand Member**</span></span>  
 <span data-ttu-id="543c5-162">Développe le membre sélectionné dans **Arborescence**.</span><span class="sxs-lookup"><span data-stu-id="543c5-162">Expand the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="543c5-163">**Réduire le membre**</span><span class="sxs-lookup"><span data-stu-id="543c5-163">**Collapse Member**</span></span>  
 <span data-ttu-id="543c5-164">Réduit le membre sélectionné dans **Arborescence**.</span><span class="sxs-lookup"><span data-stu-id="543c5-164">Collapse the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="543c5-165">**Écriture différée**</span><span class="sxs-lookup"><span data-stu-id="543c5-165">**Writeback**</span></span>  
 <span data-ttu-id="543c5-166">Sélectionnez cette option pour activer le mode d'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="543c5-166">Select to enable writeback mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="543c5-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="543c5-167">See Also</span></span>  
 <span data-ttu-id="543c5-168">[Barre d’outils &#40;onglet navigateur, concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="543c5-168">[Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="543c5-169">Navigateur &#40;concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="543c5-169">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
