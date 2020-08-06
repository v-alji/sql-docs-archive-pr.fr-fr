---
title: '* (Multiplier) (expression SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '* (multiply operator)'
- multiply operator (*)
ms.assetid: d457f052-ffbb-4485-833f-f4bed4349b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16d8429a869b60be31a94244a2ce47d515770c6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604646"
---
# <a name="-multiply-ssis-expression"></a><span data-ttu-id="fa5fe-102">\* (Multiplication) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="fa5fe-102">\* (Multiply) (SSIS Expression)</span></span>
  <span data-ttu-id="fa5fe-103">Multiplie deux expressions numériques.</span><span class="sxs-lookup"><span data-stu-id="fa5fe-103">Multiplies two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa5fe-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fa5fe-104">Syntax</span></span>  
  
```  
  
numeric_expression1 * numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="fa5fe-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="fa5fe-105">Arguments</span></span>  
 <span data-ttu-id="fa5fe-106">*expression_numérique1, expression_numérique2*</span><span class="sxs-lookup"><span data-stu-id="fa5fe-106">*numeric_expression1, numeric_expression2*</span></span>  
 <span data-ttu-id="fa5fe-107">Toute expression valide d'un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="fa5fe-107">Is any valid expression of a numeric data type.</span></span> <span data-ttu-id="fa5fe-108">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fa5fe-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="fa5fe-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="fa5fe-109">Result Types</span></span>  
 <span data-ttu-id="fa5fe-110">Déterminés par les types de données des deux arguments.</span><span class="sxs-lookup"><span data-stu-id="fa5fe-110">Determined by data types of the two arguments.</span></span> <span data-ttu-id="fa5fe-111">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="fa5fe-111">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa5fe-112">Notes</span><span class="sxs-lookup"><span data-stu-id="fa5fe-112">Remarks</span></span>  
 <span data-ttu-id="fa5fe-113">Si l'un des opérandes est NULL, le résultat est NULL.</span><span class="sxs-lookup"><span data-stu-id="fa5fe-113">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="fa5fe-114">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="fa5fe-114">Expression Examples</span></span>  
 <span data-ttu-id="fa5fe-115">L'exemple suivant multiplie des littéraux numériques.</span><span class="sxs-lookup"><span data-stu-id="fa5fe-115">This example multiplies numeric literals.</span></span>  
  
```  
5 * 6.09  
```  
  
 <span data-ttu-id="fa5fe-116">L’exemple suivant multiplie les valeurs de la colonne **ListPrice** par 10 pour cent.</span><span class="sxs-lookup"><span data-stu-id="fa5fe-116">This example multiplies values in the **ListPrice** column by 10 percent.</span></span>  
  
```  
ListPrice * .10  
```  
  
 <span data-ttu-id="fa5fe-117">Cet exemple soustrait le résultat d’une expression de la colonne **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="fa5fe-117">This example subtracts the result of an expression from the **ListPrice** column.</span></span> <span data-ttu-id="fa5fe-118">La variable **Discount%** doit figurer entre crochets car elle contient le caractère « % ».</span><span class="sxs-lookup"><span data-stu-id="fa5fe-118">The variable **Discount%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="fa5fe-119">Pour plus d’informations, consultez [Identificateurs &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="fa5fe-119">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
ListPrice - (ListPrice * @[Discount%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa5fe-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa5fe-120">See Also</span></span>  
 <span data-ttu-id="fa5fe-121">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="fa5fe-121">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="fa5fe-122">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="fa5fe-122">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
