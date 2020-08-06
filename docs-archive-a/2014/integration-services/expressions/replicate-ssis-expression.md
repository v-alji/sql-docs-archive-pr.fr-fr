---
title: REPLICATE (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REPLICATE function
ms.assetid: e7a37b93-6d1d-42d5-9a65-de1790abf6a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9502df5bc20c6ad85f1f98fb57fe6b3cf431cc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701412"
---
# <a name="replicate-ssis-expression"></a><span data-ttu-id="76387-102">REPLICATE (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="76387-102">REPLICATE (SSIS Expression)</span></span>
  <span data-ttu-id="76387-103">Renvoie une expression de caractères qui est répliquée plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="76387-103">Returns a character expression that is replicated a number of times.</span></span> <span data-ttu-id="76387-104">L'argument *times* doit correspondre à un nombre entier.</span><span class="sxs-lookup"><span data-stu-id="76387-104">The *times* argument must evaluate to an integer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76387-105">La fonction REPLICATE utilise habituellement des chaînes longues, elle est donc plus exposée à la limitation fixée à 4000 caractères sur la longueur d'expression.</span><span class="sxs-lookup"><span data-stu-id="76387-105">The REPLICATE function frequently uses long strings, and therefore is more likely to incur the 4000-character limit on expression length.</span></span> <span data-ttu-id="76387-106">Si le résultat de l'évaluation d'une expression donne le type de données Integration Services DT_WSTR ou DT_STR, cette expression sera réduite à 4000 caractères.</span><span class="sxs-lookup"><span data-stu-id="76387-106">If the evaluation result of an expression has the Integration Services data type DT_WSTR or DT_STR, the expression will be truncated at 4000 characters.</span></span> <span data-ttu-id="76387-107">Si le type du résultat d'une sous-expression est DT_STR ou DT_WSTR, cette sous-expression sera également tronquée à 4000 caractères, peu importe le type de résultat obtenu dans l'expression générale.</span><span class="sxs-lookup"><span data-stu-id="76387-107">If the result type of a sub-expression is DT_STR or DT_WSTR, that sub-expression likewise will be truncated to 4000 characters, regardless of the overall expression result type.</span></span> <span data-ttu-id="76387-108">Les conséquences de la troncation peuvent être gérées naturellement ou être à l'origine d'un avertissement ou d'un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="76387-108">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="76387-109">Pour plus d’informations, consultez [Syntaxe &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="76387-109">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76387-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="76387-110">Syntax</span></span>  
  
```  
  
REPLICATE(character_expression,times)  
```  
  
## <a name="arguments"></a><span data-ttu-id="76387-111">Arguments</span><span class="sxs-lookup"><span data-stu-id="76387-111">Arguments</span></span>  
 <span data-ttu-id="76387-112">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="76387-112">*character_expression*</span></span>  
 <span data-ttu-id="76387-113">Expression de caractères à répliquer.</span><span class="sxs-lookup"><span data-stu-id="76387-113">Is a character expression to replicate.</span></span>  
  
 <span data-ttu-id="76387-114">*times*</span><span class="sxs-lookup"><span data-stu-id="76387-114">*times*</span></span>  
 <span data-ttu-id="76387-115">Expression entière spécifiant le nombre de réplications de l’argument *character_expression* .</span><span class="sxs-lookup"><span data-stu-id="76387-115">Is an integer expression that specifies the number of times *character_expression* is replicated.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="76387-116">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="76387-116">Result Types</span></span>  
 <span data-ttu-id="76387-117">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="76387-117">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76387-118">Notes</span><span class="sxs-lookup"><span data-stu-id="76387-118">Remarks</span></span>  
 <span data-ttu-id="76387-119">Si l’argument *times* a pour valeur zéro, la fonction retourne une chaîne de longueur nulle.</span><span class="sxs-lookup"><span data-stu-id="76387-119">If *times* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="76387-120">Si l'argument *times* est un nombre négatif, la fonction renvoie une erreur.</span><span class="sxs-lookup"><span data-stu-id="76387-120">If *times* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="76387-121">L'argument *times* peut également utiliser des variables et des colonnes.</span><span class="sxs-lookup"><span data-stu-id="76387-121">The *times* argument can also use variables and columns.</span></span>  
  
 <span data-ttu-id="76387-122">La fonction REPLICATE est opérationnelle seulement avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="76387-122">REPLICATE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="76387-123">Un argument *character_expression* représentant un littéral de chaîne ou une colonne de données du type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que la fonction REPLICATE ne soit exécutée.</span><span class="sxs-lookup"><span data-stu-id="76387-123">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before REPLICATE performs its operation.</span></span> <span data-ttu-id="76387-124">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="76387-124">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="76387-125">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="76387-125">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="76387-126">La fonction REPLICATE renvoie un résultat NULL si l'un des arguments est NULL.</span><span class="sxs-lookup"><span data-stu-id="76387-126">REPLICATE returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="76387-127">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="76387-127">Expression Examples</span></span>  
 <span data-ttu-id="76387-128">L'exemple suivant réplique un littéral de chaîne trois fois.</span><span class="sxs-lookup"><span data-stu-id="76387-128">This example replicates a string literal three times.</span></span> <span data-ttu-id="76387-129">Le résultat obtenu est « Mountain BikeMountain BikeMountain Bike ».</span><span class="sxs-lookup"><span data-stu-id="76387-129">The return result is "Mountain BikeMountain BikeMountain Bike".</span></span>  
  
```  
REPLICATE("Mountain Bike", 3)  
```  
  
 <span data-ttu-id="76387-130">L'exemple suivant réplique les valeurs de la colonne **Name** un nombre de fois égal à la valeur de la variable **Times** .</span><span class="sxs-lookup"><span data-stu-id="76387-130">This example replicates values in the **Name** column by the value in the **Times** variable.</span></span> <span data-ttu-id="76387-131">Si la variable **Times** a pour valeur 3 et que la valeur de la colonne **Name** est « Tout-terrain », le résultat obtenu est « Tout-terrainTout-terrainTout-terrain ».</span><span class="sxs-lookup"><span data-stu-id="76387-131">If **Times** is 3 and **Name** is Touring Front Wheel, the return result is Touring Front WheelTouring Front WheelTouring Front Wheel.</span></span>  
  
```  
REPLICATE(Name, @Times)  
```  
  
 <span data-ttu-id="76387-132">L'exemple suivant réplique la valeur de la variable **Name** un nombre de fois égal à la valeur de la colonne **Times** .</span><span class="sxs-lookup"><span data-stu-id="76387-132">This example replicates the value in the **Name** variable by the value in the **Times** column.</span></span> <span data-ttu-id="76387-133">La valeur**Times** a un type de données non-entier et l’expression comprend une conversion explicite vers un type de données entier.</span><span class="sxs-lookup"><span data-stu-id="76387-133">**Times** has a non-integer data type and the expression includes an explicit cast to an integer data type.</span></span> <span data-ttu-id="76387-134">Si la variable **Name** contient « Helmet » et que la colonne **Times** a pour valeur 2, le résultat obtenu est « HelmetHelmet ».</span><span class="sxs-lookup"><span data-stu-id="76387-134">If **Name** contains Helmet and **Times** is 2, the return result is "HelmetHelmet".</span></span>  
  
```  
REPLICATE(@Name, (DT_I4(Times))  
```  
  
## <a name="see-also"></a><span data-ttu-id="76387-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76387-135">See Also</span></span>  
 [<span data-ttu-id="76387-136">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="76387-136">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
