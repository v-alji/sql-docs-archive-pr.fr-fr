---
title: LEFT (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5634dbfb-740d-4c93-8fd5-2854cc741327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f21d134988414c7d8579d720877feec45383270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613018"
---
# <a name="left-ssis-expression"></a><span data-ttu-id="946d0-102">LEFT (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="946d0-102">LEFT (SSIS Expression)</span></span>
  <span data-ttu-id="946d0-103">Renvoie le nombre de caractères spécifié en commençant par la partie la plus à gauche d'une expression de caractères donnée.</span><span class="sxs-lookup"><span data-stu-id="946d0-103">Returns the specified number of characters from the leftmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="946d0-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="946d0-104">Syntax</span></span>  
  
```  
  
LEFT(character_expression,number)  
```  
  
## <a name="arguments"></a><span data-ttu-id="946d0-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="946d0-105">Arguments</span></span>  
 <span data-ttu-id="946d0-106">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="946d0-106">*character_expression*</span></span>  
 <span data-ttu-id="946d0-107">Expression de caractères à partir de laquelle doivent être extraits les caractères.</span><span class="sxs-lookup"><span data-stu-id="946d0-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="946d0-108">*number*</span><span class="sxs-lookup"><span data-stu-id="946d0-108">*number*</span></span>  
 <span data-ttu-id="946d0-109">Expression entière indiquant le nombre de caractères à renvoyer.</span><span class="sxs-lookup"><span data-stu-id="946d0-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="946d0-110">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="946d0-110">Result Types</span></span>  
 <span data-ttu-id="946d0-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="946d0-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="946d0-112">Notes</span><span class="sxs-lookup"><span data-stu-id="946d0-112">Remarks</span></span>  
 <span data-ttu-id="946d0-113">Si *number* est supérieur à la longueur de *character_expression*, la fonction retourne *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="946d0-113">If *number* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="946d0-114">Si l'argument *number* a pour valeur zéro, la fonction renvoie une chaîne de longueur nulle.</span><span class="sxs-lookup"><span data-stu-id="946d0-114">If *number* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="946d0-115">Si l'argument *number* est un nombre négatif, la fonction renvoie une erreur.</span><span class="sxs-lookup"><span data-stu-id="946d0-115">If *number* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="946d0-116">L'argument *number* peut accepter des variables et des colonnes.</span><span class="sxs-lookup"><span data-stu-id="946d0-116">The *number* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="946d0-117">La fonction LEFT fonctionne seulement avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="946d0-117">LEFT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="946d0-118">Un argument *character_expression* qui est un littéral de chaîne ou une colonne de données avec le type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que LEFT effectue son opération.</span><span class="sxs-lookup"><span data-stu-id="946d0-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LEFT performs its operation.</span></span> <span data-ttu-id="946d0-119">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="946d0-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="946d0-120">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="946d0-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="946d0-121">La fonction LEFT renvoie un résultat NULL si l'un des arguments est NULL.</span><span class="sxs-lookup"><span data-stu-id="946d0-121">LEFT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="946d0-122">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="946d0-122">Expression Examples</span></span>  
 <span data-ttu-id="946d0-123">L'exemple suivant utilise un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="946d0-123">The following example uses a string literal.</span></span> <span data-ttu-id="946d0-124">Le résultat obtenu est `"Mountain"`.</span><span class="sxs-lookup"><span data-stu-id="946d0-124">The return result is `"Mountain"`.</span></span>  
  
```  
LEFT("Mountain Bike", 8)  
```  
  
## <a name="see-also"></a><span data-ttu-id="946d0-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="946d0-125">See Also</span></span>  
 <span data-ttu-id="946d0-126">[RIGHT &#40;expression SSIS&#41;](right-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="946d0-126">[RIGHT &#40;SSIS Expression&#41;](right-ssis-expression.md) </span></span>  
 [<span data-ttu-id="946d0-127">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="946d0-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
