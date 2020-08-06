---
title: Scénario de la valeur cible (outils d’analyse de table pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- scenario analysis
- goal seek scenario
ms.assetid: efe50306-cf7c-46b3-9cc4-e7f0b6968b0c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b3b4df4f78a2d3652b1dac3c566e66507b523ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603710"
---
# <a name="goal-seek-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="a5b19-102">Scénario Valeur cible (Outils d'analyse de table pour Excel)</span><span class="sxs-lookup"><span data-stu-id="a5b19-102">Goal Seek Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="a5b19-103">![Bouton Valeur cible dans les outils d'analyse de table](media/tat-goalseek.gif "Bouton Valeur cible dans les outils d'analyse de table")</span><span class="sxs-lookup"><span data-stu-id="a5b19-103">![Goal Seek button in Table Analysis tools](media/tat-goalseek.gif "Goal Seek button in Table Analysis tools")</span></span>  
  
 <span data-ttu-id="a5b19-104">L’outil de scénario de la valeur **cible** est complémentaire à l’outil de scénario de [What If](what-if-scenario-table-analysis-tools-for-excel.md) .</span><span class="sxs-lookup"><span data-stu-id="a5b19-104">The **Goal Seek** scenario tool is complementary to the [What If](what-if-scenario-table-analysis-tools-for-excel.md) scenario tool.</span></span> <span data-ttu-id="a5b19-105">L’outil de **simulation** vous indique l’impact d’une modification, tandis que l’outil **objectif cible** vous indique les facteurs sous-jacents qui doivent changer pour obtenir le résultat souhaité.</span><span class="sxs-lookup"><span data-stu-id="a5b19-105">The **What-If** tool tells you the impact of making a change, whereas the **Goal Seek** tool tells you the underlying factors that must change to achieve a desired result.</span></span>  
  
 <span data-ttu-id="a5b19-106">Supposons, par exemple, que votre objectif est d’augmenter la satisfaction des clients.</span><span class="sxs-lookup"><span data-stu-id="a5b19-106">For example, let's say your goal is to increase customer satisfaction.</span></span> <span data-ttu-id="a5b19-107">Vous pouvez utiliser l’analyse de la recherche de l' **objectif** pour déterminer les facteurs les plus susceptibles d’augmenter la satisfaction des clients et déterminer si ces modifications sont rentables.</span><span class="sxs-lookup"><span data-stu-id="a5b19-107">You can use **Goal Seek** analysis to determine which factors would be most likely to increase customer satisfaction, and decide whether those changes are cost-effective.</span></span>  
  
 <span data-ttu-id="a5b19-108">Lorsqu'il termine son analyse, l'outil crée deux nouvelles colonnes dans la table de données source.</span><span class="sxs-lookup"><span data-stu-id="a5b19-108">When the tool finishes its analysis, it creates two new columns in the source data table.</span></span> <span data-ttu-id="a5b19-109">Ces colonnes indiquent la *probabilité* que le résultat ciblé soit atteint et la modification recommandée, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="a5b19-109">These columns show the *likelihood* that the targeted outcome can be achieved, and the recommended change, if any.</span></span>  
  
 <span data-ttu-id="a5b19-110">L'outil peut analyser un jeu de données et élaborer des prédictions pour le jeu entier, ou vous pouvez créer l'analyse puis tester les scénarios un par un.</span><span class="sxs-lookup"><span data-stu-id="a5b19-110">The tool can analyze a set of data and make predictions for the entire set, or you can create the analysis and then test scenarios one at a time.</span></span>  
  
## <a name="using-the-goal-seek-scenario-tool"></a><span data-ttu-id="a5b19-111">Utilisation de l'outil de scénario Valeur cible</span><span class="sxs-lookup"><span data-stu-id="a5b19-111">Using the Goal Seek Scenario Tool</span></span>  
  
1.  <span data-ttu-id="a5b19-112">Ouvrez un tableau Excel.</span><span class="sxs-lookup"><span data-stu-id="a5b19-112">Open an Excel table.</span></span>  
  
2.  <span data-ttu-id="a5b19-113">Cliquez sur **scénarios**, puis sélectionnez valeur **cible**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-113">Click **Scenarios**, and select **Goal Seek**.</span></span>  
  
3.  <span data-ttu-id="a5b19-114">Dans la boîte de dialogue **analyse de scénario :** valeur cible, sélectionnez la colonne qui contient la valeur cible dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a5b19-114">In the **Scenario Analysis: Goal Seek** dialog box, select the column that contains the target value from the list.</span></span>  
  
4.  <span data-ttu-id="a5b19-115">Spécifiez la valeur à atteindre.</span><span class="sxs-lookup"><span data-stu-id="a5b19-115">Specify the value that you want to achieve.</span></span>  
  
     <span data-ttu-id="a5b19-116">Si la cible de la colonne contient des valeurs numériques continues, vous pouvez également spécifier une hausse ou une baisse souhaitée de la valeur.</span><span class="sxs-lookup"><span data-stu-id="a5b19-116">If the column goal contains continuous numeric values, you can also specify a desired increase or decrease in the value.</span></span> <span data-ttu-id="a5b19-117">Par exemple, vous pouvez choisir **Sales** comme colonne et spécifier que la cible est une augmentation de 120%.</span><span class="sxs-lookup"><span data-stu-id="a5b19-117">For example, you might choose **Sales** as the column and specify that the target is an increase of 120%.</span></span>  
  
     <span data-ttu-id="a5b19-118">Ou, vous pouvez spécifier la cible en tant que plage de valeurs, en tapant une limite inférieure et supérieure.</span><span class="sxs-lookup"><span data-stu-id="a5b19-118">Or, you can specify the goal as a range of values, by typing a lower and upper limit.</span></span>  
  
5.  <span data-ttu-id="a5b19-119">Spécifiez la colonne qui contient les valeurs que vous allez modifier.</span><span class="sxs-lookup"><span data-stu-id="a5b19-119">Specify the column that contains the values you will change.</span></span> <span data-ttu-id="a5b19-120">En d'autres termes, choisissez la colonne qui sera manipulée pour produire le résultat désiré.</span><span class="sxs-lookup"><span data-stu-id="a5b19-120">In other words, pick the column that will be manipulated to produce the desired result.</span></span>  
  
6.  <span data-ttu-id="a5b19-121">Si vous le souhaitez, cliquez sur **choisir les colonnes à utiliser pour l’analyse**, puis sélectionnez les colonnes qui contiennent des informations utiles.</span><span class="sxs-lookup"><span data-stu-id="a5b19-121">Optionally, click **Choose columns to be used for analysis**, and select columns that contain useful information.</span></span> <span data-ttu-id="a5b19-122">Désélectionnez les colonnes qui ne contribueront pas à l'analyse.</span><span class="sxs-lookup"><span data-stu-id="a5b19-122">Deselect columns that will not contribute to the analysis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5b19-123">Ne désélectionnez pas les colonnes que vous utiliserez pour la cible ou la modification.</span><span class="sxs-lookup"><span data-stu-id="a5b19-123">Do not deselect columns that you will use for either the goal or the change.</span></span> <span data-ttu-id="a5b19-124">Ces colonnes sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="a5b19-124">These columns are required.</span></span>  
  
7.  <span data-ttu-id="a5b19-125">Indiquez si les prédictions à effectuer doivent porter sur la table entière ou uniquement sur la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5b19-125">Specify whether you want to make predictions for the entire table, or for only the selected row.</span></span>  
  
8.  <span data-ttu-id="a5b19-126">Si vous avez sélectionné l’option **table entière** , l’outil ajoute les prédictions à la table source dans deux nouvelles colonnes.</span><span class="sxs-lookup"><span data-stu-id="a5b19-126">If you selected the **Entire table** option, the tool adds the predictions to the source table in two new columns.</span></span>  
  
9. <span data-ttu-id="a5b19-127">Si vous avez sélectionné l’option **sur cette ligne**, les résultats de l’analyse sont générés dans la boîte de dialogue à des fins de vérification.</span><span class="sxs-lookup"><span data-stu-id="a5b19-127">If you selected the option **On this row**, the results of analysis are output to the dialog box for review.</span></span> <span data-ttu-id="a5b19-128">La boîte de dialogue reste ouverte afin que vous puissiez continuer à essayer différentes valeurs et cibles.</span><span class="sxs-lookup"><span data-stu-id="a5b19-128">The dialog box stays open so that you can continue trying out different values and goals.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="a5b19-129">Spécifications</span><span class="sxs-lookup"><span data-stu-id="a5b19-129">Requirements</span></span>  
 <span data-ttu-id="a5b19-130">Cet outil utilise l'algorithme MLR (Microsoft Logistic Regression), qui peut traiter des valeurs numériques ou discrètes.</span><span class="sxs-lookup"><span data-stu-id="a5b19-130">This tool uses the Microsoft Logistic Regression algorithm, which can process either numeric or discrete values.</span></span>  
  
 <span data-ttu-id="a5b19-131">Vous pouvez exécuter la prédiction plusieurs fois et sélectionner par la suite d'autres colonnes, mais chaque combinaison de cible et de modification doit être calculée séparément.</span><span class="sxs-lookup"><span data-stu-id="a5b19-131">You can run the prediction multiple times, and select different columns later, but each combination of a goal and a change must be calculated separately.</span></span>  
  
 <span data-ttu-id="a5b19-132">Vous obtiendrez de meilleurs résultats en sélectionnant des colonnes contenant des informations utiles à l'analyse.</span><span class="sxs-lookup"><span data-stu-id="a5b19-132">You can achieve better results if you select columns for analysis that contain useful information.</span></span> <span data-ttu-id="a5b19-133">Cependant, si vous incluez un nombre de colonnes trop restreint, vous aurez peut-être des difficultés à obtenir un résultat.</span><span class="sxs-lookup"><span data-stu-id="a5b19-133">However, if you include too few columns, it might be difficult to obtain a result.</span></span>  
  
 <span data-ttu-id="a5b19-134">Lorsque vous créez des prédictions une à la fois, veillez à sélectionner une ligne qui ne contient pas déjà le résultat souhaité, sinon vous risquez d'obtenir une erreur.</span><span class="sxs-lookup"><span data-stu-id="a5b19-134">When you create predictions one at a time, be sure to select a row that does not already contain the desired result, or you may get an error.</span></span> <span data-ttu-id="a5b19-135">En d'autres termes, si l'objectif de la valeur cible est de déterminer les facteurs qui encouragent des achats de vélo, vous devez inclure uniquement les clients qui n'ont pas acheté de vélo.</span><span class="sxs-lookup"><span data-stu-id="a5b19-135">In other words, if the purpose of goal seeking is to determine factors that encourage bike purchases, you should only include customers who did not purchase a bike.</span></span>  
  
## <a name="understanding-the-results-of-goal-seek-analysis"></a><span data-ttu-id="a5b19-136">Interprétation des résultats d'une analyse de valeur cible</span><span class="sxs-lookup"><span data-stu-id="a5b19-136">Understanding the Results of Goal Seek Analysis</span></span>  
 <span data-ttu-id="a5b19-137">Lorsque vous créez un scénario de valeur cible, l'outil effectue trois opérations :</span><span class="sxs-lookup"><span data-stu-id="a5b19-137">When you create a goal seeking scenario, the tool does three things:</span></span>  
  
-   <span data-ttu-id="a5b19-138">il crée une structure d'exploration de données qui stocke des faits clés à propos des données de votre table ;</span><span class="sxs-lookup"><span data-stu-id="a5b19-138">Creates a data mining structure that stores key facts about the data in your table.</span></span>  
  
-   <span data-ttu-id="a5b19-139">il crée un modèle d'exploration de données de régression logistique basé sur vos données ;</span><span class="sxs-lookup"><span data-stu-id="a5b19-139">Creates a logistic regression mining model based on the data.</span></span>  
  
-   <span data-ttu-id="a5b19-140">il crée une prédiction pour chaque valeur que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="a5b19-140">Creates a prediction for each value that you specify.</span></span>  
  
 <span data-ttu-id="a5b19-141">Si vous testez des scénarios de valeur cible un par un, vous pouvez consulter les résultats interactivement.</span><span class="sxs-lookup"><span data-stu-id="a5b19-141">If you test goal-seeking scenarios one at a time, you can view the results interactively.</span></span> <span data-ttu-id="a5b19-142">Cela revient à créer une requête de *prédiction Singleton*.</span><span class="sxs-lookup"><span data-stu-id="a5b19-142">This is the same as creating a *singleton prediction query*.</span></span>  
  
 <span data-ttu-id="a5b19-143">L’outil génère un rapport dans le volet des **résultats** de la boîte de dialogue s’il a réussi à trouver un scénario qui atteint l’objectif souhaité.</span><span class="sxs-lookup"><span data-stu-id="a5b19-143">The tool reports in the **Results** pane of the dialog box whether it was successful in finding a scenario that achieves the desired goal.</span></span> <span data-ttu-id="a5b19-144">S'il trouve une solution adéquate, il émet une recommandation qui indique le changement requis.</span><span class="sxs-lookup"><span data-stu-id="a5b19-144">If a successful solution was found, the tool also generates a recommendation that tells you the required change.</span></span> <span data-ttu-id="a5b19-145">Par exemple, l’outil valeur **cible** peut vous indiquer que la distance de trajet doit être inférieure à 5 kilomètres.</span><span class="sxs-lookup"><span data-stu-id="a5b19-145">For example, the **Goal Seek** tool might tell you that the commuting distance should be less than 5 miles.</span></span>  
  
 <span data-ttu-id="a5b19-146">Résultats de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="a5b19-146">Example results:</span></span>  
  
 <span data-ttu-id="a5b19-147">**La valeur cible pour Désir d'achat a trouvé une solution.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-147">**Goal Seeking for Interest in Buying has found a solution.**</span></span>  
  
 <span data-ttu-id="a5b19-148">**La correspondance la plus proche obtenue en remplaçant 'distance domicile-travail' par '3-8 km'.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-148">**Closest match obtained by changing 'Commute distance' to '2-5 miles'.**</span></span>  
  
 <span data-ttu-id="a5b19-149">Ce résultat repose sur une ligne existante de la table de données. Autrement dit, si les données concernant un client lambda n'ont pas changé mais que sa distance domicile-travail a été ramenée à 3-8 km, le client sera, dans une certaine mesure, plus enclin à acheter une bicyclette.</span><span class="sxs-lookup"><span data-stu-id="a5b19-149">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's commute was reduced to 2-5 miles, the customer would be somewhat more likely buy a bicycle.</span></span>  
  
 <span data-ttu-id="a5b19-150">Si vous créez des prédictions de recherche d’objectif pour toutes les lignes de la table Excel en spécifiant la **table entière**, theTool crée deux nouvelles colonnes dans la table de données d’origine.</span><span class="sxs-lookup"><span data-stu-id="a5b19-150">If you create goal-seeking predictions for all the rows in the Excel table by specifying **Entire table**, thetool creates two new columns in the original data table.</span></span> <span data-ttu-id="a5b19-151">Dans la première colonne ajoutée à la table figure soit un cercle vert avec une coche pour indiquer que la cible a peut être atteinte, soit un cercle rouge avec un X pour indiquer qu'aucune modification permettant d'atteindre la cible ne peut être effectuée.</span><span class="sxs-lookup"><span data-stu-id="a5b19-151">The first column that is added to the table contains either a check mark in a green circle, to indicate that the goal can be met, or an X mark in a red circle, to indicate that no changes can be made that will enable the goal.</span></span>  
  
 <span data-ttu-id="a5b19-152">La deuxième colonne contient la modification recommandée.</span><span class="sxs-lookup"><span data-stu-id="a5b19-152">The second column contains the recommended change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5b19-153">Le niveau de confiance de la recommandation et son succès sont prédéterminés par l'algorithme et ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="a5b19-153">The confidence level for the recommendation and its success are predetermined by the algorithm and cannot be changed.</span></span>  
  
## <a name="related-tools"></a><span data-ttu-id="a5b19-154">Outils connexes</span><span class="sxs-lookup"><span data-stu-id="a5b19-154">Related Tools</span></span>  
 <span data-ttu-id="a5b19-155">Le client d'exploration de données pour Excel, un complément séparé qui fournit des fonctionnalités d'exploration de données plus avancées, comprend des Assistants pour créer des modèles d'exploration de données qui prédisent le comportement.</span><span class="sxs-lookup"><span data-stu-id="a5b19-155">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="a5b19-156">Pour plus d’informations, consultez [création d’un modèle d’exploration de données](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="a5b19-156">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
 <span data-ttu-id="a5b19-157">Pour plus d’informations sur l’algorithme utilisé par l’outil de scénario de la valeur **cible** , consultez la rubrique « algorithme de régression logistique Microsoft » dans la [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] documentation en ligne de.</span><span class="sxs-lookup"><span data-stu-id="a5b19-157">For more information about the algorithm used by the **Goal Seek** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b19-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5b19-158">See Also</span></span>  
 [<span data-ttu-id="a5b19-159">Outils d'analyse de table pour Excel</span><span class="sxs-lookup"><span data-stu-id="a5b19-159">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
