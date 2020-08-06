---
title: Création de cellules calculées au niveau de la session | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- session-scoped calculated members [MDX]
ms.assetid: f2d14a89-6286-4e74-9afb-091076f93f21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 199de07778a153cd1bc40b5033d364e5e0055bd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604189"
---
# <a name="creating-session-scoped-calculated-cells"></a><span data-ttu-id="58f9c-102">Création de cellules calculées au niveau de la session</span><span class="sxs-lookup"><span data-stu-id="58f9c-102">Creating Session-Scoped Calculated Cells</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="58f9c-103">Cette syntaxe est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="58f9c-103">This syntax has been deprecated.</span></span> <span data-ttu-id="58f9c-104">Il est conseillé d'utiliser plutôt les assignations MDX.</span><span class="sxs-lookup"><span data-stu-id="58f9c-104">You should use MDX assignments should instead.</span></span> <span data-ttu-id="58f9c-105">Pour plus d’informations sur les assignations, consultez [Script MDX de base &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="58f9c-105">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="58f9c-106">Pour créer des cellules calculées mises à la disposition de l'ensemble des requêtes au cours de la même session, vous pouvez utiliser l'instruction [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) ou l'instruction [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) .</span><span class="sxs-lookup"><span data-stu-id="58f9c-106">To create calculated cells that are available to all queries in the same session, you can use either the [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) statement or the [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) statement.</span></span> <span data-ttu-id="58f9c-107">Ces deux instructions génèrent le même résultat.</span><span class="sxs-lookup"><span data-stu-id="58f9c-107">Both statements have the same result.</span></span>  
  
## <a name="create-cell-calculation-syntax"></a><span data-ttu-id="58f9c-108">Syntaxe de l'instruction CREATE CELL CALCULATION</span><span class="sxs-lookup"><span data-stu-id="58f9c-108">CREATE CELL CALCULATION Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="58f9c-109">Cette syntaxe est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="58f9c-109">This syntax has been deprecated.</span></span> <span data-ttu-id="58f9c-110">Il est conseillé d'utiliser plutôt les assignations MDX.</span><span class="sxs-lookup"><span data-stu-id="58f9c-110">You should use MDX assignments should instead.</span></span> <span data-ttu-id="58f9c-111">Pour plus d’informations sur les assignations, consultez [Script MDX de base &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="58f9c-111">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="58f9c-112">Utilisez la syntaxe suivante pour définir une cellule calculée au niveau de la session à l'aide de l'instruction CREATE CELL CALCULATION :</span><span class="sxs-lookup"><span data-stu-id="58f9c-112">Use the following syntax to use the CREATE CELL CALCULATION statement to define a session-scoped calculated cell:</span></span>  
  
```  
CREATE CELL CALCULATION Cube_Expression.<CREATE CELL CALCULATION body clause>  
  
<CREATE CELL CALCULATION body clause> ::=CellCalc_Identifier FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
## <a name="alter-cube-syntax"></a><span data-ttu-id="58f9c-113">Syntaxe de l'instruction ALTER CUBE</span><span class="sxs-lookup"><span data-stu-id="58f9c-113">ALTER CUBE Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="58f9c-114">Cette syntaxe est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="58f9c-114">This syntax has been deprecated.</span></span> <span data-ttu-id="58f9c-115">Il est conseillé d'utiliser plutôt les assignations MDX.</span><span class="sxs-lookup"><span data-stu-id="58f9c-115">You should use MDX assignments should instead.</span></span> <span data-ttu-id="58f9c-116">Pour plus d’informations sur les assignations, consultez [Script MDX de base &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="58f9c-116">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="58f9c-117">Utilisez la syntaxe suivante pour définir une cellule calculée au niveau de la session à l'aide de l'instruction ALTER CUBE :</span><span class="sxs-lookup"><span data-stu-id="58f9c-117">Use the following syntax to use the ALTER CUBE statement to define a session-scoped calculated cell:</span></span>  
  
```  
ALTER CUBE Cube_Identifier CREATE CELL CALCULATION  
FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
 <span data-ttu-id="58f9c-118">La valeur `String_Expression` contient une liste d'expressions de jeu MDX unidimensionnelles et orthogonales dont chacune doit prendre la valeur de l'une des catégories de jeux répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="58f9c-118">The `String_Expression` value contains a list of orthogonal, single-dimensional MDX set expressions, each of which must resolve to one of the categories of sets that are listed in the following table.</span></span>  
  
|<span data-ttu-id="58f9c-119">Category</span><span class="sxs-lookup"><span data-stu-id="58f9c-119">Category</span></span>|<span data-ttu-id="58f9c-120">Description</span><span class="sxs-lookup"><span data-stu-id="58f9c-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="58f9c-121">Jeu vide</span><span class="sxs-lookup"><span data-stu-id="58f9c-121">Empty set</span></span>|<span data-ttu-id="58f9c-122">Expression de jeu MDX qui prend la valeur d'un ensemble vide.</span><span class="sxs-lookup"><span data-stu-id="58f9c-122">An MDX set expression that resolves into an empty set.</span></span> <span data-ttu-id="58f9c-123">Dans ce cas, la portée de la cellule calculée est l'intégralité du cube.</span><span class="sxs-lookup"><span data-stu-id="58f9c-123">In this case, the scope of the calculated cell is the whole cube.</span></span>|  
|<span data-ttu-id="58f9c-124">Jeu à un seul membre</span><span class="sxs-lookup"><span data-stu-id="58f9c-124">Single member set</span></span>|<span data-ttu-id="58f9c-125">Expression de jeu MDX qui prend la valeur d'un seul membre.</span><span class="sxs-lookup"><span data-stu-id="58f9c-125">An MDX set expression that resolves into a single member.</span></span>|  
|<span data-ttu-id="58f9c-126">Jeu de membres de niveau</span><span class="sxs-lookup"><span data-stu-id="58f9c-126">Set of level members</span></span>|<span data-ttu-id="58f9c-127">Expression de jeu MDX qui prend la valeur des membres d'un même niveau.</span><span class="sxs-lookup"><span data-stu-id="58f9c-127">An MDX set expression that resolves into the members of a single level.</span></span> <span data-ttu-id="58f9c-128">L' *Level_Expression*en est un exemple.`Members`</span><span class="sxs-lookup"><span data-stu-id="58f9c-128">An example of this is the *Level_Expression*.`Members`</span></span> <span data-ttu-id="58f9c-129">Fonction MDX.</span><span class="sxs-lookup"><span data-stu-id="58f9c-129">MDX function.</span></span> <span data-ttu-id="58f9c-130">Pour inclure des membres calculés, utilisez l' *Level_Expression*.`AllMembers`</span><span class="sxs-lookup"><span data-stu-id="58f9c-130">To include calculated members, use the *Level_Expression*.`AllMembers`</span></span> <span data-ttu-id="58f9c-131">Fonction MDX.</span><span class="sxs-lookup"><span data-stu-id="58f9c-131">MDX function.</span></span><br /><br /> <span data-ttu-id="58f9c-132">Pour plus d’informations, consultez [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span><span class="sxs-lookup"><span data-stu-id="58f9c-132">For more information, see [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span></span>|  
|<span data-ttu-id="58f9c-133">Jeu de descendants</span><span class="sxs-lookup"><span data-stu-id="58f9c-133">Set of descendants</span></span>|<span data-ttu-id="58f9c-134">Expression de jeu MDX qui prend la valeur des descendants d'un membre spécifié.</span><span class="sxs-lookup"><span data-stu-id="58f9c-134">An MDX set expression that resolves into the descendants of a specified member.</span></span> <span data-ttu-id="58f9c-135">Par exemple `Descendants` , la fonction MDX (*Member_Expression*, *Level_Expression*, *Desc_Flag*).</span><span class="sxs-lookup"><span data-stu-id="58f9c-135">An example of this is the `Descendants`(*Member_Expression*, *Level_Expression*, *Desc_Flag*) MDX function.</span></span><br /><br /> <span data-ttu-id="58f9c-136">Pour plus d’informations, consultez [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span><span class="sxs-lookup"><span data-stu-id="58f9c-136">For more information, see [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58f9c-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58f9c-137">See Also</span></span>  
 [<span data-ttu-id="58f9c-138">Création de calculs de cellules à l’aide de la syntaxe MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="58f9c-138">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)  
  
  
