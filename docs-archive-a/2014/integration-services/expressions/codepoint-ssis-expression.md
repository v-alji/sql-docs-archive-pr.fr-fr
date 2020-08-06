---
title: CODEPOINT (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CODEPOINT function
- leftmost character of expression
ms.assetid: 0783d05e-7f35-42fb-a2c4-9621c46effd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf05cc0838763ba9e22707af57892133d449da07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601009"
---
# <a name="codepoint-ssis-expression"></a><span data-ttu-id="94970-102">CODEPOINT (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="94970-102">CODEPOINT (SSIS Expression)</span></span>
  <span data-ttu-id="94970-103">Renvoie le point de code Unicode du caractère placé à l'extrême gauche d'une expression de caractères.</span><span class="sxs-lookup"><span data-stu-id="94970-103">Returns the Unicode code point of the leftmost character of a character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94970-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="94970-104">Syntax</span></span>  
  
```  
  
CODEPOINT(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="94970-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="94970-105">Arguments</span></span>  
 <span data-ttu-id="94970-106">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="94970-106">*character_expression*</span></span>  
 <span data-ttu-id="94970-107">Expression de type caractère dont le caractère situé à l'extrême gauche sera évalué.</span><span class="sxs-lookup"><span data-stu-id="94970-107">Is a character expression whose leftmost character will be evaluated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="94970-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="94970-108">Result Types</span></span>  
 <span data-ttu-id="94970-109">DT_UI2</span><span class="sxs-lookup"><span data-stu-id="94970-109">DT_UI2</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94970-110">Notes</span><span class="sxs-lookup"><span data-stu-id="94970-110">Remarks</span></span>  
 <span data-ttu-id="94970-111">*character_expression* doit être du type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="94970-111">*character_expression* must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="94970-112">CODEPOINT retourne un résultat Null si *character_expression* est Null ou est une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="94970-112">CODEPOINT returns a null result if *character_expression* is null or an empty string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="94970-113">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="94970-113">Expression Examples</span></span>  
 <span data-ttu-id="94970-114">L'exemple suivant utilise un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="94970-114">This example uses a string literal.</span></span> <span data-ttu-id="94970-115">Le résultat obtenu est 77, soit le point de code Unicode de M.</span><span class="sxs-lookup"><span data-stu-id="94970-115">The return result is 77, the Unicode code point for M.</span></span>  
  
```  
CODEPOINT("Mountain Bike")  
```  
  
 <span data-ttu-id="94970-116">L'exemple suivant utilise une variable.</span><span class="sxs-lookup"><span data-stu-id="94970-116">This example uses a variable.</span></span> <span data-ttu-id="94970-117">Si **Name** a pour valeur « Tout-terrain », le résultat obtenu est 84, soit le point de code Unicode de T.</span><span class="sxs-lookup"><span data-stu-id="94970-117">If **Name** is Touring Front Wheel, the return result is 84, the Unicode code point for T.</span></span>  
  
```  
CODEPOINT(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="94970-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94970-118">See Also</span></span>  
 [<span data-ttu-id="94970-119">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="94970-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
