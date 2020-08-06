---
title: ROUND (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- rounding expressions
- ROUND function [SSIS]
ms.assetid: 376f1947-4fc5-4611-ad86-823e4db1b468
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d77045787eafbc3dd402db9982d8d7a98190bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701399"
---
# <a name="round-ssis-expression"></a><span data-ttu-id="485ec-102">ROUND (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="485ec-102">ROUND (SSIS Expression)</span></span>
  <span data-ttu-id="485ec-103">Renvoie une expression numérique, arrondie à la longueur ou à la précision indiquée.</span><span class="sxs-lookup"><span data-stu-id="485ec-103">Returns a numeric expression that is rounded to the specified length or precision.</span></span> <span data-ttu-id="485ec-104">La valeur du paramètre de longueur doit correspondre à un entier.</span><span class="sxs-lookup"><span data-stu-id="485ec-104">The length parameter must evaluate to an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="485ec-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="485ec-105">Syntax</span></span>  
  
```  
  
ROUND(numeric_expression,length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="485ec-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="485ec-106">Arguments</span></span>  
 <span data-ttu-id="485ec-107">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="485ec-107">*numeric_expression*</span></span>  
 <span data-ttu-id="485ec-108">Expression d'un type numérique valide.</span><span class="sxs-lookup"><span data-stu-id="485ec-108">Is an expression of a valid numeric type.</span></span> <span data-ttu-id="485ec-109">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="485ec-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="485ec-110">*length*</span><span class="sxs-lookup"><span data-stu-id="485ec-110">*length*</span></span>  
 <span data-ttu-id="485ec-111">Expression entière.</span><span class="sxs-lookup"><span data-stu-id="485ec-111">Is an integer expression.</span></span> <span data-ttu-id="485ec-112">Il s’agit de la précision avec laquelle *numeric_expression* est arrondie.</span><span class="sxs-lookup"><span data-stu-id="485ec-112">It is the precision to which *numeric_expression* is rounded.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="485ec-113">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="485ec-113">Result Types</span></span>  
 <span data-ttu-id="485ec-114">Type similaire à celui de *numeric*_*expression*.</span><span class="sxs-lookup"><span data-stu-id="485ec-114">The same type as *numeric*_*expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="485ec-115">Notes</span><span class="sxs-lookup"><span data-stu-id="485ec-115">Remarks</span></span>  
 <span data-ttu-id="485ec-116">L'argument *length* doit avoir une valeur positive entière ou égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="485ec-116">The *length* argument must evaluate to a positive integer or zero.</span></span>  
  
 <span data-ttu-id="485ec-117">La fonction ROUND renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="485ec-117">ROUND returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="485ec-118">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="485ec-118">Expression Examples</span></span>  
 <span data-ttu-id="485ec-119">Les exemples suivants arrondissent des littéraux numériques à une longueur de trois.</span><span class="sxs-lookup"><span data-stu-id="485ec-119">These examples round numeric literals to a length of three.</span></span> <span data-ttu-id="485ec-120">Le premier résultat obtenu est 137,1570, tandis que le second est 137,1580.</span><span class="sxs-lookup"><span data-stu-id="485ec-120">The first return result is 137.1570, the second 137.1580.</span></span>  
  
```  
ROUND(137.1574,3)  
ROUND(137.1575,3)  
```  
  
## <a name="see-also"></a><span data-ttu-id="485ec-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="485ec-121">See Also</span></span>  
 [<span data-ttu-id="485ec-122">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="485ec-122">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
