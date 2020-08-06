---
title: Utilisation de la fonction RollupChildren (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], RollupChildren function
- RollupChildren function
- custom member properties [MDX]
- IIf function
ms.assetid: 03c624d4-f277-451d-9995-623a07ea2f86
author: minewiskan
ms.author: owend
ms.openlocfilehash: 341468d521cebe1fda33d73ea999f3b6571cb01e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705600"
---
# <a name="working-with-the-rollupchildren-function-mdx"></a><span data-ttu-id="8c455-102">Utilisation de la fonction RollupChildren (MDX)</span><span class="sxs-lookup"><span data-stu-id="8c455-102">Working with the RollupChildren Function (MDX)</span></span>
  <span data-ttu-id="8c455-103">La fonction d’expressions multidimensionnelles (MDX) [RollupChildren](/sql/mdx/rollupchildren-mdx) [script pour la fonction de recherche et de remplacement] regroupe les enfants d’un membre, en appliquant un opérateur unaire différent à chaque enfant, et retourne la valeur de ce cumul sous la forme d’un nombre.</span><span class="sxs-lookup"><span data-stu-id="8c455-103">The Multidimensional Expressions (MDX) [RollupChildren](/sql/mdx/rollupchildren-mdx) [Script for Search and Replace] function rolls up the children of a member, applying a different unary operator to each child, and returns the value of this rollup as a number.</span></span> <span data-ttu-id="8c455-104">L'opérateur unaire peut être fourni par une propriété de membre associée au membre enfant, ou être une expression de type chaîne directement fournie à la fonction.</span><span class="sxs-lookup"><span data-stu-id="8c455-104">The unary operator can be supplied by a member property associated with the child member, or the operator can be a string expression provided directly to the function.</span></span>  
  
## <a name="rollupchildren-function-examples"></a><span data-ttu-id="8c455-105">Exemples de fonctions RollupChildren</span><span class="sxs-lookup"><span data-stu-id="8c455-105">RollupChildren Function Examples</span></span>  
 <span data-ttu-id="8c455-106">L'utilisation de la fonction `RollupChildren` dans les instructions MDX (Multidimensional Expressions) est simple à expliquer, mais elle peut avoir d'importantes répercussions sur les requêtes MDX.</span><span class="sxs-lookup"><span data-stu-id="8c455-106">The use of the `RollupChildren` function in Multidimensional Expressions (MDX) statements is simple to explain, but the effect of this function on MDX queries can be wide-ranging.</span></span>  
  
 <span data-ttu-id="8c455-107">L'effet de la fonction `RollupChildren` est perceptible dans les requêtes MDX conçues pour effectuer des analyses sélectives portant sur des données de cube existantes.</span><span class="sxs-lookup"><span data-stu-id="8c455-107">The effect of the `RollupChildren` function occurs in MDX queries designed to perform selective analysis on existing cube data.</span></span> <span data-ttu-id="8c455-108">Par exemple, le tableau suivant contient une liste de membres enfants du membre parent Net Sales, ainsi que leurs opérateurs unaires entre parenthèses (représentés par la propriété de membre `UNARY_OPERATOR`).</span><span class="sxs-lookup"><span data-stu-id="8c455-108">For example, the following table contains a list of child members for the Net Sales parent member, with their unary operators (represented by the `UNARY_OPERATOR` member property) shown in parentheses.</span></span>  
  
|<span data-ttu-id="8c455-109">Membre parent</span><span class="sxs-lookup"><span data-stu-id="8c455-109">Parent member</span></span>|<span data-ttu-id="8c455-110">Membre enfant</span><span class="sxs-lookup"><span data-stu-id="8c455-110">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="8c455-111">Ventes nettes</span><span class="sxs-lookup"><span data-stu-id="8c455-111">Net Sales</span></span>|<span data-ttu-id="8c455-112">Domestic Sales (+)</span><span class="sxs-lookup"><span data-stu-id="8c455-112">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="8c455-113">Domestic Returns (-)</span><span class="sxs-lookup"><span data-stu-id="8c455-113">Domestic Returns (-)</span></span><br /><br /> <span data-ttu-id="8c455-114">Foreign Sales (+)</span><span class="sxs-lookup"><span data-stu-id="8c455-114">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="8c455-115">Foreign Returns (-)</span><span class="sxs-lookup"><span data-stu-id="8c455-115">Foreign Returns (-)</span></span>|  
  
 <span data-ttu-id="8c455-116">Dans le cadre du cumul, le total des ventes nettes fourni en l'occurrence par le membre parent Net Sales est exprimé par les valeurs des ventes brutes réalisées sur le marché national et à l'étranger, moins les invendus réalisés sur le marché national et à l'étranger.</span><span class="sxs-lookup"><span data-stu-id="8c455-116">The Net Sales parent member currently provides a total of net sales minus the gross domestic and foreign sales values, with the domestic and foreign returns subtracted as part of the rollup.</span></span>  
  
 <span data-ttu-id="8c455-117">Cependant, vous souhaitez fournir une estimation rapide et simple des ventes brutes réalisées sur le marché national et à l'étranger majorées de 10 %, sans tenir compte des invendus réalisés sur le marché national et à l'étranger.</span><span class="sxs-lookup"><span data-stu-id="8c455-117">However, you want to provide a quick and easy forecast of domestic and foreign gross sales plus 10%, ignoring the domestic and foreign returns.</span></span> <span data-ttu-id="8c455-118">Pour calculer cette valeur, vous pouvez utiliser la fonction `RollupChildren` des deux manières suivantes : avec une propriété de membre personnalisée ou avec la fonction `IIf`.</span><span class="sxs-lookup"><span data-stu-id="8c455-118">To calculate this value, you can use the `RollupChildren` function in one of two ways: with a custom member property or with the `IIf` function.</span></span>  
  
### <a name="using-a-custom-member-property"></a><span data-ttu-id="8c455-119">Utilisation d'une propriété de membre personnalisée</span><span class="sxs-lookup"><span data-stu-id="8c455-119">Using a Custom Member Property</span></span>  
 <span data-ttu-id="8c455-120">Si le calcul de cumuls est appelé à être souvent utilisé, une méthode consiste à créer pour une fonction donnée une propriété de membre qui stocke les opérateurs à utiliser pour chaque enfant.</span><span class="sxs-lookup"><span data-stu-id="8c455-120">If the rollup calculation is to be a frequently performed operation, one method is to create a member property that stores the operator that will be used for each child for a specific function.</span></span> <span data-ttu-id="8c455-121">Le tableau suivant présente les opérateurs unaires corrects et décrit le résultat attendu.</span><span class="sxs-lookup"><span data-stu-id="8c455-121">The following table displays valid unary operators and describes the expected result.</span></span>  
  
|<span data-ttu-id="8c455-122">Opérateur</span><span class="sxs-lookup"><span data-stu-id="8c455-122">Operator</span></span>|<span data-ttu-id="8c455-123">Résultat</span><span class="sxs-lookup"><span data-stu-id="8c455-123">Result</span></span>|  
|--------------|------------|  
|+|<span data-ttu-id="8c455-124">total = total + enfant actuel</span><span class="sxs-lookup"><span data-stu-id="8c455-124">total = total + current child</span></span>|  
|-|<span data-ttu-id="8c455-125">total = total - enfant actuel</span><span class="sxs-lookup"><span data-stu-id="8c455-125">total = total - current child</span></span>|  
|*|<span data-ttu-id="8c455-126">total = total \* enfant actuel</span><span class="sxs-lookup"><span data-stu-id="8c455-126">total = total \* current child</span></span>|  
|/|<span data-ttu-id="8c455-127">total = total / enfant actuel</span><span class="sxs-lookup"><span data-stu-id="8c455-127">total = total / current child</span></span>|  
|~|<span data-ttu-id="8c455-128">L'enfant n'est pas utilisé dans le cumul.</span><span class="sxs-lookup"><span data-stu-id="8c455-128">Child is not used in the rollup.</span></span> <span data-ttu-id="8c455-129">La valeur de l'enfant est ignorée.</span><span class="sxs-lookup"><span data-stu-id="8c455-129">The child's value is ignored.</span></span>|  
  
 <span data-ttu-id="8c455-130">Par exemple, une propriété de membre appelée `SALES_OPERATOR` est créée, à laquelle sont attribués des opérateurs unaires, comme le montre le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="8c455-130">For example, a member property called `SALES_OPERATOR` could be created, and the following unary operators would be assigned to that member property, as shown in the following table.</span></span>  
  
|<span data-ttu-id="8c455-131">Membre parent</span><span class="sxs-lookup"><span data-stu-id="8c455-131">Parent member</span></span>|<span data-ttu-id="8c455-132">Membre enfant</span><span class="sxs-lookup"><span data-stu-id="8c455-132">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="8c455-133">Ventes nettes</span><span class="sxs-lookup"><span data-stu-id="8c455-133">Net Sales</span></span>|<span data-ttu-id="8c455-134">Domestic Sales (+)</span><span class="sxs-lookup"><span data-stu-id="8c455-134">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="8c455-135">Domestic Returns (~)</span><span class="sxs-lookup"><span data-stu-id="8c455-135">Domestic Returns (~)</span></span><br /><br /> <span data-ttu-id="8c455-136">Foreign Sales (+)</span><span class="sxs-lookup"><span data-stu-id="8c455-136">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="8c455-137">Foreign Returns (~)</span><span class="sxs-lookup"><span data-stu-id="8c455-137">Foreign Returns (~)</span></span>|  
  
 <span data-ttu-id="8c455-138">Grâce à cette nouvelle propriété de membre, l'instruction MDX suivante effectue l'estimation des ventes brutes rapidement et efficacement (en ignorant les invendus réalisés sur le marché national et à l'étranger) :</span><span class="sxs-lookup"><span data-stu-id="8c455-138">With this new member property, the following MDX statement would perform the gross sales estimate operation quickly and efficiently (ignoring Foreign and Domestic returns):</span></span>  
  
```  
RollupChildren([Net Sales], [Net Sales].CurrentMember.Properties("SALES_OPERATOR")) * 1.1  
```  
  
 <span data-ttu-id="8c455-139">Lorsque la fonction est appelée, la valeur de chaque enfant s'applique à un total à l'aide de l'opérateur stocké dans la propriété de membre.</span><span class="sxs-lookup"><span data-stu-id="8c455-139">When the function is called, the value of each child is applied to a total using the operator stored in the member property.</span></span> <span data-ttu-id="8c455-140">Les membres correspondant aux invendus réalisés sur le marché national et à l'étranger sont ignorés, et le total du cumul renvoyé par la fonction `RollupChildren` est multiplié par 1,1.</span><span class="sxs-lookup"><span data-stu-id="8c455-140">The members for domestic and foreign returns are ignored, and the rollup total returned by the `RollupChildren` function is multiplied by 1.1.</span></span>  
  
### <a name="using-the-iif-function"></a><span data-ttu-id="8c455-141">Utilisation de la fonction IIf</span><span class="sxs-lookup"><span data-stu-id="8c455-141">Using the IIf Function</span></span>  
 <span data-ttu-id="8c455-142">Si l’opération d’exemple n’est pas courante ou si l’opération ne s’applique qu’à une seule requête MDX, la fonction [IIf](/sql/mdx/iif-mdx) peut être utilisée avec la `RollupChildren` fonction pour fournir le même résultat.</span><span class="sxs-lookup"><span data-stu-id="8c455-142">If the example operation is not commonplace or if the operation applies only to one MDX query, the [IIf](/sql/mdx/iif-mdx) function can be used with the `RollupChildren` function to provide the same result.</span></span> <span data-ttu-id="8c455-143">La requête MDX suivante fournit le même résultat que l'instruction MDX précédente, mais sans avoir recours à une propriété de membre personnalisée :</span><span class="sxs-lookup"><span data-stu-id="8c455-143">The following MDX query provides the same result as the earlier MDX example, but does so without resorting to the use of a custom member property:</span></span>  
  
```  
RollupChildren([Net Sales], IIf([Net Sales].CurrentMember.Properties("UNARY_OPERATOR") = "-", "~", [Net Sales].CurrentMember.Properties("UNARY_OPERATOR))) * 1.1  
```  
  
 <span data-ttu-id="8c455-144">L'instruction MDX examine l'opérateur unaire du membre enfant.</span><span class="sxs-lookup"><span data-stu-id="8c455-144">The MDX statement examines the unary operator of the child member.</span></span> <span data-ttu-id="8c455-145">S'il est utilisé pour une soustraction (comme dans le cas des membres correspondant aux invendus réalisés sur le marché national et à l'étranger), l'opérateur unaire tilde (~) est remplacé par la fonction `IIf`.</span><span class="sxs-lookup"><span data-stu-id="8c455-145">If the unary operator is used for subtraction (as in the case with the domestic and foreign returns members), the `IIf` function substitutes the tilde (~) unary operator.</span></span> <span data-ttu-id="8c455-146">Sinon, la fonction `IIf` utilise l'opérateur unaire du membre enfant.</span><span class="sxs-lookup"><span data-stu-id="8c455-146">Otherwise, the `IIf` function uses the unary operator of the child member.</span></span> <span data-ttu-id="8c455-147">Enfin, le total du cumul renvoyé est multiplié par 1,1 afin de fournir la valeur estimée des ventes brutes sur le marché national et à l'étranger.</span><span class="sxs-lookup"><span data-stu-id="8c455-147">Finally, the returned rollup total is then multiplied by 1.1 to provide the domestic and foreign gross sales forecast value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c455-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c455-148">See Also</span></span>  
 [<span data-ttu-id="8c455-149">Manipulation de données &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8c455-149">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
