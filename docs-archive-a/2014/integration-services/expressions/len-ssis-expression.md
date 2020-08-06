---
title: LEN (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- LEN function
- number of characters
ms.assetid: d961398b-e4d0-4936-be17-8f4c5882a640
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8863864168295a3a9a924df588312ee65b6f7fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604047"
---
# <a name="len-ssis-expression"></a><span data-ttu-id="65a7b-102">LEN (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="65a7b-102">LEN (SSIS Expression)</span></span>
  <span data-ttu-id="65a7b-103">Renvoie le nombre de caractères d'une expression de caractères.</span><span class="sxs-lookup"><span data-stu-id="65a7b-103">Returns the number of characters in a character expression.</span></span> <span data-ttu-id="65a7b-104">Si la chaîne comprend des espaces de début et de fin, la fonction les inclut dans le nombre.</span><span class="sxs-lookup"><span data-stu-id="65a7b-104">If the string includes leading and trailing blanks, the function includes them in the count.</span></span> <span data-ttu-id="65a7b-105">La fonction LEN renvoie la même valeur pour une chaîne donnée, que celle-ci soit composée de caractères codés sur un octet ou sur deux octets.</span><span class="sxs-lookup"><span data-stu-id="65a7b-105">LEN returns identical values for the same string of single and double byte characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a7b-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="65a7b-106">Syntax</span></span>  
  
```  
  
LEN(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="65a7b-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="65a7b-107">Arguments</span></span>  
 <span data-ttu-id="65a7b-108">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="65a7b-108">*character_expression*</span></span>  
 <span data-ttu-id="65a7b-109">Expression à évaluer.</span><span class="sxs-lookup"><span data-stu-id="65a7b-109">Is the expression to evaluate.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="65a7b-110">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="65a7b-110">Result Types</span></span>  
 <span data-ttu-id="65a7b-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="65a7b-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65a7b-112">Notes</span><span class="sxs-lookup"><span data-stu-id="65a7b-112">Remarks</span></span>  
 <span data-ttu-id="65a7b-113">L’argument *character_expression* peut être d’un type de données DT_WSTR, DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="65a7b-113">The *character_expression* argument can be a DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type.</span></span> <span data-ttu-id="65a7b-114">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="65a7b-114">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="65a7b-115">Si *character_expression* est un littéral de chaîne ou une colonne de données avec le type de données DT_STR, il est implicitement converti dans le type de données DT_WSTR avant que la fonction LEN soit exécutée.</span><span class="sxs-lookup"><span data-stu-id="65a7b-115">If *character_expression* is a string literal or a data column with the DT_STR data type, it is implicitly cast to the DT_WSTR data type before LEN performs its operation.</span></span> <span data-ttu-id="65a7b-116">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="65a7b-116">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="65a7b-117">Pour plus d’informations, consultez [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="65a7b-117">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="65a7b-118">Si l'argument transmis à la fonction LEN a un type de données BLOB (Binary Large Object Block), tel que DT_TEXT, DT_NTEXT ou DT_IMAGE, la fonction renvoie un nombre d'octets.</span><span class="sxs-lookup"><span data-stu-id="65a7b-118">If the argument passed to the LEN function has a Binary Large Object Block (BLOB) data type, such as DT_TEXT, DT_NTEXT, or DT_IMAGE, the function returns a byte count.</span></span>  
  
 <span data-ttu-id="65a7b-119">La fonction LEN renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="65a7b-119">LEN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="65a7b-120">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="65a7b-120">Expression Examples</span></span>  
 <span data-ttu-id="65a7b-121">Cet exemple renvoie la longueur d'un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="65a7b-121">This example returns the length of a string literal.</span></span> <span data-ttu-id="65a7b-122">Le résultat obtenu est 12.</span><span class="sxs-lookup"><span data-stu-id="65a7b-122">The return result is 12.</span></span>  
  
```  
LEN("Ball Bearing")  
```  
  
 <span data-ttu-id="65a7b-123">L'exemple suivant renvoie la différence de longueur des valeurs des colonnes **FirstName** et **LastName** .</span><span class="sxs-lookup"><span data-stu-id="65a7b-123">This example returns the difference between the length of values in the **FirstName** and **LastName** columns.</span></span>  
  
```  
LEN(FirstName) - LEN(LastName)  
```  
  
 <span data-ttu-id="65a7b-124">Renvoie la longueur d'un nom d'ordinateur à partir de la variable système **MachineName**.</span><span class="sxs-lookup"><span data-stu-id="65a7b-124">Returns the length of a computer name using the System variable **MachineName**.</span></span>  
  
```  
LEN(@MachineName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="65a7b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65a7b-125">See Also</span></span>  
 [<span data-ttu-id="65a7b-126">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="65a7b-126">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
