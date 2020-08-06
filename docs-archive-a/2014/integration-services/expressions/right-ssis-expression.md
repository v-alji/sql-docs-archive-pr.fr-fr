---
title: RIGHT (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RIGHT function
ms.assetid: 83e70e75-4be5-4783-a8cf-032f82afe16e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2584ee33ecbf0436c4e3dc6e92b957e60ae396ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701406"
---
# <a name="right-ssis-expression"></a><span data-ttu-id="75f7c-102">RIGHT (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="75f7c-102">RIGHT (SSIS Expression)</span></span>
  <span data-ttu-id="75f7c-103">Renvoie le nombre de caractères spécifié en commençant par la partie la plus à droite d'une expression de caractères donnée.</span><span class="sxs-lookup"><span data-stu-id="75f7c-103">Returns the specified number of characters from the rightmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f7c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="75f7c-104">Syntax</span></span>  
  
```  
  
RIGHT(character_expression,integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="75f7c-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="75f7c-105">Arguments</span></span>  
 <span data-ttu-id="75f7c-106">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="75f7c-106">*character_expression*</span></span>  
 <span data-ttu-id="75f7c-107">Expression de caractères à partir de laquelle doivent être extraits les caractères.</span><span class="sxs-lookup"><span data-stu-id="75f7c-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="75f7c-108">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="75f7c-108">*integer_expression*</span></span>  
 <span data-ttu-id="75f7c-109">Expression entière indiquant le nombre de caractères à renvoyer.</span><span class="sxs-lookup"><span data-stu-id="75f7c-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="75f7c-110">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="75f7c-110">Result Types</span></span>  
 <span data-ttu-id="75f7c-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="75f7c-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75f7c-112">Notes</span><span class="sxs-lookup"><span data-stu-id="75f7c-112">Remarks</span></span>  
 <span data-ttu-id="75f7c-113">Si *integer_expression* est supérieure à la longueur de *character_expression*, la fonction retourne *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="75f7c-113">If *integer_expression* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="75f7c-114">Si l’argument *integer_expression* a pour valeur zéro, la fonction renvoie une chaîne de longueur nulle.</span><span class="sxs-lookup"><span data-stu-id="75f7c-114">If *integer_expression* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="75f7c-115">Si l’argument *integer_expression* est un nombre négatif, la fonction renvoie une erreur.</span><span class="sxs-lookup"><span data-stu-id="75f7c-115">If *integer_expression* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="75f7c-116">L’argument *integer_expression* peut accepter des variables et des colonnes.</span><span class="sxs-lookup"><span data-stu-id="75f7c-116">The *integer_expression* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="75f7c-117">La fonction RIGHT n'est opérationnelle qu'avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="75f7c-117">RIGHT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="75f7c-118">Un argument *character_expression* représentant un littéral de chaîne ou une colonne de données du type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que la fonction RIGHT ne soit exécutée.</span><span class="sxs-lookup"><span data-stu-id="75f7c-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RIGHT performs its operation.</span></span> <span data-ttu-id="75f7c-119">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="75f7c-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="75f7c-120">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="75f7c-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="75f7c-121">La fonction RIGHT renvoie un résultat NULL si l'un des arguments est NULL.</span><span class="sxs-lookup"><span data-stu-id="75f7c-121">RIGHT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="75f7c-122">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="75f7c-122">Expression Examples</span></span>  
 <span data-ttu-id="75f7c-123">L'exemple suivant utilise un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="75f7c-123">The following example uses a string literal.</span></span> <span data-ttu-id="75f7c-124">Le résultat obtenu est `"Bike"`.</span><span class="sxs-lookup"><span data-stu-id="75f7c-124">The return result is `"Bike"`.</span></span>  
  
```  
RIGHT("Mountain Bike", 4)  
```  
  
 <span data-ttu-id="75f7c-125">L'exemple suivant retourne le nombre de caractères situés le plus à droite dans la variable `Times` depuis la colonne `Name` .</span><span class="sxs-lookup"><span data-stu-id="75f7c-125">The following example returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="75f7c-126">Si `Name` est `Touring Front Wheel` et `Times` est 5, le résultat retourné est `"Wheel"`.</span><span class="sxs-lookup"><span data-stu-id="75f7c-126">If `Name` is `Touring Front Wheel` and `Times` is 5, the return result is `"Wheel"`.</span></span>  
  
```  
RIGHT(Name, @Times)  
```  
  
 <span data-ttu-id="75f7c-127">L'exemple suivant retourne également le nombre de caractères situés le plus à droite dans la variable `Times` de la colonne `Name` .</span><span class="sxs-lookup"><span data-stu-id="75f7c-127">The following example also returns the number of rightmost characters that is specified in the `Times` variable, from the `Name` column.</span></span> <span data-ttu-id="75f7c-128">`Times` La variable est du type de données noninteger et l’expression comprend une conversion explicite vers le type de données DT_I2.</span><span class="sxs-lookup"><span data-stu-id="75f7c-128">`Times` has a noninteger data type and the expression includes an explicit cast to the DT_I2 data type.</span></span> <span data-ttu-id="75f7c-129">Si `Name` est `Touring Front Wheel` et `Times` est `4.32`, le résultat obtenu est `"heel"` parce que la fonction RIGHT convertit la valeur de 4.32 à 4, puis retourne les quatre caractères situés les plus à droite.</span><span class="sxs-lookup"><span data-stu-id="75f7c-129">If `Name` is `Touring Front Wheel` and `Times` is `4.32`, the return result is `"heel"` because the RIGHT function converts the value of 4.32 to 4, and then returns the rightmost four characters.</span></span>  
  
```  
RIGHT(Name, (DT_I2)@Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="75f7c-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75f7c-130">See Also</span></span>  
 <span data-ttu-id="75f7c-131">[LEFT &#40;expression SSIS&#41;](left-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="75f7c-131">[LEFT &#40;SSIS Expression&#41;](left-ssis-expression.md) </span></span>  
 [<span data-ttu-id="75f7c-132">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="75f7c-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
