---
title: '- (Soustraire) (expression SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (subtract)'
- subtract operator (-)
ms.assetid: b48da086-37dd-460a-8a4b-912f52c9b158
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 79c47689baf47c33952c6b208ac622e9920d05fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701351"
---
# <a name="--subtract-ssis-expression"></a><span data-ttu-id="ff400-102">- (Soustraction) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="ff400-102">- (Subtract) (SSIS Expression)</span></span>
  <span data-ttu-id="ff400-103">Soustrait la deuxième expression numérique de la première.</span><span class="sxs-lookup"><span data-stu-id="ff400-103">Subtracts the second numeric expression from the first one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff400-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ff400-104">Syntax</span></span>  
  
```  
  
numeric_expression1 - numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff400-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="ff400-105">Arguments</span></span>  
 <span data-ttu-id="ff400-106">*expression_numérique1, expression_numérique2*</span><span class="sxs-lookup"><span data-stu-id="ff400-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="ff400-107">Toute expression valide d'un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="ff400-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="ff400-108">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ff400-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ff400-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="ff400-109">Result Types</span></span>  
 <span data-ttu-id="ff400-110">Déterminés par les types de données des deux arguments.</span><span class="sxs-lookup"><span data-stu-id="ff400-110">Determined by the data types of the two arguments.</span></span> <span data-ttu-id="ff400-111">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ff400-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff400-112">Notes</span><span class="sxs-lookup"><span data-stu-id="ff400-112">Remarks</span></span>  
 <span data-ttu-id="ff400-113">Ajoutez l'expression unaire négative entre parenthèses pour garantir que l'expression est évaluée dans l'ordre correct</span><span class="sxs-lookup"><span data-stu-id="ff400-113">Enclose the minus unary expression in parenthesis to ensure that the expression is evaluated in the correct order</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff400-114">Notes</span><span class="sxs-lookup"><span data-stu-id="ff400-114">Remarks</span></span>  
 <span data-ttu-id="ff400-115">Si l'un des opérandes est NULL, le résultat est NULL.</span><span class="sxs-lookup"><span data-stu-id="ff400-115">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ff400-116">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="ff400-116">Expression Examples</span></span>  
 <span data-ttu-id="ff400-117">L'exemple suivant soustrait des littéraux numériques.</span><span class="sxs-lookup"><span data-stu-id="ff400-117">This example subtracts numeric literals.</span></span>  
  
```  
5 - 6.09  
```  
  
 <span data-ttu-id="ff400-118">L’exemple suivant soustrait la valeur de la colonne **StandardCost** de la valeur de la colonne **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="ff400-118">This example subtracts the value in the **StandardCost** column from the value in the **ListPrice** column.</span></span>  
  
```  
ListPrice - StandardCost  
```  
  
 <span data-ttu-id="ff400-119">L’exemple suivant soustrait une valeur calculée de la colonne **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="ff400-119">This example subtracts a calculated value from the **ListPrice** column.</span></span> <span data-ttu-id="ff400-120">La variable **Discount%** doit figurer entre crochets car elle contient le caractère « % ».</span><span class="sxs-lookup"><span data-stu-id="ff400-120">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="ff400-121">Pour plus d’informations, consultez [Identificateurs &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="ff400-121">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff400-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff400-122">See Also</span></span>  
 <span data-ttu-id="ff400-123">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="ff400-123">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="ff400-124">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ff400-124">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
