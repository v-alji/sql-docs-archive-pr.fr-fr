---
title: Ajouter un filtre (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10ae54e7-0e8a-4dff-995d-05516c51d076
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61a5444c437027d92a9f054e74cbcac6af5cc776
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710191"
---
# <a name="add-a-filter-report-builder-and-ssrs"></a><span data-ttu-id="de0c4-102">Ajouter un filtre (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="de0c4-102">Add a Filter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="de0c4-103">Ajoutez un filtre à un dataset, une région de données ou un groupe lorsque vous souhaitez inclure ou exclure des valeurs spécifiques pour des calculs ou l'affichage.</span><span class="sxs-lookup"><span data-stu-id="de0c4-103">Add a filter to a dataset, data region, or group when you want to include or exclude specific values for calculations or display.</span></span> <span data-ttu-id="de0c4-104">Les filtres sont appliqués dans un premier temps au moment de l'exécution sur le dataset, puis sur la région de données, puis sur le groupe, dans l'ordre de haut en bas des hiérarchies de groupe.</span><span class="sxs-lookup"><span data-stu-id="de0c4-104">Filters are applied at run time first on the dataset, and then on the data region, and then on the group, in top-down order for group hierarchies.</span></span> <span data-ttu-id="de0c4-105">Dans une table, une matrice ou une liste, les filtres des groupes de lignes, des groupes de colonnes et des groupes adjacents sont appliqués indépendamment.</span><span class="sxs-lookup"><span data-stu-id="de0c4-105">In a table, matrix, or list, filters for row groups, column groups, and adjacent groups are applied independently.</span></span> <span data-ttu-id="de0c4-106">Dans un graphique, les filtres des groupes de catégories et des groupes de séries sont appliqués indépendamment.</span><span class="sxs-lookup"><span data-stu-id="de0c4-106">In a chart, filters for category groups and series groups are applied independently.</span></span>  
  
 <span data-ttu-id="de0c4-107">Pour ajouter un filtre, vous devez spécifier une ou plusieurs équations de filtre.</span><span class="sxs-lookup"><span data-stu-id="de0c4-107">To add a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="de0c4-108">Une équation de filtre est composée d'une expression qui identifie les données que vous souhaitez filtrer, d'un opérateur et de la valeur de comparaison.</span><span class="sxs-lookup"><span data-stu-id="de0c4-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="de0c4-109">Les types de données des données filtrées et de la valeur doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="de0c4-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="de0c4-110">Le tri sur des valeurs agrégées n'est pas pris en charge pour les datasets ou les régions de données.</span><span class="sxs-lookup"><span data-stu-id="de0c4-110">Filtering on aggregate values for a dataset or data region is not supported.</span></span>  
  
 <span data-ttu-id="de0c4-111">Pour filtrer des points de données dans un graphique, vous pouvez définir un filtre sur un groupe de catégories ou un groupe de séries.</span><span class="sxs-lookup"><span data-stu-id="de0c4-111">To filter data points in a chart, you can set a filter on a category group or a series group.</span></span> <span data-ttu-id="de0c4-112">Par défaut, le graphique utilise la fonction intégrée Sum pour agréger les valeurs appartenant au même groupe en un point de données individuel dans la série.</span><span class="sxs-lookup"><span data-stu-id="de0c4-112">By default, the chart uses the built-in function Sum to aggregate values that belong to the same group into an individual data point in the series.</span></span> <span data-ttu-id="de0c4-113">Si vous modifiez la fonction d'agrégation d'une série, vous devez modifier la fonction d'agrégation dans l'expression de filtre.</span><span class="sxs-lookup"><span data-stu-id="de0c4-113">If you change the aggregate function of a series, you must change the aggregate function in the filter expression.</span></span>  
  
 <span data-ttu-id="de0c4-114">Pour plus d’informations sur le filtrage de datasets incorporés et partagés, consultez [Ajouter un filtre à un dataset &#40;Générateur de rapports et SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de0c4-114">For more information about filtering embedded and shared datasets, see [Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-filter-on-a-data-region"></a><span data-ttu-id="de0c4-115">Pour définir un filtre sur une région de données</span><span class="sxs-lookup"><span data-stu-id="de0c4-115">To set a filter on a data region</span></span>  
  
1.  <span data-ttu-id="de0c4-116">Ouvrez un rapport en mode **Conception** .</span><span class="sxs-lookup"><span data-stu-id="de0c4-116">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="de0c4-117">Sélectionnez la région de données sur l’aire de conception, puis cliquez avec le bouton droit sur _\<data region>_ **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-117">Select the data region on the design surface, and then right-click _\<data region>_**Properties**.</span></span> <span data-ttu-id="de0c4-118">Pour une jauge, sélectionnez **Propriétés du panneau de jauge**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-118">For a gauge, select **Gauge Panel Properties**.</span></span> <span data-ttu-id="de0c4-119">La _\<data region>_ boîte de dialogue **Propriétés** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="de0c4-119">The _\<data region>_**Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de0c4-120">Dans une région de données de tableau matriciel, cliquez avec le bouton droit sur la cellule d’angle ou sur une poignée de ligne ou de colonne, puis cliquez sur **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-120">On a Tablix data region, right-click the corner cell or a row or column handle, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="de0c4-121">Cliquez sur **Filtres**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-121">Click **Filters**.</span></span> <span data-ttu-id="de0c4-122">La liste actuelle des équations de filtre s'affiche.</span><span class="sxs-lookup"><span data-stu-id="de0c4-122">This displays the current list of filter equations.</span></span> <span data-ttu-id="de0c4-123">Par défaut, elle est vide.</span><span class="sxs-lookup"><span data-stu-id="de0c4-123">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="de0c4-124">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-124">Click **Add**.</span></span> <span data-ttu-id="de0c4-125">Une nouvelle équation de filtre vierge apparaît.</span><span class="sxs-lookup"><span data-stu-id="de0c4-125">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="de0c4-126">Dans **Expression**, tapez ou sélectionnez l'expression pour le champ à filtrer.</span><span class="sxs-lookup"><span data-stu-id="de0c4-126">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="de0c4-127">Pour modifier l’expression, cliquez sur le bouton d’expression (*fx*).</span><span class="sxs-lookup"><span data-stu-id="de0c4-127">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="de0c4-128">Dans la liste déroulante, sélectionnez le type de données correspondant au type de données de l'expression que vous avez créée à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="de0c4-128">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="de0c4-129">Dans la zone **Opérateur** , sélectionnez l'opérateur que le filtre doit utiliser pour comparer les valeurs des zones **Expression** et **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="de0c4-129">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="de0c4-130">L'opérateur sélectionné détermine le nombre de valeurs utilisées pour l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="de0c4-130">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="de0c4-131">Dans la zone **Valeur** , tapez l'expression ou la valeur en fonction de laquelle le filtre doit évaluer la valeur indiquée dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-131">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="de0c4-132">Pour obtenir des exemples d’équations de filtre, consultez [Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de0c4-132">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-tablix-row-or-column-group"></a><span data-ttu-id="de0c4-133">Pour ajouter un filtre à un groupe de lignes ou de colonnes de tableau matriciel</span><span class="sxs-lookup"><span data-stu-id="de0c4-133">To set a filter on a Tablix row or column group</span></span>  
  
1.  <span data-ttu-id="de0c4-134">Ouvrez un rapport en mode **Conception** .</span><span class="sxs-lookup"><span data-stu-id="de0c4-134">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="de0c4-135">Sur l'aire de conception, cliquez avec le bouton droit sur la région de données de table, de matrice ou de liste pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="de0c4-135">Right-click the table, matrix, or list data region on the design surface to select it.</span></span> <span data-ttu-id="de0c4-136">Le volet Regroupement affiche les groupes de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="de0c4-136">The Grouping pane displays the groups for the selected item.</span></span>  
  
3.  <span data-ttu-id="de0c4-137">Dans le volet Regroupement, cliquez avec le bouton droit sur le groupe, puis cliquez sur **Modifier le groupe**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-137">In the Grouping pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="de0c4-138">La boîte de dialogue **Groupe de tableaux matriciels** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="de0c4-138">The **Tablix Group** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="de0c4-139">Cliquez sur **Filtres**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-139">Click **Filters**.</span></span> <span data-ttu-id="de0c4-140">La liste actuelle des équations de filtre s'affiche.</span><span class="sxs-lookup"><span data-stu-id="de0c4-140">This displays the current list of filter equations.</span></span> <span data-ttu-id="de0c4-141">Par défaut, elle est vide.</span><span class="sxs-lookup"><span data-stu-id="de0c4-141">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="de0c4-142">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-142">Click **Add**.</span></span> <span data-ttu-id="de0c4-143">Une nouvelle équation de filtre vierge apparaît.</span><span class="sxs-lookup"><span data-stu-id="de0c4-143">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="de0c4-144">Dans **Expression**, tapez ou sélectionnez l'expression pour le champ à filtrer.</span><span class="sxs-lookup"><span data-stu-id="de0c4-144">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="de0c4-145">Pour modifier l’expression, cliquez sur le bouton d’expression (*fx*).</span><span class="sxs-lookup"><span data-stu-id="de0c4-145">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="de0c4-146">Dans la liste déroulante, sélectionnez le type de données correspondant au type de données de l'expression que vous avez créée à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="de0c4-146">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="de0c4-147">Dans la zone **Opérateur** , sélectionnez l'opérateur que le filtre doit utiliser pour comparer les valeurs des zones **Expression** et **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="de0c4-147">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="de0c4-148">L'opérateur sélectionné détermine le nombre de valeurs utilisées pour l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="de0c4-148">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="de0c4-149">Dans la zone **Valeur** , tapez l'expression ou la valeur en fonction de laquelle le filtre doit évaluer la valeur indiquée dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-149">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="de0c4-150">Pour obtenir des exemples d’équations de filtre, consultez [Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de0c4-150">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-category-group"></a><span data-ttu-id="de0c4-151">Pour définir un filtre sur un groupe de catégories de graphique.</span><span class="sxs-lookup"><span data-stu-id="de0c4-151">To set a filter on a Chart category group</span></span>  
  
1.  <span data-ttu-id="de0c4-152">Ouvrez un rapport en mode **Conception** .</span><span class="sxs-lookup"><span data-stu-id="de0c4-152">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="de0c4-153">Sur l'aire de conception, cliquez deux fois sur le graphique pour appeler les zones de dépôt des champs de données, de série et de catégorie.</span><span class="sxs-lookup"><span data-stu-id="de0c4-153">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="de0c4-154">Cliquez avec le bouton droit sur un champ de la zone de dépôt du champ de catégorie, puis sélectionnez **Propriétés du groupe de catégories**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-154">Right-click on a field contained in the category field drop zone and select **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="de0c4-155">Cliquez sur **Filtres**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-155">Click **Filters**.</span></span> <span data-ttu-id="de0c4-156">La liste actuelle des équations de filtre s'affiche.</span><span class="sxs-lookup"><span data-stu-id="de0c4-156">This displays the current list of filter equations.</span></span> <span data-ttu-id="de0c4-157">Par défaut, elle est vide.</span><span class="sxs-lookup"><span data-stu-id="de0c4-157">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="de0c4-158">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-158">Click **Add**.</span></span> <span data-ttu-id="de0c4-159">Une nouvelle équation de filtre vierge apparaît.</span><span class="sxs-lookup"><span data-stu-id="de0c4-159">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="de0c4-160">Dans **Expression**, tapez ou sélectionnez l'expression pour le champ à filtrer.</span><span class="sxs-lookup"><span data-stu-id="de0c4-160">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="de0c4-161">Pour modifier l’expression, cliquez sur le bouton d’expression (*fx*).</span><span class="sxs-lookup"><span data-stu-id="de0c4-161">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="de0c4-162">Dans la liste déroulante, sélectionnez le type de données correspondant au type de données de l'expression que vous avez créée à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="de0c4-162">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="de0c4-163">Dans la zone **Opérateur** , sélectionnez l'opérateur que le filtre doit utiliser pour comparer les valeurs des zones **Expression** et **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="de0c4-163">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="de0c4-164">L'opérateur sélectionné détermine le nombre de valeurs utilisées pour l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="de0c4-164">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="de0c4-165">Dans la zone **Valeur** , tapez l'expression ou la valeur en fonction de laquelle le filtre doit évaluer la valeur indiquée dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-165">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="de0c4-166">Pour obtenir des exemples d’équations de filtre, consultez [Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de0c4-166">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-series-group"></a><span data-ttu-id="de0c4-167">Pour définir un filtre sur un groupe de série de graphique.</span><span class="sxs-lookup"><span data-stu-id="de0c4-167">To set a filter on a Chart series group</span></span>  
  
1.  <span data-ttu-id="de0c4-168">Ouvrez un rapport en mode **Conception** .</span><span class="sxs-lookup"><span data-stu-id="de0c4-168">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="de0c4-169">Sur l'aire de conception, cliquez deux fois sur le graphique pour appeler les zones de dépôt des champs de données, de série et de catégorie.</span><span class="sxs-lookup"><span data-stu-id="de0c4-169">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="de0c4-170">Cliquez avec le bouton droit sur un champ de la zone de dépôt du champ de série, puis sélectionnez **Propriétés du groupe de séries**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-170">Right-click on a field contained in the series field drop zone and select **Series Group Properties**.</span></span>  
  
4.  <span data-ttu-id="de0c4-171">Cliquez sur **Filtres**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-171">Click **Filters**.</span></span> <span data-ttu-id="de0c4-172">La liste actuelle des équations de filtre s'affiche.</span><span class="sxs-lookup"><span data-stu-id="de0c4-172">This displays the current list of filter equations.</span></span> <span data-ttu-id="de0c4-173">Par défaut, elle est vide.</span><span class="sxs-lookup"><span data-stu-id="de0c4-173">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="de0c4-174">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-174">Click **Add**.</span></span> <span data-ttu-id="de0c4-175">Une nouvelle équation de filtre vierge apparaît.</span><span class="sxs-lookup"><span data-stu-id="de0c4-175">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="de0c4-176">Dans **Expression**, tapez ou sélectionnez l'expression pour le champ à filtrer.</span><span class="sxs-lookup"><span data-stu-id="de0c4-176">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="de0c4-177">Pour modifier l’expression, cliquez sur le bouton d’expression (*fx*).</span><span class="sxs-lookup"><span data-stu-id="de0c4-177">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="de0c4-178">Dans la liste déroulante, sélectionnez le type de données correspondant au type de données de l'expression que vous avez créée à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="de0c4-178">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="de0c4-179">Dans la zone **Opérateur** , sélectionnez l'opérateur que le filtre doit utiliser pour comparer les valeurs des zones **Expression** et **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="de0c4-179">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="de0c4-180">L'opérateur sélectionné détermine le nombre de valeurs utilisées pour l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="de0c4-180">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="de0c4-181">Dans la zone **Valeur** , tapez l'expression ou la valeur en fonction de laquelle le filtre doit évaluer la valeur indiquée dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="de0c4-181">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="de0c4-182">Pour obtenir des exemples d’équations de filtre, consultez [Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de0c4-182">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de0c4-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de0c4-183">See Also</span></span>  
 <span data-ttu-id="de0c4-184">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupes &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="de0c4-184">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="de0c4-185">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de0c4-185">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="de0c4-186">[Jauges &#40;Générateur de rapports et SSRS&#41;](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de0c4-186">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="de0c4-187">[Répertorie &#40;Générateur de rapports et SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de0c4-187">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="de0c4-188">Graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="de0c4-188">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
