---
title: FLOOR (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- largest integer less than or equal to expression
- FLOOR function [SSIS]
ms.assetid: 168084db-badd-40f2-87b4-1f5bc45c3e24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b638c9a7215d120c562e416cdecee463f031ad2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604653"
---
# <a name="floor-ssis-expression"></a><span data-ttu-id="44cff-102">FLOOR (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="44cff-102">FLOOR (SSIS Expression)</span></span>
  <span data-ttu-id="44cff-103">Renvoie l'entier le plus élevé inférieur ou égal à une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="44cff-103">Returns the largest integer that is less than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44cff-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="44cff-104">Syntax</span></span>  
  
```  
  
FLOOR(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="44cff-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="44cff-105">Arguments</span></span>  
 <span data-ttu-id="44cff-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="44cff-106">*numeric_expression*</span></span>  
 <span data-ttu-id="44cff-107">Expression numérique valide.</span><span class="sxs-lookup"><span data-stu-id="44cff-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="44cff-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="44cff-108">Result Types</span></span>  
 <span data-ttu-id="44cff-109">Type de données numérique de l'expression de l'argument.</span><span class="sxs-lookup"><span data-stu-id="44cff-109">The numeric data type of the argument expression.</span></span> <span data-ttu-id="44cff-110">Le résultat est la partie entière de la valeur calculée dans le même type de données que *numeric_expression.*</span><span class="sxs-lookup"><span data-stu-id="44cff-110">The result is the integer portion of the calculated value in the same data type as *numeric_expression.*</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44cff-111">Notes</span><span class="sxs-lookup"><span data-stu-id="44cff-111">Remarks</span></span>  
 <span data-ttu-id="44cff-112">La fonction FLOOR renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="44cff-112">FLOOR returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="44cff-113">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="44cff-113">Expression Examples</span></span>  
 <span data-ttu-id="44cff-114">Les exemples suivants appliquent la fonction FLOOR à une valeur successivement positive, négative et nulle.</span><span class="sxs-lookup"><span data-stu-id="44cff-114">These examples apply the FLOOR function to positive, negative, and zero values.</span></span>  
  
```  
FLOOR(123.45)  
```  
  
 <span data-ttu-id="44cff-115">Retourne 123.00</span><span class="sxs-lookup"><span data-stu-id="44cff-115">Returns 123.00</span></span>  
  
```  
FLOOR(-123.45)  
```  
  
 <span data-ttu-id="44cff-116">Retourne -124.00</span><span class="sxs-lookup"><span data-stu-id="44cff-116">Returns -124.00</span></span>  
  
```  
FLOOR(0.00)  
```  
  
 <span data-ttu-id="44cff-117">Renvoie 0,00</span><span class="sxs-lookup"><span data-stu-id="44cff-117">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44cff-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="44cff-118">See Also</span></span>  
 <span data-ttu-id="44cff-119">[CEILING &#40;expression SSIS&#41;](ceiling-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="44cff-119">[CEILING &#40;SSIS Expression&#41;](ceiling-ssis-expression.md) </span></span>  
 [<span data-ttu-id="44cff-120">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="44cff-120">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
