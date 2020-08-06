---
title: FINDSTRING (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FINDSTRING function
ms.assetid: c83cb1b1-3c52-4496-b518-4c9253b9336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72f2ff21cb179ce565e60c6550b8ecc2618a5adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604652"
---
# <a name="findstring-ssis-expression"></a><span data-ttu-id="6ab8d-102">FINDSTRING (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="6ab8d-102">FINDSTRING (SSIS Expression)</span></span>
  <span data-ttu-id="6ab8d-103">Renvoie l'emplacement de l'occurrence spécifiée d'une chaîne dans une expression de caractères.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-103">Returns the location of the specified occurrence of a string within a character expression.</span></span> <span data-ttu-id="6ab8d-104">Le résultat obtenu est l'index de base un de l'occurrence.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-104">The return result is the one-based index of the occurrence.</span></span> <span data-ttu-id="6ab8d-105">Le paramètre de chaîne doit s'évaluer à une expression de caractères et le paramètre de l'occurrence doit s'évaluer à un entier.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-105">The string parameter must evaluate to a character expression, and the occurrence parameter must evaluate to an integer.</span></span> <span data-ttu-id="6ab8d-106">Si la chaîne est introuvable, la valeur retournée est 0.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-106">If the string is not found, the return value is 0.</span></span> <span data-ttu-id="6ab8d-107">Si la chaîne se produit moins souvent que l'argument de l'occurrence ne le spécifie, la valeur retournée est 0.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-107">If the string occurs fewer times than the occurrence argument specifies, the return value is 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ab8d-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6ab8d-108">Syntax</span></span>  
  
```  
  
FINDSTRING(character_expression, searchstring, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ab8d-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="6ab8d-109">Arguments</span></span>  
 <span data-ttu-id="6ab8d-110">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="6ab8d-110">*character_expression*</span></span>  
 <span data-ttu-id="6ab8d-111">Chaîne de caractères dans laquelle la recherche doit être effectuée.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-111">Is the character string to search in.</span></span>  
  
 <span data-ttu-id="6ab8d-112">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="6ab8d-112">*searchstring*</span></span>  
 <span data-ttu-id="6ab8d-113">Chaîne de caractères à rechercher.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-113">Is the character string to search for.</span></span>  
  
 <span data-ttu-id="6ab8d-114">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="6ab8d-114">*occurrence*</span></span>  
 <span data-ttu-id="6ab8d-115">Entier signé ou non signé spécifiant l’occurrence de *searchstring* à signaler.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-115">Is a signed or unsigned integer specifying which occurrence of *searchstring* to report.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6ab8d-116">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="6ab8d-116">Result Types</span></span>  
 <span data-ttu-id="6ab8d-117">DT_I4</span><span class="sxs-lookup"><span data-stu-id="6ab8d-117">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ab8d-118">Notes</span><span class="sxs-lookup"><span data-stu-id="6ab8d-118">Remarks</span></span>  
 <span data-ttu-id="6ab8d-119">La fonction FINDSTRING n'est opérationnelle qu'avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-119">FINDSTRING works only with the DT_WSTR data type.</span></span>  <span data-ttu-id="6ab8d-120">Les arguments*character_expression* et *searchstring* qui représentent des littéraux de chaîne ou des colonnes de données du type de données DT_STR sont implicitement convertis dans le type de données DT_WSTR avant que la fonction FINDSTRING soit exécutée.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-120">*character_expression* and *searchstring* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before FINDSTRING performs its operation.</span></span> <span data-ttu-id="6ab8d-121">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-121">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="6ab8d-122">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="6ab8d-122">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="6ab8d-123">FINDSTRING retourne NULL si *character_expression* ou *searchstring* a la valeur Null.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-123">FINDSTRING returns null if either *character_expression* or *searchstring* are null.</span></span>  
  
 <span data-ttu-id="6ab8d-124">Utilisez la valeur 1 dans l'argument *occurrence* pour obtenir l'index de la première occurrence, la valeur 2 pour obtenir celui de la deuxième occurrence, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-124">Use a value of 1 in the *occurrence* argument to get the index of the first occurrence, 2 for the second occurrence and so forth.</span></span>  
  
 <span data-ttu-id="6ab8d-125">L'argument *occurrence* doit être un entier supérieur à 0.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-125">The *occurrence* must be an integer with a value greater than 0.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="6ab8d-126">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="6ab8d-126">Expression Examples</span></span>  
 <span data-ttu-id="6ab8d-127">L'exemple suivant utilise un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-127">This example uses a string literal.</span></span> <span data-ttu-id="6ab8d-128">Il renvoie la valeur 11.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-128">It returns the value 11.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 1)   
```  
  
 <span data-ttu-id="6ab8d-129">L'exemple suivant utilise un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-129">This example uses a string literal.</span></span> <span data-ttu-id="6ab8d-130">La chaîne « NY » ne se produisant que deux fois, le résultat retourné est 0.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-130">Because the string "NY" occurs only two times, the return result is 0.</span></span>  
  
```  
FINDSTRING("New York, NY, NY", "NY", 3)   
```  
  
 <span data-ttu-id="6ab8d-131">L'exemple suivant utilise la colonne **Name** .</span><span class="sxs-lookup"><span data-stu-id="6ab8d-131">This example uses the **Name** column.</span></span> <span data-ttu-id="6ab8d-132">Il renvoie l'emplacement de la valeur « n » dans la colonne **Name** .</span><span class="sxs-lookup"><span data-stu-id="6ab8d-132">It returns the location of the value n in the **Name** column.</span></span> <span data-ttu-id="6ab8d-133">Le résultat obtenu varie en fonction de la valeur de la colonne **Name**.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-133">The return result varies depending on the value in **Name**.</span></span> <span data-ttu-id="6ab8d-134">Si **Name** contient Anderson, la fonction retourne 8.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-134">If **Name** contains Anderson, the function returns 8.</span></span>  
  
```  
FINDSTRING(Name,"n", 2)   
```  
  
 <span data-ttu-id="6ab8d-135">L'exemple suivant utilise les colonnes **Name** et **Size** .</span><span class="sxs-lookup"><span data-stu-id="6ab8d-135">This example uses the **Name** and **Size** columns.</span></span> <span data-ttu-id="6ab8d-136">Il renvoie l'emplacement du caractère situé à l'extrême gauche de la valeur **Size** de la colonne **Name** .</span><span class="sxs-lookup"><span data-stu-id="6ab8d-136">It returns the location of the leftmost character of the **Size** value in the **Name** column.</span></span> <span data-ttu-id="6ab8d-137">Le résultat obtenu dépend des valeurs de la colonne.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-137">The return result varies depending on column values.</span></span> <span data-ttu-id="6ab8d-138">Si la colonne **Name** contient « Mountain,500Red,42 » et que la colonne **Size** contient « 42 », le résultat obtenu est 17.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-138">If **Name** contains Mountain,500Red,42 and **Size** contains 42, the return result is 17.</span></span>  
  
```  
FINDSTRING(Name,Size,1)   
```  
  
## <a name="see-also"></a><span data-ttu-id="6ab8d-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ab8d-139">See Also</span></span>  
 <span data-ttu-id="6ab8d-140">[REPLACE &#40;expression SSIS&#41;](replace-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="6ab8d-140">[REPLACE &#40;SSIS Expression&#41;](replace-ssis-expression.md) </span></span>  
 [<span data-ttu-id="6ab8d-141">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="6ab8d-141">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
