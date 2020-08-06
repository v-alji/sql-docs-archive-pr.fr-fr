---
title: Ajouter ou supprimer un groupe dans une région de données (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4de53c3c-c6fc-49ce-b692-3609fc0b3ec5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c355ca87db578d47181935e1ca6bc48e75bf8b8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703879"
---
# <a name="add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="07108-102">Ajouter ou supprimer un groupe dans une région de données (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="07108-102">Add or Delete a Group in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="07108-103">Vous pouvez ajouter un groupe à une région de données pour organiser les données selon une valeur spécifique ou un ensemble d'expressions à des fins d'affichage et de calculs.</span><span class="sxs-lookup"><span data-stu-id="07108-103">Add a group to a data region when you want to organize data by a specific value or set of expressions, for display and calculations.</span></span> <span data-ttu-id="07108-104">Un groupe porte un nom et possède une expression qui identifient les données d'un dataset qui appartient à ce groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-104">A group has a name and an expression that identifies which data from a dataset belongs to the group.</span></span> <span data-ttu-id="07108-105">Pour plus d’informations sur les groupes, consultez [Fonctionnement des groupes &#40;Générateur de rapports et SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="07108-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="07108-106">Dans une région de données de tableau matriciel, cliquez sur la table, la matrice ou la liste pour afficher le volet de regroupement.</span><span class="sxs-lookup"><span data-stu-id="07108-106">In a tablix data region, click in the table, matrix, or list to display the Grouping pane.</span></span> <span data-ttu-id="07108-107">Faites glisser des champs du dataset vers les volets Groupe de lignes et Groupe de colonnes pour créer des groupes parents ou enfants.</span><span class="sxs-lookup"><span data-stu-id="07108-107">Drag dataset fields to the Row Group and Column Group pane to create parent or child groups.</span></span> <span data-ttu-id="07108-108">Cliquez avec le bouton droit sur un groupe existant pour ajouter un groupe adjacent.</span><span class="sxs-lookup"><span data-stu-id="07108-108">Right-click an existing group to add an adjacent group.</span></span> <span data-ttu-id="07108-109">Par définition, le groupe de détails est le groupe le plus profond et ne peut être ajouté qu'en tant que groupe enfant.</span><span class="sxs-lookup"><span data-stu-id="07108-109">By definition, the details group is the innermost group and can only be added as a child group.</span></span> <span data-ttu-id="07108-110">Cliquez avec le bouton droit sur un groupe existant pour le supprimer.</span><span class="sxs-lookup"><span data-stu-id="07108-110">Right-click an existing group to delete it.</span></span> <span data-ttu-id="07108-111">Les lignes et les colonnes dans lesquelles des valeurs de groupe seront affichées sont automatiquement ajoutées.</span><span class="sxs-lookup"><span data-stu-id="07108-111">Rows and columns on which to display group values are automatically added for you.</span></span> <span data-ttu-id="07108-112">Pour plus d’informations, consultez [Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="07108-112">For more information, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="07108-113">Dans une région de données de graphique, cliquez sur le graphique pour afficher les zones de dépôt.</span><span class="sxs-lookup"><span data-stu-id="07108-113">In a Chart data region, click in the chart to display the drop-zones.</span></span> <span data-ttu-id="07108-114">Créez des groupes en faisant glisser des champs du dataset vers les zones de dépôt des catégories et des séries.</span><span class="sxs-lookup"><span data-stu-id="07108-114">Create groups by dragging dataset fields to the category and series drop zones.</span></span> <span data-ttu-id="07108-115">Pour ajouter des groupes imbriqués, ajoutez plusieurs champs à la zone de dépôt.</span><span class="sxs-lookup"><span data-stu-id="07108-115">To add nested groups, add multiple fields to the drop-zone.</span></span>  
  
 <span data-ttu-id="07108-116">Ces groupes ne sont pas définis dans une jauge par défaut.</span><span class="sxs-lookup"><span data-stu-id="07108-116">Groups are not defined in a gauge by default.</span></span> <span data-ttu-id="07108-117">Le comportement par défaut de la jauge consiste à agréger toutes les valeurs du champ spécifié en une seule valeur qui est indiquée sur la jauge.</span><span class="sxs-lookup"><span data-stu-id="07108-117">The default behavior for the gauge is to aggregate all values in the specified field into one value that is displayed on the gauge.</span></span> <span data-ttu-id="07108-118">Pour plus d’informations, consultez [Jauges &#40;Générateur de rapports et SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="07108-118">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="07108-119">Pour ajouter un groupe de lignes ou de colonnes parent ou enfant à une région de données de tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="07108-119">To add a parent or child row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="07108-120">Faites glisser un champ du volet **Données du rapport** vers le volet **Groupes de lignes** ou le volet **Groupes de colonnes** .</span><span class="sxs-lookup"><span data-stu-id="07108-120">Drag a field from the **Report Data** pane to the **Row Groups** pane or the **Column Groups** pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="07108-121">Si le volet de regroupement n’est pas visible, sous l’onglet Affichage, cliquez sur **Regroupement**.</span><span class="sxs-lookup"><span data-stu-id="07108-121">If you do not see the Grouping pane, on the View tab, click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="07108-122">Déplacez le champ situé au-dessus ou en dessous de la hiérarchie de groupes à l'aide de la barre de repère pour placer le groupe en tant que groupe parent ou groupe enfant dans un groupe existant.</span><span class="sxs-lookup"><span data-stu-id="07108-122">Drop the field above or below the group hierarchy using the guide bar to place the group as a parent group or a child group to an existing group.</span></span>  
  
     <span data-ttu-id="07108-123">Le groupe est ajouté avec un nom, une expression de groupe et une expression de tri par défaut reposant sur le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="07108-123">The group is added with a default name, group expression, and sort expression that is based on the field name.</span></span>  
  
### <a name="to-add-an-adjacent-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="07108-124">Pour ajouter un groupe de lignes ou de colonnes adjacent à une région de données de tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="07108-124">To add an adjacent row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="07108-125">Dans le volet de regroupement, cliquez avec le bouton droit sur un groupe homologue du groupe que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="07108-125">In the Grouping pane, right-click a group that is a peer to the group that you want to add.</span></span> <span data-ttu-id="07108-126">Cliquez sur **Ajouter un groupe**, puis sur **Adjacent avant** ou sur **Adjacent après** pour spécifier l’emplacement auquel ajouter le groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-126">Click **Add Group**, and then click **Adjacent Before** or **Adjacent After** to specify where to add the group.</span></span> <span data-ttu-id="07108-127">La boîte de dialogue **Groupe de tableaux matriciels** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="07108-127">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="07108-128">Dans **Nom**, tapez le nom du groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-128">In **Name**, type a name for the group.</span></span>  
  
3.  <span data-ttu-id="07108-129">Dans **Expression Groupe**, tapez une expression ou cliquez sur le bouton Expression (**fx**) pour créer une expression.</span><span class="sxs-lookup"><span data-stu-id="07108-129">In **Group expression**, type an expression or click the expression button (**fx**) to create an expression.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="07108-130">Un nouveau groupe est ajouté au volet de regroupement et une ligne ou une colonne dans laquelle des valeurs de groupe seront affichées est ajoutée à la région de données de tableau matriciel sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="07108-130">A new group is added to the Grouping pane and a row or column on which to display group values is added to the tablix data region on the design surface.</span></span>  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="07108-131">Pour ajouter un groupe de détails à une région de données de tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="07108-131">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="07108-132">Dans le volet de regroupement, cliquez avec le bouton droit sur un groupe qui est le groupe enfant le plus profond, mais pas le groupe **Détails** .</span><span class="sxs-lookup"><span data-stu-id="07108-132">In the Grouping pane, right-click a group that is the innermost child group, but not the **Details** group.</span></span> <span data-ttu-id="07108-133">Cliquez sur **Ajouter un groupe**, puis sur **Groupe enfant**.</span><span class="sxs-lookup"><span data-stu-id="07108-133">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="07108-134">La boîte de dialogue **Groupe de tableaux matriciels** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="07108-134">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="07108-135">Dans **Expression Groupe**, laissez l'expression vide.</span><span class="sxs-lookup"><span data-stu-id="07108-135">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="07108-136">Un groupe de détails ne possède aucune expression.</span><span class="sxs-lookup"><span data-stu-id="07108-136">A details group has no expression.</span></span>  
  
3.  <span data-ttu-id="07108-137">Sélectionnez **Afficher les données de détail**.</span><span class="sxs-lookup"><span data-stu-id="07108-137">Select **Show detail data**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="07108-138">Un nouveau groupe de détails est ajouté en tant que groupe enfant dans le volet Regroupement et le descripteur de ligne du groupe que vous avez sélectionné au cours de l'étape 1 affiche l'icône du groupe de détails.</span><span class="sxs-lookup"><span data-stu-id="07108-138">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="07108-139">Pour plus d’informations sur les descripteurs, consultez [Cellules, lignes et colonnes de région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="07108-139">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-edit-a-row-or-column-group-in-a-tablix-data-region"></a><span data-ttu-id="07108-140">Pour modifier un groupe de lignes ou de colonnes dans une région de données de tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="07108-140">To edit a row or column group in a tablix data region</span></span>  
  
1.  <span data-ttu-id="07108-141">Sur l'aire de conception du rapport, cliquez n'importe où dans la région de données de tableau matriciel pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="07108-141">On the report design surface, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="07108-142">Le volet Regroupement affiche les groupes de lignes et de colonnes.</span><span class="sxs-lookup"><span data-stu-id="07108-142">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="07108-143">Cliquez avec le bouton droit sur le groupe, puis cliquez sur **Propriétés du groupe**.</span><span class="sxs-lookup"><span data-stu-id="07108-143">Right-click the group, and then click **Group Properties**.</span></span>  
  
3.  <span data-ttu-id="07108-144">Dans **Nom**, tapez le nom du groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-144">In **Name**, type the name of the group.</span></span>  
  
4.  <span data-ttu-id="07108-145">Dans **Expressions Groupe**, tapez ou sélectionnez une expression simple ou cliquez sur le bouton Expression (**fx**) pour créer une expression de groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-145">In **Group expressions**, type or select a simple expression, or click the Expression (**fx**) button to create a group expression.</span></span>  
  
5.  <span data-ttu-id="07108-146">Cliquez sur **Ajouter** pour créer d’autres expressions.</span><span class="sxs-lookup"><span data-stu-id="07108-146">Click **Add** to create additional expressions.</span></span> <span data-ttu-id="07108-147">Toutes les expressions que vous spécifiez sont combinées à l'aide d'une logique AND pour spécifier les données de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-147">All expressions you specify are combined using a logical AND to specify data for this group.</span></span>  
  
6.  <span data-ttu-id="07108-148">(Facultatif) Cliquez sur **Sauts de page** pour définir des options de saut de page.</span><span class="sxs-lookup"><span data-stu-id="07108-148">(Optional) Click **Page Breaks** to set page break options.</span></span>  
  
7.  <span data-ttu-id="07108-149">(Facultatif) Cliquez sur **Tri** pour sélectionner ou taper des expressions qui spécifient l’ordre de tri des valeurs du groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-149">(Optional) Click **Sorting** to select or type expressions that specify the sort order for values in the group.</span></span>  
  
8.  <span data-ttu-id="07108-150">(Facultatif) Cliquez sur **Visibilité** pour sélectionner les options de visibilité de l’élément.</span><span class="sxs-lookup"><span data-stu-id="07108-150">(Optional) Click **Visibility** to select the visibility options for the item.</span></span>  
  
9. <span data-ttu-id="07108-151">(Facultatif) Cliquez sur **Filtres** pour définir les filtres de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-151">(Optional) Click **Filters** to set filters for this group.</span></span>  
  
10. <span data-ttu-id="07108-152">(Facultatif) Cliquez sur **Variables** pour définir les variables étendues à ce groupe et accessibles à partir de tous les groupes enfants.</span><span class="sxs-lookup"><span data-stu-id="07108-152">(Optional) Click **Variables** to define variables scoped to this group and accessible from any child groups.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-tablix-data-region"></a><span data-ttu-id="07108-153">Pour supprimer un groupe d’une région de données de tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="07108-153">To delete a group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="07108-154">Dans le volet de regroupement, cliquez avec le bouton droit sur le groupe, puis cliquez sur **Supprimer le groupe**.</span><span class="sxs-lookup"><span data-stu-id="07108-154">In the Grouping pane, right-click the group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="07108-155">Dans la boîte de dialogue **Supprimer le groupe** , sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="07108-155">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="07108-156">**Supprimer le groupe et les colonnes et lignes associées** Choisissez cette option pour supprimer la définition de groupe et toutes les lignes associées qui affichent des données de groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-156">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="07108-157">Pour les groupes de détails, si une même ligne appartient à la fois aux données de détail et de groupe, seules les lignes de données de détail sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="07108-157">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="07108-158">**Supprimer le groupe uniquement** Choisissez cette option pour conserver la structure de la région de données de tableau matriciel et ne supprimer que la définition de groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-158">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-details-group-from-a-tablix-data-region"></a><span data-ttu-id="07108-159">Pour supprimer un groupe de détails d’une région de données de tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="07108-159">To delete a details group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="07108-160">Dans le volet de regroupement, cliquez avec le bouton droit sur le groupe de détails, puis cliquez sur **Supprimer le groupe**.</span><span class="sxs-lookup"><span data-stu-id="07108-160">In the Grouping pane, right-click the details group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="07108-161">Dans la boîte de dialogue **Supprimer le groupe** , sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="07108-161">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="07108-162">**Supprimer le groupe et les colonnes et lignes associées** Choisissez cette option pour supprimer la définition de groupe et toutes les lignes associées qui affichent des données de groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-162">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="07108-163">Pour les groupes de détails, si une même ligne appartient à la fois aux données de détail et de groupe, seules les lignes de données de détail sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="07108-163">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="07108-164">**Supprimer le groupe uniquement** Choisissez cette option pour conserver la structure de la région de données de tableau matriciel et ne supprimer que la définition de groupe.</span><span class="sxs-lookup"><span data-stu-id="07108-164">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="07108-165">Le groupe de détails est supprimé.</span><span class="sxs-lookup"><span data-stu-id="07108-165">The details group is deleted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="07108-166">Lorsque vous supprimez une ligne de détails, vérifiez que l'expression dans chaque cellule spécifie, le cas échéant, une expression d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="07108-166">Verify that after you remove a details row, the expression in each cell specifies an aggregate expression where appropriate.</span></span> <span data-ttu-id="07108-167">Si nécessaire, modifiez l'expression pour spécifier les fonctions d'agrégation appropriées.</span><span class="sxs-lookup"><span data-stu-id="07108-167">If necessary, edit the expression to specify aggregate functions as needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07108-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07108-168">See Also</span></span>  
 <span data-ttu-id="07108-169">[Références à des collections de variables de rapport et de groupe &#40;Générateur de rapports et SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="07108-169">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 <span data-ttu-id="07108-170">[Exemples d’expressions de groupe &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07108-170">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07108-171">[Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07108-171">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07108-172">[Région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07108-172">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07108-173">[Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07108-173">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07108-174">[Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07108-174">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07108-175">[Listes &#40;Générateur de rapports et SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07108-175">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="07108-176">Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="07108-176">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
