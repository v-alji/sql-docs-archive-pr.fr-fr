---
title: Afficher les mêmes données dans une matrice et sur un graphique (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1262f283-9fc2-4bc1-9c79-457f7642abc7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7746ce1f06d4dcc67c51ddc40714f19a3ff83d51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704916"
---
# <a name="display-the-same-data-on-a-matrix-and-a-chart-report-builder"></a><span data-ttu-id="21b6a-102">Afficher les mêmes données dans une matrice et sur un graphique (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="21b6a-102">Display the Same Data on a Matrix and a Chart (Report Builder)</span></span>
  <span data-ttu-id="21b6a-103">Pour afficher les mêmes données dans une matrice et sur un graphique, vous devez définir des propriétés sur ces deux régions de données afin de spécifier le même dataset, ainsi que les mêmes expressions pour les filtres, les groupes, les tris et les données.</span><span class="sxs-lookup"><span data-stu-id="21b6a-103">When you want to show the same data in a matrix and a chart, you must set properties on both data regions to specify the same dataset, and also the same expressions for filters, groups, sorts, and data.</span></span>  
  
 <span data-ttu-id="21b6a-104">Étant donné que les deux régions de données auront le même ancêtre de données (à savoir le dataset du rapport), vous pouvez ajouter à la matrice un bouton de tri interactif qui permettra aux utilisateurs de modifier l'ordre de tri à la fois pour la matrice et le graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-104">Because both data regions will have the same ancestor for data (the report dataset), you can add an interactive sort button to the matrix that, when the user clicks it, changes the sort order for both the matrix and the chart.</span></span> <span data-ttu-id="21b6a-105">Pour plus d’informations, consultez [Ajouter un tri interactif à un tableau ou une matrice &#40;Générateur de rapports et SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="21b6a-105">For more information, see [Add Interactive Sort to a Table or Matrix &#40;Report Builder and SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="21b6a-106">Pour utiliser les valeurs de groupe de colonnes de matrice comme légende pour le graphique, vous devez spécifier les couleurs des données de série sur le graphique, puis utiliser les mêmes couleurs que les couleurs de remplissage pour l'arrière-plan des zones de texte de la cellule de matrice qui affiche les valeurs de groupe.</span><span class="sxs-lookup"><span data-stu-id="21b6a-106">To use the matrix column group values as a legend for the chart, you must specify the colors for the series data on the chart, and then use the same colors as the fill colors for the background of the text boxes in the matrix cell that displays the group values.</span></span> <span data-ttu-id="21b6a-107">Pour plus d’informations, consultez [Spécifier des couleurs cohérentes pour plusieurs graphiques à base de formes &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="21b6a-107">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="21b6a-108">Au moment de l'exécution, votre rapport peut paraître surchargé s'il contient un trop grand nombre de valeurs de groupe pour vos définitions de groupe.</span><span class="sxs-lookup"><span data-stu-id="21b6a-108">At run-time, your report may appear cluttered if there are too many group values for your group definitions.</span></span> <span data-ttu-id="21b6a-109">Il peut s'avérer nécessaire de filtrer des valeurs, de combiner des groupes ou d'ajuster le seuil pour que le graphique combine les groupes à votre place.</span><span class="sxs-lookup"><span data-stu-id="21b6a-109">You might need to filter values, combine groups, or adjust the threshold for the chart to combine groups for you.</span></span> <span data-ttu-id="21b6a-110">Pour plus d’informations, consultez [Liaison de plusieurs régions de données à un même dataset &#40;Générateur de rapports et SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="21b6a-110">For more information, see [Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-matrix-and-chart-to-display-the-same-data"></a><span data-ttu-id="21b6a-111">Pour ajouter une matrice et un graphique affichant les mêmes données</span><span class="sxs-lookup"><span data-stu-id="21b6a-111">To add a matrix and chart to display the same data</span></span>  
  
1.  <span data-ttu-id="21b6a-112">Ouvrez un rapport en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="21b6a-112">Open a report in design view.</span></span>  
  
2.  <span data-ttu-id="21b6a-113">Sous l’onglet **Insérer** , dans le groupe **Régions de données** , cliquez sur **Matrice**, puis cliquez dans le corps du rapport ou dans un rectangle du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="21b6a-113">From the **Insert** tab, in the **Data Regions** group, click **Matrix**, and then click the report body or in a rectangle in the report body.</span></span> <span data-ttu-id="21b6a-114">Une matrice est ajoutée au rapport.</span><span class="sxs-lookup"><span data-stu-id="21b6a-114">A matrix is added to the report.</span></span>  
  
3.  <span data-ttu-id="21b6a-115">Sous l’onglet **Insérer** , dans le groupe **Régions de données** , cliquez sur **Graphique**, puis sélectionnez le type de graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-115">From the **Insert** tab, in the **Data Regions** group, click **Chart**, and then select the chart type.</span></span> <span data-ttu-id="21b6a-116">Un graphique est ajouté au rapport.</span><span class="sxs-lookup"><span data-stu-id="21b6a-116">A chart is added to the report.</span></span>  
  
4.  <span data-ttu-id="21b6a-117">(Facultatif) Sous l’onglet **Insérer** , dans le groupe **Éléments de rapport** , cliquez sur **Rectangle**, puis cliquez sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="21b6a-117">(Optional) From the **Insert** tab, in the **Report Items** group, click **Rectangle**, and then click the report.</span></span> <span data-ttu-id="21b6a-118">Un rectangle est ajouté au rapport.</span><span class="sxs-lookup"><span data-stu-id="21b6a-118">A rectangle is added to the report.</span></span> <span data-ttu-id="21b6a-119">Faites glisser la matrice et le graphique des étapes 2 et 3 dans le rectangle.</span><span class="sxs-lookup"><span data-stu-id="21b6a-119">Drag the matrix and chart from steps 2 and 3 into the rectangle.</span></span>  
  
     <span data-ttu-id="21b6a-120">Le fait de placer plusieurs régions de données dans le conteneur rectangle vous permet de contrôler plus facilement le rendu de la matrice et du graphique lors de la visualisation du rapport.</span><span class="sxs-lookup"><span data-stu-id="21b6a-120">By placing multiple data regions in the rectangle container, you help control how the matrix and chart render when you view the report.</span></span>  
  
     <span data-ttu-id="21b6a-121">Aux étapes suivantes, vous allez choisir le même champ de dataset à afficher dans la matrice et dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-121">In the next few steps, you will choose the same dataset field to display in the matrix and to display in the chart.</span></span>  
  
5.  <span data-ttu-id="21b6a-122">À partir du volet Données du rapport, faites glisser un champ de dataset numérique vers la cellule de données de la matrice.</span><span class="sxs-lookup"><span data-stu-id="21b6a-122">From the Report Data pane, drag a numeric dataset field to the Data cell in the matrix.</span></span>  
  
     <span data-ttu-id="21b6a-123">Par défaut, la fonction d’agrégation Sum est utilisée pour calculer la valeur de groupe.</span><span class="sxs-lookup"><span data-stu-id="21b6a-123">By default, the aggregate function Sum is used for calculating the group value.</span></span> <span data-ttu-id="21b6a-124">Si vous modifiez la fonction d'agrégation dans la matrice, vous devez également la modifier dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-124">If you change the aggregate function in the matrix, you must change in the chart also.</span></span>  
  
6.  <span data-ttu-id="21b6a-125">Dans la matrice, cliquez avec le bouton droit sur la cellule contenant les données, cliquez sur **Propriétés de la zone de texte**, puis sur **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="21b6a-125">In the matrix, right-click the cell with data, click **Text Box Properties**, and then click **Number**.</span></span> <span data-ttu-id="21b6a-126">Choisissez un format approprié pour la valeur de champ de dataset.</span><span class="sxs-lookup"><span data-stu-id="21b6a-126">Choose an appropriate format for the dataset field value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="21b6a-127">Faites glisser le même champ de dataset que celui sélectionné à l’étape 3 vers la zone **Valeurs** sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-127">Drag the same dataset field you chose in step 3 to the **Values** area on the chart.</span></span>  
  
9. <span data-ttu-id="21b6a-128">Sur le graphique, cliquez avec le bouton droit sur l’axe Y, cliquez sur **Propriétés de l’axe**, puis sur **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="21b6a-128">In the chart, right-click the Y axis, click **Axis Properties**, and then click **Number**.</span></span> <span data-ttu-id="21b6a-129">Choisissez pour les données le même format que celui sélectionné à l'étape 4.</span><span class="sxs-lookup"><span data-stu-id="21b6a-129">Choose the same format for the data that you chose in step 4.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="21b6a-130">Aux étapes suivantes, vous devez affecter au groupe de lignes de la matrice et au groupe de séries du graphique la même expression, ainsi que définir l'ordre de tri du groupe de séries du graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-130">In the next few steps, you will set the matrix row group and the chart series group to the same expression, and also set the sort order for the chart series group.</span></span>  
  
11. <span data-ttu-id="21b6a-131">À partir du volet Données du rapport, faites glisser vers le volet Groupe de lignes le champ de dataset selon lequel vous souhaitez effectuer le regroupement des lignes de la matrice.</span><span class="sxs-lookup"><span data-stu-id="21b6a-131">From the Report Data pane, drag the dataset field that you want to group by for matrix rows to the Row Groups pane.</span></span>  
  
     <span data-ttu-id="21b6a-132">Par défaut, le groupe de lignes de la matrice ajoute une expression de tri identique à l'expression de groupe.</span><span class="sxs-lookup"><span data-stu-id="21b6a-132">By default, the matrix row group adds a sort expression that is the same as the group expression.</span></span>  
  
12. <span data-ttu-id="21b6a-133">Faites glisser le même champ de dataset que celui utilisé à l’étape 9 vers la zone **Groupes de séries** du graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-133">Drag the same dataset field that you used in step 9 to the **Series Groups** area for the chart.</span></span>  
  
13. <span data-ttu-id="21b6a-134">Cliquez avec le bouton droit sur le groupe dans la zone **Groupes de séries** , puis sélectionnez **Propriétés du groupe de séries**.</span><span class="sxs-lookup"><span data-stu-id="21b6a-134">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
14. <span data-ttu-id="21b6a-135">Cliquez sur **Tri**.</span><span class="sxs-lookup"><span data-stu-id="21b6a-135">Click **Sorting**.</span></span>  
  
15. <span data-ttu-id="21b6a-136">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="21b6a-136">Click **Add**.</span></span> <span data-ttu-id="21b6a-137">Une nouvelle ligne apparaît dans la grille d'expressions de tri.</span><span class="sxs-lookup"><span data-stu-id="21b6a-137">A new row appears in the sort expressions grid.</span></span>  
  
16. <span data-ttu-id="21b6a-138">Dans **Trier par**, dans la liste déroulante, sélectionnez le champ de dataset selon lequel vous avez choisi d’effectuer le regroupement à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="21b6a-138">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 9.</span></span>  
  
17. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="21b6a-139">Aux étapes suivantes, vous devez affecter au groupe de colonnes de la matrice et au groupe de catégories du graphique la même expression, ainsi que définir l'ordre de tri du groupe de catégories du graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-139">In the next few steps, you will set the matrix column group and the chart category group to the same expression, and also set the sort order for the chart category group.</span></span>  
  
18. <span data-ttu-id="21b6a-140">À partir du volet Données du rapport, faites glisser vers le volet Groupes de colonnes le champ de dataset selon lequel vous souhaitez effectuer le regroupement des colonnes de la matrice.</span><span class="sxs-lookup"><span data-stu-id="21b6a-140">From the Report Data pane, drag the dataset field that you want to group by for matrix columns to the Column Groups pane.</span></span>  
  
     <span data-ttu-id="21b6a-141">Par défaut, le groupe de colonnes de la matrice ajoute une expression de tri identique à l'expression de groupe.</span><span class="sxs-lookup"><span data-stu-id="21b6a-141">By default, the matrix column group adds a sort expression that is the same as the group expression.</span></span>  
  
19. <span data-ttu-id="21b6a-142">Faites glisser le même champ de dataset que celui utilisé à l’étape 16 vers la zone **Groupes de catégories** du graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-142">Drag the same dataset field that you used in step 16 to the **Category Groups** area for the chart.</span></span>  
  
20. <span data-ttu-id="21b6a-143">Cliquez avec le bouton droit sur le groupe dans la zone **Groupes de catégories** , puis cliquez sur **Propriétés du groupe de catégories**.</span><span class="sxs-lookup"><span data-stu-id="21b6a-143">Right-click the group in the **CategoryGroups** area, and then click **Category Group Properties**.</span></span>  
  
21. <span data-ttu-id="21b6a-144">Cliquez sur **Tri**.</span><span class="sxs-lookup"><span data-stu-id="21b6a-144">Click **Sorting**.</span></span>  
  
22. <span data-ttu-id="21b6a-145">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="21b6a-145">Click **Add**.</span></span> <span data-ttu-id="21b6a-146">Une nouvelle ligne apparaît dans la grille d'expressions de tri.</span><span class="sxs-lookup"><span data-stu-id="21b6a-146">A new row appears in the sort expressions grid.</span></span>  
  
23. <span data-ttu-id="21b6a-147">Dans **Trier par**, dans la liste déroulante, sélectionnez le champ de dataset selon lequel vous avez choisi d’effectuer le regroupement à l’étape 16.</span><span class="sxs-lookup"><span data-stu-id="21b6a-147">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 16.</span></span>  
  
24. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
25. <span data-ttu-id="21b6a-148">Affichez un aperçu du résultat.</span><span class="sxs-lookup"><span data-stu-id="21b6a-148">Preview the result.</span></span> <span data-ttu-id="21b6a-149">Les groupes de lignes et de colonnes de la matrice affichent les mêmes données que les groupes de catégories et de séries du graphique.</span><span class="sxs-lookup"><span data-stu-id="21b6a-149">The matrix row and column groups display the same data as the chart series and category groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b6a-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21b6a-150">See Also</span></span>  
 <span data-ttu-id="21b6a-151">[Liaison de plusieurs régions de données à un même dataset &#40;Générateur de rapports et SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="21b6a-151">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="21b6a-152">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupes &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="21b6a-152">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="21b6a-153">[Répertorie &#40;Générateur de rapports et SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="21b6a-153">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="21b6a-154">Graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="21b6a-154">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
