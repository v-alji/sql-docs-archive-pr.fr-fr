---
title: Créer un groupe de hiérarchies récursives (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8b830ba5-4d64-4348-a2b1-76b9338a1462
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf86c3989170ed8cd452168a558ead348258331e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603881"
---
# <a name="create-a-recursive-hierarchy-group-report-builder-and-ssrs"></a><span data-ttu-id="06a74-102">Créer un groupe de hiérarchies récursives (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="06a74-102">Create a Recursive Hierarchy Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="06a74-103">Un groupe de hiérarchies récursives organise les données d'un dataset de rapport unique qui inclut plusieurs niveaux hiérarchiques, tels que la structure de rapports pour les relations entre directeur et employé dans une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="06a74-103">A recursive hierarchy group organizes data from a single report dataset that includes multiple hierarchical levels, such as the report-to structure for manager-employee relationships in an organizational hierarchy.</span></span>  
  
 <span data-ttu-id="06a74-104">Avant de pouvoir organiser les données d'une table comme un groupe de hiérarchies récursives, vous devez avoir un dataset unique qui contient toutes les données hiérarchiques. En outre, vous devez disposer de champs distincts pour l'élément à grouper et l'élément en fonction duquel le regroupement est effectué.</span><span class="sxs-lookup"><span data-stu-id="06a74-104">Before you can organize data in a table as a recursive hierarchy group, you must have a single dataset that contains all the hierarchical data, You must have separate fields for the item to group and for the item to group by.</span></span> <span data-ttu-id="06a74-105">Par exemple, un dataset où vous souhaitez regrouper les employés de manière récursive sous leur responsable, peut contenir un nom, un nom d'employé, un ID d'employé et un ID de responsable.</span><span class="sxs-lookup"><span data-stu-id="06a74-105">For example, a dataset where you want to group employees recursively under their manager might contain a name, an employee name, an employee ID, and a manager ID.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-recursive-hierarchy-group"></a><span data-ttu-id="06a74-106">Pour créer un groupe de hiérarchies récursives</span><span class="sxs-lookup"><span data-stu-id="06a74-106">To create a recursive hierarchy group</span></span>  
  
1.  <span data-ttu-id="06a74-107">En mode Conception, ajoutez une table et faites glisser les champs de dataset à afficher.</span><span class="sxs-lookup"><span data-stu-id="06a74-107">In Design view, add a table, and drag the dataset fields to display.</span></span> <span data-ttu-id="06a74-108">En général, le champ que vous souhaitez afficher comme une hiérarchie figure dans la première colonne.</span><span class="sxs-lookup"><span data-stu-id="06a74-108">Typically, the field that you want to show as a hierarchy is in the first column.</span></span>  
  
2.  <span data-ttu-id="06a74-109">Cliquez avec le bouton droit n'importe où dans la table pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="06a74-109">Right-click anywhere in the table to select it.</span></span> <span data-ttu-id="06a74-110">Le volet de regroupement affiche le groupe de détails pour la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="06a74-110">The Grouping pane displays the details group for the selected table.</span></span> <span data-ttu-id="06a74-111">Dans le volet Groupes de lignes, cliquez avec le bouton droit sur **Détails**, puis cliquez sur **Modifier le groupe**.</span><span class="sxs-lookup"><span data-stu-id="06a74-111">In the Row Groups pane, right-click **Details**, and then click **Edit Group**.</span></span> <span data-ttu-id="06a74-112">La boîte de dialogue **Propriétés du groupe** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="06a74-112">The **Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="06a74-113">Dans **Expressions Groupe**, cliquez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="06a74-113">In **Group expressions**, click **Add**.</span></span> <span data-ttu-id="06a74-114">Une nouvelle ligne apparaît dans la grille.</span><span class="sxs-lookup"><span data-stu-id="06a74-114">A new row appears in the grid.</span></span>  
  
4.  <span data-ttu-id="06a74-115">Dans la liste **Grouper sur** , tapez ou sélectionnez le champ de groupement.</span><span class="sxs-lookup"><span data-stu-id="06a74-115">In the **Group on** list, type or select the field to group.</span></span>  
  
5.  <span data-ttu-id="06a74-116">Cliquez sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="06a74-116">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="06a74-117">Dans la liste **Parent récursif** , entrez ou sélectionnez le champ de groupement.</span><span class="sxs-lookup"><span data-stu-id="06a74-117">In the **Recursive Parent** list, enter or select the field to group on.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="06a74-118">Exécutez le rapport.</span><span class="sxs-lookup"><span data-stu-id="06a74-118">Run the report.</span></span> <span data-ttu-id="06a74-119">Le rapport affiche le groupe de hiérarchies récursives, même si aucun retrait n'indique la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="06a74-119">The report displays the recursive hierarchy group, although there is no indent to show the hierarchy</span></span>  
  
### <a name="to-format-a-recursive-hierarchy-group-with-indent-levels"></a><span data-ttu-id="06a74-120">Pour mettre en forme un groupe de hiérarchies récursives avec des niveaux de retrait</span><span class="sxs-lookup"><span data-stu-id="06a74-120">To format a recursive hierarchy group with indent levels</span></span>  
  
1.  <span data-ttu-id="06a74-121">Cliquez sur la zone de texte qui contient le champ auquel vous souhaitez ajouter des niveaux de retrait pour afficher un format de hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="06a74-121">Click the text box that contains the field to which you want to add indent levels to display a hierarchy format.</span></span> <span data-ttu-id="06a74-122">Les propriétés de la zone de texte s'affichent dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="06a74-122">The properties for the text box appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="06a74-123">Si vous ne voyez pas le volet Propriétés, cliquez sur **Propriétés** sous l’onglet **Affichage** .</span><span class="sxs-lookup"><span data-stu-id="06a74-123">If you do not see the Properties pane, click **Properties** on the **View** tab.</span></span>  
  
2.  <span data-ttu-id="06a74-124">Dans le volet Propriétés, développez le `Padding` nœud, cliquez sur **gauche**, puis dans la liste déroulante, sélectionnez **\<Expression...>** .</span><span class="sxs-lookup"><span data-stu-id="06a74-124">In the Properties pane, expand the `Padding` node, click **Left**, and from the drop-down list, select **\<Expression...>**.</span></span>  
  
3.  <span data-ttu-id="06a74-125">Dans le volet Expression, tapez l'expression suivante :</span><span class="sxs-lookup"><span data-stu-id="06a74-125">In the Expression pane, type the following expression:</span></span>  
  
     `=CStr(2 + (Level()*10)) + "pt"`  
  
     <span data-ttu-id="06a74-126">Les propriétés de remplissage nécessitent toutes une chaîne au format *nnyy*, où *nn* est un nombre et *yy* une unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="06a74-126">The Padding properties all require a string in the format *nnyy*, where *nn* is a number and *yy* is the unit of measure.</span></span> <span data-ttu-id="06a74-127">L'exemple d'expression génère une chaîne utilisant la fonction `Level` pour augmenter la taille du remplissage en fonction du niveau de récursivité.</span><span class="sxs-lookup"><span data-stu-id="06a74-127">The example expression builds a string that uses the `Level` function to increase the size of the padding based on recursion level.</span></span> <span data-ttu-id="06a74-128">Ainsi, une ligne de niveau 1 implique un remplissage de 12 points (2 + (1\*10)) et une ligne de niveau 3 correspond à un remplissage de 32 points (2 + (3\*10)).</span><span class="sxs-lookup"><span data-stu-id="06a74-128">For example, a row that has a level of 1 would result in a padding of (2 + (1\*10))=12pt, and a row that has a level of 3 would result in a padding of (2 + (3\*10))=32pt.</span></span> <span data-ttu-id="06a74-129">Pour plus d’informations sur la `Level` fonction, consultez [niveau](report-builder-functions-level-function.md).</span><span class="sxs-lookup"><span data-stu-id="06a74-129">For information about the `Level` function, see [Level](report-builder-functions-level-function.md).</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="06a74-130">Exécutez le rapport.</span><span class="sxs-lookup"><span data-stu-id="06a74-130">Run the report.</span></span> <span data-ttu-id="06a74-131">Le rapport affiche une vue hiérarchique des données groupées.</span><span class="sxs-lookup"><span data-stu-id="06a74-131">The report displays a hierarchical view of the grouped data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a74-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="06a74-132">See Also</span></span>  
 <span data-ttu-id="06a74-133">[Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="06a74-133">[Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="06a74-134">[Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="06a74-134">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="06a74-135">[Informations de référence sur les fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span><span class="sxs-lookup"><span data-stu-id="06a74-135">[Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span></span>  
 <span data-ttu-id="06a74-136">[Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="06a74-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="06a74-137">[Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="06a74-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="06a74-138">[Listes &#40;Générateur de rapports et SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="06a74-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="06a74-139">Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="06a74-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
