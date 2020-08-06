---
title: Fusionner des cellules dans une région de données (Générateur de rapports et SSRS)| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 43551300-89b2-4f4e-af09-69084324afaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c69ce8182bda3e0b644893e97b69280a003f5732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703843"
---
# <a name="merge-cells-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="5924f-102">Fusionner des cellules dans une région de données (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="5924f-102">Merge Cells in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5924f-103">Vous pouvez fusionner des cellules dans une région de données pour les combiner, améliorer l'apparence de la région de données ou fournir des étiquettes étendues pour les groupes de colonnes et de lignes.</span><span class="sxs-lookup"><span data-stu-id="5924f-103">You can merge cells in a data region to combine cells, improve data region appearance, or provide spanning labels for column groups and row groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5924f-104">Les cellules peuvent uniquement être fusionnées à l'intérieur de chaque zone d'une région de données : angle, en-têtes de colonne, définition de groupe (ou en-têtes de ligne) et corps.</span><span class="sxs-lookup"><span data-stu-id="5924f-104">Cells can only be merged within each area of a data region: corner, column headers, group definition (or row headers), and body.</span></span> <span data-ttu-id="5924f-105">Vous ne pouvez pas fusionner de cellules dépassant les limites de la zone.</span><span class="sxs-lookup"><span data-stu-id="5924f-105">You cannot merge cells that cross area boundaries.</span></span> <span data-ttu-id="5924f-106">Vous ne pouvez par exemple pas fusionner une cellule située dans la zone d'angle de la région de données avec une cellule située dans la zone de groupe de lignes.</span><span class="sxs-lookup"><span data-stu-id="5924f-106">For example, you cannot merge a cell in the data region corner area with a cell in the row group area.</span></span> <span data-ttu-id="5924f-107">Pour plus d’informations sur les zones de tableau matriciel, consultez [listes &#40;générateur de rapports et les&#41;SSRS ](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5924f-107">For more information about tablix areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-merge-cells-in-a-data-region"></a><span data-ttu-id="5924f-108">Pour fusionner des cellules dans une région de données</span><span class="sxs-lookup"><span data-stu-id="5924f-108">To merge cells in a data region</span></span>  
  
1.  <span data-ttu-id="5924f-109">Dans la région de données sur l'aire de conception du rapport, cliquez sur la première cellule à fusionner.</span><span class="sxs-lookup"><span data-stu-id="5924f-109">In the data region on the report design surface, click the first cell to merge.</span></span> <span data-ttu-id="5924f-110">Tout en maintenant le bouton gauche de la souris enfoncé, faites glisser verticalement ou horizontalement la souris pour sélectionner des cellules adjacentes.</span><span class="sxs-lookup"><span data-stu-id="5924f-110">Holding the left mouse button down, drag vertically or horizontally to select adjacent cells.</span></span> <span data-ttu-id="5924f-111">Les cellules sélectionnées sont mises en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="5924f-111">The selected cells are highlighted.</span></span>  
  
2.  <span data-ttu-id="5924f-112">Cliquez avec le bouton droit sur les cellules sélectionnées, puis sélectionnez **Fusionner les cellules**.</span><span class="sxs-lookup"><span data-stu-id="5924f-112">Right-click the selected cells and select **Merge Cells**.</span></span> <span data-ttu-id="5924f-113">Les cellules sélectionnées sont combinées en une seule cellule.</span><span class="sxs-lookup"><span data-stu-id="5924f-113">The selected cells are combined into a single cell.</span></span>  
  
3.  <span data-ttu-id="5924f-114">Répétez les étapes 1 et 2 pour fusionner d'autres cellules adjacentes dans une région de données.</span><span class="sxs-lookup"><span data-stu-id="5924f-114">Repeat steps 1 and 2 to merge other adjacent cells in a data region.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5924f-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5924f-115">See Also</span></span>  
 <span data-ttu-id="5924f-116">[Région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5924f-116">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5924f-117">[Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5924f-117">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5924f-118">[Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5924f-118">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5924f-119">[Répertorie &#40;Générateur de rapports et SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5924f-119">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5924f-120">Listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5924f-120">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
