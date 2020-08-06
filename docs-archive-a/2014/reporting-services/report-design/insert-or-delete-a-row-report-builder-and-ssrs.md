---
title: Insérer ou supprimer une ligne (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b9642af3-b3ae-4f78-b0be-8f96b79fc313
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fdec24801d1fae3b95c7d75acb5a3add650d523b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707104"
---
# <a name="insert-or-delete-a-row-report-builder-and-ssrs"></a><span data-ttu-id="a6d5e-102">Insérer ou supprimer une ligne (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="a6d5e-102">Insert or Delete a Row (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a6d5e-103">Vous pouvez ajouter ou supprimer des lignes dans une région de données de tableau matriciel.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-103">You can add or delete rows in a tablix data region.</span></span> <span data-ttu-id="a6d5e-104">Cette région peut être une table, une matrice ou une liste.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="a6d5e-105">Les procédures suivantes ne s'appliquent pas aux régions de données de graphique ou de jauge.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="a6d5e-106">Dans une région de données de tableau matriciel, vous pouvez ajouter des lignes associées à un groupe (à l'intérieur d'un groupe) ou non associées à un groupe (à l'extérieur d'un groupe).</span><span class="sxs-lookup"><span data-stu-id="a6d5e-106">In a tablix data region, you can add rows that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="a6d5e-107">Une ligne qui se trouve à l'intérieur d'un groupe n'est utilisée qu'à une seule reprise pour chaque valeur de groupe unique.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-107">A row that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="a6d5e-108">Par exemple, une ligne située à l'intérieur d'un groupe dont les données sont regroupées en colonnes contenant des noms de couleur n'est utilisée qu'une seule fois par nom de couleur distinct.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-108">For example, a row inside a group based on the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="a6d5e-109">Pour les groupes imbriqués, une ligne peut être à l'extérieur du groupe enfant mais à l'intérieur du groupe parent.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-109">For nested groups, a row can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="a6d5e-110">Dans ce cas, la ligne est utilisée une fois pour chaque valeur unique dans le groupe parent.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-the-row-and-column-handles-appear"></a><span data-ttu-id="a6d5e-111">Pour sélectionner une région de données de manière à afficher les poignées de ligne et de colonne</span><span class="sxs-lookup"><span data-stu-id="a6d5e-111">To select a data region so the row and column handles appear</span></span>  
  
-   <span data-ttu-id="a6d5e-112">En mode Conception, cliquez dans l'angle supérieur gauche de la région de données de tableau matriciel pour faire apparaître les poignées de colonne et de ligne au-dessus et en regard de cette région.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-112">In Design view, click the upper left corner of the tablix data region so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="a6d5e-113">Pour plus d’informations sur les zones de région de données, consultez [listes &#40;générateur de rapports et SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a6d5e-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-row-in-a-selected-data-region"></a><span data-ttu-id="a6d5e-114">Pour insérer une ligne dans une région de données sélectionnée</span><span class="sxs-lookup"><span data-stu-id="a6d5e-114">To insert a row in a selected data region</span></span>  
  
-   <span data-ttu-id="a6d5e-115">Cliquez avec le bouton droit sur un handle de ligne à l’emplacement où vous souhaitez insérer une ligne, puis cliquez sur **Insérer une ligne**et sur **Au-dessus** ou **En dessous**.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-115">Right-click a row handle where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
     <span data-ttu-id="a6d5e-116">\- ou -</span><span class="sxs-lookup"><span data-stu-id="a6d5e-116">\- or -</span></span>  
  
-   <span data-ttu-id="a6d5e-117">Cliquez avec le bouton droit sur une cellule de la région de données au niveau de laquelle vous souhaitez insérer une ligne, cliquez sur **Insérer une ligne**, puis sur **Au-dessus** ou **En dessous**.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-117">Right-click a cell in the data region where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
### <a name="to-delete-a-row-from-a-selected-data-region"></a><span data-ttu-id="a6d5e-118">Pour supprimer une ligne d'une région de données sélectionnée</span><span class="sxs-lookup"><span data-stu-id="a6d5e-118">To delete a row from a selected data region</span></span>  
  
-   <span data-ttu-id="a6d5e-119">Sélectionnez chaque ligne à supprimer, cliquez avec le bouton droit sur le handle d’une ligne sélectionnée, puis cliquez sur **Supprimer les lignes**.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-119">Select the row or rows that you want to delete, right-click the handle for one of the rows you selected, and then click **Delete Rows**.</span></span>  
  
     <span data-ttu-id="a6d5e-120">\- ou -</span><span class="sxs-lookup"><span data-stu-id="a6d5e-120">\- or -</span></span>  
  
-   <span data-ttu-id="a6d5e-121">Cliquez avec le bouton droit sur une cellule de la région de données au niveau de laquelle vous souhaitez supprimer une ligne, puis cliquez sur **Supprimer les lignes**.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-121">Right-click a cell in the data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
### <a name="to-insert-a-row-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="a6d5e-122">Pour insérer une ligne dans un groupe dans une région de données sélectionnée</span><span class="sxs-lookup"><span data-stu-id="a6d5e-122">To insert a row in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="a6d5e-123">Dans la zone de groupe de lignes d’une région de données de tableau matriciel, cliquez avec le bouton droit sur une cellule de groupe de lignes au niveau de laquelle vous souhaitez insérer une ligne, cliquez sur **Insérer une ligne**, puis cliquez sur **Au-dessus - En dehors du groupe**, **Au-dessus - Dans le groupe**, **En dessous - Dans le groupe**ou **En dessous - En dehors du groupe**.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-123">Right-click a row group cell in the row group area of a tablix data region where you want to insert a row, click **Insert Row**, and then click **Above - Outside Group**, **Above - Inside Group**, **Below - Inside Group**, or **Below - Outside Group**.</span></span>  
  
     <span data-ttu-id="a6d5e-124">Une ligne est ajoutée à l'intérieur ou à l'extérieur du groupe représenté par la cellule de groupe de lignes sur laquelle vous avez cliqué.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-124">A row is added either inside or outside the group represented by the row group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-row-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="a6d5e-125">Pour supprimer une ligne d'un groupe dans une région de données sélectionnée</span><span class="sxs-lookup"><span data-stu-id="a6d5e-125">To delete a row from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="a6d5e-126">Dans la zone de groupe de lignes d’une région de données de tableau matriciel, cliquez avec le bouton droit sur une cellule de groupe de lignes au niveau de laquelle vous souhaitez supprimer une ligne, puis cliquez sur **Supprimer les lignes**.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-126">Right-click a row group cell in the row group area of a tablix data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d5e-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6d5e-127">See Also</span></span>  
 <span data-ttu-id="a6d5e-128">[Région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a6d5e-128">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a6d5e-129">[Fonctionnement des groupes &#40;Générateur de rapports et SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a6d5e-129">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a6d5e-130">[Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a6d5e-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a6d5e-131">[Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a6d5e-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a6d5e-132">[Listes &#40;Générateur de rapports et SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a6d5e-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a6d5e-133">Listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a6d5e-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
