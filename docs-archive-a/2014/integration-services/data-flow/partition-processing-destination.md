---
title: Destination de traitement de partition | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partitionprocessingdest.f1
helpviewer_keywords:
- partitions [Analysis Services], processing
- Partition Processing destination [Integration Services]
- destinations [Integration Services], Partition Processing
ms.assetid: 36c592ff-3f78-4a58-b496-31c1c8eee131
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d32306328f7a0575e55397d5209b4767d0cf1bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602922"
---
# <a name="partition-processing-destination"></a><span data-ttu-id="68787-102">Destination de traitement de partition</span><span class="sxs-lookup"><span data-stu-id="68787-102">Partition Processing Destination</span></span>
  <span data-ttu-id="68787-103">La destination de traitement de partition charge et traite une partition [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68787-103">The Partition Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] partition.</span></span> <span data-ttu-id="68787-104">Pour plus d’informations sur les partitions, consultez [Partitions &#40;Analysis Services - Données multidimensionnelles&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="68787-104">For more information about partitions, see [Partitions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="68787-105">La destination de traitement de partition regroupe les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="68787-105">The Partition Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="68787-106">options permettant de choisir entre un traitement incrémentiel, un traitement complet ou un traitement de mise à jour ;</span><span class="sxs-lookup"><span data-stu-id="68787-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="68787-107">configuration d'erreur permettant de spécifier si le traitement ignore les erreurs ou s'arrête après un nombre spécifique d'erreurs ;</span><span class="sxs-lookup"><span data-stu-id="68787-107">Error configuration, to specify whether processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="68787-108">mappage des colonnes d'entrée aux colonnes de partition.</span><span class="sxs-lookup"><span data-stu-id="68787-108">Mapping of input columns to partition columns.</span></span>  
  
 <span data-ttu-id="68787-109">Pour plus d’informations sur le traitement des objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consultez [Options et paramètres de traitement &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="68787-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68787-110">Les tâches décrites ici ne s’appliquent pas aux modèles tabulaires Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="68787-110">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="68787-111">Vous ne pouvez pas mapper des colonnes d’entrée aux colonnes de partition pour les modèles tabulaires.</span><span class="sxs-lookup"><span data-stu-id="68787-111">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="68787-112">Vous pouvez en revanche utiliser la tâche DDL d'exécution [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) d'Analysis Services pour traiter la partition.</span><span class="sxs-lookup"><span data-stu-id="68787-112">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="configuration-of-the-partition-processing-destination"></a><span data-ttu-id="68787-113">Configuration de la destination de traitement de partition</span><span class="sxs-lookup"><span data-stu-id="68787-113">Configuration of the Partition Processing Destination</span></span>  
 <span data-ttu-id="68787-114">La destination de traitement de partition utilise un gestionnaire de connexions [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour se connecter au projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à l’instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui contient les cubes et partitions traités par la destination.</span><span class="sxs-lookup"><span data-stu-id="68787-114">The Partition Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the cubes and partitions the destination processes.</span></span> <span data-ttu-id="68787-115">Pour plus d'informations, consultez [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="68787-115">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="68787-116">Cette destination comporte une entrée.</span><span class="sxs-lookup"><span data-stu-id="68787-116">This destination has one input.</span></span> <span data-ttu-id="68787-117">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="68787-117">It does not support an error output.</span></span>  
  
 <span data-ttu-id="68787-118">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="68787-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="68787-119">Pour plus d’informations sur les propriétés pouvant être définies dans la boîte de dialogue **Éditeur de destination de traitement de partition** , cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="68787-119">For more information about the properties that you can set in the Partition Processing **Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="68787-120">Éditeur de destination de traitement de partition &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="68787-120">Partition Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../partition-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="68787-121">Éditeur de destination de traitement de partition &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="68787-121">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../partition-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="68787-122">Éditeur de destination de traitement de partition &#40;page Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="68787-122">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../partition-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="68787-123">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="68787-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="68787-124">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="68787-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="68787-125">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="68787-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="68787-126">Propriétés personnalisées de la destination de traitement de partition</span><span class="sxs-lookup"><span data-stu-id="68787-126">Partition Processing Destination Custom Properties</span></span>](partition-processing-destination-custom-properties.md)  
  
 <span data-ttu-id="68787-127">Pour plus d’informations sur la façon de définir des propriétés, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="68787-127">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
