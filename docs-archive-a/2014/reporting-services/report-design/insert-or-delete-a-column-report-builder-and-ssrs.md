---
title: Insérer ou supprimer une colonne (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9db79e2-7e7d-4359-a706-cb746c94182a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9a6f782dbb6cc1024583926aafe4bab1cfe2d042
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707111"
---
# <a name="insert-or-delete-a-column-report-builder-and-ssrs"></a><span data-ttu-id="acfb9-102">Insérer ou supprimer une colonne (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="acfb9-102">Insert or Delete a Column (Report Builder and SSRS)</span></span>
  <span data-ttu-id="acfb9-103">Vous pouvez ajouter ou supprimer des colonnes dans une région de données de tableau matriciel.</span><span class="sxs-lookup"><span data-stu-id="acfb9-103">You can add or delete columns in a tablix data region.</span></span> <span data-ttu-id="acfb9-104">Cette région peut être une table, une matrice ou une liste.</span><span class="sxs-lookup"><span data-stu-id="acfb9-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="acfb9-105">Les procédures suivantes ne s'appliquent pas aux régions de données de graphique ou de jauge.</span><span class="sxs-lookup"><span data-stu-id="acfb9-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="acfb9-106">Dans une région de données de tableau matriciel, vous pouvez ajouter des colonnes associées à un groupe (à l'intérieur d'un groupe) ou non associées à un groupe (à l'extérieur d'un groupe).</span><span class="sxs-lookup"><span data-stu-id="acfb9-106">In a tablix data region, you can add columns that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="acfb9-107">Une colonne qui se trouve à l'intérieur d'un groupe n'est utilisée qu'à une seule reprise pour chaque valeur de groupe unique.</span><span class="sxs-lookup"><span data-stu-id="acfb9-107">A column that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="acfb9-108">Par exemple, une colonne située à l'intérieur d'un groupe dont les données sont regroupées en colonnes contenant des noms de couleur n'est utilisée qu'une seule fois par nom de couleur distinct.</span><span class="sxs-lookup"><span data-stu-id="acfb9-108">For example, a column inside a group based the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="acfb9-109">Pour les groupes imbriqués, une colonne peut être à l'extérieur du groupe enfant mais à l'intérieur du groupe parent.</span><span class="sxs-lookup"><span data-stu-id="acfb9-109">For nested groups, a column can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="acfb9-110">Dans ce cas, la ligne est utilisée une fois pour chaque valeur unique dans le groupe parent.</span><span class="sxs-lookup"><span data-stu-id="acfb9-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-that-the-row-and-column-handles-appear"></a><span data-ttu-id="acfb9-111">Pour sélectionner une région de données de manière à afficher les poignées de ligne et de colonne</span><span class="sxs-lookup"><span data-stu-id="acfb9-111">To select a data region so that the row and column handles appear</span></span>  
  
-   <span data-ttu-id="acfb9-112">En mode Conception, cliquez dans l'angle supérieur gauche de la région de données de tableau matriciel pour faire apparaître les poignées de colonne et de ligne au-dessus et en regard de cette région.</span><span class="sxs-lookup"><span data-stu-id="acfb9-112">In Design view, click the upper left corner of the tablix data region, so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="acfb9-113">Pour plus d’informations sur les zones de région de données, consultez [listes &#40;générateur de rapports et SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="acfb9-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-column-in-a-selected-data-region"></a><span data-ttu-id="acfb9-114">Pour insérer une colonne dans une région de données sélectionnée</span><span class="sxs-lookup"><span data-stu-id="acfb9-114">To insert a column in a selected data region</span></span>  
  
-   <span data-ttu-id="acfb9-115">Cliquez avec le bouton droit sur une poignée de colonne à l’emplacement où vous souhaitez insérer une colonne, cliquez sur **Insérer une colonne**, puis sur **Gauche** ou **Droite**.</span><span class="sxs-lookup"><span data-stu-id="acfb9-115">Right-click a column handle where you want to insert a column, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
     <span data-ttu-id="acfb9-116">\- ou -</span><span class="sxs-lookup"><span data-stu-id="acfb9-116">-- or --</span></span>  
  
-   <span data-ttu-id="acfb9-117">Cliquez avec le bouton droit sur une cellule de la région de données au niveau de laquelle vous souhaitez insérer une colonne, cliquez sur **Insérer une colonne**, puis sur **Gauche** ou **Droite**.</span><span class="sxs-lookup"><span data-stu-id="acfb9-117">Right-click a cell in the data region where you want to insert a row, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
### <a name="to-delete-a-column-from-a-selected-data-region"></a><span data-ttu-id="acfb9-118">Pour supprimer une colonne d'une région de données sélectionnée</span><span class="sxs-lookup"><span data-stu-id="acfb9-118">To delete a column from a selected data region</span></span>  
  
-   <span data-ttu-id="acfb9-119">Sélectionnez la ou les colonnes que vous souhaitez supprimer, cliquez avec le bouton droit sur la poignée de l’une des colonnes sélectionnées, puis cliquez sur **Supprimer les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="acfb9-119">Select the column or columns that you want to delete, right-click the handle for one of the columns you selected, and then click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="acfb9-120">\- ou -</span><span class="sxs-lookup"><span data-stu-id="acfb9-120">-- or --</span></span>  
  
-   <span data-ttu-id="acfb9-121">Cliquez avec le bouton droit sur une cellule de la région de données au niveau de laquelle vous souhaitez supprimer une colonne, puis cliquez sur **Supprimer les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="acfb9-121">Right-click a cell in the data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
### <a name="to-insert-a-column-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="acfb9-122">Pour insérer une colonne dans un groupe d'une région de données sélectionnée</span><span class="sxs-lookup"><span data-stu-id="acfb9-122">To insert a column in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="acfb9-123">Dans la zone de groupe de colonnes d’une région de données de tableau matriciel, cliquez avec le bouton droit sur une cellule de groupe de colonnes au niveau de laquelle vous souhaitez insérer une colonne, sélectionnez **Insérer une colonne**, puis cliquez sur **À gauche - En dehors du groupe**, **À gauche - Dans le groupe**, **À droite - Dans le groupe**ou **À droite - En dehors du groupe**.</span><span class="sxs-lookup"><span data-stu-id="acfb9-123">Right-click a column group cell in the column group area of a tablix data region where you want to insert a column, click **Insert Column**, and then click **Left - Outside Group**, **Left - Inside Group**, **Right - Inside Group**, or **Right - Outside Group**.</span></span>  
  
     <span data-ttu-id="acfb9-124">Une colonne est ajoutée à l'intérieur ou à l'extérieur du groupe représenté par la cellule de groupe de colonnes sur laquelle vous avez cliqué.</span><span class="sxs-lookup"><span data-stu-id="acfb9-124">A column is added either inside or outside the group represented by the column group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-column-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="acfb9-125">Pour supprimer une colonne d'un groupe d'une région de données sélectionnée</span><span class="sxs-lookup"><span data-stu-id="acfb9-125">To delete a column from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="acfb9-126">Dans la zone de groupe de colonnes d’une région des données de tableau matriciel, cliquez avec le bouton droit sur une cellule de groupe de colonnes au niveau de laquelle vous souhaitez supprimer une colonne, puis sélectionnez **Supprimer les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="acfb9-126">Right-click a column group cell in the column group area of a tablix data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acfb9-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="acfb9-127">See Also</span></span>  
 <span data-ttu-id="acfb9-128">[Fonctionnement des groupes &#40;Générateur de rapports et SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="acfb9-128">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="acfb9-129">[Région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="acfb9-129">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="acfb9-130">[Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="acfb9-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="acfb9-131">[Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="acfb9-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="acfb9-132">[Listes &#40;Générateur de rapports et SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="acfb9-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="acfb9-133">Listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="acfb9-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
