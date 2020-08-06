---
title: Calculs (Concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationsview.f1
ms.assetid: 46e2fbe2-bb41-4eaa-91f8-eb2bd3b8d00d
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdbc35a8e47557923b90cda4e72280c3cca940dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603159"
---
# <a name="calculations-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="e7fe2-102">Calculs (Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="e7fe2-102">Calculations (Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e7fe2-103">Utilisez l’onglet **Calculs** dans le Concepteur de cube pour afficher ou modifier les calculs, y compris les membres calculés, les jeux nommés et les commandes de script MDX (Multidimensional Expressions) du cube sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e7fe2-103">Use the **Calculations** tab in Cube Designer to view and edit calculations, including calculated members, named sets, and Multidimensional Expressions (MDX) script commands for the selected cube.</span></span>  
  
## <a name="form-view-and-script-view"></a><span data-ttu-id="e7fe2-104">Mode Formulaire et Mode Script</span><span class="sxs-lookup"><span data-stu-id="e7fe2-104">Form View and Script View</span></span>  
 <span data-ttu-id="e7fe2-105">L'onglet **Calculs** permet d'utiliser deux modes d'affichage et de modification des calculs :</span><span class="sxs-lookup"><span data-stu-id="e7fe2-105">The **Calculations** tab supports two different views when viewing or editing calculations:</span></span>  
  
-   <span data-ttu-id="e7fe2-106">Mode Formulaire</span><span class="sxs-lookup"><span data-stu-id="e7fe2-106">Form view</span></span>  
  
     <span data-ttu-id="e7fe2-107">Ce mode affiche une vue organisée des membres calculés, des jeux nommés et des commandes de script contenus dans le script MDX associé au cube, et fournit un éditeur de formulaires pour afficher et modifier les membres calculés et les jeux nommés, et afficher les métadonnées, les fonctions et les outils disponibles dans le cube.</span><span class="sxs-lookup"><span data-stu-id="e7fe2-107">This view displays an organized view of the calculated members, named sets, and script commands contained in the MDX script associated with the cube and provides form editors to view and edit calculated members and named sets, as well as displaying the metadata, functions, and tools available to the cube.</span></span>  
  
-   <span data-ttu-id="e7fe2-108">Mode Script</span><span class="sxs-lookup"><span data-stu-id="e7fe2-108">Script view</span></span>  
  
     <span data-ttu-id="e7fe2-109">Pour les utilisateurs avancés, cette vue affiche l'ensemble du script MDX associé au cube, ainsi que les métadonnées, les fonctions et les outils disponibles pour le cube.</span><span class="sxs-lookup"><span data-stu-id="e7fe2-109">For advanced users, this view displays the entire MDX script associated with the cube, as well as displaying the metadata, functions, and tools available to the cube.</span></span>  
  
## <a name="panes"></a><span data-ttu-id="e7fe2-110">Volets</span><span class="sxs-lookup"><span data-stu-id="e7fe2-110">Panes</span></span>  
 <span data-ttu-id="e7fe2-111">**Barre d’outils**</span><span class="sxs-lookup"><span data-stu-id="e7fe2-111">**Toolbar**</span></span>  
 <span data-ttu-id="e7fe2-112">Utilisez la barre d’outils en mode formulaire et script pour effectuer des opérations courantes dans cet onglet. Pour plus d’informations sur ce volet, consultez [barre d’outils &#40;l’onglet calculs, concepteur de Cube&#41; &#40;Analysis Services-&#41;de données multidimensionnelles ](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e7fe2-112">Use the toolbar in both form view and script view to perform common operations on this tab. For more information about this pane, see [Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e7fe2-113">**Organisateur de script**</span><span class="sxs-lookup"><span data-stu-id="e7fe2-113">**Script Organizer**</span></span>  
 <span data-ttu-id="e7fe2-114">Utilisez le volet **Organisateur de script** en mode Formulaire pour afficher le contenu du cube dans un format ordonné.</span><span class="sxs-lookup"><span data-stu-id="e7fe2-114">Use the **Script Organizer** pane in form view to display the contents of the cube script in an ordered format.</span></span> <span data-ttu-id="e7fe2-115">Pour plus d’informations sur ce volet, consultez [Organisateur de script &#40;onglet Calculs, Concepteur de cube&#41; &#40;Analysis Services - Données multidimensionnelles&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e7fe2-115">For more information about this pane, see [Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e7fe2-116">**Outils de calcul**</span><span class="sxs-lookup"><span data-stu-id="e7fe2-116">**Calculation Tools**</span></span>  
 <span data-ttu-id="e7fe2-117">Utilisez le volet **Outils de calcul** en mode Formulaire et Script pour afficher les métadonnées, les fonctions et les outils disponibles pour le cube.</span><span class="sxs-lookup"><span data-stu-id="e7fe2-117">Use the **Calculation Tools** pane in both form view and script view to display metadata, functions, and tools available to the cube.</span></span> <span data-ttu-id="e7fe2-118">Pour plus d’informations sur ce volet, consultez [Outils de calcul &#40;onglet Calculs, Concepteur de cube&#41; &#40;Analysis Services - Données multidimensionnelles&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e7fe2-118">For more information about this pane, see [Calculation Tools &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e7fe2-119">**Éditeur de script**</span><span class="sxs-lookup"><span data-stu-id="e7fe2-119">**Script Editor**</span></span>  
 <span data-ttu-id="e7fe2-120">Utilisez le volet **Éditeur de script** en mode Script pour modifier l’ensemble du script du cube, et en mode Formulaire pour modifier les commandes du script du cube.</span><span class="sxs-lookup"><span data-stu-id="e7fe2-120">Use the **Script Editor** pane in script view to edit the entire cube script and in form view to edit script commands contained in the cube script.</span></span> <span data-ttu-id="e7fe2-121">Pour plus d’informations sur ce volet, consultez [Éditeur de script &#40;onglet Calculs, Concepteur de cube&#41; &#40;Analysis Services - Données multidimensionnelles&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e7fe2-121">For more information about this pane, see [Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e7fe2-122">**Éditeur de formulaire de membre calculé**</span><span class="sxs-lookup"><span data-stu-id="e7fe2-122">**Calculated Member Form Editor**</span></span>  
 <span data-ttu-id="e7fe2-123">Utilisez le volet **Éditeur de formulaire de membre calculé** en mode Formulaire pour modifier les membres calculés du script du cube.</span><span class="sxs-lookup"><span data-stu-id="e7fe2-123">Use the **Calculated Member Form Editor** pane in form view to edit calculated members in the cube script.</span></span> <span data-ttu-id="e7fe2-124">Pour plus d’informations sur ce volet, consultez [Éditeur de formulaire de membre calculé &#40;onglet Calculs, Concepteur de cube&#41; &#40;Analysis Services - Données multidimensionnelles&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e7fe2-124">For more information about this pane, see [Calculated Member Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e7fe2-125">**Éditeur de formulaire de jeu nommé**</span><span class="sxs-lookup"><span data-stu-id="e7fe2-125">**Named Set Form Editor**</span></span>  
 <span data-ttu-id="e7fe2-126">Utilisez le volet **Éditeur de formulaire de jeu nommé** en mode Formulaire pour modifier les jeux nommés du script du cube.</span><span class="sxs-lookup"><span data-stu-id="e7fe2-126">Use the **Named Set Form Editor** pane in form view to edit named sets in the cube script.</span></span> <span data-ttu-id="e7fe2-127">Pour plus d’informations sur ce volet, consultez [Éditeur de formulaire de jeu nommé &#40;onglet Calculs, Concepteur de cube&#41; &#40;Analysis Services - Données multidimensionnelles&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e7fe2-127">For more information about this pane, see [Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7fe2-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7fe2-128">See Also</span></span>  
 <span data-ttu-id="e7fe2-129">[Objets de cube &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e7fe2-129">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e7fe2-130">[Touchant](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="e7fe2-130">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="e7fe2-131">[Notions de base de l’écriture de scripts MDX &#40;Analysis Services&#41;](multidimensional-models/mdx/mdx-scripting-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e7fe2-131">[MDX Scripting Fundamentals &#40;Analysis Services&#41;](multidimensional-models/mdx/mdx-scripting-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="e7fe2-132">[Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e7fe2-132">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e7fe2-133">Créer des jeux nommés</span><span class="sxs-lookup"><span data-stu-id="e7fe2-133">Create Named Sets</span></span>](multidimensional-models/create-named-sets.md)  
  
  
