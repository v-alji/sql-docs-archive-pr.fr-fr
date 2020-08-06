---
title: Cubes dans les modèles multidimensionnels | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OLAP objects [Analysis Services], cubes
- cubes [Analysis Services], about cubes
- cubes [Analysis Services]
- OLAP [Analysis Services], cubes
ms.assetid: e0f7acf3-4b07-41fc-a5fc-ac30b4a56c54
author: minewiskan
ms.author: owend
ms.openlocfilehash: 372bb8075b232ff8fbf8a54facf9bc065e6763a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708779"
---
# <a name="cubes-in-multidimensional-models"></a><span data-ttu-id="162f8-102">Cubes dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-102">Cubes in Multidimensional Models</span></span>
  <span data-ttu-id="162f8-103">Un cube est une structure multidimensionnelle qui contient des informations à des fins analytiques ; les constituants principaux d'un cube sont des dimensions et des mesures.</span><span class="sxs-lookup"><span data-stu-id="162f8-103">A cube is a multidimensional structure that contains information for analytical purposes; the main constituents of a cube are dimensions and measures.</span></span> <span data-ttu-id="162f8-104">Les dimensions définissent la structure du cube que vous utilisez pour la découpe, et les mesures fournissent des valeurs numériques agrégées qui intéressent l'utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="162f8-104">Dimensions define the structure of the cube that you use to slice and dice over, and measures provide aggregated numerical values of interest to the end user.</span></span> <span data-ttu-id="162f8-105">Comme structure logique, un cube permet à une application cliente de récupérer des valeurs, de mesures, comme si elles étaient contenues dans des cellules du cube ; les cellules sont définies pour chaque valeur résumée possible.</span><span class="sxs-lookup"><span data-stu-id="162f8-105">As a logical structure, a cube allows a client application to retrieve values, of measures, as if they were contained in cells in the cube; cells are defined for every possible summarized value.</span></span> <span data-ttu-id="162f8-106">Une cellule, dans le cube, est définie par l'intersection des membres de dimension et contient les valeurs agrégées des mesures à cette intersection spécifique.</span><span class="sxs-lookup"><span data-stu-id="162f8-106">A cell, in the cube, is defined by the intersection of dimension members and contains the aggregated values of the measures at that specific intersection.</span></span>  
  
## <a name="benefits-of-using-cubes"></a><span data-ttu-id="162f8-107">Avantages de l'utilisation des cubes</span><span class="sxs-lookup"><span data-stu-id="162f8-107">Benefits of Using Cubes</span></span>  
 <span data-ttu-id="162f8-108">Un cube fournit un seul emplacement où toutes les données associées, pour l'analyse, sont stockées.</span><span class="sxs-lookup"><span data-stu-id="162f8-108">A cube provides a single place where all related data, for analysis, is stored.</span></span>  
  
## <a name="components-of-cubes"></a><span data-ttu-id="162f8-109">Composants des cubes</span><span class="sxs-lookup"><span data-stu-id="162f8-109">Components of Cubes</span></span>  
 <span data-ttu-id="162f8-110">Un cube est composé de :</span><span class="sxs-lookup"><span data-stu-id="162f8-110">A cube is composed of:</span></span>  
  
|<span data-ttu-id="162f8-111">Élément</span><span class="sxs-lookup"><span data-stu-id="162f8-111">Element</span></span>|<span data-ttu-id="162f8-112">Description</span><span class="sxs-lookup"><span data-stu-id="162f8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="162f8-113">Dimensions</span><span class="sxs-lookup"><span data-stu-id="162f8-113">Dimensions</span></span>|[<span data-ttu-id="162f8-114">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-114">Dimensions in Multidimensional Models</span></span>](dimensions-in-multidimensional-models.md)|  
|<span data-ttu-id="162f8-115">Mesures et groupes de mesures</span><span class="sxs-lookup"><span data-stu-id="162f8-115">Measures and Measure Groups</span></span>|[<span data-ttu-id="162f8-116">Création de mesures et de groupes de mesures dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-116">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|  
|<span data-ttu-id="162f8-117">Partitions</span><span class="sxs-lookup"><span data-stu-id="162f8-117">Partitions</span></span>|[<span data-ttu-id="162f8-118">Partitions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-118">Partitions in Multidimensional Models</span></span>](partitions-in-multidimensional-models.md)|  
|<span data-ttu-id="162f8-119">Perspectives</span><span class="sxs-lookup"><span data-stu-id="162f8-119">Perspectives</span></span>|[<span data-ttu-id="162f8-120">Perspectives dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-120">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|  
|<span data-ttu-id="162f8-121">Hierarchies</span><span class="sxs-lookup"><span data-stu-id="162f8-121">Hierarchies</span></span>|[<span data-ttu-id="162f8-122">Créer des hiérarchies définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="162f8-122">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)|  
|<span data-ttu-id="162f8-123">Actions</span><span class="sxs-lookup"><span data-stu-id="162f8-123">Actions</span></span>|[<span data-ttu-id="162f8-124">Actions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-124">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|  
|<span data-ttu-id="162f8-125">Indicateurs de performance clés (KPI)</span><span class="sxs-lookup"><span data-stu-id="162f8-125">Key Performance Indicators (KPI)</span></span>|[<span data-ttu-id="162f8-126">Indicateurs de performance clés &#40;KPI&#41; dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-126">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](key-performance-indicators-kpis-in-multidimensional-models.md)|  
|<span data-ttu-id="162f8-127">Calculs</span><span class="sxs-lookup"><span data-stu-id="162f8-127">Calculations</span></span>|[<span data-ttu-id="162f8-128">Calculs dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-128">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|  
|<span data-ttu-id="162f8-129">Translations</span><span class="sxs-lookup"><span data-stu-id="162f8-129">Translations</span></span>|[<span data-ttu-id="162f8-130">Traductions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-130">Translations in Multidimensional Models</span></span>](translations-in-multidimensional-models-analysis-services.md)|  
  
## <a name="related-tasks"></a><span data-ttu-id="162f8-131">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="162f8-131">Related Tasks</span></span>  
  
|<span data-ttu-id="162f8-132">Rubrique</span><span class="sxs-lookup"><span data-stu-id="162f8-132">Topic</span></span>|<span data-ttu-id="162f8-133">Description</span><span class="sxs-lookup"><span data-stu-id="162f8-133">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="162f8-134">Créer un cube à l'aide de l'Assistant Cube</span><span class="sxs-lookup"><span data-stu-id="162f8-134">Create a Cube Using the Cube Wizard</span></span>](create-a-cube-using-the-cube-wizard.md)|<span data-ttu-id="162f8-135">Décrit comment utiliser l'Assistant Cube pour définir un cube, des dimensions, des attributs de dimension et des hiérarchies définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="162f8-135">Describes how to use the Cube Wizard to define a cube, dimensions, dimension attributes, and user-defined hierarchies.</span></span>|  
|[<span data-ttu-id="162f8-136">Création de mesures et de groupes de mesures dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-136">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|<span data-ttu-id="162f8-137">Décrit comment définir des groupes de mesures.</span><span class="sxs-lookup"><span data-stu-id="162f8-137">Describes how to define measure groups.</span></span>|  
|[<span data-ttu-id="162f8-138">Calculs dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-138">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|<span data-ttu-id="162f8-139">Décrit comment définir et configurer un calcul dans un script MDX.</span><span class="sxs-lookup"><span data-stu-id="162f8-139">Describes how to define and configure a calculation in an MDX script.</span></span>|  
|[<span data-ttu-id="162f8-140">Actions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-140">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|<span data-ttu-id="162f8-141">Décrit comment définir et configurer une action.</span><span class="sxs-lookup"><span data-stu-id="162f8-141">Describes how to define and configure an action.</span></span>|  
|[<span data-ttu-id="162f8-142">Perspectives dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="162f8-142">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|<span data-ttu-id="162f8-143">Décrit comment définir et configurer une perspective.</span><span class="sxs-lookup"><span data-stu-id="162f8-143">Describes how to define and configure a perspective.</span></span>|  
|[<span data-ttu-id="162f8-144">Définition de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="162f8-144">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)|<span data-ttu-id="162f8-145">Décrit comment utiliser les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="162f8-145">Describes how to work with stored procedures.</span></span>|  
  
  
