---
title: Génération de calculs de cellules dans MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculated cells [MDX]
- queries [MDX], cell calculations
- cells [MDX]
- MDX [Analysis Services], calculations
- calculation subcubes [MDX]
- calculated values [MDX]
- Multidimensional Expressions [Analysis Services], cell calculations
ms.assetid: 068aea63-d419-4791-a960-3d74e76f808e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ab3219850c49c2ec16a12aab3ba7db67e9a8721
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703331"
---
# <a name="building-cell-calculations-in-mdx-mdx"></a><span data-ttu-id="2d107-102">Création de calculs de cellules à l'aide de la syntaxe MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="2d107-102">Building Cell Calculations in MDX (MDX)</span></span>
  <span data-ttu-id="2d107-103">MDX (Multidimensional Expressions) propose un certain nombre d'outils qui vous permettent de générer des valeurs calculées comme des membres calculés, des cumuls personnalisés et des membres personnalisés.</span><span class="sxs-lookup"><span data-stu-id="2d107-103">Multidimensional Expressions (MDX) provides you with a number of tools for generating calculated values, such as calculated members, custom rollups, and custom members.</span></span> <span data-ttu-id="2d107-104">Cependant, il est difficile d'affecter un jeu de cellules spécifique (voire une cellule unique) à l'aide de ces outils.</span><span class="sxs-lookup"><span data-stu-id="2d107-104">However, using these features to affect a specific set of cells, or a single cell for that matter, would be difficult.</span></span>  
  
 <span data-ttu-id="2d107-105">Pour générer des valeurs calculées en particulier pour des cellules, vous devez utiliser la fonctionnalité de cellules calculées de MDX.</span><span class="sxs-lookup"><span data-stu-id="2d107-105">To generated calculated values for specifically for cells, you need to use the calculated cells feature in MDX.</span></span> <span data-ttu-id="2d107-106">Les cellules calculées permettent de définir une « tranche » de cellules, appelée *sous-cube de calcul*, et d’appliquer une formule à chacune des cellules de ce sous-cube de calcul, sous réserve d’une condition facultative qui peut être appliquée à chaque cellule.</span><span class="sxs-lookup"><span data-stu-id="2d107-106">Calculated cells let you define a specific slice of cells, called a *calculation subcube*, and apply a formula to each and every cell within the calculation subcube, subject to an optional condition that can be applied to each cell.</span></span>  
  
 <span data-ttu-id="2d107-107">Les cellules calculées proposent également des fonctionnalités complexes (par exemple, des formules de recherche d’objectif, telles qu'elles sont utilisées dans les KPI, ou des formules d'analyse spéculative).</span><span class="sxs-lookup"><span data-stu-id="2d107-107">Calculated cells also offer complex functionality, such as goal-seeking formulas, as used in KPIs, or speculative analysis formulas.</span></span> <span data-ttu-id="2d107-108">Ce niveau de fonctionnalité provient de la fonctionnalité d’ordre de test dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] qui permet d’effectuer des passes récursives avec des cellules calculées, avec des formules de calcul appliquées à des passes spécifiques dans l’ordre de passage.</span><span class="sxs-lookup"><span data-stu-id="2d107-108">This level of functionality comes from the pass order feature in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that allows recursive passes to be made with calculated cells, with calculation formulas applied at specific passes in the pass order.</span></span> <span data-ttu-id="2d107-109">Pour plus d’informations sur l’ordre de passage, consultez [Présentation des concepts d’ordre de passage et d’ordre de résolution &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="2d107-109">For more information on pass order, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="2d107-110">Du point de vue de leur portée, les cellules calculées sont semblables aux jeux nommés et aux membres calculés en ce sens qu'elles peuvent créées temporairement pour la durée d'une session ou d'une seule requête, ou encore être globalement mises à la disposition des utilisateurs dans le cadre d'un cube :</span><span class="sxs-lookup"><span data-stu-id="2d107-110">In terms of creation scope, calculated cells are similar to both named sets and calculated members in that calculated cells can be temporarily created for the lifetime of either a session or a single query, or made globally available as part of a cube:</span></span>  
  
-   <span data-ttu-id="2d107-111">**Étendue de requête** Pour créer une cellule calculée définie en tant que partie d’une requête MDX, et dont l’étendue est donc limitée à la requête, utilisez le mot clé WITH.</span><span class="sxs-lookup"><span data-stu-id="2d107-111">**Query-scoped** To create a calculated cell that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="2d107-112">Vous pouvez ensuite utiliser la cellule calculée au sein d'une instruction MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="2d107-112">You can then use the calculated cell within an MDX SELECT statement.</span></span> <span data-ttu-id="2d107-113">De cette manière, vous pouvez modifier la cellule calculée créée à l'aide du mot clé `WITH` sans porter atteinte à l'instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="2d107-113">Using this approach, the calculated cell created by using the `WITH` keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="2d107-114">Pour plus d’informations sur l’utilisation du mot clé WITH pour la création de membres calculés, consultez [Création de calculs de cellules au niveau de la requête &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span><span class="sxs-lookup"><span data-stu-id="2d107-114">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span></span>  
  
-   <span data-ttu-id="2d107-115">**Étendue de session** Pour créer un membre calculé dont l’étendue est plus étendue que le contexte de la requête, c’est-à-dire dont l’étendue est la durée de vie de la session MDX, vous devez utiliser l’instruction CREATE CELL CALCULATION ou ALTER CUBE.</span><span class="sxs-lookup"><span data-stu-id="2d107-115">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use either the CREATE CELL CALCULATION or ALTER CUBE statement.</span></span>  
  
     <span data-ttu-id="2d107-116">Pour plus d’informations sur l’utilisation de l’instruction CREATE CELL CALCULATION ou ALTER CUBE afin de créer des cellules calculées dans une session, consultez [Création de cellules calculées au niveau de la session](mdx-cell-calculations-session-scoped-calculated-cells.md).</span><span class="sxs-lookup"><span data-stu-id="2d107-116">For more information about how to use either the CREATE CELL CALCULATION or ALTER CUBE statement to create calculated cells in a session, see [Creating Session-Scoped Calculated Cells](mdx-cell-calculations-session-scoped-calculated-cells.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d107-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d107-117">See Also</span></span>  
 <span data-ttu-id="2d107-118">[Instruction ALTER CUBE &#40;&#41;MDX](/sql/mdx/mdx-data-definition-alter-cube) </span><span class="sxs-lookup"><span data-stu-id="2d107-118">[ALTER CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-alter-cube) </span></span>  
 <span data-ttu-id="2d107-119">[Instruction CREATe CELL CALCULation &#40;&#41;MDX](/sql/mdx/mdx-data-definition-create-cell-calculation) </span><span class="sxs-lookup"><span data-stu-id="2d107-119">[CREATE CELL CALCULATION Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation) </span></span>  
 <span data-ttu-id="2d107-120">[Création de calculs de cellules d’étendue de requête &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="2d107-120">[Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 [<span data-ttu-id="2d107-121">Principes de base des requêtes MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2d107-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
