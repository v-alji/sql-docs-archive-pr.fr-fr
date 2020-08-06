---
title: 'Leçon 5 : génération de modèles de réseau neuronal et de régression logistique (didacticiel sur l’exploration de données intermédiaire) | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- logistic regression [Analysis Services]
- data mining [Analysis Services], tutorials
- neural networks
- tutorials [Data Mining]
- neural network model [Analysis Services]
ms.assetid: 42c3701a-1fd2-44ff-b7de-377345bbbd6b
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a8c9fcf0380582f15fa2bf30d6fdeb97bb2ab1fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604315"
---
# <a name="lesson-5-building-neural-network-and-logistic-regression-models-intermediate-data-mining-tutorial"></a><span data-ttu-id="8b909-102">Leçon 5 : Génération de modèles de réseau neuronal et de régression logistique (Didacticiel sur l'exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="8b909-102">Lesson 5: Building Neural Network and Logistic Regression Models (Intermediate Data Mining Tutorial)</span></span>
  
  
 <span data-ttu-id="8b909-103">Le service d'exploitation de la société [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] prend part à un projet visant à améliorer la satisfaction des clients avec leur centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="8b909-103">The Operations department of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] is engaged in a project to improve customer satisfaction with their call center.</span></span> <span data-ttu-id="8b909-104">Il a embauché un fournisseur pour gérer le centre d'appels et signaler des mesures de l'efficacité du centre d'appels, et vous a demandé d'analyser certaines données préliminaires fournies par ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8b909-104">They hired a vendor to manage the call center and to report metrics on call center effectiveness, and have asked you to analyze some preliminary data provided by the vendor.</span></span> <span data-ttu-id="8b909-105">Il veut savoir si des découvertes intéressantes ont été faites.</span><span class="sxs-lookup"><span data-stu-id="8b909-105">They want to know if there are any interesting findings.</span></span> <span data-ttu-id="8b909-106">En particulier, il veut savoir si les données suggèrent des problèmes de personnel ou des façons d'améliorer la satisfaction de la clientèle.</span><span class="sxs-lookup"><span data-stu-id="8b909-106">In particular, they would like to know if the data suggests any staffing problems with staffing or ways to improve customer satisfaction.</span></span>  
  
 <span data-ttu-id="8b909-107">Le jeu de données est peu volumineux et couvre uniquement une période de 30 jours du fonctionnement du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="8b909-107">The data set is small and covers only a 30-day period in the operation of the call center.</span></span> <span data-ttu-id="8b909-108">Les données suivent le nombre des opérateurs nouveaux et expérimentés dans chaque équipe, le nombre d'appels entrants, le nombre de commandes, ainsi que les problèmes qui doivent être résolus et la durée moyenne d'attente d'un client avant que quelqu'un ne réponde à un appel.</span><span class="sxs-lookup"><span data-stu-id="8b909-108">The data tracks the number of new and experienced operators in each shift, the number of incoming calls, the number of orders as well as issues that must be resolved, and the average time a customer waits for someone to respond to a call.</span></span> <span data-ttu-id="8b909-109">Les données incluent également une niveau mesure de qualité de service basée sur *le taux d'abandon*qui est un indicateur de la frustration des clients.</span><span class="sxs-lookup"><span data-stu-id="8b909-109">The data also includes a service quality metric based on *abandon rate*, which is an indicator of customer frustration.</span></span>  
  
 <span data-ttu-id="8b909-110">Puisque vous n'avez pas d'attente préalable par rapport à ce que les données indiqueront, vous décidez d'utiliser un modèle de réseau neuronal pour explorer les corrélations possibles.</span><span class="sxs-lookup"><span data-stu-id="8b909-110">Because you do not have any prior expectations about what the data will show, you decide to use a neural network model to explore possible correlations.</span></span> <span data-ttu-id="8b909-111">Les modèles de réseau neuronal sont souvent utilisés pour l'exploration car ils peuvent analyser des relations complexes entre de nombreuses entrées et sorties.</span><span class="sxs-lookup"><span data-stu-id="8b909-111">Neural network models are often used for exploration because they can analyze complex relationships between many inputs and outputs.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="8b909-112">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="8b909-112">What You Will Learn</span></span>  
 <span data-ttu-id="8b909-113">Dans cette leçon, vous allez utiliser l'algorithme MNN (Microsoft Neural Network) pour générer un modèle que vous et l'équipe Opérations pouvez utiliser pour comprendre les tendances des données.</span><span class="sxs-lookup"><span data-stu-id="8b909-113">In this lesson, you will use the neural network algorithm to build a model that you and the Operations team can use to understand the trends in the data.</span></span> <span data-ttu-id="8b909-114">Dans le cadre de cette leçon, vous allez essayer de répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b909-114">As part of this lesson, you will try to answer the following questions:</span></span>  
  
-   <span data-ttu-id="8b909-115">Quels facteurs affectent la satisfaction des clients ?</span><span class="sxs-lookup"><span data-stu-id="8b909-115">What factors affect customer satisfaction?</span></span>  
  
-   <span data-ttu-id="8b909-116">Qu'est-ce que le centre d'appels peut faire pour améliorer la qualité du service ?</span><span class="sxs-lookup"><span data-stu-id="8b909-116">What can the call center do to improve service quality?</span></span>  
  
 <span data-ttu-id="8b909-117">Sur la base des résultats, vous générerez ensuite un modèle de régression logistique que vous pouvez utiliser pour des prédictions.</span><span class="sxs-lookup"><span data-stu-id="8b909-117">Based on the results, you will then build a logistic regression model that you can use for predictions.</span></span> <span data-ttu-id="8b909-118">Les prédictions seront utilisées par l'équipe d'exploitation comme une aide dans la planification du fonctionnement du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="8b909-118">The predictions will be used by the Operations team as an aid in planning call center operation.</span></span>  
  
 <span data-ttu-id="8b909-119">Cette leçon contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b909-119">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="8b909-120">Ajout d’une vue de source de données pour le centre de données &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-120">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="8b909-121">Création d’une structure et d’un modèle de réseau neuronal &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-121">Creating a Neural Network Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-neural-network-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="8b909-122">Exploration du modèle de centre d’appels &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-122">Exploring the Call Center Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-call-center-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="8b909-123">Ajout d’un modèle de régression logistique à la structure du centre d’appels &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-123">Adding a Logistic Regression Model to the Call Center Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-logistic-regression-model-to-call-center-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="8b909-124">Création de prédictions pour les modèles de centre d’appels &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-124">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8b909-125">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="8b909-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8b909-126">Ajout d’une vue de source de données pour le centre de données &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-126">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="8b909-127">Toutes les leçons</span><span class="sxs-lookup"><span data-stu-id="8b909-127">All Lessons</span></span>  
 [<span data-ttu-id="8b909-128">Leçon 1 : création de la solution intermédiaire d’exploration de données &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-128">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="8b909-129">Leçon 2 : génération d’un scénario de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-129">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="8b909-130">Leçon 3 : Génération d’un scénario de panier d’achat &#40;Didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-130">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="8b909-131">Leçon 4 : génération d’un scénario Sequence Clustering &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-131">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 <span data-ttu-id="8b909-132">Leçon 5 : Scénario de réseau neuronal et de régression logistique (didacticiel sur l’exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="8b909-132">Lesson 5: Neural Network and Logistic Regression Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b909-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b909-133">See Also</span></span>  
 <span data-ttu-id="8b909-134">[Didacticiel sur l’exploration de données de base](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="8b909-134">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="8b909-135">Didacticiel sur l’exploration de données intermédiaire &#40;Analysis Services d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="8b909-135">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
