---
title: Notions de base des requêtes MDX (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- statements [MDX]
- Multidimensional Expressions [Analysis Services], statements
- Multidimensional Expressions [Analysis Services], queries
- MDX [Analysis Services], statements
- MDX queries [Analysis Services]
- MDX [Analysis Services], queries
- queries [MDX]
ms.assetid: a560383b-bb58-472e-95f5-65d03d8ea08b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a2a9a4f564bc33cc7a1b41a1a4c766c7a76a2cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612569"
---
# <a name="mdx-query-fundamentals-analysis-services"></a><span data-ttu-id="13ed9-102">Principes de base des requêtes MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="13ed9-102">MDX Query Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="13ed9-103">La syntaxe MDX (Multidimensional Expressions) permet de lancer des requêtes sur des objets multidimensionnels, tels que des cubes, et de retourner des jeux de cellules multidimensionnels contenant les données du cube.</span><span class="sxs-lookup"><span data-stu-id="13ed9-103">Multidimensional Expressions (MDX) lets you query multidimensional objects, such as cubes, and return multidimensional cellsets that contain the cube's data.</span></span> <span data-ttu-id="13ed9-104">Cette rubrique et ses sous-rubriques donnent une vue d'ensemble des requêtes MDX.</span><span class="sxs-lookup"><span data-stu-id="13ed9-104">This topic and its subtopics provide an overview of MDX queries.</span></span>  
  
 <span data-ttu-id="13ed9-105">Les rubriques suivantes décrivent des requêtes MDX et les jeux de cellules qu'elles produisent, en fournissant des informations plus détaillées sur la syntaxe MDX de base.</span><span class="sxs-lookup"><span data-stu-id="13ed9-105">The following topics describe MDX queries and the cellsets they produce, and provide more detailed information about basic MDX syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13ed9-106">Pour plus d’informations sur les problèmes de performances liés aux calculs et requêtes MDX, consultez la section « écriture d’expressions MDX efficaces » dans le [Guide des performances SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="13ed9-106">For more information about performance issues related to MDX queries and calculations, see the section "Writing Efficient MDX" in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13ed9-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="13ed9-107">In This Section</span></span>  
  
|<span data-ttu-id="13ed9-108">Rubrique</span><span class="sxs-lookup"><span data-stu-id="13ed9-108">Topic</span></span>|<span data-ttu-id="13ed9-109">Description</span><span class="sxs-lookup"><span data-stu-id="13ed9-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="13ed9-110">Requête MDX de base &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-110">The Basic MDX Query &#40;MDX&#41;</span></span>](mdx-query-the-basic-query.md)|<span data-ttu-id="13ed9-111">Fournit des informations de base sur la syntaxe de l'instruction MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="13ed9-111">Provides basic syntax information for the MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="13ed9-112">Restriction de la requête avec des axes de requête et de secteur &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-112">Restricting the Query with Query and Slicer Axes &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-restricting-the-query.md)|<span data-ttu-id="13ed9-113">Décrit les axes de requête et de découpage ainsi que la manière de les spécifier.</span><span class="sxs-lookup"><span data-stu-id="13ed9-113">Describes what query and slicer axes are and how to specify them.</span></span>|  
|[<span data-ttu-id="13ed9-114">Définition d’un contexte de cube dans une requête &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-114">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)|<span data-ttu-id="13ed9-115">Indique le rôle de la clause FROM dans une instruction MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="13ed9-115">Provides a description of the purpose of the FROM clause in an MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="13ed9-116">Création de jeux nommés à l’aide d’expressions MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-116">Building Named Sets in MDX &#40;MDX&#41;</span></span>](mdx-named-sets-building-named-sets.md)|<span data-ttu-id="13ed9-117">Décrit le rôle des jeux nommés dans la syntaxe MDX et les techniques nécessaires pour les créer et les utiliser dans des requêtes MDX.</span><span class="sxs-lookup"><span data-stu-id="13ed9-117">Describes the purpose of named sets in MDX, and the techniques needed to create and use them in MDX queries.</span></span>|  
|[<span data-ttu-id="13ed9-118">Création de membres calculés dans MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-118">Building Calculated Members in MDX &#40;MDX&#41;</span></span>](mdx-calculated-members-building-calculated-members.md)|<span data-ttu-id="13ed9-119">Fournit des informations sur les membres calculés dans la syntaxe MDX, notamment sur les techniques nécessaires pour les créer et les utiliser dans des expressions MDX.</span><span class="sxs-lookup"><span data-stu-id="13ed9-119">Provides information about calculated members in MDX, including the techniques needed to create and use them in MDX expressions.</span></span>|  
|[<span data-ttu-id="13ed9-120">Création de calculs de cellules à l’aide de la syntaxe MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-120">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)|<span data-ttu-id="13ed9-121">Explique de manière détaillée le processus de création et l'utilisation des cellules calculées.</span><span class="sxs-lookup"><span data-stu-id="13ed9-121">Details the process of creating and using calculated cells.</span></span>|  
|[<span data-ttu-id="13ed9-122">Création et utilisation de valeurs de propriétés &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-122">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)|<span data-ttu-id="13ed9-123">Décrit en détail le processus de création et l'utilisation des propriétés de dimension, de niveau, de membre et de cellule.</span><span class="sxs-lookup"><span data-stu-id="13ed9-123">Details the process of creating and using dimension, level, member, and cell properties.</span></span>|  
|[<span data-ttu-id="13ed9-124">Manipulation de données &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-124">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)|<span data-ttu-id="13ed9-125">Décrit les principes de base qui sous-tendent la manipulation de données à l'aide d'extractions et de cumuls, ainsi que l'ordre de test et l'ordre de résolution dans la syntaxe MDX.</span><span class="sxs-lookup"><span data-stu-id="13ed9-125">Describes the basics behind manipulating data using drillthrough and rollup, and also describes pass order and solve order in MDX.</span></span>|  
|[<span data-ttu-id="13ed9-126">Modification de données &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-126">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)|<span data-ttu-id="13ed9-127">Décrit l'utilisation d'écritures différées pour modifier de manière temporaire ou permanente les données multidimensionnelles.</span><span class="sxs-lookup"><span data-stu-id="13ed9-127">Describes how to use writebacks to temporarily or permanently change multidimensional data.</span></span>|  
|[<span data-ttu-id="13ed9-128">Utilisation de variables et de paramètres &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-128">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="13ed9-129">Décrit le mode d'utilisation des variables et des paramètres dans des requêtes MDX.</span><span class="sxs-lookup"><span data-stu-id="13ed9-129">Describes how to use variables and parameters within MDX queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13ed9-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13ed9-130">See Also</span></span>  
 [<span data-ttu-id="13ed9-131">Référence MDX &#40;Multidimensional Expressions&#41;</span><span class="sxs-lookup"><span data-stu-id="13ed9-131">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
