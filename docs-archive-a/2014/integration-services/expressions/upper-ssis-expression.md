---
title: UPPER (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- UPPER function
- converting lowercase to uppercase
- uppercase characters [Integration Services]
- lowercase characters
ms.assetid: d33985f7-1048-4023-83e4-274090acda78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181e231d735a8e98cd2bce10c692e35668a686f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701316"
---
# <a name="upper-ssis-expression"></a><span data-ttu-id="670fd-102">UPPER (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="670fd-102">UPPER (SSIS Expression)</span></span>
  <span data-ttu-id="670fd-103">Renvoie une chaîne de caractères après avoir converti les caractères minuscules en caractères majuscules.</span><span class="sxs-lookup"><span data-stu-id="670fd-103">Returns a character expression after converting lowercase characters to uppercase characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="670fd-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="670fd-104">Syntax</span></span>  
  
```  
  
UPPER(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="670fd-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="670fd-105">Arguments</span></span>  
 <span data-ttu-id="670fd-106">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="670fd-106">*character_expression*</span></span>  
 <span data-ttu-id="670fd-107">Expression de type caractère à convertir en caractères majuscules.</span><span class="sxs-lookup"><span data-stu-id="670fd-107">Is a character expression to convert to uppercase characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="670fd-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="670fd-108">Result Types</span></span>  
 <span data-ttu-id="670fd-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="670fd-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="670fd-110">Notes</span><span class="sxs-lookup"><span data-stu-id="670fd-110">Remarks</span></span>  
 <span data-ttu-id="670fd-111">La fonction UPPER n'est opérationnelle qu'avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="670fd-111">UPPER works only with the DT_WSTR data type.</span></span> <span data-ttu-id="670fd-112">Un argument *expression_caractère* qui est un littéral de chaîne ou une colonne de données avec le type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que UPPER effectue son opération.</span><span class="sxs-lookup"><span data-stu-id="670fd-112">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before UPPER performs its operation.</span></span> <span data-ttu-id="670fd-113">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="670fd-113">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="670fd-114">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="670fd-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="670fd-115">La fonction UPPER renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="670fd-115">UPPER returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="670fd-116">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="670fd-116">Expression Examples</span></span>  
 <span data-ttu-id="670fd-117">L'exemple suivant convertit un littéral de chaîne en caractères majuscules.</span><span class="sxs-lookup"><span data-stu-id="670fd-117">This example converts a string literal to uppercase characters.</span></span> <span data-ttu-id="670fd-118">Le résultat obtenu est « HELLO ».</span><span class="sxs-lookup"><span data-stu-id="670fd-118">The return result is "HELLO".</span></span>  
  
```  
UPPER("hello")  
```  
  
 <span data-ttu-id="670fd-119">L'exemple suivant transforme le premier caractère de la colonne **FirstName** en un caractère majuscule.</span><span class="sxs-lookup"><span data-stu-id="670fd-119">This example converts the first character in the **FirstName** column to an uppercase character.</span></span> <span data-ttu-id="670fd-120">Si l'argument **FirstName** a pour valeur « anna », le résultat obtenu est « A ».</span><span class="sxs-lookup"><span data-stu-id="670fd-120">If **FirstName** is anna, the return result is "A".</span></span> <span data-ttu-id="670fd-121">Pour plus d’informations, consultez [SUBSTRING &#40;expression SSIS&#41;](substring-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="670fd-121">For more information, see [SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md).</span></span>  
  
```  
UPPER(SUBSTRING(FirstName, 1, 1))  
```  
  
 <span data-ttu-id="670fd-122">L'exemple suivant convertit la valeur de la variable **PostalCode** en caractères majuscules.</span><span class="sxs-lookup"><span data-stu-id="670fd-122">This example converts the value in the **PostalCode** variable to uppercase characters.</span></span> <span data-ttu-id="670fd-123">Si la variable **PostalCode** a pour valeur « k4b1s2 », le résultat obtenu est « K4B1S2 ».</span><span class="sxs-lookup"><span data-stu-id="670fd-123">If **PostalCode** is k4b1s2, the return result is "K4B1S2".</span></span>  
  
```  
UPPER(@PostalCode)  
```  
  
## <a name="see-also"></a><span data-ttu-id="670fd-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="670fd-124">See Also</span></span>  
 <span data-ttu-id="670fd-125">[LOWER &#40;expression SSIS&#41;](lower-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="670fd-125">[LOWER &#40;SSIS Expression&#41;](lower-ssis-expression.md) </span></span>  
 [<span data-ttu-id="670fd-126">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="670fd-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
