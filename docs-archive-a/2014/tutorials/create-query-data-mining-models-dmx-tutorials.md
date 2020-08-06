---
title: 'Création et interrogation de modèles d’exploration de données à l’aide de DMX : didacticiels (Analysis Services-exploration de données) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 145b81a7-c0c3-4ca3-bb32-0b482423b9a0
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 22ed01105a32f460bcbeb2c067299fdf62af2eed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599711"
---
# <a name="creating-and-querying-data-mining-models-with-dmx-tutorials-analysis-services---data-mining"></a><span data-ttu-id="d6301-102">Création et interrogation de modèles d'exploration de données à l'aide du langage DMX : didacticiels (Analysis Services - Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="d6301-102">Creating and Querying Data Mining Models with DMX: Tutorials (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="d6301-103">Une fois que vous avez créé une solution d’exploration de données à l’aide de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , vous pouvez créer des requêtes sur les modèles d’exploration de données pour prédire des tendances, récupérer des modèles dans les données et mesurer la précision des modèles d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d6301-103">After you have created a data mining solution by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you can create queries against the data mining models to predict trends, retrieve patterns in the data, and measure the accuracy of the mining models.</span></span>  
  
 <span data-ttu-id="d6301-104">Les didacticiels pas à pas de la liste suivante vous aideront à apprendre à créer et à exécuter des requêtes d’exploration de données à l’aide de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] afin que vous puissiez tirer le meilleur parti de vos données.</span><span class="sxs-lookup"><span data-stu-id="d6301-104">The step-by-step tutorials in the following list will help you learn how to build and run data mining queries by using [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] so that you can get the most from your data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6301-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d6301-105">In This Section</span></span>  
  
-   [<span data-ttu-id="d6301-106">Didacticiel DMX Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="d6301-106">Bike Buyer DMX Tutorial</span></span>](../../2014/tutorials/bike-buyer-dmx-tutorial.md)  
  
     <span data-ttu-id="d6301-107">Dans ce didacticiel, vous allez apprendre à créer une nouvelle structure et des modèles d'exploration de données  à l'aide du langage DMX (Data Mining Extensions) et à créer des requêtes de prédiction DMX.</span><span class="sxs-lookup"><span data-stu-id="d6301-107">This tutorial walks you through the creation of a new mining structure and mining models by using the Data Mining Extensions (DMX) language, and explains how to create DMX prediction queries.</span></span>  
  
-   [<span data-ttu-id="d6301-108">Didacticiel DMX Market Basket</span><span class="sxs-lookup"><span data-stu-id="d6301-108">Market Basket DMX Tutorial</span></span>](../../2014/tutorials/market-basket-dmx-tutorial.md)  
  
     <span data-ttu-id="d6301-109">Ce didacticiel utilise un scénario de panier d'achat typique, avec des associations entre les produits que les clients achètent simultanément.</span><span class="sxs-lookup"><span data-stu-id="d6301-109">This tutorial uses a typical market basket scenario, where you find associations between the products that customers purchase together.</span></span> <span data-ttu-id="d6301-110">Ce didacticiel montre également comment utiliser des tables imbriquées lorsque vous créez une structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d6301-110">This tutorial also demonstrates how to use nested tables when you create a mining structure.</span></span> <span data-ttu-id="d6301-111">Vous générez et effectuez l'apprentissage d'un modèle selon cette structure, puis vous créez des prédictions à l'aide de DMX.</span><span class="sxs-lookup"><span data-stu-id="d6301-111">You build and train a model based on this structure, and then create predictions using DMX.</span></span>  
  
-   [<span data-ttu-id="d6301-112">Didacticiel DMX sur la prédiction de série chronologique</span><span class="sxs-lookup"><span data-stu-id="d6301-112">Time Series Prediction DMX Tutorial</span></span>](../../2014/tutorials/time-series-prediction-dmx-tutorial.md)  
  
     <span data-ttu-id="d6301-113">Ce didacticiel crée un modèle de prévision pour illustrer l'utilisation de l'instruction CREATE MODEL (DMX).</span><span class="sxs-lookup"><span data-stu-id="d6301-113">This tutorial creates a forecasting model to illustrate the use of the CREATE MODEL (DMX) statement.</span></span> <span data-ttu-id="d6301-114">Vous ajoutez ensuite des modèles liés et personnalisez le comportement de chacun en modifiant les paramètres de l'algorithme MTS (Microsoft Time Series).</span><span class="sxs-lookup"><span data-stu-id="d6301-114">You then add related models and customize the behavior of each by changing the parameters of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="d6301-115">Enfin, vous créez des prédictions et mettez à jour ces prédictions avec les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="d6301-115">Finally you create predictions and update the predictions with new data.</span></span> <span data-ttu-id="d6301-116">La possibilité de mettre à jour une série chronologique tout en faisant des prédictions a été ajoutée dans [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6301-116">The ability to update a time series while making predictions was added in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d6301-117">Informations de référence</span><span class="sxs-lookup"><span data-stu-id="d6301-117">Reference</span></span>  
 [<span data-ttu-id="d6301-118">Algorithmes d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d6301-118">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="d6301-119">Référence DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="d6301-119">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
## <a name="related-sections"></a><span data-ttu-id="d6301-120">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="d6301-120">Related Sections</span></span>  
  
-   [<span data-ttu-id="d6301-121">Didacticiel d’exploration de données de base</span><span class="sxs-lookup"><span data-stu-id="d6301-121">Basic Data Mining Tutorial</span></span>](../../2014/tutorials/basic-data-mining-tutorial.md)  
  
     <span data-ttu-id="d6301-122">Ce didacticiel introduit des concepts de base, tels que la procédure de création d'un projet et de génération de structures et de modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d6301-122">This tutorial introduces basic concepts, such as how to create a project and how to build mining structures and mining models.</span></span>  
  
-   [<span data-ttu-id="d6301-123">Didacticiel sur l’exploration de données intermédiaire &#40;Analysis Services d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d6301-123">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
     <span data-ttu-id="d6301-124">Ce didacticiel contient plusieurs leçons indépendantes, chacune d'elle vous initiant à un type de modèle différent.</span><span class="sxs-lookup"><span data-stu-id="d6301-124">This tutorial contains a number of independent lessons, each introducing you to a different model type.</span></span> <span data-ttu-id="d6301-125">Chaque leçon vous guide dans le processus de création d'un modèle, l'exploration du modèle, puis la personnalisation du modèle et la création de requêtes de prédiction.</span><span class="sxs-lookup"><span data-stu-id="d6301-125">Each lesson walks you through the process of creating a model, exploring the model, and then customizing the model and creating prediction queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6301-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6301-126">See Also</span></span>  
 <span data-ttu-id="d6301-127">[Solutions d’exploration de données](../../2014/analysis-services/data-mining/data-mining-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="d6301-127">[Data Mining Solutions](../../2014/analysis-services/data-mining/data-mining-solutions.md) </span></span>  
 <span data-ttu-id="d6301-128">[Outils d’exploration de données](../../2014/analysis-services/data-mining/data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d6301-128">[Data Mining Tools](../../2014/analysis-services/data-mining/data-mining-tools.md) </span></span>  
 [<span data-ttu-id="d6301-129">Projets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="d6301-129">Data Mining Projects</span></span>](../../2014/analysis-services/data-mining/data-mining-projects.md)  
  
  
