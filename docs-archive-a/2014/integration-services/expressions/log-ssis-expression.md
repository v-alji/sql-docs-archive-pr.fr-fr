---
title: LOG (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- base-10 logarithms
- LOG function
ms.assetid: f7fccace-c178-4e13-bde9-7dc4ef1d98fa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0de84c1a92f94507bcc69c47cc4d9b6cda50a4f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611914"
---
# <a name="log-ssis-expression"></a><span data-ttu-id="a54ea-102">LOG (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="a54ea-102">LOG (SSIS Expression)</span></span>
  <span data-ttu-id="a54ea-103">Renvoie le logarithme de base 10 d'une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="a54ea-103">Returns the base-10 logarithm of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a54ea-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a54ea-104">Syntax</span></span>  
  
```  
  
LOG(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="a54ea-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="a54ea-105">Arguments</span></span>  
 <span data-ttu-id="a54ea-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="a54ea-106">*numeric_expression*</span></span>  
 <span data-ttu-id="a54ea-107">Expression numérique valide différente de zéro ou non négative.</span><span class="sxs-lookup"><span data-stu-id="a54ea-107">Is a valid nonzero or nonnegative numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a54ea-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="a54ea-108">Result Types</span></span>  
 <span data-ttu-id="a54ea-109">DT_R8</span><span class="sxs-lookup"><span data-stu-id="a54ea-109">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a54ea-110">Notes</span><span class="sxs-lookup"><span data-stu-id="a54ea-110">Remarks</span></span>  
 <span data-ttu-id="a54ea-111">*L’expression numérique* est convertie vers le type de données DT_R8 avant le calcul du logarithme.</span><span class="sxs-lookup"><span data-stu-id="a54ea-111">The *numeric expression* is cast to the DT_R8 data type before the logarithm is computed.</span></span> <span data-ttu-id="a54ea-112">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a54ea-112">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="a54ea-113">Si l’argument *numeric_expression* donne une valeur inférieure ou égale à zéro, le résultat obtenu est NULL.</span><span class="sxs-lookup"><span data-stu-id="a54ea-113">If *numeric_expression* evaluates to zero or a negative value, the return result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="a54ea-114">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="a54ea-114">Expression Examples</span></span>  
 <span data-ttu-id="a54ea-115">L'exemple suivant utilise un littéral numérique.</span><span class="sxs-lookup"><span data-stu-id="a54ea-115">This example uses a numeric literal.</span></span> <span data-ttu-id="a54ea-116">La fonction renvoie la valeur 1,988291341907488.</span><span class="sxs-lookup"><span data-stu-id="a54ea-116">The function returns the value 1.988291341907488.</span></span>  
  
```  
LOG(97.34)  
```  
  
 <span data-ttu-id="a54ea-117">L'exemple suivant utilise la colonne **Length**.</span><span class="sxs-lookup"><span data-stu-id="a54ea-117">This example uses the column **Length**.</span></span> <span data-ttu-id="a54ea-118">Si la valeur de la colonne est 101,24, la fonction renvoie 2,005352136486217.</span><span class="sxs-lookup"><span data-stu-id="a54ea-118">If the column is 101.24, the function returns 2.005352136486217.</span></span>  
  
```  
LOG(Length)   
```  
  
 <span data-ttu-id="a54ea-119">L'exemple suivant utilise la variable **Length**.</span><span class="sxs-lookup"><span data-stu-id="a54ea-119">This example uses the variable **Length**.</span></span> <span data-ttu-id="a54ea-120">La variable doit être d'un type de données numérique ou l'expression doit comprendre une conversion explicite en un type de données [!INCLUDE[ssIS](../../includes/ssis-md.md)] numérique.</span><span class="sxs-lookup"><span data-stu-id="a54ea-120">The variable must have a numeric data type or the expression must include an explicit cast to a numeric [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span> <span data-ttu-id="a54ea-121">Si la variable **Length** a pour valeur 234,567, la fonction renvoie 2,370266913465859.</span><span class="sxs-lookup"><span data-stu-id="a54ea-121">If **Length** is 234.567, the function returns 2.370266913465859.</span></span>  
  
```  
LOG(@Length)   
```  
  
## <a name="see-also"></a><span data-ttu-id="a54ea-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a54ea-122">See Also</span></span>  
 <span data-ttu-id="a54ea-123">[EXP &#40;expression SSIS&#41;](exp-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a54ea-123">[EXP &#40;SSIS Expression&#41;](exp-ssis-expression.md) </span></span>  
 <span data-ttu-id="a54ea-124">[LN &#40;expression SSIS&#41;](ln-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a54ea-124">[LN &#40;SSIS Expression&#41;](ln-ssis-expression.md) </span></span>  
 [<span data-ttu-id="a54ea-125">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="a54ea-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
