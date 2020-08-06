---
title: Propriétés OLAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- AggregationPerfLog property
- DefaultPageSizeForProp property
- UseSinglePassForDimSecurityAutoExist property
- DeepCompressValue property
- CacheRowsetRows property
- Income property
- AggregationNewAlgo property
- MemoryAdjustFactor property
- DimensionLatencyAccuracy property
- InitialBonus property
- DefaultPageSizeForDataHeader property
- MaxCPUUsage property
- DistinctBuffer property
- PartitionLatencyAccuracy property
- MaxRetries property
- UseDataCacheRegistryMultiplyKey property
- ConvertDeletedToUnknown property
- DatabaseConnectionPoolMax property
- DataFileInitEnabled property
- DefaultPageSizeForHash property
- MaxRolapOrConditions property
- UseDataCacheFreeLastPageMemory property
- OLAP [Analysis Services], properties
- MapHandleAlgorithm property
- IndexBuildEnabled property
- MaxObjectsInParallel property
- IgnoreNullRolapRows property
- DimensionPropertyCacheSize property
- DefaultRefreshInterval property
- CheckDistinctRecordSortOrder property
- BufferMemoryLimit property
- EnableTableGrouping property
- ExpressNonEmptyUseEnabled property
- CopyLinkedDataCacheAndRegistry property
- UseDataSlice property
- MemoryLimitErrorEnabled property
- Enabled property
- EnableRolapOptimization property
- DatabaseConnectionPoolTimeout property
- UseDataCacheRegistryHashTable property
- AggregationsBuildEnabled property
- Tax property
- DatabaseConnectionPoolGeneralTimeout property
- DefaultPageSizeForString property
- DatabaseConnectionPoolConnectTimeout property
- MinimumBalance property
- OptimizeSchema property
- UseCalculationCacheRegistry property
- MaxTableDepth property
- DataSliceInitEnabled property
- PrefetchLowerGranularities property
- UseVBANet property
- BufferRecordLimit property
- DefaultPageSizeForIndexHeader property
- MaximumBalance property
- CalculationCacheRegistryMaxIterations property
- DefaultDrillthroughMaxRows property
- IndexBuildThreshold property
- UseDataCacheRegistry property
- MemoryAdjustConst property
- ApplyIntersect property
- IndexFileInitEnabled property
- CacheRowsetToDisk property
- DataCacheRegistryMaxIterations property
- AllowSEFiltering property
- ForceMultiPass property
- ApplySubtract property
- IndexUseEnabled property
- AggregationsUseEnabled property
- DataPlacementOptimization property
- UseMaterializedIterators property
- CacheRecordLimit property
- ROLAPDimensionProcessingEffort property
- DefaultPageSizeForIndex property
- EnableRolapDimQueryTableGrouping property
- DimensionPropertyKeyCache property
- SleepIntervalSecs property
- DefaultPageSizeForData property
- MapFormatMask property
- CalculationEvaluationPolicy property
- AggregationMemoryLimitMin property
- RecordsReportGranularity property
- MemoryLimit property
- AggregationMemoryLimitMax property
ms.assetid: 06eb0d78-96c0-42ff-b759-f4c794597c8d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2eb89d318bfdb78935eb4d9f202db11b978c59b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604757"
---
# <a name="olap-properties"></a><span data-ttu-id="b64ef-102">Propriétés OLAP</span><span class="sxs-lookup"><span data-stu-id="b64ef-102">OLAP Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="b64ef-103">prend en charge les propriétés de serveur OLAP répertoriées dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="b64ef-103">supports the OLAP server properties listed in the following tables.</span></span> <span data-ttu-id="b64ef-104">Pour plus d'informations sur les autres propriétés de serveur et la façon de les configurer, consultez [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="b64ef-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="b64ef-105">**S’applique à :** Mode serveur multidimensionnel uniquement</span><span class="sxs-lookup"><span data-stu-id="b64ef-105">**Applies to:** Multidimensional server mode only</span></span>  
  
## <a name="memory"></a><span data-ttu-id="b64ef-106">Mémoire</span><span class="sxs-lookup"><span data-stu-id="b64ef-106">Memory</span></span>  
 `DefaultPageSizeForData`  
 <span data-ttu-id="b64ef-107">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-107">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForDataHeader`  
 <span data-ttu-id="b64ef-108">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-108">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForIndex`  
 <span data-ttu-id="b64ef-109">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForIndexHeader`  
 <span data-ttu-id="b64ef-110">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForString`  
 <span data-ttu-id="b64ef-111">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-111">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForHash`  
 <span data-ttu-id="b64ef-112">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-112">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForProp`  
 <span data-ttu-id="b64ef-113">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-113">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="lazyprocessing"></a><span data-ttu-id="b64ef-114">LazyProcessing</span><span class="sxs-lookup"><span data-stu-id="b64ef-114">LazyProcessing</span></span>  
 `Enabled`  
 <span data-ttu-id="b64ef-115">Propriété booléenne qui spécifie si le traitement différé des agrégations est activé.</span><span class="sxs-lookup"><span data-stu-id="b64ef-115">A Boolean property that specifies whether lazy aggregation processing is enabled.</span></span>  
  
 `SleepIntervalSecs`  
 <span data-ttu-id="b64ef-116">Propriété dont la valeur est un entier 32 bits signé qui définit l'intervalle, en secondes, en fonction duquel le serveur vérifie s'il y a des travaux de traitement différé en attente.</span><span class="sxs-lookup"><span data-stu-id="b64ef-116">A signed 32-bit integer property that defines the interval, in seconds, that the server checks whether there are lazy processing jobs pending.</span></span>  
  
 `MaxCPUUsage`  
 <span data-ttu-id="b64ef-117">Propriété dont la valeur est un nombre 64 bits signé en virgule flottante double précision qui définit sous la forme d'un pourcentage l'utilisation maximale de l'unité centrale pour les traitements différés.</span><span class="sxs-lookup"><span data-stu-id="b64ef-117">A signed 64-bit double-precision floating-point number property that defines maximum CPU usage for lazy processing, expressed as a percentage.</span></span> <span data-ttu-id="b64ef-118">Le serveur surveille l'utilisation moyenne de l'unité centrale en prenant des instantanés à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="b64ef-118">The server monitors average CPU use based on snapshots.</span></span> <span data-ttu-id="b64ef-119">Il est normal que l'unité centrale dépasse temporairement ce seuil lors des pointes d'activité.</span><span class="sxs-lookup"><span data-stu-id="b64ef-119">It is normal behavior for the CPU to spike above this threshold.</span></span>  
  
 <span data-ttu-id="b64ef-120">La valeur par défaut de cette propriété, 0,5, indique qu'un maximum de 50 % de l'unité centrale sera consacré au traitement différé.</span><span class="sxs-lookup"><span data-stu-id="b64ef-120">The default value for this property is 0.5, indicating a maximum of 50% of the CPU will be devoted to lazy processing.</span></span>  
  
 `MaxObjectsInParallel`  
 <span data-ttu-id="b64ef-121">Propriété dont la valeur est un entier 32 bits signé qui spécifie le nombre maximal de partitions pouvant faire l'objet d'un traitement différé en parallèle.</span><span class="sxs-lookup"><span data-stu-id="b64ef-121">A signed 32-bit integer property that specifies the maximum number of partitions that can be lazily processed in parallel.</span></span>  
  
 `MaxRetries`  
 <span data-ttu-id="b64ef-122">Propriété dont la valeur est un entier 32 bits signé qui définit le nombre de nouvelles tentatives en cas d'échec du traitement en différé avant qu'une erreur ne soit déclenchée.</span><span class="sxs-lookup"><span data-stu-id="b64ef-122">A signed 32-bit integer property that defines the number of retries in the event that lazy processing fails before an error is raised.</span></span>  
  
## <a name="processplan"></a><span data-ttu-id="b64ef-123">ProcessPlan</span><span class="sxs-lookup"><span data-stu-id="b64ef-123">ProcessPlan</span></span>  
 `CacheRowsetRows`  
 <span data-ttu-id="b64ef-124">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-124">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CacheRowsetToDisk`  
 <span data-ttu-id="b64ef-125">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-125">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DistinctBuffer`  
 <span data-ttu-id="b64ef-126">Propriété dont la valeur est un entier 32 bits signé qui définit la taille d'une mémoire tampon interne utilisée pour les comptages de valeurs.</span><span class="sxs-lookup"><span data-stu-id="b64ef-126">A signed 32-bit integer property that defines the size of an internal buffer used for distinct counts.</span></span> <span data-ttu-id="b64ef-127">Augmentez cette valeur si vous souhaitez accélérer le traitement du comptage de valeurs au prix d'une plus grande consommation de mémoire.</span><span class="sxs-lookup"><span data-stu-id="b64ef-127">Increase this value to speed up distinct count processing at the cost of memory use.</span></span>  
  
 `EnableRolapDimQueryTableGrouping`  
 <span data-ttu-id="b64ef-128">Propriété booléenne qui spécifie si le regroupement de tables est activé pour les dimensions ROLAP.</span><span class="sxs-lookup"><span data-stu-id="b64ef-128">A Boolean property that specifies whether table grouping is enabled for ROLAP dimensions.</span></span> <span data-ttu-id="b64ef-129">Si sa valeur est True, lors de l'extraction des dimensions ROLAP au moment de l'exécution, les tables de dimension ROLAP sont consultées en entier immédiatement, au lieu d'utiliser des requêtes distinctes pour chaque attribut.</span><span class="sxs-lookup"><span data-stu-id="b64ef-129">If True, when querying ROLAP dimensions at runtime, entire ROLAP dimension tables are queried at once, as opposed to separate queries for each attribute.</span></span>  
  
 `EnableTableGrouping`  
 <span data-ttu-id="b64ef-130">Propriété booléenne qui spécifie si le regroupement de tables est activé.</span><span class="sxs-lookup"><span data-stu-id="b64ef-130">A Boolean property that specifies whether table grouping is enabled.</span></span> <span data-ttu-id="b64ef-131">Si sa valeur est True, lors du traitement des dimensions, les tables de dimension sont consultées en entier immédiatement, au lieu d'utiliser des requêtes distinctes pour chaque attribut.</span><span class="sxs-lookup"><span data-stu-id="b64ef-131">If True, when processing dimensions, entire dimension tables are queried at once, as opposed to separate queries for each attribute.</span></span>  
  
 `ForceMultiPass`  
 <span data-ttu-id="b64ef-132">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-132">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxTableDepth`  
 <span data-ttu-id="b64ef-133">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-133">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryAdjustConst`  
 <span data-ttu-id="b64ef-134">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-134">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryAdjustFactor`  
 <span data-ttu-id="b64ef-135">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-135">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryLimit`  
 <span data-ttu-id="b64ef-136">Propriété dont la valeur est un nombre 64 bits signé en virgule flottante double précision qui définit la capacité de mémoire maximale à consacrer au traitement, exprimée en pourcentage de la mémoire physique.</span><span class="sxs-lookup"><span data-stu-id="b64ef-136">A signed 64-bit double-precision floating-point number property that defines the maximum amount of memory to be devoted to processing, expressed as a percentage of physical memory.</span></span>  
  
 <span data-ttu-id="b64ef-137">La valeur par défaut de cette propriété, 65, indique que 65 % de la mémoire physique peut être consacrée au traitement des cubes et des dimensions.</span><span class="sxs-lookup"><span data-stu-id="b64ef-137">The default value for this property is 65, indicating that 65% of physical memory may be devoted to cube and dimension processing.</span></span>  
  
 `MemoryLimitErrorEnabled`  
 <span data-ttu-id="b64ef-138">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-138">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `OptimizeSchema`  
 <span data-ttu-id="b64ef-139">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-139">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="proactivecaching"></a><span data-ttu-id="b64ef-140">ProactiveCaching</span><span class="sxs-lookup"><span data-stu-id="b64ef-140">ProactiveCaching</span></span>  
 `DefaultRefreshInterval`  
 <span data-ttu-id="b64ef-141">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DimensionLatencyAccuracy`  
 <span data-ttu-id="b64ef-142">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PartitionLatencyAccuracy`  
 <span data-ttu-id="b64ef-143">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-143">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="process"></a><span data-ttu-id="b64ef-144">Process</span><span class="sxs-lookup"><span data-stu-id="b64ef-144">Process</span></span>  
 `AggregationMemoryLimitMax`  
 <span data-ttu-id="b64ef-145">Propriété dont la valeur est un nombre 64 bits signé en virgule flottante double précision qui définit la capacité de mémoire maximale pouvant être consacrée au traitement des agrégations, exprimée en pourcentage de la mémoire physique.</span><span class="sxs-lookup"><span data-stu-id="b64ef-145">A signed 64-bit double-precision floating-point number property that defines the maximum amount of memory that can be devoted to aggregation processing, expressed as a percentage of physical memory.</span></span>  
  
 <span data-ttu-id="b64ef-146">La valeur par défaut de cette propriété, 80, indique que 80 % de la mémoire physique peut être consacrée au traitement des agrégations.</span><span class="sxs-lookup"><span data-stu-id="b64ef-146">The default value for this property is 80, indicating that 80% of physical memory may be devoted to aggregation processing.</span></span>  
  
 `AggregationMemoryLimitMin`  
 <span data-ttu-id="b64ef-147">Propriété dont la valeur est un nombre 64 bits signé en virgule flottante double précision qui définit la capacité de mémoire minimale pouvant être consacrée au traitement des agrégations, exprimée en pourcentage de la mémoire physique.</span><span class="sxs-lookup"><span data-stu-id="b64ef-147">A signed 64-bit double-precision floating-point number property that defines the minimum amount of memory that can be devoted to aggregation processing, expressed as a percentage of physical memory.</span></span> <span data-ttu-id="b64ef-148">Une valeur supérieure est susceptible d'accélérer le traitement des agrégations au prix d'une plus grande consommation de mémoire.</span><span class="sxs-lookup"><span data-stu-id="b64ef-148">A larger value may speed up aggregation processing at the cost of memory usage.</span></span>  
  
 <span data-ttu-id="b64ef-149">La valeur par défaut de cette propriété, 10, indique qu'un minimum de 10 % de la mémoire physique sera consacré au traitement des agrégations.</span><span class="sxs-lookup"><span data-stu-id="b64ef-149">The default value for this property is 10, indicating that minimally 10% of physical memory will be devoted to aggregation processing.</span></span>  
  
 `AggregationNewAlgo`  
 <span data-ttu-id="b64ef-150">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `AggregationPerfLog2`  
 <span data-ttu-id="b64ef-151">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `AggregationsBuildEnabled`  
 <span data-ttu-id="b64ef-152">Propriété booléenne qui spécifie si la génération d'agrégations est activée.</span><span class="sxs-lookup"><span data-stu-id="b64ef-152">A Boolean property that specifies whether aggregation building is enabled.</span></span> <span data-ttu-id="b64ef-153">Il s'agit d'un mécanisme permettant de tester les performances de la génération d'agrégations sans modifier la conception des agrégations.</span><span class="sxs-lookup"><span data-stu-id="b64ef-153">This is a mechanism to benchmark aggregation building without changing aggregation design.</span></span>  
  
 `BufferMemoryLimit`  
 <span data-ttu-id="b64ef-154">Propriété dont la valeur est un nombre 64 bits signé en virgule flottante double précision qui définit la limite de la mémoire tampon de traitement, exprimée en pourcentage de la mémoire physique.</span><span class="sxs-lookup"><span data-stu-id="b64ef-154">A signed 64-bit double-precision floating-point number property that defines the processing buffer memory limit, expressed as a percent of physical memory.</span></span>  
  
 <span data-ttu-id="b64ef-155">La valeur par défaut de cette propriété, 60, indique qu'il est possible d'utiliser jusqu'à 60 % de la mémoire physique comme mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="b64ef-155">The default value for this property is 60, which indicates that up to 60% of physical memory can be used for buffer memory.</span></span>  
  
 `BufferRecordLimit`  
 <span data-ttu-id="b64ef-156">Propriété dont la valeur est un entier 32 bits signé qui définit le nombre d'enregistrements qu'il est possible de stocker en mémoire tampon durant le traitement.</span><span class="sxs-lookup"><span data-stu-id="b64ef-156">A signed 32-bit integer property that defines the number of records that can be buffered during processing.</span></span>  
  
 <span data-ttu-id="b64ef-157">La valeur par défaut de cette propriété est 1 048 576 (enregistrements).</span><span class="sxs-lookup"><span data-stu-id="b64ef-157">The default value for this property is 1048576 (records).</span></span>  
  
 `CacheRecordLimit`  
 <span data-ttu-id="b64ef-158">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-158">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CheckDistinctRecordSortOrder`  
 <span data-ttu-id="b64ef-159">Propriété booléenne qui définit si l'ordre de tri des résultats d'une requête de comptage de valeurs est significatif lors du traitement de partitions.</span><span class="sxs-lookup"><span data-stu-id="b64ef-159">A Boolean property that defines if the sort order for the results of a distinct count query are meaningful when processing partitions.</span></span> <span data-ttu-id="b64ef-160">La valeur True indique que l'ordre de tri n'est pas significatif et doit être « vérifié » par le serveur.</span><span class="sxs-lookup"><span data-stu-id="b64ef-160">True indicates the sort order is not meaningful and must be "checked" by the server.</span></span> <span data-ttu-id="b64ef-161">Lors du traitement des partitions avec une mesure de comptage de valeurs, une requête comportant une clause ORDER BY est envoyée à SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b64ef-161">When processing partitions with distinct count measure, query sent to SQL with order-by.</span></span> <span data-ttu-id="b64ef-162">Attribuez la valeur False à cette propriété si vous souhaitez accélérer le traitement.</span><span class="sxs-lookup"><span data-stu-id="b64ef-162">Set to false to speed up processing.</span></span>  
  
 <span data-ttu-id="b64ef-163">La valeur par défaut de cette propriété, True, indique que l'ordre de tri n'est pas significatif et doit être vérifié.</span><span class="sxs-lookup"><span data-stu-id="b64ef-163">The default value for this property is True, which indicates that the sort order is not meaningful and must be checked.</span></span>  
  
 `DatabaseConnectionPoolConnectTimeout`  
 <span data-ttu-id="b64ef-164">Propriété dont la valeur est un entier 32 bits signé qui spécifie le délai d'attente en secondes lors de l'ouverture d'une nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="b64ef-164">A signed 32-bit integer property that specifies timeout when opening a new connection in seconds.</span></span>  
  
 `DatabaseConnectionPoolGeneralTimeout`  
 <span data-ttu-id="b64ef-165">Propriété dont la valeur est un entier 32 bits signé qui spécifie le délai de connexion de base de données en secondes à utiliser avec les connexions OLEDB externes.</span><span class="sxs-lookup"><span data-stu-id="b64ef-165">A signed 32-bit integer property that specifies database connection timeout for use with external OLEDB connections in seconds.</span></span>  
  
 `DatabaseConnectionPoolMax`  
 <span data-ttu-id="b64ef-166">Propriété dont la valeur est un entier 32 bits signé qui spécifie le nombre maximal de connexions de base de données regroupées en pool.</span><span class="sxs-lookup"><span data-stu-id="b64ef-166">A signed 32-bit integer property that specifies the maximum number of pooled database connections.</span></span>  
  
 <span data-ttu-id="b64ef-167">La valeur par défaut de cette propriété est 50 (connexions).</span><span class="sxs-lookup"><span data-stu-id="b64ef-167">The default value for this property is 50 (connections).</span></span>  
  
 `DatabaseConnectionPoolTimeout`  
 <span data-ttu-id="b64ef-168">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-168">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataFileInitEnabled`  
 <span data-ttu-id="b64ef-169">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-169">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataPlacementOptimization`  
 <span data-ttu-id="b64ef-170">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-170">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataSliceInitEnabled`  
 <span data-ttu-id="b64ef-171">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-171">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DeepCompressValue`  
 <span data-ttu-id="b64ef-172">Propriété booléenne s'appliquant aux mesures avec le type de données Double qui spécifie si les nombres peuvent être compressés, ce qui entraîne une perte de précision numérique.</span><span class="sxs-lookup"><span data-stu-id="b64ef-172">A Boolean property applying to measures with Double data type that specifies whether numbers can be compressed, causing a loss in numeric precision.</span></span> <span data-ttu-id="b64ef-173">La valeur False indique l'absence de compression et la conservation de la précision.</span><span class="sxs-lookup"><span data-stu-id="b64ef-173">A value of False indicates no compression and no precision loss.</span></span>  
  
 <span data-ttu-id="b64ef-174">La valeur par défaut de cette propriété, True, indique que la compression est activée au détriment de la précision.</span><span class="sxs-lookup"><span data-stu-id="b64ef-174">The default value for this property is True, which indicates that compression is enabled and precision will be lost.</span></span>  
  
 `DimensionPropertyKeyCache`  
 <span data-ttu-id="b64ef-175">Propriété booléenne qui spécifie si les clés de propriété de dimension sont stockées en cache.</span><span class="sxs-lookup"><span data-stu-id="b64ef-175">A Boolean property that specifies whether dimension property keys are cached.</span></span> <span data-ttu-id="b64ef-176">Cette propriété doit avoir la valeur True si les clés ne sont pas uniques.</span><span class="sxs-lookup"><span data-stu-id="b64ef-176">Must be set to True if keys are non-unique.</span></span>  
  
 `IndexBuildEnabled`  
 <span data-ttu-id="b64ef-177">Propriété booléenne qui spécifie si les index sont générés lors du traitement.</span><span class="sxs-lookup"><span data-stu-id="b64ef-177">A Boolean property that specifies whether indexes are built upon processing.</span></span> <span data-ttu-id="b64ef-178">Cette propriété sert à tester les performances et à informer.</span><span class="sxs-lookup"><span data-stu-id="b64ef-178">This property is for benchmarking and informational purposes.</span></span>  
  
 `IndexBuildThreshold`  
 <span data-ttu-id="b64ef-179">Propriété dont la valeur est un entier 32 bits signé qui spécifie un seuil, exprimé en nombre de lignes, en dessous duquel les index ne seront pas générés pour les partitions.</span><span class="sxs-lookup"><span data-stu-id="b64ef-179">A signed 32-bit integer property that specifies a row count threshold below which indexes will not be built for partitions.</span></span>  
  
 <span data-ttu-id="b64ef-180">La valeur par défaut de cette propriété est 4 096 (lignes).</span><span class="sxs-lookup"><span data-stu-id="b64ef-180">The default value for this property is 4096 (rows).</span></span>  
  
 `IndexFileInitEnabled`  
 <span data-ttu-id="b64ef-181">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-181">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MapFormatMask`  
 <span data-ttu-id="b64ef-182">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-182">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RecordsReportGranularity`  
 <span data-ttu-id="b64ef-183">Propriété dont la valeur est un entier 32 bits signé qui spécifie la périodicité, exprimée en nombre de lignes, selon laquelle le serveur enregistre les événements Trace durant le traitement.</span><span class="sxs-lookup"><span data-stu-id="b64ef-183">A signed 32-bit integer property that specifies how often the server records Trace events during processing, in rows.</span></span>  
  
 <span data-ttu-id="b64ef-184">La valeur par défaut de cette propriété, 1 000, indique qu'un événement Trace est enregistré toutes les 1 000 lignes.</span><span class="sxs-lookup"><span data-stu-id="b64ef-184">The default value for this property is 1000, which indicates that a Trace event is logged once every 1000 rows.</span></span>  
  
 `ROLAPDimensionProcessingEffort`  
 <span data-ttu-id="b64ef-185">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-185">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="query"></a><span data-ttu-id="b64ef-186">Query</span><span class="sxs-lookup"><span data-stu-id="b64ef-186">Query</span></span>  
 `AggregationsUseEnabled`  
 <span data-ttu-id="b64ef-187">Propriété booléenne qui définit si les agrégations stockées sont utilisées au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="b64ef-187">A Boolean property that defines whether stored aggregations are used at runtime.</span></span> <span data-ttu-id="b64ef-188">Cette propriété permet de désactiver les agrégations sans qu'il soit nécessaire de modifier leur conception ou de les retraiter, par exemple dans un but informatif ou pour tester les performances.</span><span class="sxs-lookup"><span data-stu-id="b64ef-188">This property allows aggregations to be disabled without changing the aggregation design or re-processing, for informational and benchmarking purposes.</span></span>  
  
 <span data-ttu-id="b64ef-189">La valeur par défaut de cette propriété, True, indique que les agrégations sont activées.</span><span class="sxs-lookup"><span data-stu-id="b64ef-189">The default value for this property is True, indicating that aggregations are enabled.</span></span>  
  
 `AllowSEFiltering`  
 <span data-ttu-id="b64ef-190">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-190">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationCacheRegistryMaxIterations`  
 <span data-ttu-id="b64ef-191">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-191">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationEvaluationPolicy`  
 <span data-ttu-id="b64ef-192">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-192">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ConvertDeletedToUnknown`  
 <span data-ttu-id="b64ef-193">Propriété booléenne qui spécifie si les membres de dimension supprimés sont convertis en membres inconnus.</span><span class="sxs-lookup"><span data-stu-id="b64ef-193">A Boolean property that specifies whether deleted dimension members are converted to Unknown member.</span></span>  
  
 `CopyLinkedDataCacheAndRegistry`  
 <span data-ttu-id="b64ef-194">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-194">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCacheRegistryMaxIterations`  
 <span data-ttu-id="b64ef-195">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-195">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultDrillthroughMaxRows`  
 <span data-ttu-id="b64ef-196">Propriété dont la valeur est un entier 32 bits signé qui spécifie le nombre maximal de lignes qui seront renvoyées par une requête qui effectue une extraction.</span><span class="sxs-lookup"><span data-stu-id="b64ef-196">A signed 32-bit integer property that specifies the maximum number of rows that will return from a drill-through query.</span></span>  
  
 <span data-ttu-id="b64ef-197">La valeur par défaut de cette propriété est 10 000 (lignes).</span><span class="sxs-lookup"><span data-stu-id="b64ef-197">The default value for this property is 10000 (rows).</span></span>  
  
 `DimensionPropertyCacheSize`  
 <span data-ttu-id="b64ef-198">Propriété dont la valeur est un entier 32 bits signé qui spécifie la quantité de mémoire (en octets) utilisée pour mettre en cache les membres de dimension utilisés dans une requête.</span><span class="sxs-lookup"><span data-stu-id="b64ef-198">A signed 32-bit integer property that specifies the amount of memory (in bytes) used to cache dimension members used in a query.</span></span>  
  
 <span data-ttu-id="b64ef-199">La valeur par défaut est 4 000 000 octets (ou 4 Mo) par hiérarchie d'attribut, par requête active.</span><span class="sxs-lookup"><span data-stu-id="b64ef-199">The default is 4,000,000 bytes (or 4 MB) per attribute hierarchy, per active query.</span></span> <span data-ttu-id="b64ef-200">La valeur par défaut fournit une taille de cache bien équilibrée pour les solutions comportant des hiérarchies standard.</span><span class="sxs-lookup"><span data-stu-id="b64ef-200">The default value provides a well-balanced cache size for solutions having typical hierarchies.</span></span> <span data-ttu-id="b64ef-201">Toutefois, les dimensions avec un grand nombre de membres (des millions) ou des hiérarchies profondes offrent de meilleures performances si vous augmentez cette valeur.</span><span class="sxs-lookup"><span data-stu-id="b64ef-201">However, dimensions with a very large number of members (in the millions) or deep hierarchies perform better if you increase this value.</span></span>  
  
 <span data-ttu-id="b64ef-202">Impact de l'augmentation de la taille du cache :</span><span class="sxs-lookup"><span data-stu-id="b64ef-202">Implications of increasing cache size:</span></span>  
  
-   <span data-ttu-id="b64ef-203">Les coûts d'utilisation de la mémoire augmentent lorsque vous autorisez l'utilisation de davantage de mémoire par le cache de dimension.</span><span class="sxs-lookup"><span data-stu-id="b64ef-203">Memory utilization costs increase when you allow more memory to be used by the dimension cache.</span></span> <span data-ttu-id="b64ef-204">L'utilisation réelle dépend de l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="b64ef-204">Actual usage depends on query execution.</span></span> <span data-ttu-id="b64ef-205">Certaines requêtes n'utilisent pas la quantité maximale autorisée.</span><span class="sxs-lookup"><span data-stu-id="b64ef-205">Not all queries will use the allowable maximum.</span></span>  
  
     <span data-ttu-id="b64ef-206">Notez que la mémoire utilisée par ces caches est considérée comme non réductible et est incluse dans la propriété **TotalMemoryLimit**.</span><span class="sxs-lookup"><span data-stu-id="b64ef-206">Note that the memory used by these caches is considered nonshrinkable and will be included when accounting against the **TotalMemoryLimit**.</span></span>  
  
-   <span data-ttu-id="b64ef-207">Affecte toutes les bases de données sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b64ef-207">Affects all databases on the server.</span></span> <span data-ttu-id="b64ef-208">**DimensionPropertyCachesize** est une propriété à l’échelle du serveur.</span><span class="sxs-lookup"><span data-stu-id="b64ef-208">**DimensionPropertyCachesize** is a server-wide property.</span></span> <span data-ttu-id="b64ef-209">La modification de cette propriété affecte toutes les bases de données exécutées sur l'instance actuelle.</span><span class="sxs-lookup"><span data-stu-id="b64ef-209">Changing this property affects all databases running on the current instance.</span></span>  
  
 <span data-ttu-id="b64ef-210">Approche pour estimer la configuration requise du cache de dimension :</span><span class="sxs-lookup"><span data-stu-id="b64ef-210">Approach for estimating dimension cache requirements:</span></span>  
  
1.  <span data-ttu-id="b64ef-211">Commencez par augmenter la taille en entrant un grand nombre pour déterminer si l'augmentation de la taille du cache de dimension présente un avantage.</span><span class="sxs-lookup"><span data-stu-id="b64ef-211">Start by increasing the size by a large number to determine whether there is a benefit to increasing the dimension cache size.</span></span> <span data-ttu-id="b64ef-212">Par exemple, doublez la valeur par défaut lors de l'étape initiale.</span><span class="sxs-lookup"><span data-stu-id="b64ef-212">For example, you might want to double the default value as an initial step.</span></span>  
  
2.  <span data-ttu-id="b64ef-213">Si une amélioration des performances est visible, réduisez la valeur de manière incrémentielle jusqu'à ce qu'un équilibre entre les performances et l'utilisation de la mémoire soit atteint.</span><span class="sxs-lookup"><span data-stu-id="b64ef-213">If a performance improvement is evident, incrementally reduce the value until you reach a balance between performance and memory utilization.</span></span>  
  
 `ExpressNonEmptyUseEnabled`  
 <span data-ttu-id="b64ef-214">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-214">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `IgnoreNullRolapRows`  
 <span data-ttu-id="b64ef-215">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-215">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `IndexUseEnabled`  
 <span data-ttu-id="b64ef-216">Propriété booléenne qui définit si les index sont utilisés au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="b64ef-216">A Boolean property that defines whether indexes are used at runtime.</span></span> <span data-ttu-id="b64ef-217">Cette propriété sert à tester les performances et à informer.</span><span class="sxs-lookup"><span data-stu-id="b64ef-217">This property is for informational and benchmarking purposes.</span></span>  
  
 `MapHandleAlgorithm`  
 <span data-ttu-id="b64ef-218">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-218">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxRolapOrConditions`  
 <span data-ttu-id="b64ef-219">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-219">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseCalculationCacheRegistry`  
 <span data-ttu-id="b64ef-220">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-220">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataCacheFreeLastPageMemory`  
 <span data-ttu-id="b64ef-221">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-221">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataCacheRegistry`  
 <span data-ttu-id="b64ef-222">Propriété booléenne qui spécifie s'il faut activer le registre du cache des données, où les résultats (non calculés) des requêtes sont mis en cache.</span><span class="sxs-lookup"><span data-stu-id="b64ef-222">A Boolean property that specifies whether to enable the data cache registry, where query results are cached (though not calculated results).</span></span>  
  
 `UseDataCacheRegistryHashTable`  
 <span data-ttu-id="b64ef-223">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-223">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataCacheRegistryMultiplyKey`  
 <span data-ttu-id="b64ef-224">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-224">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataSlice`  
 <span data-ttu-id="b64ef-225">Propriété booléenne qui définit si les tranches de données de partition sont utilisées au moment de l'exécution pour l'optimisation des requêtes.</span><span class="sxs-lookup"><span data-stu-id="b64ef-225">A Boolean property that defines whether to use partition data slices at runtime for query optimization.</span></span> <span data-ttu-id="b64ef-226">Cette propriété sert à tester les performances et à informer.</span><span class="sxs-lookup"><span data-stu-id="b64ef-226">This property is for benchmarking and informational purposes.</span></span>  
  
 `UseMaterializedIterators`  
 <span data-ttu-id="b64ef-227">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-227">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseSinglePassForDimSecurityAutoExist`  
 <span data-ttu-id="b64ef-228">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-228">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseVBANet`  
 <span data-ttu-id="b64ef-229">Propriété booléenne qui définit si l'assembly .net VBA doit être utilisé pour les fonctions définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b64ef-229">A Boolean property that defines whether to use the VBA .net assembly for user-defined functions.</span></span>  
  
 `CalculationPrefetchLocality\ ApplyIntersect`  
 <span data-ttu-id="b64ef-230">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-230">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationPrefetchLocality\ ApplySubtract`  
 <span data-ttu-id="b64ef-231">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-231">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationPrefetchLocality\ PrefetchLowerGranularities`  
 <span data-ttu-id="b64ef-232">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-232">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ Income`  
 <span data-ttu-id="b64ef-233">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-233">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ InitialBonus`  
 <span data-ttu-id="b64ef-234">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-234">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ MaximumBalance`  
 <span data-ttu-id="b64ef-235">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-235">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ MinimumBalance`  
 <span data-ttu-id="b64ef-236">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-236">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ Tax`  
 <span data-ttu-id="b64ef-237">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-237">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ Income`  
 <span data-ttu-id="b64ef-238">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-238">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ InitialBonus`  
 <span data-ttu-id="b64ef-239">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-239">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ MaximumBalance`  
 <span data-ttu-id="b64ef-240">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-240">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ MinimumBalance`  
 <span data-ttu-id="b64ef-241">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-241">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ Tax`  
 <span data-ttu-id="b64ef-242">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-242">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ Income`  
 <span data-ttu-id="b64ef-243">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-243">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ InitialBonus`  
 <span data-ttu-id="b64ef-244">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-244">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ MaximumBalance`  
 <span data-ttu-id="b64ef-245">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-245">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ MinimumBalance`  
 <span data-ttu-id="b64ef-246">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-246">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel\ Tax`  
 <span data-ttu-id="b64ef-247">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-247">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="jobs"></a><span data-ttu-id="b64ef-248">travaux</span><span class="sxs-lookup"><span data-stu-id="b64ef-248">Jobs</span></span>  
 `ProcessAggregation\ MemoryModel\ Income`  
 <span data-ttu-id="b64ef-249">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-249">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ InitialBonus`  
 <span data-ttu-id="b64ef-250">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-250">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ MaximumBalance`  
 <span data-ttu-id="b64ef-251">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-251">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ MinimumBalance`  
 <span data-ttu-id="b64ef-252">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-252">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ Tax`  
 <span data-ttu-id="b64ef-253">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-253">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition\ Income`  
 <span data-ttu-id="b64ef-254">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-254">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ InitialBonus`  
 <span data-ttu-id="b64ef-255">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-255">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ MaximumBalance`  
 <span data-ttu-id="b64ef-256">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-256">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ MinimumBalance`  
 <span data-ttu-id="b64ef-257">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-257">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ Tax`  
 <span data-ttu-id="b64ef-258">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-258">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ Income`  
 <span data-ttu-id="b64ef-259">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-259">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ InitialBonus`  
 <span data-ttu-id="b64ef-260">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-260">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ MaximumBalance`  
 <span data-ttu-id="b64ef-261">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-261">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ MinimumBalance`  
 <span data-ttu-id="b64ef-262">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-262">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ Tax`  
 <span data-ttu-id="b64ef-263">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b64ef-263">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64ef-264">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b64ef-264">See Also</span></span>  
 <span data-ttu-id="b64ef-265">[Configurer les propriétés du serveur dans Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="b64ef-265">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="b64ef-266">Déterminer le mode serveur d'une instance Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b64ef-266">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
