---
title: Test d’un modèle filtré (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0d74f8c-600d-4df5-a742-695e6947a071
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a97b5ca3523d1fc73405baba52b179a9bef04767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600378"
---
# <a name="testing-a-filtered-model-basic-data-mining-tutorial"></a><span data-ttu-id="6ae5b-102">Test d'un modèle filtré (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="6ae5b-102">Testing a Filtered Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="6ae5b-103">Maintenant que vous avez déterminé que le `TM_Decision_Tree` modèle est le plus précis, vous allez personnaliser le modèle pour qu’il réponde mieux aux besoins de la [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] campagne de publipostage ciblée.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-103">Now that you have determined that the `TM_Decision_Tree` model is the most accurate, you will customize the model to better suit the needs of the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] targeted mailing campaign.</span></span> <span data-ttu-id="6ae5b-104">Plus précisément, le service marketing souhaite savoir s'il existe des différences entre les clients hommes et femmes.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-104">Specifically, the Marketing department would like to know if there are any differences between male and female customers.</span></span> <span data-ttu-id="6ae5b-105">Ces informations les aideront à décider quels magazines utiliser pour la publicité et quels produits présenter dans leurs publipostages.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-105">The information could help them decide which magazines to use for advertising and which products to feature in their mailings.</span></span>  
  
## <a name="using-filters"></a><span data-ttu-id="6ae5b-106">Utilisation de filtres</span><span class="sxs-lookup"><span data-stu-id="6ae5b-106">Using Filters</span></span>  
 <span data-ttu-id="6ae5b-107">Le filtrage vous permet de créer facilement des modèles basés sur des sous-ensembles de vos données.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-107">Filtering enables you to easily create models built on subsets of your data.</span></span> <span data-ttu-id="6ae5b-108">Le filtre est appliqué uniquement au modèle et ne modifie pas la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-108">The filter is applied only to the model and does not change the underlying data source.</span></span>  
  
 <span data-ttu-id="6ae5b-109">Dans cette leçon, vous allez créer un modèle qui est filtré sur le type, pour prédire les caractéristiques qui influencent le plus le comportement d'achat des hommes et des femmes.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-109">In this lesson, you will create a model that is filtered on gender, to predict the characteristics that most influence buying behavior in males and female.</span></span>  
  
 <span data-ttu-id="6ae5b-110">Tout d’abord, vous allez effectuer une copie du `TM_Decision_Tree` modèle.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-110">First you will make a copy of the `TM_Decision_Tree` model.</span></span>  
  
#### <a name="to-copy-the-decision-tree-model"></a><span data-ttu-id="6ae5b-111">Pour copier le modèle d'arbre de décision</span><span class="sxs-lookup"><span data-stu-id="6ae5b-111">To copy the Decision Tree Model</span></span>  
  
1.  <span data-ttu-id="6ae5b-112">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , dans Explorateur de solutions, sélectionnez **BasicDataMining**.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, select **BasicDataMining**.</span></span>  
  
2.  <span data-ttu-id="6ae5b-113">Cliquez sur l'onglet **Modèles d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-113">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="6ae5b-114">Cliquez avec le bouton droit sur le `TM_Decision_Tree` modèle, puis sélectionnez **nouveau modèle d’exploration de données.**</span><span class="sxs-lookup"><span data-stu-id="6ae5b-114">Right click the `TM_Decision_Tree` model, and select **New Mining Model.**</span></span>  
  
4.  <span data-ttu-id="6ae5b-115">Dans le champ **nom du modèle** , tapez `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-115">In the **Model name** field, type `TM_Decision_Tree_Male`.</span></span>  
  
5.  <span data-ttu-id="6ae5b-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-116">Click **OK**.</span></span>  
  
 <span data-ttu-id="6ae5b-117">Ensuite, créez un filtre pour sélectionner des clients pour le modèle en fonction de leur sexe.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-117">Next, create a filter to select customers for the model based on their gender.</span></span>  
  
#### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="6ae5b-118">Pour créer un filtre de cas sur un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="6ae5b-118">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="6ae5b-119">Cliquez avec le bouton droit sur le `TM_Decision_Tree_Male` modèle d’exploration de données pour ouvrir le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-119">Right-click the `TM_Decision_Tree_Male` mining model to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="6ae5b-120">- ou -</span><span class="sxs-lookup"><span data-stu-id="6ae5b-120">-- or --</span></span>  
  
     <span data-ttu-id="6ae5b-121">Sélectionnez le modèle.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-121">Select the model.</span></span> <span data-ttu-id="6ae5b-122">Dans le menu **Modèle d'exploration de données** , sélectionnez **Définir le filtre de modèle**.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-122">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="6ae5b-123">Dans la boîte de dialogue **Filtre de modèle** , cliquez sur la ligne supérieure dans la grille, dans la zone de texte **Colonne de la structure d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
     <span data-ttu-id="6ae5b-124">La liste déroulante affiche uniquement les noms des colonnes dans cette table.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-124">The drop-down list displays only the names of the columns in that table.</span></span>  
  
3.  <span data-ttu-id="6ae5b-125">Dans la zone de texte colonne de la structure d’exploration de données, sélectionnez **sexe**.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-125">In the Mining Structure Column text box, select **Gender**.</span></span>  
  
     <span data-ttu-id="6ae5b-126">L'icône située à gauche de la zone de texte change pour indiquer que l'élément sélectionné est une table ou une colonne.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-126">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
4.  <span data-ttu-id="6ae5b-127">Cliquez sur la zone de texte **opérateur** et sélectionnez l’opérateur égal à (=) dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-127">Click the **Operator** text box and select the equal (=) operator from the list.</span></span>  
  
5.  <span data-ttu-id="6ae5b-128">Cliquez sur la zone de texte **valeur** et tapez **M**.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-128">Click the **Value** text box, and type **M**.</span></span>  
  
6.  <span data-ttu-id="6ae5b-129">Cliquez sur la ligne suivante dans la grille.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-129">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="6ae5b-130">Cliquez sur **OK** pour fermer la boîte de dialogue **filtre de modèle** .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-130">Click **OK** to close the **Model Filter** dialog box.</span></span>  
  
     <span data-ttu-id="6ae5b-131">Le filtre s’affiche dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-131">The filter displays in the **Properties** window.</span></span> <span data-ttu-id="6ae5b-132">Vous pouvez également lancer la boîte de dialogue **filtre de modèle** à partir de la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-132">Alternately, you can launch the **Model Filter** dialog from the **Properties** window.</span></span>  
  
8.  <span data-ttu-id="6ae5b-133">Répétez les étapes ci-dessus, mais cette fois nommez le modèle `TM_Decision_Tree_Female` et tapez **F** dans la zone de texte **valeur** .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-133">Repeat the above steps, but this time name the model `TM_Decision_Tree_Female` and type **F** in the **Value** text box.</span></span>  
  
## <a name="process-the-filtered-models"></a><span data-ttu-id="6ae5b-134">Traiter les modèles filtrés</span><span class="sxs-lookup"><span data-stu-id="6ae5b-134">Process the Filtered Models</span></span>  
 <span data-ttu-id="6ae5b-135">Les modèles ne peuvent pas être utilisés tant qu'ils n'ont pas été déployés et traités.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-135">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="6ae5b-136">Pour plus d’informations sur le traitement des modèles, consultez [traitement des modèles dans la structure de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="6ae5b-136">For more information on processing models, see [Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span></span>  
  
#### <a name="to-process-the-filtered-model"></a><span data-ttu-id="6ae5b-137">Pour traiter le modèle filtré</span><span class="sxs-lookup"><span data-stu-id="6ae5b-137">To process the filtered model</span></span>  
  
1.  <span data-ttu-id="6ae5b-138">Cliquez avec le bouton droit sur le `TM_Decision_Tree_Male` modèle et sélectionnez **traiter l’exploration de données structure et tous les modèles**.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-138">Right-click the `TM_Decision_Tree_Male` model and select **Process Mining Structure and all Model**s</span></span>  
  
2.  <span data-ttu-id="6ae5b-139">Cliquez sur **exécuter** pour traiter les nouveaux modèles.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-139">Click **Run** to process the new models.</span></span>  
  
3.  <span data-ttu-id="6ae5b-140">Une fois le traitement terminé, cliquez sur **Fermer** dans les deux fenêtres de traitement.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-140">After processing is complete, click **Close** on both processing windows.</span></span>  
  
     <span data-ttu-id="6ae5b-141">Vous avez maintenant deux nouveaux modèles affichés sous l’onglet **modèles d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-141">You now have two new models displayed in the **Mining Models** tab.</span></span>  
  
## <a name="evaluate-the-results"></a><span data-ttu-id="6ae5b-142">Évaluer les résultats</span><span class="sxs-lookup"><span data-stu-id="6ae5b-142">Evaluate the Results</span></span>  
 <span data-ttu-id="6ae5b-143">Consultez les résultats et déterminez l'exactitude des modèles filtrés de la même manière que vous l'avez fait pour les trois modèles précédents.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-143">View the results and assess the accuracy of the filtered models in much the same way as you did for the previous three models.</span></span> <span data-ttu-id="6ae5b-144">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="6ae5b-144">For more information, see:</span></span>  
  
 [<span data-ttu-id="6ae5b-145">Exploration du modèle d’arbre de décision &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="6ae5b-145">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="6ae5b-146">Test de la précision à l’aide de graphiques de courbes d’élévation &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="6ae5b-146">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
#### <a name="to-explore-the-filtered-models"></a><span data-ttu-id="6ae5b-147">Pour explorer les modèles filtrés</span><span class="sxs-lookup"><span data-stu-id="6ae5b-147">To explore the filtered models</span></span>  
  
1.  <span data-ttu-id="6ae5b-148">Sélectionnez l’onglet **visionneuse de modèle d’exploration** de données dans le concepteur d’exploration de **données**.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-148">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="6ae5b-149">Dans la zone modèle d’exploration de données, sélectionnez `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-149">In the Mining Model box, select `TM_Decision_Tree_Male`.</span></span>  
  
3.  <span data-ttu-id="6ae5b-150">**Affichez le niveau** de diaporama sur `3` .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-150">Slide **Show Level** to `3`.</span></span>  
  
4.  <span data-ttu-id="6ae5b-151">Remplacez la valeur d' **arrière-plan** par `1` .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-151">Change the **Background** value to `1`.</span></span>  
  
5.  <span data-ttu-id="6ae5b-152">Placez le curseur sur le nœud intitulé **tout** pour voir le nombre d’acheteurs de vélos par rapport aux acheteurs non-Bikes.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-152">Place your cursor over the node labeled **All** to see the number of bike buyers versus non-bike buyers.</span></span>  
  
6.  <span data-ttu-id="6ae5b-153">Répétez les étapes 1-5 pour `TM_Decision_Tree_Female` .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-153">Repeat steps 1 - 5 for `TM_Decision_Tree_Female`.</span></span>  
  
7.  <span data-ttu-id="6ae5b-154">Explorez les résultats pour le `TM_Decision_Tree` et les modèles filtrés pour le sexe.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-154">Explore the results for the `TM_Decision_Tree` and the models filtered for gender.</span></span> <span data-ttu-id="6ae5b-155">Comparé à tous les acheteurs de vélo, les acheteurs de vélo homme et femme partagent certaines caractéristiques identiques avec les acheteurs de vélo non filtrés, mais tous les trois présentent aussi des différences significatives.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-155">Compared to all bike buyers, male and female bike buyers share some of the same characteristics as the unfiltered bike buyers but all three have interesting differences as well.</span></span> <span data-ttu-id="6ae5b-156">Il s’agit d’informations utiles qui [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] peuvent être utilisées pour développer leur campagne marketing.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-156">This is useful information that [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] can use to develop their marketing campaign.</span></span>  
  
#### <a name="to-test-the-lift-of-the-filtered-models"></a><span data-ttu-id="6ae5b-157">Pour tester la finesse des modèles filtrés</span><span class="sxs-lookup"><span data-stu-id="6ae5b-157">To test the lift of the filtered models</span></span>  
  
1.  <span data-ttu-id="6ae5b-158">Basculez vers l’onglet graphique d’analyse de précision de l' **exploration** de données dans le concepteur d’exploration de données dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] et sélectionnez l’onglet **sélection d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-158">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="6ae5b-159">Dans la zone de groupe **Sélectionner le jeu de données à utiliser pour le graphique de précision** , sélectionnez **utiliser les cas de test**de la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-159">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span>  
  
3.  <span data-ttu-id="6ae5b-160">Sous l’onglet **sélection d’entrée** du concepteur d’exploration de données, sous sélectionner les colonnes de modèle d’exploration de données **prévisible à afficher dans le graphique de courbes d’élévation**, activez la case à cocher **synchroniser les colonnes de prédiction et les valeurs**.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-160">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
4.  <span data-ttu-id="6ae5b-161">Dans la colonne nom de la **colonne prévisible** , vérifiez que **vélo Buyer** est sélectionné pour chaque modèle.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-161">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
5.  <span data-ttu-id="6ae5b-162">Dans la colonne **Afficher** , sélectionnez chacun des modèles.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-162">In the **Show** column, select each of the models.</span></span>  
  
6.  <span data-ttu-id="6ae5b-163">Dans la colonne **prédire la valeur** , sélectionnez `1` .</span><span class="sxs-lookup"><span data-stu-id="6ae5b-163">In the **Predict Value** column, select `1`.</span></span>  
  
7.  <span data-ttu-id="6ae5b-164">Sélectionnez l’onglet **graphique de courbes d’élévation** pour afficher le graphique de courbes d’élévation.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-164">Select the **Lift Chart** tab to display the lift chart.</span></span>  
  
     <span data-ttu-id="6ae5b-165">Vous remarquerez maintenant que les trois modèles d'arbre de décision fournissent une finesse importante par rapport au modèle d'estimation aléatoire, et devancent également les modèles de Clustering et Naive-Bayes.</span><span class="sxs-lookup"><span data-stu-id="6ae5b-165">You will now notice that all three Decision Tree models provide significant lift compared to the random guess model, and also outperform the Clustering and Naive-Bayes models.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6ae5b-166">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="6ae5b-166">Related Tasks</span></span>  
 <span data-ttu-id="6ae5b-167">Pour plus d’informations sur les filtres, consultez [filtres pour les modèles d’exploration de données &#40;Analysis Services-exploration de données&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="6ae5b-167">For more information on filters, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="6ae5b-168">Pour obtenir un exemple d’application de filtres à des tables imbriquées, consultez le didacticiel sur l' [exploration de données intermédiaire &#40;Analysis Services-exploration de données&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="6ae5b-168">For an example of how to apply filters to nested tables, see [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="6ae5b-169">Tâche précédente de la leçon</span><span class="sxs-lookup"><span data-stu-id="6ae5b-169">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="6ae5b-170">Test de la précision à l’aide de graphiques de courbes d’élévation &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="6ae5b-170">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="6ae5b-171">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="6ae5b-171">Next Lesson</span></span>  
 [<span data-ttu-id="6ae5b-172">Leçon 6 : création et utilisation de prédictions &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="6ae5b-172">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ae5b-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ae5b-173">See Also</span></span>  
 <span data-ttu-id="6ae5b-174">[Didacticiel sur l’exploration de données intermédiaire &#40;Analysis Services d’exploration de données&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6ae5b-174">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="6ae5b-175">[Tâches du modèle d’exploration de données et procédures](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="6ae5b-175">[Mining Model Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="6ae5b-176">[Supprimer un filtre d’un modèle d’exploration de données](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="6ae5b-176">[Delete a Filter from a Mining Model](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="6ae5b-177">Filtres pour les modèles d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="6ae5b-177">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
