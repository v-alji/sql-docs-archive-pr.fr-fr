---
title: 'Leçon 2 : génération d’un scénario de prévision (Didacticiel intermédiaire sur l’exploration de données) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time series [Analysis Services]
- data mining [Analysis Services], tutorials
- tutorials [Data Mining]
ms.assetid: 9a988156-c900-4c22-97fa-f6b0c1aea9e2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c81d5846df0a37c2b4182cb92fea86ce6f3417a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600423"
---
# <a name="lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="286f2-102">Leçon 2 : génération d'un scénario de prévision (Didacticiel intermédiaire sur l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="286f2-102">Lesson 2: Building a Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="286f2-103">Vous êtes analyste des ventes pour [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]et il vous a été demandé de fournir une estimation des ventes des produits pour l'année à venir.</span><span class="sxs-lookup"><span data-stu-id="286f2-103">As the sales analyst for [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you have been asked to forecast the sales of products for the next year.</span></span> <span data-ttu-id="286f2-104">Plus précisément, vous devez comparer les estimations entre les différentes régions et les différentes gammes de produits.</span><span class="sxs-lookup"><span data-stu-id="286f2-104">In particular, you have been asked to compare forecasts for the different regions and product lines.</span></span> <span data-ttu-id="286f2-105">Vous devez, de plus, déterminer si les ventes des différents produits varient en fonction de la période de l'année.</span><span class="sxs-lookup"><span data-stu-id="286f2-105">Additionally, you have been asked to determine whether sales of different products vary depending on the time of the year.</span></span>  
  
 <span data-ttu-id="286f2-106">Afin de rechercher les informations demandées, vous allez, au cours de cette leçon, faire un récapitulatif des ventes de l'entreprise au niveau mensuel et synthétiser les chiffres des ventes en fonction de trois régions : Europe, Amérique du Nord et Pacifique.</span><span class="sxs-lookup"><span data-stu-id="286f2-106">To find the requested information, in this lesson you will summarize the company's sales data at the monthly level, and you will also summarize sales figures by three regions: Europe, North America, and the Pacific.</span></span>  
  
 <span data-ttu-id="286f2-107">Une fois les tâches de cette leçon terminées, vous serez en mesure de répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="286f2-107">After you complete the tasks in this lesson, you will be able to answer the following questions:</span></span>  
  
-   <span data-ttu-id="286f2-108">Comment les ventes de différents modèles de vélos varient-elles au fil du temps ?</span><span class="sxs-lookup"><span data-stu-id="286f2-108">How do the sales of different bike models change over time?</span></span>  
  
-   <span data-ttu-id="286f2-109">Existe-t-il des différences entre les modèles des ventes dans les trois régions ?</span><span class="sxs-lookup"><span data-stu-id="286f2-109">Are there differences between the patterns for sales in the three regions?</span></span>  
  
-   <span data-ttu-id="286f2-110">Est-il possible de prédire des pics dans les ventes ?</span><span class="sxs-lookup"><span data-stu-id="286f2-110">Can we forecast sales peaks?</span></span>  
  
 <span data-ttu-id="286f2-111">La leçon peut être effectuée en deux parties :</span><span class="sxs-lookup"><span data-stu-id="286f2-111">The lesson can be completed in two parts:</span></span>  
  
-   <span data-ttu-id="286f2-112">La première partie présente la création et l'utilisation de base d'un modèle de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="286f2-112">Part One introduces the basics of how to create and use a time series model.</span></span>  
  
-   <span data-ttu-id="286f2-113">La deuxième partie vous guide tout au long de la création d'un modèle de série chronologique, basé sur toutes les régions.</span><span class="sxs-lookup"><span data-stu-id="286f2-113">Part Two walks you through creation of a general time series model, based on all regions.</span></span> <span data-ttu-id="286f2-114">Utilisez ce modèle général pour une *prédiction croisée*.</span><span class="sxs-lookup"><span data-stu-id="286f2-114">You can use this general model for *cross-prediction*.</span></span>  
  
 <span data-ttu-id="286f2-115">Pour effectuer les tâches de cette leçon, répertoriées ci-dessous, vous allez utiliser la [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] source de données que vous avez créée au cours de la [leçon 1 : création de la solution intermédiaire d’exploration de données &#40;didacticiel sur l’exploration de données intermédiaire&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="286f2-115">To complete the tasks in this lesson, which are listed below, you will use the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source that you created in [Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="286f2-116">Les dates dans l'exemple de base de données de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] ont été mises à jour pour cette version.</span><span class="sxs-lookup"><span data-stu-id="286f2-116">The dates in the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] sample database have been updated for this release.</span></span> <span data-ttu-id="286f2-117">Si vous utilisez une version antérieure de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], vous pouvez générer le modèle en suivant ces étapes, mais les résultats peuvent être différents.</span><span class="sxs-lookup"><span data-stu-id="286f2-117">If you use an earlier version of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you can build the model following these steps, but you might see different results.</span></span>  
  
 <span data-ttu-id="286f2-118">**Création d'un modèle de prévision simple**</span><span class="sxs-lookup"><span data-stu-id="286f2-118">**Creating a Simple Forecasting Model**</span></span>  
  
-   [<span data-ttu-id="286f2-119">Ajout d’une vue de source de données pour les prévisions &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-119">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="286f2-120">Création d’une structure et d’un modèle de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-120">Creating a Forecasting Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="286f2-121">Modification de la structure de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-121">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="286f2-122">Personnalisation et traitement du modèle de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-122">Customizing and Processing the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/customize-process-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="286f2-123">Exploration du modèle de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-123">Exploring the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="286f2-124">Création de prédictions de série chronologique &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-124">Creating Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="286f2-125">**Création d'un modèle de prévision général pour la prédiction croisée**</span><span class="sxs-lookup"><span data-stu-id="286f2-125">**Creating a General Forecasting Model for Cross-Prediction**</span></span>  
  
-   [<span data-ttu-id="286f2-126">Prédictions de série chronologique avancées &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-126">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="286f2-127">Prédictions de série chronologique utilisant des données mises à jour &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-127">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="286f2-128">Prédictions de série chronologique utilisant des données de remplacement &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-128">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="286f2-129">Comparaison des prédictions pour les modèles de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-129">Comparing Predictions for Forecasting Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="286f2-130">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="286f2-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="286f2-131">Ajout d’une vue de source de données pour les prévisions &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-131">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="286f2-132">Comprendre la configuration requise pour un modèle de série chronologique &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-132">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="286f2-133">Toutes les leçons</span><span class="sxs-lookup"><span data-stu-id="286f2-133">All Lessons</span></span>  
 [<span data-ttu-id="286f2-134">Leçon 1 : création de la solution intermédiaire d’exploration de données &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-134">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="286f2-135">Leçon 2 : Scénario de prévision (didacticiel sur l’exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="286f2-135">Lesson 2: Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="286f2-136">Leçon 3 : Génération d’un scénario de panier d’achat &#40;Didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-136">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="286f2-137">Leçon 4 : génération d’un scénario Sequence Clustering &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-137">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="286f2-138">Leçon 5 : Génération de modèles de réseau neuronal et de régression logistique &#40;Didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="286f2-138">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="286f2-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="286f2-139">See Also</span></span>  
 <span data-ttu-id="286f2-140">[Didacticiel sur l’exploration de données de base](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="286f2-140">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="286f2-141">[Didacticiel sur l’exploration de données intermédiaire &#40;Analysis Services d’exploration de données&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="286f2-141">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="286f2-142">Algorithme MTS (Microsoft Time Series)</span><span class="sxs-lookup"><span data-stu-id="286f2-142">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
