---
title: Exploration d’un modèle de réseau neuronal | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- mining model, neural network
- neural networks
- dependency network
ms.assetid: e4224cb7-115b-4889-ac07-03f096fb55fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: ab2673d5b1881f74c2bc146b084d2efc7b06d69b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602555"
---
# <a name="browsing-a-neural-network-model"></a><span data-ttu-id="bf3b9-102">Exploration d'un modèle MNN (Microsoft Neural Network)</span><span class="sxs-lookup"><span data-stu-id="bf3b9-102">Browsing a Neural Network Model</span></span>
  <span data-ttu-id="bf3b9-103">Quand vous ouvrez un modèle de réseau neuronal ou de régression logistique à l’aide de **Parcourir**, le modèle est affiché dans une visionneuse interactive semblable à la visionneuse de modèle de réseau neuronal dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf3b9-103">When you open a neural network or logistic regression model using **Browse**, the model is displayed in an interactive viewer, similar to the neural network model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="bf3b9-104">La visionneuse permet d'explorer les corrélations et d'obtenir des informations sur les schémas du modèle et les données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-104">The viewer helps you explore correlations, and get information about the patterns in the model and the underlying data.</span></span>

##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="bf3b9-105">Explorer le modèle</span><span class="sxs-lookup"><span data-stu-id="bf3b9-105">Explore the Model</span></span>
 <span data-ttu-id="bf3b9-106">Les modèles basés sur les algorithmes de réseau neuronal ou de régression logistique de [!INCLUDE[msCoName](../includes/msconame-md.md)] sont similaires dans le sens où ils analysent des données comme un ensemble de connexions parmi les entrées et les sorties connues.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-106">Models that are based on [!INCLUDE[msCoName](../includes/msconame-md.md)] Neural Network or Logistic Regression algorithms are similar in that they analyze data as a set of connections among known inputs and outputs.</span></span> <span data-ttu-id="bf3b9-107">La visionneuse **Parcourir** vous aide à explorer ces connexions, avec les contrôles suivants :</span><span class="sxs-lookup"><span data-stu-id="bf3b9-107">The **Browse** viewer helps you to explore those connections, using the following controls:</span></span>

-   [<span data-ttu-id="bf3b9-108">Variables</span><span class="sxs-lookup"><span data-stu-id="bf3b9-108">Variables</span></span>](#BKMK_Variables)

-   [<span data-ttu-id="bf3b9-109">Entrées</span><span class="sxs-lookup"><span data-stu-id="bf3b9-109">Inputs</span></span>](#BKMK_Inputs)

-   [<span data-ttu-id="bf3b9-110">Sorties</span><span class="sxs-lookup"><span data-stu-id="bf3b9-110">Outputs</span></span>](#BKMK_Outputs)

 <span data-ttu-id="bf3b9-111">Si vous souhaitez essayer cette visionneuse, vous pouvez créer un modèle à l’aide de [l’Assistant Classification &#40;compléments d’exploration de données pour Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md), puis utiliser l’option **Avancé** pour remplacer l’algorithme par Microsoft Logistic Regression dans la boîte de dialogue **Paramètres d’algorithme**.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-111">If you want to experiment with this viewer, you can create a model using the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard, and use the **Advanced** option to change the algorithm to Microsoft Logistic Regression in the **Algorithm Parameters** dialog box.</span></span>

###  <a name="variables"></a><a name="BKMK_Variables"></a><span data-ttu-id="bf3b9-112">Variables</span><span class="sxs-lookup"><span data-stu-id="bf3b9-112">Variables</span></span>
 <span data-ttu-id="bf3b9-113">Le volet **Variables** affiche la liste des variables d’entrée par ordre de leur effet sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-113">The **Variables** pane displays a list of input variables in order of their effect on the model.</span></span> <span data-ttu-id="bf3b9-114">Vous utilisez les contrôles **Entrée** et **Sortie** pour filtrer le modèle, ce qui affecte les variables qui sont affichées, ainsi que leur ordre.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-114">You use the **Input** and **Output** controls to filter the model, affecting the variables that are displayed, as well as their order.</span></span>

 <span data-ttu-id="bf3b9-115">Grâce à cette visionneuse, vous pouvez explorer les facteurs qui sont les plus importants pour déterminer si un client est plus susceptible d'appartenir à la catégorie des acheteurs de vélo ou à la catégorie des non-acheteurs.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-115">Using this viewer, you can explore the factors that are most important in determining whether a customer more likely belongs to the bike buyer category or the non-buyer category.</span></span>

 <span data-ttu-id="bf3b9-116">![Tester l'effet sur le résultat des attributs sélectionnés](media/dm13-neuralnet-agebuyer1.gif "Tester l'effet sur le résultat des attributs sélectionnés")</span><span class="sxs-lookup"><span data-stu-id="bf3b9-116">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer1.gif "Testing effect on outcome of selected attributes")</span></span>

##### <a name="explore-variables"></a><span data-ttu-id="bf3b9-117">Explorer les variables</span><span class="sxs-lookup"><span data-stu-id="bf3b9-117">Explore variables</span></span>

1.  <span data-ttu-id="bf3b9-118">Initialement, le volet **Variables** est trié par ordre des attributs les plus importants, en fonction des filtres actifs.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-118">Initially, the **Variables** pane is sorted in order of the most important attributes, given the current filters.</span></span> <span data-ttu-id="bf3b9-119">La longueur de la barre indique l'intensité du facteur.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-119">The length of the bar indicates the strength of the factor.</span></span>

     <span data-ttu-id="bf3b9-120">Dans l'exemple, vous pouvez voir que le revenu est le facteur le plus influent, suivi de la région.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-120">In the example, you can see that income is the most influential factor, followed by region.</span></span> <span data-ttu-id="bf3b9-121">D'autre part, les clients possédant plusieurs voitures et les parents de plusieurs enfants sont bien moins susceptibles d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-121">On the other hand, customers with many cars and many children are highly unlikely to buy a bike.</span></span>

2.  <span data-ttu-id="bf3b9-122">Dans le volet **Variables**, cliquez sur l’en-tête de colonne **Attribut**.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-122">In the **Variables** pane, click the column heading for **Attribute**.</span></span>

     <span data-ttu-id="bf3b9-123">En effectuant le tri sur l'attribut, vous pouvez voir les conteneurs qui ont été créés pour chacune des colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-123">By sorting on attribute, you can see the bins that were created for each of the input columns.</span></span> <span data-ttu-id="bf3b9-124">Les colonnes avec des valeurs discrètes, telles que la profession, sont placées dans un *conteneur* selon les valeurs littérales.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-124">Columns with discrete values, such as occupation, are *binned* by the literal values.</span></span>

3.  <span data-ttu-id="bf3b9-125">Notez les plages de valeurs qui ont été trouvées pour **Age** et **Income**.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-125">Notice the ranges of values that were found for **Age** and **Income**.</span></span>

     <span data-ttu-id="bf3b9-126">Si certaines de vos colonnes d'entrée sont des nombres (autrement dit, la colonne de données entière est un type de données numériques continues), les nombres sont placés dans un compartiment, ou dans un conteneur, selon des plages discrètes.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-126">If any of your input columns are numbers (that is, the entire column of data is a continuous numeric data type), the numbers are bucketed, or binned, into discrete ranges.</span></span>

     <span data-ttu-id="bf3b9-127">Pour ce qui est du revenu, la colonne a été sous-divisée en regroupements tels que 78,4-154,06 (pour la plage de revenu la plus haute).</span><span class="sxs-lookup"><span data-stu-id="bf3b9-127">For Income, the column has been subdivided into groupings such as 78.4-154.06 (for the uppermost income range).</span></span>

     <span data-ttu-id="bf3b9-128">![trier pour voir comment les variables sont placées dans un conteneur](media/dm13-nn-bucketing-variables.gif "trier pour voir comment les variables sont placées dans un conteneur")</span><span class="sxs-lookup"><span data-stu-id="bf3b9-128">![sort to view how variables were binned](media/dm13-nn-bucketing-variables.gif "sort to view how variables were binned")</span></span>

     <span data-ttu-id="bf3b9-129">Si vous souhaitez différents regroupements, utilisez l’outil [Réétiqueter &#40;compléments d’exploration de données SQL Server&#41;](relabel-sql-server-data-mining-add-ins.md) ou les fonctions Excel pour créer des catégories de revenu avant de générer le modèle.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-129">If you want different groupings, you should use the [Relabel &#40;SQL Server Data Mining Add-ins&#41;](relabel-sql-server-data-mining-add-ins.md) tool, or Excel functions, to create new income categories before building the model.</span></span>

4.  <span data-ttu-id="bf3b9-130">Cliquez sur **Privilégie Oui** pour rétablir la vue par défaut du graphique.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-130">Click **Favors Yes** to restore the graph to the default view.</span></span>

     <span data-ttu-id="bf3b9-131">Par défaut, la vue est triée selon la valeur de **Privilégie** pour la première valeur de résultat.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-131">By default, the view is sorted by the value of **Favors** for the first outcome value.</span></span> <span data-ttu-id="bf3b9-132">Vous pouvez modifier les résultats qui sont attribués aux première et deuxième colonnes en choisissant une nouvelle valeur pour **Valeur 1** et **Valeur 2** dans **Sortie**.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-132">You can change which outcomes are assigned to the first and second columns by choosing a new value for **Value 1** and **Value 2** in **Output**.</span></span>

5.  <span data-ttu-id="bf3b9-133">Placez le pointeur de la souris sur la barre de couleur la plus élevée dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-133">Pause the mouse over the topmost colored bar in the chart.</span></span>

     <span data-ttu-id="bf3b9-134">Une info-bulle apparaît. Elle comprend un score *d’importance*, une paire de scores de *probabilité* et une paire de valeurs de *finesse*.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-134">A ToolTip appears that includes an *importance* score, a pair of *probability* scores, and a pair of *lift* values.</span></span>

    -   <span data-ttu-id="bf3b9-135">**importance** est calculée dans l’intégralité du dataset et identifie l’attribut qui, compte tenu de toutes les entrées, est le plus corrélé avec le résultat cible.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-135">**Importance** is calculated across the entire dataset, and identifies the attribute that, given all inputs, is most correlated with the target outcome.</span></span> <span data-ttu-id="bf3b9-136">La visionneuse trie les valeurs dans le graphique par scores d'importance.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-136">The viewer sorts the values in the chart by the importance scores.</span></span>

    -   <span data-ttu-id="bf3b9-137">La **probabilité** est calculée pour chaque ensemble de paires attribut-valeur, pour les résultats cibles dans le jeu de données entier.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-137">**Probability** is calculated for each set of attribute-value pairs, for the target outcomes, across the entire data set.</span></span>

    -   <span data-ttu-id="bf3b9-138">La **finesse** vous indique l’utilité de cette paire attribut-valeur particulière pour favoriser un résultat ou un autre.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-138">**Lift** tells you how useful this particular attribute-value pair is for promoting one outcome or another.</span></span>

     <span data-ttu-id="bf3b9-139">Remarque : l'info-bulle contient les mêmes informations, quelle que soit la colonne où vous positionnez la souris.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-139">Note: The ToolTip contains the same information no matter whether you position the mouse over one column or the other.</span></span>

 [<span data-ttu-id="bf3b9-140">Retour au début</span><span class="sxs-lookup"><span data-stu-id="bf3b9-140">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="inputs"></a><a name="BKMK_Inputs"></a><span data-ttu-id="bf3b9-141">Port</span><span class="sxs-lookup"><span data-stu-id="bf3b9-141">Inputs</span></span>
 <span data-ttu-id="bf3b9-142">Le volet **Entrées** vous permet de choisir un ensemble d’entrées et de l’appliquer en tant que filtre au modèle, ce qui vous permet de voir l’impact de ces choix sur les résultats, en fonction des données d’apprentissage</span><span class="sxs-lookup"><span data-stu-id="bf3b9-142">The **Inputs** pane lets you choose a set of inputs and apply that as a filter to the model, which lets you see the influence of those choices on the outcome, based on the training data</span></span>

##### <a name="explore-inputs"></a><span data-ttu-id="bf3b9-143">Explorer les entrées</span><span class="sxs-lookup"><span data-stu-id="bf3b9-143">Explore inputs</span></span>

1.  <span data-ttu-id="bf3b9-144">Supposez que vous vouliez cibler un groupe particulier et voir les facteurs qui influent le plus sur la décision d'achat dans ce groupe.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-144">Suppose you want to target a particular group, and see the factors that most influence purchasing in that group.</span></span>

     <span data-ttu-id="bf3b9-145">Dans le volet **entrée** , cliquez sur la **\<All>** cellule sous **attribut**, puis sélectionnez Age ( **âge**).</span><span class="sxs-lookup"><span data-stu-id="bf3b9-145">In the **Input** pane, click the **\<All>** cell under **Attribute**, and select **Age**.</span></span>

     <span data-ttu-id="bf3b9-146">Pour **Valeur**, sélectionnez la catégorie correspondant à la tranche d’âge des plus jeunes.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-146">For **Value**, select the youngest age category.</span></span>

2.  <span data-ttu-id="bf3b9-147">Notez que même lorsque vous filtrez sur un groupe d'âges particulier, la zone Pacifique est proche du haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-147">Notice that even when you filter on a particular age group, the Pacific region comes to near the top of the list.</span></span> <span data-ttu-id="bf3b9-148">Cela s'explique par le fait que les clients de la zone Pacifique sont bien plus susceptibles d'acheter un vélo que les clients dans d'autres régions du monde.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-148">This is because customers in the Pacific region are far more likely to buy a bike than customers in other regions.</span></span>

     <span data-ttu-id="bf3b9-149">Dans la mesure où la région ne constitue pas un critère sur lequel vous pouvez influer, vous pouvez à nouveau modifier les entrées pour supprimer cette variable des facteurs à prendre en compte et afficher d'autres facteurs.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-149">Since region is not something you can influence, to remove this variable from consideration and see other factors, you can change the inputs again.</span></span>

     <span data-ttu-id="bf3b9-150">Dans le volet **Entrée**, cliquez sur la cellule vide sous **Age** puis sélectionnez **Region**.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-150">In the **Input** pane, click the empty cell under **Age**, and select **Region**.</span></span>

     <span data-ttu-id="bf3b9-151">Pour **Valeur**, sélectionnez **Europe**.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-151">For **Value**, select **Europe**.</span></span>

3.  <span data-ttu-id="bf3b9-152">Continuez à ajouter des filtres d'entrée pour vous concentrer sur un groupe d'intérêt spécifique.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-152">Continue adding input filters to focus on a group of particular interest.</span></span>

     <span data-ttu-id="bf3b9-153">Par exemple, pour l’attribut d’entrée, ajoutez **Gender**, puis sélectionnez **Female** comme valeur.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-153">For example, for the input attribute, add **Gender**, and select **Female** as the value.</span></span>

     <span data-ttu-id="bf3b9-154">![Tester l'effet sur le résultat des attributs sélectionnés](media/dm13-neuralnet-agebuyer2.gif "Tester l'effet sur le résultat des attributs sélectionnés")</span><span class="sxs-lookup"><span data-stu-id="bf3b9-154">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer2.gif "Testing effect on outcome of selected attributes")</span></span>

     <span data-ttu-id="bf3b9-155">Notez le changement de la liste des variables.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-155">Notice how the list of variables changes.</span></span> <span data-ttu-id="bf3b9-156">Maintenant, **Income** est la variable qui est la plus importante lors de la prédiction du résultat cible.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-156">Now **Income** is the variable that is most important in predicting the target outcome.</span></span>

     <span data-ttu-id="bf3b9-157">L'ordre dans lequel vous appliquez les filtres d'entrée n'affecte pas les résultats.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-157">The order in which you apply the input filters does not affect the results.</span></span>

 [<span data-ttu-id="bf3b9-158">Retour au début</span><span class="sxs-lookup"><span data-stu-id="bf3b9-158">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="outputs"></a><a name="BKMK_Outputs"></a><span data-ttu-id="bf3b9-159">Enverra</span><span class="sxs-lookup"><span data-stu-id="bf3b9-159">Outputs</span></span>
 <span data-ttu-id="bf3b9-160">Dans le volet **Outputs**, vous pouvez choisir le résultat qui vous intéresse.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-160">In the **Outputs** pane, you can choose the outcome that you are interested in.</span></span> <span data-ttu-id="bf3b9-161">Les réseaux neuronaux vous permettent de spécifier autant de colonnes de résultats que vous le souhaitez, bien que l'ajout de sorties supplémentaires ajoute à la complexité du modèle et puisse nécessiter un temps de traitement beaucoup plus long.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-161">Neural networks let you specify as many outcome columns as you like, although adding more outputs adds to the complexity of the model and may require a much longer time to process.</span></span>

 <span data-ttu-id="bf3b9-162">Pour comparer deux sorties, elles doivent avoir été désignées comme colonnes **Prédire** ou **Prédire uniquement**.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-162">To compare two outputs, they must have been designated as **Predict** or **Predict Only** columns.</span></span>

##### <a name="explore-outputs"></a><span data-ttu-id="bf3b9-163">Explorer les sorties</span><span class="sxs-lookup"><span data-stu-id="bf3b9-163">Explore outputs</span></span>

1.  <span data-ttu-id="bf3b9-164">Utilisez la liste **Attribut de sortie** pour sélectionner un attribut.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-164">Use the **Output Attribute** list to select an attribute.</span></span>

2.  <span data-ttu-id="bf3b9-165">Sélectionnez deux résultats des listes Valeur 1 et Valeur 2.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-165">Select two outcomes from the Value 1 and Value 2 lists.</span></span> <span data-ttu-id="bf3b9-166">Ces deux états de l’attribut de sortie seront comparés dans le volet **Variables** .</span><span class="sxs-lookup"><span data-stu-id="bf3b9-166">These two states of the output attribute will be compared in the **Variables** pane.</span></span>

 [<span data-ttu-id="bf3b9-167">Retour au début</span><span class="sxs-lookup"><span data-stu-id="bf3b9-167">Back To Top</span></span>](#BKMK_Tabs)

## <a name="more-about-neural-network-models"></a><span data-ttu-id="bf3b9-168">En savoir plus sur les modèles de réseau neuronal</span><span class="sxs-lookup"><span data-stu-id="bf3b9-168">More About Neural Network Models</span></span>
 <span data-ttu-id="bf3b9-169">Les informations de la visionneuse sont récupérées du serveur à l'aide d'une procédure stockée spécifique à ce type de modèle : System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-169">The information in the viewer is retrieved from the server using a stored procedure specific to this model type: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span></span>

 <span data-ttu-id="bf3b9-170">Si vous souhaitez créer un modèle comprenant de nombreux attributs prédictibles à l’aide des compléments, utilisez les options de modélisation **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="bf3b9-170">If you want to create a model with multiple predictable attributes using the add-ins, use the **Advanced** modeling options.</span></span>

 <span data-ttu-id="bf3b9-171">Pour plus d’informations, consultez [Créer une structure d’exploration de données &#40;compléments d’exploration de données SQL Server&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) et [Ajouter un modèle à une structure &#40;compléments d’exploration de données pour Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="bf3b9-171">For more information, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) and [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf3b9-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf3b9-172">See Also</span></span>
 [<span data-ttu-id="bf3b9-173">Exploration des modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="bf3b9-173">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)


