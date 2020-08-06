---
title: LN (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LN function
- natural logarithm of expression [Integration Services]
ms.assetid: 55d7b657-b5fd-4753-9c81-54ed7575e720
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c06d6e246cfa51f8e84eb93ab7eb73eab40c392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611918"
---
# <a name="ln-ssis-expression"></a><span data-ttu-id="47fca-102">LN (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="47fca-102">LN (SSIS Expression)</span></span>
  <span data-ttu-id="47fca-103">Renvoie le logarithme népérien d'une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="47fca-103">Returns the natural logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47fca-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="47fca-104">Syntax</span></span>  
  
```  
  
LN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="47fca-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="47fca-105">Arguments</span></span>  
 <span data-ttu-id="47fca-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="47fca-106">*numeric_expression*</span></span>  
 <span data-ttu-id="47fca-107">Expression numérique valide non négative et différente de zéro.</span><span class="sxs-lookup"><span data-stu-id="47fca-107">Is a valid non-zero and non-negative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="47fca-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="47fca-108">Result Types</span></span>  
 <span data-ttu-id="47fca-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="47fca-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47fca-110">Notes</span><span class="sxs-lookup"><span data-stu-id="47fca-110">Remarks</span></span>  
 <span data-ttu-id="47fca-111">L'expression numérique est convertie vers le type de données DT_R8 avant le calcul du logarithme.</span><span class="sxs-lookup"><span data-stu-id="47fca-111">The numeric expression is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="47fca-112">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="47fca-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="47fca-113">Si l’argument *numeric_expression* donne une valeur inférieure ou égale à zéro, le résultat obtenu est NULL.</span><span class="sxs-lookup"><span data-stu-id="47fca-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="47fca-114">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="47fca-114">Expression Examples</span></span>  
 <span data-ttu-id="47fca-115">L'exemple suivant utilise un littéral numérique.</span><span class="sxs-lookup"><span data-stu-id="47fca-115">This example uses a numeric literal.</span></span> <span data-ttu-id="47fca-116">La fonction renvoie la valeur 3,737766961828337.</span><span class="sxs-lookup"><span data-stu-id="47fca-116">The function returns the value 3.737766961828337.</span></span>  
  
```  
LN(42)  
```  
  
 <span data-ttu-id="47fca-117">L'exemple suivant utilise la colonne **Length**.</span><span class="sxs-lookup"><span data-stu-id="47fca-117">This example uses the column **Length**.</span></span> <span data-ttu-id="47fca-118">Si la valeur de la colonne est 53,99, la fonction renvoie 3,9887988442302.</span><span class="sxs-lookup"><span data-stu-id="47fca-118">If the column value is 53.99, the function returns 3.9887988442302.</span></span>  
  
```  
LN(Length)   
```  
  
 <span data-ttu-id="47fca-119">L'exemple suivant utilise la variable **Length**.</span><span class="sxs-lookup"><span data-stu-id="47fca-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="47fca-120">La variable doit être d'un type de données numérique ou l'expression doit comprendre une conversion explicite vers un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="47fca-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric data type.</span></span> <span data-ttu-id="47fca-121">Si la variable **Length** a pour valeur 234,567, la fonction renvoie 5,45774126708797.</span><span class="sxs-lookup"><span data-stu-id="47fca-121">If **Length** is 234.567, the function returns 5.45774126708797.</span></span>  
  
```  
LN(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="47fca-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47fca-122">See Also</span></span>  
 <span data-ttu-id="47fca-123">[LOG &#40;expression SSIS&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="47fca-123">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="47fca-124">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="47fca-124">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
