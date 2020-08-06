---
title: Objets de base de données (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], about objects
- SQL Server Analysis Services, objects
- Analysis Services objects, about Analysis Services objects
- SSAS, objects
- Analysis Services objects
- objects [Analysis Services]
ms.assetid: f76d869b-fc1d-4807-9f28-da09c7be382d
author: minewiskan
ms.author: owend
ms.openlocfilehash: d61e3213356146e1cf9e452e0b62e02c96bd4902
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710927"
---
# <a name="database-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="ac94e-102">Objets de bases de données (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="ac94e-102">Database Objects (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ac94e-103">Une [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance de contient des objets de base de données et des assemblys à utiliser avec le traitement analytique en ligne (OLAP) et l’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="ac94e-103">A [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance contains database objects and assemblies for use with online analytical processing (OLAP) and data mining.</span></span>  
  
-   <span data-ttu-id="ac94e-104">Les bases de données contiennent des objets OLAP et des objets d'exploration de données, tels que des sources de données, des vues de sources de données, des cubes, des mesures, des groupes de mesures, des dimensions, des attributs, des hiérarchies, des structures d'exploration de données, des modèles d'exploration de données et des rôles.</span><span class="sxs-lookup"><span data-stu-id="ac94e-104">Databases contain OLAP and data mining objects, such as data sources, data source views, cubes, measures, measure groups, dimensions, attributes, hierarchies, mining structures, mining models and roles.</span></span>  
  
-   <span data-ttu-id="ac94e-105">Les assemblys contiennent des fonctions définies par l'utilisateur qui étendent les fonctionnalités des fonctions intrinsèques fournies avec les langages MDX (Multidimensional Expressions) et DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="ac94e-105">Assemblies contain user-defined functions that extend the functionality of the intrinsic functions provided with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span>  
  
 <span data-ttu-id="ac94e-106">L'objet <xref:Microsoft.AnalysisServices.Database> est le conteneur pour tous les objets de données exigés pour un projet Business Intelligence (tel que les cubes OLAP, les dimensions et les structures d'exploration de données) et leurs objets de prise en charge (tel que <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account> et <xref:Microsoft.AnalysisServices.Role>).</span><span class="sxs-lookup"><span data-stu-id="ac94e-106">The <xref:Microsoft.AnalysisServices.Database> object is the container for all data objects that are needed for a business intelligence project (such as OLAP cubes, dimensions, and data mining structures), and their supporting objects (such as <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account>, and <xref:Microsoft.AnalysisServices.Role>).</span></span>  
  
 <span data-ttu-id="ac94e-107">Un objet <xref:Microsoft.AnalysisServices.Database> fournit l'accès aux objets et attributs qui incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ac94e-107">A <xref:Microsoft.AnalysisServices.Database> object provides access to objects and attributes that include the following:</span></span>  
  
-   <span data-ttu-id="ac94e-108">Tous les cubes auxquels vous pouvez accéder, comme une collection.</span><span class="sxs-lookup"><span data-stu-id="ac94e-108">All cubes that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="ac94e-109">Toutes les dimensions auxquelles vous pouvez accéder, comme une collection.</span><span class="sxs-lookup"><span data-stu-id="ac94e-109">All dimensions that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="ac94e-110">Toutes les structures d'exploration de données auxquelles vous pouvez accéder, comme une collection.</span><span class="sxs-lookup"><span data-stu-id="ac94e-110">All mining structures that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="ac94e-111">Toutes les sources de données et vues de source de données, comme deux collections.</span><span class="sxs-lookup"><span data-stu-id="ac94e-111">All data sources and data source views, as two collections.</span></span>  
  
-   <span data-ttu-id="ac94e-112">Tous les rôles et autorisations de base de données, comme deux collections.</span><span class="sxs-lookup"><span data-stu-id="ac94e-112">All roles and database permissions, as two collections.</span></span>  
  
-   <span data-ttu-id="ac94e-113">La valeur de classement par défaut de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ac94e-113">The collation value for the database.</span></span>  
  
-   <span data-ttu-id="ac94e-114">La taille estime de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ac94e-114">The estimated size of the database.</span></span>  
  
-   <span data-ttu-id="ac94e-115">La valeur de langage de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ac94e-115">The language value of the database.</span></span>  
  
-   <span data-ttu-id="ac94e-116">Le paramètre visible pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="ac94e-116">The visible setting for the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac94e-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ac94e-117">In This Section</span></span>  
 <span data-ttu-id="ac94e-118">Les rubriques suivantes décrivent les objets communs aux fonctionnalités OLAP et aux fonctionnalités d'exploration de données dans [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac94e-118">The following topics describe objects shared by both OLAP and data mining features in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="ac94e-119">Rubrique</span><span class="sxs-lookup"><span data-stu-id="ac94e-119">Topic</span></span>|<span data-ttu-id="ac94e-120">Description</span><span class="sxs-lookup"><span data-stu-id="ac94e-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ac94e-121">Sources de données dans des modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="ac94e-121">Data Sources in Multidimensional Models</span></span>](../data-sources-in-multidimensional-models.md)|<span data-ttu-id="ac94e-122">Décrit les sources de données dans [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac94e-122">Describes a data source in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="ac94e-123">Vues de sources de données dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="ac94e-123">Data Source Views in Multidimensional Models</span></span>](../data-source-views-in-multidimensional-models.md)|<span data-ttu-id="ac94e-124">Décrit un modèle de données logique basé sur une ou plusieurs sources de données dans [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac94e-124">Describes a logical data model based on one or more data sources, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="ac94e-125">Cubes dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="ac94e-125">Cubes in Multidimensional Models</span></span>](../cubes-in-multidimensional-models.md)|<span data-ttu-id="ac94e-126">Décrit les cubes et les objets de cube, y compris les mesures, les groupes de mesures, les relations d'utilisation de dimension, les calculs, les indicateurs de performance clés (KPI), les actions, les traductions, les partitions et les perspectives.</span><span class="sxs-lookup"><span data-stu-id="ac94e-126">Describes cubes and cube objects, including measures, measure groups, dimension usage relationships, calculations, key performance indicators, actions, translations, partitions, and perspectives.</span></span>|  
|[<span data-ttu-id="ac94e-127">Dimensions &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="ac94e-127">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="ac94e-128">Décrit les dimensions et les objets de dimension, y compris les attributs, les relations d'attributs, les hiérarchies, les niveaux et les membres.</span><span class="sxs-lookup"><span data-stu-id="ac94e-128">Describes dimensions and dimension objects, including attributes, attribute relationships, hierarchies, levels, and members.</span></span>|  
|[<span data-ttu-id="ac94e-129">Structures d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="ac94e-129">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](../../data-mining/mining-structures-analysis-services-data-mining.md)|<span data-ttu-id="ac94e-130">Décrit les structures d'exploration de données et les objets d'exploration de données, y compris les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="ac94e-130">Describes mining structures and mining objects, including mining models.</span></span>|  
|[<span data-ttu-id="ac94e-131">Rôles de sécurité &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="ac94e-131">Security Roles  &#40;Analysis Services - Multidimensional Data&#41;</span></span>](security-roles-analysis-services-multidimensional-data.md)|<span data-ttu-id="ac94e-132">Décrit les rôles, le mécanisme de sécurité utilisé pour contrôler l'accès aux objets dans [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac94e-132">Describes a role, the security mechanism used to control access to objects in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="ac94e-133">Gestion des assemblys de modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="ac94e-133">Multidimensional Model Assemblies Management</span></span>](../multidimensional-model-assemblies-management.md)|<span data-ttu-id="ac94e-134">Décrit les assemblys, des collections de fonctions définies par l'utilisateur qui sont utilisées pour étendre les langages MDX et DMX dans [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac94e-134">Describes an assembly, a collection of user-defined functions used to extend the MDX and DMX languages, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac94e-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac94e-135">See Also</span></span>  
 <span data-ttu-id="ac94e-136">[Sources de données prises en charge &#40;SSAS multidimensionnel&#41;](../supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="ac94e-136">[Data Sources Supported &#40;SSAS Multidimensional&#41;](../supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="ac94e-137">[Solutions de modèles multidimensionnels &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="ac94e-137">[Multidimensional Model Solutions &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span></span>  
 [<span data-ttu-id="ac94e-138">Solutions d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="ac94e-138">Data Mining Solutions</span></span>](../../data-mining/data-mining-solutions.md)  
  
  
