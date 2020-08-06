---
title: YEAR (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], YEAR
- YEAR function
ms.assetid: 9d88dead-ace8-44b9-b8e2-916c1842e155
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 181375d489fbf7abf0718386efacf4167ba555d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612454"
---
# <a name="year-ssis-expression"></a><span data-ttu-id="97070-102">YEAR (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="97070-102">YEAR (SSIS Expression)</span></span>
  <span data-ttu-id="97070-103">Renvoie un entier qui représente la partie année d'une date.</span><span class="sxs-lookup"><span data-stu-id="97070-103">Returns an integer that represents the year datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97070-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="97070-104">Syntax</span></span>  
  
```  
  
YEAR(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="97070-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="97070-105">Arguments</span></span>  
 <span data-ttu-id="97070-106">*date*</span><span class="sxs-lookup"><span data-stu-id="97070-106">*date*</span></span>  
 <span data-ttu-id="97070-107">Date à n'importe quel format de date.</span><span class="sxs-lookup"><span data-stu-id="97070-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="97070-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="97070-108">Result Types</span></span>  
 <span data-ttu-id="97070-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="97070-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97070-110">Notes</span><span class="sxs-lookup"><span data-stu-id="97070-110">Remarks</span></span>  
 <span data-ttu-id="97070-111">La fonction YEAR renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="97070-111">YEAR returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="97070-112">Un littéral de date doit être explicitement converti dans l'un des types de données date.</span><span class="sxs-lookup"><span data-stu-id="97070-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="97070-113">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="97070-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97070-114">La validation de l'expression échoue lorsqu'un littéral de date est explicitement converti en un des types de données de date suivants : DT_DBTIMESTAMPOFFSET et DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="97070-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="97070-115">L'utilisation de la fonction YEAR est plus directe mais elle est équivalente à celle de la fonction DATEPART("Year", date).</span><span class="sxs-lookup"><span data-stu-id="97070-115">Using the YEAR function is briefer but equivalent to using the DATEPART("Year", date) function.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="97070-116">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="97070-116">Expression Examples</span></span>  
 <span data-ttu-id="97070-117">Cet exemple renvoie le nombre représentant l'année dans un littéral de date.</span><span class="sxs-lookup"><span data-stu-id="97070-117">This example returns the number of the year in a date literal.</span></span> <span data-ttu-id="97070-118">Si le format de la date est « mm/jj/aaaa », l'exemple renvoie « 2002 ».</span><span class="sxs-lookup"><span data-stu-id="97070-118">If the date is in mm/dd/yyyy format, this example returns "2002".</span></span>  
  
```  
YEAR((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="97070-119">L’exemple suivant renvoie l’entier qui représente l’année dans la colonne **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="97070-119">This example returns the integer that represents the year in the **ModifiedDate** column.</span></span>  
  
```  
YEAR(ModifiedDate)  
```  
  
 <span data-ttu-id="97070-120">L'exemple suivant renvoie l'entier qui représente l'année de la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="97070-120">This example returns the integer that represents the year of the current date.</span></span>  
  
```  
YEAR(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="97070-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97070-121">See Also</span></span>  
 <span data-ttu-id="97070-122">[DATEADD &#40;expression SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="97070-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="97070-123">[DATEDIFF &#40;expression SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="97070-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="97070-124">[DATEPART &#40;expression SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="97070-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="97070-125">[DAY &#40;expression SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="97070-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="97070-126">[MONTH &#40;expression SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="97070-126">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 [<span data-ttu-id="97070-127">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="97070-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
