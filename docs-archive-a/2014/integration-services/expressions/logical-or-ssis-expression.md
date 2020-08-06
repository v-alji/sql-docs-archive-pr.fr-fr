---
title: '|| (OR logique) (expression SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OR operator
- logical OR (||)
- '|| (logical OR)'
ms.assetid: a3c07c09-f121-4187-9617-b01adcf843c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 72d4a1c7b54856675f0faa7f5f58452cb8bca450
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697031"
---
# <a name="-logical-or-ssis-expression"></a><span data-ttu-id="5d734-102">|| (OU logique) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="5d734-102">|| (Logical OR) (SSIS Expression)</span></span>
  <span data-ttu-id="5d734-103">Effectue une opération OR logique.</span><span class="sxs-lookup"><span data-stu-id="5d734-103">Performs a logical OR operation.</span></span> <span data-ttu-id="5d734-104">L'expression renvoie la valeur TRUE si au moins une des deux conditions s'évalue à TRUE.</span><span class="sxs-lookup"><span data-stu-id="5d734-104">The expression evaluates to TRUE if one or both conditions are TRUE.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d734-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5d734-105">Syntax</span></span>  
  
```  
  
boolean_expression1 || boolean_expression2  
```  
  
## <a name="arguments"></a><span data-ttu-id="5d734-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="5d734-106">Arguments</span></span>  
 <span data-ttu-id="5d734-107">*boolean_expression1, boolean_expression2*</span><span class="sxs-lookup"><span data-stu-id="5d734-107">*boolean_expression1, boolean_expression2*</span></span>  
 <span data-ttu-id="5d734-108">Expression valide qui renvoie TRUE, FALSE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="5d734-108">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5d734-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="5d734-109">Result Types</span></span>  
 <span data-ttu-id="5d734-110">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="5d734-110">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d734-111">Notes</span><span class="sxs-lookup"><span data-stu-id="5d734-111">Remarks</span></span>  
 <span data-ttu-id="5d734-112">Le tableau suivant indique le résultat de l'opérateur « || »</span><span class="sxs-lookup"><span data-stu-id="5d734-112">The following table shows the result of the || operator.</span></span>  
  
|<span data-ttu-id="5d734-113">Résultats</span><span class="sxs-lookup"><span data-stu-id="5d734-113">Result</span></span>|<span data-ttu-id="5d734-114">Expression</span><span class="sxs-lookup"><span data-stu-id="5d734-114">Expression</span></span>|<span data-ttu-id="5d734-115">Expression</span><span class="sxs-lookup"><span data-stu-id="5d734-115">Expression</span></span>|  
|------------|----------------|----------------|  
|<span data-ttu-id="5d734-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d734-116">TRUE</span></span>|<span data-ttu-id="5d734-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d734-117">TRUE</span></span>|<span data-ttu-id="5d734-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d734-118">TRUE</span></span>|  
|<span data-ttu-id="5d734-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d734-119">TRUE</span></span>|<span data-ttu-id="5d734-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d734-120">TRUE</span></span>|<span data-ttu-id="5d734-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="5d734-121">FALSE</span></span>|  
|<span data-ttu-id="5d734-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="5d734-122">FALSE</span></span>|<span data-ttu-id="5d734-123">FALSE</span><span class="sxs-lookup"><span data-stu-id="5d734-123">FALSE</span></span>|<span data-ttu-id="5d734-124">FALSE</span><span class="sxs-lookup"><span data-stu-id="5d734-124">FALSE</span></span>|  
|<span data-ttu-id="5d734-125">NULL</span><span class="sxs-lookup"><span data-stu-id="5d734-125">NULL</span></span>|<span data-ttu-id="5d734-126">NULL</span><span class="sxs-lookup"><span data-stu-id="5d734-126">NULL</span></span>|<span data-ttu-id="5d734-127">NULL</span><span class="sxs-lookup"><span data-stu-id="5d734-127">NULL</span></span>|  
|<span data-ttu-id="5d734-128">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d734-128">TRUE</span></span>|<span data-ttu-id="5d734-129">NULL</span><span class="sxs-lookup"><span data-stu-id="5d734-129">NULL</span></span>|<span data-ttu-id="5d734-130">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d734-130">TRUE</span></span>|  
|<span data-ttu-id="5d734-131">NULL</span><span class="sxs-lookup"><span data-stu-id="5d734-131">NULL</span></span>|<span data-ttu-id="5d734-132">NULL</span><span class="sxs-lookup"><span data-stu-id="5d734-132">NULL</span></span>|<span data-ttu-id="5d734-133">FALSE</span><span class="sxs-lookup"><span data-stu-id="5d734-133">FALSE</span></span>|  
  
## <a name="ssis-expression-examples"></a><span data-ttu-id="5d734-134">Exemples d'expressions SSIS</span><span class="sxs-lookup"><span data-stu-id="5d734-134">SSIS Expression Examples</span></span>  
 <span data-ttu-id="5d734-135">L'exemple suivant utilise les colonnes **StandardCost** et **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="5d734-135">This example uses the **StandardCost** and **ListPrice** columns.</span></span> <span data-ttu-id="5d734-136">L'exemple renvoie la valeur TRUE si la valeur de la colonne **StandardCost** est inférieure à 300 ou que celle de la colonne **ListPrice** est supérieure à 500.</span><span class="sxs-lookup"><span data-stu-id="5d734-136">The example evaluates to TRUE if the value of the **StandardCost** column is less than 300 or the **ListPrice** column is greater than 500.</span></span>  
  
```  
StandardCost < 300 || ListPrice > 500  
```  
  
 <span data-ttu-id="5d734-137">L'exemple suivant utilise les variables **SPrice** et **LPrice** au lieu de littéraux numériques.</span><span class="sxs-lookup"><span data-stu-id="5d734-137">This example uses the variables **SPrice** and **LPrice** instead of numeric literals.</span></span>  
  
```  
StandardCost < @SPrice || ListPrice > @LPrice  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d734-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d734-138">See Also</span></span>  
 <span data-ttu-id="5d734-139">[&#124; &#40;opération OR inclusive au niveau du bit&#41; &#40;expression SSIS&#41;](bitwise-inclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5d734-139">[&#124; &#40;Bitwise Inclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-inclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="5d734-140">[^ &#40;OR exclusif au niveau du bit&#41; &#40;expression SSIS&#41;](bitwise-exclusive-or-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="5d734-140">[^ &#40;Bitwise Exclusive OR&#41; &#40;SSIS Expression&#41;](bitwise-exclusive-or-ssis-expression.md) </span></span>  
 <span data-ttu-id="5d734-141">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="5d734-141">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="5d734-142">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5d734-142">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
