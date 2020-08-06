---
title: SQRT (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQRT function
- square root of given expression
ms.assetid: 54a75389-c501-4e22-87b8-905f66d6a3a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9efa3f8da2e5280692aa65a25610211aba2fa40f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701376"
---
# <a name="sqrt-ssis-expression"></a><span data-ttu-id="3b29f-102">SQRT (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="3b29f-102">SQRT (SSIS Expression)</span></span>
  <span data-ttu-id="3b29f-103">Renvoie la racine carrée d'une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="3b29f-103">Returns the square root of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b29f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3b29f-104">Syntax</span></span>  
  
```  
  
SQRT(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="3b29f-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="3b29f-105">Arguments</span></span>  
 <span data-ttu-id="3b29f-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="3b29f-106">*numeric_expression*</span></span>  
 <span data-ttu-id="3b29f-107">Expression numérique d'un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="3b29f-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="3b29f-108">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="3b29f-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3b29f-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="3b29f-109">Result Types</span></span>  
 <span data-ttu-id="3b29f-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="3b29f-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b29f-111">Notes</span><span class="sxs-lookup"><span data-stu-id="3b29f-111">Remarks</span></span>  
 <span data-ttu-id="3b29f-112">La fonction SQRT renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="3b29f-112">SQRT returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="3b29f-113">Elle échoue si l'argument est une valeur négative.</span><span class="sxs-lookup"><span data-stu-id="3b29f-113">SQRT fails if the argument is a negative value.</span></span>  
  
 <span data-ttu-id="3b29f-114">L'argument est converti vers le type de données DT_R8 avant le calcul de la racine carrée.</span><span class="sxs-lookup"><span data-stu-id="3b29f-114">The argument is cast to the DT_R8 data type before the square root operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="3b29f-115">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="3b29f-115">Expression Examples</span></span>  
 <span data-ttu-id="3b29f-116">L'exemple suivant renvoie la racine carrée d'un littéral numérique.</span><span class="sxs-lookup"><span data-stu-id="3b29f-116">This example returns the square root of a numeric literal.</span></span> <span data-ttu-id="3b29f-117">Le résultat obtenu est 12.</span><span class="sxs-lookup"><span data-stu-id="3b29f-117">The return result is 12.</span></span>  
  
```  
SQRT(144)  
```  
  
 <span data-ttu-id="3b29f-118">L'exemple suivant renvoie la racine carrée d'une expression, en l'occurrence le résultat de la soustraction des valeurs des colonnes **Value1** et **Value2** .</span><span class="sxs-lookup"><span data-stu-id="3b29f-118">This example returns the square root of an expression, the result of subtracting values in the **Value1** and **Value2** columns.</span></span>  
  
```  
SQRT(Value1 - Value2)  
```  
  
 <span data-ttu-id="3b29f-119">L'exemple suivant renvoie la longueur du troisième côté d'un triangle rectangle en appliquant la fonction SQUARE à deux variables puis en calculant la racine carrée de leur somme.</span><span class="sxs-lookup"><span data-stu-id="3b29f-119">This example returns the length of the third side of a right triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="3b29f-120">Si la variable **Side1** a pour valeur 3 et que la variable **Side2** a pour valeur 4, la fonction SQRT renvoie 5.</span><span class="sxs-lookup"><span data-stu-id="3b29f-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3b29f-121">Dans les expressions, les noms de variables comportent toujours le préfixe \@.</span><span class="sxs-lookup"><span data-stu-id="3b29f-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b29f-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3b29f-122">See Also</span></span>  
 [<span data-ttu-id="3b29f-123">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3b29f-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
