---
title: Diviser (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- / (divide)
- divide operator (/)
ms.assetid: 5bde9223-872d-443e-8a27-57735e1d8f3d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4541cd4601047770d1bf361077b1c474219e8833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602211"
---
# <a name="divide-ssis-expression"></a><span data-ttu-id="ee1b9-102">Diviser (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="ee1b9-102">Divide (SSIS Expression)</span></span>
  <span data-ttu-id="ee1b9-103">Divise la première expression numérique par la deuxième.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-103">Divides the first numeric expression by the second one.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee1b9-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ee1b9-104">Syntax</span></span>  
  
```  
  
dividend / divisor  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ee1b9-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="ee1b9-105">Arguments</span></span>  
 <span data-ttu-id="ee1b9-106">*dividend*</span><span class="sxs-lookup"><span data-stu-id="ee1b9-106">*dividend*</span></span>  
 <span data-ttu-id="ee1b9-107">Expression numérique à diviser.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-107">Is the numeric expression to divide.</span></span> <span data-ttu-id="ee1b9-108">*dividend* peut être n’importe quelle expression numérique valide.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-108">*dividend* can be any valid numeric expression.</span></span> <span data-ttu-id="ee1b9-109">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ee1b9-109">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="ee1b9-110">*divisor*</span><span class="sxs-lookup"><span data-stu-id="ee1b9-110">*divisor*</span></span>  
 <span data-ttu-id="ee1b9-111">Expression numérique par laquelle diviser le dividende.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-111">Is the numeric expression to divide the dividend by.</span></span> <span data-ttu-id="ee1b9-112">*divisor* peut être n’importe quelle expression numérique valide, sauf zéro.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-112">*divisor* can be any valid numeric expression except zero.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ee1b9-113">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="ee1b9-113">Result Types</span></span>  
 <span data-ttu-id="ee1b9-114">Déterminés par les types de données des deux arguments.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-114">Determined by data types of the two arguments.</span></span> <span data-ttu-id="ee1b9-115">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ee1b9-115">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee1b9-116">Notes</span><span class="sxs-lookup"><span data-stu-id="ee1b9-116">Remarks</span></span>  
 <span data-ttu-id="ee1b9-117">Si l'un des opérandes est NULL, le résultat est NULL.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-117">If either operand is null, the result is null.</span></span>  
  
 <span data-ttu-id="ee1b9-118">La division par zéro n'est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-118">Dividing by zero is not legal.</span></span> <span data-ttu-id="ee1b9-119">L’évaluation de la sous-expression *divisor* génère l’une des erreurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ee1b9-119">Depending on how the *divisor* subexpression is evaluated, one of following errors occurs:</span></span>  
  
-   <span data-ttu-id="ee1b9-120">Si la sous-expression *divisor* qui donne la valeur zéro est une constante, l’erreur se produit au moment de la conception et provoque l’échec de la validation de l’expression.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-120">If the *divisor* subexpression that evaluates to zero is a constant, the error appears at design time, causing the expression to fail validation.</span></span>  
  
-   <span data-ttu-id="ee1b9-121">Si la sous-expression *divisor* qui donne la valeur zéro contient des variables, mais aucune colonne d’entrée, le composant auquel l’expression appartient ne parvient pas à valider l’exécution préalable du package.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-121">If the *divisor* subexpression that evaluates to zero contains variables, but no input columns, the component to which the expression belongs fails the pre-execution validation that occurs before the package runs.</span></span>  
  
-   <span data-ttu-id="ee1b9-122">Si la sous-expression *divisor* qui donne la valeur zéro contient des colonnes d’entrée, l’erreur se produit au moment de l’exécution et est gérée en fonction des règles de flux d’erreur du composant de flux de données.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-122">If the *divisor* subexpression that evaluates to zero contains input columns, the error appears at run time and is handled according to the error flow rules of the data flow component.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ee1b9-123">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="ee1b9-123">Expression Examples</span></span>  
 <span data-ttu-id="ee1b9-124">L'exemple suivant divise deux littéraux numériques.</span><span class="sxs-lookup"><span data-stu-id="ee1b9-124">This example divides two numeric literals.</span></span>  
  
```  
25 / 5  
```  
  
 <span data-ttu-id="ee1b9-125">L’exemple suivant divise les valeurs de la colonne **ListPrice** par celles de la colonne **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="ee1b9-125">This example divides values in the **ListPrice** column by values in the **StandardCost** column.</span></span>  
  
```  
ListPrice / StandardCost  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee1b9-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee1b9-126">See Also</span></span>  
 <span data-ttu-id="ee1b9-127">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="ee1b9-127">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="ee1b9-128">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee1b9-128">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
