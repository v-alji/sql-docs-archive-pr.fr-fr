---
title: NULL (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- NULL function
- null values [Integration Services]
ms.assetid: df144237-3fbb-41ac-8624-efd92b6522b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14cd51b4e245ca6984a4c62eae2b9d5536ab1f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601008"
---
# <a name="null-ssis-expression"></a><span data-ttu-id="5c46d-102">NULL (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="5c46d-102">NULL (SSIS Expression)</span></span>
  <span data-ttu-id="5c46d-103">Renvoie une valeur NULL d'un type de données demandé.</span><span class="sxs-lookup"><span data-stu-id="5c46d-103">Returns a null value of a requested data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c46d-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5c46d-104">Syntax</span></span>  
  
```  
  
NULL(typespec)  
```  
  
## <a name="arguments"></a><span data-ttu-id="5c46d-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="5c46d-105">Arguments</span></span>  
 <span data-ttu-id="5c46d-106">*typespec*</span><span class="sxs-lookup"><span data-stu-id="5c46d-106">*typespec*</span></span>  
 <span data-ttu-id="5c46d-107">Type de données valide.</span><span class="sxs-lookup"><span data-stu-id="5c46d-107">Is a valid data type.</span></span> <span data-ttu-id="5c46d-108">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5c46d-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5c46d-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="5c46d-109">Result Types</span></span>  
 <span data-ttu-id="5c46d-110">Tout type de données valide avec une valeur Null.</span><span class="sxs-lookup"><span data-stu-id="5c46d-110">Any valid data type with a null value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c46d-111">Notes</span><span class="sxs-lookup"><span data-stu-id="5c46d-111">Remarks</span></span>  
 <span data-ttu-id="5c46d-112">La fonction NULL renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="5c46d-112">NULL returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="5c46d-113">Des paramètres sont nécessaires pour demander une valeur NULL pour certains types de données.</span><span class="sxs-lookup"><span data-stu-id="5c46d-113">Parameters are required to request a null value for some data types.</span></span> <span data-ttu-id="5c46d-114">Le tableau suivant décrit ces types de données et leurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="5c46d-114">The following table lists these data types and their parameters.</span></span>  
  
|<span data-ttu-id="5c46d-115">Type de données</span><span class="sxs-lookup"><span data-stu-id="5c46d-115">Data type</span></span>|<span data-ttu-id="5c46d-116">Paramètre</span><span class="sxs-lookup"><span data-stu-id="5c46d-116">Parameter</span></span>|<span data-ttu-id="5c46d-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="5c46d-117">Example</span></span>|  
|---------------|---------------|-------------|  
|<span data-ttu-id="5c46d-118">DT_STR</span><span class="sxs-lookup"><span data-stu-id="5c46d-118">DT_STR</span></span>|<span data-ttu-id="5c46d-119">*charcount*</span><span class="sxs-lookup"><span data-stu-id="5c46d-119">*charcount*</span></span><br /><br /> <span data-ttu-id="5c46d-120">*codepage*</span><span class="sxs-lookup"><span data-stu-id="5c46d-120">*codepage*</span></span>|<span data-ttu-id="5c46d-121">L'expression (DT_STR,30,1252) convertit 30 caractères vers le type de données DT_STR à l'aide de la page de codes 1252.</span><span class="sxs-lookup"><span data-stu-id="5c46d-121">(DT_STR,30,1252) casts 30 characters to the DT_STR data type using the 1252 code page.</span></span>|  
|<span data-ttu-id="5c46d-122">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="5c46d-122">DT_WSTR</span></span>|<span data-ttu-id="5c46d-123">*charcount*</span><span class="sxs-lookup"><span data-stu-id="5c46d-123">*charcount*</span></span>|<span data-ttu-id="5c46d-124">L'expression (DT_WSTR,20) convertit 20 caractères vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="5c46d-124">(DT_WSTR,20) casts 20 characters to the DT_WSTR data type.</span></span>|  
|<span data-ttu-id="5c46d-125">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="5c46d-125">DT_BYTES</span></span>|<span data-ttu-id="5c46d-126">*bytecount*</span><span class="sxs-lookup"><span data-stu-id="5c46d-126">*bytecount*</span></span>|<span data-ttu-id="5c46d-127">L'expression (DT_BYTES,50) convertit 50 octets vers le type de données DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="5c46d-127">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|  
|<span data-ttu-id="5c46d-128">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="5c46d-128">DT_DECIMAL</span></span>|<span data-ttu-id="5c46d-129">*scale*</span><span class="sxs-lookup"><span data-stu-id="5c46d-129">*scale*</span></span>|<span data-ttu-id="5c46d-130">L'expression (DT_DECIMAL,2) convertit une valeur numérique dans le type de données DT_DECIMAL avec une échelle égale à 2.</span><span class="sxs-lookup"><span data-stu-id="5c46d-130">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|  
|<span data-ttu-id="5c46d-131">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="5c46d-131">DT_NUMERIC</span></span>|<span data-ttu-id="5c46d-132">*precision*</span><span class="sxs-lookup"><span data-stu-id="5c46d-132">*precision*</span></span><br /><br /> <span data-ttu-id="5c46d-133">*scale*</span><span class="sxs-lookup"><span data-stu-id="5c46d-133">*scale*</span></span>|<span data-ttu-id="5c46d-134">L'expression (DT_NUMERIC,10,3) convertit une valeur numérique dans le type de données DT_NUMERIC avec une précision de 10 et une échelle de 3.</span><span class="sxs-lookup"><span data-stu-id="5c46d-134">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|  
|<span data-ttu-id="5c46d-135">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="5c46d-135">DT_TEXT</span></span>|<span data-ttu-id="5c46d-136">*codepage*</span><span class="sxs-lookup"><span data-stu-id="5c46d-136">*codepage*</span></span>|<span data-ttu-id="5c46d-137">L'expression (DT_TEXT,1252) convertit une valeur vers le type de données DT_TEXT à l'aide de la page de codes 1252.</span><span class="sxs-lookup"><span data-stu-id="5c46d-137">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="5c46d-138">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="5c46d-138">Expression Examples</span></span>  
 <span data-ttu-id="5c46d-139">Les exemples ci-après renvoient la valeur Null des types de données suivants : DT_STR, DT_DATE et DT_BOOL.</span><span class="sxs-lookup"><span data-stu-id="5c46d-139">These examples return the null value of the data types: DT_STR, DT_DATE, and DT_BOOL.</span></span>  
  
```  
NULL(DT_STR,10,1252)  
NULL(DT_DATE)  
NULL(DT_BOOL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c46d-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c46d-140">See Also</span></span>  
 <span data-ttu-id="5c46d-141">[ISNULL &#40;expression SSIS&#41;](null-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5c46d-141">[ISNULL &#40;SSIS Expression&#41;](null-ssis-expression.md) </span></span>  
 [<span data-ttu-id="5c46d-142">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5c46d-142">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
