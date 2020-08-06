---
title: SQUARE (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQUARE
- square values
ms.assetid: cecf1bb2-3d55-40a6-9688-ed67bcc150b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 09955e708aae707a88aa7821d2a72651a3a44d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701370"
---
# <a name="square-ssis-expression"></a><span data-ttu-id="c6846-102">SQUARE (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="c6846-102">SQUARE (SSIS Expression)</span></span>
  <span data-ttu-id="c6846-103">Renvoie le carré d'une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="c6846-103">Returns the square of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6846-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c6846-104">Syntax</span></span>  
  
```  
  
SQUARE(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c6846-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="c6846-105">Arguments</span></span>  
 <span data-ttu-id="c6846-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="c6846-106">*numeric_expression*</span></span>  
 <span data-ttu-id="c6846-107">Expression numérique d'un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="c6846-107">Is a numeric expression of any numeric data type.</span></span> <span data-ttu-id="c6846-108">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c6846-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c6846-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="c6846-109">Result Types</span></span>  
 <span data-ttu-id="c6846-110">DT_R8</span><span class="sxs-lookup"><span data-stu-id="c6846-110">DT_R8</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6846-111">Notes</span><span class="sxs-lookup"><span data-stu-id="c6846-111">Remarks</span></span>  
 <span data-ttu-id="c6846-112">La fonction SQUARE renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="c6846-112">SQUARE returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="c6846-113">L'argument est converti vers le type de données DT_R8 avant le calcul du carré.</span><span class="sxs-lookup"><span data-stu-id="c6846-113">The argument is cast to the DT_R8 data type before the square operation.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c6846-114">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="c6846-114">Expression Examples</span></span>  
 <span data-ttu-id="c6846-115">Cet exemple renvoie le carré de 12.</span><span class="sxs-lookup"><span data-stu-id="c6846-115">This example returns the square of 12.</span></span> <span data-ttu-id="c6846-116">Le résultat retourné est 144.</span><span class="sxs-lookup"><span data-stu-id="c6846-116">The return result is 144.</span></span>  
  
```  
SQUARE(12)  
```  
  
 <span data-ttu-id="c6846-117">L'exemple suivant renvoie le carré du résultat de la soustraction des valeurs de deux colonnes.</span><span class="sxs-lookup"><span data-stu-id="c6846-117">This example returns the square of the result of subtracting values in two columns.</span></span> <span data-ttu-id="c6846-118">Si **Value1** contient 12 et **Value2** contient 4, la fonction SQUARE retourne 64.</span><span class="sxs-lookup"><span data-stu-id="c6846-118">If **Value1** contains 12 and **Value2** contains 4, the SQUARE function returns 64.</span></span>  
  
```  
SQUARE(Value1 - Value2)  
```  
  
 <span data-ttu-id="c6846-119">L'exemple suivant renvoie la longueur du troisième côté d'un triangle rectangle en appliquant la fonction SQUARE à deux variables, puis en calculant la racine carrée de leur somme.</span><span class="sxs-lookup"><span data-stu-id="c6846-119">This example returns the length of the third side of a right angle triangle by applying the SQUARE function to two variables and then calculating the square root of their sum.</span></span> <span data-ttu-id="c6846-120">Si la variable **Side1** a pour valeur 3 et que la variable **Side2** a pour valeur 4, la fonction SQRT renvoie 5.</span><span class="sxs-lookup"><span data-stu-id="c6846-120">If **Side1** contains 3 and **Side2** contains 4, the SQRT function returns 5.</span></span>  
  
```  
SQRT(SQUARE(@Side1) + SQUARE(@Side2))  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c6846-121">Dans les expressions, les noms de variables comportent toujours le préfixe \@.</span><span class="sxs-lookup"><span data-stu-id="c6846-121">In expressions, variable names always include the \@ prefix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6846-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6846-122">See Also</span></span>  
 [<span data-ttu-id="c6846-123">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c6846-123">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
