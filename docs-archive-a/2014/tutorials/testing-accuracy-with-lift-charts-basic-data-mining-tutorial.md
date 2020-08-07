---
title: Test de précision avec les graphiques de courbes d’élévation (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 822d414b-4a39-473f-80c3-53476e30655a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a3dcdd1d1b78911f5ffd37a383532abdd4814c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703468"
---
# <a name="testing-accuracy-with-lift-charts-basic-data-mining-tutorial"></a><span data-ttu-id="1c386-102">Test de la précision à l'aide de graphiques de courbes d'élévation (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="1c386-102">Testing Accuracy with Lift Charts (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="1c386-103">Sous l’onglet graphique d’analyse de précision de l' **exploration** de données du concepteur d’exploration de données, vous pouvez calculer le degré de prédiction de chacun de vos modèles et comparer les résultats de chaque modèle directement aux résultats des autres modèles.</span><span class="sxs-lookup"><span data-stu-id="1c386-103">On the **Mining Accuracy Chart** tab of Data Mining Designer, you can calculate how well each of your models makes predictions, and compare the results of each model directly against the results of the other models.</span></span> <span data-ttu-id="1c386-104">Cette méthode de comparaison est désignée sous le terme de *graphique de courbes d’élévation*.</span><span class="sxs-lookup"><span data-stu-id="1c386-104">This method of comparison is referred to as a *lift chart*.</span></span> <span data-ttu-id="1c386-105">En général, la précision prédictive d'un modèle d'exploration de données se mesure par la finesse ou la précision de classification.</span><span class="sxs-lookup"><span data-stu-id="1c386-105">Typically, the predictive accuracy of a mining model is measured by either lift or classification accuracy.</span></span> <span data-ttu-id="1c386-106">Pour ce didacticiel, nous utiliserons le graphique de courbes d'élévation uniquement.</span><span class="sxs-lookup"><span data-stu-id="1c386-106">For this tutorial we will use the lift chart only.</span></span>  
  
 <span data-ttu-id="1c386-107">Au cours de cette rubrique, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1c386-107">In this topic, you will perform the following tasks:</span></span>  
  
-   [<span data-ttu-id="1c386-108">Choisir des données d'entrée</span><span class="sxs-lookup"><span data-stu-id="1c386-108">Choose the Input Data</span></span>](#BKMK_InputData)  
  
-   [<span data-ttu-id="1c386-109">Configurer les paramètres du graphique d'analyse de précision</span><span class="sxs-lookup"><span data-stu-id="1c386-109">Configure Accuracy Chart Parameters</span></span>](#BKMK_Selecting)  
  
##  <a name="choosing-the-input-data"></a><a name="BKMK_InputData"></a><span data-ttu-id="1c386-110">Choix des données d’entrée</span><span class="sxs-lookup"><span data-stu-id="1c386-110">Choosing the Input Data</span></span>  
 <span data-ttu-id="1c386-111">La première étape du test de précision de vos modèles d'exploration de données consiste à sélectionner la source de données que vous allez utiliser pour les tests.</span><span class="sxs-lookup"><span data-stu-id="1c386-111">The first step in testing the accuracy of your mining models is to select the data source that you will use for testing.</span></span> <span data-ttu-id="1c386-112">Vous allez tester le degré de précision des modèles avec vos données de test, puis vous les utiliserez avec des données externes.</span><span class="sxs-lookup"><span data-stu-id="1c386-112">You will test how well the models perform against your testing data and then you will use them with external data.</span></span>  
  
#### <a name="to-select-the-data-set"></a><span data-ttu-id="1c386-113">Pour sélectionner le jeu de données</span><span class="sxs-lookup"><span data-stu-id="1c386-113">To select the data set</span></span>  
  
1.  <span data-ttu-id="1c386-114">Basculez vers l’onglet graphique d’analyse de précision de l' **exploration** de données dans le concepteur d’exploration de données dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] et sélectionnez l’onglet **sélection d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="1c386-114">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="1c386-115">Dans la zone de groupe **Sélectionner le jeu de données à utiliser pour le graphique de précision** , sélectionnez **utiliser les cas de test**de la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="1c386-115">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span> <span data-ttu-id="1c386-116">Il s'agit du jeu de données que vous avez mis de côté lorsque vous avez créé la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="1c386-116">This is the testing data that you set aside when you created the mining structure.</span></span>  
  
     <span data-ttu-id="1c386-117">Pour plus d’informations sur les autres options, consultez [choisir un type de graphique d’exactitude et définir des options de graphique](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span><span class="sxs-lookup"><span data-stu-id="1c386-117">For more information on the other options, see [Choose an Accuracy Chart Type and Set Chart Options](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span></span>  
  
##  <a name="setting-accuracy-chart-parameters"></a><a name="BKMK_Selecting"></a><span data-ttu-id="1c386-118">Définition des paramètres du graphique de précision</span><span class="sxs-lookup"><span data-stu-id="1c386-118">Setting Accuracy Chart Parameters</span></span>  
 <span data-ttu-id="1c386-119">Pour créer un graphique d'analyse de précision, vous devez définir trois éléments :</span><span class="sxs-lookup"><span data-stu-id="1c386-119">To create an accuracy chart, you must define three things:</span></span>  
  
-   <span data-ttu-id="1c386-120">Les modèles à inclure dans le graphique d'analyse de précision</span><span class="sxs-lookup"><span data-stu-id="1c386-120">Which models should you include in the accuracy chart?</span></span>  
  
-   <span data-ttu-id="1c386-121">L'attribut prédictible à mesurer</span><span class="sxs-lookup"><span data-stu-id="1c386-121">Which predictable attribute do you want to measure?</span></span> <span data-ttu-id="1c386-122">Certains modèles peuvent avoir plusieurs cibles, mais chaque graphique ne mesure qu'un seul résultat à la fois.</span><span class="sxs-lookup"><span data-stu-id="1c386-122">Some models might have multiple targets, but each chart can measure only one outcome at a time.</span></span>  
  
     <span data-ttu-id="1c386-123">Pour utiliser une colonne comme **nom de colonne prévisible** dans un graphique de précision, les colonnes doivent avoir le type d' `Predict` utilisation `Predict Only` ou.</span><span class="sxs-lookup"><span data-stu-id="1c386-123">To use a column as the **Predictable Column Name** in an accuracy chart, the columns must have the usage type of `Predict` or `Predict Only`.</span></span> <span data-ttu-id="1c386-124">En outre, le type de contenu de la colonne cible doit être `Discrete` ou `Discretized`.</span><span class="sxs-lookup"><span data-stu-id="1c386-124">Also, the content type of the target column must be either `Discrete` or `Discretized`.</span></span> <span data-ttu-id="1c386-125">En d'autres termes, vous ne pouvez pas utiliser le graphique de courbes d'élévation pour mesurer la précision par rapport à des valeurs numériques continues.</span><span class="sxs-lookup"><span data-stu-id="1c386-125">In other words, you cannot measure accuracy against continuous numeric outputs using the lift chart.</span></span>  
  
-   <span data-ttu-id="1c386-126">Voulez-vous mesurer la précision générale du modèle ou sa précision dans la prédiction d’une valeur particulière (par exemple, [vélo Buyer] = 'Oui')</span><span class="sxs-lookup"><span data-stu-id="1c386-126">Do you want to measure the model's general accuracy, or its accuracy  in predicting a particular value (such as [Bike Buyer] = 'Yes')</span></span>  
  
#### <a name="to-generate-the-lift-chart"></a><span data-ttu-id="1c386-127">Pour générer le graphique de courbes d'élévation</span><span class="sxs-lookup"><span data-stu-id="1c386-127">To generate the lift chart</span></span>  
  
1.  <span data-ttu-id="1c386-128">Sous l’onglet **sélection d’entrée** du concepteur d’exploration de données, sous sélectionner les colonnes de modèle d’exploration de données **prévisible à afficher dans le graphique de courbes d’élévation**, activez la case à cocher **synchroniser les colonnes de prédiction et les valeurs**.</span><span class="sxs-lookup"><span data-stu-id="1c386-128">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
2.  <span data-ttu-id="1c386-129">Dans la colonne nom de la **colonne prévisible** , vérifiez que **vélo Buyer** est sélectionné pour chaque modèle.</span><span class="sxs-lookup"><span data-stu-id="1c386-129">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
3.  <span data-ttu-id="1c386-130">Dans la colonne **Afficher** , sélectionnez chacun des modèles.</span><span class="sxs-lookup"><span data-stu-id="1c386-130">In the **Show** column, select each of the models.</span></span>  
  
     <span data-ttu-id="1c386-131">Par défaut, tous les modèles de la structure d'exploration de données sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="1c386-131">By default, all the models in the mining structure are selected.</span></span> <span data-ttu-id="1c386-132">Vous pouvez choisir de ne pas inclure un modèle, mais pour ce didacticiel, conservez tous les modèles sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="1c386-132">You can decide not to include a model, but for this tutorial leave all the models selected.</span></span>  
  
4.  <span data-ttu-id="1c386-133">Dans la colonne **prédire la valeur** , sélectionnez **1**.</span><span class="sxs-lookup"><span data-stu-id="1c386-133">In the **Predict Value** column, select **1**.</span></span> <span data-ttu-id="1c386-134">La même valeur est automatiquement remplie dans chaque modèle comportant la même colonne prédictible.</span><span class="sxs-lookup"><span data-stu-id="1c386-134">The same value is automatically filled in for each model that has the same predictable column.</span></span>  
  
5.  <span data-ttu-id="1c386-135">Sélectionnez l’onglet **graphique de courbes d’élévation** .</span><span class="sxs-lookup"><span data-stu-id="1c386-135">Select the **Lift Chart** tab.</span></span>  
  
     <span data-ttu-id="1c386-136">Lorsque vous cliquez sur l'onglet, une requête de prédiction s'exécute pour obtenir des prédictions pour les données de test, et les résultats sont comparés aux valeurs connues.</span><span class="sxs-lookup"><span data-stu-id="1c386-136">When you click the tab, a prediction query is executed to get predictions for the test data, and the results are compared against the known values.</span></span> <span data-ttu-id="1c386-137">Les résultats sont reportés sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="1c386-137">The results are plotted on the graph.</span></span>  
  
     <span data-ttu-id="1c386-138">Si vous avez spécifié un résultat cible particulier à l’aide de l’option **prédire la valeur** , le graphique de courbes d’élévation trace les résultats des hypothèses aléatoires et les résultats d’un modèle idéal.</span><span class="sxs-lookup"><span data-stu-id="1c386-138">If you specified a particular target outcome using the **Predict Value** option, the lift chart plots the results of random guesses and the results of an ideal model.</span></span>  
  
    -   <span data-ttu-id="1c386-139">La ligne d'estimation aléatoire indique la précision du modèle sans utiliser de données pour éclairer ses prédictions : c'est-à-dire, un fractionnement 50-50 entre deux résultats.</span><span class="sxs-lookup"><span data-stu-id="1c386-139">The random guess line shows how accurate the model would be without using any data to inform its predictions: that is, a 50-50 split between two outcomes.</span></span> <span data-ttu-id="1c386-140">Le graphique de courbes d'élévation vous aide à visualiser le gain de performances de votre modèle par rapport à une estimation aléatoire.</span><span class="sxs-lookup"><span data-stu-id="1c386-140">The lift chart helps you visualize how much better your model performs in comparison to a random guess.</span></span>  
  
    -   <span data-ttu-id="1c386-141">La ligne de modèle idéal représente la limite supérieure de précision.</span><span class="sxs-lookup"><span data-stu-id="1c386-141">The ideal model line represents the upper bound of accuracy.</span></span> <span data-ttu-id="1c386-142">Elle indique les éventuels avantages que vous pouvez retirer si votre modèle a toujours effectué des prédictions précises.</span><span class="sxs-lookup"><span data-stu-id="1c386-142">It shows you the maximum possible benefit you could achieve if your model always predicted accurately.</span></span>  
  
     <span data-ttu-id="1c386-143">Les modèles d'exploration de données que vous avez créés se situent généralement entre ces deux extrêmes.</span><span class="sxs-lookup"><span data-stu-id="1c386-143">The mining models you created will usually fall between these two extremes.</span></span> <span data-ttu-id="1c386-144">Toute amélioration par rapport à l’estimation aléatoire est considérée comme une *élévation*.</span><span class="sxs-lookup"><span data-stu-id="1c386-144">Any improvement from the random guess is considered to be *lift*.</span></span>  
  
6.  <span data-ttu-id="1c386-145">Utilisez la légende pour repérer les lignes colorées qui représentent le modèle idéal et le modèle d'estimation aléatoire.</span><span class="sxs-lookup"><span data-stu-id="1c386-145">Use the legend to locate the colored lines representing the Ideal Model and the Random Guess Model.</span></span>  
  
     <span data-ttu-id="1c386-146">Vous remarquerez que le `TM_Decision_Tree` modèle fournit la plus grande élévation, ce qui a pour avantage les modèles de clustering et Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="1c386-146">You'll notice that the `TM_Decision_Tree` model provides the greatest lift,  outperforming both the Clustering and Naive Bayes models.</span></span>  
  
 <span data-ttu-id="1c386-147">Pour une explication détaillée d’un graphique de courbes d’élévation similaire à celui créé dans cette leçon, consultez [graphique de courbes d’élévation &#40;Analysis Services d’exploration de données&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1c386-147">For an in-depth explanation of a lift chart similar to the one created in this lesson, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="1c386-148">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="1c386-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="1c386-149">Test d’un modèle filtré &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="1c386-149">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="1c386-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c386-150">See Also</span></span>  
 <span data-ttu-id="1c386-151">[Graphique de courbes d’élévation &#40;Analysis Services d’exploration de données&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1c386-151">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="1c386-152">Onglet graphique de courbes d’élévation &#40;vue graphique d’analyse de précision de l’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="1c386-152">Lift Chart Tab &#40;Mining Accuracy Chart View&#41;</span></span>](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md)  
  
  
