---
title: '! (Non logique) (expression SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logical Not (!)
- '! (logical Not)'
ms.assetid: d5c4d1e1-7be4-4d25-bcd9-5b6ddb53b3b3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bbf313930575e864f1556952425567fca96db15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604651"
---
# <a name="-logical-not-ssis-expression"></a><span data-ttu-id="ac843-103">!</span><span class="sxs-lookup"><span data-stu-id="ac843-103">!</span></span> <span data-ttu-id="ac843-104">(Non logique) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="ac843-104">(Logical Not) (SSIS Expression)</span></span>
  <span data-ttu-id="ac843-105">Inverse un opérande booléen.</span><span class="sxs-lookup"><span data-stu-id="ac843-105">Negates a Boolean operand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac843-106">L'opérateur « ! »</span><span class="sxs-lookup"><span data-stu-id="ac843-106">The !</span></span> <span data-ttu-id="ac843-107">ne peut pas être utilisé en combinaison avec d'autres opérateurs.</span><span class="sxs-lookup"><span data-stu-id="ac843-107">operator cannot be used in conjunction with other operators.</span></span> <span data-ttu-id="ac843-108">Par exemple, vous ne pouvez pas combiner les opérateurs « ! »</span><span class="sxs-lookup"><span data-stu-id="ac843-108">For example, you cannot combine the !</span></span> <span data-ttu-id="ac843-109">et > pour former l'opérateur « !> »</span><span class="sxs-lookup"><span data-stu-id="ac843-109">and the > operators into the !>.</span></span> <span data-ttu-id="ac843-110">.</span><span class="sxs-lookup"><span data-stu-id="ac843-110">operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac843-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ac843-111">Syntax</span></span>  
  
```  
  
!boolean_expression  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac843-112">Arguments</span><span class="sxs-lookup"><span data-stu-id="ac843-112">Arguments</span></span>  
 <span data-ttu-id="ac843-113">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="ac843-113">*boolean_expression*</span></span>  
 <span data-ttu-id="ac843-114">Toute expression valide qui s'évalue à une valeur booléenne.</span><span class="sxs-lookup"><span data-stu-id="ac843-114">Is any valid expression that evaluates to a Boolean.</span></span> <span data-ttu-id="ac843-115">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac843-115">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ac843-116">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="ac843-116">Result Types</span></span>  
 <span data-ttu-id="ac843-117">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="ac843-117">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac843-118">Notes</span><span class="sxs-lookup"><span data-stu-id="ac843-118">Remarks</span></span>  
 <span data-ttu-id="ac843-119">Le tableau suivant indique le résultat de l'opération « ! »</span><span class="sxs-lookup"><span data-stu-id="ac843-119">The following table shows the result of the !</span></span> <span data-ttu-id="ac843-120">.</span><span class="sxs-lookup"><span data-stu-id="ac843-120">operation.</span></span>  
  
|<span data-ttu-id="ac843-121">Expression booléenne initiale</span><span class="sxs-lookup"><span data-stu-id="ac843-121">Original Boolean expression</span></span>|<span data-ttu-id="ac843-122">Après application de l'opérateur « ! »</span><span class="sxs-lookup"><span data-stu-id="ac843-122">After applying the !</span></span> <span data-ttu-id="ac843-123">operator</span><span class="sxs-lookup"><span data-stu-id="ac843-123">operator</span></span>|  
|---------------------------------|------------------------------------|  
|<span data-ttu-id="ac843-124">TRUE</span><span class="sxs-lookup"><span data-stu-id="ac843-124">TRUE</span></span>|<span data-ttu-id="ac843-125">FALSE</span><span class="sxs-lookup"><span data-stu-id="ac843-125">FALSE</span></span>|  
|<span data-ttu-id="ac843-126">NULL</span><span class="sxs-lookup"><span data-stu-id="ac843-126">NULL</span></span>|<span data-ttu-id="ac843-127">NULL</span><span class="sxs-lookup"><span data-stu-id="ac843-127">NULL</span></span>|  
|<span data-ttu-id="ac843-128">FALSE</span><span class="sxs-lookup"><span data-stu-id="ac843-128">FALSE</span></span>|<span data-ttu-id="ac843-129">TRUE</span><span class="sxs-lookup"><span data-stu-id="ac843-129">TRUE</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="ac843-130">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="ac843-130">Expression Examples</span></span>  
 <span data-ttu-id="ac843-131">L’exemple suivant donne la valeur FALSE si la colonne **Color** a pour valeur « red ».</span><span class="sxs-lookup"><span data-stu-id="ac843-131">This example evaluates to FALSE if the **Color** column value is "red".</span></span>  
  
```  
!(Color == "red")  
```  
  
 <span data-ttu-id="ac843-132">L’exemple suivant donne la valeur TRUE si la valeur de la variable **MonthNumber** et celle de l’entier qui représente le mois actuel sont identiques.</span><span class="sxs-lookup"><span data-stu-id="ac843-132">This example evaluates to TRUE if the value of the **MonthNumber** variable is the same as the integer that represents the current month.</span></span> <span data-ttu-id="ac843-133">Pour plus d’informations, consultez [MONTH &#40;expression SSIS&#41;](month-ssis-expression.md) et [GETDATE &#40;expression SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="ac843-133">For more information, see [MONTH &#40;SSIS Expression&#41;](month-ssis-expression.md) and [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
!(@MonthNumber != MONTH(GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac843-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac843-134">See Also</span></span>  
 <span data-ttu-id="ac843-135">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="ac843-135">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="ac843-136">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ac843-136">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
