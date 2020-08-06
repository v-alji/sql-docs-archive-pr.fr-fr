---
title: '| (OR inclusif au niveau du bit) (expression SSIS)| Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '| (bitwise inclusive OR)'
- bitwise inclusive OR (|)
ms.assetid: 4dce9eb2-3680-4adc-81a3-816ea52cef49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 73d64886b433ffe5b4e06dc4870bbca06b2a53dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611920"
---
# <a name="-bitwise-inclusive-or-ssis-expression"></a><span data-ttu-id="2a811-102">| (OR inclusive au niveau du bit) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="2a811-102">| (Bitwise Inclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="2a811-103">Effectue une opération OR au niveau du bit avec deux valeurs entières.</span><span class="sxs-lookup"><span data-stu-id="2a811-103">Performs a bitwise OR operation of two integer values.</span></span> <span data-ttu-id="2a811-104">Cette fonction compare chaque bit de son premier opérande au bit correspondant de son second opérande.</span><span class="sxs-lookup"><span data-stu-id="2a811-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="2a811-105">Si l'un des deux bits a pour valeur 1, le bit obtenu correspondant a pour valeur 1.</span><span class="sxs-lookup"><span data-stu-id="2a811-105">If either bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="2a811-106">Sinon, il a pour valeur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="2a811-106">Otherwise, the corresponding result bit is set to zero (0).</span></span>  
  
 <span data-ttu-id="2a811-107">Les deux conditions doivent être de type de données signed integer ou unsigned integer.</span><span class="sxs-lookup"><span data-stu-id="2a811-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a811-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2a811-108">Syntax</span></span>  
  
```  
  
integer_expression1 | integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a811-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="2a811-109">Arguments</span></span>  
 <span data-ttu-id="2a811-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="2a811-110">*integer_expression1 ,integer_ expression2*</span></span>  
 <span data-ttu-id="2a811-111">Toute expression valide de type de données signed integer ou unsigned integer.</span><span class="sxs-lookup"><span data-stu-id="2a811-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="2a811-112">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2a811-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2a811-113">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="2a811-113">Result Types</span></span>  
 <span data-ttu-id="2a811-114">Déterminés par les types de données des deux arguments.</span><span class="sxs-lookup"><span data-stu-id="2a811-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="2a811-115">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2a811-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a811-116">Notes</span><span class="sxs-lookup"><span data-stu-id="2a811-116">Remarks</span></span>  
 <span data-ttu-id="2a811-117">Si l'une des deux conditions est NULL, le résultat de l'expression est NULL.</span><span class="sxs-lookup"><span data-stu-id="2a811-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2a811-118">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="2a811-118">Expression Examples</span></span>  
 <span data-ttu-id="2a811-119">L’exemple suivant effectue une opération OR inclusive au niveau du bit entre les variables **NumberA** et **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="2a811-119">This example performs a bitwise inclusive OR operation between the variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="2a811-120">La variable**NumberA** contient la valeur 3 (00000011) et la variable **NumberB** contient la valeur 9 (00001001).</span><span class="sxs-lookup"><span data-stu-id="2a811-120">**NumberA** contains 3 (00000011) and **NumberB** contains 9 (00001001).</span></span>  
  
```  
@NumberA | @NumberB  
```  
  
 <span data-ttu-id="2a811-121">L'expression renvoie la valeur 11 (00001011).</span><span class="sxs-lookup"><span data-stu-id="2a811-121">The expression evaluates to 11 (00001011).</span></span>  
  
 <span data-ttu-id="2a811-122">00000011</span><span class="sxs-lookup"><span data-stu-id="2a811-122">00000011</span></span>  
  
 <span data-ttu-id="2a811-123">00001001</span><span class="sxs-lookup"><span data-stu-id="2a811-123">00001001</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="2a811-124">00001011</span><span class="sxs-lookup"><span data-stu-id="2a811-124">00001011</span></span>  
  
 <span data-ttu-id="2a811-125">L’exemple suivant effectue une opération OR inclusive au niveau du bit entre les colonnes **ReorderPoint** et **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="2a811-125">This example performs a bitwise inclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint | SafetyStockLevel  
```  
  
 <span data-ttu-id="2a811-126">Si la colonne **ReorderPoint** contient la valeur 10 et la colonne **SafetyStockLevel** la valeur 8, l’expression renvoie la valeur 10 (00001010).</span><span class="sxs-lookup"><span data-stu-id="2a811-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 10 (00001010).</span></span>  
  
 <span data-ttu-id="2a811-127">00001010</span><span class="sxs-lookup"><span data-stu-id="2a811-127">00001010</span></span>  
  
 <span data-ttu-id="2a811-128">00001000</span><span class="sxs-lookup"><span data-stu-id="2a811-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="2a811-129">00001010</span><span class="sxs-lookup"><span data-stu-id="2a811-129">00001010</span></span>  
  
 <span data-ttu-id="2a811-130">L'exemple suivant effectue une opération OR inclusive au niveau du bit entre deux entiers.</span><span class="sxs-lookup"><span data-stu-id="2a811-130">This example performs a bitwise inclusive OR operation between two integers.</span></span>  
  
```  
3 | 5   
```  
  
 <span data-ttu-id="2a811-131">L'expression renvoie la valeur 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="2a811-131">The expression evaluates to 7 (00000111).</span></span>  
  
 <span data-ttu-id="2a811-132">00000011</span><span class="sxs-lookup"><span data-stu-id="2a811-132">00000011</span></span>  
  
 <span data-ttu-id="2a811-133">00000101</span><span class="sxs-lookup"><span data-stu-id="2a811-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="2a811-134">00000111</span><span class="sxs-lookup"><span data-stu-id="2a811-134">00000111</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a811-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a811-135">See Also</span></span>  
 <span data-ttu-id="2a811-136">[&#124;&#124; &#40;OR logique&#41; &#40;expression SSIS&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="2a811-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="2a811-137">[^ &#40;OR exclusif au niveau du bit&#41; &#40;expression SSIS&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="2a811-137">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="2a811-138">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="2a811-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="2a811-139">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2a811-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
