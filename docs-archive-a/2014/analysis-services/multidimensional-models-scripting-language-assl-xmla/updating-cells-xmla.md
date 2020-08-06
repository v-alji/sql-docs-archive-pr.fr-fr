---
title: Mise à jour de cellules (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- modifying cells
- XMLA, cells
- updating cells
- cells [Analysis Services]
- XML for Analysis, cells
ms.assetid: a1c61496-36ee-4bce-98d9-d13440d349aa
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c3d9a7c27533666c75102d9eac3b8311bfe4af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706872"
---
# <a name="updating-cells-xmla"></a><span data-ttu-id="ec032-102">Mise à jour de cellules (XMLA)</span><span class="sxs-lookup"><span data-stu-id="ec032-102">Updating Cells (XMLA)</span></span>
  <span data-ttu-id="ec032-103">Vous pouvez utiliser la commande [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) pour modifier la valeur d’une ou plusieurs cellules dans un cube activé pour l’écriture différée de cube.</span><span class="sxs-lookup"><span data-stu-id="ec032-103">You can use the [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) command to change the value of one or more cells in a cube enabled for cube writeback.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="ec032-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stocke les informations mises à jour dans une table d’écriture différée distincte pour chaque partition qui contient des cellules à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ec032-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stores the updated information in a separate writeback table for each partition that contains cells to be updated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec032-105">La commande `UpdateCells` ne prend pas en charge les allocations pendant l'écriture différée du cube.</span><span class="sxs-lookup"><span data-stu-id="ec032-105">The `UpdateCells` command does not support allocations during cube writeback.</span></span> <span data-ttu-id="ec032-106">Pour utiliser l’écriture différée allouée, vous devez utiliser la commande [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) pour envoyer une instruction Update MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="ec032-106">To use allocated writeback, you should use the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command to send a Multidimensional Expressions (MDX) UPDATE statement.</span></span> <span data-ttu-id="ec032-107">Pour plus d’informations, consultez [instruction UPDATE CUBE &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-update-cube).</span><span class="sxs-lookup"><span data-stu-id="ec032-107">For more information, see [UPDATE CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-update-cube).</span></span>  
  
## <a name="specifying-cells"></a><span data-ttu-id="ec032-108">Spécification de cellules</span><span class="sxs-lookup"><span data-stu-id="ec032-108">Specifying Cells</span></span>  
 <span data-ttu-id="ec032-109">La propriété de [cellule](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) de la `UpdateCells` commande contient les cellules à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ec032-109">The [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property of the `UpdateCells` command contains the cells to be updated.</span></span> <span data-ttu-id="ec032-110">Vous pouvez identifier chaque cellule dans la propriété `Cell` en utilisant leur nombre ordinal.</span><span class="sxs-lookup"><span data-stu-id="ec032-110">You identify each cell in the `Cell` property using that cell's ordinal number.</span></span> <span data-ttu-id="ec032-111">D’un plan conceptuel, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] les cellules d’un cube sont numérotées comme si le cube était un tableau de dimensions *p*, où *p* est le nombre d’axes.</span><span class="sxs-lookup"><span data-stu-id="ec032-111">Conceptually, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] numbers cells in a cube as if the cube were a *p*-dimensional array, where *p* is the number of axes.</span></span> <span data-ttu-id="ec032-112">Les cellules sont traitées dans l'ordre ligne-champ.</span><span class="sxs-lookup"><span data-stu-id="ec032-112">Cells are addressed in row-major order.</span></span> <span data-ttu-id="ec032-113">L'illustration suivante présente la formule permettant de calculer le nombre ordinal d'une cellule.</span><span class="sxs-lookup"><span data-stu-id="ec032-113">The following illustration shows the formula for calculating the ordinal number of a cell.</span></span>  
  
 <span data-ttu-id="ec032-114">![Formule de calcul de position ordinale de cellule](../../analysis-services/dev-guide/media/cellordinalformula.gif "Formule de calcul de position ordinale de cellule")</span><span class="sxs-lookup"><span data-stu-id="ec032-114">![Formula to calculate the cell ordinal position](../../analysis-services/dev-guide/media/cellordinalformula.gif "Formula to calculate the cell ordinal position")</span></span>  
  
 <span data-ttu-id="ec032-115">Une fois que vous connaissez le nombre ordinal d’une cellule, vous pouvez indiquer la valeur prévue de la cellule dans la propriété [value](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) de la propriété de [cellule](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="ec032-115">Once you know a cell's ordinal number, you can indicate the intended value of the cell in the [Value](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) property of the [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec032-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ec032-116">See Also</span></span>  
 <span data-ttu-id="ec032-117">[Élément Update &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="ec032-117">[Update Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span></span>  
 [<span data-ttu-id="ec032-118">Développement avec XMLA dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ec032-118">Developing with XMLA in Analysis Services</span></span>](../multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  
