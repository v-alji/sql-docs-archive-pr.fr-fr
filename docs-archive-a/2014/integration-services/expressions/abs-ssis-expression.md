---
title: ABS (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- ABS function
- absolute positive value
ms.assetid: 156747f6-e016-44cf-9a9f-ae8e4a1b4f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f429dda94282646ef769a1c393f9fa54b56e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611933"
---
# <a name="abs-ssis-expression"></a><span data-ttu-id="2e79f-102">ABS (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="2e79f-102">ABS (SSIS Expression)</span></span>
  <span data-ttu-id="2e79f-103">Renvoie la valeur absolue d'une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="2e79f-103">Returns the absolute, positive value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e79f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2e79f-104">Syntax</span></span>  
  
```  
  
ABS(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="2e79f-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="2e79f-105">Arguments</span></span>  
 <span data-ttu-id="2e79f-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="2e79f-106">*numeric_expression*</span></span>  
 <span data-ttu-id="2e79f-107">Expression numérique signée ou non signée.</span><span class="sxs-lookup"><span data-stu-id="2e79f-107">Is a signed or unsigned numeric expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2e79f-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="2e79f-108">Result Types</span></span>  
 <span data-ttu-id="2e79f-109">Type de données de l'expression numérique envoyée à la fonction.</span><span class="sxs-lookup"><span data-stu-id="2e79f-109">The data type of the numeric expression submitted to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e79f-110">Notes</span><span class="sxs-lookup"><span data-stu-id="2e79f-110">Remarks</span></span>  
 <span data-ttu-id="2e79f-111">La fonction ABS renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="2e79f-111">ABS returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2e79f-112">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="2e79f-112">Expression Examples</span></span>  
 <span data-ttu-id="2e79f-113">Les exemples suivants appliquent la fonction ABS à un nombre positif et à un nombre négatif.</span><span class="sxs-lookup"><span data-stu-id="2e79f-113">These examples apply the ABS function to a positive and a negative number.</span></span> <span data-ttu-id="2e79f-114">Tous les deux renvoient le résultat 1,23.</span><span class="sxs-lookup"><span data-stu-id="2e79f-114">Both return 1.23.</span></span>  
  
```  
ABS(-1.23)  
ABS(1.23)  
```  
  
 <span data-ttu-id="2e79f-115">L'exemple suivant applique la fonction ABS à une expression qui calcule la différence entre les valeurs des variables **HighTemperature** et **LowTempature**.</span><span class="sxs-lookup"><span data-stu-id="2e79f-115">This example applies the ABS function to an expression that subtracts values in the variables **HighTemperature** and **LowTempature**.</span></span>  
  
```  
ABS(@HighTemperature - @LowTemperature)  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e79f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e79f-116">See Also</span></span>  
 [<span data-ttu-id="2e79f-117">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2e79f-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
