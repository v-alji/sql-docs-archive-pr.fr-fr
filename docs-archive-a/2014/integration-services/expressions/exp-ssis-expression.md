---
title: EXP (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- exponential functions
- EXP function
ms.assetid: 4cd96d3c-58c9-4a67-a6f6-b72758232912
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 150c92355ab3e0d3a028c98defe2e2fa9a1bf8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610738"
---
# <a name="exp-ssis-expression"></a><span data-ttu-id="1b0d7-102">EXP (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="1b0d7-102">EXP (SSIS Expression)</span></span>
  <span data-ttu-id="1b0d7-103">Renvoie l'exposant en base e d'une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-103">Returns the exponent to base e of a numeric expression.</span></span> <span data-ttu-id="1b0d7-104">La fonction EXP est complémentaire de l'action LN et est parfois appelée « antilogarithme ».</span><span class="sxs-lookup"><span data-stu-id="1b0d7-104">The EXP function complements the action of the LN function and is sometimes referred to as the antilogarithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b0d7-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1b0d7-105">Syntax</span></span>  
  
```  
  
EXP(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b0d7-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="1b0d7-106">Arguments</span></span>  
 <span data-ttu-id="1b0d7-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="1b0d7-107">*numeric_expression*</span></span>  
 <span data-ttu-id="1b0d7-108">Expression numérique valide.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-108">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1b0d7-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="1b0d7-109">Result Types</span></span>  
 <span data-ttu-id="1b0d7-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="1b0d7-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b0d7-111">Notes</span><span class="sxs-lookup"><span data-stu-id="1b0d7-111">Remarks</span></span>  
 <span data-ttu-id="1b0d7-112">L'expression numérique est convertie vers le type de données DT_R8 avant le calcul du l'exposant.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-112">The numeric expression is cast to the DT_R8 data type before the exponent is computed.</span></span> <span data-ttu-id="1b0d7-113">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1b0d7-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="1b0d7-114">Le résultat obtenu est toujours un nombre positif.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-114">The return result is always a positive number.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="1b0d7-115">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="1b0d7-115">Expression Examples</span></span>  
 <span data-ttu-id="1b0d7-116">Les exemples suivants appliquent la fonction EXP à des valeurs positive, négative, ainsi qu'à la valeur zéro.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-116">These examples apply the EXP function to positive and negative values and to zero.</span></span>  
  
```  
EXP(74)  
```  
  
 <span data-ttu-id="1b0d7-117">Renvoie 1,373382979540176E+32.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-117">Returns 1.373382979540176E+32.</span></span>  
  
```  
EXP(-27)  
```  
  
 <span data-ttu-id="1b0d7-118">Renvoie 1,879528816539083E-12.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-118">Returns 1.879528816539083E-12.</span></span>  
  
```  
EXP(0)  
```  
  
 <span data-ttu-id="1b0d7-119">Renvoie 1.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-119">Returns 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0d7-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b0d7-120">See Also</span></span>  
 <span data-ttu-id="1b0d7-121">[LOG &#40;expression SSIS&#41;](log-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1b0d7-121">[LOG &#40;SSIS Expression&#41;](log-ssis-expression.md) </span></span>  
 [<span data-ttu-id="1b0d7-122">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1b0d7-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
