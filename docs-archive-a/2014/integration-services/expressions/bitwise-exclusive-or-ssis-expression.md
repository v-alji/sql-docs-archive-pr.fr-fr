---
title: ^ (OR exclusif au niveau du bit) (expression SSIS)| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ^ (bitwise exclusive OR operator)
- bitwise exclusive OR (^)
ms.assetid: 6ac53cab-29c4-4835-9f87-371b058b2f38
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d86c3d810e9e5572af93c97f82c2275db2c979b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611927"
---
# <a name="-bitwise-exclusive-or-ssis-expression"></a><span data-ttu-id="3d5ed-102">^ (OR exclusif au niveau du bit) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="3d5ed-102">^ (Bitwise Exclusive OR) (SSIS Expression)</span></span>
  <span data-ttu-id="3d5ed-103">Effectue une opération OR exclusive au niveau du bit avec deux valeurs entières.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-103">Performs a bitwise exclusive OR operation of two integer values.</span></span> <span data-ttu-id="3d5ed-104">Cette fonction compare chaque bit de son premier opérande au bit correspondant de son second opérande.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="3d5ed-105">Si un bit a pour valeur 0 et que l'autre a pour valeur 1, le bit obtenu correspondant a pour valeur 1.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-105">If one bit is 0 and the other bit is 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="3d5ed-106">Si les deux bits ont pour valeur 0 ou 1, le bit obtenu correspondant a pour valeur 0.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-106">If both bits are 0 or both bits are 1, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="3d5ed-107">Les deux conditions doivent être de type de données signed integer ou unsigned integer.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-107">Both conditions must be a signed integer data type or both conditions must be an unsigned integer data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d5ed-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3d5ed-108">Syntax</span></span>  
  
```  
  
integer_expression1 ^ integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3d5ed-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="3d5ed-109">Arguments</span></span>  
 <span data-ttu-id="3d5ed-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="3d5ed-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="3d5ed-111">Toute expression valide de type de données signed integer ou unsigned integer.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="3d5ed-112">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3d5ed-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3d5ed-113">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="3d5ed-113">Result Types</span></span>  
 <span data-ttu-id="3d5ed-114">Déterminés par les types de données des deux arguments.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="3d5ed-115">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3d5ed-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d5ed-116">Notes</span><span class="sxs-lookup"><span data-stu-id="3d5ed-116">Remarks</span></span>  
 <span data-ttu-id="3d5ed-117">Si l'une des deux conditions est NULL, le résultat de l'expression est NULL.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3d5ed-118">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="3d5ed-118">Expression Examples</span></span>  
 <span data-ttu-id="3d5ed-119">L’exemple suivant effectue une opération OR exclusive au niveau du bit entre les variables **NumberA** et **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-119">This example performs a bitwise exclusive OR operation between variables **NumberA** and **NumberB**.</span></span> <span data-ttu-id="3d5ed-120">La variable**NumberA** contient la valeur 3 (00000011) et la variable **NumberB** contient la valeur 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="3d5ed-120">**NumberA** contains 3 (00000011) and **NumberB** contains 7 (00000111).</span></span>  
  
```  
@NumberA ^ @NumberB  
```  
  
 <span data-ttu-id="3d5ed-121">L'expression renvoie la valeur 4 (00000100).</span><span class="sxs-lookup"><span data-stu-id="3d5ed-121">The expression evaluates to 4 (00000100).</span></span>  
  
 <span data-ttu-id="3d5ed-122">00000011</span><span class="sxs-lookup"><span data-stu-id="3d5ed-122">00000011</span></span>  
  
 <span data-ttu-id="3d5ed-123">00000111</span><span class="sxs-lookup"><span data-stu-id="3d5ed-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="3d5ed-124">00000100</span><span class="sxs-lookup"><span data-stu-id="3d5ed-124">00000100</span></span>  
  
 <span data-ttu-id="3d5ed-125">L’exemple suivant effectue une opération OR exclusive au niveau du bit entre les colonnes **ReorderPoint** et **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="3d5ed-125">This example performs a bitwise exclusive OR operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint ^ SafetyStockLevel  
```  
  
 <span data-ttu-id="3d5ed-126">Si la colonne **ReorderPoint** contient la valeur 10 et la colonne **SafetyStockLevel** la valeur 8, l’expression renvoie la valeur 2 (00000010).</span><span class="sxs-lookup"><span data-stu-id="3d5ed-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 2 (00000010).</span></span>  
  
 <span data-ttu-id="3d5ed-127">00001010</span><span class="sxs-lookup"><span data-stu-id="3d5ed-127">00001010</span></span>  
  
 <span data-ttu-id="3d5ed-128">00001000</span><span class="sxs-lookup"><span data-stu-id="3d5ed-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="3d5ed-129">00000010</span><span class="sxs-lookup"><span data-stu-id="3d5ed-129">00000010</span></span>  
  
 <span data-ttu-id="3d5ed-130">L'exemple suivant effectue une opération OR exclusive au niveau du bit entre deux entiers.</span><span class="sxs-lookup"><span data-stu-id="3d5ed-130">This example performs a bitwise exclusive OR operation between two integers.</span></span>  
  
```  
3 ^ 5   
```  
  
 <span data-ttu-id="3d5ed-131">L'expression renvoie la valeur 6 (00000110).</span><span class="sxs-lookup"><span data-stu-id="3d5ed-131">The expression evaluates to 6 (00000110).</span></span>  
  
 <span data-ttu-id="3d5ed-132">00000011</span><span class="sxs-lookup"><span data-stu-id="3d5ed-132">00000011</span></span>  
  
 <span data-ttu-id="3d5ed-133">00000101</span><span class="sxs-lookup"><span data-stu-id="3d5ed-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="3d5ed-134">00000110</span><span class="sxs-lookup"><span data-stu-id="3d5ed-134">00000110</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d5ed-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d5ed-135">See Also</span></span>  
 <span data-ttu-id="3d5ed-136">[&#124;&#124; &#40;OR logique&#41; &#40;expression SSIS&#41;](logical-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="3d5ed-136">[&#124;&#124; &#40;Logical OR&#41; &#40;SSIS Expression&#41;](logical-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="3d5ed-137">[&#124; &#40;opération OR inclusive au niveau du bit&#41; &#40;expression SSIS&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="3d5ed-137">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="3d5ed-138">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="3d5ed-138">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="3d5ed-139">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3d5ed-139">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
