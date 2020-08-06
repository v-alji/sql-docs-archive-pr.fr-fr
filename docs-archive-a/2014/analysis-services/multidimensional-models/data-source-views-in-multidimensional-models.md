---
title: Vues de sources de données dans les modèles multidimensionnels | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data source views [Analysis Services]
- data source views [Analysis Services], about data source views
- SQL Server Analysis Services, data source views
- data source views [Analysis Services], multiple
- Analysis Services, data source views
- multiple data source views
- SSAS, data source views
ms.assetid: 4c12376f-4fc2-492b-9a00-93eec34571ed
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1aef6b6d716ec71ac082ca8b7c042492c1712b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708771"
---
# <a name="data-source-views-in-multidimensional-models"></a><span data-ttu-id="d640a-102">Vues de sources de données dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="d640a-102">Data Source Views in Multidimensional Models</span></span>
  <span data-ttu-id="d640a-103">Une vue de source de données (DSV) est une abstraction d'une source de données relationnelle qui devient la base des cubes et des dimensions que vous créez dans un projet multidimensionnel.</span><span class="sxs-lookup"><span data-stu-id="d640a-103">A data source view (DSV) is an abstraction of a relational data source that becomes the basis of the cubes and dimensions you create in a multidimensional project.</span></span> <span data-ttu-id="d640a-104">L'objectif d'une vue DSV est de vous donner le contrôle des structures de données utilisées dans votre projet, et de travailler indépendamment des sources de données sous-jacentes (par exemple, possibilité de renommer ou concaténer des colonnes sans modifier directement la source de données d'origine).</span><span class="sxs-lookup"><span data-stu-id="d640a-104">The purpose of a DSV is to give you control over the data structures used in your project, and to work independently of the underlying data sources (for example, the ability to rename or concatenate columns without directly modifying the original data source).</span></span>  
  
 <span data-ttu-id="d640a-105">Vous pouvez créer plusieurs vues de sources de données dans un projet ou une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sur une ou plusieurs sources de données et construire chacune d’elles en fonction de la configuration requise pour une solution différente.</span><span class="sxs-lookup"><span data-stu-id="d640a-105">You can build multiple data source views in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database on one or more data sources, and construct each one to satisfy the requirements for a different solution.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d640a-106">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="d640a-106">Related Tasks</span></span>  
 [<span data-ttu-id="d640a-107">Définition d’une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-107">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](defining-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-108">Ajout ou suppression de tables ou de vues dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-108">Adding or Removing Tables or Views in a Data Source View &#40;Analysis Services&#41;</span></span>](adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-109">Modifier les propriétés d’une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-109">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-110">Définir des relations logiques dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-110">Define Logical Relationships in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-relationships-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-111">Définir des clés primaires logiques dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-111">Define Logical Primary Keys in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-primary-keys-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-112">Définir des calculs nommés dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-112">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-113">Définir des requêtes nommées dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-113">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-114">Remplacer une table ou une requête nommée dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-114">Replace a Table or a Named Query in a Data Source View &#40;Analysis Services&#41;</span></span>](replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-115">Utiliser des diagrammes dans un concepteur de vues de sources de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-115">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
 [<span data-ttu-id="d640a-116">Explorer des données dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-116">Explore Data in a Data Source View &#40;Analysis Services&#41;</span></span>](explore-data-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-117">Supprimer une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-117">Delete a Data Source View &#40;Analysis Services&#41;</span></span>](delete-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="d640a-118">Actualiser le schéma dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-118">Refresh the Schema in a Data Source View &#40;Analysis Services&#41;</span></span>](refresh-the-schema-in-a-data-source-view-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="d640a-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d640a-119">See Also</span></span>  
 <span data-ttu-id="d640a-120">[Assistant génération de schéma &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="d640a-120">[Schema Generation Wizard &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span></span>  
 [<span data-ttu-id="d640a-121">Sources de données prises en charge &#40;SSAS multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="d640a-121">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
