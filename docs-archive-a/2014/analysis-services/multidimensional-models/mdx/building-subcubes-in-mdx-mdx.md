---
title: Création de sous-cubes dans MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], subcubes
- subcubes [MDX]
- filtered views [MDX]
- MDX [Analysis Services], subcubes
- Multidimensional Expressions [Analysis Services], subcubes
- CREATE SUBCUBE statement
ms.assetid: 5403a62b-99ac-4d83-b02a-89bf78bf0f46
author: minewiskan
ms.author: owend
ms.openlocfilehash: 653b4d30aa86f52179c7b13619ac4347aa65c339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611370"
---
# <a name="building-subcubes-in-mdx-mdx"></a><span data-ttu-id="58210-102">Création de sous-cubes à l'aide de la syntaxe MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="58210-102">Building Subcubes in MDX (MDX)</span></span>
  <span data-ttu-id="58210-103">Un sous-cube est un sous-jeu d'un cube représentant une vue filtrée des données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="58210-103">A subcube is a subset of a cube on representing a filtered view of the underlying data.</span></span> <span data-ttu-id="58210-104">En limitant le cube à un sous-cube, vous pouvez améliorer les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="58210-104">By limiting the cube to a subcube, you can improve query performance.</span></span>  
  
 <span data-ttu-id="58210-105">Pour définir un sous-cube, vous devez utiliser l’instruction [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) , comme décrit dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="58210-105">To define a subcube, you use the [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) statement, as described in this topic.</span></span>  
  
## <a name="create-subcube-syntax"></a><span data-ttu-id="58210-106">Syntaxe CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="58210-106">CREATE SUBCUBE Syntax</span></span>  
 <span data-ttu-id="58210-107">Utilisez la syntaxe suivante pour créer un sous-cube :</span><span class="sxs-lookup"><span data-stu-id="58210-107">Use the following syntax to create a subcube:</span></span>  
  
```  
CREATE SUBCUBE Subcube_Identifier AS Subcube_Expression  
```  
  
 <span data-ttu-id="58210-108">La syntaxe CREATE SUBCUBE est relativement simple.</span><span class="sxs-lookup"><span data-stu-id="58210-108">The CREATE SUBCUBE syntax is fairly simple.</span></span> <span data-ttu-id="58210-109">Le paramètre *Subcube_Identifier* identifie le cube sur lequel doit se baser le sous-cube.</span><span class="sxs-lookup"><span data-stu-id="58210-109">The *Subcube_Identifier* parameter identifies the cube on which the subcube will be based.</span></span> <span data-ttu-id="58210-110">Le paramètre *Subcube_Expression* sélectionne la partie du cube qui deviendra le sous-cube.</span><span class="sxs-lookup"><span data-stu-id="58210-110">The *Subcube_Expression* parameter selects the part of the cube that will become the subcube</span></span>  
  
 <span data-ttu-id="58210-111">Une fois le sous-cube créé, il devient le contexte de toutes les requêtes MDX jusqu’à la fermeture de la session ou l’exécution de l’instruction [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) .</span><span class="sxs-lookup"><span data-stu-id="58210-111">After you create a subcube, that subcube becomes the context for all MDX queries until either the session closes or you run the [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) statement.</span></span>  
  
### <a name="what-a-subcube-contains"></a><span data-ttu-id="58210-112">Éléments contenus dans un sous-cube</span><span class="sxs-lookup"><span data-stu-id="58210-112">What a Subcube Contains</span></span>  
 <span data-ttu-id="58210-113">Même si l'instruction CREATE SUBCUBE est relativement simple à utiliser, l'instruction proprement dite n'indique pas explicitement tous les membres qui font partie d'un sous-cube.</span><span class="sxs-lookup"><span data-stu-id="58210-113">Although the CREATE SUBCUBE statement is fairly simple to use, the statement itself does not explicitly show all the members that become part of a subcube.</span></span> <span data-ttu-id="58210-114">Lors de la définition d'un sous-cube, les règles suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="58210-114">In defining a subcube, the following rules apply:</span></span>  
  
-   <span data-ttu-id="58210-115">Si vous incluez le membre `(All)` d'une hiérarchie, vous incluez tous les membres qu'elle contient.</span><span class="sxs-lookup"><span data-stu-id="58210-115">If you include the `(All)` member of a hierarchy, you include every member of that hierarchy.</span></span>  
  
-   <span data-ttu-id="58210-116">Si vous incluez un membre, vous incluez également ses ascendants et ses descendants.</span><span class="sxs-lookup"><span data-stu-id="58210-116">If you include any member, you include that member's ascendants and descendants.</span></span>  
  
-   <span data-ttu-id="58210-117">Si vous incluez tous les membres d'un niveau, vous incluez tous les membres de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="58210-117">If you include every member from a level, you include all members from the hierarchy.</span></span> <span data-ttu-id="58210-118">Les membres des autres hiérarchies seront exclus s'ils ne possèdent pas de membre de ce niveau (par exemple, une hiérarchie déséquilibrée telle qu'une ville qui ne contient aucun client).</span><span class="sxs-lookup"><span data-stu-id="58210-118">Members from other hierarchies will be excluded if those members do not exist with members from the level (for example, an unbalanced hierarchy such as a city that does not contain customers).</span></span>  
  
-   <span data-ttu-id="58210-119">Un sous-cube contient toujours tous les membres `(All)` du cube.</span><span class="sxs-lookup"><span data-stu-id="58210-119">A subcube will always contain every `(All)` member from the cube.</span></span>  
  
 <span data-ttu-id="58210-120">En outre, les valeurs d'agrégation contenues dans le sous-cube sont totalisées visuellement.</span><span class="sxs-lookup"><span data-stu-id="58210-120">Additionally, aggregate values within the subcube are visually totaled.</span></span> <span data-ttu-id="58210-121">Par exemple, un sous-cube contient `USA`, `WA`et `OR`.</span><span class="sxs-lookup"><span data-stu-id="58210-121">For example, a subcube contains `USA`, `WA`, and `OR`.</span></span> <span data-ttu-id="58210-122">La valeur d'agrégation de `USA` sera la somme de `{WA,OR}` , car `WA` et `OR` sont les seuls États définis par le sous-cube.</span><span class="sxs-lookup"><span data-stu-id="58210-122">The aggregate value for `USA` will be the sum of `{WA,OR}` because `WA` and `OR` are the only states defined by the subcube.</span></span> <span data-ttu-id="58210-123">Tous les autres États seront ignorés.</span><span class="sxs-lookup"><span data-stu-id="58210-123">All other states will be ignored.</span></span>  
  
 <span data-ttu-id="58210-124">Par ailleurs, les références explicites à des cellules situées en dehors du sous-cube retournent des valeurs évaluées dans le contexte de l'intégralité du cube.</span><span class="sxs-lookup"><span data-stu-id="58210-124">Also, explicit references to cells outside the subcube return cell values that are evaluated in the context of the whole cube.</span></span> <span data-ttu-id="58210-125">Supposons que vous créez un sous-cube limité à l'année en cours.</span><span class="sxs-lookup"><span data-stu-id="58210-125">For example, you create a subcube that is limited to the current year.</span></span> <span data-ttu-id="58210-126">Ensuite, vous utilisez la fonction [ParallelPeriod](/sql/mdx/parallelperiod-mdx) pour comparer l’année en cours à l’année précédente.</span><span class="sxs-lookup"><span data-stu-id="58210-126">You then use the [ParallelPeriod](/sql/mdx/parallelperiod-mdx) function to compare the current year to the previous year.</span></span> <span data-ttu-id="58210-127">La différence dans les valeurs est retournée même si la valeur de l’année précédente se situe en dehors du sous-cube.</span><span class="sxs-lookup"><span data-stu-id="58210-127">The difference in values will be returned even though the previous year's value lies outside the subcube.</span></span>  
  
 <span data-ttu-id="58210-128">Pour terminer, si le contexte original n'est pas remplacé, les fonctions de jeu évaluées dans une sous-sélection sont évaluées dans le contexte de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="58210-128">Finally, if the original context is not overwritten, set functions evaluated in a subselect are evaluated in the context of the subselect.</span></span> <span data-ttu-id="58210-129">Si ce contexte est remplacé, les fonctions de jeu sont évaluées dans le contexte de l'intégralité du cube.</span><span class="sxs-lookup"><span data-stu-id="58210-129">If the context is overwritten, set functions are evaluated in the context of the whole cube.</span></span>  
  
## <a name="create-subcube-example"></a><span data-ttu-id="58210-130">Exemple de syntaxe CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="58210-130">CREATE SUBCUBE Example</span></span>  
 <span data-ttu-id="58210-131">L'exemple suivant crée un sous-cube qui limite le cube Budget aux comptes 4200 et 4300 uniquement :</span><span class="sxs-lookup"><span data-stu-id="58210-131">The following example creates a subcube that restricts the Budget cube to only accounts 4200 and 4300:</span></span>  
  
 `CREATE SUBCUBE Budget AS SELECT {[Account].[Account].&[4200], [Account].[Account].&[4300] } ON 0 FROM Budget`  
  
 <span data-ttu-id="58210-132">Lorsque vous avez créé un sous-cube pour la session, toutes les requêtes suivantes sont exécutées sur celui-ci plutôt que sur l'intégralité du cube.</span><span class="sxs-lookup"><span data-stu-id="58210-132">Having created a subcube for the session, any subsequent queries will be against the subcube, not the whole cube.</span></span> <span data-ttu-id="58210-133">Vous pouvez par exemple exécuter la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="58210-133">For example, you run the following query.</span></span> <span data-ttu-id="58210-134">Elle ne retourne que les membres des comptes 4200 et 4300.</span><span class="sxs-lookup"><span data-stu-id="58210-134">This query will only return members from accounts 4200 and 4300.</span></span>  
  
 `SELECT [Account].[Account].Members ON 0, Measures.Members ON 1 FROM Budget`  
  
## <a name="see-also"></a><span data-ttu-id="58210-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58210-135">See Also</span></span>  
 <span data-ttu-id="58210-136">[Établissement d’un contexte de cube dans une requête &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="58210-136">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 [<span data-ttu-id="58210-137">Principes de base des requêtes MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="58210-137">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
