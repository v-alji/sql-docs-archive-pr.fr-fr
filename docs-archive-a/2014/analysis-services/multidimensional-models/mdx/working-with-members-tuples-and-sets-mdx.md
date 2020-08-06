---
title: Utilisation de membres, de tuples et de jeux (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], tuples
- member keys [MDX]
- MDX [Analysis Services], sets
- calculated members [MDX]
- members [MDX]
- Multidimensional Expressions [Analysis Services], members
- named sets [MDX]
- Multidimensional Expressions [Analysis Services], tuples
- member functions [MDX]
- sets [MDX]
- MDX [Analysis Services], members
- member names [MDX]
- Multidimensional Expressions [Analysis Services], sets
- tuple functions
- tuples
- set functions [MDX]
ms.assetid: b6ec2439-caef-46d3-9fd7-5f4526cee334
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ce3bf2d5ad7df2b1cd74897b3b49c7cef97e8ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601132"
---
# <a name="working-with-members-tuples-and-sets-mdx"></a><span data-ttu-id="f9a01-102">Utilisation de membres, de tuples et de jeux (MDX)</span><span class="sxs-lookup"><span data-stu-id="f9a01-102">Working with Members, Tuples, and Sets (MDX)</span></span>
  <span data-ttu-id="f9a01-103">MDX fournit de nombreuses fonctions chargées de retourner un ou plusieurs membres, tuples ou jeux ou conçues pour agir sur un membre, un tuple ou un jeu donné.</span><span class="sxs-lookup"><span data-stu-id="f9a01-103">MDX provides numerous functions that return one or more members, tuples, or sets; or that act upon a member, tuple, or set.</span></span>  
  
## <a name="member-functions"></a><span data-ttu-id="f9a01-104">Fonctions de membre</span><span class="sxs-lookup"><span data-stu-id="f9a01-104">Member Functions</span></span>  
 <span data-ttu-id="f9a01-105">MDX intègre plusieurs fonctions à l'aide desquelles vous pouvez extraire des membres d'autres entités MDX, notamment des dimensions, des niveaux, des jeux ou des tuples.</span><span class="sxs-lookup"><span data-stu-id="f9a01-105">MDX provides several functions for retrieving members from other MDX entities, such as from dimensions, levels, sets, or tuples.</span></span> <span data-ttu-id="f9a01-106">Par exemple, la fonction [FirstChild](/sql/mdx/firstchild-mdx) est une fonction qui agit sur un membre et retourne un membre.</span><span class="sxs-lookup"><span data-stu-id="f9a01-106">For example, the [FirstChild](/sql/mdx/firstchild-mdx) function is a function that acts upon a member and returns a member.</span></span>  
  
 <span data-ttu-id="f9a01-107">Pour obtenir le premier membre enfant de la dimension Time, vous pouvez le définir explicitement, comme le montre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="f9a01-107">To obtain the first child member of the Time dimension, you can explicitly state the member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].[CY 2001] on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="f9a01-108">Vous pouvez également utiliser la fonction `FirstChild` pour retourner ce même membre, comme dans l'exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f9a01-108">You can also use the `FirstChild` function to return the same member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].FirstChild on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="f9a01-109">Pour plus d’informations sur les fonctions de membre MDX, consultez [Guide de référence des fonctions MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f9a01-109">For more information about MDX member functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="tuple-functions"></a><span data-ttu-id="f9a01-110">fonctions de tuple</span><span class="sxs-lookup"><span data-stu-id="f9a01-110">Tuple Functions</span></span>  
 <span data-ttu-id="f9a01-111">MDX fournit plusieurs fonctions permettant de retourner des tuples ; ces fonctions peuvent être utilisées partout où un tuple est accepté.</span><span class="sxs-lookup"><span data-stu-id="f9a01-111">MDX provides several functions that return tuples, and they can be used anywhere that a tuple is accepted.</span></span> <span data-ttu-id="f9a01-112">Par exemple, vous pouvez utiliser la fonction [Item &#40;Tuple&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx) pour extraire le premier tuple du jeu, ce qui est très utile lorsque vous savez qu’un jeu est composé d’un seul tuple et souhaitez fournir ce tuple à une fonction qui en nécessite un.</span><span class="sxs-lookup"><span data-stu-id="f9a01-112">For example, the [Item &#40;Tuple&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx) function can be used to extract the first tuple from set, which is very useful when you know that a set is composed of a single tuple and you want to supply that tuple to a function that requires a tuple.</span></span>  
  
 <span data-ttu-id="f9a01-113">L'exemple ci-dessous retourne le premier tuple du jeu de tuples dans l'axe des colonnes.</span><span class="sxs-lookup"><span data-stu-id="f9a01-113">The following example returns the first tuple from within the set of tuples on the column axis.</span></span>  
  
```  
SELECT {  
   ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2003]  
   )  
, ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2004]  
   )  
}.Item(0)  
ON COLUMNS   
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="f9a01-114">Pour plus d’informations sur les fonctions de tuple, consultez [Guide de référence des fonctions MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f9a01-114">For more information about tuple functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="set-functions"></a><span data-ttu-id="f9a01-115">Fonctions de jeu</span><span class="sxs-lookup"><span data-stu-id="f9a01-115">Set Functions</span></span>  
 <span data-ttu-id="f9a01-116">MDX fournit plusieurs fonctions qui retournent des jeux.</span><span class="sxs-lookup"><span data-stu-id="f9a01-116">MDX provides several functions that return sets.</span></span> <span data-ttu-id="f9a01-117">Pour extraire un jeu, il existe d'autres méthodes que la spécification explicite de tuples et leur mise entre accolades.</span><span class="sxs-lookup"><span data-stu-id="f9a01-117">Explicitly typing tuples and enclosing them in braces is not the only way to retrieve a set.</span></span> <span data-ttu-id="f9a01-118">Pour plus d’informations sur l’utilisation des fonctions de membre pour retourner un jeu, consultez [Concepts clés dans MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="f9a01-118">For more information about the members function to return a set, see [Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span></span> <span data-ttu-id="f9a01-119">Il existe beaucoup d'autres fonctions de jeu.</span><span class="sxs-lookup"><span data-stu-id="f9a01-119">There are many additional set functions.</span></span>  
  
 <span data-ttu-id="f9a01-120">L'opérateur deux points (:) permet d'utiliser l'ordre naturel des membres pour créer un jeu.</span><span class="sxs-lookup"><span data-stu-id="f9a01-120">The colon operator lets you use the natural order of members to create a set.</span></span> <span data-ttu-id="f9a01-121">Par exemple, le jeu illustré dans l'exemple suivant contient des tuples pour les trimestres 1 à 4 (Q1 et Q4) de l'année civile 2002.</span><span class="sxs-lookup"><span data-stu-id="f9a01-121">For example, the set shown in the following example contains tuples for the 1st through the 4th quarter of calendar year 2002.</span></span>  
  
```  
SELECT   
   {[Calendar Quarter].[Q1 CY 2002]:[Calendar Quarter].[Q4 CY 2002]}   
ON 0  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="f9a01-122">Si vous n'utilisez pas l'opérateur deux points pour créer le jeu, vous pouvez créer le même jeu de membres en spécifiant les tuples dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="f9a01-122">If you do not use the colon operator to create the set, you can create the same set of members by specifying the tuples in the following example.</span></span>  
  
```  
SELECT {  
   [Calendar Quarter].[Q1 CY 2002],   
   [Calendar Quarter].[Q2 CY 2002],   
   [Calendar Quarter].[Q3 CY 2002],   
   [Calendar Quarter].[Q4 CY 2002]  
   } ON 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="f9a01-123">L'opérateur deux points est une fonction inclusive.</span><span class="sxs-lookup"><span data-stu-id="f9a01-123">The colon operator is an inclusive function.</span></span> <span data-ttu-id="f9a01-124">Les membres situés de part et d'autre de celui-ci sont inclus dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="f9a01-124">The members on both sides of the colon operator are included in the resulting set.</span></span>  
  
 <span data-ttu-id="f9a01-125">Pour plus d’informations sur les fonctions de jeu, consultez [Guide de référence des fonctions MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f9a01-125">For more information about set functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="array-functions"></a><span data-ttu-id="f9a01-126">Fonctions de tableau</span><span class="sxs-lookup"><span data-stu-id="f9a01-126">Array Functions</span></span>  
 <span data-ttu-id="f9a01-127">Une fonction de tableau agit sur un jeu et retourne un tableau.</span><span class="sxs-lookup"><span data-stu-id="f9a01-127">An array function acts upon a set and returns an array.</span></span> <span data-ttu-id="f9a01-128">Pour plus d’informations sur les fonctions de tableau, consultez [Guide de référence des fonctions MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f9a01-128">For more information about array functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="hierarchy-functions"></a><span data-ttu-id="f9a01-129">Fonctions de hiérarchie</span><span class="sxs-lookup"><span data-stu-id="f9a01-129">Hierarchy Functions</span></span>  
 <span data-ttu-id="f9a01-130">Une fonction de hiérarchie retourne une hiérarchie en agissant sur un membre, un niveau, une hiérarchie ou une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f9a01-130">A hierarchy function returns a hierarchy by acting upon a member, level, hierarchy, or string.</span></span> <span data-ttu-id="f9a01-131">Pour plus d’informations sur les fonctions de hiérarchie, consultez [Guide de référence des fonctions MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f9a01-131">For more information about hierarchy functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="level-functions"></a><span data-ttu-id="f9a01-132">Fonctions de niveau</span><span class="sxs-lookup"><span data-stu-id="f9a01-132">Level Functions</span></span>  
 <span data-ttu-id="f9a01-133">Une fonction de niveau retourne un niveau en agissant sur un membre, un niveau ou une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f9a01-133">A level function returns a level by acting upon a member, level, or string.</span></span> <span data-ttu-id="f9a01-134">Pour plus d’informations sur les fonctions de niveau, consultez [Guide de référence des fonctions MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f9a01-134">For more information about level functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="logical-functions"></a><span data-ttu-id="f9a01-135">Fonctions logiques</span><span class="sxs-lookup"><span data-stu-id="f9a01-135">Logical Functions</span></span>  
 <span data-ttu-id="f9a01-136">Une fonction logique agit sur une expression MDX pour retourner des informations sur les tuples, les membres ou les jeux au sein de l'expression.</span><span class="sxs-lookup"><span data-stu-id="f9a01-136">A logical function acts upon a MDX expression to return information about the tuples, members, or sets in the expression.</span></span> <span data-ttu-id="f9a01-137">Par exemple, la fonction [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx) évalue si une expression a retourné une valeur de cellule vide.</span><span class="sxs-lookup"><span data-stu-id="f9a01-137">For example, the [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx) function evaluates whether an expression has returned an empty cell value.</span></span> <span data-ttu-id="f9a01-138">Pour plus d’informations sur les fonctions logiques, consultez [Guide de référence des fonctions MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f9a01-138">For more information about logical functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="numeric-functions"></a><span data-ttu-id="f9a01-139">Fonctions numériques</span><span class="sxs-lookup"><span data-stu-id="f9a01-139">Numeric Functions</span></span>  
 <span data-ttu-id="f9a01-140">Une fonction numérique agit sur une expression MDX pour retourner une valeur scalaire.</span><span class="sxs-lookup"><span data-stu-id="f9a01-140">A numeric function acts upon a MDX expression to return a scalar value.</span></span> <span data-ttu-id="f9a01-141">Par exemple, la fonction [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) retourne une valeur scalaire calculée en agrégeant des mesures sur les tuples dans un jeu spécifique.</span><span class="sxs-lookup"><span data-stu-id="f9a01-141">For example, the [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) function returns a scalar value calculated by aggregating measures over the tuples in a specified set.</span></span> <span data-ttu-id="f9a01-142">Pour plus d’informations sur les fonctions numériques, consultez [Guide de référence des fonctions MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f9a01-142">For more information about numeric functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="string-functions"></a><span data-ttu-id="f9a01-143">Fonctions de chaîne</span><span class="sxs-lookup"><span data-stu-id="f9a01-143">String Functions</span></span>  
 <span data-ttu-id="f9a01-144">Une fonction de chaîne agit sur une expression MDX pour retourner une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f9a01-144">A string function acts upon a MDX expression to return a string.</span></span> <span data-ttu-id="f9a01-145">Par exemple, la fonction [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx) retourne une valeur de chaîne qui contient le nom unique d’une dimension, d’une hiérarchie, d’un niveau ou d’un membre.</span><span class="sxs-lookup"><span data-stu-id="f9a01-145">For example, the [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx) function returns a string value containing the unique name of a dimension, hierarchy, level, or member.</span></span> <span data-ttu-id="f9a01-146">Pour plus d’informations sur les fonctions de chaîne, consultez [Guide de référence des fonctions MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="f9a01-146">For more information about string functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a01-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9a01-147">See Also</span></span>  
 <span data-ttu-id="f9a01-148">[Concepts clés dans MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f9a01-148">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="f9a01-149">[Notions de base des requêtes MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f9a01-149">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="f9a01-150">Guide de référence des fonctions MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f9a01-150">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
