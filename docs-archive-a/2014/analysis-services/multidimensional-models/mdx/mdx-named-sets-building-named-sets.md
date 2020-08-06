---
title: Génération de jeux nommés dans MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], named sets
- named sets [MDX]
- sets [MDX]
- MDX [Analysis Services], named sets
- queries [MDX], named sets
- set expressions [MDX]
ms.assetid: 213b0035-e96d-4ba0-83f2-ded206905603
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91296f8c5d47afb15c67f0b60435c7f961734573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698646"
---
# <a name="building-named-sets-in-mdx-mdx"></a><span data-ttu-id="d87a7-102">Création de jeux nommés à l'aide d'expressions MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="d87a7-102">Building Named Sets in MDX (MDX)</span></span>
  <span data-ttu-id="d87a7-103">Une expression d'ensemble peut être une déclaration assez longue, complexe et donc difficile à assimiler.</span><span class="sxs-lookup"><span data-stu-id="d87a7-103">A set expression can be a lengthy and complex declaration, and therefore be difficult to follow or understand.</span></span> <span data-ttu-id="d87a7-104">Ou bien, il est possible que vous l'utilisiez si souvent qu'il devient pénible de la redéfinir à chaque fois.</span><span class="sxs-lookup"><span data-stu-id="d87a7-104">Or, a set expression may be used so frequently that repeatedly defining the set becomes burdensome.</span></span> <span data-ttu-id="d87a7-105">Pour faciliter l’utilisation d’une expression longue, complexe ou fréquemment utilisée, MDX (Multidimensional Expressions) vous permet de traiter une telle expression sous forme de *jeu nommé*.</span><span class="sxs-lookup"><span data-stu-id="d87a7-105">To help make working with a lengthy, complex or commonly used expression easier, Multidimensional Expressions (MDX) lets you such an expression as a *named set*.</span></span>  
  
 <span data-ttu-id="d87a7-106">Un jeu nommé est essentiellement une expression d'ensemble à laquelle un alias a été attribué.</span><span class="sxs-lookup"><span data-stu-id="d87a7-106">Basically, a named set is a set expression to which an alias has been assigned.</span></span> <span data-ttu-id="d87a7-107">Il peut comprendre les membres ou les fonctions pouvant être normalement intégrées dans un jeu.</span><span class="sxs-lookup"><span data-stu-id="d87a7-107">A named set can incorporate any members or functions that can ordinarily be incorporated into a set.</span></span> <span data-ttu-id="d87a7-108">MDX traitant l'alias du jeu nommé comme une expression d'ensemble, vous pouvez utiliser cet alias où une telle expression est acceptée.</span><span class="sxs-lookup"><span data-stu-id="d87a7-108">Because MDX treats the named set alias as a set expression, you can use that alias anywhere a set expression is accepted.</span></span>  
  
 <span data-ttu-id="d87a7-109">Vous pouvez définir pour un jeu nommé l'un des contextes suivants :</span><span class="sxs-lookup"><span data-stu-id="d87a7-109">You can define a named set to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="d87a7-110">**Étendue de requête** Pour créer un jeu nommé défini en tant que partie d’une requête MDX, et dont l’étendue est donc limitée à la requête, utilisez le mot clé WITH.</span><span class="sxs-lookup"><span data-stu-id="d87a7-110">**Query-scoped** To create a named set that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="d87a7-111">Vous pouvez ensuite utiliser le jeu nommé au sein d'une instruction MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="d87a7-111">You can then use the named set within an MDX SELECT statement.</span></span> <span data-ttu-id="d87a7-112">De la sorte, vous pouvez modifier le jeu nommé créé à l'aide du mot clé WITH sans porter atteinte à l'instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="d87a7-112">Using this approach, the named set created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="d87a7-113">Pour plus d’informations sur l’utilisation du mot clé WITH pour la création de jeux nommés, consultez [Création de jeux nommés d’étendue de requête &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d87a7-113">For more information about how to use the WITH keyword to create named sets, see [Creating Query-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span></span>  
  
-   <span data-ttu-id="d87a7-114">**Étendue de session** Pour créer un jeu nommé dont l’étendue est plus vaste que le contexte de la requête, c’est-à-dire dont l’étendue est la durée de la session MDX, utilisez l’instruction CREATE SET.</span><span class="sxs-lookup"><span data-stu-id="d87a7-114">**Session-scoped** To create a named set whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE SET statement.</span></span> <span data-ttu-id="d87a7-115">Un jeu nommé défini à l'aide de l'instruction CREATE SET est disponible pour toutes les requêtes MDX de cette session.</span><span class="sxs-lookup"><span data-stu-id="d87a7-115">A named set defined by using the CREATE SET statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="d87a7-116">L'instruction CREATE SET est appropriée par exemple dans le cas d'une application cliente qui réutilise le même jeu dans différentes requêtes.</span><span class="sxs-lookup"><span data-stu-id="d87a7-116">The CREATE SET statement makes sense, for example, in a client application that consistently reuses a set in a variety of queries.</span></span>  
  
     <span data-ttu-id="d87a7-117">Pour plus d’informations sur l’utilisation de l’instruction CREATE SET pour la création de jeux nommés dans une session, consultez [Création de jeux nommés dans l’étendue de session &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d87a7-117">For more information about how to use the CREATE SET statement to create named sets in a session, see [Creating Session-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d87a7-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d87a7-118">See Also</span></span>  
 <span data-ttu-id="d87a7-119">[Instruction SELECT &#40;&#41;MDX](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="d87a7-119">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 <span data-ttu-id="d87a7-120">[Instruction CREATe SET &#40;&#41;MDX](/sql/mdx/mdx-data-definition-create-set) </span><span class="sxs-lookup"><span data-stu-id="d87a7-120">[CREATE SET Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-set) </span></span>  
 [<span data-ttu-id="d87a7-121">Principes de base des requêtes MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d87a7-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
