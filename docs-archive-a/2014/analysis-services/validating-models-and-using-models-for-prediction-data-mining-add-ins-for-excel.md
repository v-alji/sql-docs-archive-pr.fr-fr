---
title: Validation des modèles et utilisation des modèles pour la prédiction (compléments d’exploration de données pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, validating
- mining models, charting
- validation [data mining]
- mining models, testing
ms.assetid: e245ac1f-1230-48e9-9091-e70b131aa2a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1dd4f9bab977a90579076b824d2c0aa525c84af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603655"
---
# <a name="validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel"></a><span data-ttu-id="57d87-102">Validation des modèles et utilisation des modèles pour la prédiction (compléments d'exploration de données pour Excel)</span><span class="sxs-lookup"><span data-stu-id="57d87-102">Validating Models and Using Models for Prediction (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="57d87-103">Le test et la validation de votre modèle est une étape importante du processus d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="57d87-103">Testing and validating your model is an important step in the data mining process.</span></span> <span data-ttu-id="57d87-104">Vous devez savoir dans quelle mesure vos modèles d'exploration de données sont efficaces sur des données réelles avant de les déployer dans un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="57d87-104">You must know how well your mining models perform against real data before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="57d87-105">Les compléments d'exploration de données incluent des outils qui permettent de tester les modèles que vous avez créés, et de créer des prédictions et des recommandations à l'aide des modèles.</span><span class="sxs-lookup"><span data-stu-id="57d87-105">The Data Mining Add-ins include tools that help you test the models you built, and create predictions and recommendations using the models.</span></span>  
  
## <a name="accuracy-chart"></a><span data-ttu-id="57d87-106">Graphique de précision</span><span class="sxs-lookup"><span data-stu-id="57d87-106">Accuracy Chart</span></span>  
 <span data-ttu-id="57d87-107">L’Assistant **graphique de précision** vous aide à créer une requête de prédiction et à évaluer les performances d’un modèle d’exploration de données en créant un graphique de courbes d’élévation ou un graphique à nuages de points.</span><span class="sxs-lookup"><span data-stu-id="57d87-107">The **Accuracy Chart** wizard helps you create a prediction query and assess the performance of a data mining model by creating a lift chart or scatter plot chart.</span></span> <span data-ttu-id="57d87-108">Le graphique de courbes d'élévation permet de différencier les modèles dans les structures où ils sont presque identiques et de déterminer quels sont ceux permettant d'obtenir les prédictions les plus précises.</span><span class="sxs-lookup"><span data-stu-id="57d87-108">The lift chart helps distinguish between models in a structure that are almost the same, to help you determine which model provides the best predictions.</span></span>  
  
 [<span data-ttu-id="57d87-109">Graphique d’analyse de précision &#40;SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="57d87-109">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
## <a name="classification-matrix"></a><span data-ttu-id="57d87-110">Matrice de classification</span><span class="sxs-lookup"><span data-stu-id="57d87-110">Classification Matrix</span></span>  
 <span data-ttu-id="57d87-111">L’Assistant **matrice de classification** vous aide à créer une requête de prédiction pour évaluer les performances d’un modèle de classification.</span><span class="sxs-lookup"><span data-stu-id="57d87-111">The **Classification Matrix** wizard helps you create a prediction query to assess the performance of a classification model.</span></span> <span data-ttu-id="57d87-112">Il en résulte un graphique qui synthétise à la fois les prédictions précises et les prédictions imprécises effectuées par le modèle.</span><span class="sxs-lookup"><span data-stu-id="57d87-112">The output is a chart that summarizes both accurate and inaccurate predictions made by the model.</span></span> <span data-ttu-id="57d87-113">La matrice est un outil très utile étant donné qu'elle montre non seulement combien de fois le modèle a correctement prédit une valeur, mais aussi les valeurs que le modèle a le plus fréquemment prédites de façon incorrecte.</span><span class="sxs-lookup"><span data-stu-id="57d87-113">The matrix is a valuable tool because it not only shows how frequently the model correctly predicted a value, but also shows which values the model most frequently predicted incorrectly.</span></span>  
  
 [<span data-ttu-id="57d87-114">&#40;de matrices de classification SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="57d87-114">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
## <a name="profit-chart"></a><span data-ttu-id="57d87-115">Graphique des bénéfices</span><span class="sxs-lookup"><span data-stu-id="57d87-115">Profit Chart</span></span>  
 <span data-ttu-id="57d87-116">L’Assistant **graphique des bénéfices** vous aide à évaluer les avantages de l’utilisation d’un modèle d’exploration de données et à évaluer les coûts des faux positifs et des faux négatifs</span><span class="sxs-lookup"><span data-stu-id="57d87-116">The **Profit Chart** wizard helps you weigh the benefits of using a data mining model and assess the costs of both false positives and false negatives</span></span>  
  
 <span data-ttu-id="57d87-117">Ce type de graphique mesure la précision de prédiction du modèle et incorpore l'unité et le coût global spécifiés.</span><span class="sxs-lookup"><span data-stu-id="57d87-117">This chart type measures the prediction accuracy of the model and incorporates unit and overall costs that you specify.</span></span>  
  
 <span data-ttu-id="57d87-118">[Graphique des bénéfices &#40;SQL Server&#41;des compléments d’exploration de données ](profit-chart-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="57d87-118">[Profit Chart &#40;SQL Server Data Mining Add-ins&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="cross-validation"></a><span data-ttu-id="57d87-119">Validation croisée</span><span class="sxs-lookup"><span data-stu-id="57d87-119">Cross-Validation</span></span>  
 <span data-ttu-id="57d87-120">La validation croisée est une technique établie dans la communauté d'exploration de données pour évaluer la validité d'un jeu de données et la précision d'un modèle d'exploration de données sur ce jeu de données.</span><span class="sxs-lookup"><span data-stu-id="57d87-120">Cross-validation is an established technique in the data mining community for assessing the validity of a data set and the accuracy of a mining model on that data set.</span></span> <span data-ttu-id="57d87-121">Elle divise un ensemble de données en sous-ensembles, puis crée, forme et test de manière itérative les modèles sur chaque sous-ensemble.</span><span class="sxs-lookup"><span data-stu-id="57d87-121">It divides a set of data into subsets, and then iteratively creates, trains, and tests models on each subset.</span></span>  
  
 <span data-ttu-id="57d87-122">L’Assistant **validation croisée** vous permet de spécifier le nombre de replis pour la Division de vos données, puis fournit un rapport de validation croisée qui décrit de façon statistique les différences entre ces sections croisées.</span><span class="sxs-lookup"><span data-stu-id="57d87-122">The **Cross-Validation** wizard lets you specify the number of folds to divide your data by, and then provides a cross-validation report that statistically describes the differences among these cross-sections.</span></span> <span data-ttu-id="57d87-123">Déterminez ensuite si le modèle est efficace sur toutes les données d'apprentissage, ou peut être dévié vers un sous-ensemble particulier.</span><span class="sxs-lookup"><span data-stu-id="57d87-123">From this you can determine whether the model performs well on all training data, or might be skewed to a particular subset.</span></span>  
  
 [<span data-ttu-id="57d87-124">Validation croisée &#40;SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="57d87-124">Cross-Validation &#40;SQL Server Data Mining Add-ins&#41;</span></span>](cross-validation-sql-server-data-mining-add-ins.md)  
  
## <a name="query-wizard"></a><span data-ttu-id="57d87-125">Assistant Requête</span><span class="sxs-lookup"><span data-stu-id="57d87-125">Query Wizard</span></span>  
 <span data-ttu-id="57d87-126">L’Assistant **requête** est un outil interactif qui vous aide à créer une requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="57d87-126">The **Query** wizard is an interactive tool that helps you build a prediction query.</span></span> <span data-ttu-id="57d87-127">Les requêtes indiquent comment sont générées les recommandations, les prévisions, etc.</span><span class="sxs-lookup"><span data-stu-id="57d87-127">Queries are how you generate recommendations, future forecasts, and so forth.</span></span>  
  
 <span data-ttu-id="57d87-128">Dans l’Assistant **requête** , vous choisissez un modèle, puis vous fournissez des données d’entrée, soit comme valeurs uniques, soit à partir d’une table ou d’une plage, et l’Assistant vous aide à sélectionner les colonnes à générer.</span><span class="sxs-lookup"><span data-stu-id="57d87-128">In the **Query** wizard, you pick a model, and then provide input data, either as single values or from a table or range, and the wizard helps you select columns to output.</span></span> <span data-ttu-id="57d87-129">Ajoutez également des fonctions à votre requête pour générer des scores de probabilité et d'autres statistiques utiles.</span><span class="sxs-lookup"><span data-stu-id="57d87-129">You can also add functions to your query to generate probability scores and other useful statistics.</span></span>  
  
 [<span data-ttu-id="57d87-130">&#40;de requêtes SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="57d87-130">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
## <a name="advanced-query-editor"></a><span data-ttu-id="57d87-131">Éditeur de requête avancé</span><span class="sxs-lookup"><span data-stu-id="57d87-131">Advanced Query Editor</span></span>  
 <span data-ttu-id="57d87-132">L' **éditeur de requêtes avancé** est un ensemble interactif de boîtes de dialogue qui vous aide à créer tous les types d’instructions DMX, de l’exécution de requêtes personnalisées à la création et à l’apprentissage de nouveaux modèles, à la suppression de modèles ou à la création de nouveaux jeux de données.</span><span class="sxs-lookup"><span data-stu-id="57d87-132">The **Advanced Query Editor** is an interactive set of dialog boxes that helps you build all kinds of DMX statements, anything from running custom queries to creating and training new models, deleting models, or creating new data sets.</span></span>  
  
 [<span data-ttu-id="57d87-133">Éditeur de requêtes d’exploration de données avancée</span><span class="sxs-lookup"><span data-stu-id="57d87-133">Advanced Data Mining Query Editor</span></span>](advanced-data-mining-query-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="57d87-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57d87-134">See Also</span></span>  
 <span data-ttu-id="57d87-135">[Exploration et nettoyage des données](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="57d87-135">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="57d87-136">[Création d’un modèle d’exploration de données](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="57d87-136">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="57d87-137">Déploiement et mise à l’échelle des modèles d’exploration de données &#40;les compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="57d87-137">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
