---
title: Action d’exploration (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10249"
- "10186"
- sql12.rtp.rptdesigner.calculatedseriesproperties.visibility.f1
- sql12.rtp.rptdesigner.seriesproperties.visibility.f1
- sql12.rtp.rptdesigner.chartareaproperties.visibility.f1
- "10092"
- sql12.rtp.rptdesigner.textboxproperties.visibility.f1
- sql12.rtp.rptdesigner.charttitleproperties.visibility.f1
- "10167"
- sql12.rtp.rptdesigner.rectangleproperties.visibility.f1
- "10174"
- sql12.rtp.rptdesigner.majorgridlineproperties.visibility.f1
- "10155"
- "10123"
- sql12.rtp.rptdesigner.subreportproperties.visibility.f1
- "10425"
- sql12.rtp.rptdesigner.minorgridlineproperties.visibility.f1
- "10217"
- sql12.rtp.rptdesigner.axisproperties.visibility.f1
- sql12.rtp.rptdesigner.serieslabelproperties.visibility.f1
- "10161"
- sql12.rtp.rptdesigner.chartproperties.visibility.f1
- sql12.rtp.rptdesigner.legendproperties.visibility.f1
- sql12.rtp.rptdesigner.pictureproperties.visibility.f1
- "10215"
- "10258"
- "10144"
- "10062"
- "10053"
ms.assetid: 1f8d1ef2-0daf-40c6-9ba7-3b391249bcd4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fe3d55dc70a606df759c049b7b147820f0e3110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613311"
---
# <a name="drilldown-action-report-builder-and-ssrs"></a><span data-ttu-id="4185a-102">Action d'exploration (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="4185a-102">Drilldown Action (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4185a-103">En fournissant des icônes plus et moins (+/-) dans une zone de texte, vous pouvez permettre aux utilisateurs de masquer et d'afficher des éléments de manière interactive.</span><span class="sxs-lookup"><span data-stu-id="4185a-103">B providing plus and minus icons on a text box, you can enable users to hide and display items interactively.</span></span> <span data-ttu-id="4185a-104">Cela s'appelle une action d' *exploration* .</span><span class="sxs-lookup"><span data-stu-id="4185a-104">This is called a *drilldown* action.</span></span> <span data-ttu-id="4185a-105">Pour une table ou une matrice, vous pouvez afficher ou masquer des colonnes et des lignes statiques ou des colonnes et des lignes qui sont associées à des groupes.</span><span class="sxs-lookup"><span data-stu-id="4185a-105">For a table or matrix, you can show or hide static rows and columns, or rows and columns that are associated with groups.</span></span>  
  
 <span data-ttu-id="4185a-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span><span class="sxs-lookup"><span data-stu-id="4185a-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span></span>  
  
 <span data-ttu-id="4185a-107">Dans cette illustration, l'utilisateur clique sur les signes plus (+) situés dans le rapport pour afficher les données de détail.</span><span class="sxs-lookup"><span data-stu-id="4185a-107">In this illustration, the user clicks the plus signs (+) in the report to show detail data.</span></span>  
  
 <span data-ttu-id="4185a-108">Par exemple, vous pouvez masquer à la base toutes les lignes sauf la ligne de synthèse d'un groupe externe dans le cadre d'une table avec des groupes de lignes.</span><span class="sxs-lookup"><span data-stu-id="4185a-108">For example, you can initially hide all the rows except the outer group summary row for a table with row groups.</span></span> <span data-ttu-id="4185a-109">Pour chaque groupe interne (y compris le groupe de détails), vous pouvez ajouter une icône Développer/Réduire à la cellule de regroupement du groupe conteneur.</span><span class="sxs-lookup"><span data-stu-id="4185a-109">For each inner group (including the details group), add an expand/collapse icon to the grouping cell of the containing group.</span></span> <span data-ttu-id="4185a-110">Lors du rendu du rapport, l'utilisateur peut cliquer sur la zone de texte pour développer ou réduire les données de détail.</span><span class="sxs-lookup"><span data-stu-id="4185a-110">When the report is rendered, the user can click the text box to expand and collapse the detail data.</span></span> <span data-ttu-id="4185a-111">Pour plus d’informations, consultez [Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4185a-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="4185a-112">Pour autoriser les utilisateurs à développer ou réduire un élément, définissez les propriétés de visibilité de cet élément.</span><span class="sxs-lookup"><span data-stu-id="4185a-112">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4185a-113">Lorsque vous créez un rapport avec une action d'exploration, les informations de visibilité doivent être définies sur le groupe, la colonne ou la ligne à masquer, et pas simplement sur une zone de texte unique dans la ligne ou la colonne.</span><span class="sxs-lookup"><span data-stu-id="4185a-113">When you create a report with a drilldown action, the visibility information must be set on the group, column, or row that you want to hide, not just a single text box in the row or column.</span></span> <span data-ttu-id="4185a-114">De plus, la zone de texte que vous utilisez pour la bascule doit figurer dans une étendue contenante qui contrôle l'élément que vous souhaitez afficher ou masquer.</span><span class="sxs-lookup"><span data-stu-id="4185a-114">In addition, the text box that you use for the toggle must be in a containing scope that controls the item that you want to show or hide.</span></span>  
>   
>  <span data-ttu-id="4185a-115">Par exemple, pour masquer une ligne associée à un groupe imbriqué, la zone de texte doit figurer dans une ligne associée au groupe parent ou à un niveau plus élevé dans la hiérarchie de la relation contenant-contenu.</span><span class="sxs-lookup"><span data-stu-id="4185a-115">For example, to hide a row associated with a nested group, the text box must be in a row associated with the parent group or higher in the containment hierarchy.</span></span>  
>   
>  <span data-ttu-id="4185a-116">Pour plus d’informations sur la configuration des informations de visibilité d’un groupe, d’une colonne ou d’une ligne, consultez [Ajouter une action Développer ou Réduire à un élément &#40;Générateur de rapports et SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4185a-116">For information on setting visibility information on the group, column or row, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="4185a-117">Pour plus d’informations sur le masquage des éléments de rapport, consultez [Masquer un élément &#40;Générateur de rapports et SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4185a-117">For more information about hiding report items, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="comparing-drilldown-and-drillthrough-reports"></a><span data-ttu-id="4185a-118">Comparaison entre les rapports d'exploration et d'extraction</span><span class="sxs-lookup"><span data-stu-id="4185a-118">Comparing Drilldown and Drillthrough Reports</span></span>  
 <span data-ttu-id="4185a-119">Dans un rapport d'extraction, un utilisateur clique sur un bouton plus ou moins afin de développer ou réduire une section d'un rapport et d'afficher les données de détail présentes.</span><span class="sxs-lookup"><span data-stu-id="4185a-119">In a drilldown report, a user clicks a plus or minus button to expand or collapse a section of a report to show detail data in place.</span></span> <span data-ttu-id="4185a-120">Dans un rapport d'extraction, l'utilisateur clique sur le lien d'une valeur de synthèse, ce qui entraîne l'ouverture d'un rapport associé distinct permettant d'afficher des données de détail.</span><span class="sxs-lookup"><span data-stu-id="4185a-120">In a drillthrough report, the user clicks a link for a summary value, and this opens a separate, related report to show detail data.</span></span> <span data-ttu-id="4185a-121">Les données de détail sont uniquement récupérées au moment de l'exécution du rapport détaillé.</span><span class="sxs-lookup"><span data-stu-id="4185a-121">The detail data is only retrieved when the detail report runs.</span></span> <span data-ttu-id="4185a-122">En règle générale, les rapports d'extraction requièrent moins de ressources que les rapports d'exploration.</span><span class="sxs-lookup"><span data-stu-id="4185a-122">Drillthrough reports typically require fewer resources than drilldown reports.</span></span> <span data-ttu-id="4185a-123">Pour plus d’informations, consultez [Extraction, exploration, sous-rapports et régions de données imbriquées &#40;Générateur de rapports et SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span><span class="sxs-lookup"><span data-stu-id="4185a-123">For more information, see [Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span></span>  
  
## <a name="rendering-extension-support-for-hidden-report-items"></a><span data-ttu-id="4185a-124">Prise en charge des extensions de rendu pour les éléments de rapport masqués</span><span class="sxs-lookup"><span data-stu-id="4185a-124">Rendering Extension Support for Hidden Report Items</span></span>  
 <span data-ttu-id="4185a-125">La bascule d'affichage/de masquage d'éléments de rapport n'est prise en charge que par les extensions de rendu gérant l'interactivité utilisateur, par exemple l'extension de rendu HTML utilisée lorsque vous exécutez un rapport dans le Générateur de rapports et le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="4185a-125">The show-and-hide toggle on report items is supported only by rendering extensions that support user interactivity, such as the HTML rendering extension that is used when you run a report in Report Builder and in Report Manager, for example.</span></span> <span data-ttu-id="4185a-126">D'autres extensions de rendu affichent des éléments masqués.</span><span class="sxs-lookup"><span data-stu-id="4185a-126">Other rendering extensions display hidden items.</span></span> <span data-ttu-id="4185a-127">La visibilité conditionnelle des éléments de rapport prise en charge est listée ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="4185a-127">The following list describes support for report items with conditional visibility:</span></span>  
  
-   <span data-ttu-id="4185a-128">En HTML, si des éléments sont masqués, ils ne sont pas visibles dans la source HTML.</span><span class="sxs-lookup"><span data-stu-id="4185a-128">In HTML, if items are hidden, they are not visible in the HTML source.</span></span>  
  
-   <span data-ttu-id="4185a-129">L'extension de rendu XML affiche tous les éléments de rapport, qu'ils soient masqués ou non.</span><span class="sxs-lookup"><span data-stu-id="4185a-129">The XML rendering extension displays all report items, regardless of whether they are hidden.</span></span>  
  
-   <span data-ttu-id="4185a-130">L'extension de rendu Excel affiche et développe les lignes et les colonnes masquées d'une table, d'une matrice ou d'une liste.</span><span class="sxs-lookup"><span data-stu-id="4185a-130">The Excel rendering extension displays and expands hidden rows and columns for a table, matrix, or list.</span></span> <span data-ttu-id="4185a-131">Toutes les lignes et les colonnes sont visibles.</span><span class="sxs-lookup"><span data-stu-id="4185a-131">All rows and columns are visible.</span></span>  
  
 <span data-ttu-id="4185a-132">Pour plus d’informations, consultez [Comportements de rendu &#40;Générateur de rapports et SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4185a-132">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4185a-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4185a-133">See Also</span></span>  
 <span data-ttu-id="4185a-134">[Extraction, exploration, sous-rapports et régions de données imbriquées &#40;Générateur de rapports et SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span><span class="sxs-lookup"><span data-stu-id="4185a-134">[Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span></span>  
 <span data-ttu-id="4185a-135">[Tri interactif, Explorateurs de documents et liens &#40;Générateur de rapports et SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4185a-135">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4185a-136">Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4185a-136">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
