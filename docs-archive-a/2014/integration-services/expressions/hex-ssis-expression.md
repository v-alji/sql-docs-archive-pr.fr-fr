---
title: HEX (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- hexadecimal data
- HEX function
ms.assetid: f5d471ee-aeef-421c-b6e1-55b9676c3842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 640ae38ec5d2cd5ffb448e9aebde5ba5ceba2684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705331"
---
# <a name="hex-ssis-expression"></a><span data-ttu-id="52353-102">HEX (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="52353-102">HEX (SSIS Expression)</span></span>
  <span data-ttu-id="52353-103">Renvoie une chaîne représentant la valeur hexadécimale d'un entier.</span><span class="sxs-lookup"><span data-stu-id="52353-103">Returns a string representing the hexadecimal value of an integer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52353-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="52353-104">Syntax</span></span>  
  
```  
  
HEX(integer_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="52353-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="52353-105">Arguments</span></span>  
 <span data-ttu-id="52353-106">*integer_expression*</span><span class="sxs-lookup"><span data-stu-id="52353-106">*integer_expression*</span></span>  
 <span data-ttu-id="52353-107">Entier signé ou non signé.</span><span class="sxs-lookup"><span data-stu-id="52353-107">Is a signed or unsigned integer.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="52353-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="52353-108">Result Types</span></span>  
 <span data-ttu-id="52353-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="52353-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52353-110">Notes</span><span class="sxs-lookup"><span data-stu-id="52353-110">Remarks</span></span>  
 <span data-ttu-id="52353-111">HEX retourne null si *integer_expression* est null.</span><span class="sxs-lookup"><span data-stu-id="52353-111">HEX returns null if *integer_expression* is null.</span></span>  
  
 <span data-ttu-id="52353-112">L’argument *integer_expression* doit correspondre à un nombre entier.</span><span class="sxs-lookup"><span data-stu-id="52353-112">The *integer_expression* argument must evaluate to an integer.</span></span> <span data-ttu-id="52353-113">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="52353-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="52353-114">Le résultat obtenu ne comprend pas de qualificateurs tels que le préfixe « 0x ».</span><span class="sxs-lookup"><span data-stu-id="52353-114">The return result does not include qualifiers such as the 0x prefix.</span></span> <span data-ttu-id="52353-115">Pour inclure un préfixe, utilisez l'opérateur « + » (concaténer).</span><span class="sxs-lookup"><span data-stu-id="52353-115">To include a prefix, use the + (Concatenate) operator.</span></span> <span data-ttu-id="52353-116">Pour plus d’informations, consultez [+ &#40;Concaténer&#41; &#40;expression SSIS&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="52353-116">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="52353-117">Les lettres « A » à « F », utilisées en notation hexadécimale, apparaissent en caractères majuscules.</span><span class="sxs-lookup"><span data-stu-id="52353-117">The letters A - F, used in HEX notations, appear as uppercase characters.</span></span>  
  
 <span data-ttu-id="52353-118">La longueur de la chaîne obtenue pour les types de données entiers est la suivante :</span><span class="sxs-lookup"><span data-stu-id="52353-118">The length of the resulting string for integer data types is as follows:</span></span>  
  
-   <span data-ttu-id="52353-119">Les types de données DT_I1 et DT_UI1 renvoient une chaîne d'une longueur maximale de 2.</span><span class="sxs-lookup"><span data-stu-id="52353-119">DT_I1 and DT_UI1 return a string with a maximum length of 2.</span></span>  
  
-   <span data-ttu-id="52353-120">Les types de données DT_I2 et DT_UI2 renvoient une chaîne d'une longueur maximale de 4.</span><span class="sxs-lookup"><span data-stu-id="52353-120">DT_I2 and DT_UI2 return a string with a maximum length of 4.</span></span>  
  
-   <span data-ttu-id="52353-121">Les types de données DT_I4 et DT_UI4 renvoient une chaîne d'une longueur maximale de 8.</span><span class="sxs-lookup"><span data-stu-id="52353-121">DT_I4 and DT_UI4 return a string with a maximum length of 8.</span></span>  
  
-   <span data-ttu-id="52353-122">Les types de données DT_I8 et DT_UI8 renvoient une chaîne d'une longueur maximale de 16.</span><span class="sxs-lookup"><span data-stu-id="52353-122">DT_I8 and DT_UI8 return a string with a maximum length of 16.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="52353-123">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="52353-123">Expression Examples</span></span>  
 <span data-ttu-id="52353-124">L'exemple suivant utilise un littéral numérique.</span><span class="sxs-lookup"><span data-stu-id="52353-124">This example uses a numeric literal.</span></span> <span data-ttu-id="52353-125">La fonction retourne la valeur 190.</span><span class="sxs-lookup"><span data-stu-id="52353-125">The function returns the value 190.</span></span>  
  
```  
HEX(400)   
```  
  
 <span data-ttu-id="52353-126">L’exemple suivant utilise la colonne **ReorderPoint** .</span><span class="sxs-lookup"><span data-stu-id="52353-126">This example uses the **ReorderPoint** column.</span></span> <span data-ttu-id="52353-127">Le type de données de la colonne est `smallint`.</span><span class="sxs-lookup"><span data-stu-id="52353-127">The column data type is `smallint`.</span></span> <span data-ttu-id="52353-128">Si la variable **ReorderPoint** a pour valeur 750, la fonction renvoie 2EE.</span><span class="sxs-lookup"><span data-stu-id="52353-128">If **ReorderPoint** is 750, the function returns 2EE.</span></span>  
  
```  
HEX(ReorderPoint)   
```  
  
 <span data-ttu-id="52353-129">L’exemple suivant utilise la variable système **LocaleID**.</span><span class="sxs-lookup"><span data-stu-id="52353-129">This example uses **LocaleID**, a system variable.</span></span> <span data-ttu-id="52353-130">Si la variable **LocaleID** a pour valeur 1033, la fonction renvoie 409.</span><span class="sxs-lookup"><span data-stu-id="52353-130">If **LocaleID** is 1033, the function returns 409.</span></span>  
  
```  
HEX(@LocaleID)  
```  
  
## <a name="see-also"></a><span data-ttu-id="52353-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52353-131">See Also</span></span>  
 [<span data-ttu-id="52353-132">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="52353-132">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
