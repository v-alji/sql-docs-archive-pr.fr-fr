---
title: Algorithmes d’exploration de données (compléments d’exploration de données SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- segmentation
- data mining algorithms
- clustering [data mining]
- linear regression
- association [data mining]
- neural networks
- logistic regression
- regression
- sequence analysis
- decision tree [data mining]
- Naive Bayes
- time series [data mining]
ms.assetid: 3a1a62e4-9fb5-4cdb-a6c6-1b8b30d417ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3a73ce5a538756a740afd2db72d585fa54f03cae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613234"
---
# <a name="data-mining-algorithms-sql-server-data-mining-add-ins"></a><span data-ttu-id="0750f-102">Algorithmes d'exploration de données (Compléments d'exploration de données SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0750f-102">Data Mining Algorithms (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="0750f-103">Les Compléments d'exploration de données pour Office prennent en charge la création de modèles analytiques utilisant les algorithmes d'exploration de données suivants.</span><span class="sxs-lookup"><span data-stu-id="0750f-103">The Data Mining Add-ins for Office supports creation of analytical models using the following data mining algorithms.</span></span> <span data-ttu-id="0750f-104">Tous les algorithmes reposent sur des méthodes d'apprentissage automatique connues et ont été implémentés par Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="0750f-104">All algorithms are based on well-known machine learning methods and have been implemented by Microsoft Research.</span></span>  
  
## <a name="algorithms"></a><span data-ttu-id="0750f-105">Algorithmes</span><span class="sxs-lookup"><span data-stu-id="0750f-105">Algorithms</span></span>  
  
|<span data-ttu-id="0750f-106">Méthode d'apprentissage automatique</span><span class="sxs-lookup"><span data-stu-id="0750f-106">Machine learning method</span></span>|<span data-ttu-id="0750f-107">Fonctionnement</span><span class="sxs-lookup"><span data-stu-id="0750f-107">How it works</span></span>|  
|-----------------------------|------------------|  
|<span data-ttu-id="0750f-108">Algorithme MAR (Microsoft Association Rules)</span><span class="sxs-lookup"><span data-stu-id="0750f-108">Microsoft Association Rules  algorithm</span></span>|<span data-ttu-id="0750f-109">Découvrez les produits achetés ensemble ou les événements qui se produisent simultanément, et utilisez le modèle pour créer des recommandations.</span><span class="sxs-lookup"><span data-stu-id="0750f-109">Discover which products are purchased together or which events occur together, and use the model to create recommendations.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174916.aspx](https://msdn.microsoft.com/library/ms174916.aspx)|  
|<span data-ttu-id="0750f-110">Algorithme de gestion de clusters Microsoft</span><span class="sxs-lookup"><span data-stu-id="0750f-110">Microsoft Clustering algorithm</span></span>|<span data-ttu-id="0750f-111">Définissez des segments de marché, regroupez automatiquement les clients liés, ou recherchez des relations dans les données à utiliser dans une exploration des données plus détaillée.</span><span class="sxs-lookup"><span data-stu-id="0750f-111">Define market segments, automatically group related customers together, or find relationships in data to use in further mining.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174879.aspx](https://msdn.microsoft.com/library/ms174879.aspx)|  
|<span data-ttu-id="0750f-112">Algorithme MDT (Microsoft Decision Trees)</span><span class="sxs-lookup"><span data-stu-id="0750f-112">Microsoft Decision Trees algorithm</span></span>|<span data-ttu-id="0750f-113">Identifiez les relations précédemment inconnues entre chaque élément de vos données afin de mieux éclairer vos décisions, ou recherchez les facteurs qui ont généré des résultats spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0750f-113">Identify previously unknown relationships between various elements of your data to better inform your decisions, or find the factors that lead to specific outcomes.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
|<span data-ttu-id="0750f-114">Algorithme MLR (Microsoft Linear Regression)</span><span class="sxs-lookup"><span data-stu-id="0750f-114">Microsoft Linear Regression algorithm</span></span>|<span data-ttu-id="0750f-115">Recherchez une formule mathématique décrivant les facteurs qui contribuent à un résultat numérique.</span><span class="sxs-lookup"><span data-stu-id="0750f-115">Find a mathematical formula that describes factors that contribute to a numeric outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174824.aspx](https://msdn.microsoft.com/library/ms174824.aspx)|  
|<span data-ttu-id="0750f-116">Algorithme MLR (Microsoft Logistic Regression)</span><span class="sxs-lookup"><span data-stu-id="0750f-116">Microsoft Logistic Regression algorithm</span></span>|<span data-ttu-id="0750f-117">Identifiez les facteurs qui contribuent à des résultats binaires et apprenez comment les utiliser pour affecter les résultats.</span><span class="sxs-lookup"><span data-stu-id="0750f-117">Identify the factors that contribute to binary outcomes, and learn how to use those to affect results.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174828.aspx](https://msdn.microsoft.com/library/ms174828.aspx)|  
|<span data-ttu-id="0750f-118">Algorithme MNB (Microsoft Naive Bayes)</span><span class="sxs-lookup"><span data-stu-id="0750f-118">Microsoft Naïve Bayes algorithm</span></span>|<span data-ttu-id="0750f-119">Explorez les relations dans vos données et recherchez celles qui sont le plus étroitement corrélées avec un résultat.</span><span class="sxs-lookup"><span data-stu-id="0750f-119">Explore relationships in your data and find those mostly closely correlated with an outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174806.aspx](https://msdn.microsoft.com/library/ms174806.aspx)|  
|<span data-ttu-id="0750f-120">Algorithme MNN (Microsoft Neural Networks)</span><span class="sxs-lookup"><span data-stu-id="0750f-120">Microsoft Neural Networks algorithm</span></span>|<span data-ttu-id="0750f-121">Recherchez des relations masquées entre plusieurs entrées et même entre plusieurs sorties.</span><span class="sxs-lookup"><span data-stu-id="0750f-121">Find hidden relationships among multiple inputs and even multiple outputs.</span></span> <span data-ttu-id="0750f-122">Utilisation pour l'exploration ou pour une prédiction.</span><span class="sxs-lookup"><span data-stu-id="0750f-122">Use for exploration or for prediction.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174941.aspx](https://msdn.microsoft.com/library/ms174941.aspx)|  
|<span data-ttu-id="0750f-123">Algorithme MTS (Microsoft Time Series)</span><span class="sxs-lookup"><span data-stu-id="0750f-123">Microsoft Time Series algorithm</span></span>|<span data-ttu-id="0750f-124">Utilisez des données d'historique pour prédire des valeurs futures.</span><span class="sxs-lookup"><span data-stu-id="0750f-124">Use historical data to forecast future values.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
  
## <a name="advanced-options"></a><span data-ttu-id="0750f-125">Options avancées</span><span class="sxs-lookup"><span data-stu-id="0750f-125">Advanced Options</span></span>  
 <span data-ttu-id="0750f-126">Lorsque vous utilisez le Client d'exploration de données pour Excel, vous pouvez soit créer vos propres structures et modèles d'exploration de données, soit optimiser les paramètres des algorithmes.</span><span class="sxs-lookup"><span data-stu-id="0750f-126">When you use the Data Mining Client for Excel, you have the option to create your own data mining structures and models, or to fine-tune the parameters of the algorithms.</span></span>  
  
 [<span data-ttu-id="0750f-127">Les paramètres d’algorithme &#40;SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="0750f-127">Algorithm Parameters &#40;SQL Server Data Mining Add-ins&#41;</span></span>](algorithm-parameters-sql-server-data-mining-add-ins.md)  
  
 <span data-ttu-id="0750f-128">Il existe deux façons de personnaliser vos modèles à l'aide de ces options avancées :</span><span class="sxs-lookup"><span data-stu-id="0750f-128">There are two ways to customize your models using these advanced options:</span></span>  
  
-   <span data-ttu-id="0750f-129">Utilisez l’Assistant **requête d’exploration de données** pour créer votre modèle.</span><span class="sxs-lookup"><span data-stu-id="0750f-129">Use the **Data Mining Query** wizard to create your model.</span></span>  
  
-   <span data-ttu-id="0750f-130">Dans le **client d’exploration de données**, après avoir démarré l’Assistant, cliquez sur **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="0750f-130">In the **Data Mining Client**, after you start the wizard, click **Parameters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0750f-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0750f-131">See Also</span></span>  
 <span data-ttu-id="0750f-132">[&#40;de requêtes SQL Server des compléments d’exploration de données&#41;](query-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="0750f-132">[Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="0750f-133">Modèles avancés &#40;des compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0750f-133">Advanced Modeling &#40;Data Mining Add-ins for Excel&#41;</span></span>](advanced-modeling-data-mining-add-ins-for-excel.md)  
  
  
