---
title: Établissement d’un contexte de cube dans une requête (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], MDX
- MDX [Analysis Services], cube context
- SELECT statement [MDX]
- Multidimensional Expressions [Analysis Services], cube context
- queries [MDX], cube context
ms.assetid: 79d6a1e8-2825-4eb9-97df-5071aecae8f0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72ae6e19f879651feb47841d70b444e9f845c74e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694755"
---
# <a name="establishing-cube-context-in-a-query-mdx"></a><span data-ttu-id="808c2-102">Définition d'un contexte de cube dans une requête (MDX)</span><span class="sxs-lookup"><span data-stu-id="808c2-102">Establishing Cube Context in a Query (MDX)</span></span>
  <span data-ttu-id="808c2-103">Chaque requête MDX s'exécute dans un contexte de cube spécifié.</span><span class="sxs-lookup"><span data-stu-id="808c2-103">Every MDX query runs within a specified cube context.</span></span> <span data-ttu-id="808c2-104">Ce contexte définit les membres qui sont évalués par les expressions incluses dans la requête.</span><span class="sxs-lookup"><span data-stu-id="808c2-104">This context defines the members that are evaluated by the expressions within the query.</span></span>  
  
 <span data-ttu-id="808c2-105">Dans l'instruction SELECT, la clause FROM détermine le contexte de cube.</span><span class="sxs-lookup"><span data-stu-id="808c2-105">In the SELECT statement, the FROM clause determines the cube context.</span></span> <span data-ttu-id="808c2-106">Ce contexte peut être le cube complet ou seulement un sous-cube de ce cube.</span><span class="sxs-lookup"><span data-stu-id="808c2-106">This context can be the whole cube or just a subcube from that cube.</span></span> <span data-ttu-id="808c2-107">Après avoir spécifié le contexte de cube à l'aide de la clause FROM, vous pouvez utiliser d'autres fonctions pour développer ou restreindre ce contexte.</span><span class="sxs-lookup"><span data-stu-id="808c2-107">Having specified cube context through the FROM clause, you can use additional functions to expand or restrict that context.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="808c2-108">Les instructions SCOPE et CALCULATE vous permettent également de gérer le contexte de cube à l'intérieur d'un script MDX.</span><span class="sxs-lookup"><span data-stu-id="808c2-108">The SCOPE and CALCULATE statements also let you manage cube context from within an MDX script.</span></span> <span data-ttu-id="808c2-109">Pour plus d’informations, consultez [Principes de base des scripts MDX &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="808c2-109">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
## <a name="from-clause-syntax"></a><span data-ttu-id="808c2-110">Syntaxe de la clause FROM</span><span class="sxs-lookup"><span data-stu-id="808c2-110">FROM Clause Syntax</span></span>  
 <span data-ttu-id="808c2-111">La syntaxe suivante décrit la clause FROM :</span><span class="sxs-lookup"><span data-stu-id="808c2-111">The following syntax describes the FROM clause:</span></span>  
  
```  
<SELECT subcube clause> ::=  
   Cube_Identifier |   
   (SELECT [  
      * |   
      ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]   
   FROM <SELECT subcube clause> <SELECT slicer axis clause> )  
```  
  
 <span data-ttu-id="808c2-112">Dans cette syntaxe, notez que c'est la clause `<SELECT subcube clause>` qui décrit le cube ou le sous-cube sur lequel s'exécute l'instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="808c2-112">In this syntax, notice that it is the `<SELECT subcube clause>` clause that describes the cube or subcube on which the SELECT statement is executed.</span></span>  
  
 <span data-ttu-id="808c2-113">Un exemple simple de clause FROM pourrait s'exécuter sur l'ensemble du cube Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="808c2-113">A simple example of a FROM clause would be one that runs against the entire Adventure Works sample cube.</span></span> <span data-ttu-id="808c2-114">Une telle clause FROM aurait le format suivant :</span><span class="sxs-lookup"><span data-stu-id="808c2-114">Such a FROM clause would have the following format:</span></span>  
  
```  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="808c2-115">Pour plus d’informations sur la clause FROM de l’instruction MDX SELECT, consultez [Instruction SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="808c2-115">For more information about the FROM clause in the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="refining-the-context"></a><span data-ttu-id="808c2-116">Affinement du contexte</span><span class="sxs-lookup"><span data-stu-id="808c2-116">Refining the Context</span></span>  
 <span data-ttu-id="808c2-117">Bien que la clause FROM spécifie le contexte de cube comme dans un cube unique, cela ne doit pas vous empêcher d'utiliser simultanément des données issues de plusieurs cubes.</span><span class="sxs-lookup"><span data-stu-id="808c2-117">Although the FROM clause specifies the cube context as within a single cube, this does not have to limit you from working with data from more than one cube at a time.</span></span>  
  
 <span data-ttu-id="808c2-118">Vous pouvez utiliser la fonction [LookupCube](/sql/mdx/lookupcube-mdx) MDX pour récupérer des données de cubes en dehors du contexte des cubes.</span><span class="sxs-lookup"><span data-stu-id="808c2-118">You can use the MDX [LookupCube](/sql/mdx/lookupcube-mdx) function to retrieve data from cubes outside the cube context.</span></span> <span data-ttu-id="808c2-119">De plus, il existe des fonctions telles que [Filter](/sql/mdx/filter-mdx) qui permettent de restreindre temporairement le contexte durant l’évaluation de la requête.</span><span class="sxs-lookup"><span data-stu-id="808c2-119">Additionally, functions such as the [Filter](/sql/mdx/filter-mdx) function, are available that allow temporary restriction of the context while evaluating the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="808c2-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="808c2-120">See Also</span></span>  
 [<span data-ttu-id="808c2-121">Principes de base des requêtes MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="808c2-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
