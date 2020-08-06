---
title: SUBSTRING (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SUBSTRING function
- part of expression returned [Integration Services]
ms.assetid: 3a46748a-f5f8-4a6c-9108-673666754068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba53676bc6d13ed34892f48fca3b70372cb30604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701357"
---
# <a name="substring-ssis-expression"></a><span data-ttu-id="960a2-102">SUBSTRING (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="960a2-102">SUBSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="960a2-103">Renvoie la partie d'une expression de caractères qui commence à la position spécifiée et qui a la longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="960a2-103">Returns the part of a character expression that starts at the specified position and has the specified length.</span></span> <span data-ttu-id="960a2-104">Les paramètres *position* et *length* doivent correspondre à des entiers.</span><span class="sxs-lookup"><span data-stu-id="960a2-104">The *position* parameter and the *length* parameter must evaluate to integers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="960a2-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="960a2-105">Syntax</span></span>  
  
```  
  
SUBSTRING(character_expression, position, length)  
```  
  
## <a name="arguments"></a><span data-ttu-id="960a2-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="960a2-106">Arguments</span></span>  
 <span data-ttu-id="960a2-107">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="960a2-107">*character_expression*</span></span>  
 <span data-ttu-id="960a2-108">Expression de caractères à partir de laquelle doivent être extraits les caractères.</span><span class="sxs-lookup"><span data-stu-id="960a2-108">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="960a2-109">*position*</span><span class="sxs-lookup"><span data-stu-id="960a2-109">*position*</span></span>  
 <span data-ttu-id="960a2-110">Entier précisant où commence sous-chaîne.</span><span class="sxs-lookup"><span data-stu-id="960a2-110">Is an integer that specifies where the substring begins.</span></span>  
  
 <span data-ttu-id="960a2-111">*length*</span><span class="sxs-lookup"><span data-stu-id="960a2-111">*length*</span></span>  
 <span data-ttu-id="960a2-112">Entier exprimant, en nombre de caractères, la longueur de la sous-chaîne.</span><span class="sxs-lookup"><span data-stu-id="960a2-112">Is an integer that specifies the length of the substring as number of characters.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="960a2-113">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="960a2-113">Result Types</span></span>  
 <span data-ttu-id="960a2-114">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="960a2-114">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="960a2-115">Notes</span><span class="sxs-lookup"><span data-stu-id="960a2-115">Remarks</span></span>  
 <span data-ttu-id="960a2-116">SUBSTRING utilise un index de base un.</span><span class="sxs-lookup"><span data-stu-id="960a2-116">SUBSTRING uses a one-based index.</span></span> <span data-ttu-id="960a2-117">Si *position* est 1, la sous-chaîne commence par le premier caractère de *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="960a2-117">If *position* is 1, the substring begins with the first character in *character_expression*.</span></span>  
  
 <span data-ttu-id="960a2-118">La fonction SUBSTRING n'est opérationnelle qu'avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="960a2-118">SUBSTRING works only with the DT_WSTR data type.</span></span> <span data-ttu-id="960a2-119">Un argument *character_expression* représentant un littéral de chaîne ou une colonne de données du type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que la fonction SUBSTRING soit exécutée.</span><span class="sxs-lookup"><span data-stu-id="960a2-119">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before SUBSTRING performs its operation.</span></span> <span data-ttu-id="960a2-120">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="960a2-120">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="960a2-121">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="960a2-121">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="960a2-122">La fonction SUBSTRING renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="960a2-122">SUBSTRING returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="960a2-123">Tous les arguments de l'expression peuvent utiliser des variables et des colonnes.</span><span class="sxs-lookup"><span data-stu-id="960a2-123">All arguments in the expression can use variables and columns.</span></span>  
  
 <span data-ttu-id="960a2-124">L'argument *length* peut être supérieur à la longueur de la chaîne.</span><span class="sxs-lookup"><span data-stu-id="960a2-124">The *length* argument can exceed the length of the string.</span></span> <span data-ttu-id="960a2-125">Dans ce cas, la fonction renvoie le reste de la chaîne.</span><span class="sxs-lookup"><span data-stu-id="960a2-125">In that case, the function returns the remainder of the string.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="960a2-126">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="960a2-126">Expression Examples</span></span>  
 <span data-ttu-id="960a2-127">L'exemple suivant renvoie deux caractères, à partir du quatrième caractère, d'un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="960a2-127">This example returns two characters, beginning with character 4, from a string literal.</span></span> <span data-ttu-id="960a2-128">Le résultat obtenu est « ph ».</span><span class="sxs-lookup"><span data-stu-id="960a2-128">The return result is "ph".</span></span>  
  
```  
SUBSTRING("elephant",4,2)  
```  
  
 <span data-ttu-id="960a2-129">L'exemple suivant renvoie le reste d'un littéral de chaîne, à partir du quatrième caractère.</span><span class="sxs-lookup"><span data-stu-id="960a2-129">This example returns the remainder of a string literal, beginning at the fourth character.</span></span> <span data-ttu-id="960a2-130">Le résultat obtenu est « phant ».</span><span class="sxs-lookup"><span data-stu-id="960a2-130">The return result is "phant".</span></span> <span data-ttu-id="960a2-131">Si l'argument *length* dépasse la longueur de la chaîne, cela ne constitue pas une erreur.</span><span class="sxs-lookup"><span data-stu-id="960a2-131">It is not an error for the *length* argument to exceed the length of the string.</span></span>  
  
```  
SUBSTRING ("elephant",4,50)  
```  
  
 <span data-ttu-id="960a2-132">L'exemple suivant renvoie la première lettre de la colonne **MiddleName** .</span><span class="sxs-lookup"><span data-stu-id="960a2-132">This example returns the first letter from the **MiddleName** column.</span></span>  
  
```  
SUBSTRING(MiddleName,1,1)  
```  
  
 <span data-ttu-id="960a2-133">L'exemple suivant utilise des variables dans les arguments *position* et *length* .</span><span class="sxs-lookup"><span data-stu-id="960a2-133">This example uses variables in the *position* and *length* arguments.</span></span> <span data-ttu-id="960a2-134">Si les variables **Start** et **Length** ont pour valeur respective 1 et 5, la fonction renvoie les cinq premiers caractères de la colonne **Name** .</span><span class="sxs-lookup"><span data-stu-id="960a2-134">If **Start** is 1 and **Length** is 5, the function returns the first five characters in the **Name** column.</span></span>  
  
```  
SUBSTRING(Name,@Start,@Length)  
```  
  
 <span data-ttu-id="960a2-135">L'exemple suivant renvoie les quatre derniers caractères de la variable **PostalCode** , à partir du sixième caractère.</span><span class="sxs-lookup"><span data-stu-id="960a2-135">This example returns the last four characters from the **PostalCode** variable beginning at the sixth character.</span></span>  
  
```  
SUBSTRING (@PostalCode,6,4)  
```  
  
 <span data-ttu-id="960a2-136">L'exemple suivant renvoie une chaîne de longueur nulle d'un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="960a2-136">This example returns a zero-length string from a string literal.</span></span>  
  
```  
SUBSTRING ("Redmond",4,0)  
```  
  
## <a name="see-also"></a><span data-ttu-id="960a2-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="960a2-137">See Also</span></span>  
 [<span data-ttu-id="960a2-138">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="960a2-138">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
