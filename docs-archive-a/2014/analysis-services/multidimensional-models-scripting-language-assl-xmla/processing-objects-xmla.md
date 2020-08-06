---
title: Traitement d’objets (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- objects [XML for Analysis]
- XML for Analysis, objects
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
- writeback [Analysis Services], XML for Analysis
- out-of-line bindings
- processing objects [XML for Analysis]
- XMLA, objects
ms.assetid: a65b3249-303d-49c6-98af-6ac6eed11a03
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e59c7953ae8fc7d3cfceafa7b0e9d8c7186daf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706867"
---
# <a name="processing-objects-xmla"></a><span data-ttu-id="5da3d-102">Traitement d'objets (XMLA)</span><span class="sxs-lookup"><span data-stu-id="5da3d-102">Processing Objects (XMLA)</span></span>
  <span data-ttu-id="5da3d-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , le traitement est l’étape ou la série d’étapes qui transforment les données en informations pour l’analyse de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="5da3d-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], processing is the step or series of steps that turn data into information for business analysis.</span></span> <span data-ttu-id="5da3d-104">Si le traitement varie selon le type d'objet, le traitement consiste toujours à transformer des données en informations.</span><span class="sxs-lookup"><span data-stu-id="5da3d-104">Processing is different depending on the type of object, but processing is always part of turning data into information.</span></span>  
  
 <span data-ttu-id="5da3d-105">Pour traiter un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objet, vous pouvez utiliser la commande [traiter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="5da3d-105">To process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object, you can use the [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) command.</span></span> <span data-ttu-id="5da3d-106">La commande `Process` peut traiter les objets suivants dans une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="5da3d-106">The `Process` command can process the following objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance:</span></span>  
  
-   <span data-ttu-id="5da3d-107">Cubes</span><span class="sxs-lookup"><span data-stu-id="5da3d-107">Cubes</span></span>  
  
-   <span data-ttu-id="5da3d-108">Bases de données</span><span class="sxs-lookup"><span data-stu-id="5da3d-108">Databases</span></span>  
  
-   <span data-ttu-id="5da3d-109">Dimensions</span><span class="sxs-lookup"><span data-stu-id="5da3d-109">Dimensions</span></span>  
  
-   <span data-ttu-id="5da3d-110">les groupes de mesures ;</span><span class="sxs-lookup"><span data-stu-id="5da3d-110">Measure groups</span></span>  
  
-   <span data-ttu-id="5da3d-111">Modèles d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5da3d-111">Mining models</span></span>  
  
-   <span data-ttu-id="5da3d-112">Structures d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5da3d-112">Mining structures</span></span>  
  
-   <span data-ttu-id="5da3d-113">Partitions</span><span class="sxs-lookup"><span data-stu-id="5da3d-113">Partitions</span></span>  
  
 <span data-ttu-id="5da3d-114">Pour contrôler le traitement des objets, la commande `Process` propose plusieurs propriétés définissables.</span><span class="sxs-lookup"><span data-stu-id="5da3d-114">To control the processing of objects, the `Process` command has various properties that can be set.</span></span> <span data-ttu-id="5da3d-115">Les propriétés de la commande `Process` permettent de contrôler les éléments suivants : portée du traitement, types d'objets à traiter, utilisation ou non de liaisons hors ligne, gestion des erreurs et gestion des tables d'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="5da3d-115">The `Process` command has properties that control: how much processing will be done, which objects will be processed, whether to use out-of-line bindings, how to handle errors, and how to manage writeback tables.</span></span>  
  
## <a name="specifying-processing-options"></a><span data-ttu-id="5da3d-116">Spécification d'options de traitement</span><span class="sxs-lookup"><span data-stu-id="5da3d-116">Specifying Processing Options</span></span>  
 <span data-ttu-id="5da3d-117">La propriété [type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) de la `Process` commande spécifie l’option de traitement à utiliser lors du traitement de l’objet.</span><span class="sxs-lookup"><span data-stu-id="5da3d-117">The [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) property of the `Process` command specifies the processing option to use when processing the object.</span></span> <span data-ttu-id="5da3d-118">Pour plus d’informations sur les options de traitement, consultez [Options et paramètres de traitement &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="5da3d-118">For more information about processing options, see [Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span></span>  
  
 <span data-ttu-id="5da3d-119">Le tableau suivant répertorie les constantes associées à la propriété `Type` et les différents objets qui peuvent être traités avec chaque constant.</span><span class="sxs-lookup"><span data-stu-id="5da3d-119">The following table lists the constants for the `Type` property and the various objects that can be processed using each constant.</span></span>  
  
|<span data-ttu-id="5da3d-120">Valeur `Type`</span><span class="sxs-lookup"><span data-stu-id="5da3d-120">`Type` value</span></span>|<span data-ttu-id="5da3d-121">Objets applicables</span><span class="sxs-lookup"><span data-stu-id="5da3d-121">Applicable objects</span></span>|  
|--------------------|------------------------|  
|<span data-ttu-id="5da3d-122">*ProcessFull*</span><span class="sxs-lookup"><span data-stu-id="5da3d-122">*ProcessFull*</span></span>|<span data-ttu-id="5da3d-123">Cube, base de données, dimension, groupe de mesures, modèle d'exploration de données, structure d'exploration de données, partition</span><span class="sxs-lookup"><span data-stu-id="5da3d-123">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="5da3d-124">*ProcessAdd*</span><span class="sxs-lookup"><span data-stu-id="5da3d-124">*ProcessAdd*</span></span>|<span data-ttu-id="5da3d-125">Dimension, partition</span><span class="sxs-lookup"><span data-stu-id="5da3d-125">Dimension, partition</span></span>|  
|<span data-ttu-id="5da3d-126">*ProcessUpdate*</span><span class="sxs-lookup"><span data-stu-id="5da3d-126">*ProcessUpdate*</span></span>|<span data-ttu-id="5da3d-127">Dimension</span><span class="sxs-lookup"><span data-stu-id="5da3d-127">Dimension</span></span>|  
|<span data-ttu-id="5da3d-128">*ProcessIndexes*</span><span class="sxs-lookup"><span data-stu-id="5da3d-128">*ProcessIndexes*</span></span>|<span data-ttu-id="5da3d-129">Dimension, cube, groupe de mesures, partition</span><span class="sxs-lookup"><span data-stu-id="5da3d-129">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="5da3d-130">*ProcessData*</span><span class="sxs-lookup"><span data-stu-id="5da3d-130">*ProcessData*</span></span>|<span data-ttu-id="5da3d-131">Dimension, cube, groupe de mesures, partition</span><span class="sxs-lookup"><span data-stu-id="5da3d-131">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="5da3d-132">*ProcessDefault*</span><span class="sxs-lookup"><span data-stu-id="5da3d-132">*ProcessDefault*</span></span>|<span data-ttu-id="5da3d-133">Cube, base de données, dimension, groupe de mesures, modèle d'exploration de données, structure d'exploration de données, partition</span><span class="sxs-lookup"><span data-stu-id="5da3d-133">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="5da3d-134">*ProcessClear*</span><span class="sxs-lookup"><span data-stu-id="5da3d-134">*ProcessClear*</span></span>|<span data-ttu-id="5da3d-135">Cube, base de données, dimension, groupe de mesures, modèle d'exploration de données, structure d'exploration de données, partition</span><span class="sxs-lookup"><span data-stu-id="5da3d-135">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="5da3d-136">*ProcessStructure*</span><span class="sxs-lookup"><span data-stu-id="5da3d-136">*ProcessStructure*</span></span>|<span data-ttu-id="5da3d-137">Cube, structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5da3d-137">Cube, mining structure</span></span>|  
|<span data-ttu-id="5da3d-138">*ProcessClearStructureOnly*</span><span class="sxs-lookup"><span data-stu-id="5da3d-138">*ProcessClearStructureOnly*</span></span>|<span data-ttu-id="5da3d-139">Structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5da3d-139">Mining structure</span></span>|  
|<span data-ttu-id="5da3d-140">*ProcessScriptCache*</span><span class="sxs-lookup"><span data-stu-id="5da3d-140">*ProcessScriptCache*</span></span>|<span data-ttu-id="5da3d-141">Cube</span><span class="sxs-lookup"><span data-stu-id="5da3d-141">Cube</span></span>|  
  
 <span data-ttu-id="5da3d-142">Pour plus d’informations sur le traitement des [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objets, consultez traitement de l' [objet de modèle multidimensionnel](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="5da3d-142">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
## <a name="specifying-objects-to-be-processed"></a><span data-ttu-id="5da3d-143">Spécification des objets à traiter</span><span class="sxs-lookup"><span data-stu-id="5da3d-143">Specifying Objects to be Processed</span></span>  
 <span data-ttu-id="5da3d-144">La propriété [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) de la `Process` commande contient l’identificateur d’objet de l’objet à traiter.</span><span class="sxs-lookup"><span data-stu-id="5da3d-144">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Process` command contains the object identifier of the object to be processed.</span></span> <span data-ttu-id="5da3d-145">Seul un objet peut être spécifié dans une commande `Process`, mais le traitement d'un objet porte également sur les objets enfants.</span><span class="sxs-lookup"><span data-stu-id="5da3d-145">Only one object can be specified in a `Process` command, but processing an object also processes any child objects.</span></span> <span data-ttu-id="5da3d-146">Par exemple, le traitement d'un groupe de mesures dans un cube englobe toutes les partitions de ce groupe de mesures. De même, le traitement d'une base de données porte sur tous ses objets, notamment les cubes, les dimensions et les structures d'exploration de données contenus dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5da3d-146">For example, processing a measure group in a cube processes all the partitions for that measure group, while processing a database processes all the objects, including cubes, dimensions, and mining structures, that are contained by the database.</span></span>  
  
 <span data-ttu-id="5da3d-147">Si vous définissez l'attribut `ProcessAffectedObjects` de la commande `Process` à true, les objets connexes affectés par le traitement de l'objet spécifié sont égalements traités.</span><span class="sxs-lookup"><span data-stu-id="5da3d-147">If you set the `ProcessAffectedObjects` attribute of the `Process` command to true, any related object affected by processing the specified object is also processed.</span></span> <span data-ttu-id="5da3d-148">Par exemple, si une dimension est mise à jour de façon incrémentielle à l’aide de l’option de traitement *ProcessUpdate* de la `Process` commande, toute partition dont les agrégations sont invalidées en raison de l’ajout ou de la suppression de membres est également traitée par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] si a la valeur `ProcessAffectedObjects` true.</span><span class="sxs-lookup"><span data-stu-id="5da3d-148">For example, if a dimension is incrementally updated by using the *ProcessUpdate* processing option in the `Process` command, any partition whose aggregations are invalidated because of members being added or deleted is also processed by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] if `ProcessAffectedObjects` is set to true.</span></span> <span data-ttu-id="5da3d-149">Dans ce cas, une seule commande `Process` peut traiter plusieurs objets dans une même instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], mais c'est [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui détermine quels sont les objets, outre l'objet unique spécifié dans la commande `Process`, qui doivent également être traités.</span><span class="sxs-lookup"><span data-stu-id="5da3d-149">In this case, a single `Process` command can process multiple objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, but [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determines which objects besides the single object specified in the `Process` command must also be processed.</span></span>  
  
 <span data-ttu-id="5da3d-150">Toutefois, vous pouvez traiter simultanément plusieurs objets, tels que des dimensions, en utilisant plusieurs commandes `Process` au sein d'une commande `Batch`.</span><span class="sxs-lookup"><span data-stu-id="5da3d-150">However, you can process multiple objects, such as dimensions, at the same time by using multiple `Process` commands within a `Batch` command.</span></span> <span data-ttu-id="5da3d-151">Lorsqu'il s'agit de traiter les objets d'une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en série ou en parallèle, les opérations de traitement par lot offrent un niveau de contrôle plus fin qu'en utilisant l'attribut `ProcessAffectedObjects`. Elles vous permettent en outre d'affiner votre approche de traitement pour les bases de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] plus volumineuses.</span><span class="sxs-lookup"><span data-stu-id="5da3d-151">Batch operations provide a finer level of control for serial or parallel processing of objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance than using the `ProcessAffectedObjects` attribute, and let you to tune your processing approach for larger [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases.</span></span> <span data-ttu-id="5da3d-152">Pour plus d’informations sur l’exécution d’opérations par lots, consultez [exécution d’opérations par lots &#40;&#41;XMLA ](performing-batch-operations-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="5da3d-152">For more information about performing batch operations, see [Performing Batch Operations &#40;XMLA&#41;](performing-batch-operations-xmla.md).</span></span>  
  
## <a name="specifying-out-of-line-bindings"></a><span data-ttu-id="5da3d-153">Spécification de liaisons hors ligne</span><span class="sxs-lookup"><span data-stu-id="5da3d-153">Specifying Out-of-Line Bindings</span></span>  
 <span data-ttu-id="5da3d-154">Si la `Process` commande n’est pas contenue `Batch` dans une commande, vous pouvez éventuellement spécifier des liaisons hors ligne dans les propriétés [bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla)et [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) de la `Process` commande pour les objets à traiter.</span><span class="sxs-lookup"><span data-stu-id="5da3d-154">If the `Process` command is not contained by a `Batch` command, you can optionally specify out-of-line bindings in the [Bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla), and [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) properties of the `Process` command for the objects to be processed.</span></span> <span data-ttu-id="5da3d-155">Les liaisons hors lignes sont des références à des sources de données, des vues de source de données et d'autres objets dans lesquels elles existent seulement le temps de l'exécution de la commande `Process`. Elles remplacent les liaisons existantes associées aux objets traités.</span><span class="sxs-lookup"><span data-stu-id="5da3d-155">Out-of-line bindings are references to data sources, data source views, and other objects in which the binding exists only during the execution of the `Process` command, and which override any existing bindings associated with the objects being processed.</span></span> <span data-ttu-id="5da3d-156">Si aucune liaison hors ligne n'est spécifiée, les liaisons actuellement associées aux objets à traiter sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="5da3d-156">If out-of-line bindings are not specified, the bindings currently associated with the objects to be processed are used.</span></span>  
  
 <span data-ttu-id="5da3d-157">Les liaisons hors ligne sont utilisées dans les circonstances suivantes :</span><span class="sxs-lookup"><span data-stu-id="5da3d-157">Out-of-line bindings are used in the following circumstances:</span></span>  
  
-   <span data-ttu-id="5da3d-158">traitement incrémentiel d'une partition dans laquelle une table de faits alternative ou un filtre appliqué à la table de faits existante doit être spécifié pour éviter que les lignes ne soient comptées deux fois ;</span><span class="sxs-lookup"><span data-stu-id="5da3d-158">Incrementally processing a partition, in which an alternative fact table or a filter on the existing fact table must be specified to make sure that rows are not counted twice.</span></span>  
  
-   <span data-ttu-id="5da3d-159">Utilisation d’une tâche de workflow dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pour fournir des données lors du traitement d’une dimension, d’un modèle d’exploration de données ou d’une partition.</span><span class="sxs-lookup"><span data-stu-id="5da3d-159">Using a data flow task in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to provide data while processing a dimension, mining model, or partition.</span></span>  
  
 <span data-ttu-id="5da3d-160">Les liaisons hors ligne sont décrites dans le cadre d'ASSL (Analysis Services Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="5da3d-160">Out-of-line bindings are described as part of the Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="5da3d-161">Pour plus d’informations sur les liaisons hors ligne dans ASSL, consultez sources de [données et liaisons &#40;&#41;multidimensionnel SSAS ](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="5da3d-161">For more information about out-of-line bindings in ASSL, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span></span>  
  
### <a name="incrementally-updating-partitions"></a><span data-ttu-id="5da3d-162">Mise à jour incrémentielle des partitions</span><span class="sxs-lookup"><span data-stu-id="5da3d-162">Incrementally Updating Partitions</span></span>  
 <span data-ttu-id="5da3d-163">La mise à jour incrémentielle d'une partition déjà traitée fait généralement appel à une liaison hors ligne, car la liaison spécifiée pour la partition fait référence à des données de table de faits déjà agrégées dans la partition.</span><span class="sxs-lookup"><span data-stu-id="5da3d-163">Incrementally updating an already processed partition typically requires an out-of-line binding because the binding specified for the partition references fact table data already aggregated within the partition.</span></span> <span data-ttu-id="5da3d-164">Lors de la mise à jour incrémentielle d'une partition déjà traitée par le biais de la commande `Process`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] effectue les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="5da3d-164">When incrementally updating an already processed partition by using the `Process` command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] performs the following actions:</span></span>  
  
-   <span data-ttu-id="5da3d-165">création d'une partition temporaire avec une structure identique à celle de la partition devant faire l'objet d'une mise à jour incrémentielle ;</span><span class="sxs-lookup"><span data-stu-id="5da3d-165">Creates a temporary partition with a structure identical to that of the partition to be incrementally updated.</span></span>  
  
-   <span data-ttu-id="5da3d-166">traitement de la partition temporaire en utilisant la liaison hors ligne spécifiée dans la commande `Process` ;</span><span class="sxs-lookup"><span data-stu-id="5da3d-166">Processes the temporary partition, using the out-of-line binding specified in the `Process` command.</span></span>  
  
-   <span data-ttu-id="5da3d-167">fusion de la partition temporaire avec la partition sélectionnée existante.</span><span class="sxs-lookup"><span data-stu-id="5da3d-167">Merges the temporary partition with the existing selected partition.</span></span>  
  
 <span data-ttu-id="5da3d-168">Pour plus d’informations sur la fusion de partitions à l’aide d’XML for Analysis (XMLA), consultez [fusion de partitions &#40;&#41;XMLA ](merging-partitions-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="5da3d-168">For more information about merging partitions using XML for Analysis (XMLA), see [Merging Partitions &#40;XMLA&#41;](merging-partitions-xmla.md).</span></span>  
  
## <a name="handling-processing-errors"></a><span data-ttu-id="5da3d-169">Gestion des erreurs de traitement</span><span class="sxs-lookup"><span data-stu-id="5da3d-169">Handling Processing Errors</span></span>  
 <span data-ttu-id="5da3d-170">La propriété [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) de la `Process` commande vous permet de spécifier comment gérer les erreurs rencontrées lors du traitement d’un objet.</span><span class="sxs-lookup"><span data-stu-id="5da3d-170">The [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) property of the `Process` command lets you specify how to handle errors encountered while processing an object.</span></span> <span data-ttu-id="5da3d-171">Par exemple, lors du traitement d'une dimension, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] rencontre une valeur en double dans la colonne clé de l'attribut de clé.</span><span class="sxs-lookup"><span data-stu-id="5da3d-171">For example, while processing a dimension, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encounters a duplicate value in the key column of the key attribute.</span></span> <span data-ttu-id="5da3d-172">Du fait que les clés d'attribut doivent être uniques, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ignore les enregistrements en double.</span><span class="sxs-lookup"><span data-stu-id="5da3d-172">Because attribute keys must be unique, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] discards the duplicate records.</span></span> <span data-ttu-id="5da3d-173">Basée sur la propriété [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) de `ErrorConfiguration` , [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] peut :</span><span class="sxs-lookup"><span data-stu-id="5da3d-173">Based on the [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) property of `ErrorConfiguration`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] could:</span></span>  
  
-   <span data-ttu-id="5da3d-174">ignorer l'erreur et poursuivre le traitement de la dimension ;</span><span class="sxs-lookup"><span data-stu-id="5da3d-174">Ignore the error and continue processing the dimension.</span></span>  
  
-   <span data-ttu-id="5da3d-175">retourner un message qui indique qu'[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a rencontré une clé en double et poursuivre le traitement.</span><span class="sxs-lookup"><span data-stu-id="5da3d-175">Return a message that states [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encountered a duplicate key and continue processing.</span></span>  
  
 <span data-ttu-id="5da3d-176">Pendant l'exécution d'une commande `ErrorConfiguration`, `Process` peut proposer des options dans de nombreuses conditions similaires.</span><span class="sxs-lookup"><span data-stu-id="5da3d-176">There are many similar conditions for which `ErrorConfiguration` provides options during a `Process` command.</span></span>  
  
## <a name="managing-writeback-tables"></a><span data-ttu-id="5da3d-177">Gestion des tables d'écriture différée</span><span class="sxs-lookup"><span data-stu-id="5da3d-177">Managing Writeback Tables</span></span>  
 <span data-ttu-id="5da3d-178">Si la commande `Process` rencontre une partition activée en écriture (ou un cube ou un groupe de mesures pour une partition de ce type) qui n'est pas déjà traitée en intégralité, il se peut qu'il n'existe pas encore de table d'écriture différée pour cette partition.</span><span class="sxs-lookup"><span data-stu-id="5da3d-178">If the `Process` command encounters a write-enabled partition, or a cube or measure group for such a partition, that is not already fully processed, a writeback table may not already exist for that partition.</span></span> <span data-ttu-id="5da3d-179">La propriété [WriteBackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) de la `Process` commande détermine si [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] doit créer une table d’écriture différée.</span><span class="sxs-lookup"><span data-stu-id="5da3d-179">The [WritebackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) property of the `Process` command determines whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should create a writeback table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5da3d-180">Exemples</span><span class="sxs-lookup"><span data-stu-id="5da3d-180">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="5da3d-181">Description</span><span class="sxs-lookup"><span data-stu-id="5da3d-181">Description</span></span>  
 <span data-ttu-id="5da3d-182">L'exemple suivant traite entièrement la base de données [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5da3d-182">The following example fully processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5da3d-183">Code</span><span class="sxs-lookup"><span data-stu-id="5da3d-183">Code</span></span>  
  
```  
<Process xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
  </Object>  
  <Type>ProcessFull</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
### <a name="description"></a><span data-ttu-id="5da3d-184">Description</span><span class="sxs-lookup"><span data-stu-id="5da3d-184">Description</span></span>  
 <span data-ttu-id="5da3d-185">L’exemple suivant traite de façon incrémentielle la partition **Internet_Sales_2004** dans le groupe de mesures **Internet Sales** du cube **Adventure Works DW** de l' [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] exemple [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de base de données.</span><span class="sxs-lookup"><span data-stu-id="5da3d-185">The following example incrementally processes the **Internet_Sales_2004** partition in the **Internet Sales** measure group of the **Adventure Works DW** cube in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="5da3d-186">La `Process` commande ajoute des agrégations pour les dates de commande ultérieures au 31 décembre 2006 à la partition à l’aide d’une liaison de requête hors ligne dans la `Bindings` propriété de la `Process` commande pour récupérer les lignes de la table de faits à partir desquelles générer des agrégations à ajouter à la partition.</span><span class="sxs-lookup"><span data-stu-id="5da3d-186">The `Process` command is adding aggregations for order dates later than December 31, 2006 to the partition by using an out-of-line query binding in the `Bindings` property of the `Process` command to retrieve the fact table rows from which to generate aggregations to add to the partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5da3d-187">Code</span><span class="sxs-lookup"><span data-stu-id="5da3d-187">Code</span></span>  
  
```  
<Process ProcessAffectedObjects="true" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2006</PartitionID>  
  </Object>  
  <Bindings>  
    <Binding>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2006</PartitionID>  
      <Source xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="QueryBinding">  
        <DataSourceID>Adventure Works DW</DataSourceID>  
        <QueryDefinition>  
          SELECT  
            [dbo].[FactInternetSales].[ProductKey],  
            [dbo].[FactInternetSales].[OrderDateKey],  
            [dbo].[FactInternetSales].[DueDateKey],  
            [dbo].[FactInternetSales].[ShipDateKey],   
            [dbo].[FactInternetSales].[CustomerKey],   
            [dbo].[FactInternetSales].[PromotionKey],  
            [dbo].[FactInternetSales].[CurrencyKey],  
            [dbo].[FactInternetSales].[SalesTerritoryKey],  
            [dbo].[FactInternetSales].[SalesOrderNumber],  
            [dbo].[FactInternetSales].[SalesOrderLineNumber],  
            [dbo].[FactInternetSales].[RevisionNumber],  
            [dbo].[FactInternetSales].[OrderQuantity],  
            [dbo].[FactInternetSales].[UnitPrice],  
            [dbo].[FactInternetSales].[ExtendedAmount],  
            [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
            [dbo].[FactInternetSales].[DiscountAmount],  
            [dbo].[FactInternetSales].[ProductStandardCost],  
            [dbo].[FactInternetSales].[TotalProductCost],  
            [dbo].[FactInternetSales].[SalesAmount],  
            [dbo].[FactInternetSales].[TaxAmt],  
            [dbo].[FactInternetSales].[Freight],  
            [dbo].[FactInternetSales].[CarrierTrackingNumber],  
            [dbo].[FactInternetSales].[CustomerPONumber]  
          FROM [dbo].[FactInternetSales]  
          WHERE OrderDateKey > '1280'  
        </QueryDefinition>  
      </Source>  
    </Binding>  
  </Bindings>  
  <Type>ProcessAdd</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
  
