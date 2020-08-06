---
title: DAY (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- DAY function
- dates [Integration Services], DAY
ms.assetid: d8447187-49df-45b7-a98e-142ad44fd3e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b7acac3f3949cbbd07adbe6382ea3d875f94cb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700056"
---
# <a name="day-ssis-expression"></a><span data-ttu-id="523ee-102">DAY (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="523ee-102">DAY (SSIS Expression)</span></span>
  <span data-ttu-id="523ee-103">Renvoie un entier qui représente la partie jour d'une date.</span><span class="sxs-lookup"><span data-stu-id="523ee-103">Returns an integer that represents the day datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="523ee-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="523ee-104">Syntax</span></span>  
  
```  
  
DAY(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="523ee-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="523ee-105">Arguments</span></span>  
 <span data-ttu-id="523ee-106">*date*</span><span class="sxs-lookup"><span data-stu-id="523ee-106">*date*</span></span>  
 <span data-ttu-id="523ee-107">Expression renvoyant une date valide ou une chaîne dans un format de date.</span><span class="sxs-lookup"><span data-stu-id="523ee-107">Is an expression that returns a valid date or a string in date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="523ee-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="523ee-108">Result Types</span></span>  
 <span data-ttu-id="523ee-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="523ee-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="523ee-110">Notes</span><span class="sxs-lookup"><span data-stu-id="523ee-110">Remarks</span></span>  
 <span data-ttu-id="523ee-111">La fonction DAY renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="523ee-111">DAY returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="523ee-112">Un littéral de date doit être explicitement converti dans l'un des types de données date.</span><span class="sxs-lookup"><span data-stu-id="523ee-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="523ee-113">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="523ee-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="523ee-114">La validation de l'expression échoue lorsqu'un littéral de date est explicitement converti en un des types de données de date suivants : DT_DBTIMESTAMPOFFSET et DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="523ee-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="523ee-115">L'utilisation de la fonction DAY est plus directe mais équivalente à celle de la fonction DATEPART("Day", date).</span><span class="sxs-lookup"><span data-stu-id="523ee-115">Using the DAY function is briefer but equivalent to using DATEPART("Day", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="523ee-116">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="523ee-116">Expression Examples</span></span>  
 <span data-ttu-id="523ee-117">Cet exemple renvoie le nombre représentant le jour dans un littéral de date.</span><span class="sxs-lookup"><span data-stu-id="523ee-117">This example returns the number of the day in a date literal.</span></span> <span data-ttu-id="523ee-118">Si le format de la date est « mm/jj/aaaa », l'exemple renvoie 23.</span><span class="sxs-lookup"><span data-stu-id="523ee-118">If the date format is in "mm/dd/yyyy" format, this example returns 23.</span></span>  
  
```  
DAY((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="523ee-119">L’exemple suivant retourne l’entier qui représente le jour dans la colonne **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="523ee-119">This example returns the integer that represents the day in the **ModifiedDate** column.</span></span>  
  
```  
DAY(ModifiedDate)  
```  
  
 <span data-ttu-id="523ee-120">L'exemple suivant renvoie l'entier qui représente le jour de la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="523ee-120">This example returns the integer that represents the day of the current date.</span></span>  
  
```  
DAY(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="523ee-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="523ee-121">See Also</span></span>  
 <span data-ttu-id="523ee-122">[DATEADD &#40;expression SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="523ee-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="523ee-123">[DATEDIFF &#40;expression SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="523ee-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="523ee-124">[DATEPART &#40;expression SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="523ee-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="523ee-125">[MONTH &#40;expression SSIS&#41;](month-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="523ee-125">[MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) </span></span>  
 <span data-ttu-id="523ee-126">[YEAR &#40;expression SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="523ee-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="523ee-127">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="523ee-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
