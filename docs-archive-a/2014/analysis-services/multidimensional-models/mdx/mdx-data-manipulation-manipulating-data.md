---
title: Manipulation de données (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], data manipulation
- data manipulation [MDX]
- Multidimensional Expressions [Analysis Services], data manipulation
ms.assetid: 4865192e-f46b-4ce5-b51c-9e08dbad5b85
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a1de8b9a3431d79573cd916fa7273b6d8fa7f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605810"
---
# <a name="manipulating-data-mdx"></a><span data-ttu-id="b007d-102">Manipulation de données (MDX)</span><span class="sxs-lookup"><span data-stu-id="b007d-102">Manipulating Data (MDX)</span></span>

<span data-ttu-id="b007d-103">La syntaxe MDX (Multidimensional Expressions) permet de manipuler les données de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="b007d-103">Multidimensional Expressions (MDX) can be used to manipulate the data in a variety of ways.</span></span> <span data-ttu-id="b007d-104">L’article présenté dans cet article couvre certains des concepts plus avancés de manipulation de données dans le langage MDX.</span><span class="sxs-lookup"><span data-stu-id="b007d-104">The article listed in this article cover some of the more advanced concepts of data manipulation in the MDX language.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b007d-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b007d-105">In This Section</span></span>

|<span data-ttu-id="b007d-106">Rubrique</span><span class="sxs-lookup"><span data-stu-id="b007d-106">Topic</span></span>|<span data-ttu-id="b007d-107">Description</span><span class="sxs-lookup"><span data-stu-id="b007d-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b007d-108">Utilisation de l’instruction DRILLTHROUGH pour récupérer des données sources &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b007d-108">Using DRILLTHROUGH to Retrieve Source Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-retrieve-source-data-using-drillthrough.md)|<span data-ttu-id="b007d-109">Explique comment utiliser l’instruction MDX [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) pour récupérer les jeux de lignes des données sources d’une cellule dans une source de données multidimensionnelles.</span><span class="sxs-lookup"><span data-stu-id="b007d-109">Discusses the use of the MDX [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) statement to retrieve the rowsets of source data applicable to a cell in a multidimensional data source</span></span>|  
|[<span data-ttu-id="b007d-110">Utilisation de la fonction RollupChildren &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b007d-110">Working with the RollupChildren Function &#40;MDX&#41;</span></span>](mdx-data-manipulation-rollupchildren-function.md)|<span data-ttu-id="b007d-111">Décrit l’impact de la MDX [RollupChildren](/sql/mdx/rollupchildren-mdx)</span><span class="sxs-lookup"><span data-stu-id="b007d-111">Discusses the impact of the MDX [RollupChildren](/sql/mdx/rollupchildren-mdx)</span></span>
|[<span data-ttu-id="b007d-112">Présentation des concepts d’ordre de passage et d’ordre de résolution &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b007d-112">Understanding Pass Order and Solve Order &#40;MDX&#41;</span></span>](mdx-data-manipulation-understanding-pass-order-and-solve-order.md)|<span data-ttu-id="b007d-113">Décrit en détail les concepts de l'ordre de résolution et la manière dont cette fonction affecte les expressions, instructions et scripts MDX.</span><span class="sxs-lookup"><span data-stu-id="b007d-113">Details the concepts of solve order, and how this feature affects MDX expressions, statements, and scripts.</span></span>|  

<!-- ??

|[Script for Search and Replace] function on the analysis of multidimensional data.|

GeneMi is removing this commented row because it is unclear what article its link meant to link to.
Also, I had to add its leading '|' character, for consistency to aid bulk automated updated to our markdown source code.

GeneMi , 2019/01/19
-->

## <a name="see-also"></a><span data-ttu-id="b007d-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b007d-114">See Also</span></span>

[<span data-ttu-id="b007d-115">Principes de base des requêtes MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b007d-115">MDX Query Fundamentals (Analysis Services)</span></span>](mdx-query-fundamentals-analysis-services.md)
