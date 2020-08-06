---
title: Propriétés d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ClusterCount property
- AllowedProvidersInOpenRowset property
- MinimumSeriesValue property
- ScoreMethod property
- MinimumImportance property
- ModellingCardinality property
- BrentTolerance property
- ComplexityPenalty property
- MaximumItemsetCount property
- MinimumSupport property
- AllowSessionMiningModels property
- HoldoutPercentage property
- ClusterCountPrior property
- MaximumSequenceStates property
- OptimizedPredictionCount property
- data mining [Analysis Services], properties
- MaximumStates property
- MaximumContinuousInputAttributes property
- MaximumOutputAttributes property
- AllowAdHocOpenRowsetQueries property
- Enabled property
- HistoricModelGap property
- SampleSize property
- MaximumInputAttributes property
- PeriodicityHint property
- MissingValueSubstitution property
- SplitMethod property
- ForceRegressor property
- MaximumBucketsForContinuousSplit property
- MaxConcurrentPredictionQueries property
- MinimumItemsetSize property
- AcyclicGraph property
- HoldoutMethod property
- StoppingTolerance property
- properties [data mining]
- AutoDetectPeriodicity property
- HoldoutTolerance property
- MinimumLeafCases property
- HoldoutSeed property
- MinimumClusterCases property
- ClusterCountDeviation property
- MinimumDependencyProbability property
- ClusteringMethod property
- MaximumItemsetSize property
- HiddenNodeRatio property
- MaximumSeriesValue property
ms.assetid: 9bc9abed-180a-4bd8-b2eb-89c62fa88110
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ed1c47faafeb0c680e6afb6f8e509c426760da2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710868"
---
# <a name="data-mining-properties"></a><span data-ttu-id="1d88d-102">Propriétés de l'exploration de données</span><span class="sxs-lookup"><span data-stu-id="1d88d-102">Data Mining Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="1d88d-103">prend en charge les propriétés de serveur d'exploration de données répertoriées dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="1d88d-103">supports the data mining server properties listed in the following tables.</span></span> <span data-ttu-id="1d88d-104">Pour plus d'informations sur les autres propriétés de serveur et la façon de les configurer, consultez [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d88d-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="1d88d-105">**S’applique à :** Mode serveur multidimensionnel uniquement</span><span class="sxs-lookup"><span data-stu-id="1d88d-105">**Applies to:** Multidimensional server mode only</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="1d88d-106">Catégorie non spécifique</span><span class="sxs-lookup"><span data-stu-id="1d88d-106">Non-Specific Category</span></span>  
 `AllowSessionMiningModels`  
 <span data-ttu-id="1d88d-107">Propriété booléenne qui indique s'il est possible de créer des modèles d'exploration de données de session.</span><span class="sxs-lookup"><span data-stu-id="1d88d-107">A Boolean property that indicates whether session mining models can be created.</span></span>  
  
 <span data-ttu-id="1d88d-108">La valeur par défaut de cette propriété, False, indique qu'il n'est pas possible de créer des modèles d'exploration de session.</span><span class="sxs-lookup"><span data-stu-id="1d88d-108">The default value for this property is false, which indicates that session mining models cannot be created.</span></span>  
  
 `AllowAdHocOpenRowsetQueries`  
 <span data-ttu-id="1d88d-109">Propriété booléenne qui indique si les requêtes OPENROWSET ad hoc sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="1d88d-109">A Boolean property that indicates whether adhoc open rowset queries are allowed.</span></span>  
  
 <span data-ttu-id="1d88d-110">La valeur par défaut de cette propriété, False, indique que les requêtes OPENROWSET ne sont pas autorisées pendant une session.</span><span class="sxs-lookup"><span data-stu-id="1d88d-110">The default value for this property is false, which indicates that open rowset queries are not allowed during a session.</span></span>  
  
 `AllowedProvidersInOpenRowset`  
 <span data-ttu-id="1d88d-111">Propriété de type chaîne qui identifie les fournisseurs autorisés dans une clause OPENROWSET. Il s'agit soit d'une liste de ProgID séparés par des virgules, soit de [Tous].</span><span class="sxs-lookup"><span data-stu-id="1d88d-111">A string property that identifies which providers are allowed in an open rowset, consisting of a comma/semi-colon separated list of provider ProgIDs, or else [All].</span></span>  
  
 `MaxConcurrentPredictionQueries`  
 <span data-ttu-id="1d88d-112">Propriété dont la valeur est un entier 32 bits signé qui spécifie le nombre maximal de requêtes de prédiction simultanées.</span><span class="sxs-lookup"><span data-stu-id="1d88d-112">A signed 32-bit integer property that defines the maximum number of concurrent prediction queries.</span></span>  
  
## <a name="algorithms-category"></a><span data-ttu-id="1d88d-113">Catégorie algorithmes</span><span class="sxs-lookup"><span data-stu-id="1d88d-113">Algorithms Category</span></span>  
 `Microsoft_Association_Rules\ Enabled`  
 <span data-ttu-id="1d88d-114">Propriété booléenne qui indique si l'algorithme Microsoft_Association_Rules est activé.</span><span class="sxs-lookup"><span data-stu-id="1d88d-114">A Boolean property that indicates whether the Microsoft_Association_Rules algorithm is enabled.</span></span>  
  
 `Microsoft_Clustering\ Enabled`  
 <span data-ttu-id="1d88d-115">Propriété booléenne qui indique si l'algorithme Microsoft_Clustering est activé.</span><span class="sxs-lookup"><span data-stu-id="1d88d-115">A Boolean property that indicates whether the Microsoft_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Decision_Trees\ Enabled`  
 <span data-ttu-id="1d88d-116">Propriété booléenne qui indique si l'algorithme Microsoft_DecisionTrees est activé.</span><span class="sxs-lookup"><span data-stu-id="1d88d-116">A Boolean property that indicates whether the Microsoft_DecisionTrees algorithm is enabled.</span></span>  
  
 `Microsoft_Naive_Bayes\ Enabled`  
 <span data-ttu-id="1d88d-117">Propriété booléenne qui indique si l'algorithme Microsoft_Naive_Bayes est activé.</span><span class="sxs-lookup"><span data-stu-id="1d88d-117">A Boolean property that indicates whether the Microsoft_ Naive_Bayes algorithm is enabled.</span></span>  
  
 `Microsoft_Neural_Network\ Enabled`  
 <span data-ttu-id="1d88d-118">Propriété booléenne qui indique si l'algorithme Microsoft_Neural_Network est activé.</span><span class="sxs-lookup"><span data-stu-id="1d88d-118">A Boolean property that indicates whether the Microsoft_Neural_Network algorithm is enabled.</span></span>  
  
 `Microsoft_Sequence_Clustering\ Enabled`  
 <span data-ttu-id="1d88d-119">Propriété booléenne qui indique si l'algorithme Microsoft_Sequence_Clustering est activé.</span><span class="sxs-lookup"><span data-stu-id="1d88d-119">A Boolean property that indicates whether the Microsoft_Sequence_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Time_Series\ Enabled`  
 <span data-ttu-id="1d88d-120">Propriété booléenne qui indique si l'algorithme Microsoft_Time_Series est activé.</span><span class="sxs-lookup"><span data-stu-id="1d88d-120">A Boolean property that indicates whether the Microsoft_Time_Series algorithm is enabled.</span></span>  
  
 `Microsoft_Linear_Regression\ Enabled`  
 <span data-ttu-id="1d88d-121">Propriété booléenne qui indique si l'algorithme Microsoft_Linear_Regression est activé.</span><span class="sxs-lookup"><span data-stu-id="1d88d-121">A Boolean property that indicates whether the Microsoft_Linear_Regression algorithm is enabled.</span></span>  
  
 `Microsoft_Logistic_Regression\ Enabled`  
 <span data-ttu-id="1d88d-122">Propriété booléenne qui indique si l'algorithme Microsoft_Logistic_Regression est activé.</span><span class="sxs-lookup"><span data-stu-id="1d88d-122">A Boolean property that indicates whether the Microsoft_Logistic_Regression algorithm is enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d88d-123">En plus des propriétés qui définissent les services d'exploration de données disponibles sur le serveur, il existe des propriétés d'exploration de données définissant le comportement d'algorithmes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1d88d-123">In addition to properties that define the data mining services available on the server, there are data mining properties that define the behavior of specific algorithms.</span></span> <span data-ttu-id="1d88d-124">Vous configurez ces propriétés lorsque vous créez un modèle d'exploration de données individuel, pas au niveau serveur.</span><span class="sxs-lookup"><span data-stu-id="1d88d-124">You configure these properties when you create an individual data mining model, not at the server level.</span></span> <span data-ttu-id="1d88d-125">Pour plus d’informations, consultez [Algorithmes d’exploration de données &#40;Analysis Services - Exploration de données&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1d88d-125">For more information, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d88d-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d88d-126">See Also</span></span>  
 <span data-ttu-id="1d88d-127">[Architecture physique &#40;Analysis Services d’exploration de données&#41;](../data-mining/physical-architecture-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1d88d-127">[Physical Architecture &#40;Analysis Services - Data Mining&#41;](../data-mining/physical-architecture-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="1d88d-128">[Configurer les propriétés du serveur dans Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="1d88d-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="1d88d-129">Déterminer le mode serveur d'une instance Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1d88d-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
