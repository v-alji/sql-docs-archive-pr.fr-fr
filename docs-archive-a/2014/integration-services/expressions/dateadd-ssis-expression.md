---
title: DATEADD (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEADD
- dates [Integration Services]
- DATEADD function
ms.assetid: fa5c37b1-2ddc-4857-8f8e-f6d5643b654f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9feb288318bdf9705928cb930f175f5c170c384e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705335"
---
# <a name="dateadd-ssis-expression"></a><span data-ttu-id="7f958-102">DATEADD (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="7f958-102">DATEADD (SSIS Expression)</span></span>
  <span data-ttu-id="7f958-103">Renvoie une nouvelle valeur DT_DBTIMESTAMP après l'ajout d'un nombre qui représente un intervalle de date ou d'heure à la partie de date spécifiée d'une date.</span><span class="sxs-lookup"><span data-stu-id="7f958-103">Returns a new DT_DBTIMESTAMP value after adding a number that represents a date or time interval to the specified datepart in a date.</span></span> <span data-ttu-id="7f958-104">Le paramètre numérique doit s'évaluer à un entier et le paramètre de date doit s'évaluer à une date valide.</span><span class="sxs-lookup"><span data-stu-id="7f958-104">The number parameter must evaluate to an integer, and the date parameter must evaluate to a valid date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f958-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7f958-105">Syntax</span></span>  
  
```  
  
DATEADD(datepart, number, date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7f958-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="7f958-106">Arguments</span></span>  
 <span data-ttu-id="7f958-107">*datepart*</span><span class="sxs-lookup"><span data-stu-id="7f958-107">*datepart*</span></span>  
 <span data-ttu-id="7f958-108">Paramètre spécifiant la partie de la date à laquelle ajouter un nombre.</span><span class="sxs-lookup"><span data-stu-id="7f958-108">Is the parameter that specifies which part of the date to add a number to.</span></span>  
  
 <span data-ttu-id="7f958-109">*number*</span><span class="sxs-lookup"><span data-stu-id="7f958-109">*number*</span></span>  
 <span data-ttu-id="7f958-110">Valeur utilisée pour incrémenter *datepart*.</span><span class="sxs-lookup"><span data-stu-id="7f958-110">Is the value used to increment *datepart*.</span></span> <span data-ttu-id="7f958-111">La valeur doit être une valeur entière connue au moment de l'analyse de l'expression.</span><span class="sxs-lookup"><span data-stu-id="7f958-111">The value must be an integer value that is known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="7f958-112">*date*</span><span class="sxs-lookup"><span data-stu-id="7f958-112">*date*</span></span>  
 <span data-ttu-id="7f958-113">Expression renvoyant une date valide ou une chaîne dans un format de date.</span><span class="sxs-lookup"><span data-stu-id="7f958-113">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7f958-114">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="7f958-114">Result Types</span></span>  
 <span data-ttu-id="7f958-115">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="7f958-115">DT_DBTIMESTAMP</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f958-116">Notes</span><span class="sxs-lookup"><span data-stu-id="7f958-116">Remarks</span></span>  
 <span data-ttu-id="7f958-117">Le tableau suivant décrit les parties de date et les abréviations reconnues par l'évaluateur d'expression.</span><span class="sxs-lookup"><span data-stu-id="7f958-117">The following table lists the dateparts and abbreviations recognized by the expression evaluator.</span></span> <span data-ttu-id="7f958-118">Les noms de partie de date ne respectent pas la casse.</span><span class="sxs-lookup"><span data-stu-id="7f958-118">Datepart names are not case sensitive.</span></span>  
  
|<span data-ttu-id="7f958-119">partie de date</span><span class="sxs-lookup"><span data-stu-id="7f958-119">Datepart</span></span>|<span data-ttu-id="7f958-120">Abréviations</span><span class="sxs-lookup"><span data-stu-id="7f958-120">Abbreviations</span></span>|  
|--------------|-------------------|  
|<span data-ttu-id="7f958-121">Year</span><span class="sxs-lookup"><span data-stu-id="7f958-121">Year</span></span>|<span data-ttu-id="7f958-122">yy, yyyy</span><span class="sxs-lookup"><span data-stu-id="7f958-122">yy, yyyy</span></span>|  
|<span data-ttu-id="7f958-123">Quarter</span><span class="sxs-lookup"><span data-stu-id="7f958-123">Quarter</span></span>|<span data-ttu-id="7f958-124">qq, q</span><span class="sxs-lookup"><span data-stu-id="7f958-124">qq, q</span></span>|  
|<span data-ttu-id="7f958-125">Month</span><span class="sxs-lookup"><span data-stu-id="7f958-125">Month</span></span>|<span data-ttu-id="7f958-126">mm, m</span><span class="sxs-lookup"><span data-stu-id="7f958-126">mm, m</span></span>|  
|<span data-ttu-id="7f958-127">Jour de l'année</span><span class="sxs-lookup"><span data-stu-id="7f958-127">Dayofyear</span></span>|<span data-ttu-id="7f958-128">dy, y</span><span class="sxs-lookup"><span data-stu-id="7f958-128">dy, y</span></span>|  
|<span data-ttu-id="7f958-129">jour</span><span class="sxs-lookup"><span data-stu-id="7f958-129">Day</span></span>|<span data-ttu-id="7f958-130">dd, d</span><span class="sxs-lookup"><span data-stu-id="7f958-130">dd, d</span></span>|  
|<span data-ttu-id="7f958-131">Week</span><span class="sxs-lookup"><span data-stu-id="7f958-131">Week</span></span>|<span data-ttu-id="7f958-132">wk, ww</span><span class="sxs-lookup"><span data-stu-id="7f958-132">wk, ww</span></span>|  
|<span data-ttu-id="7f958-133">Jour de la semaine</span><span class="sxs-lookup"><span data-stu-id="7f958-133">Weekday</span></span>|<span data-ttu-id="7f958-134">dw, w</span><span class="sxs-lookup"><span data-stu-id="7f958-134">dw, w</span></span>|  
|<span data-ttu-id="7f958-135">Heure</span><span class="sxs-lookup"><span data-stu-id="7f958-135">Hour</span></span>|<span data-ttu-id="7f958-136">Hh</span><span class="sxs-lookup"><span data-stu-id="7f958-136">Hh</span></span>|  
|<span data-ttu-id="7f958-137">Minute</span><span class="sxs-lookup"><span data-stu-id="7f958-137">Minute</span></span>|<span data-ttu-id="7f958-138">mi, n</span><span class="sxs-lookup"><span data-stu-id="7f958-138">mi, n</span></span>|  
|<span data-ttu-id="7f958-139">Seconde</span><span class="sxs-lookup"><span data-stu-id="7f958-139">Second</span></span>|<span data-ttu-id="7f958-140">ss, s</span><span class="sxs-lookup"><span data-stu-id="7f958-140">ss, s</span></span>|  
|<span data-ttu-id="7f958-141">Milliseconde</span><span class="sxs-lookup"><span data-stu-id="7f958-141">Millisecond</span></span>|<span data-ttu-id="7f958-142">Ms</span><span class="sxs-lookup"><span data-stu-id="7f958-142">Ms</span></span>|  
  
 <span data-ttu-id="7f958-143">L’argument *nombre* doit être disponible quand l’expression est analysée.</span><span class="sxs-lookup"><span data-stu-id="7f958-143">The *number* argument must be available when the expression is parsed.</span></span> <span data-ttu-id="7f958-144">Cet argument peut être une constante ou une variable.</span><span class="sxs-lookup"><span data-stu-id="7f958-144">The argument can be a constant or a variable.</span></span> <span data-ttu-id="7f958-145">Vous ne pouvez pas utiliser des valeurs de colonne car celles-ci ne sont pas connues lorsque l'expression est analysée.</span><span class="sxs-lookup"><span data-stu-id="7f958-145">You cannot use column values because the values are not known when the expression is parsed.</span></span>  
  
 <span data-ttu-id="7f958-146">L’argument *datepart* doit être placé entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="7f958-146">The *datepart* argument must be enclosed by quotation marks.</span></span>  
  
 <span data-ttu-id="7f958-147">Un littéral de date doit être explicitement converti dans l'un des types de données date.</span><span class="sxs-lookup"><span data-stu-id="7f958-147">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="7f958-148">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f958-148">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="7f958-149">La fonction DATEADD renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="7f958-149">DATEADD returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="7f958-150">Des erreurs se produisent dans les cas suivants : une date n'est pas valide, l'unité de date ou d'heure n'est pas une chaîne ou l'incrément n'est pas un entier statique.</span><span class="sxs-lookup"><span data-stu-id="7f958-150">Errors occur if a date is invalid, if the date or time unit is not a string, or if the increment is not a static integer.</span></span>  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="7f958-151">Exemples d'expressions SSIS</span><span class="sxs-lookup"><span data-stu-id="7f958-151">SSIS Expression Examples</span></span>  
 <span data-ttu-id="7f958-152">L'exemple suivant ajoute un mois à la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="7f958-152">This example adds one month to the current date.</span></span>  
  
```  
DATEADD("Month", 1,GETDATE())  
```  
  
 <span data-ttu-id="7f958-153">L’exemple suivant ajoute 21 jours aux dates de la colonne **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="7f958-153">This example adds 21 days to the dates in the **ModifiedDate** column.</span></span>  
  
```  
DATEADD("day", 21, ModifiedDate)  
```  
  
 <span data-ttu-id="7f958-154">L'exemple suivant ajoute 2 années à une date littérale.</span><span class="sxs-lookup"><span data-stu-id="7f958-154">This example adds 2 years to a literal date.</span></span>  
  
```  
DATEADD("yyyy", 2, (DT_DBTIMESTAMP)"8/6/2003")  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f958-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f958-155">See Also</span></span>  
 <span data-ttu-id="7f958-156">[DATEDIFF &#40;expression SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7f958-156">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="7f958-157">[DATEPART &#40;expression SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7f958-157">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="7f958-158">[DAY &#40;expression SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7f958-158">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="7f958-159">[MONTH &#40;expression SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7f958-159">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="7f958-160">[YEAR &#40;expression SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7f958-160">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="7f958-161">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7f958-161">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
