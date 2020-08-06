---
title: REVERSE (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REVERSE function
- reverse character expressions
ms.assetid: bcebcc55-7247-4896-8f53-4d582d58cfb4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2ace136eed0abcb9df7b25d9370c46d7556c1d48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701411"
---
# <a name="reverse-ssis-expression"></a><span data-ttu-id="ab5fd-102">REVERSE (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="ab5fd-102">REVERSE (SSIS Expression)</span></span>
  <span data-ttu-id="ab5fd-103">Renvoie une expression de caractères en ordre inverse.</span><span class="sxs-lookup"><span data-stu-id="ab5fd-103">Returns a character expression in reverse order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab5fd-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ab5fd-104">Syntax</span></span>  
  
```  
  
REVERSE(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ab5fd-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="ab5fd-105">Arguments</span></span>  
 <span data-ttu-id="ab5fd-106">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="ab5fd-106">*character_expression*</span></span>  
 <span data-ttu-id="ab5fd-107">Expression de caractères à inverser.</span><span class="sxs-lookup"><span data-stu-id="ab5fd-107">Is a character expression to be reversed.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ab5fd-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="ab5fd-108">Result Types</span></span>  
 <span data-ttu-id="ab5fd-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="ab5fd-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab5fd-110">Notes</span><span class="sxs-lookup"><span data-stu-id="ab5fd-110">Remarks</span></span>  
 <span data-ttu-id="ab5fd-111">L’argument *character_expression* doit être du type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="ab5fd-111">The *character_expression* argument must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="ab5fd-112">REVERSE retourne un résultat Null si *character_expression* est Null.</span><span class="sxs-lookup"><span data-stu-id="ab5fd-112">REVERSE returns a null result if *character_expression* is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ab5fd-113">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="ab5fd-113">Expression Examples</span></span>  
 <span data-ttu-id="ab5fd-114">L'exemple suivant utilise un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="ab5fd-114">This example uses a string literal.</span></span> <span data-ttu-id="ab5fd-115">Le résultat obtenu est « ekiB niatnuoM ».</span><span class="sxs-lookup"><span data-stu-id="ab5fd-115">The return result is "ekiB niatnuoM".</span></span>  
  
```  
REVERSE("Mountain Bike")  
```  
  
 <span data-ttu-id="ab5fd-116">L'exemple suivant utilise une variable.</span><span class="sxs-lookup"><span data-stu-id="ab5fd-116">This example uses a variable.</span></span> <span data-ttu-id="ab5fd-117">Si la variable **Name** contient « VTT », le résultat obtenu est « TTV ».</span><span class="sxs-lookup"><span data-stu-id="ab5fd-117">If **Name** contains Touring Bike, the return result is "ekiB gniruoT".</span></span>  
  
```  
REVERSE(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab5fd-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab5fd-118">See Also</span></span>  
 [<span data-ttu-id="ab5fd-119">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ab5fd-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
