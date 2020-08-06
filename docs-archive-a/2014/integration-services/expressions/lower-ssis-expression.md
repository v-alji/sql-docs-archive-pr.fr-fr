---
title: LOWER (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting uppercase to lowercase
- LOWER function
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: 109328e1-5604-40ff-895e-f2e7c13fff41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 180be8f3cfb5a15eb0fcd6ddd3d63b09fe874af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604650"
---
# <a name="lower-ssis-expression"></a><span data-ttu-id="65525-102">LOWER (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="65525-102">LOWER (SSIS Expression)</span></span>
  <span data-ttu-id="65525-103">Renvoie une expression de caractères après avoir transformé les caractères majuscules en caractères minuscules.</span><span class="sxs-lookup"><span data-stu-id="65525-103">Returns a character expression after converting uppercase characters to lowercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65525-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="65525-104">Syntax</span></span>  
  
```  
  
LOWER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="65525-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="65525-105">Arguments</span></span>  
 <span data-ttu-id="65525-106">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="65525-106">*character_expression*</span></span>  
 <span data-ttu-id="65525-107">Expression de type caractère à convertir en caractères minuscules.</span><span class="sxs-lookup"><span data-stu-id="65525-107">Is a character expression to convert to lowercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="65525-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="65525-108">Result Types</span></span>  
 <span data-ttu-id="65525-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="65525-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65525-110">Notes</span><span class="sxs-lookup"><span data-stu-id="65525-110">Remarks</span></span>  
 <span data-ttu-id="65525-111">La fonction LOWER n'est opérationnelle qu'avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="65525-111">LOWER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="65525-112">Un argument *character_expression* qui est un littéral de chaîne ou une colonne de données avec le type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que UPPER effectue son opération.</span><span class="sxs-lookup"><span data-stu-id="65525-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LOWER performs its operation.</span></span> <span data-ttu-id="65525-113">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="65525-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="65525-114">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="65525-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="65525-115">La fonction LOWER renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="65525-115">LOWER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="65525-116">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="65525-116">Expression Examples</span></span>  
 <span data-ttu-id="65525-117">L'exemple suivant convertit un littéral de chaîne en caractères minuscules.</span><span class="sxs-lookup"><span data-stu-id="65525-117">This example converts a string literal to lowercase characters.</span></span> <span data-ttu-id="65525-118">Le résultat obtenu est « new york ».</span><span class="sxs-lookup"><span data-stu-id="65525-118">The return result is "new york".</span></span>  
  
```  
LOWER("New York")  
```  
  
 <span data-ttu-id="65525-119">L’exemple suivant convertit tous les caractères de la colonne d’entrée **Color** , à l’exception du premier caractère, en caractères minuscules.</span><span class="sxs-lookup"><span data-stu-id="65525-119">This example converts all characters from the **Color** input column, except the first character, to lowercase characters.</span></span> <span data-ttu-id="65525-120">Si la colonne Color a pour valeur JAUNE, le résultat obtenu est « Jaune ».</span><span class="sxs-lookup"><span data-stu-id="65525-120">If Color is YELLOW, the return result is "Yellow".</span></span> <span data-ttu-id="65525-121">Pour plus d’informations, consultez [SUBSTRING &#40;expression SSIS&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="65525-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
LOWER(SUBSTRING(Color, 2, 15))  
```  
  
 <span data-ttu-id="65525-122">L’exemple suivant convertit la valeur de la variable **CityName** en caractères minuscules.</span><span class="sxs-lookup"><span data-stu-id="65525-122">This example converts the value in the **CityName** variable to lowercase characters.</span></span>  
  
```  
LOWER(@CityName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="65525-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65525-123">See Also</span></span>  
 <span data-ttu-id="65525-124">[UPPER &#40;expression SSIS&#41;](upper-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="65525-124">[UPPER &#40;SSIS Expression&#41;](upper-ssis-expression.md) </span></span>  
 [<span data-ttu-id="65525-125">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="65525-125">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
