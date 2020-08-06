---
title: () (Parenthèses) (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- () (parentheses operator)
- evaluation order [Integration Services]
- parentheses operator ()
ms.assetid: 931e10eb-1707-4121-b2f1-43565561119f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e390e10e485bd9cc22480300b6a9c33098bda8f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707680"
---
# <a name="-parentheses-ssis-expression"></a><span data-ttu-id="5cec6-102">() (Parenthèses) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="5cec6-102">() (Parentheses) (SSIS Expression)</span></span>
  <span data-ttu-id="5cec6-103">Identifie l'ordre d'évaluation des expressions.</span><span class="sxs-lookup"><span data-stu-id="5cec6-103">Identifies the evaluation order of expressions.</span></span> <span data-ttu-id="5cec6-104">Les expressions entre parenthèses ont la priorité d'évaluation la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="5cec6-104">Expressions enclosed in parentheses have the highest evaluation precedence.</span></span> <span data-ttu-id="5cec6-105">L'évaluation des expressions imbriquées placées entre parenthèses commence par celle située le plus à l'intérieur, puis se poursuit jusqu'à celle située le plus à l'extérieur.</span><span class="sxs-lookup"><span data-stu-id="5cec6-105">Nested expressions enclosed in parentheses are evaluated in inner-to-outer order.</span></span>  
  
 <span data-ttu-id="5cec6-106">Les parenthèses permettent également de faciliter la compréhension des expressions complexes.</span><span class="sxs-lookup"><span data-stu-id="5cec6-106">Parentheses are also used to make complex expressions easier to understand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cec6-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5cec6-107">Syntax</span></span>  
  
```  
  
(expression)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="5cec6-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="5cec6-108">Arguments</span></span>  
 <span data-ttu-id="5cec6-109">*expression*</span><span class="sxs-lookup"><span data-stu-id="5cec6-109">*expression*</span></span>  
 <span data-ttu-id="5cec6-110">Peut être toute expression valide.</span><span class="sxs-lookup"><span data-stu-id="5cec6-110">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5cec6-111">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="5cec6-111">Result Types</span></span>  
 <span data-ttu-id="5cec6-112">Le type de données *expression*.</span><span class="sxs-lookup"><span data-stu-id="5cec6-112">The data type of *expression*.</span></span> <span data-ttu-id="5cec6-113">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5cec6-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="5cec6-114">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="5cec6-114">Expression Examples</span></span>  
 <span data-ttu-id="5cec6-115">Cet exemple illustre la façon dont l'utilisation des parenthèses modifie la priorité des opérateurs.</span><span class="sxs-lookup"><span data-stu-id="5cec6-115">This example shows how the use of parenthesis modifies the precedence of operators.</span></span> <span data-ttu-id="5cec6-116">La première expression totalise 100 tandis que la seconde cumule à 31.</span><span class="sxs-lookup"><span data-stu-id="5cec6-116">The first expression evaluates to 100, whereas the second one evaluates to 31.</span></span>  
  
```  
(5 + 5) * (4 + 6)  
5 + 5 * 4 + 6  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cec6-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5cec6-117">See Also</span></span>  
 <span data-ttu-id="5cec6-118">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="5cec6-118">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="5cec6-119">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5cec6-119">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
