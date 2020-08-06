---
title: Trier des données dans une région de données (Générateur de rapports et SSRS)| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2fcb9be2-1daa-4c92-ad00-5f63cdf39f70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc1fb458066bb942a490b08c0faad876dd3d5438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707059"
---
# <a name="sort-data-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="af501-102">Trier des données dans une région de données (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="af501-102">Sort Data in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="af501-103">Pour changer l'ordre de tri des données dans une région de données à la première exécution d'un rapport, vous devez définir l'expression de tri sur le groupe ou la région de données.</span><span class="sxs-lookup"><span data-stu-id="af501-103">To change the sort order of data in a data region when a report first runs, you must set the sort expression on the data region or group.</span></span> <span data-ttu-id="af501-104">Par défaut, l'expression de tri d'un groupe a automatiquement la même valeur que l'expression de groupe.</span><span class="sxs-lookup"><span data-stu-id="af501-104">By default, the sort expression for a group is automatically set to the same value as the group expression.</span></span>  
  
-   <span data-ttu-id="af501-105">Dans une région de données de tableau matriciel, définissez l'expression de tri pour la région de données ou pour chaque groupe, y compris pour le groupe de détails.</span><span class="sxs-lookup"><span data-stu-id="af501-105">In a tablix data region, set the sort expression for the data region or for each group, including the details group.</span></span> <span data-ttu-id="af501-106">Si une région de données de tableau matriciel ne contient qu’un seul groupe de détails, vous pouvez définir une expression de tri dans la requête, sur la région de données ou sur le groupe de détails ; l’effet sera identique.</span><span class="sxs-lookup"><span data-stu-id="af501-106">If you have only one details group in a tablix data region, you can define a sort expression in the query, on the data region, or on the details group and they all have the same effect.</span></span>  
  
-   <span data-ttu-id="af501-107">Dans une région de données de graphique, définissez l’expression de tri pour les groupes de catégories et de séries afin de contrôler l’ordre de tri de chaque de groupe.</span><span class="sxs-lookup"><span data-stu-id="af501-107">In a chart data region, set the sort expression for the Category and Series groups to control the sort order for each group.</span></span> <span data-ttu-id="af501-108">L'ordre des couleurs dans une légende de graphique est déterminé par l'expression de tri des points de données dans le groupe de catégories.</span><span class="sxs-lookup"><span data-stu-id="af501-108">The order for colors in a chart legend is determined by the sort expression for the data points in the Category group.</span></span>  
  
-   <span data-ttu-id="af501-109">Dans une région de données de jauge, vous n'avez généralement pas besoin de trier les données, la jauge affichant une valeur unique relative à une plage.</span><span class="sxs-lookup"><span data-stu-id="af501-109">In a gauge data region, you do not typically need to sort data because the gauge displays a single value relative to a range.</span></span> <span data-ttu-id="af501-110">Si vous devez trier les données dans une jauge, définissez d’abord un groupe, puis l’expression de tri pour ce dernier.</span><span class="sxs-lookup"><span data-stu-id="af501-110">If you do need sort data in a gauge, you must first define a group, and then set the sort expression for the group.</span></span>  
  
 <span data-ttu-id="af501-111">Pour plus d’informations, consultez [Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="af501-111">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="af501-112">Pour une région de données de tableau matriciel, vous pouvez également ajouter un bouton de tri interactif en haut d’un en-tête de colonne pour permettre aux utilisateurs de modifier l’ordre de tri des groupes ou des lignes de détails.</span><span class="sxs-lookup"><span data-stu-id="af501-112">For a tablix data region, you can also add an interactive sort button to the top of a column header to provide the user with the ability to change the sort order of groups or detail rows.</span></span> <span data-ttu-id="af501-113">Pour plus d’informations, consultez [Tri interactif &#40;Générateur de rapports et SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="af501-113">For more information, see [Interactive Sort &#40;Report Builder and SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-sort-data-in-a-tablix-data-region"></a><span data-ttu-id="af501-114">Pour trier les données dans une région de données de tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="af501-114">To sort data in a Tablix data region</span></span>  
  
1.  <span data-ttu-id="af501-115">Dans l’aire de conception, cliquez avec le bouton droit sur un descripteur de ligne, puis cliquez sur **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="af501-115">On the design surface, right-click a row handle, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="af501-116">Cliquez sur **Tri**.</span><span class="sxs-lookup"><span data-stu-id="af501-116">Click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="af501-117">Pour chaque expression de tri, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="af501-117">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="af501-118">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="af501-118">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="af501-119">Tapez ou sélectionnez une expression selon laquelle trier les données.</span><span class="sxs-lookup"><span data-stu-id="af501-119">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="af501-120">Dans la liste déroulante de la colonne **Ordre** , sélectionnez le sens de tri de chaque expression.</span><span class="sxs-lookup"><span data-stu-id="af501-120">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="af501-121">**A-Z** trie l’expression par ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="af501-121">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="af501-122">**Z-A** trie l’expression par ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="af501-122">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-values-in-a-group-including-the-details-group-for-a-tablix"></a><span data-ttu-id="af501-123">Pour trier les valeurs dans un groupe, y compris dans un groupe de détails, d'un tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="af501-123">To sort values in a group, including the details group, for a Tablix</span></span>  
  
1.  <span data-ttu-id="af501-124">Dans l'aire de conception, cliquez dans la région de données de tableau matriciel pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="af501-124">On the design surface, click in the tablix data region to select it.</span></span> <span data-ttu-id="af501-125">Le volet Regroupement affiche les groupes de lignes et de colonnes de la région de données de tableau matriciel.</span><span class="sxs-lookup"><span data-stu-id="af501-125">The Grouping pane displays the row groups and column groups for the Tablix data region.</span></span>  
  
2.  <span data-ttu-id="af501-126">Dans le volet Groupes de lignes, cliquez avec le bouton droit sur le nom du groupe, puis cliquez sur **Modifier le groupe**.</span><span class="sxs-lookup"><span data-stu-id="af501-126">In the Row Groups pane, right-click the group name, and then click **Edit Group**.</span></span>  
  
3.  <span data-ttu-id="af501-127">Dans la boîte de dialogue **Groupe de tableaux matriciels** , cliquez sur **Trier**.</span><span class="sxs-lookup"><span data-stu-id="af501-127">In the **Tablix Group** dialog box, click **Sort**.</span></span>  
  
4.  <span data-ttu-id="af501-128">Pour chaque expression de tri, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="af501-128">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="af501-129">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="af501-129">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="af501-130">Tapez ou sélectionnez une expression selon laquelle trier les données.</span><span class="sxs-lookup"><span data-stu-id="af501-130">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="af501-131">Dans la liste déroulante de la colonne **Ordre** , sélectionnez le sens de tri de chaque expression.</span><span class="sxs-lookup"><span data-stu-id="af501-131">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="af501-132">**A-Z** trie l’expression par ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="af501-132">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="af501-133">**Z-A** trie l’expression par ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="af501-133">**Z-A** sorts the expression in descending order.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-x-axis-labels-in-alphabetical-order-on-a-chart"></a><span data-ttu-id="af501-134">Pour trier les étiquettes de l'axe X par ordre alphabétique sur un graphique</span><span class="sxs-lookup"><span data-stu-id="af501-134">To sort x-axis labels in alphabetical order on a chart</span></span>  
  
1.  <span data-ttu-id="af501-135">Cliquez avec le bouton droit sur un champ de la zone de dépôt Champ de catégorie, puis cliquez sur **Propriétés du groupe de catégories**.</span><span class="sxs-lookup"><span data-stu-id="af501-135">Right-click a field in the Category Field drop-zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="af501-136">Dans la boîte de dialogue **Propriétés du groupe de catégories** , cliquez sur **Tri**.</span><span class="sxs-lookup"><span data-stu-id="af501-136">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="af501-137">Pour chaque expression de tri, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="af501-137">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="af501-138">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="af501-138">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="af501-139">Sélectionnez l'expression qui correspond à votre champ de regroupement.</span><span class="sxs-lookup"><span data-stu-id="af501-139">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="af501-140">Vous pouvez vérifier l’expression du champ de regroupement en cliquant sur **Regroupement**.</span><span class="sxs-lookup"><span data-stu-id="af501-140">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="af501-141">Dans la liste déroulante de la colonne **Ordre** , sélectionnez le sens de tri de chaque expression.</span><span class="sxs-lookup"><span data-stu-id="af501-141">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="af501-142">**A-Z** trie l’expression par ordre alphabétique croissant.</span><span class="sxs-lookup"><span data-stu-id="af501-142">**A-Z** sorts the expression in ascending alphabetical order.</span></span> <span data-ttu-id="af501-143">**Z-A** trie l’expression par ordre alphabétique décroissant.</span><span class="sxs-lookup"><span data-stu-id="af501-143">**Z-A** sorts the expression in descending alphabetical order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-the-data-points-in-ascending-or-descending-order-on-a-chart"></a><span data-ttu-id="af501-144">Pour trier les points de données par ordre croissant ou décroissant sur un graphique</span><span class="sxs-lookup"><span data-stu-id="af501-144">To sort the data points in ascending or descending order on a chart</span></span>  
  
1.  <span data-ttu-id="af501-145">Cliquez avec le bouton droit sur un champ de la zone de dépôt Champ de catégorie, puis cliquez sur **Propriétés du groupe de catégories**.</span><span class="sxs-lookup"><span data-stu-id="af501-145">Right-click a field in the Category Field drop zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="af501-146">Dans la boîte de dialogue **Propriétés du groupe de catégories** , cliquez sur **Tri**.</span><span class="sxs-lookup"><span data-stu-id="af501-146">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="af501-147">Pour chaque expression de tri, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="af501-147">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="af501-148">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="af501-148">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="af501-149">Sélectionnez l'expression qui correspond à votre champ de données.</span><span class="sxs-lookup"><span data-stu-id="af501-149">Select the expression that matches your data field.</span></span> <span data-ttu-id="af501-150">Dans la plupart des cas, il s’agit d’une valeur agrégée, telle que `=Sum(Fields!Quantity.Value)`.</span><span class="sxs-lookup"><span data-stu-id="af501-150">In most cases, this is an aggregated value, such as `=Sum(Fields!Quantity.Value)`.</span></span>  
  
    3.  <span data-ttu-id="af501-151">Dans la liste déroulante de la colonne **Ordre** , sélectionnez le sens de tri de chaque expression.</span><span class="sxs-lookup"><span data-stu-id="af501-151">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="af501-152">**A-Z** trie l’expression par ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="af501-152">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="af501-153">**Z-A** trie l’expression par ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="af501-153">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-data-in-ascending-or-descending-order-for-display-on-a-gauge"></a><span data-ttu-id="af501-154">Pour trier les données par ordre croissant ou décroissant sur l'affichage d'une jauge</span><span class="sxs-lookup"><span data-stu-id="af501-154">To sort data in ascending or descending order for display on a gauge</span></span>  
  
1.  <span data-ttu-id="af501-155">Cliquez avec le bouton droit sur la jauge, puis cliquez sur **Ajouter un groupe de données**.</span><span class="sxs-lookup"><span data-stu-id="af501-155">Right-click the gauge and click **Add Data Group**.</span></span>  
  
2.  <span data-ttu-id="af501-156">Dans la boîte de dialogue **Propriétés du groupe de panneaux de jauges** , cliquez sur **Général** si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="af501-156">In the **Gauge Panel GroupProperties** dialog box, click **General** if necessary.</span></span>  
  
3.  <span data-ttu-id="af501-157">Dans **Expressions Groupe**, cliquez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="af501-157">In **Group expressions**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="af501-158">Dans **Regrouper sur**, tapez ou sélectionnez une expression selon laquelle regrouper les données.</span><span class="sxs-lookup"><span data-stu-id="af501-158">In **Group on**, type or select an expression by which to group the data.</span></span>  
  
5.  <span data-ttu-id="af501-159">Répétez les étapes 3 et 4 autant de fois que nécessaire pour ajouter toutes les expressions de groupe que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="af501-159">Repeat steps 3 and 4 until you have added all the group expressions you want to use.</span></span>  
  
6.  <span data-ttu-id="af501-160">Cliquez sur **Tri**.</span><span class="sxs-lookup"><span data-stu-id="af501-160">Click **Sorting**.</span></span>  
  
7.  <span data-ttu-id="af501-161">Pour chaque expression de tri, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="af501-161">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="af501-162">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="af501-162">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="af501-163">Sélectionnez l'expression qui correspond à votre champ de regroupement.</span><span class="sxs-lookup"><span data-stu-id="af501-163">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="af501-164">Vous pouvez vérifier l’expression du champ de regroupement en cliquant sur **Regroupement**.</span><span class="sxs-lookup"><span data-stu-id="af501-164">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="af501-165">Dans la liste déroulante de la colonne **Ordre** , sélectionnez le sens de tri de chaque expression.</span><span class="sxs-lookup"><span data-stu-id="af501-165">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="af501-166">**A-Z** trie l’expression par ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="af501-166">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="af501-167">**Z-A** trie l’expression par ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="af501-167">**Z-A** sorts the expression in descending order.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="af501-168">Pour plus d’informations sur la façon dont les données sont regroupées dans une jauge, consultez [Jauges &#40;Générateur de rapports et SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="af501-168">For more information about how data is grouped in a gauge, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af501-169">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af501-169">See Also</span></span>  
 <span data-ttu-id="af501-170">[Aide Générateur de rapports pour les boîtes de dialogue, les volets et les assistants](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="af501-170">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="af501-171">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="af501-171">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="af501-172">[Mise en forme des étiquettes d’axe sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="af501-172">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="af501-173">Spécifier des couleurs cohérentes pour plusieurs graphiques à base de formes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="af501-173">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
