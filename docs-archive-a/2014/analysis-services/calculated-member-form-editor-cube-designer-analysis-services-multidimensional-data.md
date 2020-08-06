---
title: Éditeur de formulaire de membre calculé (onglet calculs, concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationexpression.calculatedmember.f1
ms.assetid: f7719b9e-b1e6-4792-90a6-30d9d8eb1196
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dd45ece03fd81e0e7356e7bdcd0ec8dc53287bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602541"
---
# <a name="calculated-member-form-editor-calculations-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="0aaf9-102">Éditeur de formulaire de membre calculé (onglet Calculs, Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="0aaf9-102">Calculated Member Form Editor (Calculations Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="0aaf9-103">Utilisez le volet **Éditeur de formulaire de membre calculé** de l'onglet **Calculs** dans le Concepteur de cube pour créer et modifier un membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-103">Use the **Calculated Member Form Editor** pane on the **Calculations** tab in Cube Designer to create or modify a calculated member.</span></span>  
  
 <span data-ttu-id="0aaf9-104">**Remarque** Ce volet s'affiche uniquement en mode Formulaire.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-104">**Note** This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0aaf9-105">Options</span><span class="sxs-lookup"><span data-stu-id="0aaf9-105">Options</span></span>  
 <span data-ttu-id="0aaf9-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-106">**Name**</span></span>  
 <span data-ttu-id="0aaf9-107">Tapez le nom du membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-107">Type the name of the calculated member.</span></span>  
  
 <span data-ttu-id="0aaf9-108">**Propriétés parentes**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-108">**Parent Properties**</span></span>  
 <span data-ttu-id="0aaf9-109">Développez cette branche pour afficher les options **Hiérarchie parente**, **Membre parent**et **Modifier** .</span><span class="sxs-lookup"><span data-stu-id="0aaf9-109">Expand to view the **Parent hierarchy**, **Parent member**, and **Change** options.</span></span>  
  
 <span data-ttu-id="0aaf9-110">**Hiérarchie parente**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-110">**Parent hierarchy**</span></span>  
 <span data-ttu-id="0aaf9-111">Sélectionnez dans le cube sélectionné la dimension et la hiérarchie à inclure dans le membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-111">Select the dimension and hierarchy in the selected cube that is to include the calculated member.</span></span> <span data-ttu-id="0aaf9-112">Sélectionnez MESURES pour définir une mesure calculée.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-112">Select MEASURES to define a calculated measure.</span></span>  
  
 <span data-ttu-id="0aaf9-113">**Membre parent**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-113">**Parent member**</span></span>  
 <span data-ttu-id="0aaf9-114">Sélectionnez le membre parent sous lequel le membre calculé doit apparaître.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-114">Select the member beneath which the calculated member is to appear.</span></span>  
  
 <span data-ttu-id="0aaf9-115">**Remarque** Cette option est disponible si **Hiérarchie parente** spécifie une hiérarchie différente de MESURES.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-115">**Note** This option is available if **Parent hierarchy** specifies a hierarchy other than MEASURES.</span></span>  
  
 <span data-ttu-id="0aaf9-116">**Changement**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-116">**Change**</span></span>  
 <span data-ttu-id="0aaf9-117">Affiche la boîte de dialogue **Sélectionnez le membre parent** pour choisir un **Membre parent**.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-117">Select to display the **Select Parent Member** dialog box and choose a member for **Parent member**.</span></span> <span data-ttu-id="0aaf9-118">Pour plus d’informations sur la boîte de dialogue **Sélectionnez le membre parent**, consultez [Boîte de dialogue Sélectionnez le membre parent &#40;Analysis Services - Données multidimensionnelles&#41;](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="0aaf9-118">For more information about the **Select Parent Member** dialog box, see [Select Parent Member Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="0aaf9-119">**Expression**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-119">**Expression**</span></span>  
 <span data-ttu-id="0aaf9-120">Développez cette branche pour afficher ou modifier l'expression MDX (Multidimensional Expressions) du membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-120">Expand to view or edit the Multidimensional Expressions (MDX) expression for the calculated member.</span></span>  
  
 <span data-ttu-id="0aaf9-121">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-121">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0aaf9-122">Il est recommandé que cette expression soit évaluée à une chaîne de caractères ou une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-122">It is recommended that this expression evaluate to a string or to a numeric value.</span></span>  
  
 <span data-ttu-id="0aaf9-123">**Propriétés supplémentaires**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-123">**Additional Properties**</span></span>  
 <span data-ttu-id="0aaf9-124">Développez cette branche pour afficher les options **Chaîne de format**, **Visible**, **Comportement non vide**, **Expressions de couleur**et **Expressions de police** .</span><span class="sxs-lookup"><span data-stu-id="0aaf9-124">Expand to view the **Format string**, **Visible**, **Non-empty behavior**, **Color Expressions**, and **Font Expressions** options.</span></span>  
  
 <span data-ttu-id="0aaf9-125">**Chaîne de format**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-125">**Format string**</span></span>  
 <span data-ttu-id="0aaf9-126">Tapez la chaîne de format MDX utilisée pour mettre en forme la valeur retournée par le membre calculé ou sélectionnez une chaîne de format prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-126">Type the MDX format string used to format the value returned by the calculated member, or select a predefined format string.</span></span>  
  
 <span data-ttu-id="0aaf9-127">Pour plus d’informations sur les chaînes de format MDX, consultez [Contenu de FORMAT_STRING &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span><span class="sxs-lookup"><span data-stu-id="0aaf9-127">For more information about MDX format strings, see [FORMAT_STRING Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span></span>  
  
 <span data-ttu-id="0aaf9-128">**Parent**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-128">**Visible**</span></span>  
 <span data-ttu-id="0aaf9-129">Sélectionnez **True** pour que le membre calculé soit visible dans les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-129">Select **True** to allow the calculated member to be visible to client applications.</span></span>  
  
 <span data-ttu-id="0aaf9-130">**Comportement non vide**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-130">**Non-empty behavior**</span></span>  
 <span data-ttu-id="0aaf9-131">Sélectionnez le nom de la mesure utilisée pour résoudre les requêtes NON EMPTY dans la chaîne MDX du membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-131">Select the name of the measure used to resolve NON EMPTY queries in MDX for the calculated member.</span></span> <span data-ttu-id="0aaf9-132">Si la propriété **Comportement non vide** est vide, le membre calculé doit être évalué à plusieurs reprises pour déterminer si un membre est vide.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-132">If the **Non Empty Behavior** property is blank, the calculated member must be evaluated repeatedly to determine if a member is empty.</span></span> <span data-ttu-id="0aaf9-133">Si la propriété **Comportement non vide** contient le nom d'une mesure, le membre calculé est considéré comme vide si la mesure spécifiée est vide.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-133">If the **Non Empty Behavior** property contains the name of a measure, the calculated member is treated as empty if the specified measure is empty.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0aaf9-134">Cette propriété est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-134">This property is deprecated.</span></span> <span data-ttu-id="0aaf9-135">Évitez de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-135">Avoid setting it.</span></span> <span data-ttu-id="0aaf9-136">Pour plus d’informations, consultez [fonctionnalités de Analysis Services dépréciées dans SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) .</span><span class="sxs-lookup"><span data-stu-id="0aaf9-136">See [Deprecated Analysis Services Features in SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) for details.</span></span>  
  
 <span data-ttu-id="0aaf9-137">**Expressions de couleur**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-137">**Color Expressions**</span></span>  
 <span data-ttu-id="0aaf9-138">Développez cette branche pour afficher les options **Couleur avant** et **Couleur d’arrière-plan** .</span><span class="sxs-lookup"><span data-stu-id="0aaf9-138">Expand to view the **Fore color** and **Back color** options.</span></span>  
  
 <span data-ttu-id="0aaf9-139">**Couleur avant**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-139">**Fore color**</span></span>  
 <span data-ttu-id="0aaf9-140">Tapez l'expression MDX qui fournit la couleur de premier plan du membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-140">Type the MDX expression that provides the foreground color of the calculated member.</span></span>  
  
 <span data-ttu-id="0aaf9-141">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-141">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0aaf9-142">Cliquez sur le bouton de sélection des couleurs pour afficher la boîte de dialogue **Couleur** et insérer la valeur RVB (rouge/vert/bleu) d’une couleur spécifiée dans l’expression MDX.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-142">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="0aaf9-143">Pour plus d’informations sur les valeurs RVB, consultez [Contenu de FORE_COLOR et BACK_COLOR &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="0aaf9-143">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="0aaf9-144">**Couleur d’arrière-plan**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-144">**Back color**</span></span>  
 <span data-ttu-id="0aaf9-145">Tapez l'expression MDX qui fournit la couleur d'arrière-plan du membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-145">Type the MDX expression that provides the background color of the calculated member.</span></span>  
  
 <span data-ttu-id="0aaf9-146">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-146">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0aaf9-147">Cliquez sur le bouton de sélection des couleurs pour afficher la boîte de dialogue **Couleur** et insérer la valeur RVB (rouge/vert/bleu) d’une couleur spécifiée dans l’expression MDX.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-147">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="0aaf9-148">Pour plus d’informations sur les valeurs RVB, consultez [Contenu de FORE_COLOR et BACK_COLOR &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="0aaf9-148">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="0aaf9-149">**Expressions de police**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-149">**Font Expressions**</span></span>  
 <span data-ttu-id="0aaf9-150">Développez cette branche pour afficher les options **Nom de police**, **Taille de police**et **Indicateurs de police** .</span><span class="sxs-lookup"><span data-stu-id="0aaf9-150">Expand to view the **Font name**, **Font size**, and **Font flags** options.</span></span>  
  
 <span data-ttu-id="0aaf9-151">**Nom de la police**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-151">**Font name**</span></span>  
 <span data-ttu-id="0aaf9-152">Tapez l'expression MDX qui fournit le nom de la police utilisée pour le membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-152">Type the MDX expression that provides the name of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="0aaf9-153">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0aaf9-154">Cliquez sur le bouton de sélection pour afficher la boîte de dialogue **Police** et insérer les valeurs des propriétés d'une police spécifiée dans l'expression MDX.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-154">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="0aaf9-155">Pour plus d’informations sur les valeurs des propriétés, consultez [Création et utilisation de valeurs de propriétés &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="0aaf9-155">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="0aaf9-156">**Taille de police**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-156">**Font size**</span></span>  
 <span data-ttu-id="0aaf9-157">Tapez l'expression MDX qui fournit la taille de la police utilisée pour le membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-157">Type the MDX expression that provides the size of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="0aaf9-158">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-158">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0aaf9-159">Cliquez sur le bouton de sélection pour afficher la boîte de dialogue **Police** et insérer les valeurs des propriétés d'une police spécifiée dans l'expression MDX.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-159">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="0aaf9-160">Pour plus d’informations sur les valeurs des propriétés, consultez [Création et utilisation de valeurs de propriétés &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="0aaf9-160">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="0aaf9-161">**Indicateurs de police**</span><span class="sxs-lookup"><span data-stu-id="0aaf9-161">**Font flags**</span></span>  
 <span data-ttu-id="0aaf9-162">Tapez l'expressionDX qui fournit la valeur bitmap qui contient les attributs (ex. souligné ou gras) de la police utilisée pour le membre calculé.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-162">Type the MDX expression that provides the bitmapped value containing the font flags, such as underline or bold, of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="0aaf9-163">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-163">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0aaf9-164">Cliquez sur le bouton de sélection pour afficher la boîte de dialogue **Police** et insérer les valeurs des propriétés d'une police spécifiée dans l'expression MDX.</span><span class="sxs-lookup"><span data-stu-id="0aaf9-164">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="0aaf9-165">Pour plus d’informations sur les valeurs des propriétés, consultez [Création et utilisation de valeurs de propriétés &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="0aaf9-165">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aaf9-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0aaf9-166">See Also</span></span>  
 <span data-ttu-id="0aaf9-167">[Touchant](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="0aaf9-167">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="0aaf9-168">[Créer des membres calculés](multidimensional-models/create-calculated-members.md) </span><span class="sxs-lookup"><span data-stu-id="0aaf9-168">[Create Calculated Members](multidimensional-models/create-calculated-members.md) </span></span>  
 <span data-ttu-id="0aaf9-169">[Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0aaf9-169">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0aaf9-170">[Calculs &#40;concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0aaf9-170">[Calculations &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0aaf9-171">[Toolbar &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0aaf9-171">[Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0aaf9-172">[Organisateur de script &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0aaf9-172">[Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0aaf9-173">[Outils de calcul &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0aaf9-173">[Calculation Tools &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0aaf9-174">[Éditeur de formulaire de jeu nommé &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0aaf9-174">[Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="0aaf9-175">Éditeur de script &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="0aaf9-175">Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md)  
  
  
