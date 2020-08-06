---
title: POWER (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- POWER function
ms.assetid: db48ae65-bfa6-4db1-8d3c-d0d4f8a399bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1f5742f482ae52620ec11d95b84cb3d06199fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610735"
---
# <a name="power-ssis-expression"></a><span data-ttu-id="a492f-102">POWER (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="a492f-102">POWER (SSIS Expression)</span></span>
  <span data-ttu-id="a492f-103">Renvoie le résultat de l'élévation d'une expression numérique à une puissance donnée.</span><span class="sxs-lookup"><span data-stu-id="a492f-103">Returns the result of raising a numeric expression to a power.</span></span> <span data-ttu-id="a492f-104">La valeur du paramètre de la puissance doit s'évaluer à un entier.</span><span class="sxs-lookup"><span data-stu-id="a492f-104">The power parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a492f-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a492f-105">Syntax</span></span>  
  
```  
  
POWER(numeric_expression,power)  
```  
  
## <a name="arguments"></a><span data-ttu-id="a492f-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="a492f-106">Arguments</span></span>  
 <span data-ttu-id="a492f-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="a492f-107">*numeric_expression*</span></span>  
 <span data-ttu-id="a492f-108">Expression numérique valide.</span><span class="sxs-lookup"><span data-stu-id="a492f-108">Is a valid numeric expression.</span></span>  
  
 <span data-ttu-id="a492f-109">*puissance*</span><span class="sxs-lookup"><span data-stu-id="a492f-109">*power*</span></span>  
 <span data-ttu-id="a492f-110">Expression numérique valide.</span><span class="sxs-lookup"><span data-stu-id="a492f-110">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a492f-111">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="a492f-111">Result Types</span></span>  
 <span data-ttu-id="a492f-112">DT_R8</span><span class="sxs-lookup"><span data-stu-id="a492f-112">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a492f-113">Notes</span><span class="sxs-lookup"><span data-stu-id="a492f-113">Remarks</span></span>  
 <span data-ttu-id="a492f-114">Les arguments *numeric_expression* et *power* sont convertis dans le type de données DT_R8 avant le calcul de la puissance.</span><span class="sxs-lookup"><span data-stu-id="a492f-114">The *numeric_expression* and *power* arguments are cast to the DT_R8 data type before the power is computed.</span></span> <span data-ttu-id="a492f-115">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a492f-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="a492f-116">Si l’argument *numeric_expression* correspond à la valeur zéro et que l’argument *power* est négatif, l’évaluateur d’expression retourne une erreur et le résultat obtenu est Null.</span><span class="sxs-lookup"><span data-stu-id="a492f-116">If *numeric_expression* evaluates to zero and *power* is negative, the expression evaluator returns an error and sets the return result to null.</span></span>  
  
 <span data-ttu-id="a492f-117">Si *numeric_expression* ou *power* correspond à des résultats indéterminés, la valeur Null est retournée.</span><span class="sxs-lookup"><span data-stu-id="a492f-117">If *numeric_expression* or *power* evaluate to indeterminate results, the return result is null.</span></span>  
  
 <span data-ttu-id="a492f-118">L’argument *power* peut être une fraction.</span><span class="sxs-lookup"><span data-stu-id="a492f-118">The *power* argument can be a fraction.</span></span> <span data-ttu-id="a492f-119">Par exemple, vous pouvez utiliser la valeur 0,5 comme puissance.</span><span class="sxs-lookup"><span data-stu-id="a492f-119">For example, you can use the value 0.5 as the power.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="a492f-120">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="a492f-120">Expression Examples</span></span>  
 <span data-ttu-id="a492f-121">L'exemple suivant utilise un littéral numérique.</span><span class="sxs-lookup"><span data-stu-id="a492f-121">This example uses a numeric literal.</span></span> <span data-ttu-id="a492f-122">La fonction élève 4 à la puissance 3 et renvoie 64.</span><span class="sxs-lookup"><span data-stu-id="a492f-122">The function raises 4 to the power of 3 and returns 64.</span></span>  
  
```  
POWER(4,3)  
```  
  
 <span data-ttu-id="a492f-123">L’exemple suivant utilise la colonne **Length** et la variable **DimensionCount** .</span><span class="sxs-lookup"><span data-stu-id="a492f-123">This example uses the **Length** column and the **DimensionCount** variable.</span></span> <span data-ttu-id="a492f-124">Si l’argument **Length** a la valeur 8 et l’argument **DimensionCount** la valeur 2, le résultat obtenu est 64.</span><span class="sxs-lookup"><span data-stu-id="a492f-124">If **Length** is 8, and **DimensionCount** is 2, the return result is 64.</span></span>  
  
```  
POWER(Length, @DimensionCount)   
```  
  
## <a name="see-also"></a><span data-ttu-id="a492f-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a492f-125">See Also</span></span>  
 [<span data-ttu-id="a492f-126">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="a492f-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
