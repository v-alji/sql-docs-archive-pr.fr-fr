---
title: Outils de calcul (onglet calculs, concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationsview.calculationtoolspane.f1
ms.assetid: b1aa8a1a-6532-45d2-8f53-d3e211d7197a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6701a15a7d773a90e48ec39dc976b9ef579c9ec8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602531"
---
# <a name="calculation-tools-calculations-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="29a46-102">Outils de calcul (onglet Calculs, Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="29a46-102">Calculation Tools (Calculations Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="29a46-103">Utilisez le volet **Outils de calcul** de l'onglet **Calculs** accessible dans le Concepteur de cube pour explorer les métadonnées, les fonctions et les modèles disponibles en vue de leur utilisation dans les calculs.</span><span class="sxs-lookup"><span data-stu-id="29a46-103">Use the **Calculation Tools** pane on the **Calculations** tab in Cube Designer to explore metadata, functions, and templates available for use in calculations.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29a46-104">Options</span><span class="sxs-lookup"><span data-stu-id="29a46-104">Options</span></span>  
 <span data-ttu-id="29a46-105">**Métadonnées**</span><span class="sxs-lookup"><span data-stu-id="29a46-105">**Metadata**</span></span>  
 <span data-ttu-id="29a46-106">Affiche les métadonnées du cube sélectionné.</span><span class="sxs-lookup"><span data-stu-id="29a46-106">Displays the metadata for the selected cube.</span></span>  
  
 <span data-ttu-id="29a46-107">Faites glisser un élément sélectionné dans le volet Éditeur de script, Éditeur de formulaire de membre calculé ou Éditeur de formulaire de jeu nommé pour inclure la syntaxe MDX (Multidimensional Expressions) de cet élément à l'emplacement sélectionné dans le volet.</span><span class="sxs-lookup"><span data-stu-id="29a46-107">Drag a selected element to the Script Editor, Calculated Member Form Editor, or Named Set Form Editor pane to include the Multidimensional Expressions (MDX) syntax for that element at the selected location in the pane.</span></span>  
  
 <span data-ttu-id="29a46-108">**Fonctions**</span><span class="sxs-lookup"><span data-stu-id="29a46-108">**Functions**</span></span>  
 <span data-ttu-id="29a46-109">Affiche les fonctions disponibles pour les expressions et les conditions.</span><span class="sxs-lookup"><span data-stu-id="29a46-109">Displays the functions available for expressions and conditions.</span></span>  
  
 <span data-ttu-id="29a46-110">Faites glisser un élément sélectionné dans le volet **Éditeur de script**, **Éditeur de formulaire de membre calculé**ou **Éditeur de formulaire de jeu nommé** pour inclure la syntaxe MDX de cet élément à l'emplacement sélectionné dans le volet.</span><span class="sxs-lookup"><span data-stu-id="29a46-110">Drag a selected element to the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29a46-111">En mode projet, la boîte de dialogue **Outils de calcul** lit les informations de cette option dans un fichier XML nommé MDXFunctions.xml inclus dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29a46-111">In project mode, the **Calculation Tools** dialog box reads information for this option from an XML file named MDXFunctions.xml, included with [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="29a46-112">En mode en ligne, les informations de cette option sont récupérées de l'ensemble de lignes du schéma MDSCHEMA_FUNCTIONS pour l'instance.</span><span class="sxs-lookup"><span data-stu-id="29a46-112">In online mode, information for this option is retrieved from the MDSCHEMA_FUNCTIONS schema rowset for the instance.</span></span>  
  
 <span data-ttu-id="29a46-113">**Modèles**</span><span class="sxs-lookup"><span data-stu-id="29a46-113">**Templates**</span></span>  
 <span data-ttu-id="29a46-114">Permet d'afficher les modèles prédéfinis disponibles aux membres calculés, aux jeux nommés et aux commandes de script.</span><span class="sxs-lookup"><span data-stu-id="29a46-114">Displays the predefined templates available for calculated members, named sets, and script commands.</span></span>  
  
 <span data-ttu-id="29a46-115">Faites glisser un élément sélectionné dans le volet **Éditeur de script**, **Éditeur de formulaire de membre calculé**ou **Éditeur de formulaire de jeu nommé** pour inclure la syntaxe MDX de cet élément à l'emplacement sélectionné dans le volet.</span><span class="sxs-lookup"><span data-stu-id="29a46-115">Drag a selected element to the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="29a46-116">Menu contextuel</span><span class="sxs-lookup"><span data-stu-id="29a46-116">Context Menu</span></span>  
 <span data-ttu-id="29a46-117">Le menu contextuel propose les options suivantes. Vous y accédez en cliquant avec le bouton droit sur un élément du volet **Outils de calcul** :</span><span class="sxs-lookup"><span data-stu-id="29a46-117">The following options are available in the context menu displayed by right-clicking an element in the **Calculation Tools** pane:</span></span>  
  
 <span data-ttu-id="29a46-118">**Copier**</span><span class="sxs-lookup"><span data-stu-id="29a46-118">**Copy**</span></span>  
 <span data-ttu-id="29a46-119">Sélectionnez cette option pour copier l'élément sélectionné dans **Métadonnées** ou **Fonctions** dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="29a46-119">Select to copy the selected element in **Metadata** or **Functions** to the Clipboard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29a46-120"> Cette option ne s'affiche pas si **Modèles** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="29a46-120">This option is not displayed if **Templates** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29a46-121"> Cette option est désactivée s'il n'est pas possible de copier le membre sélectionné (ex. le dossier **Ensembles** d'une dimension affichée dans **Métadonnées** ou le dossier de groupe de fonctions affiché dans **Fonctions**).</span><span class="sxs-lookup"><span data-stu-id="29a46-121">This option is disabled if the selected member cannot be copied, such as the **Sets** folder of a dimension displayed in **Metadata** or the function group folder for a function displayed in **Functions**.</span></span>  
  
 <span data-ttu-id="29a46-122">**Filtrer les membres**</span><span class="sxs-lookup"><span data-stu-id="29a46-122">**Filter Members**</span></span>  
 <span data-ttu-id="29a46-123">Sélectionnez cette option pour afficher la boîte de dialogue **Filtrer les membres** et filtrer les membres affichés pour l'élément sélectionné dans **Métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="29a46-123">Select to display the **Filter Members** dialog box and filter members displayed for the selected element in **Metadata**.</span></span> <span data-ttu-id="29a46-124">Pour plus d’informations sur la boîte de dialogue **Filtrer les membres**, consultez [Boîte de dialogue Filtrer les membres &#40;Analysis Services - Données multidimensionnelles&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="29a46-124">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29a46-125"> Cette option s'affiche uniquement si **Métadonnées** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="29a46-125">This option is displayed only if **Metadata** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29a46-126"> Cette option est activée uniquement si le niveau d'un attribut est sélectionné dans **Métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="29a46-126">This option is enabled only if a level for an attribute is selected in **Metadata**.</span></span>  
  
 <span data-ttu-id="29a46-127">**Ajouter un Modèle**</span><span class="sxs-lookup"><span data-stu-id="29a46-127">**Add Template**</span></span>  
 <span data-ttu-id="29a46-128">Permet d’ajouter un nouveau membre calculé, un nouveau jeu nommé ou une nouvelle commande de script sur la base du modèle sélectionné au script du cube, et d’afficher **l’Éditeur de script**, **l’Éditeur de formulaire de membre calculé**ou **l’Éditeur de formulaire de jeu nommé** selon la commande (en mode Formulaire), ou de faire défiler le contenu du volet **Éditeur de script** jusqu’à l’emplacement de la commande dans le script du cube (en mode Script).</span><span class="sxs-lookup"><span data-stu-id="29a46-128">Select to add a new calculated member, named set, or script command based on the selected template to the cube script and display the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** as appropriate for that command (in form view) or to scroll the contents of the **Script Editor** pane to the location of the command in the cube script (in script view).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29a46-129"> Cette option s'affiche uniquement si **Métadonnées** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="29a46-129">This option is displayed only if **Metadata** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29a46-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29a46-130">See Also</span></span>  
 <span data-ttu-id="29a46-131">[Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29a46-131">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="29a46-132">[Toolbar &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29a46-132">[Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="29a46-133">[Organisateur de script &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29a46-133">[Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="29a46-134">[Éditeur de formulaire de membre calculé &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29a46-134">[Calculated Member Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="29a46-135">[Éditeur de formulaire de jeu nommé &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29a46-135">[Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="29a46-136">[Éditeur de script &#40;onglet calculs, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29a46-136">[Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="29a46-137">Calculs &#40;concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="29a46-137">Calculations &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](calculations-cube-designer-analysis-services-multidimensional-data.md)  
  
  
