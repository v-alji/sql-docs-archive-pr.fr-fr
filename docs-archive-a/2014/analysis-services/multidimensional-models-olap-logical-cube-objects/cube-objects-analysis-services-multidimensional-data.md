---
title: Objets de cube (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], objects
ms.assetid: 5cee362e-3f95-4467-bc6c-29b1518ecbf3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0e6dfb75be696ab26893e668b99dc36c7340f86c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610896"
---
# <a name="cube-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="a90a7-102">Objets de cube (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="a90a7-102">Cube Objects (Analysis Services - Multidimensional Data)</span></span>
    
## <a name="introducing-cube-objects"></a><span data-ttu-id="a90a7-103">Présentation des objets de cube</span><span class="sxs-lookup"><span data-stu-id="a90a7-103">Introducing Cube Objects</span></span>  
 <span data-ttu-id="a90a7-104">Un objet <xref:Microsoft.AnalysisServices.Cube> simple est composé d'informations de base, de dimensions et de groupes de mesures.</span><span class="sxs-lookup"><span data-stu-id="a90a7-104">A simple <xref:Microsoft.AnalysisServices.Cube> object is composed of: basic information, dimensions, and measure groups.</span></span> <span data-ttu-id="a90a7-105">Les informations de base incluent le nom du cube, la mesure par défaut du cube, la source de données, le mode de stockage et d'autres informations.</span><span class="sxs-lookup"><span data-stu-id="a90a7-105">Basic information includes the name of the cube, the default measure of the cube, the data source, the storage mode, and others.</span></span>  
  
 <span data-ttu-id="a90a7-106">La collection Dimensions contient le jeu réel de dimensions utilisé dans le cube depuis la collection de dimensions de la base de données.</span><span class="sxs-lookup"><span data-stu-id="a90a7-106">The Dimensions collection contains the actual set of dimensions used in the cube from the database dimensions colection.</span></span> <span data-ttu-id="a90a7-107">Toutes les dimensions doivent être définies dans la collection de dimensions de la base de données avant d'être référencées dans le cube.</span><span class="sxs-lookup"><span data-stu-id="a90a7-107">All dimensions have to be defined in the dimensions collection of the database before being referenced in the cube.</span></span> <span data-ttu-id="a90a7-108">Les dimensions privées ne sont pas disponibles dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a90a7-108">Private dimensions are not available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a90a7-109">Les groupes de mesures sont les jeux de mesures du cube.</span><span class="sxs-lookup"><span data-stu-id="a90a7-109">Measure groups are sets of measures in the cube.</span></span> <span data-ttu-id="a90a7-110">Un groupe de mesures est une collection de mesures qui ont en commun une vue de source de données et un jeu de dimensions.</span><span class="sxs-lookup"><span data-stu-id="a90a7-110">A measure group is a collection of measures that have a common data source view and a common set of dimensions.</span></span> <span data-ttu-id="a90a7-111">Un groupe de mesures est l'unité du processus pour les mesures ; les groupes de mesures peuvent être traités individuellement, puis parcourus.</span><span class="sxs-lookup"><span data-stu-id="a90a7-111">A measure group is the unit of process for measures; measure groups can be processed individually and then browsed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a90a7-112">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="a90a7-112">In this section</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a90a7-113">Rubrique</span><span class="sxs-lookup"><span data-stu-id="a90a7-113">Topic</span></span>||  
|[<span data-ttu-id="a90a7-114">Actions &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="a90a7-114">Actions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models/actions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="a90a7-115">Agrégations et conceptions d'agrégation</span><span class="sxs-lookup"><span data-stu-id="a90a7-115">Aggregations and Aggregation Designs</span></span>](aggregations-and-aggregation-designs.md)||  
|[<span data-ttu-id="a90a7-116">Calculs</span><span class="sxs-lookup"><span data-stu-id="a90a7-116">Calculations</span></span>](calculations.md)||  
|[<span data-ttu-id="a90a7-117">Cellules de cube &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="a90a7-117">Cube Cells &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-cells-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="a90a7-118">Propriétés de cube</span><span class="sxs-lookup"><span data-stu-id="a90a7-118">Cube Properties</span></span>](cube-properties-multidimensional-model-programming.md)||  
|[<span data-ttu-id="a90a7-119">Stockage cube &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="a90a7-119">Cube Storage &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-storage-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="a90a7-120">Traductions de cube</span><span class="sxs-lookup"><span data-stu-id="a90a7-120">Cube Translations</span></span>](cube-translations.md)||  
|[<span data-ttu-id="a90a7-121">Relations de dimension</span><span class="sxs-lookup"><span data-stu-id="a90a7-121">Dimension Relationships</span></span>](dimension-relationships.md)||  
|[<span data-ttu-id="a90a7-122">Indicateurs de performance clés &#40;KPI&#41; dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="a90a7-122">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](../multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)||  
|[<span data-ttu-id="a90a7-123">Mesures et groupes de mesures</span><span class="sxs-lookup"><span data-stu-id="a90a7-123">Measures and Measure Groups</span></span>](../multidimensional-models/measures-and-measure-groups.md)||  
|[<span data-ttu-id="a90a7-124">Partitions &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="a90a7-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partitions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="a90a7-125">Perspectives</span><span class="sxs-lookup"><span data-stu-id="a90a7-125">Perspectives</span></span>](perspectives.md)||  
  
  
