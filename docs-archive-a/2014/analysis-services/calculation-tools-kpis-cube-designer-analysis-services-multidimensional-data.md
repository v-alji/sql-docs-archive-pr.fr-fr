---
title: Outils de calcul (onglet indicateurs de performance clés, concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpisview.calculationtoolspane.f1
ms.assetid: c030c725-7763-4c23-9988-4b274a88fc31
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bb8470173b0a413795fb7b5e3213bb50aa8ee43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602529"
---
# <a name="calculation-tools-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="a7a9b-102">Outils de calcul (onglet Indicateurs de performance clés, Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="a7a9b-102">Calculation Tools (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="a7a9b-103">Utilisez le volet **Outils de calcul** de l’onglet **Indicateurs de performance clés** du Concepteur de cube pour explorer les métadonnées, les fonctions et les modèles disponibles dans les indicateurs de performance clés (KPI).</span><span class="sxs-lookup"><span data-stu-id="a7a9b-103">Use the **Calculation Tools** pane on the **KPIs** tab in Cube Designer to explore metadata, functions, and templates available for use in Key Performance Indicators (KPIs).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7a9b-104">Ce volet s'affiche uniquement en mode Formulaire.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a7a9b-105">Options</span><span class="sxs-lookup"><span data-stu-id="a7a9b-105">Options</span></span>  
 <span data-ttu-id="a7a9b-106">**Métadonnées**</span><span class="sxs-lookup"><span data-stu-id="a7a9b-106">**Metadata**</span></span>  
 <span data-ttu-id="a7a9b-107">Affiche les métadonnées du cube sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-107">Displays the metadata for the selected cube.</span></span>  
  
 <span data-ttu-id="a7a9b-108">Faites glisser un élément sélectionné dans le volet **Éditeur de formulaire d’indicateur de performance clé** pour inclure la syntaxe des expressions multidimensionnelles (MDX) de cet élément à l’emplacement sélectionné dans le volet.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-108">Drag a selected element to the **KPI Form Editor** pane to include the Multidimensional Expressions (MDX) syntax for that element at the selected location in the pane.</span></span>  
  
 <span data-ttu-id="a7a9b-109">**Fonctions**</span><span class="sxs-lookup"><span data-stu-id="a7a9b-109">**Functions**</span></span>  
 <span data-ttu-id="a7a9b-110">Affiche les fonctions disponibles pour les expressions et les conditions.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-110">Displays the functions available for expressions and conditions.</span></span>  
  
 <span data-ttu-id="a7a9b-111">Faites glisser un élément sélectionné dans le volet **Éditeur de formulaire d'indicateur de performance clé** pour inclure la syntaxe MDX de cet élément à l'emplacement sélectionné dans le volet.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-111">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7a9b-112">En mode projet, la boîte de dialogue **Outils de calcul** lit les informations de cette option dans un fichier XML nommé MDXFunctions.xml inclus dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7a9b-112">In project mode, the **Calculation Tools** dialog box reads information for this option from an XML file named MDXFunctions.xml, included with [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="a7a9b-113">En mode en ligne, les informations de cette option sont récupérées de l'ensemble de lignes du schéma MDSCHEMA_FUNCTIONS pour l'instance.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-113">In online mode, information for this option is retrieved from the MDSCHEMA_FUNCTIONS schema rowset for the instance.</span></span>  
  
 <span data-ttu-id="a7a9b-114">**Modèles**</span><span class="sxs-lookup"><span data-stu-id="a7a9b-114">**Templates**</span></span>  
 <span data-ttu-id="a7a9b-115">Affiche les modèles prédéfinis disponibles pour les indicateurs de performance clés (KPI).</span><span class="sxs-lookup"><span data-stu-id="a7a9b-115">Displays the predefined templates available for KPIs.</span></span>  
  
 <span data-ttu-id="a7a9b-116">Faites glisser un élément sélectionné dans le volet **Éditeur de formulaire d'indicateur de performance clé** pour inclure la syntaxe MDX de cet élément à l'emplacement sélectionné dans le volet.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-116">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="a7a9b-117">Menu contextuel</span><span class="sxs-lookup"><span data-stu-id="a7a9b-117">Context Menu</span></span>  
 <span data-ttu-id="a7a9b-118">Le menu contextuel propose les options suivantes. Vous y accédez en cliquant avec le bouton droit sur un élément du volet **Outils de calcul** :</span><span class="sxs-lookup"><span data-stu-id="a7a9b-118">The following options are available in the context menu displayed by right-clicking an element in the **Calculation Tools** pane:</span></span>  
  
 <span data-ttu-id="a7a9b-119">**Copier**</span><span class="sxs-lookup"><span data-stu-id="a7a9b-119">**Copy**</span></span>  
 <span data-ttu-id="a7a9b-120">Sélectionnez cette option pour copier l'élément sélectionné dans **Métadonnées** ou **Fonctions** dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-120">Select to copy the selected element in **Metadata** or **Functions** to the Clipboard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7a9b-121"> Cette option ne s'affiche pas si **Modèles** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-121">This option is not displayed if **Templates** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7a9b-122"> Cette option est désactivée s'il n'est pas possible de copier le membre sélectionné (ex. le dossier **Ensembles** d'une dimension affichée dans **Métadonnées** ou le dossier de groupe de fonctions affiché dans **Fonctions**).</span><span class="sxs-lookup"><span data-stu-id="a7a9b-122">This option is disabled if the selected member cannot be copied, such as the **Sets** folder of a dimension displayed in **Metadata** or the function group folder for a function displayed in **Functions**.</span></span>  
  
 <span data-ttu-id="a7a9b-123">**Filtrer les membres**</span><span class="sxs-lookup"><span data-stu-id="a7a9b-123">**Filter Members**</span></span>  
 <span data-ttu-id="a7a9b-124">Sélectionnez cette option pour afficher la boîte de dialogue **Filtrer les membres** et filtrer les membres affichés pour l'élément sélectionné dans **Métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-124">Select to display the **Filter Members** dialog box and filter members displayed for the selected element in **Metadata**.</span></span> <span data-ttu-id="a7a9b-125">Pour plus d’informations sur la boîte de dialogue **Filtrer les membres**, consultez [Boîte de dialogue Filtrer les membres &#40;Analysis Services - Données multidimensionnelles&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="a7a9b-125">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7a9b-126"> Cette option s'affiche uniquement si **Métadonnées** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-126">This option is displayed only if **Metadata** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7a9b-127"> Cette option est activée uniquement si le niveau d'un attribut est sélectionné dans **Métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-127">This option is enabled only if a level for an attribute is selected in **Metadata**.</span></span>  
  
 <span data-ttu-id="a7a9b-128">**Ajouter un Modèle**</span><span class="sxs-lookup"><span data-stu-id="a7a9b-128">**Add Template**</span></span>  
 <span data-ttu-id="a7a9b-129">Sélectionnez un nouveau membre calculé, un ensemble nommé ou un script de commandes d’après le modèle sélectionné vers le script du cube et affichez l’ **Éditeur de formulaire d’indicateur de performance clé** en mode formulaire.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-129">Select to add a new calculated member, named set, or script command based on the selected template to the cube script and display the **KPI Form Editor** in form view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7a9b-130"> Cette option s'affiche uniquement si **Métadonnées** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7a9b-130">This option is displayed only if **Metadata** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a9b-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7a9b-131">See Also</span></span>  
 <span data-ttu-id="a7a9b-132">[Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a7a9b-132">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="a7a9b-133">[Indicateurs de performance clés &#40;&#41; &#40;concepteur de cube Analysis Services-données multidimensionnelles&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a7a9b-133">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="a7a9b-134">[Barre d’outils &#40;onglet indicateurs de performance clés, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a7a9b-134">[Toolbar &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="a7a9b-135">[Organisateur d’indicateur de performance clé &#40;onglet indicateurs de performance clés, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a7a9b-135">[KPI Organizer &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="a7a9b-136">[Éditeur de formulaire d’indicateur de performance clé &#40;onglet indicateurs de performance clés, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a7a9b-136">[KPI Form Editor &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="a7a9b-137">Explorateur d’indicateurs de performance clés &#40;onglet indicateurs de performance clés, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="a7a9b-137">KPI Browser &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpi-browser-kpis-tab-cube-designer-analysis-services-multidimensional-data.md)  
  
  
