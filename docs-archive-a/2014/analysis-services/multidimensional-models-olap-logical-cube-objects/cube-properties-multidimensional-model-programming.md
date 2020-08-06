---
title: Propriétés du cube | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Collation property
- ID property
- ErrorConfiguration property
- cubes [Analysis Services], properties
- Description property
- DefaultMeasure property
- ProcessingMode property
- AggregationPrefix property
- EstimatedRows property
- Visible property
- StorageLocation property
- StorageMode property
- ScriptErrorHandlingMode property
- Source property
- ScriptCacheProcessingMode property
- Language property
- Name property
- properties [Analysis Services], cubes
- ProcessingPriority property
- ProactiveCaching property
ms.assetid: 72ca3387-620d-4473-8e23-7fe1f2b3d5bf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 27d4202774107795eaddf76c27e21010d534d977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601760"
---
# <a name="cube-properties"></a><span data-ttu-id="5139e-102">Propriétés de cube</span><span class="sxs-lookup"><span data-stu-id="5139e-102">Cube Properties</span></span>
  <span data-ttu-id="5139e-103">Les cubes ont un grand nombre de propriétés que vous pouvez définir pour affecter le comportement à l'échelle du cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-103">Cubes have a number of properties that you can set to affect cube-wide behavior.</span></span> <span data-ttu-id="5139e-104">Ces propriétés sont présentées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5139e-104">These properties are summarized in the following table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5139e-105">Certaines propriétés sont définies automatiquement lors de la création du cube et ne peuvent pas être modifiées.</span><span class="sxs-lookup"><span data-stu-id="5139e-105">Some properties are set automatically when the cube is created and cannot be changed.</span></span>  
  
 <span data-ttu-id="5139e-106">Pour plus d’informations sur la définition des propriétés d’un cube, consultez [Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](../cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="5139e-106">For more information about how to set cube properties, see [Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](../cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
|<span data-ttu-id="5139e-107">Propriété</span><span class="sxs-lookup"><span data-stu-id="5139e-107">Property</span></span>|<span data-ttu-id="5139e-108">Description</span><span class="sxs-lookup"><span data-stu-id="5139e-108">Description</span></span>|  
|--------------|-----------------|  
|`AggregationPrefix`|<span data-ttu-id="5139e-109">Spécifie le préfixe commun qui est utilisé pour les noms d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="5139e-109">Specifies the common prefix that is used for aggregation names.</span></span>|  
|`Collation`|<span data-ttu-id="5139e-110">Spécifie l'identificateur de paramètres régionaux (LCID) et l'indicateur de comparaison, séparés par un trait de soulignement, comme dans Latin1_General_C1_AS.</span><span class="sxs-lookup"><span data-stu-id="5139e-110">Specifies the locale identifier (LCID) and the comparison flag, separated by an underscore: for example, Latin1_General_C1_AS.</span></span>|  
|`DefaultMeasure`|<span data-ttu-id="5139e-111">Contient une expression MDX (Multidimensional Expressions) qui définit la mesure par défaut pour le cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-111">Contains a Multidimensional Expressions (MDX) expression that defines the default measure for the cube.</span></span>|  
|`Description`|<span data-ttu-id="5139e-112">Fournit une description du cube, qui peut être exposée dans les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="5139e-112">Provides a description of the cube, which may be exposed in client applications.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="5139e-113">Contient des paramètres configurables de gestion d'erreur pour la gestion des clés dupliquées, des clés inconnues, des limites d'erreur, des actions en cas de détection d'erreur, du fichier journal des erreurs et pour la gestion des clés NULL.</span><span class="sxs-lookup"><span data-stu-id="5139e-113">Contains configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`EstimatedRows`|<span data-ttu-id="5139e-114">Spécifie le nombre de lignes estimées dans le cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-114">Specifies the number of estimated rows in the cube.</span></span>|  
|`ID`|<span data-ttu-id="5139e-115">Contient l'identificateur (ID) unique du cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-115">Contains the unique identifier (ID) of the cube.</span></span>|  
|`Language`|<span data-ttu-id="5139e-116">Spécifie l'identificateur de langue par défaut du cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-116">Specifies the default language identifier of the cube.</span></span>|  
|`Name`|<span data-ttu-id="5139e-117">Spécifie le nom convivial du cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-117">Specifies the user-friendly name of the cube.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="5139e-118">Définit les paramètres de mise en cache proactive pour le cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-118">Defines proactive cache settings for the cube.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="5139e-119">Indique si l'indexation et l'agrégation doivent avoir lieu lors du traitement ou après celui-ci.</span><span class="sxs-lookup"><span data-stu-id="5139e-119">Indicates whether indexing and aggregating should occur during or after processing.</span></span> <span data-ttu-id="5139e-120">Les options sont **Regular** ou `lazy` .</span><span class="sxs-lookup"><span data-stu-id="5139e-120">Options are **regular** or `lazy`.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="5139e-121">Détermine la priorité de traitement du cube pendant les opérations d'arrière-plan, telles que les agrégations et les indexations différées (Lazy).</span><span class="sxs-lookup"><span data-stu-id="5139e-121">Determines the processing priority of the cube during background operations, such as lazy aggregations and indexing.</span></span> <span data-ttu-id="5139e-122">La valeur par défaut est **0**.</span><span class="sxs-lookup"><span data-stu-id="5139e-122">The default value is **0**.</span></span>|  
|`ScriptCacheProcessingMode`|<span data-ttu-id="5139e-123">Indique si le cache des scripts doit être généré durant le traitement ou après celui-ci.</span><span class="sxs-lookup"><span data-stu-id="5139e-123">Indicates whether the script cache should be built during or after processing.</span></span> <span data-ttu-id="5139e-124">Les options sont **Regular** et `lazy` .</span><span class="sxs-lookup"><span data-stu-id="5139e-124">Options are **regular** and `lazy`.</span></span>|  
|`ScriptErrorHandlingMode`|<span data-ttu-id="5139e-125">Détermine la gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="5139e-125">Determines error handling.</span></span> <span data-ttu-id="5139e-126">Les options sont `IgnoreNone` ou`IgnoreAll`</span><span class="sxs-lookup"><span data-stu-id="5139e-126">Options are `IgnoreNone` or `IgnoreAll`</span></span>|  
|`Source`|<span data-ttu-id="5139e-127">Affiche la vue de source de données utilisée pour le cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-127">Displays the data source view used for the cube.</span></span>|  
|`StorageLocation`|<span data-ttu-id="5139e-128">Spécifie l'emplacement de stockage du système de fichiers pour le cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-128">Specifies the file system storage location for the cube.</span></span> <span data-ttu-id="5139e-129">Si aucun n'est spécifié, l'emplacement est hérité de la base de données qui contient l'objet du cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-129">If none is specified, the location is inherited from the database that contains the cube object.</span></span>|  
|`StorageMode`|<span data-ttu-id="5139e-130">Spécifie le mode de stockage pour le cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-130">Specifies the storage mode for the cube.</span></span> <span data-ttu-id="5139e-131">Les valeurs sont `MOLAP` , `ROLAP` ou`HOLAP``.`</span><span class="sxs-lookup"><span data-stu-id="5139e-131">Values are `MOLAP`, `ROLAP`, or `HOLAP``.`</span></span>|  
|`Visible`|<span data-ttu-id="5139e-132">Détermine la visibilité du cube.</span><span class="sxs-lookup"><span data-stu-id="5139e-132">Determines the visibility of the cube.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="5139e-133">Pour plus d’informations sur la définition des valeurs de la propriété ErrorConfiguration lors de l’utilisation de valeurs NULL et d’autres problèmes d’intégrité des données, consultez [gestion des problèmes d’intégrité des données dans Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="5139e-133">For more information about setting values for the ErrorConfiguration property when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5139e-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5139e-134">See Also</span></span>  
 [<span data-ttu-id="5139e-135">Mise en cache proactive &#40;les partitions&#41;</span><span class="sxs-lookup"><span data-stu-id="5139e-135">Proactive Caching &#40;Partitions&#41;</span></span>](partitions-proactive-caching.md)  
  
  
