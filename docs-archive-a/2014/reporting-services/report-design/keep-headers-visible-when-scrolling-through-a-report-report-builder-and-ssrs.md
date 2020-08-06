---
title: Laisser les en-têtes visibles lors du défilement d’un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6d9192a4-fd5c-41ad-b9ef-f88f9496afed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d37fcd38a402dc0f88ac002c679c1046d5b0b583
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707096"
---
# <a name="keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs"></a><span data-ttu-id="73649-102">Laisser les en-têtes visibles lors du défilement d'un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="73649-102">Keep Headers Visible When Scrolling Through a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="73649-103">Pour empêcher les étiquettes de lignes et de colonnes de disparaître de l'écran après le rendu d'un rapport, vous pouvez figer les en-têtes de lignes ou de colonnes.</span><span class="sxs-lookup"><span data-stu-id="73649-103">To prevent row and column labels from scrolling out of view after rendering a report, you can freeze the row or column headings.</span></span>  
  
 <span data-ttu-id="73649-104">La façon de contrôler les lignes et les colonnes varie selon que vous disposez d'une table ou d'une matrice.</span><span class="sxs-lookup"><span data-stu-id="73649-104">How you control the rows and columns depends on whether you have a table or a matrix.</span></span> <span data-ttu-id="73649-105">Si vous avez une table, vous configurez les membres statiques (en-têtes de colonnes et de lignes) pour qu'ils restent visibles.</span><span class="sxs-lookup"><span data-stu-id="73649-105">If you have a table, you configure static members (row and column headings) to remain visible.</span></span> <span data-ttu-id="73649-106">Si vous avez une matrice, vous configurez les en-têtes de groupes de colonnes et de lignes pour qu'ils restent visibles.</span><span class="sxs-lookup"><span data-stu-id="73649-106">If you have a matrix, you configure row and column group headers to remain visible.</span></span>  
  
 <span data-ttu-id="73649-107">Si vous exportez le rapport vers Excel, l'en-tête ne sera pas automatiquement figé.</span><span class="sxs-lookup"><span data-stu-id="73649-107">If you export the report to Excel, the header will not be frozen automatically.</span></span> <span data-ttu-id="73649-108">Vous pouvez figer le volet dans Excel.</span><span class="sxs-lookup"><span data-stu-id="73649-108">You can freeze the pane in Excel.</span></span> <span data-ttu-id="73649-109">Pour plus d’informations, consultez la section **En-têtes et pieds de page** de l’article [Exportation vers Microsoft Excel &#40;Générateur de rapports et SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="73649-109">For more information see the **Page Headers and Footers** section of [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73649-110">Même si une table possède des groupes de lignes et de colonnes, vous ne pouvez pas conserver ces en-têtes de groupes visibles pendant le défilement</span><span class="sxs-lookup"><span data-stu-id="73649-110">Even if a table has row and column groups, you cannot keep those group headers visible while scrolling</span></span>  
  
 <span data-ttu-id="73649-111">L'image suivante illustre une table.</span><span class="sxs-lookup"><span data-stu-id="73649-111">The following image shows a table.</span></span>  
  
 <span data-ttu-id="73649-112">![Table](../media/table.png "Table de charge de travail")</span><span class="sxs-lookup"><span data-stu-id="73649-112">![Table](../media/table.png "Table")</span></span>  
  
 <span data-ttu-id="73649-113">L'image suivante illustre une matrice.</span><span class="sxs-lookup"><span data-stu-id="73649-113">The following image shows a matrix.</span></span>  
  
 <span data-ttu-id="73649-114">![Matrice](../media/matrix.png "Matrix")</span><span class="sxs-lookup"><span data-stu-id="73649-114">![Matrix](../media/matrix.png "Matrix")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-keep-matrix-group-headers-visible-while-scrolling"></a><span data-ttu-id="73649-115">Pour garder les en-têtes de groupes de matrice visibles pendant le défilement</span><span class="sxs-lookup"><span data-stu-id="73649-115">To keep matrix group headers visible while scrolling</span></span>  
  
1.  <span data-ttu-id="73649-116">Cliquez avec le bouton droit sur la ligne, la colonne ou la poignée d’angle d’une région de données de tableau matriciel, puis sélectionnez **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="73649-116">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="73649-117">Sous l'onglet **Général** , sous **En-têtes de lignes** ou **En-têtes de colonnes**, sélectionnez **L'en-tête doit rester visible pendant le défilement**.</span><span class="sxs-lookup"><span data-stu-id="73649-117">On the **General** tab, under **Row Headers** or **Column Headers**, select **Header should remain visible while scrolling**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-keep-a-static-tablix-member-row-or-column-visible-while-scrolling"></a><span data-ttu-id="73649-118">Pour laisser un membre de tableau matriciel statique (ligne ou colonne) visible pendant le défilement</span><span class="sxs-lookup"><span data-stu-id="73649-118">To keep a static tablix member (row or column) visible while scrolling</span></span>  
  
1.  <span data-ttu-id="73649-119">Sur l'aire de conception, cliquez n'importe où dans la table pour afficher les membres statiques, ainsi que les groupes, dans le volet de regroupement.</span><span class="sxs-lookup"><span data-stu-id="73649-119">On the design surface, click anywhere in the table to display static members, as well as groups, in the grouping pane.</span></span>  
  
     <span data-ttu-id="73649-120">![Volet de regroupement](../media/grouppane-updated.png "Volet de regroupement")</span><span class="sxs-lookup"><span data-stu-id="73649-120">![Grouping pane](../media/grouppane-updated.png "Grouping pane")</span></span>  
  
     <span data-ttu-id="73649-121">Le volet Groupes de lignes affiche les membres statiques et dynamiques hiérarchiques pour la hiérarchie de groupes de lignes, et le volet Groupes de colonnes affiche une vue semblable pour la hiérarchie de groupes de colonnes.</span><span class="sxs-lookup"><span data-stu-id="73649-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy, and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
2.  <span data-ttu-id="73649-122">Dans la partie droite du volet de regroupement, cliquez sur la flèche orientée vers le bas, puis sur **Mode avancé**.</span><span class="sxs-lookup"><span data-stu-id="73649-122">On the right side of the grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span>  
  
3.  <span data-ttu-id="73649-123">Cliquez sur le membre statique (ligne ou colonne) que vous souhaitez laisser visible pendant le défilement.</span><span class="sxs-lookup"><span data-stu-id="73649-123">Click the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="73649-124">Le volet Propriétés affiche les propriétés du **membre du tableau matriciel** .</span><span class="sxs-lookup"><span data-stu-id="73649-124">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="73649-125">![Propriétés de membre de tableau matriciel](../media/grouppane-tablixmember-updated.png "Propriétés de membre de tableau matriciel")</span><span class="sxs-lookup"><span data-stu-id="73649-125">![Tablix Member properties](../media/grouppane-tablixmember-updated.png "Tablix Member properties")</span></span>  
  
4.  <span data-ttu-id="73649-126">Dans le volet Propriétés, affectez à **FixedData** la valeur `True` .</span><span class="sxs-lookup"><span data-stu-id="73649-126">In the Properties pane, set **FixedData** to `True`.</span></span>  
  
5.  <span data-ttu-id="73649-127">Répétez cette étape pour tous les membres adjacents que vous souhaitez laisser visibles pendant le défilement.</span><span class="sxs-lookup"><span data-stu-id="73649-127">Repeat this for as many adjacent members as you want to keep visible while scrolling.</span></span>  
  
6.  <span data-ttu-id="73649-128">Affichez l'aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="73649-128">Preview the report.</span></span>  
  
 <span data-ttu-id="73649-129">Lorsque vous faites défiler un rapport verticalement ou horizontalement, les membres de tableau matriciel statiques restent visibles.</span><span class="sxs-lookup"><span data-stu-id="73649-129">As you page down or across the report, the static tablix members remain in view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73649-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="73649-130">See Also</span></span>  
 <span data-ttu-id="73649-131">[Région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="73649-131">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="73649-132">[Recherche, affichage et gestion des rapports &#40;Générateur de rapports et SSRS&#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="73649-132">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="73649-133">[Exportation de rapports &#40;Générateur de rapports et SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="73649-133">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="73649-134">[Afficher des en-têtes et des pieds de page de groupe &#40;Générateur de rapports et SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="73649-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="73649-135">[Afficher des en-têtes de ligne et de colonne sur plusieurs pages &#40;Générateur de rapports et SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="73649-135">[Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="73649-136">Volet de regroupement &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="73649-136">Grouping Pane &#40;Report Builder&#41;</span></span>](grouping-pane-report-builder.md)  
  
  
