---
title: Modifier la vue des résultats de trace | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 860a80dc-bac0-4ef0-bf7f-7a9b430d7aa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 050c8f179742cf3cef6473b03f062390caf195f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601638"
---
# <a name="modify-the-trace-results-view"></a><span data-ttu-id="f237d-102">Modifier la vue des résultats de trace</span><span class="sxs-lookup"><span data-stu-id="f237d-102">Modify the Trace Results View</span></span>
  <span data-ttu-id="f237d-103">Cette rubrique explique comment modifier la vue des résultats de trace d'une session événements étendus dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] en effectuant les tâches suivantes.</span><span class="sxs-lookup"><span data-stu-id="f237d-103">This topic describes how to modify the trace results view of an Extended Events session in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] by performing the following tasks.</span></span>  
  
1.  [<span data-ttu-id="f237d-104">Ajouter ou supprimer des colonnes</span><span class="sxs-lookup"><span data-stu-id="f237d-104">Add or Remove Columns</span></span>](#AddRemoveColumns)  
  
2.  [<span data-ttu-id="f237d-105">Créer, modifier ou supprimer des colonnes fusionnées</span><span class="sxs-lookup"><span data-stu-id="f237d-105">Create, Edit, or Delete Merged Columns</span></span>](#ChangeColumns)  
  
3.  [<span data-ttu-id="f237d-106">Trier les résultats</span><span class="sxs-lookup"><span data-stu-id="f237d-106">Sort the Results</span></span>](#SortResults)  
  
4.  [<span data-ttu-id="f237d-107">Regrouper les résultats</span><span class="sxs-lookup"><span data-stu-id="f237d-107">Group the Results</span></span>](#GroupResults)  
  
5.  [<span data-ttu-id="f237d-108">Agréger les résultats</span><span class="sxs-lookup"><span data-stu-id="f237d-108">Aggregate the Results</span></span>](#AggregateResults)  
  
6.  [<span data-ttu-id="f237d-109">Filtrer les résultats</span><span class="sxs-lookup"><span data-stu-id="f237d-109">Filter the Results</span></span>](#Filter)  
  
7.  [<span data-ttu-id="f237d-110">Rechercher du texte dans des colonnes</span><span class="sxs-lookup"><span data-stu-id="f237d-110">Search for Text in Columns</span></span>](#Search)  
  
8.  [<span data-ttu-id="f237d-111">Modifier les paramètres d'affichage</span><span class="sxs-lookup"><span data-stu-id="f237d-111">Change the Display Settings</span></span>](#ChangeDisplay)  
  
##  <a name="add-or-remove-columns"></a><a name="AddRemoveColumns"></a><span data-ttu-id="f237d-112">Ajouter ou supprimer des colonnes</span><span class="sxs-lookup"><span data-stu-id="f237d-112">Add or Remove Columns</span></span>  
  
1.  <span data-ttu-id="f237d-113">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-113">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-114"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, puis sélectionner **Surveiller les données actives**.</span><span class="sxs-lookup"><span data-stu-id="f237d-114">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="f237d-115">Dans la fenêtre des résultats de trace, cliquez avec le bouton droit sur l'en-tête de colonne, puis sélectionnez **Choisir les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="f237d-115">In the trace results window, right-click the column header, and then select **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="f237d-116">Dans la boîte de dialogue **Choisir les colonnes** , dans la section **Colonnes disponibles** , sélectionnez les noms de colonnes à ajouter, puis cliquez sur la flèche droite.</span><span class="sxs-lookup"><span data-stu-id="f237d-116">In the **Choose Columns** dialog box, in the **Available columns** section, select the column names you want to add, and then click the right arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-117">Par défaut, les colonnes sont organisées par nom.</span><span class="sxs-lookup"><span data-stu-id="f237d-117">By default, the columns are arranged by name.</span></span> <span data-ttu-id="f237d-118">Pour afficher les colonnes par événement, cliquez sur **Organiser par événement**.</span><span class="sxs-lookup"><span data-stu-id="f237d-118">To display the columns by event, click **Arrange by event**.</span></span>  
  
     <span data-ttu-id="f237d-119">Pour supprimer des colonnes, dans la section **Colonnes sélectionnées** , sélectionnez les colonnes à supprimer, puis cliquez sur la flèche gauche.</span><span class="sxs-lookup"><span data-stu-id="f237d-119">To remove columns, in the **Selected columns** section, select the columns you want to remove, and click the left arrow.</span></span>  
  
4.  <span data-ttu-id="f237d-120">Dans la section **Colonnes sélectionnées** , pour modifier l'affichage de l'ordre des colonnes, cliquez respectivement sur **Monter** ou sur **Descendre** .</span><span class="sxs-lookup"><span data-stu-id="f237d-120">In the **Selected columns** section, to change the column order display, click **Move Up** or **Move Down** respectively.</span></span> <span data-ttu-id="f237d-121">Vous ne pouvez pas déplacer plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="f237d-121">You cannot move multiple rows.</span></span>  
  
5.  <span data-ttu-id="f237d-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f237d-122">Click **OK**.</span></span>  
  
##  <a name="create-edit-or-delete-merged-columns"></a><a name="ChangeColumns"></a><span data-ttu-id="f237d-123">Créer, modifier ou supprimer des colonnes fusionnées</span><span class="sxs-lookup"><span data-stu-id="f237d-123">Create, Edit, or Delete Merged Columns</span></span>  
  
#### <a name="to-create-merged-columns"></a><span data-ttu-id="f237d-124">Pour créer des colonnes fusionnées</span><span class="sxs-lookup"><span data-stu-id="f237d-124">To create merged columns</span></span>  
  
1.  <span data-ttu-id="f237d-125">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-125">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-126"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, puis sélectionner **Surveiller les données actives**.</span><span class="sxs-lookup"><span data-stu-id="f237d-126">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="f237d-127">Dans la fenêtre des résultats de trace, cliquez avec le bouton droit sur l'en-tête de colonne, puis sélectionnez **Choisir les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="f237d-127">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="f237d-128">Dans la boîte de dialogue **Choisir les colonnes** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f237d-128">In the **Choose Columns** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="f237d-129">Dans la boîte de dialogue **Nouvelle colonne fusionnée** , dans la zone **Nom de la colonne fusionnée** , entrez un nom pour les colonnes fusionnées.</span><span class="sxs-lookup"><span data-stu-id="f237d-129">In the **New Merged Column** dialog box, in the **Merged column name** box, enter a name for the merged columns.</span></span>  
  
5.  <span data-ttu-id="f237d-130">Dans la zone **Colonnes d'origine à fusionner** , sélectionnez deux colonnes ou plus à fusionner dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f237d-130">In the **Original columns to merge** box, select two or more columns to merge from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-131">Les événements étendus prennent en charge la fusion de cinq colonnes au maximum.</span><span class="sxs-lookup"><span data-stu-id="f237d-131">Extended Events only supports merging up to five columns.</span></span>  
  
6.  <span data-ttu-id="f237d-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f237d-132">Click **OK**.</span></span>  
  
#### <a name="to-edit-merged-columns"></a><span data-ttu-id="f237d-133">Pour modifier des colonnes fusionnées</span><span class="sxs-lookup"><span data-stu-id="f237d-133">To edit merged columns</span></span>  
  
1.  <span data-ttu-id="f237d-134">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-134">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-135"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, puis sélectionner **Surveiller les données actives**.</span><span class="sxs-lookup"><span data-stu-id="f237d-135">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="f237d-136">Dans la fenêtre des résultats de trace, cliquez avec le bouton droit sur l'en-tête de colonne, puis sélectionnez **Choisir les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="f237d-136">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="f237d-137">Dans la boîte de dialogue **Choisir les colonnes** , cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f237d-137">In the **Choose Columns** dialog box, click **Edit**.</span></span>  
  
4.  <span data-ttu-id="f237d-138">Pour modifier le nom de la colonne fusionnée, dans la boîte de dialogue **Nouvelle colonne fusionnée** , dans la zone **Nom de la colonne fusionnée** , entrez un nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="f237d-138">To change the name of the merged column, in the **New Merged Column** dialog box, in the **Merged column name** box, enter the new name.</span></span>  
  
     <span data-ttu-id="f237d-139">Pour changer les colonnes que vous voulez fusionner, dans la zone **Colonnes d'origine à fusionner** , sélectionnez les colonnes que vous voulez fusionner dans la liste déroulante, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f237d-139">To change the columns you want to merge, in the **Original columns to merge** box, select the columns you want to merge from the drop-down list, and then click **OK**.</span></span>  
  
#### <a name="to-delete-merged-columns"></a><span data-ttu-id="f237d-140">Pour supprimer des colonnes fusionnées</span><span class="sxs-lookup"><span data-stu-id="f237d-140">To delete merged columns</span></span>  
  
1.  <span data-ttu-id="f237d-141">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-141">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-142"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, puis sélectionner **Surveiller les données actives**.</span><span class="sxs-lookup"><span data-stu-id="f237d-142">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="f237d-143">Dans la fenêtre des résultats de trace, cliquez avec le bouton droit sur l'en-tête de colonne, puis sélectionnez **Choisir les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="f237d-143">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="f237d-144">Dans la boîte de dialogue **Choisir les colonnes** , sélectionnez le nom de la colonne fusionnée à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="f237d-144">In the **Choose Columns** dialog box, select the name of the merged column you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="sort-the-results"></a><a name="SortResults"></a><span data-ttu-id="f237d-145">Trier les résultats</span><span class="sxs-lookup"><span data-stu-id="f237d-145">Sort the Results</span></span>  
  
#### <a name="to-sort-the-results-in-ascending-or-descending-order"></a><span data-ttu-id="f237d-146">Pour trier les résultats dans l'ordre croissant ou décroissant</span><span class="sxs-lookup"><span data-stu-id="f237d-146">To sort the results in ascending or descending order</span></span>  
  
-   <span data-ttu-id="f237d-147">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-147">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-148"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, sélectionner **Surveiller les données actives**, puis cliquer sur le bouton **Arrêter le flux de données** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="f237d-148">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
-   <span data-ttu-id="f237d-149">Dans la fenêtre des résultats de trace, cliquez avec le bouton droit sur l'en-tête de colonne que vous souhaitez trier.</span><span class="sxs-lookup"><span data-stu-id="f237d-149">In the trace results window, right-click the column heading you want to sort.</span></span> <span data-ttu-id="f237d-150">Cliquez sur **Tri croissant** ou **Tri décroissant** pour trier la colonne dans l'ordre croissant décroissant respectivement.</span><span class="sxs-lookup"><span data-stu-id="f237d-150">Click **Sort Ascending** or **Sort Descending** to sort the column in ascending or descending order respectively.</span></span>  
  
     <span data-ttu-id="f237d-151">Si vous avez regroupé des colonnes, le tri de la colonne ne concerne que les données du groupe.</span><span class="sxs-lookup"><span data-stu-id="f237d-151">If you have grouped columns, sorting the column will only sort data within the group.</span></span>  
  
##  <a name="group-results"></a><a name="GroupResults"></a><span data-ttu-id="f237d-152">Résultats du groupe</span><span class="sxs-lookup"><span data-stu-id="f237d-152">Group Results</span></span>  
  
#### <a name="to-group-the-results-by-a-single-column"></a><span data-ttu-id="f237d-153">Pour regrouper les résultats par une seule colonne</span><span class="sxs-lookup"><span data-stu-id="f237d-153">To group the results by a single column</span></span>  
  
1.  <span data-ttu-id="f237d-154">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-154">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-155"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, sélectionner **Surveiller les données actives**, puis cliquer sur le bouton **Arrêter le flux de données** dans la barre d'outils des événements étendus.</span><span class="sxs-lookup"><span data-stu-id="f237d-155">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the Extended Events toolbar.</span></span>  
  
2.  <span data-ttu-id="f237d-156">Dans la fenêtre des résultats de trace, cliquez avec le bouton droit sur l'en-tête de colonne à regrouper, puis sélectionnez **Regrouper par cette colonne**.</span><span class="sxs-lookup"><span data-stu-id="f237d-156">In the trace results window, right-click the column header you want to group, and then click **Group By This Column**.</span></span>  
  
#### <a name="to-group-the-results-by-multiple-columns"></a><span data-ttu-id="f237d-157">Pour regrouper les résultats par plusieurs colonnes</span><span class="sxs-lookup"><span data-stu-id="f237d-157">To group the results by multiple columns</span></span>  
  
1.  <span data-ttu-id="f237d-158">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-158">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-159"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, sélectionner **Surveiller les données actives**, puis cliquer sur le bouton **Arrêter le flux de données** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="f237d-159">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
2.  <span data-ttu-id="f237d-160">Cliquez sur le bouton **Regroupement** dans la barre d'outils des événements étendus.</span><span class="sxs-lookup"><span data-stu-id="f237d-160">Click the **Grouping** button on the Extended Events toolbar.</span></span>  
  
3.  <span data-ttu-id="f237d-161">Dans la boîte de dialogue **Regroupement** , dans la zone **Colonnes disponibles** , sélectionnez les colonnes à regrouper, puis cliquez sur la flèche droite.</span><span class="sxs-lookup"><span data-stu-id="f237d-161">In the **Grouping** dialog box, in the **Available columns** box, select the columns you want to group, and then click the right arrow.</span></span>  
  
     <span data-ttu-id="f237d-162">Pour modifier l'ordre de regroupement, dans la section **Colonnes groupées** , cliquez sur les flèches haut ou bas.</span><span class="sxs-lookup"><span data-stu-id="f237d-162">To change the grouping order, in the **Columns grouped on** section, click the up or down arrows.</span></span>  
  
     <span data-ttu-id="f237d-163">Pour supprimer des colonnes du regroupement, dans la zone **Colonnes groupées** , sélectionnez les colonnes à supprimer, puis cliquez sur la flèche gauche.</span><span class="sxs-lookup"><span data-stu-id="f237d-163">To remove columns from the grouping, in the **Columns grouped on** box, select the columns you want to remove and then click the left arrow.</span></span>  
  
4.  <span data-ttu-id="f237d-164">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f237d-164">Click **OK**.</span></span>  
  
##  <a name="aggregate-results"></a><a name="AggregateResults"></a><span data-ttu-id="f237d-165">Résultats de l’agrégat</span><span class="sxs-lookup"><span data-stu-id="f237d-165">Aggregate Results</span></span>  
 <span data-ttu-id="f237d-166">Les événements étendus prennent en charge cinq fonctions d'agrégation :</span><span class="sxs-lookup"><span data-stu-id="f237d-166">Extended Events supports five aggregation functions:</span></span>  
  
-   <span data-ttu-id="f237d-167">SUM</span><span class="sxs-lookup"><span data-stu-id="f237d-167">Sum</span></span>  
  
-   <span data-ttu-id="f237d-168">Min</span><span class="sxs-lookup"><span data-stu-id="f237d-168">Min</span></span>  
  
-   <span data-ttu-id="f237d-169">Max</span><span class="sxs-lookup"><span data-stu-id="f237d-169">Max</span></span>  
  
-   <span data-ttu-id="f237d-170">Average</span><span class="sxs-lookup"><span data-stu-id="f237d-170">Average</span></span>  
  
-   <span data-ttu-id="f237d-171">Count</span><span class="sxs-lookup"><span data-stu-id="f237d-171">Count</span></span>  
  
 <span data-ttu-id="f237d-172">Somme, Min, Max et Moyenne peuvent être utilisés avec les colonnes numériques disponibles.</span><span class="sxs-lookup"><span data-stu-id="f237d-172">Sum, Min,  Max, and Average can only be used with available numeric columns.</span></span> <span data-ttu-id="f237d-173">La fonction « count » correspond au nombre de valeurs non Null qui existent pour la colonne sélectionnée dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="f237d-173">Count is the number of non-null values that exist for the selected column in the group.</span></span>  
  
#### <a name="to-aggregate-results"></a><span data-ttu-id="f237d-174">Pour agréger les résultats</span><span class="sxs-lookup"><span data-stu-id="f237d-174">To aggregate results</span></span>  
  
1.  <span data-ttu-id="f237d-175">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-175">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-176"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, sélectionner **Surveiller les données actives**, puis cliquer sur le bouton **Arrêter le flux de données** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="f237d-176">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-177">L'agrégation est effectuée sur un groupe ; vous devez donc regrouper les résultats avant de pouvoir exécuter l'agrégation.</span><span class="sxs-lookup"><span data-stu-id="f237d-177">Aggregation is run against a group, so you must group the results before you can perform the aggregation.</span></span>  
  
2.  <span data-ttu-id="f237d-178">Dans la barre d'outils des événements étendus, cliquez sur le bouton **Agréger** .</span><span class="sxs-lookup"><span data-stu-id="f237d-178">On the Extended Events toolbar, click the **Aggregate** button.</span></span>  
  
     <span data-ttu-id="f237d-179">La boîte de dialogue **Agrégation** apparaît avec les colonnes disponibles pour l'agrégation.</span><span class="sxs-lookup"><span data-stu-id="f237d-179">The **Aggregation** dialog box appears displaying the columns available for aggregation.</span></span>  
  
3.  <span data-ttu-id="f237d-180">Sous **Type d'agrégation**, sélectionnez la manière d'agréger la colonne correspondante dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f237d-180">Under **Aggregation Type**, select how you want to aggregate the corresponding column from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="f237d-181">Dans la zone **Trier l'agrégation par** , sélectionnez la colonne d'après laquelle vous souhaitez trier les données dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f237d-181">In the **Sort aggregation by** box, select the column you want to sort by from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="f237d-182">Sélectionnez l'option **Dans l'ordre croissant** afin de trier le résultat de l'agrégation dans l'ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="f237d-182">Select the **In ascending order** option to sort the aggregation result in ascending order.</span></span>  
  
6.  <span data-ttu-id="f237d-183">Sélectionnez l'option **Dans l'ordre décroissant** afin de trier le résultat de l'agrégation dans l'ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="f237d-183">Select the **In descending order** option to sort the aggregation result in descending order.</span></span>  
  
7.  <span data-ttu-id="f237d-184">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f237d-184">Click **OK**.</span></span>  
  
##  <a name="filter-results"></a><a name="Filter"></a><span data-ttu-id="f237d-185">Filtrer les résultats</span><span class="sxs-lookup"><span data-stu-id="f237d-185">Filter Results</span></span>  
 <span data-ttu-id="f237d-186">Vous pouvez appliquer des filtres pour limiter les résultats de trace affichés dans la fenêtre de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-186">You can apply filters to narrow down the trace results that are displayed in the trace window.</span></span> <span data-ttu-id="f237d-187">Le filtre d'affichage comprend un filtre de temps et un filtre avancé.</span><span class="sxs-lookup"><span data-stu-id="f237d-187">The display filter includes a time filter and an advanced filter.</span></span> <span data-ttu-id="f237d-188">Vous utilisez le filtre de temps pour filtrer les résultats de trace par horodatage d'un événement, et le filtre avancé pour élaborer des conditions de filtre à l'aide des actions et des champs d'événement.</span><span class="sxs-lookup"><span data-stu-id="f237d-188">You use the time filter to filter the trace results by event timestamp, and you use the advanced filter to construct filter conditions using the event fields and actions.</span></span> <span data-ttu-id="f237d-189">Il existe une relation AND logique entre les filtres de temps et les filtres avancés.</span><span class="sxs-lookup"><span data-stu-id="f237d-189">There is an logical AND relationship between the Time and Advanced Filters.</span></span>  
  
#### <a name="to-create-a-filter"></a><span data-ttu-id="f237d-190">Pour créer un filtre</span><span class="sxs-lookup"><span data-stu-id="f237d-190">To create a filter</span></span>  
  
1.  <span data-ttu-id="f237d-191">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-191">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-192"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, puis sélectionner **Surveiller les données actives**.</span><span class="sxs-lookup"><span data-stu-id="f237d-192">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="f237d-193">Dans la fenêtre des résultats de trace, sélectionnez les résultats que vous souhaitez filtrer, puis dans la barre d'outils d'événements étendus, cliquez sur le bouton **Filtres** .</span><span class="sxs-lookup"><span data-stu-id="f237d-193">In the trace results window, select the results you want to filter, and then on the Extended Events toolbar, click the **Filters** button.</span></span>  
  
3.  <span data-ttu-id="f237d-194">Dans la boîte de dialogue **Filtres** , sélectionnez **Définir le filtre de temps** afin de définir le filtre de temps en faisant glisser les barres de curseur pour définir la chronologie.</span><span class="sxs-lookup"><span data-stu-id="f237d-194">In the **Filters** dialog box, select **Set time filter** to set the time filter by dragging the slider bars to set the timeline.</span></span> <span data-ttu-id="f237d-195">Notez que lorsque vous déplacez les barres de curseur, la zone de temps affiche la valeur d'heure en conséquence.</span><span class="sxs-lookup"><span data-stu-id="f237d-195">Note that when you move the slider bars, the time box displays the time value accordingly.</span></span> <span data-ttu-id="f237d-196">Vous pouvez également entrer l'heure dans les zones de temps, ou la sélectionner dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f237d-196">You can also enter the time in the time boxes, or you select it from the drop-down list.</span></span> <span data-ttu-id="f237d-197">Notez que lorsque vous entrez l'heure, le curseur gauche de temps se déplace en conséquence.</span><span class="sxs-lookup"><span data-stu-id="f237d-197">Note that when you enter the time, the left time slider will move accordingly.</span></span>  
  
4.  <span data-ttu-id="f237d-198">Dans la section **filtres supplémentaires** , appliquez vos critères de filtre, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="f237d-198">In the **Additional Filters** section, apply your filter criteria, and then click **Apply**.</span></span> <span data-ttu-id="f237d-199">Lorsque votre filtre a été créé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f237d-199">When your finished created the filter, click **OK**.</span></span>  
  
 <span data-ttu-id="f237d-200">Un cas spécial est celui où un champ d'événement porte le même nom qu'une action.</span><span class="sxs-lookup"><span data-stu-id="f237d-200">A special situation is when an event field has the same name as an action.</span></span> <span data-ttu-id="f237d-201">Par exemple, le nom « session_id ».</span><span class="sxs-lookup"><span data-stu-id="f237d-201">An example of this would be session_id.</span></span> <span data-ttu-id="f237d-202">Il existe plusieurs événements qui incluent un champ session_id et vous pouvez également ajouter l'action session_id.</span><span class="sxs-lookup"><span data-stu-id="f237d-202">There are several events that include a session_id field and you could also add the session_id action.</span></span> <span data-ttu-id="f237d-203">Les deux informations sont collectées, mais la grille d'affichage du Générateur de profils d'événements étendus utilise la logique suivante.</span><span class="sxs-lookup"><span data-stu-id="f237d-203">Both pieces of information are collected, but the Extended Events profiler display grid uses the following logic.</span></span>  
  
-   <span data-ttu-id="f237d-204">Une seule copie de la colonne (session_id dans ce cas) est affichée dans la grille.</span><span class="sxs-lookup"><span data-stu-id="f237d-204">Only one copy of the column (session_id in this case) is shown in the grid display.</span></span>  
  
-   <span data-ttu-id="f237d-205">Si les champs et l'action existent dans les données, la valeur du champ est affichée.</span><span class="sxs-lookup"><span data-stu-id="f237d-205">If both fields and action exist in the data, the field value is shown.</span></span>  
  
-   <span data-ttu-id="f237d-206">Si seul le champ ou l'action existe dans les données, le champ ou l'action est affiché.</span><span class="sxs-lookup"><span data-stu-id="f237d-206">If only field or action is exists in the data, the field or action is displayed.</span></span>  
  
-   <span data-ttu-id="f237d-207">Si ni l'action ni le champ existent, NULL est affiché.</span><span class="sxs-lookup"><span data-stu-id="f237d-207">If neither action nor field exists, display NULL.</span></span>  
  
##  <a name="search-for-text-in-columns"></a><a name="Search"></a><span data-ttu-id="f237d-208">Rechercher du texte dans des colonnes</span><span class="sxs-lookup"><span data-stu-id="f237d-208">Search for Text in Columns</span></span>  
  
1.  <span data-ttu-id="f237d-209">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-209">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-210"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, puis sélectionner **Surveiller les données actives**.</span><span class="sxs-lookup"><span data-stu-id="f237d-210">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="f237d-211">Dans la barre d'outils événements étendus, cliquez sur le bouton **Rechercher** .</span><span class="sxs-lookup"><span data-stu-id="f237d-211">On the Extended Events toolbar, click the **Find** button.</span></span>  
  
3.  <span data-ttu-id="f237d-212">Dans la boîte de dialogue **Rechercher dans les événements étendus** , dans la zone **Rechercher** , entrez le texte que vous souhaitez rechercher.</span><span class="sxs-lookup"><span data-stu-id="f237d-212">In the **Find in Extended Events** dialog box, in the **Find what** box, enter the text you want to search for.</span></span>  
  
     <span data-ttu-id="f237d-213">Vous pouvez sélectionner l'une de vos 20 dernières chaînes de recherche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f237d-213">You can select one of your last 20 search strings from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="f237d-214">Dans la zone **Regarder dans** , sélectionnez l'emplacement dans lequel rechercher le texte spécifié dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f237d-214">In the **Look in** box, select the location in which to search for the specified text from the drop-down list.</span></span> <span data-ttu-id="f237d-215">Utilisez les options suivantes pour la recherche :</span><span class="sxs-lookup"><span data-stu-id="f237d-215">Use the following options for searching:</span></span>  
  
    -   <span data-ttu-id="f237d-216">**Colonnes de table**.</span><span class="sxs-lookup"><span data-stu-id="f237d-216">**Table Columns**.</span></span> <span data-ttu-id="f237d-217">Utilisez cette option pour rechercher toutes les colonnes visibles dans la fenêtre de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-217">Use this option to search all visible columns in the trace window.</span></span>  
  
    -   <span data-ttu-id="f237d-218">**Détails**.</span><span class="sxs-lookup"><span data-stu-id="f237d-218">**Details**.</span></span> <span data-ttu-id="f237d-219">Utilisez cette option pour rechercher toutes les colonnes (promues et non promues) dans la fenêtre de trace qui ont été sélectionnées avant d’ouvrir la boîte **de dialogue Rechercher dans les événements étendus** .</span><span class="sxs-lookup"><span data-stu-id="f237d-219">Use this option to search all columns (promoted and non-promoted) in the trace window that were selected before opening the **Find in Extended Events** dialog box.</span></span>  
  
    -   <span data-ttu-id="f237d-220">**\<Event column name>**.</span><span class="sxs-lookup"><span data-stu-id="f237d-220">**\<Event column name>**.</span></span> <span data-ttu-id="f237d-221">Utilisez cette option pour effectuer une recherche dans une colonne d'événement spécifique dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f237d-221">Use this option to search in a specific event column from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="f237d-222">Utilisez les options suivantes pour spécifier la façon dont vous souhaitez définir la recherche :</span><span class="sxs-lookup"><span data-stu-id="f237d-222">Use the following options to specify how you want to define the search:</span></span>  
  
    1.  <span data-ttu-id="f237d-223">**Respecter la casse**.</span><span class="sxs-lookup"><span data-stu-id="f237d-223">**Match case**.</span></span> <span data-ttu-id="f237d-224">Utilisez cette option pour afficher les résultats de la recherche pour le texte que vous avez entré dans la zone **Rechercher** qui correspond à la fois par le contenu et par la casse.</span><span class="sxs-lookup"><span data-stu-id="f237d-224">Use this option to display the search results for the text you entered in the **Find what** box that are matched both by content and by case.</span></span>  
  
    2.  <span data-ttu-id="f237d-225">**Mot entier**.</span><span class="sxs-lookup"><span data-stu-id="f237d-225">**Match whole word**.</span></span> <span data-ttu-id="f237d-226">Utilisez cette option pour n'afficher que les résultats de la recherche du texte que vous avez entré et qui correspondent à des mots entiers.</span><span class="sxs-lookup"><span data-stu-id="f237d-226">Use this option to display only the search results for the text you entered that match complete words.</span></span>  
  
    3.  <span data-ttu-id="f237d-227">**Recherche vers le haut**.</span><span class="sxs-lookup"><span data-stu-id="f237d-227">**Search up**.</span></span> <span data-ttu-id="f237d-228">Utilisez cette option pour effectuer la recherche depuis l'emplacement du curseur jusqu'au début des résultats.</span><span class="sxs-lookup"><span data-stu-id="f237d-228">Use this option to search from your cursor location to the beginning of the results.</span></span>  
  
    4.  <span data-ttu-id="f237d-229">**Utilisez**.</span><span class="sxs-lookup"><span data-stu-id="f237d-229">**Use**.</span></span> <span data-ttu-id="f237d-230">Utilisez cette option pour interpréter les caractères spéciaux et les expressions régulières que vous avez entrés dans la zone **Rechercher** .</span><span class="sxs-lookup"><span data-stu-id="f237d-230">Use this option to interpret the special characters and the regular expressions you entered in the **Find what** box.</span></span> <span data-ttu-id="f237d-231">Les caractères spéciaux incluent les caractères génériques (\*) et (?) pour représenter un ou plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="f237d-231">Special characters include the wildcard characters (\*) and (?) to represent one or more characters.</span></span> <span data-ttu-id="f237d-232">Les expressions régulières sont des notations spéciales utilisées pour définir des modèles de texte recherché.</span><span class="sxs-lookup"><span data-stu-id="f237d-232">Regular expressions are special notations used to define patterns of search text.</span></span>  
  
6.  <span data-ttu-id="f237d-233">Cliquez sur **Suivant** pour rechercher le texte suivant que vous avez entré dans la zone **Rechercher** .</span><span class="sxs-lookup"><span data-stu-id="f237d-233">Click **Find Next** to search for the next text that you entered in the **Find what** box.</span></span>  
  
##  <a name="change-the-display-settings"></a><a name="ChangeDisplay"></a><span data-ttu-id="f237d-234">Modifier les paramètres d’affichage</span><span class="sxs-lookup"><span data-stu-id="f237d-234">Change the Display Settings</span></span>  
 <span data-ttu-id="f237d-235">Vous pouvez enregistrer les informations sur la colonne (ordre des colonnes, colonne de fusion et largeur de colonne) et les informations de filtre d'un résultat de trace dans un fichier de paramètres d'affichage des événements étendus (fichier .viewsetting).</span><span class="sxs-lookup"><span data-stu-id="f237d-235">You can save column information (column order, merge column, and column width) and filter information of a trace result into an Extended Events display setting file (.viewsetting file).</span></span> <span data-ttu-id="f237d-236">Après avoir enregistré le fichier, vous pouvez l'appliquer à vos résultats de trace pour modifier la vue.</span><span class="sxs-lookup"><span data-stu-id="f237d-236">After saving the file, you can apply it to your trace results to change the view.</span></span>  
  
#### <a name="to-change-the-display-settings"></a><span data-ttu-id="f237d-237">Pour modifier les paramètres d'affichage</span><span class="sxs-lookup"><span data-stu-id="f237d-237">To change the display settings</span></span>  
  
1.  <span data-ttu-id="f237d-238">Ouvrez un fichier .XEL pour consulter les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="f237d-238">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f237d-239"> Vous pouvez également cliquer avec le bouton droit sur le nom de session, puis sélectionner **Surveiller les données actives**.</span><span class="sxs-lookup"><span data-stu-id="f237d-239">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="f237d-240">Dans la fenêtre de résultats de trace, dans la barre d'outils ou dans le menu Événements étendus, sélectionnez **Paramètres d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="f237d-240">In the trace results window, on the Extended Events toolbar or menu, select **Display Settings**.</span></span>  
  
3.  <span data-ttu-id="f237d-241">Dans la liste déroulante, sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f237d-241">From the drop-down list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="f237d-242">**Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="f237d-242">**Save as**.</span></span> <span data-ttu-id="f237d-243">Enregistrez les informations de colonne et de filtre d'un résultat de trace dans un fichier .viewsetting.</span><span class="sxs-lookup"><span data-stu-id="f237d-243">Save the columns and filter information of a trace result to a .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="f237d-244">**Ouvrez**.</span><span class="sxs-lookup"><span data-stu-id="f237d-244">**Open**.</span></span> <span data-ttu-id="f237d-245">Ouvrez un fichier .viewsetting existant.</span><span class="sxs-lookup"><span data-stu-id="f237d-245">Open an existing .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="f237d-246">**Ouvrez récent**.</span><span class="sxs-lookup"><span data-stu-id="f237d-246">**Open recent**.</span></span> <span data-ttu-id="f237d-247">Ouvrez un fichier .viewsetting enregistré récemment.</span><span class="sxs-lookup"><span data-stu-id="f237d-247">Open a recently saved .viewsetting file.</span></span>  
  
  
