---
title: MONTH (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], MONTH
- MONTH function
ms.assetid: b5a47a11-c2ef-49bd-bd70-235632ff7bf6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1f56906b4d25f2ba01f54fbdbc404d2c9ae4704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604647"
---
# <a name="month-ssis-expression"></a><span data-ttu-id="b95e5-102">MONTH (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="b95e5-102">MONTH (SSIS Expression)</span></span>
  <span data-ttu-id="b95e5-103">Renvoie un entier qui représente la partie mois d'une date.</span><span class="sxs-lookup"><span data-stu-id="b95e5-103">Returns an integer that represents the month datepart of a date.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b95e5-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b95e5-104">Syntax</span></span>  
  
```  
  
MONTH(date)  
```  
  
## <a name="arguments"></a><span data-ttu-id="b95e5-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="b95e5-105">Arguments</span></span>  
 <span data-ttu-id="b95e5-106">*date*</span><span class="sxs-lookup"><span data-stu-id="b95e5-106">*date*</span></span>  
 <span data-ttu-id="b95e5-107">Date à n'importe quel format de date.</span><span class="sxs-lookup"><span data-stu-id="b95e5-107">Is a date in any date format.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b95e5-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="b95e5-108">Result Types</span></span>  
 <span data-ttu-id="b95e5-109">DT_I4</span><span class="sxs-lookup"><span data-stu-id="b95e5-109">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b95e5-110">Notes</span><span class="sxs-lookup"><span data-stu-id="b95e5-110">Remarks</span></span>  
 <span data-ttu-id="b95e5-111">La fonction MONTH renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="b95e5-111">MONTH returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="b95e5-112">Un littéral de date doit être explicitement converti dans l'un des types de données date.</span><span class="sxs-lookup"><span data-stu-id="b95e5-112">A date literal must be explicitly cast to one of the date data types.</span></span> <span data-ttu-id="b95e5-113">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b95e5-113">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b95e5-114">La validation de l'expression échoue lorsqu'un littéral de date est explicitement converti en un des types de données de date suivants : DT_DBTIMESTAMPOFFSET et DT_DBTIMESTAMP2.</span><span class="sxs-lookup"><span data-stu-id="b95e5-114">The expression fails to validate when a date literal is explicitly cast to one of these date data types: DT_DBTIMESTAMPOFFSET and DT_DBTIMESTAMP2.</span></span>  
  
 <span data-ttu-id="b95e5-115">L'utilisation de la fonction MONTH est plus directe mais équivalente à celle de la fonction DATEPART("Month", date).</span><span class="sxs-lookup"><span data-stu-id="b95e5-115">Using the MONTH function is briefer but equivalent to using DATEPART("Month", date).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="b95e5-116">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="b95e5-116">Expression Examples</span></span>  
 <span data-ttu-id="b95e5-117">Cet exemple renvoie le chiffre représentant le mois dans un littéral de date.</span><span class="sxs-lookup"><span data-stu-id="b95e5-117">This example returns the number of the month in a date literal.</span></span> <span data-ttu-id="b95e5-118">Si le format de la date est « mm/jj/aaaa », l'exemple renvoie 11.</span><span class="sxs-lookup"><span data-stu-id="b95e5-118">If the date is in "mm/dd/yyyy" format, this example returns 11.</span></span>  
  
```  
MONTH((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 <span data-ttu-id="b95e5-119">L’exemple suivant renvoie l’entier qui représente le mois dans la colonne **ModifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="b95e5-119">This example returns the integer that represents the month in the **ModifiedDate** column.</span></span>  
  
```  
MONTH(ModifiedDate)  
```  
  
 <span data-ttu-id="b95e5-120">L'exemple suivant renvoie l'entier qui représente le mois de la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="b95e5-120">This example returns the integer that represents the month of the current date.</span></span>  
  
```  
MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="b95e5-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b95e5-121">See Also</span></span>  
 <span data-ttu-id="b95e5-122">[DATEADD &#40;expression SSIS&#41;](dateadd-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b95e5-122">[DATEADD &#40;SSIS Expression&#41;](dateadd-ssis-expression.md) </span></span>  
 <span data-ttu-id="b95e5-123">[DATEDIFF &#40;expression SSIS&#41;](datediff-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b95e5-123">[DATEDIFF &#40;SSIS Expression&#41;](datediff-ssis-expression.md) </span></span>  
 <span data-ttu-id="b95e5-124">[DATEPART &#40;expression SSIS&#41;](datepart-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b95e5-124">[DATEPART &#40;SSIS Expression&#41;](datepart-ssis-expression.md) </span></span>  
 <span data-ttu-id="b95e5-125">[DAY &#40;expression SSIS&#41;](day-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b95e5-125">[DAY &#40;SSIS Expression&#41;](day-ssis-expression.md) </span></span>  
 <span data-ttu-id="b95e5-126">[YEAR &#40;expression SSIS&#41;](year-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="b95e5-126">[YEAR &#40;SSIS Expression&#41;](year-ssis-expression.md) </span></span>  
 [<span data-ttu-id="b95e5-127">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b95e5-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
