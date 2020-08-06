---
title: Modifier la hauteur de ligne ou la largeur de colonne (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f061c204-5cd5-4467-9a9c-8a12803d93ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5d75a8101d07d7d6e81c624d08cd951277936eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612169"
---
# <a name="change-row-height-or-column-width-report-builder-and-ssrs"></a><span data-ttu-id="85571-102">Modifier la hauteur de ligne ou la largeur de colonne (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="85571-102">Change Row Height or Column Width (Report Builder and SSRS)</span></span>
  <span data-ttu-id="85571-103">Lorsque vous définissez la hauteur d'une ligne, vous spécifiez sa hauteur maximale dans le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="85571-103">When you set a row height, you are specifying the maximum height for the row in the rendered report.</span></span> <span data-ttu-id="85571-104">Toutefois, par défaut, les zones de texte de la ligne sont définies de manière à s'étendre verticalement pour accueillir toutes les données requises au moment de l'exécution, ce qui peut entraîner le développement d'une ligne au-delà de la hauteur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="85571-104">However, by default, text boxes in the row are set to grow vertically to accommodate their data at run-time, and this can cause a row to expand beyond the height that you specify.</span></span> <span data-ttu-id="85571-105">Pour définir une hauteur de ligne fixe, vous devez modifier les propriétés des zones de texte afin qu'elles ne se développent pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="85571-105">To set a fixed row height, you must change the text box properties so they do not automatically expand.</span></span>  
  
 <span data-ttu-id="85571-106">Lorsque vous définissez la largeur d'une colonne,vous spécifiez sa largeur maximale dans le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="85571-106">When you set a column width, you are specifying the maximum width for the column in the rendered report.</span></span> <span data-ttu-id="85571-107">Les colonnes ne s'ajustent pas horizontalement de manière automatique en fonction du texte à afficher.</span><span class="sxs-lookup"><span data-stu-id="85571-107">Columns do not automatically adjust horizontally to accommodate text.</span></span>  
  
 <span data-ttu-id="85571-108">Si une cellule d'une ligne ou d'une colonne contient un rectangle ou une région de données, la hauteur et la largeur minimales de la cellule sont déterminées par la hauteur et largeur de l'élément contenu.</span><span class="sxs-lookup"><span data-stu-id="85571-108">If a cell in a row or column contains a rectangle or data region, the minimum height and width of the cell is determined by the height and width of the contained item.</span></span> <span data-ttu-id="85571-109">Pour plus d’informations, consultez [Comportements de rendu &#40;Générateur de rapports et SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="85571-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-row-height-by-moving-row-handles"></a><span data-ttu-id="85571-110">Pour modifier la hauteur de ligne en déplaçant les poignées de ligne</span><span class="sxs-lookup"><span data-stu-id="85571-110">To change row height by moving row handles</span></span>  
  
1.  <span data-ttu-id="85571-111">Dans la vue Conception, cliquez n'importe où dans la région de données de tableau matriciel pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="85571-111">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="85571-112">Des poignées de ligne grises s'affichent sur la bordure extérieure de la région de données de tableau matriciel.</span><span class="sxs-lookup"><span data-stu-id="85571-112">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="85571-113">Avec la souris, pointez sur le bord de la poignée de ligne que vous souhaitez développer.</span><span class="sxs-lookup"><span data-stu-id="85571-113">Hover over the row handle edge that you want to expand.</span></span> <span data-ttu-id="85571-114">Une double flèche apparaît.</span><span class="sxs-lookup"><span data-stu-id="85571-114">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="85571-115">Cliquez pour saisir le bord de la ligne et le déplacer vers le haut ou vers le bas afin d'ajuster la hauteur de la ligne</span><span class="sxs-lookup"><span data-stu-id="85571-115">Click to grab the edge of the row and move it higher or lower to adjust the row height.</span></span>  
  
### <a name="to-change-row-height-by-setting-cell-properties"></a><span data-ttu-id="85571-116">Pour modifier la hauteur de ligne en définissant les propriétés de cellule</span><span class="sxs-lookup"><span data-stu-id="85571-116">To change row height by setting cell properties</span></span>  
  
1.  <span data-ttu-id="85571-117">Dans la vue Conception, cliquez sur une cellule dans la ligne de table.</span><span class="sxs-lookup"><span data-stu-id="85571-117">In Design view, click a cell in the table row.</span></span>  
  
     <span data-ttu-id="85571-118">![Cellule sélectionnée dans une table](../media/table-selectcell.png "Cellule sélectionnée dans une table")</span><span class="sxs-lookup"><span data-stu-id="85571-118">![Selected Cell in a Table](../media/table-selectcell.png "Selected Cell in a Table")</span></span>  
  
2.  <span data-ttu-id="85571-119">Dans le volet **Propriétés** qui s’affiche, modifiez la propriété **Hauteur** , puis cliquez n’importe où en dehors du volet **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="85571-119">In the **Properties** pane that displays, modify the **Height** property, and then click anywhere outside the **Properties** pane.</span></span>  
  
     <span data-ttu-id="85571-120">![Volet Propriétés pour la cellule de table sélectionnée](../media/cell-propertiespane.png "Volet Propriétés pour la cellule de table sélectionnée")</span><span class="sxs-lookup"><span data-stu-id="85571-120">![Properties Pane for selected table cell](../media/cell-propertiespane.png "Properties Pane for selected table cell")</span></span>  
  
### <a name="to-prevent-a-row-from-automatically-expanding-vertically"></a><span data-ttu-id="85571-121">Pour empêcher le développement vertical automatique d'une ligne</span><span class="sxs-lookup"><span data-stu-id="85571-121">To prevent a row from automatically expanding vertically</span></span>  
  
1.  <span data-ttu-id="85571-122">Dans la vue Conception, cliquez n'importe où dans la région de données de tableau matriciel pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="85571-122">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="85571-123">Des poignées de ligne grises s'affichent sur la bordure extérieure de la région de données de tableau matriciel.</span><span class="sxs-lookup"><span data-stu-id="85571-123">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="85571-124">Cliquez sur la poignée de la ligne pour sélectionner la ligne.</span><span class="sxs-lookup"><span data-stu-id="85571-124">Click the row handle to select the row.</span></span>  
  
3.  <span data-ttu-id="85571-125">Dans le volet Propriétés, affectez à CanGrow la valeur **False**.</span><span class="sxs-lookup"><span data-stu-id="85571-125">In the Properties pane, set CanGrow to **False**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85571-126">Si le volet Propriétés n’est pas visible, dans le menu **Affichage** , cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="85571-126">If you cannot see the Properties pane, from the **View** menu, click **Properties**.</span></span>  
  
### <a name="to-change-column-width"></a><span data-ttu-id="85571-127">Pour modifier la largeur de colonne</span><span class="sxs-lookup"><span data-stu-id="85571-127">To change column width</span></span>  
  
1.  <span data-ttu-id="85571-128">Dans la vue Conception, cliquez n'importe où dans la région de données de tableau matriciel pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="85571-128">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="85571-129">Des poignées de colonne grises s’affichent sur la bordure extérieure de la région de données de tableau matriciel.</span><span class="sxs-lookup"><span data-stu-id="85571-129">Gray column handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="85571-130">Avec la souris, pointez sur le bord de la poignée de colonne que vous souhaitez développer.</span><span class="sxs-lookup"><span data-stu-id="85571-130">Hover over the column handle edge that you want to expand.</span></span> <span data-ttu-id="85571-131">Une double flèche apparaît.</span><span class="sxs-lookup"><span data-stu-id="85571-131">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="85571-132">Cliquez pour saisir le bord de la colonne et le déplacer vers la gauche ou vers la droite afin d'ajuster la largeur de la colonne.</span><span class="sxs-lookup"><span data-stu-id="85571-132">Click to grab the edge of the column and move it left or right to adjust the column width.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85571-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85571-133">See Also</span></span>  
 <span data-ttu-id="85571-134">[Région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85571-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85571-135">[Cellules, lignes et colonnes de région de données de tableau matriciel &#40;Générateur de rapports&#41; et SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85571-135">[Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85571-136">[Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85571-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85571-137">[Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85571-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85571-138">[Répertorie &#40;Générateur de rapports et SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85571-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="85571-139">Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="85571-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
