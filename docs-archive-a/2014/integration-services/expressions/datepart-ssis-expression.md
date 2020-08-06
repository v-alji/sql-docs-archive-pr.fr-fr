---
title: DATEPART (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEPART
- DATEPART function
ms.assetid: 3e590094-fc49-4144-805f-fdc1bf2fe509
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aed7146c74c6738ba979f422bd65b7e1b539e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700062"
---
# <a name="datepart-ssis-expression"></a><span data-ttu-id="f081b-102">DATEPART (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="f081b-102">DATEPART (SSIS Expression)</span></span>
  <span data-ttu-id="f081b-103">Renvoie un entier représentant une partie d'une date.</span><span class="sxs-lookup"><span data-stu-id="f081b-103">Returns an integer representing a datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f081b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f081b-104">Syntax</span></span>  
  
```  
  
DATEPART(datepart, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="f081b-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="f081b-105">Arguments</span></span>  
 <span data-ttu-id="f081b-106">*datepart*</span><span class="sxs-lookup"><span data-stu-id="f081b-106">*datepart*</span></span>  
 <span data-ttu-id="f081b-107">Paramètre qui indique la partie de date pour laquelle il faut retourner une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="f081b-107">Is the parameter that specifies for which part of the date to return a new value.</span></span>  
  
 <span data-ttu-id="f081b-108">*date*</span><span class="sxs-lookup"><span data-stu-id="f081b-108">*date*</span></span>  
 <span data-ttu-id="f081b-109">Expression renvoyant une date valide ou une chaîne dans un format de date.</span><span class="sxs-lookup"><span data-stu-id="f081b-109">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f081b-110">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="f081b-110">Result Types</span></span>  
 <span data-ttu-id="f081b-111">DT_I4</span><span class="sxs-lookup"><span data-stu-id="f081b-111">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f081b-112">Notes</span><span class="sxs-lookup"><span data-stu-id="f081b-112">Remarks</span></span>  
 <span data-ttu-id="f081b-113">La fonction DATEPART renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="f081b-113">DATEPART returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="f081b-114">Un littéral de date doit être explicitement converti dans l'un des types de données date.</span><span class="sxs-lookup"><span data-stu-id="f081b-114">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="f081b-115">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f081b-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="f081b-116">Le tableau suivant décrit les parties de date et les abréviations reconnues par l'évaluateur d'expression.</span><span class="sxs-lookup"><span data-stu-id="f081b-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="f081b-117">Les noms de partie de date ne respectent pas la casse.</span><span class="sxs-lookup"><span data-stu-id="f081b-117">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="f081b-118">partie de date</span><span class="sxs-lookup"><span data-stu-id="f081b-118">Datepart</span></span>|<span data-ttu-id="f081b-119">Abréviations</span><span class="sxs-lookup"><span data-stu-id="f081b-119">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="f081b-120">Year</span><span class="sxs-lookup"><span data-stu-id="f081b-120">Year</span></span>|<span data-ttu-id="f081b-121">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="f081b-121">yy, yyyy</span></span>|  
|<span data-ttu-id="f081b-122">Quarter</span><span class="sxs-lookup"><span data-stu-id="f081b-122">Quarter</span></span>|<span data-ttu-id="f081b-123">qq, q</span><span class="sxs-lookup"><span data-stu-id="f081b-123">qq, q</span></span>|  
|<span data-ttu-id="f081b-124">Month</span><span class="sxs-lookup"><span data-stu-id="f081b-124">Month</span></span>|<span data-ttu-id="f081b-125">mm, m</span><span class="sxs-lookup"><span data-stu-id="f081b-125">mm, m</span></span>|  
|<span data-ttu-id="f081b-126">Jour de l'année</span><span class="sxs-lookup"><span data-stu-id="f081b-126">Dayofyear</span></span>|<span data-ttu-id="f081b-127">dy, y</span><span class="sxs-lookup"><span data-stu-id="f081b-127">dy, y</span></span>|  
|<span data-ttu-id="f081b-128">jour</span><span class="sxs-lookup"><span data-stu-id="f081b-128">Day</span></span>|<span data-ttu-id="f081b-129">dd, d</span><span class="sxs-lookup"><span data-stu-id="f081b-129">dd, d</span></span>|  
|<span data-ttu-id="f081b-130">Week</span><span class="sxs-lookup"><span data-stu-id="f081b-130">Week</span></span>|<span data-ttu-id="f081b-131">wk, ww</span><span class="sxs-lookup"><span data-stu-id="f081b-131">wk, ww</span></span>|  
|<span data-ttu-id="f081b-132">Jour de la semaine</span><span class="sxs-lookup"><span data-stu-id="f081b-132">Weekday</span></span>|<span data-ttu-id="f081b-133">dw</span><span class="sxs-lookup"><span data-stu-id="f081b-133">dw</span></span>|  
|<span data-ttu-id="f081b-134">Heure</span><span class="sxs-lookup"><span data-stu-id="f081b-134">Hour</span></span>|<span data-ttu-id="f081b-135">Hh</span><span class="sxs-lookup"><span data-stu-id="f081b-135">Hh</span></span>|  
|<span data-ttu-id="f081b-136">Minute</span><span class="sxs-lookup"><span data-stu-id="f081b-136">Minute</span></span>|<span data-ttu-id="f081b-137">mi, n</span><span class="sxs-lookup"><span data-stu-id="f081b-137">mi, n</span></span>|  
|<span data-ttu-id="f081b-138">Seconde</span><span class="sxs-lookup"><span data-stu-id="f081b-138">Second</span></span>|<span data-ttu-id="f081b-139">ss, s</span><span class="sxs-lookup"><span data-stu-id="f081b-139">ss, s</span></span>|  
|<span data-ttu-id="f081b-140">Milliseconde</span><span class="sxs-lookup"><span data-stu-id="f081b-140">Millisecond</span></span>|<span data-ttu-id="f081b-141">Ms</span><span class="sxs-lookup"><span data-stu-id="f081b-141">Ms</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="f081b-142">Exemples d'expressions SSIS</span><span class="sxs-lookup"><span data-stu-id="f081b-142">SSIS Expression Examples</span></span>  
 <span data-ttu-id="f081b-143">L'exemple suivant renvoie l'entier qui représente le mois dans un littéral de date.</span><span class="sxs-lookup"><span data-stu-id="f081b-143">This example returns the integer that represents the month in a date literal.</span></span> <span data-ttu-id="f081b-144">Si le format de la date est « mm/jj/aaaa », l'exemple renvoie 11.</span><span class="sxs-lookup"><span data-stu-id="f081b-144">If the date is in mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
DATEPART("month", (DT_DBTIMESTAMP)"11/04/2002")  
```  
  
 <span data-ttu-id="f081b-145">L’exemple suivant retourne l’entier qui représente le jour dans la colonne **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="f081b-145">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DATEPART("dd", ModifiedDate)  
```  
  
 <span data-ttu-id="f081b-146">L'exemple suivant renvoie l'entier qui représente l'année de la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="f081b-146">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
DATEPART("yy",GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="f081b-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f081b-147">See Also</span></span>  
 <span data-ttu-id="f081b-148">[DATEADD &#40;expression SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f081b-148">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="f081b-149">[DATEDIFF &#40;expression SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f081b-149">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="f081b-150">[DAY &#40;expression SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f081b-150">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="f081b-151">[MONTH &#40;expression SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f081b-151">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="f081b-152">[YEAR &#40;expression SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="f081b-152">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="f081b-153">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f081b-153">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
