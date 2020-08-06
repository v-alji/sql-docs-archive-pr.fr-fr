---
title: DATEDIFF (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DATEDIFF statement
- dates [Integration Services], DATEDIFF
ms.assetid: 449b327f-47c7-4709-8bc6-4ee9a35cc330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33edf2a152f70bb8c5bbd1f69cb87354e099b246
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700068"
---
# <a name="datediff-ssis-expression"></a><span data-ttu-id="1b775-102">DATEDIFF (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="1b775-102">DATEDIFF (SSIS Expression)</span></span>
  <span data-ttu-id="1b775-103">Renvoie le nombre de limites de date et d'heure traversées entre deux dates données.</span><span class="sxs-lookup"><span data-stu-id="1b775-103">Returns the number of date and time boundaries crossed between two specified dates.</span></span> <span data-ttu-id="1b775-104">Le paramètre *datepart* identifie quelles limites de date et d’heure il faut comparer.</span><span class="sxs-lookup"><span data-stu-id="1b775-104">The *datepart* parameter identifies which date and time boundaries to compare.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b775-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1b775-105">Syntax</span></span>  
  
```  
  
DATEDIFF(datepart, startdate, endate)  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b775-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="1b775-106">Arguments</span></span>  
 <span data-ttu-id="1b775-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="1b775-107">*datepart*</span></span>  
 <span data-ttu-id="1b775-108">Paramètre qui indique la partie de la date à comparer et pour laquelle une valeur doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="1b775-108">Is the parameter that specifies which part of the date to compare and return a value for.</span></span>  
  
 <span data-ttu-id="1b775-109">*startdate*</span><span class="sxs-lookup"><span data-stu-id="1b775-109">*startdate*</span></span>  
 <span data-ttu-id="1b775-110">Date de début de l'intervalle.</span><span class="sxs-lookup"><span data-stu-id="1b775-110">Is the start date of the interval.</span></span>  
  
 <span data-ttu-id="1b775-111">*endate*</span><span class="sxs-lookup"><span data-stu-id="1b775-111">*endate*</span></span>  
 <span data-ttu-id="1b775-112">Date de fin de l'intervalle.</span><span class="sxs-lookup"><span data-stu-id="1b775-112">Is the end date of the interval.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1b775-113">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="1b775-113">Result Types</span></span>  
 <span data-ttu-id="1b775-114">DT_I4</span><span class="sxs-lookup"><span data-stu-id="1b775-114">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b775-115">Notes</span><span class="sxs-lookup"><span data-stu-id="1b775-115">Remarks</span></span>  
 <span data-ttu-id="1b775-116">Le tableau suivant décrit les parties de date et les abréviations reconnues par l'évaluateur d'expression.</span><span class="sxs-lookup"><span data-stu-id="1b775-116">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span>  
  
|<span data-ttu-id="1b775-117">partie de date</span><span class="sxs-lookup"><span data-stu-id="1b775-117">Datepart</span></span>|<span data-ttu-id="1b775-118">Abréviations</span><span class="sxs-lookup"><span data-stu-id="1b775-118">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="1b775-119">Year</span><span class="sxs-lookup"><span data-stu-id="1b775-119">Year</span></span>|<span data-ttu-id="1b775-120">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="1b775-120">yy, yyyy</span></span>|  
|<span data-ttu-id="1b775-121">Quarter</span><span class="sxs-lookup"><span data-stu-id="1b775-121">Quarter</span></span>|<span data-ttu-id="1b775-122">qq, q</span><span class="sxs-lookup"><span data-stu-id="1b775-122">qq, q</span></span>|  
|<span data-ttu-id="1b775-123">Month</span><span class="sxs-lookup"><span data-stu-id="1b775-123">Month</span></span>|<span data-ttu-id="1b775-124">mm, m</span><span class="sxs-lookup"><span data-stu-id="1b775-124">mm, m</span></span>|  
|<span data-ttu-id="1b775-125">Jour de l'année</span><span class="sxs-lookup"><span data-stu-id="1b775-125">Dayofyear</span></span>|<span data-ttu-id="1b775-126">dy, y</span><span class="sxs-lookup"><span data-stu-id="1b775-126">dy, y</span></span>|  
|<span data-ttu-id="1b775-127">jour</span><span class="sxs-lookup"><span data-stu-id="1b775-127">Day</span></span>|<span data-ttu-id="1b775-128">dd, d</span><span class="sxs-lookup"><span data-stu-id="1b775-128">dd, d</span></span>|  
|<span data-ttu-id="1b775-129">Week</span><span class="sxs-lookup"><span data-stu-id="1b775-129">Week</span></span>|<span data-ttu-id="1b775-130">wk, ww</span><span class="sxs-lookup"><span data-stu-id="1b775-130">wk, ww</span></span>|  
|<span data-ttu-id="1b775-131">Jour de la semaine</span><span class="sxs-lookup"><span data-stu-id="1b775-131">Weekday</span></span>|<span data-ttu-id="1b775-132">dw, w</span><span class="sxs-lookup"><span data-stu-id="1b775-132">dw, w</span></span>|  
|<span data-ttu-id="1b775-133">Heure</span><span class="sxs-lookup"><span data-stu-id="1b775-133">Hour</span></span>|<span data-ttu-id="1b775-134">Hh</span><span class="sxs-lookup"><span data-stu-id="1b775-134">Hh</span></span>|  
|<span data-ttu-id="1b775-135">Minute</span><span class="sxs-lookup"><span data-stu-id="1b775-135">Minute</span></span>|<span data-ttu-id="1b775-136">mi, n</span><span class="sxs-lookup"><span data-stu-id="1b775-136">mi, n</span></span>|  
|<span data-ttu-id="1b775-137">Seconde</span><span class="sxs-lookup"><span data-stu-id="1b775-137">Second</span></span>|<span data-ttu-id="1b775-138">ss, s</span><span class="sxs-lookup"><span data-stu-id="1b775-138">ss, s</span></span>|  
|<span data-ttu-id="1b775-139">Milliseconde</span><span class="sxs-lookup"><span data-stu-id="1b775-139">Millisecond</span></span>|<span data-ttu-id="1b775-140">Ms</span><span class="sxs-lookup"><span data-stu-id="1b775-140">Ms</span></span>|  
  
 <span data-ttu-id="1b775-141">La fonction DATEDIFF renvoie un résultat NULL si un argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="1b775-141">DATEDIFF returns a null result if any argument is null.</span></span>  
  
 <span data-ttu-id="1b775-142">Un littéral de date doit être explicitement converti dans l'un des types de données date.</span><span class="sxs-lookup"><span data-stu-id="1b775-142">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="1b775-143">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1b775-143">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="1b775-144">Une erreur se produit dans les cas suivants : une date n'est pas valide, l'unité de date ou d'heure n'est pas une chaîne, la date de début n'est pas une date ou la date de fin n'est pas une date.</span><span class="sxs-lookup"><span data-stu-id="1b775-144">An error occurs if a date is not valid, if the date or time unit is not a string, if the start date is not a date, or if the end date is not a date.</span></span>  
  
 <span data-ttu-id="1b775-145">Si la date de fin est antérieure à la date de début, la fonction renvoie un nombre négatif.</span><span class="sxs-lookup"><span data-stu-id="1b775-145">If the end date is earlier than the start date, the function returns a negative number.</span></span> <span data-ttu-id="1b775-146">Si les dates de début et de fin sont identiques ou qu'elles appartiennent au même intervalle, la fonction renvoie zéro.</span><span class="sxs-lookup"><span data-stu-id="1b775-146">If the start and end dates are equal or fall within the same interval, the function returns zero.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="1b775-147">Exemples d'expressions SSIS</span><span class="sxs-lookup"><span data-stu-id="1b775-147">SSIS Expression Examples</span></span>  
 <span data-ttu-id="1b775-148">L'exemple suivant calcule le nombre de jours entre deux littéraux de date.</span><span class="sxs-lookup"><span data-stu-id="1b775-148">This example calculates the number of days between two date literals.</span></span> <span data-ttu-id="1b775-149">Si le format de la date est « mm/jj/aaaa », la fonction renvoie 7.</span><span class="sxs-lookup"><span data-stu-id="1b775-149">If the date is in "mm/dd/yyyy" format, the function returns 7.</span></span>  
  
```  
DATEDIFF("dd", (DT_DBTIMESTAMP)"8/1/2003", (DT_DBTIMESTAMP)"8/8/2003")  
```  
  
 <span data-ttu-id="1b775-150">L'exemple suivant renvoie le nombre de mois entre un littéral de date et la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="1b775-150">This example returns the number of months between a date literal and the current date.</span></span>  
  
```  
DATEDIFF("mm", (DT_DBTIMESTAMP)"8/1/2003",GETDATE())  
```  
  
 <span data-ttu-id="1b775-151">L’exemple suivant retourne le nombre de semaines entre la date de la colonne **ModifiedDate** et la variable **YearEndDate** .</span><span class="sxs-lookup"><span data-stu-id="1b775-151">This example returns the number of weeks between the date in the **ModifiedDate** column and the **YearEndDate** variable.</span></span> <span data-ttu-id="1b775-152">Si **YearEndDate** a un `date` type de données, aucun cast explicite n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1b775-152">If **YearEndDate** has a `date` data type, no explicit casting is required.</span></span>  
  
```  
DATEDIFF("Week", ModifiedDate,@YearEndDate)  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b775-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b775-153">See Also</span></span>  
 <span data-ttu-id="1b775-154">[DATEADD &#40;expression SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1b775-154">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="1b775-155">[DATEPART &#40;expression SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1b775-155">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="1b775-156">[DAY &#40;expression SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1b775-156">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="1b775-157">[MONTH &#40;expression SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1b775-157">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="1b775-158">[YEAR &#40;expression SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1b775-158">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="1b775-159">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1b775-159">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
