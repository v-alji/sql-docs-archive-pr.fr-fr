---
title: '- (Négatif) (expression SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '- (negative)'
- negative operator (-)
ms.assetid: f0118dfc-aced-4de2-953e-5ebf9c962b8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2a2d8ba292f2d24633598ab080ddf75ded5e8bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704320"
---
# <a name="--negate-ssis-expression"></a><span data-ttu-id="11a1a-102">- (Négatif) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="11a1a-102">- (Negate) (SSIS Expression)</span></span>
  <span data-ttu-id="11a1a-103">Inverse une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="11a1a-103">Negates a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a1a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="11a1a-104">Syntax</span></span>  
  
```  
  
-numeric_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="11a1a-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="11a1a-105">Arguments</span></span>  
 <span data-ttu-id="11a1a-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="11a1a-106">*numeric_expression*</span></span>  
 <span data-ttu-id="11a1a-107">Toute expression valide d’un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="11a1a-107">Is any valid expression of any numeric data type.</span></span> <span data-ttu-id="11a1a-108">Seuls les types de données numériques signés sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="11a1a-108">Only signed numeric data types are supported.</span></span> <span data-ttu-id="11a1a-109">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="11a1a-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="11a1a-110">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="11a1a-110">Result Types</span></span>  
 <span data-ttu-id="11a1a-111">Retourne le type de données *numeric_expression*.</span><span class="sxs-lookup"><span data-stu-id="11a1a-111">Returns the data type of *numeric_expression*.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="11a1a-112">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="11a1a-112">Expression Examples</span></span>  
 <span data-ttu-id="11a1a-113">Cet exemple inverse la valeur de la variable **Counter** et ajoute le littéral numérique 50.</span><span class="sxs-lookup"><span data-stu-id="11a1a-113">This example negates the value of the **Counter** variable and adds the numeric literal 50.</span></span>  
  
```  
-@Counter + 50  
```  
  
## <a name="see-also"></a><span data-ttu-id="11a1a-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11a1a-114">See Also</span></span>  
 <span data-ttu-id="11a1a-115">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="11a1a-115">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="11a1a-116">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="11a1a-116">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
