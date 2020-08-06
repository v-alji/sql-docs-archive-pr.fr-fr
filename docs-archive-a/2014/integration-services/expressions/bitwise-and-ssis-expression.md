---
title: '&amp; (AND au niveau du bit) (expression SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- AND, bitwise AND
- '& (bitwise AND)'
- bitwise AND (&)
ms.assetid: 06d2958e-66a5-44d8-8bc4-56209ebe1ff2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbf3c8ffcef079e25c82478947bc3b92a6b4be93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611926"
---
# <a name="amp-bitwise-and-ssis-expression"></a><span data-ttu-id="121dc-102">&amp; (AND au niveau du bit) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="121dc-102">&amp; (Bitwise AND) (SSIS Expression)</span></span>
  <span data-ttu-id="121dc-103">Effectue une opération AND au niveau du bit avec deux valeurs entières.</span><span class="sxs-lookup"><span data-stu-id="121dc-103">Performs a bitwise AND operation of two integer values.</span></span> <span data-ttu-id="121dc-104">Cette fonction compare chaque bit de son premier opérande au bit correspondant de son second opérande.</span><span class="sxs-lookup"><span data-stu-id="121dc-104">It compares each bit of its first operand to the corresponding bit of its second operand.</span></span> <span data-ttu-id="121dc-105">Si les deux bits ont pour valeur 1, le bit obtenu correspondant a pour valeur 1.</span><span class="sxs-lookup"><span data-stu-id="121dc-105">If both bits are 1, the corresponding result bit is set to 1.</span></span> <span data-ttu-id="121dc-106">Sinon, il a pour valeur 0.</span><span class="sxs-lookup"><span data-stu-id="121dc-106">Otherwise, the corresponding result bit is set to 0.</span></span>  
  
 <span data-ttu-id="121dc-107">Les deux conditions doivent être ou de type signed integer ou de type unsigned integer.</span><span class="sxs-lookup"><span data-stu-id="121dc-107">Both conditions must be a signed integer type or both conditions must be an unsigned integer type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="121dc-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="121dc-108">Syntax</span></span>  
  
```  
  
integer_expression1 & integer_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="121dc-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="121dc-109">Arguments</span></span>  
 <span data-ttu-id="121dc-110">*integer_expression1, integer_expression2*</span><span class="sxs-lookup"><span data-stu-id="121dc-110">*integer_expression1, integer_expression2*</span></span>  
 <span data-ttu-id="121dc-111">Toute expression valide de type de données signed integer ou unsigned integer.</span><span class="sxs-lookup"><span data-stu-id="121dc-111">Is any valid expression of a signed or unsigned integer data type.</span></span> <span data-ttu-id="121dc-112">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="121dc-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="121dc-113">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="121dc-113">Result Types</span></span>  
 <span data-ttu-id="121dc-114">Déterminés par les types de données des deux arguments.</span><span class="sxs-lookup"><span data-stu-id="121dc-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="121dc-115">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="121dc-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="121dc-116">Notes</span><span class="sxs-lookup"><span data-stu-id="121dc-116">Remarks</span></span>  
 <span data-ttu-id="121dc-117">Si l'une des deux conditions est NULL, le résultat de l'expression est NULL.</span><span class="sxs-lookup"><span data-stu-id="121dc-117">If either condition is null, the expression result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="121dc-118">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="121dc-118">Expression Examples</span></span>  
 <span data-ttu-id="121dc-119">L’exemple suivant effectue une opération AND au niveau du bit entre les colonnes **NumberA** et **NumberB**.</span><span class="sxs-lookup"><span data-stu-id="121dc-119">This example performs a bitwise AND operation between the columns **NumberA** and **NumberB**.</span></span> <span data-ttu-id="121dc-120">La colonne**NumberA** contient la valeur 3 (0000011) et la colonne **NumberB** contient la valeur 7 (00000111).</span><span class="sxs-lookup"><span data-stu-id="121dc-120">**NumberA** contains 3 (0000011) and column **NumberB** contains 7 (00000111).</span></span>  
  
```  
NumberA & NumberB  
```  
  
 <span data-ttu-id="121dc-121">L'expression renvoie la valeur 3 (00000011).</span><span class="sxs-lookup"><span data-stu-id="121dc-121">The expression evaluates to 3 (00000011).</span></span>  
  
 <span data-ttu-id="121dc-122">00000011</span><span class="sxs-lookup"><span data-stu-id="121dc-122">00000011</span></span>  
  
 <span data-ttu-id="121dc-123">00000111</span><span class="sxs-lookup"><span data-stu-id="121dc-123">00000111</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="121dc-124">00000011</span><span class="sxs-lookup"><span data-stu-id="121dc-124">00000011</span></span>  
  
 <span data-ttu-id="121dc-125">L’exemple suivant effectue une opération AND au niveau du bit entre les colonnes **ReorderPoint** et **SafetyStockLevel** .</span><span class="sxs-lookup"><span data-stu-id="121dc-125">This example performs a bitwise AND operation between the **ReorderPoint** and **SafetyStockLevel** columns.</span></span>  
  
```  
ReorderPoint & SafetyStockLevel  
```  
  
 <span data-ttu-id="121dc-126">Si la colonne **ReorderPoint** contient la valeur 10 et la colonne **SafetyStockLevel** la valeur 8, l’expression prend la valeur 8 (00001000).</span><span class="sxs-lookup"><span data-stu-id="121dc-126">If **ReorderPoint** is 10 and **SafetyStockLevel** is 8, the expression evaluates to 8 (00001000).</span></span>  
  
 <span data-ttu-id="121dc-127">00001010</span><span class="sxs-lookup"><span data-stu-id="121dc-127">00001010</span></span>  
  
 <span data-ttu-id="121dc-128">00001000</span><span class="sxs-lookup"><span data-stu-id="121dc-128">00001000</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="121dc-129">00001000</span><span class="sxs-lookup"><span data-stu-id="121dc-129">00001000</span></span>  
  
 <span data-ttu-id="121dc-130">L'exemple suivant effectue une opération AND au niveau du bit entre deux entiers.</span><span class="sxs-lookup"><span data-stu-id="121dc-130">This example performs a bitwise AND operation between two integers.</span></span>  
  
```  
3 & 5   
```  
  
 <span data-ttu-id="121dc-131">L'expression renvoie la valeur 1 (00000001).</span><span class="sxs-lookup"><span data-stu-id="121dc-131">The expression evaluates to 1(00000001).</span></span>  
  
 <span data-ttu-id="121dc-132">00000011</span><span class="sxs-lookup"><span data-stu-id="121dc-132">00000011</span></span>  
  
 <span data-ttu-id="121dc-133">00000101</span><span class="sxs-lookup"><span data-stu-id="121dc-133">00000101</span></span>  
  
 ----------\-  
  
 <span data-ttu-id="121dc-134">00000001</span><span class="sxs-lookup"><span data-stu-id="121dc-134">00000001</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="121dc-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="121dc-135">See Also</span></span>  
 <span data-ttu-id="121dc-136">[&& &#40;ET logique&#41; &#40;expression SSIS&#41;](logical-and-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="121dc-136">[&& &#40;Logical AND&#41; &#40;SSIS Expression&#41;](logical-and-ssis-expression.md) </span></span>  
 <span data-ttu-id="121dc-137">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="121dc-137">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="121dc-138">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="121dc-138">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
