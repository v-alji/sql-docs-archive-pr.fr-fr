---
title: Détails des traductions (onglet traductions, concepteur de dimensions) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.translations.translationpane.tranlationdetails.f1
ms.assetid: 0aa61df3-f2b0-4703-a63b-124da672dcc3
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7cbe4a3c69111d0f82f96ff5125f80fe0c2c57f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706755"
---
# <a name="translation-details-translations-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="d5f2a-102">Détails des traductions (onglet Traductions, Concepteur de dimensions) (Analysis Services - données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="d5f2a-102">Translation Details (Translations Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d5f2a-103">Le volet **Détails des traductions** de l’onglet **Traductions** du Concepteur de dimensions permet de définir et de gérer les traductions pour la dimension actuellement sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-103">Use the **Translation Details** pane on the **Translations** tab of Dimension Designer to define and manage translations for the currently selected dimension.</span></span>  
  
 <span data-ttu-id="d5f2a-104">**Pour afficher le volet Détails des traductions**</span><span class="sxs-lookup"><span data-stu-id="d5f2a-104">**To display the Translations Details pane**</span></span>  
  
1.  <span data-ttu-id="d5f2a-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis ouvrez la dimension souhaitée.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then open the dimension that you want.</span></span>  
  
2.  <span data-ttu-id="d5f2a-106">Cliquez sur l'onglet **Traductions** .</span><span class="sxs-lookup"><span data-stu-id="d5f2a-106">Click the **Translations** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5f2a-107">Options</span><span class="sxs-lookup"><span data-stu-id="d5f2a-107">Options</span></span>  
 <span data-ttu-id="d5f2a-108">**Langue par défaut**</span><span class="sxs-lookup"><span data-stu-id="d5f2a-108">**Default Language**</span></span>  
 <span data-ttu-id="d5f2a-109">Définit les noms des objets de dimension dans la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-109">Sets the names of the dimension objects in the default language.</span></span>  
  
 <span data-ttu-id="d5f2a-110">**Type d'objet**</span><span class="sxs-lookup"><span data-stu-id="d5f2a-110">**Object Type**</span></span>  
 <span data-ttu-id="d5f2a-111">Permet d'afficher la propriété à traduire.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-111">Displays the property that will be translated.</span></span> <span data-ttu-id="d5f2a-112">Seuls les objets et les propriétés, pour lesquels vous précisez des valeurs, peuvent être traduits.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-112">Only objects and properties for which values have been specified can be translated.</span></span> <span data-ttu-id="d5f2a-113">Les propriétés pouvant être traduites sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="d5f2a-113">The following properties can be translated:</span></span>  
  
-   <span data-ttu-id="d5f2a-114">Dimension</span><span class="sxs-lookup"><span data-stu-id="d5f2a-114">Dimension</span></span>  
  
     <span data-ttu-id="d5f2a-115">Propriétés `Caption` et `AttributeAllMember`</span><span class="sxs-lookup"><span data-stu-id="d5f2a-115">`Caption` and `AttributeAllMember` properties</span></span>  
  
-   <span data-ttu-id="d5f2a-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="d5f2a-116">Attribute</span></span>  
  
     <span data-ttu-id="d5f2a-117">Propriétés `Caption`, `AttributeHierarchyDisplayFolder` et `NamingTemplate`</span><span class="sxs-lookup"><span data-stu-id="d5f2a-117">`Caption`, `AttributeHierarchyDisplayFolder`, and `NamingTemplate` properties</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5f2a-118">La propriété `NamingTemplate` n'est disponible que pour les attributs parents.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-118">The `NamingTemplate` property is available only for parent attributes.</span></span>  
  
-   <span data-ttu-id="d5f2a-119">Hierarchy</span><span class="sxs-lookup"><span data-stu-id="d5f2a-119">Hierarchy</span></span>  
  
     <span data-ttu-id="d5f2a-120">Propriétés `Caption` et `AllMemberName`</span><span class="sxs-lookup"><span data-stu-id="d5f2a-120">`Caption` and `AllMemberName` properties</span></span>  
  
-   <span data-ttu-id="d5f2a-121">Level</span><span class="sxs-lookup"><span data-stu-id="d5f2a-121">Level</span></span>  
  
     <span data-ttu-id="d5f2a-122">Propriété `Caption`</span><span class="sxs-lookup"><span data-stu-id="d5f2a-122">`Caption` property</span></span>  
  
 **\<Language>**  
 <span data-ttu-id="d5f2a-123">Tapez ou sélectionnez la valeur de propriété de l'objet de dimension dans la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-123">Type or select the property value of the dimension object in the selected language.</span></span> <span data-ttu-id="d5f2a-124">Des boîtes de dialogue supplémentaires s’ouvrent quand vous cliquez sur le bouton de sélection (**...**), en fonction de la propriété en cours de modification :</span><span class="sxs-lookup"><span data-stu-id="d5f2a-124">Clicking the ellipsis button (**...**) opens additional dialog boxes, depending on the property being edited:</span></span>  
  
-   <span data-ttu-id="d5f2a-125">Propriété `NamingTemplate`</span><span class="sxs-lookup"><span data-stu-id="d5f2a-125">`NamingTemplate` property</span></span>  
  
     <span data-ttu-id="d5f2a-126">Affiche la [Boîte de dialogue Modèle de nom de niveau &#40;Analysis Services - Données multidimensionnelles&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="d5f2a-126">Displays the [Level Naming Template Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
-   <span data-ttu-id="d5f2a-127">Propriété `Caption` (pour les attributs)</span><span class="sxs-lookup"><span data-stu-id="d5f2a-127">`Caption` property (for attributes)</span></span>  
  
     <span data-ttu-id="d5f2a-128">Affiche la [Boîte de dialogue Traduction de données d’attribut &#40;Analysis Services - Données multidimensionnelles&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="d5f2a-128">Displays the [Attribute Data Translation Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="shortcut-menu"></a><span data-ttu-id="d5f2a-129">Menu contextuel</span><span class="sxs-lookup"><span data-stu-id="d5f2a-129">Shortcut Menu</span></span>  
 <span data-ttu-id="d5f2a-130">Les options suivantes sont disponibles dans le menu contextuel qui s’affiche quand vous cliquez avec le bouton droit sur une traduction dans le volet **Détails des traductions** :</span><span class="sxs-lookup"><span data-stu-id="d5f2a-130">The following options are available in the shortcut menu displayed by right-clicking a translation in the **Translation Details** pane:</span></span>  
  
 <span data-ttu-id="d5f2a-131">**Nouvelle traduction**</span><span class="sxs-lookup"><span data-stu-id="d5f2a-131">**New Translation**</span></span>  
 <span data-ttu-id="d5f2a-132">Entraîne l’ouverture de la boîte de dialogue **Sélectionnez une langue** où vous pouvez créer une traduction.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-132">Select to display the **Select Language** dialog box and create a new translation.</span></span> <span data-ttu-id="d5f2a-133">La traduction s’affiche dans une nouvelle colonne de la grille **Détails des traductions** .</span><span class="sxs-lookup"><span data-stu-id="d5f2a-133">The translation will appear as a new column in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="d5f2a-134">**Supprimer la traduction**</span><span class="sxs-lookup"><span data-stu-id="d5f2a-134">**Delete Translation**</span></span>  
 <span data-ttu-id="d5f2a-135">Permet de supprimer la traduction sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-135">Select to delete the selected translation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5f2a-136">Cette option est uniquement activée si vous avez cliqué avec le bouton droit sur une cellule pour supprimer la traduction.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-136">The option is enabled only if you right-clicked a cell to delete the translation.</span></span>  
  
 <span data-ttu-id="d5f2a-137">**Nouvelle colonne de légende**</span><span class="sxs-lookup"><span data-stu-id="d5f2a-137">**New Caption Column**</span></span>  
 <span data-ttu-id="d5f2a-138">Sélectionnez cette option pour afficher la boîte de dialogue **Traduction de données d’attribut** et définir une nouvelle colonne de légende quand vous modifiez un attribut dans la grille **Détails des traductions** .</span><span class="sxs-lookup"><span data-stu-id="d5f2a-138">Select to display the **Attribute Data Translation** dialog box and define a new caption column when you modify an attribute in the **Translation Details** grid.</span></span> <span data-ttu-id="d5f2a-139">Pour activer cette option, une cellule d'une colonne de traduction doit être sélectionnée dans la grille des **détails des traductions** .</span><span class="sxs-lookup"><span data-stu-id="d5f2a-139">To enable this option, a cell in a translation column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5f2a-140">Cette option est uniquement activée si vous avez cliqué avec le bouton droit sur une cellule pour supprimer la colonne de traduction d'un attribut.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-140">The option is enabled only if you right-clicked a cell to delete the translation column of an attribute.</span></span>  
  
 <span data-ttu-id="d5f2a-141">**Modifier la colonne de légende**</span><span class="sxs-lookup"><span data-stu-id="d5f2a-141">**Edit Caption Column**</span></span>  
 <span data-ttu-id="d5f2a-142">Sélectionnez cette option pour afficher la boîte de dialogue **Traduction de données d’attribut** et modifier une colonne de légende existante quand vous modifiez un attribut dans la grille **Détails des traductions** .</span><span class="sxs-lookup"><span data-stu-id="d5f2a-142">Select to display the **Attribute Data Translation** dialog box and modify an existing caption column when you modify an attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5f2a-143"> Pour que cette option soit activée, une cellule d'une colonne de traduction qui contient une colonne de légende doit être sélectionnée dans la grille des **détails des traductions** .</span><span class="sxs-lookup"><span data-stu-id="d5f2a-143">The option is enabled only if a cell in a translation column that contains a caption column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="d5f2a-144">**Supprimer la colonne de légende**</span><span class="sxs-lookup"><span data-stu-id="d5f2a-144">**Delete Caption Column**</span></span>  
 <span data-ttu-id="d5f2a-145">Sélectionnez cette option pour supprimer la colonne de légende pour l’attribut sélectionné dans la grille **Détails des traductions** .</span><span class="sxs-lookup"><span data-stu-id="d5f2a-145">Select to delete the caption column for the selected attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5f2a-146">Cette option est uniquement activée si vous avez cliqué avec le bouton droit sur une cellule dans une colonne de traduction qui contient une colonne de légende pour un attribut.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-146">The option is enabled only if you right-clicked a cell in a translation column that contains a caption column for an attribute.</span></span>  
  
 <span data-ttu-id="d5f2a-147">**Afficher tous les attributs**</span><span class="sxs-lookup"><span data-stu-id="d5f2a-147">**Show All Attributes**</span></span>  
 <span data-ttu-id="d5f2a-148">Sélectionnez cette option pour afficher ou masquer tous les attributs définis pour la dimension sélectionnée, notamment les attributs dont les hiérarchies sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="d5f2a-148">Select to toggle the display of all attributes defined for the selected dimension, including attributes for which attribute hierarchies are disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f2a-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5f2a-149">See Also</span></span>  
 [<span data-ttu-id="d5f2a-150">Traductions &#40;concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="d5f2a-150">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
