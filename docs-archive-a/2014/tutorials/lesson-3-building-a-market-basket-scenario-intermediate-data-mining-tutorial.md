---
title: 'Leçon 3 : génération d’un scénario de panier d’un marché (Didacticiel intermédiaire sur l’exploration de données) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- association algorithms [Analysis Services]
- nested tables
- tutorials [Data Mining]
ms.assetid: 651eef38-772e-4d97-af51-075b1b27fc5a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a281aa62fbf08393c95f12ded9886ac212b3165f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704463"
---
# <a name="lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="ff538-102">Leçon 3 : Génération d'un scénario de panier d'achat (Didacticiel sur l'exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="ff538-102">Lesson 3: Building a Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="ff538-103">Le service marketing de la société [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] souhaite améliorer son site Web pour promouvoir la vente croisée.</span><span class="sxs-lookup"><span data-stu-id="ff538-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to improve the company Web site to promote cross-selling.</span></span> <span data-ttu-id="ff538-104">Dans le cadre de la mise à jour du site, il veut pouvoir prédire les produits que les clients sont susceptibles d'acheter en fonction des produits déjà présents dans leurs paniers d'achat en ligne.</span><span class="sxs-lookup"><span data-stu-id="ff538-104">As part of the site update, they would like the ability to predict products that a customer might want to purchase, based on the other products that are already in the customer's online shopping basket.</span></span> <span data-ttu-id="ff538-105">Le service marketing souhaite également mieux comprendre le comportement d'achat des clients, afin de pouvoir concevoir le site Web de façon à ce que les articles susceptibles d'être achetés ensemble apparaissent ensemble.</span><span class="sxs-lookup"><span data-stu-id="ff538-105">The marketing department also wants to understand customer purchasing behavior better, so that they can design the Web site so that the items that tend to be purchased together appear together.</span></span> <span data-ttu-id="ff538-106">Il a appris que l'exploration de données est particulièrement utile pour ce type d' *analyse du panier d'achat* et vous demandé de développer un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="ff538-106">They have learned that data mining is especially useful for this kind of *market basket analysis* and have asked you to develop a data mining model.</span></span>  
  
 <span data-ttu-id="ff538-107">Une fois les tâches de cette leçon terminées, vous disposerez d'un modèle d'exploration de données qui présentera les articles par groupe à partir de l'historique des transactions des clients.</span><span class="sxs-lookup"><span data-stu-id="ff538-107">After you complete the tasks in this lesson, you will have a mining model that shows groups of items from historical customer transactions.</span></span> <span data-ttu-id="ff538-108">En outre, vous pourrez utiliser le modèle d'exploration de données pour prédire les articles supplémentaires qu'un client sera susceptible d'acheter.</span><span class="sxs-lookup"><span data-stu-id="ff538-108">Additionally, you can use the mining model to predict additional items that a customer may want to purchase.</span></span>  
  
 <span data-ttu-id="ff538-109">Pour effectuer les tâches de cette leçon, vous allez utiliser la solution et la source de données que vous avez créées dans la première leçon du didacticiel sur l' [exploration de données intermédiaire &#40;Analysis Services-exploration de données&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ff538-109">To complete the tasks in this lesson, you will use the solution and data source that you created in the first lesson of the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="ff538-110">Vous modifierez cette solution en ajoutant une vue de source de données qui contient des tables relatives au client, notamment une table imbriquée des achats des clients.</span><span class="sxs-lookup"><span data-stu-id="ff538-110">You will modify this solution by adding a data source view that contains tables about the customer, including a nested table of customer purchases.</span></span>  <span data-ttu-id="ff538-111">Vous générerez ensuite un modèle d'exploration de données qui utilise l'algorithme MAR (Microsoft Association Rules), adapté aux scénarios d'analyse de panier.</span><span class="sxs-lookup"><span data-stu-id="ff538-111">You will then build a mining model that uses the Microsoft Association Rules algorithm, which is suited to market basket scenarios.</span></span>  
  
 <span data-ttu-id="ff538-112">Cette leçon contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff538-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="ff538-113">Ajout d’une vue de source de données avec des tables imbriquées &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-113">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ff538-114">Création d’une structure et d’un modèle de panier d’évolution &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-114">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ff538-115">Modification et traitement du modèle Market Basket &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-115">Modifying and Processing the Market Basket Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modify-process-market-basket-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ff538-116">Exploration des modèles de panier d’évolution &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-116">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ff538-117">Filtrage d’une table imbriquée dans un modèle d’exploration de données &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-117">Filtering a Nested Table in a Mining Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ff538-118">Prédiction d’associations &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-118">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ff538-119">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="ff538-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ff538-120">Ajout d’une vue de source de données avec des tables imbriquées &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-120">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="ff538-121">Toutes les leçons</span><span class="sxs-lookup"><span data-stu-id="ff538-121">All Lessons</span></span>  
 [<span data-ttu-id="ff538-122">Leçon 1 : création de la solution intermédiaire d’exploration de données &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-122">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ff538-123">Leçon 2 : génération d’un scénario de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-123">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="ff538-124">Leçon 3 : Scénario de panier d’achat (didacticiel sur l’exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="ff538-124">Lesson 3: Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="ff538-125">Leçon 4 : génération d’un scénario Sequence Clustering &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-125">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="ff538-126">Leçon 5 : Génération de modèles de réseau neuronal et de régression logistique &#40;Didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-126">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff538-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff538-127">See Also</span></span>  
 <span data-ttu-id="ff538-128">[Didacticiel sur l’exploration de données de base](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ff538-128">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="ff538-129">[Leçon 2 : génération d’un scénario de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ff538-129">[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="ff538-130">Leçon 4 : génération d’un scénario Sequence Clustering &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ff538-130">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
  
