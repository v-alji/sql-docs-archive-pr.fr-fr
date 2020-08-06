---
title: SIGN (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- positive values [Integration Services]
- SIGN function
- negative values
ms.assetid: 1547db08-4329-4781-91c2-36898ed71b15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a34992b0029cd378274e38ce4e37fcd313d2b788
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701388"
---
# <a name="sign-ssis-expression"></a><span data-ttu-id="aab13-102">SIGN (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="aab13-102">SIGN (SSIS Expression)</span></span>
  <span data-ttu-id="aab13-103">Renvoie le nombre positif (+1), le nombre négatif (-1) ou zéro (0) selon le signe d'une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="aab13-103">Returns the positive (+1), negative (-1), or zero (0) sign of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aab13-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="aab13-104">Syntax</span></span>  
  
```  
  
SIGN(numeric_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="aab13-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="aab13-105">Arguments</span></span>  
 <span data-ttu-id="aab13-106">*numeric_expression*</span><span class="sxs-lookup"><span data-stu-id="aab13-106">*numeric_expression*</span></span>  
 <span data-ttu-id="aab13-107">Expression numérique signée valide.</span><span class="sxs-lookup"><span data-stu-id="aab13-107">Is a valid signed numeric expression.</span></span> <span data-ttu-id="aab13-108">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="aab13-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="aab13-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="aab13-109">Result Types</span></span>  
 <span data-ttu-id="aab13-110">DT_I4</span><span class="sxs-lookup"><span data-stu-id="aab13-110">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aab13-111">Notes</span><span class="sxs-lookup"><span data-stu-id="aab13-111">Remarks</span></span>  
 <span data-ttu-id="aab13-112">La fonction SIGN renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="aab13-112">SIGN returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="aab13-113">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="aab13-113">Expression Examples</span></span>  
 <span data-ttu-id="aab13-114">L'exemple suivant renvoie le signe d'un littéral numérique.</span><span class="sxs-lookup"><span data-stu-id="aab13-114">This example returns the sign of a numeric literal.</span></span> <span data-ttu-id="aab13-115">Le résultat obtenu est -1.</span><span class="sxs-lookup"><span data-stu-id="aab13-115">The return result is -1.</span></span>  
  
```  
SIGN(-123.45)  
```  
  
 <span data-ttu-id="aab13-116">L’exemple suivant retourne le signe du résultat de la soustraction de la colonne **StandardCost** de la colonne **DealerPrice** .</span><span class="sxs-lookup"><span data-stu-id="aab13-116">This example returns the sign of the result of subtracting the **StandardCost** column from the **DealerPrice** column.</span></span>  
  
```  
SIGN(DealerPrice - StandardCost)  
```  
  
## <a name="see-also"></a><span data-ttu-id="aab13-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aab13-117">See Also</span></span>  
 [<span data-ttu-id="aab13-118">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="aab13-118">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
