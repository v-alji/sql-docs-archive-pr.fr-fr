---
title: (Modulo) (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '% (modulo operator)'
- remainder of division operation
- modulo operator (%)
ms.assetid: e2920821-2f5b-4c76-8db8-8b9eddf4606f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e23152fca9c9f2c7c3ac11490a56b03d1a1f9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604649"
---
# <a name="modulo-ssis-expression"></a><span data-ttu-id="770db-102">(Modulo) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="770db-102">(Modulo) (SSIS Expression)</span></span>
  <span data-ttu-id="770db-103">Fournit le reste entier de la division de la première expression numérique par la deuxième.</span><span class="sxs-lookup"><span data-stu-id="770db-103">Provides the integer remainder after dividing the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="770db-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="770db-104">Syntax</span></span>  
  
```  
  
dividend % divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="770db-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="770db-105">Arguments</span></span>  
 <span data-ttu-id="770db-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="770db-106">*dividend*</span></span>  
 <span data-ttu-id="770db-107">Expression numérique à diviser.</span><span class="sxs-lookup"><span data-stu-id="770db-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="770db-108">*dividend* peut être n’importe quelle expression numérique valide.</span><span class="sxs-lookup"><span data-stu-id="770db-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="770db-109">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="770db-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md)</span></span>  
  
 <span data-ttu-id="770db-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="770db-110">*divisor*</span></span>  
 <span data-ttu-id="770db-111">Expression numérique par laquelle diviser le dividende.</span><span class="sxs-lookup"><span data-stu-id="770db-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="770db-112">*divisor* peut être n’importe quelle expression numérique valide, sauf zéro.</span><span class="sxs-lookup"><span data-stu-id="770db-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="770db-113">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="770db-113">Result Types</span></span>  
 <span data-ttu-id="770db-114">Déterminés par les types de données des deux arguments.</span><span class="sxs-lookup"><span data-stu-id="770db-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="770db-115">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="770db-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="770db-116">Notes</span><span class="sxs-lookup"><span data-stu-id="770db-116">Remarks</span></span>  
 <span data-ttu-id="770db-117">Les valeurs des deux expressions doivent s'évaluer à des types de données entier signé ou non signé.</span><span class="sxs-lookup"><span data-stu-id="770db-117">Both expressions must evaluate to signed or unsigned integer data types.</span></span>  
  
 <span data-ttu-id="770db-118">Si l'un des opérandes est NULL, le résultat est NULL.</span><span class="sxs-lookup"><span data-stu-id="770db-118">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="770db-119">Un modulo égal à zéro n'est pas autorisé.</span><span class="sxs-lookup"><span data-stu-id="770db-119">Modulo zero is not legal.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="770db-120">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="770db-120">Expression Examples</span></span>  
 <span data-ttu-id="770db-121">L'exemple suivant calcule le modulo à partir de deux littéraux numériques.</span><span class="sxs-lookup"><span data-stu-id="770db-121">This example computes the modulus from two numeric literals.</span></span> <span data-ttu-id="770db-122">Le résultat est 3.</span><span class="sxs-lookup"><span data-stu-id="770db-122">The result is 3.</span></span>  
  
```  
42 % 13  
```  
  
 <span data-ttu-id="770db-123">L’exemple suivant calcule le modulo à partir de la colonne **SalesQuota** et d’un littéral numérique.</span><span class="sxs-lookup"><span data-stu-id="770db-123">This example computes the modulus from the **SalesQuota** column and a numeric literal.</span></span>  
  
```  
SalesQuota % 12  
```  
  
 <span data-ttu-id="770db-124">L’exemple suivant calcule le modulo à partir de deux variables numériques : **Sales$** et **Month**.</span><span class="sxs-lookup"><span data-stu-id="770db-124">This example computes the modulus from two numeric variables **Sales$** and **Month**.</span></span> <span data-ttu-id="770db-125">La variable **Sales$** doit figurer entre crochets car elle contient le caractère « $ ».</span><span class="sxs-lookup"><span data-stu-id="770db-125">The variable **Sales$** must be enclosed in brackets because the name includes the $ character.</span></span> <span data-ttu-id="770db-126">Pour plus d’informations, consultez [Identificateurs &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="770db-126">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
@[Sales$] % @Month  
```  
  
 <span data-ttu-id="770db-127">L’exemple suivant utilise l’opérateur modulo pour déterminer si la valeur de la variable **Value** est paire ou impaire, et utilise l’opérateur conditionnel pour renvoyer une chaîne décrivant le résultat.</span><span class="sxs-lookup"><span data-stu-id="770db-127">This example uses the modulo operator to determine if the value of the **Value** variable is even or odd, and uses the conditional operator to return a string that describes the result.</span></span> <span data-ttu-id="770db-128">Pour plus d’informations, consultez [? : &#40;Conditionnel&#41; &#40;expression SSIS&#41;](conditional-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="770db-128">For more information, see [? : &#40;Conditional&#41; &#40;SSIS Expression&#41;](conditional-ssis-expression.md).</span></span>  
  
```  
@Value % 2 == 0? "even":"odd"  
```  
  
## <a name="see-also"></a><span data-ttu-id="770db-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="770db-129">See Also</span></span>  
 <span data-ttu-id="770db-130">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="770db-130">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="770db-131">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="770db-131">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
