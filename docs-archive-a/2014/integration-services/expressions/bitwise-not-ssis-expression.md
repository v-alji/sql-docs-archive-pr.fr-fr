---
title: ~ (NOT au niveau du bit) (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- bitwise NOT (~)
- ~ (bitwise NOT)
ms.assetid: e4413ddd-0d0e-40c3-9c76-b5ce323218ec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75745a0650c1744064f2a671659879e11464514e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611919"
---
# <a name="-bitwise-not-ssis-expression"></a><span data-ttu-id="3f01e-102">~ (NOT au niveau du bit) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="3f01e-102">~ (Bitwise Not) (SSIS Expression)</span></span>
  <span data-ttu-id="3f01e-103">Effectue une négation au niveau du bit d'un entier.</span><span class="sxs-lookup"><span data-stu-id="3f01e-103">Performs a bitwise negation of an integer.</span></span> <span data-ttu-id="3f01e-104">Cet opérateur est applicable aux types de données entier signé et non signé.</span><span class="sxs-lookup"><span data-stu-id="3f01e-104">This operator can be applied to signed and unsigned integer data types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f01e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3f01e-105">Syntax</span></span>  
  
```  
  
~integer_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3f01e-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="3f01e-106">Arguments</span></span>  
 <span data-ttu-id="3f01e-107">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="3f01e-107">*integer_expression*</span></span>  
 <span data-ttu-id="3f01e-108">Toute expression valide d'un type de données integer.</span><span class="sxs-lookup"><span data-stu-id="3f01e-108">Is any valid expression of an integer data type.</span></span> <span data-ttu-id="3f01e-109">*integer*_*expression* est un nombre entier transformé en nombre binaire pour l’opération au niveau du bit.</span><span class="sxs-lookup"><span data-stu-id="3f01e-109">*integer*_*expression* is an integer that is transformed into a binary number for the bitwise operation.</span></span> <span data-ttu-id="3f01e-110">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3f01e-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3f01e-111">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="3f01e-111">Result Types</span></span>  
 <span data-ttu-id="3f01e-112">Retourne le type de données *integer_expression*.</span><span class="sxs-lookup"><span data-stu-id="3f01e-112">Returns the data type of *integer_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f01e-113">Notes</span><span class="sxs-lookup"><span data-stu-id="3f01e-113">Remarks</span></span>  
 <span data-ttu-id="3f01e-114">None</span><span class="sxs-lookup"><span data-stu-id="3f01e-114">None</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3f01e-115">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="3f01e-115">Expression Examples</span></span>  
 <span data-ttu-id="3f01e-116">L'exemple suivant réalise une opération NOT au niveau du bit ( ~ ) sur le nombre 170 (0000 0000 1010 1010).</span><span class="sxs-lookup"><span data-stu-id="3f01e-116">This example performs a bitwise ~ (NOT) operation on the number 170 (0000 0000 1010 1010).</span></span> <span data-ttu-id="3f01e-117">Le nombre est un entier signé.</span><span class="sxs-lookup"><span data-stu-id="3f01e-117">The number is a signed integer.</span></span>  
  
```  
  
~ 170  
```  
  
 <span data-ttu-id="3f01e-118">L'expression renvoie la valeur -170 (1111111101010101).</span><span class="sxs-lookup"><span data-stu-id="3f01e-118">The expression evaluates to -170 (1111111101010101).</span></span>  
  
 <span data-ttu-id="3f01e-119">0000000010101010</span><span class="sxs-lookup"><span data-stu-id="3f01e-119">0000000010101010</span></span>  
  
 ---------------------\-  
  
 <span data-ttu-id="3f01e-120">1111111101010101</span><span class="sxs-lookup"><span data-stu-id="3f01e-120">1111111101010101</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f01e-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f01e-121">See Also</span></span>  
 <span data-ttu-id="3f01e-122">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="3f01e-122">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="3f01e-123">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3f01e-123">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
