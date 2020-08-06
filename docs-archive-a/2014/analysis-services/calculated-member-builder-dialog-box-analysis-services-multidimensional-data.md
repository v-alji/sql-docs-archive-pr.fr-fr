---
title: Générateur de membres calculés, boîte de dialogue (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.calculatedmemberbuilderdialog.f1
ms.assetid: 73b89a9f-f403-4ab8-99f7-e3ceb870c260
author: minewiskan
ms.author: owend
ms.openlocfilehash: 240e2f2471bf77c403119fd51278a975badc8358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602543"
---
# <a name="calculated-member-builder-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="6308d-102">Boîte de dialogue Générateur de membres calculés (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="6308d-102">Calculated Member Builder Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="6308d-103">Utilisez la boîte de dialogue **Générateur de membres calculés** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour créer un membre calculé.</span><span class="sxs-lookup"><span data-stu-id="6308d-103">Use the **Calculated Member Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to build a calculated member.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6308d-104">Options</span><span class="sxs-lookup"><span data-stu-id="6308d-104">Options</span></span>  
  
|<span data-ttu-id="6308d-105">Terme</span><span class="sxs-lookup"><span data-stu-id="6308d-105">Term</span></span>|<span data-ttu-id="6308d-106">Définition</span><span class="sxs-lookup"><span data-stu-id="6308d-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="6308d-107">**Nom**</span><span class="sxs-lookup"><span data-stu-id="6308d-107">**Name**</span></span>|<span data-ttu-id="6308d-108">Tapez le nom du membre calculé.</span><span class="sxs-lookup"><span data-stu-id="6308d-108">Type the name of the calculated member.</span></span>|  
|<span data-ttu-id="6308d-109">**Hiérarchie parente**</span><span class="sxs-lookup"><span data-stu-id="6308d-109">**Parent Hierarchy**</span></span>|<span data-ttu-id="6308d-110">Sélectionnez la hiérarchie parente dans laquelle créer le membre calculé.</span><span class="sxs-lookup"><span data-stu-id="6308d-110">Select the hierarchy in which to create the calculated member.</span></span>|  
|<span data-ttu-id="6308d-111">**Membre parent**</span><span class="sxs-lookup"><span data-stu-id="6308d-111">**Parent Member**</span></span>|<span data-ttu-id="6308d-112">Cette option est activée si vous sélectionnez une hiérarchie parente (différente de la dimension `Measures`) à plusieurs niveaux.</span><span class="sxs-lookup"><span data-stu-id="6308d-112">This option is enabled if you select a parent hierarchy (other than the `Measures` dimension) that has more than one level.</span></span> <span data-ttu-id="6308d-113">Cliquez sur le bouton de sélection (**...**) pour sélectionner un membre parent.</span><span class="sxs-lookup"><span data-stu-id="6308d-113">Click the ellipsis (**...**) button to select a parent member.</span></span> <span data-ttu-id="6308d-114">Le membre parent détermine l'emplacement du membre calculé dans la structure de dimension.</span><span class="sxs-lookup"><span data-stu-id="6308d-114">The parent member determines the location of the calculated member in the dimension structure.</span></span>|  
|<span data-ttu-id="6308d-115">**Expression**</span><span class="sxs-lookup"><span data-stu-id="6308d-115">**Expression**</span></span>|<span data-ttu-id="6308d-116">Tapez l'expression MDX à utiliser.</span><span class="sxs-lookup"><span data-stu-id="6308d-116">Type the MDX expression that will be used.</span></span>|  
|<span data-ttu-id="6308d-117">**Vérification**</span><span class="sxs-lookup"><span data-stu-id="6308d-117">**Check**</span></span>|<span data-ttu-id="6308d-118">Teste \*\*\*\* l'expression MDX définie dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="6308d-118">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="6308d-119">**Métadonnées**</span><span class="sxs-lookup"><span data-stu-id="6308d-119">**Metadata**</span></span>|<span data-ttu-id="6308d-120">Affiche les métadonnées de l'objet actif [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qu'il est possible d'inclure dans l'expression MDX définie dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="6308d-120">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="6308d-121">Pour copier la syntaxe MDX de l’élément sélectionné, cliquez sur l’élément avec le bouton droit et sélectionnez **Copier**ou faites glisser l’élément sélectionné vers **Expression**.</span><span class="sxs-lookup"><span data-stu-id="6308d-121">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="6308d-122">**Fonctions**</span><span class="sxs-lookup"><span data-stu-id="6308d-122">**Functions**</span></span>|<span data-ttu-id="6308d-123">Affiche les fonctions MDX disponibles dans l'instance active [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6308d-123">Displays the available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="6308d-124">La liste des éléments est extraite de l'ensemble de lignes du schéma MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="6308d-124">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="6308d-125">Pour copier la syntaxe MDX de l’élément sélectionné, cliquez sur l’élément avec le bouton droit et sélectionnez **Copier**ou faites glisser l’élément sélectionné vers **Expression**.</span><span class="sxs-lookup"><span data-stu-id="6308d-125">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6308d-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6308d-126">See Also</span></span>  
 [<span data-ttu-id="6308d-127">Référence MDX &#40;Multidimensional Expressions&#41;</span><span class="sxs-lookup"><span data-stu-id="6308d-127">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
