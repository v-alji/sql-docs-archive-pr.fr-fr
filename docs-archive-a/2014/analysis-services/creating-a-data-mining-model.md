---
title: Création d’un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining models, creating
- forecasting [data mining]
- mining models, creating
- clustering [data mining]
- association [data mining]
- data modeling [data mining]
- estimation
- classification [data mining]
ms.assetid: 804b7db3-1f6a-4f73-a81d-bbe02520d7c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1e27739d3733c0b48dc6cff3e83e01f9cb12bce7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610899"
---
# <a name="creating-a-data-mining-model"></a><span data-ttu-id="43f2a-102">Création d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="43f2a-102">Creating a Data Mining Model</span></span>
  <span data-ttu-id="43f2a-103">La modélisation des données est l’étape d’exploration de données dans laquelle vous créez des modèles et des tendances en appliquant des *algorithmes* aux données.</span><span class="sxs-lookup"><span data-stu-id="43f2a-103">Data modeling is the step of data mining where you build patterns and trends by applying *algorithms* to data.</span></span> <span data-ttu-id="43f2a-104">Ultérieurement, utilisez ces séquences pour l'analyse, ou pour faire des prédictions.</span><span class="sxs-lookup"><span data-stu-id="43f2a-104">Later you can use those patterns for analysis, or to make predictions.</span></span>  
  
 <span data-ttu-id="43f2a-105">Les compléments d'exploration de données pour Office prennent en charge l'exploration de données au moyen d'Assistants qui facilitent la création de modèles.</span><span class="sxs-lookup"><span data-stu-id="43f2a-105">The Data Mining Add-ins for Office support data mining through wizards that make it easy to create models.</span></span> <span data-ttu-id="43f2a-106">Les Assistants analysent les données, identifient des corrélations, calculent l'importance statistique de toutes les variables et sélectionnent automatiquement le meilleur modèle.</span><span class="sxs-lookup"><span data-stu-id="43f2a-106">The wizards analyze the data, identify correlations, compute statistical significance of all variables, and automatically select the best model.</span></span>  
  
 <span data-ttu-id="43f2a-107">Bien que cette fonctionnalité soit tout aussi puissante que les outils d’exploration de données fournis par [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , la combinaison d’assistants et de l’interface Excel familière facilite la création, la modification et l’utilisation de l’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="43f2a-107">Although this functionality is every bit as powerful as the data mining tools provided by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the combination of wizards and the familiar Excel interface makes it easy to create, modify, and use data mining.</span></span>  
  
## <a name="advanced-data-mining"></a><span data-ttu-id="43f2a-108">Avancés (Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="43f2a-108">Advanced (Data Mining)</span></span>  
 <span data-ttu-id="43f2a-109">Les assistants avancés vous permettent de créer des modèles d’exploration de données basés sur des données stockées dans Excel, à l’aide de l’un des algorithmes d’exploration de données de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43f2a-109">The Advanced wizards let you create new data mining models, based on data stored in Excel, by using one of the data mining algorithms in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
### <a name="create-mining-structure"></a><span data-ttu-id="43f2a-110">Créer une structure d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="43f2a-110">Create Mining Structure</span></span>  
 <span data-ttu-id="43f2a-111">L'Assistant Création d'une structure d'exploration de données vous aide à générer une nouvelle structure d'exploration de données, que vous pouvez utiliser comme base pour plusieurs modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="43f2a-111">The Create Mining Structure wizard helps you build a new data mining structure, which you can use as the basis for multiple mining models.</span></span> <span data-ttu-id="43f2a-112">L'Assistant vous permet de mettre de côté une partie des données à utiliser comme un jeu de test, afin que vous puissiez évaluer tous les modèles qui utilisent les mêmes données selon un standard de test cohérent.</span><span class="sxs-lookup"><span data-stu-id="43f2a-112">The wizard gives you the option to set aside a portion of the data to use as a testing set, so that you can evaluate all models that use the same data according to a consistent testing standard.</span></span>  
  
 [<span data-ttu-id="43f2a-113">Créer des &#40;de structure d’exploration de données SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-113">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
### <a name="add-model-to-structure"></a><span data-ttu-id="43f2a-114">Ajouter un modèle à une structure</span><span class="sxs-lookup"><span data-stu-id="43f2a-114">Add Model to Structure</span></span>  
 <span data-ttu-id="43f2a-115">L'Assistant Ajout d'un modèle à une structure vous permet de choisir une structure d'exploration de données existante et de créer un nouveau modèle d'exploration de données pour cette structure.</span><span class="sxs-lookup"><span data-stu-id="43f2a-115">The Add Model to Structure wizard lets you choose an existing data mining structure and create a new data mining model for it.</span></span> <span data-ttu-id="43f2a-116">Vous pouvez ajouter plusieurs modèles d'exploration de données à une structure, en modifiant les paramètres ou choisissant des algorithmes d'exploration de données différents et personnaliser la sortie.</span><span class="sxs-lookup"><span data-stu-id="43f2a-116">You can add multiple mining models to a structure, changing the parameters or choosing different data mining algorithms, and customize the output.</span></span>  
  
 [<span data-ttu-id="43f2a-117">Ajouter un modèle à la structure &#40;compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-117">Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;</span></span>](add-model-to-structure-data-mining-add-ins-for-excel.md)  
  
## <a name="analyze-key-influencers-analyze"></a><span data-ttu-id="43f2a-118">Analyser les facteurs d'influence clés (Analyse)</span><span class="sxs-lookup"><span data-stu-id="43f2a-118">Analyze Key Influencers (Analyze)</span></span>  
 <span data-ttu-id="43f2a-119">Vous choisissez une colonne ou une valeur de sortie d'intérêt, puis l'algorithme analyse les données d'entrée pour identifier les facteurs qui ont le plus d'influence sur la cible.</span><span class="sxs-lookup"><span data-stu-id="43f2a-119">You choose a column or output value of interest, and then the algorithm analyzes all the input data to identify the factors that have the most influence on the target.</span></span> <span data-ttu-id="43f2a-120">Éventuellement, créez un rapport qui compare deux valeurs quelconques, afin que vous puissiez voir comment les facteurs d'influence changent.</span><span class="sxs-lookup"><span data-stu-id="43f2a-120">Optionally, you can create a report that compares any two values, so that you can see how the influencers change.</span></span>  
  
 <span data-ttu-id="43f2a-121">L’outil **analyser les influences clés** utilise l’algorithme Microsoft Naïve Bayes.</span><span class="sxs-lookup"><span data-stu-id="43f2a-121">The **Analyze Key Influencers** tool uses the Microsoft Naïve Bayes algorithm.</span></span>  
  
 [<span data-ttu-id="43f2a-122">Analyser les influenceurs clés &#40;les outils d’analyse de table pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-122">Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;</span></span>](analyze-key-influencers-table-analysis-tools-for-excel.md)  
  
## <a name="associate-data-mining"></a><span data-ttu-id="43f2a-123">Association (Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="43f2a-123">Associate (Data Mining)</span></span>  
 <span data-ttu-id="43f2a-124">L’Assistant **Association** crée un modèle d’association qui détecte des associations entre les éléments qui apparaissent dans plusieurs transactions : par exemple, dans l’analyse du panier d’marché.</span><span class="sxs-lookup"><span data-stu-id="43f2a-124">The **Associate** wizard builds an association model that detects associations between items that appear in multiple transactions: for example, in market basket analysis.</span></span>  
  
 [<span data-ttu-id="43f2a-125">Assistant Association &#40;client d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-125">Associate Wizard &#40;Data Mining Client for Excel&#41;</span></span>](associate-wizard-data-mining-client-for-excel.md)  
  
## <a name="classify-data-mining"></a><span data-ttu-id="43f2a-126">Classification (Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="43f2a-126">Classify (Data Mining)</span></span>  
 <span data-ttu-id="43f2a-127">L’Assistant **classification** crée un modèle de classification qui analyse les facteurs qui ont contribué à un résultat cible.</span><span class="sxs-lookup"><span data-stu-id="43f2a-127">The  **Classify** wizard builds a classification model that analyzes the factors that contributed to a target outcome.</span></span> <span data-ttu-id="43f2a-128">Utilisez plusieurs algorithmes avec cet Assistant, y compris d'arbre de décision, Naive Bayes, et de réseaux neuronaux.</span><span class="sxs-lookup"><span data-stu-id="43f2a-128">You can use multiple algorithms with this wizard, including Decision Trees, Naïve Bayes, and Neural Networks.</span></span>  
  
 [<span data-ttu-id="43f2a-129">Assistant classification &#40;compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-129">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="cluster-data-mining"></a><span data-ttu-id="43f2a-130">Cluster (Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="43f2a-130">Cluster (Data Mining)</span></span>  
 <span data-ttu-id="43f2a-131">L’Assistant **cluster** crée un modèle de clustering qui détecte les groupes de lignes qui partagent des caractéristiques similaires.</span><span class="sxs-lookup"><span data-stu-id="43f2a-131">The **Cluster** wizard builds a clustering model that detects groups of rows that share similar characteristics.</span></span> <span data-ttu-id="43f2a-132">Le clustering (parfois appelé *segmentation*) est une technique d’apprentissage non supervisée qui est très utile lorsque vous tentez de comprendre des modèles et des regroupements dans de nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="43f2a-132">Clustering (sometimes called *segmentation*) is an unsupervised learning technique that is very useful when trying to understand patterns and groupings in new data.</span></span>  
  
 <span data-ttu-id="43f2a-133">L'algorithme de gestion de clusters Microsoft prend en charge le clustering K-means et EM (Expectation maximization)</span><span class="sxs-lookup"><span data-stu-id="43f2a-133">The Microsoft Clustering algorithm supports several varieties of both K-means and Expectation maximization (EM) clustering</span></span>  
  
 <span data-ttu-id="43f2a-134">[Assistant de Cluster &#40;des compléments d’exploration de données pour Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="43f2a-134">[Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="detect-categories-analyze"></a><span data-ttu-id="43f2a-135">Détecter les catégories (Analyse)</span><span class="sxs-lookup"><span data-stu-id="43f2a-135">Detect Categories (Analyze)</span></span>  
 <span data-ttu-id="43f2a-136">L’outil **détecter les catégories** vous permet d’ajouter n’importe quel jeu de données et d’appliquer le clustering pour rechercher des regroupements de données.</span><span class="sxs-lookup"><span data-stu-id="43f2a-136">The **Detect Categories** tool lets you add any data set and apply clustering to find groupings of data.</span></span> <span data-ttu-id="43f2a-137">Il est utile pour rechercher des similarités et pour créer des groupes à analyser plus en détail.</span><span class="sxs-lookup"><span data-stu-id="43f2a-137">It's useful for finding similarities and for creating groups to further analyze.</span></span>  
  
 <span data-ttu-id="43f2a-138">L’outil **détecter les catégories** utilise l’algorithme de clustering Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43f2a-138">The **Detect Categories** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="43f2a-139">Détecter les catégories &#40;les outils d’analyse de table pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-139">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
## <a name="estimate-data-mining"></a><span data-ttu-id="43f2a-140">Estimation (Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="43f2a-140">Estimate (Data Mining)</span></span>  
 <span data-ttu-id="43f2a-141">L'Assistant Estimation crée un modèle d'estimation qui extrait les séquences de données remarquables et les utilise pour prédire des valeurs continues de type numérique, date ou heure.</span><span class="sxs-lookup"><span data-stu-id="43f2a-141">The Estimate wizard builds an estimation model that extracts data patterns and uses the patterns to predict continuous numeric, date, or time values.</span></span> <span data-ttu-id="43f2a-142">Il utilise l'algorithme MDT ([!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees).</span><span class="sxs-lookup"><span data-stu-id="43f2a-142">It uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
 [<span data-ttu-id="43f2a-143">Assistant estimation &#40;des compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-143">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="fill-from-example-analyze"></a><span data-ttu-id="43f2a-144">Remplir à partir de l'exemple (Analyse)</span><span class="sxs-lookup"><span data-stu-id="43f2a-144">Fill From Example (Analyze)</span></span>  
 <span data-ttu-id="43f2a-145">L’outil **remplir à partir de l’exemple** vous aide à imputer les valeurs manquantes.</span><span class="sxs-lookup"><span data-stu-id="43f2a-145">The **Fill From Example** tool helps you impute missing values.</span></span> <span data-ttu-id="43f2a-146">Vous fournissez des exemples de valeurs manquantes, et l'outil crée des modèles basés sur toutes les données de la table, puis recommande de nouvelles valeurs en fonction des séquences dans les données.</span><span class="sxs-lookup"><span data-stu-id="43f2a-146">You provide some examples of what the missing values should be, and the tool builds patterns based on all data in the table, and then recommends new values based on patterns in the data.</span></span>  
  
 <span data-ttu-id="43f2a-147">L’outil **remplir à partir de l’exemple** utilise l’algorithme de régression logistique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43f2a-147">The **Fill From Example** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="43f2a-148">Remplir à partir de l’exemple &#40;les outils d’analyse de table pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-148">Fill From Example &#40;Table Analysis Tools for Excel&#41;</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-analyze"></a><span data-ttu-id="43f2a-149">Prévision (Analyse)</span><span class="sxs-lookup"><span data-stu-id="43f2a-149">Forecast (Analyze)</span></span>  
 <span data-ttu-id="43f2a-150">L’outil **prévision** prend des données qui changent au fil du temps et prédit des valeurs futures.</span><span class="sxs-lookup"><span data-stu-id="43f2a-150">The **Forecast** tool takes data that changes over time, and predicts future values.</span></span>  
  
 <span data-ttu-id="43f2a-151">L’outil **prévision** utilise l’algorithme MTS (Microsoft Time Series).</span><span class="sxs-lookup"><span data-stu-id="43f2a-151">The **Forecast** tool uses the Microsoft Time Series algorithm.</span></span>  
  
 [<span data-ttu-id="43f2a-152">Outils d’analyse de table &#40;de prévision pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-152">Forecast &#40;Table Analysis Tools for Excel&#41;</span></span>](forecast-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-data-mining"></a><span data-ttu-id="43f2a-153">Prévision (Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="43f2a-153">Forecast (Data Mining)</span></span>  
 <span data-ttu-id="43f2a-154">L’Assistant **prévision** crée un modèle de prévision qui détecte les séquences dans une série de cellules, puis prédit des valeurs supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="43f2a-154">The **Forecast** wizard builds a forecasting model that detects patterns in a series of cells, and then forecasts additional values.</span></span>  
  
 [<span data-ttu-id="43f2a-155">Assistant Prévision &#40;des compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-155">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="highlight-exceptions-analyze"></a><span data-ttu-id="43f2a-156">Mettre en surbrillance les exceptions (Analyse)</span><span class="sxs-lookup"><span data-stu-id="43f2a-156">Highlight Exceptions (Analyze)</span></span>  
 <span data-ttu-id="43f2a-157">L’outil **mettre en surbrillance les exceptions** analyse les séquences dans une table de données et recherche les lignes et les valeurs qui ne correspondent pas au modèle.</span><span class="sxs-lookup"><span data-stu-id="43f2a-157">The **Highlight Exceptions** tool analyzes patterns in a table of data and finds rows and values that don't fit the pattern.</span></span> <span data-ttu-id="43f2a-158">Vous pouvez les examiner et les corriger, puis réexécuter le modèle, ou marquer les valeurs avec un indicateur pour une action ultérieure.</span><span class="sxs-lookup"><span data-stu-id="43f2a-158">You can then review and correct them and rerun the model, or flag values for later action.</span></span>  
  
 <span data-ttu-id="43f2a-159">L’outil **mettre en surbrillance les exceptions** utilise l’algorithme de clustering Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43f2a-159">The **Highlight Exceptions** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="43f2a-160">Mettre en surbrillance les exceptions &#40;les outils d’analyse de table pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-160">Highlight Exceptions &#40;Table Analysis Tools for Excel&#41;</span></span>](highlight-exceptions-table-analysis-tools-for-excel.md)  
  
## <a name="prediction-calculator-analyze"></a><span data-ttu-id="43f2a-161">Calcul de prédiction (Analyse)</span><span class="sxs-lookup"><span data-stu-id="43f2a-161">Prediction Calculator (Analyze)</span></span>  
 <span data-ttu-id="43f2a-162">Cet outil crée un modèle d'analyse des facteurs qui mènent aux résultats, puis prédit un résultat pour toute nouvelle entrée, en fonction de critères dérivés de ces modèles. Il génère également une feuille de calcul interactive pour la prise de décision qui vous permet d'établir le score de nouvelles entrées.</span><span class="sxs-lookup"><span data-stu-id="43f2a-162">This tool creates a model that analyzes the factors leading to target outcomes, and then predicts a result for any new input, based on criteria derived from these patterns It also generates an interactive decision making worksheet that lets you easily score new inputs.</span></span> <span data-ttu-id="43f2a-163">Vous pouvez également créer une version imprimée de la feuille de calcul que vous pouvez utiliser hors connexion pour l'établissement du score.</span><span class="sxs-lookup"><span data-stu-id="43f2a-163">You can also create a printed version of the scoring worksheet for offline use.</span></span>  
  
 <span data-ttu-id="43f2a-164">L’outil **calcul de prédiction** utilise l’algorithme de régression logistique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43f2a-164">The **Prediction Calculator** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="43f2a-165">Calcul de prédiction &#40;les outils d’analyse de table pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-165">Prediction Calculator &#40;Table Analysis Tools for Excel&#41;</span></span>](prediction-calculator-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-goal-seek-analyze"></a><span data-ttu-id="43f2a-166">Scénario : valeur cible (Analyse)</span><span class="sxs-lookup"><span data-stu-id="43f2a-166">Scenario: Goal Seek (Analyze)</span></span>  
 <span data-ttu-id="43f2a-167">Dans l’outil **recherche objectif** , vous spécifiez une valeur cible et l’outil identifie les facteurs sous-jacents qui doivent changer pour répondre à cette cible.</span><span class="sxs-lookup"><span data-stu-id="43f2a-167">In the **Goal Seek** tool, you specify a target value, and the tool identifies the underlying factors that must change to meet that target.</span></span> <span data-ttu-id="43f2a-168">Par exemple, si vous savez que vous devez augmenter la satisfaction des appels de 20 %, demandez au modèle de prédire les facteurs qui doivent changer pour obtenir cet objectif.</span><span class="sxs-lookup"><span data-stu-id="43f2a-168">For example, if you know that you must increase call satisfaction by 20%, you can ask the model to predict the factors that should change to produce that goal.</span></span>  
  
 <span data-ttu-id="43f2a-169">L’outil de **recherche d’objectif** utilise l’algorithme de régression logistique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43f2a-169">The **Goal Seek** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 <span data-ttu-id="43f2a-170">details</span><span class="sxs-lookup"><span data-stu-id="43f2a-170">details</span></span>  
  
 [<span data-ttu-id="43f2a-171">Scénario de la recherche de l’objectif &#40;outils d’analyse de table pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-171">Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](goal-seek-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-what-if-scenario-analyze"></a><span data-ttu-id="43f2a-172">Scénario : Scénario (Analyse)</span><span class="sxs-lookup"><span data-stu-id="43f2a-172">Scenario: What-If Scenario (Analyze)</span></span>  
 <span data-ttu-id="43f2a-173">L’outil d' **analyse de scénarios** complète l’outil de **recherche d’objectif** .</span><span class="sxs-lookup"><span data-stu-id="43f2a-173">The **What-If Analysis** tool complements the **Goal Seek** tool.</span></span> <span data-ttu-id="43f2a-174">Avec cet outil, vous entrez la valeur que vous souhaitez modifier, puis le modèle prédit si cette modification est suffisante pour obtenir les résultats souhaités.</span><span class="sxs-lookup"><span data-stu-id="43f2a-174">With this tool, you entered the value you want to change, and the model predicts whether that change will be sufficient to achieve the desired outcome.</span></span> <span data-ttu-id="43f2a-175">Par exemple, demandez au modèle de déterminer si l'ajout d'un opérateur augmenterait la satisfaction des clients d'un point.</span><span class="sxs-lookup"><span data-stu-id="43f2a-175">For example, you might ask the model to infer whether adding one extra call operator would increase customer satisfaction by one point.</span></span>  
  
 <span data-ttu-id="43f2a-176">L’outil **simulation** utilise l’algorithme de régression logistique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43f2a-176">The **What-If** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="43f2a-177">Scénario de simulation &#40;les outils d’analyse de table pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-177">What-If Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](what-if-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="shopping-basket-analysis-analyze"></a><span data-ttu-id="43f2a-178">Analyse du panier d'achat (Analyse)</span><span class="sxs-lookup"><span data-stu-id="43f2a-178">Shopping Basket Analysis (Analyze)</span></span>  
 <span data-ttu-id="43f2a-179">L’outil d' **analyse du panier d’achat** crée des groupes de produits qui sont fréquemment achetés ensemble, afin d’identifier les modèles qui peuvent être utilisés dans la vente croisée ou la vente incitative.</span><span class="sxs-lookup"><span data-stu-id="43f2a-179">The **Shopping Basket Analysis** tool creates groups of products that are frequently purchased together, to identify patterns that can be used in cross-selling or up-selling.</span></span> <span data-ttu-id="43f2a-180">Il génère également des rapports basés sur le prix et le coût de paquets de produits connexes, pour aider à la prise de décision.</span><span class="sxs-lookup"><span data-stu-id="43f2a-180">It also generates reports based on the price and cost of related product bundles, to aid in decision-making.</span></span>  
  
 <span data-ttu-id="43f2a-181">Utilisez également cet outil pour les événements qui se produisent fréquemment ensemble, les facteurs conduisant à un diagnostic, ou tout autre ensemble de causes et résultats potentiels.</span><span class="sxs-lookup"><span data-stu-id="43f2a-181">You can also use this tool for events that frequently occur together, factors leading to a diagnosis, or any other set of potential causes and outcomes.</span></span>  
  
 <span data-ttu-id="43f2a-182">L’outil d' **analyse du panier d’achat** utilise l’algorithme Microsoft Association.</span><span class="sxs-lookup"><span data-stu-id="43f2a-182">The **Shopping Basket Analysis** tool uses the Microsoft Association algorithm.</span></span>  
  
 [<span data-ttu-id="43f2a-183">Analyse du panier d’achat &#40;table outils pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-183">Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;</span></span>](shopping-basket-analysis-table-analysistools-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="43f2a-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43f2a-184">See Also</span></span>  
 <span data-ttu-id="43f2a-185">[Exploration et nettoyage des données](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="43f2a-185">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="43f2a-186">[Validation des modèles et utilisation de modèles pour la prédiction &#40;compléments d’exploration de données pour Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="43f2a-186">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="43f2a-187">Déploiement et mise à l’échelle des modèles d’exploration de données &#40;les compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="43f2a-187">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
