---
title: CEILING (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- smallest integer great than or equal to expression
- CEILING function [SSIS]
ms.assetid: c35bd4ee-1ab6-46ab-89a7-cf771527faa2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd2f9f455226925d6bf00842e80a8713e6c72771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614743"
---
# <a name="ceiling-ssis-expression"></a><span data-ttu-id="4008a-102">CEILING (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="4008a-102">CEILING (SSIS Expression)</span></span>
  <span data-ttu-id="4008a-103">Renvoie le plus petit entier qui est supérieur ou égal à une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="4008a-103">Returns the smallest integer that is greater than or equal to a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4008a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4008a-104">Syntax</span></span>  
  
```  
  
CEILING(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="4008a-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="4008a-105">Arguments</span></span>  
 <span data-ttu-id="4008a-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="4008a-106">*numeric_expression*</span></span>  
 <span data-ttu-id="4008a-107">Expression numérique valide.</span><span class="sxs-lookup"><span data-stu-id="4008a-107">Is a valid numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4008a-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="4008a-108">Result Types</span></span>  
 <span data-ttu-id="4008a-109">Type de données de l'expression numérique envoyée à la fonction.</span><span class="sxs-lookup"><span data-stu-id="4008a-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4008a-110">Notes</span><span class="sxs-lookup"><span data-stu-id="4008a-110">Remarks</span></span>  
 <span data-ttu-id="4008a-111">La fonction CEILING renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="4008a-111">CEILING returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="4008a-112">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="4008a-112">Expression Examples</span></span>  
 <span data-ttu-id="4008a-113">Les exemples suivants appliquent la fonction CEILING à une valeur successivement positive, négative et nulle.</span><span class="sxs-lookup"><span data-stu-id="4008a-113">These examples apply the CEILING function to positive, negative, and zero values.</span></span>  
  
```  
CEILING(123.74)  
```  
  
 <span data-ttu-id="4008a-114">Retourne 124.00</span><span class="sxs-lookup"><span data-stu-id="4008a-114">Returns 124.00</span></span>  
  
```  
CEILING(-124.27)  
```  
  
 <span data-ttu-id="4008a-115">Retourne -124.00</span><span class="sxs-lookup"><span data-stu-id="4008a-115">Returns -124.00</span></span>  
  
```  
CEILING(0.00)  
```  
  
 <span data-ttu-id="4008a-116">Renvoie 0,00</span><span class="sxs-lookup"><span data-stu-id="4008a-116">Returns 0.00</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4008a-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4008a-117">See Also</span></span>  
 <span data-ttu-id="4008a-118">[FLOOR &#40;expression SSIS&#41;](floor-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4008a-118">[FLOOR &#40;SSIS Expression&#41;](floor-ssis-expression.md) </span></span>  
 [<span data-ttu-id="4008a-119">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4008a-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
