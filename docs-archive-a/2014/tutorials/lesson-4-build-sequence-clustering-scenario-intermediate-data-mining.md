---
title: 'Leçon 4 : génération d’un scénario Sequence Clustering (didacticiel sur l’exploration de données intermédiaire) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- sequence clustering algorithms [Analysis Services]
- tutorials [Data Mining]
ms.assetid: 63436bbd-0f73-4012-b6f1-358c81e4d92a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 0f417c685d8af898de7c66ffe82045fa76b582e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694859"
---
# <a name="lesson-4-building-a-sequence-clustering-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="f1ed9-102">Leçon 4 : Génération d'un scénario Sequence Clustering (Didacticiel sur l'exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="f1ed9-102">Lesson 4: Building a Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="f1ed9-103">Le service marketing de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] souhaite comprendre comment les clients se déplacent sur le site web [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1ed9-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to understand how customers move through the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] Web site.</span></span> <span data-ttu-id="f1ed9-104">Cette société suppose que l'ordre dans lequel les clients ajoutent des produits dans leurs paniers obéit à un modèle.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-104">The company suspects that there is a pattern to the order in which customers put products into their shopping baskets.</span></span> <span data-ttu-id="f1ed9-105">Il souhaite en effet analyser l'ordre des séquences d'achat afin de découvrir comment les clients ajoutent des articles associés à leurs paniers.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-105">They want to analyze the order of purchase sequences to learn how customers add related items to their baskets.</span></span> <span data-ttu-id="f1ed9-106">Elle peut utiliser ces informations pour rationaliser le flux du site Web afin qu'il conduise les clients à acheter des produits supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-106">They can then use this information to streamline the flow of the Web site so that it leads customers to purchase additional products.</span></span>  
  
 <span data-ttu-id="f1ed9-107">Une fois que vous aurez terminé les tâches de cette leçon, vous aurez créé un modèle d'exploration de données qui utiliser l'algorithme MSC ( [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering) pour prévoir le prochain article que les clients ajouteront à leurs paniers d'achats.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-107">After you complete the tasks in this lesson, you will have created a mining model that uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm to predict the next item that customers will put into their shopping baskets.</span></span> <span data-ttu-id="f1ed9-108">Vous allez expérimenter les deux versions du modèle : une qui analyse uniquement l'ordre des produits dans le panier et une qui contient d'autres caractéristiques démographiques des clients à des fins de regroupement.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-108">You will experiment with two versions of the model: one that analyzes only the order of products in the basket, and one that contains some additional customer demographics for clustering.</span></span> <span data-ttu-id="f1ed9-109">Enfin, vous allez utiliser les modèles pour créer des prédictions que vous pourrez utiliser pour recommander des produits aux clients.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-109">Finally, you will use the models to create predictions that you can use to recommend products to customers.</span></span>  
  
 <span data-ttu-id="f1ed9-110">Pour effectuer les tâches de la leçon, vous allez utiliser la structure d’exploration de données Market panier que vous avez créée au cours de la [leçon 3 : génération d’un scénario de panier de marché &#40;didacticiel sur l’exploration de données intermédiaire&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f1ed9-110">To complete the tasks in the lesson, you will use the market basket mining structure that you created in [Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="f1ed9-111">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="f1ed9-111">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="f1ed9-112">Création d’une structure de modèle d’exploration de données Sequence Clustering &#40;Didacticiel intermédiaire sur l’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-112">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="f1ed9-113">Traitement du modèle Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="f1ed9-113">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
-   [<span data-ttu-id="f1ed9-114">Exploration du modèle Sequence Clustering &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-114">Exploring the Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="f1ed9-115">Création d’un modèle de clustering séquencé associé &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-115">Creating a Related Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="f1ed9-116">Création de prédictions sur un modèle Sequence Clustering &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-116">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f1ed9-117">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="f1ed9-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f1ed9-118">Création d’une structure de modèle d’exploration de données Sequence Clustering &#40;Didacticiel intermédiaire sur l’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-118">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="f1ed9-119">Toutes les leçons</span><span class="sxs-lookup"><span data-stu-id="f1ed9-119">All Lessons</span></span>  
 [<span data-ttu-id="f1ed9-120">Leçon 1 : création de la solution intermédiaire d’exploration de données &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-120">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="f1ed9-121">Leçon 2 : génération d’un scénario de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-121">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="f1ed9-122">Leçon 3 : Génération d’un scénario de panier d’achat &#40;Didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-122">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="f1ed9-123">Leçon 4 : Scénario Sequence Clustering (didacticiel sur l’exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="f1ed9-123">Lesson 4: Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="f1ed9-124">Leçon 5 : Génération de modèles de réseau neuronal et de régression logistique &#40;Didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-124">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="f1ed9-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1ed9-125">See Also</span></span>  
 <span data-ttu-id="f1ed9-126">[Didacticiel sur l’exploration de données de base](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="f1ed9-126">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="f1ed9-127">Didacticiel sur l’exploration de données intermédiaire &#40;Analysis Services d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ed9-127">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
