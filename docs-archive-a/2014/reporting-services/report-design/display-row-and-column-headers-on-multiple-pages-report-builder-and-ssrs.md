---
title: Afficher des en-têtes de ligne et de colonne sur plusieurs pages (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2422b1e2-822f-4379-9d7f-9afebb350e3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e3b38aa0faab267a0cd71feafe600829237b55c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704923"
---
# <a name="display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs"></a><span data-ttu-id="52ced-102">Afficher des en-têtes de ligne et de colonne sur plusieurs pages (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="52ced-102">Display Row and Column Headers on Multiple Pages (Report Builder and SSRS)</span></span>
  <span data-ttu-id="52ced-103">Vous pouvez décider de répéter les en-têtes de ligne et de colonne sur chaque page pour une région de données de tableau matriciel qui couvre plusieurs pages.</span><span class="sxs-lookup"><span data-stu-id="52ced-103">You can control whether to repeat row and column headers on every page for a tablix data region that spans multiple pages.</span></span> <span data-ttu-id="52ced-104">Une région de données de tableau matriciel peut être une table, une matrice ou une liste.</span><span class="sxs-lookup"><span data-stu-id="52ced-104">A tablix data region can be a table, matrix, or list.</span></span>  
  
 <span data-ttu-id="52ced-105">La façon dont vous contrôlez les lignes et les colonnes varie selon que la région de données de tableau matriciel possède ou non des en-têtes de groupes.</span><span class="sxs-lookup"><span data-stu-id="52ced-105">How you control the rows and columns depends on whether the tablix data region has group headers.</span></span> <span data-ttu-id="52ced-106">Lorsque vous cliquez dans une région de données du tableau matriciel qui possède des en-têtes de groupes, une ligne pointillée indique les zones de tableau matriciel, comme illustré sur la figure suivante :</span><span class="sxs-lookup"><span data-stu-id="52ced-106">When you click in a tablix data region that has group headers, a dotted line shows the tablix areas, as shown in the following figure:</span></span>  
  
 <span data-ttu-id="52ced-107">![Zones de régions de données de tableau matriciel](../media/rs-tablixareas.gif "Zones de régions de données de tableau matriciel")</span><span class="sxs-lookup"><span data-stu-id="52ced-107">![Tablix data region areas](../media/rs-tablixareas.gif "Tablix data region areas")</span></span>  
  
 <span data-ttu-id="52ced-108">Les en-têtes de groupe de lignes et de colonnes sont créés automatiquement lorsque vous ajoutez des groupes à l'aide de l'Assistant Nouveau tableau ou nouvelle matrice ou de l'Assistant Nouveau graphique, en ajoutant des champs au volet Regroupement ou à l'aide des menus contextuels.</span><span class="sxs-lookup"><span data-stu-id="52ced-108">Row and column group headers are created automatically when you add groups by using the New Table or Matrix wizard or the New Chart wizard, by adding fields to the Grouping pane, or by using context menus.</span></span> <span data-ttu-id="52ced-109">Si la région de données de tableau matriciel ne possède qu'un corps de tableau matriciel et aucun en-tête de groupe, les lignes et colonnes sont des membres du tableau matriciel.</span><span class="sxs-lookup"><span data-stu-id="52ced-109">If the tablix data region has only a tablix body area and no group headers, the rows and columns are tablix members.</span></span>  
  
 <span data-ttu-id="52ced-110">Pour les membres statiques, vous pouvez afficher les lignes supérieures adjacentes ou les colonnes latérales adjacentes sur plusieurs pages.</span><span class="sxs-lookup"><span data-stu-id="52ced-110">For static members, you can display the top adjacent rows or the side adjacent columns on multiple pages.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-row-headers-on-multiple-pages"></a><span data-ttu-id="52ced-111">Pour afficher les en-têtes de ligne sur plusieurs pages</span><span class="sxs-lookup"><span data-stu-id="52ced-111">To display row headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="52ced-112">Cliquez avec le bouton droit sur la ligne, la colonne ou la poignée d’angle d’une région de données de tableau matriciel, puis sélectionnez **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="52ced-112">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="52ced-113">Dans **En-têtes de lignes**, sélectionnez **Répéter les lignes d'en-tête sur chaque page**.</span><span class="sxs-lookup"><span data-stu-id="52ced-113">In **Row Headers**, select **Repeat header rows on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-column-headers-on-multiple-pages"></a><span data-ttu-id="52ced-114">Pour afficher les en-têtes de colonne sur plusieurs pages</span><span class="sxs-lookup"><span data-stu-id="52ced-114">To display column headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="52ced-115">Cliquez avec le bouton droit sur la ligne, la colonne ou la poignée d’angle d’une région de données de tableau matriciel, puis sélectionnez **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="52ced-115">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="52ced-116">Dans **En-têtes de colonnes**, sélectionnez **Répéter les colonnes d'en-tête sur chaque page**.</span><span class="sxs-lookup"><span data-stu-id="52ced-116">In **Column Headers**, select **Repeat header columns on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-a-static-tablix-member-row-or-column-on-multiple-pages"></a><span data-ttu-id="52ced-117">Pour afficher un membre de tableau matriciel statique (ligne ou colonne) sur plusieurs pages</span><span class="sxs-lookup"><span data-stu-id="52ced-117">To display a static tablix member (row or column) on multiple pages</span></span>  
  
1.  <span data-ttu-id="52ced-118">Dans l'aire de conception, cliquez sur la poignée de ligne ou de colonne de la région de données du tableau matriciel pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="52ced-118">On the design surface, click the row or column handle of the tablix data region to select it.</span></span> <span data-ttu-id="52ced-119">Le volet Regroupement affiche les groupes de lignes et de colonnes.</span><span class="sxs-lookup"><span data-stu-id="52ced-119">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="52ced-120">Dans la partie droite du volet de regroupement, cliquez sur la flèche orientée vers le bas, puis sur **Mode avancé**.</span><span class="sxs-lookup"><span data-stu-id="52ced-120">On the right side of the Grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span> <span data-ttu-id="52ced-121">Le volet Groupes de lignes affiche les membres statiques et dynamiques hiérarchiques pour la hiérarchie de groupes de lignes et le volet Groupes de colonnes affiche une vue semblable pour la hiérarchie de groupes de colonnes.</span><span class="sxs-lookup"><span data-stu-id="52ced-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
3.  <span data-ttu-id="52ced-122">Cliquez sur le membre statique correspondant au membre statique (ligne ou colonne) qui doit rester visible pendant le défilement.</span><span class="sxs-lookup"><span data-stu-id="52ced-122">Click the static member that corresponds to the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="52ced-123">Le volet Propriétés affiche les propriétés du **membre du tableau matriciel** .</span><span class="sxs-lookup"><span data-stu-id="52ced-123">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="52ced-124">Si vous ne voyez pas le volet Propriétés, cliquez sur l’onglet **Affichage** en haut de la fenêtre du Générateur de rapports, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="52ced-124">If you don't see the Properties pane, click the **View** tab at the top of the Report Builder window and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="52ced-125">Dans le volet Propriétés, affectez à **RepeatOnNewPage** la valeur True.</span><span class="sxs-lookup"><span data-stu-id="52ced-125">In the Properties pane, set **RepeatOnNewPage** to True.</span></span>  
  
5.  <span data-ttu-id="52ced-126">Définissez **KeepWithGroup** à Après.</span><span class="sxs-lookup"><span data-stu-id="52ced-126">Set **KeepWithGroup** to After.</span></span>  
  
6.  <span data-ttu-id="52ced-127">Renouvelez cette opération pour tous les membres adjacents à répéter.</span><span class="sxs-lookup"><span data-stu-id="52ced-127">Repeat this for as many adjacent members as you want to repeat.</span></span>  
  
7.  <span data-ttu-id="52ced-128">Affichez l'aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="52ced-128">Preview the report.</span></span>  
  
 <span data-ttu-id="52ced-129">En consultant chacune des pages du rapport sur lesquelles la région de données du tableau matriciel s'étend, vous pouvez constater que les membres statiques du tableau matriciel se répètent sur chaque page.</span><span class="sxs-lookup"><span data-stu-id="52ced-129">As you view each page of the report that the tablix data region spans, the static tablix members repeat on each page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ced-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52ced-130">See Also</span></span>  
 <span data-ttu-id="52ced-131">[Recherche, affichage et gestion des rapports &#40;Générateur de rapports et SSRS&#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52ced-131">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="52ced-132">[Exportation de rapports &#40;Générateur de rapports et SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52ced-132">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="52ced-133">[Contrôle des sauts de page, des en-têtes, des colonnes et des lignes &#40;Générateur de rapports et SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52ced-133">[Controlling Page Breaks, Headings, Columns, and Rows &#40;Report Builder and SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="52ced-134">[Afficher des en-têtes et des pieds de page de groupe &#40;Générateur de rapports et SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52ced-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="52ced-135">Laisser les en-têtes visibles lors du défilement d’un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="52ced-135">Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;</span></span>](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md)  
  
  
