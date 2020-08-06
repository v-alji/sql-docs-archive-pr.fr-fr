---
title: REPLACE (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- replacing string expression
- REPLACE function
ms.assetid: a6837043-ea70-4c6a-9c7a-6868b02b2adc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e483ba6c9c72cb777f2955929a717c6c2e17a8c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701423"
---
# <a name="replace-ssis-expression"></a><span data-ttu-id="e52c9-102">REPLACE (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="e52c9-102">REPLACE (SSIS Expression)</span></span>
  <span data-ttu-id="e52c9-103">Renvoie une expression de caractères après le remplacement d'une chaîne de caractères située dans l'expression par une autre chaîne de caractères ou une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="e52c9-103">Returns a character expression after replacing a character string within the expression with either a different character string or an empty string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e52c9-104">La fonction REPLACE utilise habituellement des chaînes longues.</span><span class="sxs-lookup"><span data-stu-id="e52c9-104">The REPLACE function frequently uses long strings.</span></span> <span data-ttu-id="e52c9-105">Les conséquences de la troncation peuvent être gérées naturellement ou être à l'origine d'un avertissement ou d'un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e52c9-105">The consequences of truncation can be handled gracefully or cause a warning or an error.</span></span> <span data-ttu-id="e52c9-106">Pour plus d’informations, consultez [Syntaxe &#40;SSIS&#41;](syntax-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="e52c9-106">For more information, see [Syntax &#40;SSIS&#41;](syntax-ssis.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e52c9-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e52c9-107">Syntax</span></span>  
  
```  
  
REPLACE(character_expression,searchstring,replacementstring)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e52c9-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="e52c9-108">Arguments</span></span>  
 <span data-ttu-id="e52c9-109">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="e52c9-109">*character_expression*</span></span>  
 <span data-ttu-id="e52c9-110">Expression de caractères valide où la fonction va effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="e52c9-110">Is a valid character expression that the function searches.</span></span>  
  
 <span data-ttu-id="e52c9-111">*searchstring*</span><span class="sxs-lookup"><span data-stu-id="e52c9-111">*searchstring*</span></span>  
 <span data-ttu-id="e52c9-112">Expression de caractères valide recherchée par la fonction.</span><span class="sxs-lookup"><span data-stu-id="e52c9-112">Is a valid character expression that the function attempts to locate.</span></span>  
  
 <span data-ttu-id="e52c9-113">*replacementstring*</span><span class="sxs-lookup"><span data-stu-id="e52c9-113">*replacementstring*</span></span>  
 <span data-ttu-id="e52c9-114">Expression de caractères valide qui est l'expression de remplacement.</span><span class="sxs-lookup"><span data-stu-id="e52c9-114">Is a valid character expression that is the replacement expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e52c9-115">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="e52c9-115">Result Types</span></span>  
 <span data-ttu-id="e52c9-116">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="e52c9-116">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e52c9-117">Notes</span><span class="sxs-lookup"><span data-stu-id="e52c9-117">Remarks</span></span>  
 <span data-ttu-id="e52c9-118">La longueur de *searchstring* ne doit pas être égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="e52c9-118">The length of *searchstring* must not be zero.</span></span>  
  
 <span data-ttu-id="e52c9-119">La longueur de *replacementstring* peut être égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="e52c9-119">The length of *replacementstring* may be zero.</span></span>  
  
 <span data-ttu-id="e52c9-120">Les arguments *searchstring* et *replacementstring* peuvent utiliser des variables et des colonnes.</span><span class="sxs-lookup"><span data-stu-id="e52c9-120">The *searchstring* and *replacementstring* arguments can use variables and columns.</span></span>  
  
 <span data-ttu-id="e52c9-121">La fonction REPLACE est opérationnelle seulement avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="e52c9-121">REPLACE works only with the DT_WSTR data type.</span></span> <span data-ttu-id="e52c9-122">Les arguments*character_expression1, character_expression2* et *character_expression3* qui représentent des littéraux de chaîne ou des colonnes de données du type de données DT_STR sont implicitement convertis dans le type de données DT_WSTR avant que la fonction REPLACE soit exécutée.</span><span class="sxs-lookup"><span data-stu-id="e52c9-122">*character_expression1, character_expression2,* and *character_expression3* arguments that are string literals or data columns with the DT_STR data type are implicitly cast to the DT_WSTR data type before REPLACE performs its operation.</span></span> <span data-ttu-id="e52c9-123">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="e52c9-123">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="e52c9-124">Pour plus d’informations, consultez [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e52c9-124">For more information, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="e52c9-125">La fonction REPLACE renvoie un résultat NULL si un argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="e52c9-125">REPLACE returns a null result if any argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="e52c9-126">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="e52c9-126">Expression Examples</span></span>  
 <span data-ttu-id="e52c9-127">L'exemple suivant utilise un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="e52c9-127">This example uses a string literal.</span></span> <span data-ttu-id="e52c9-128">Le résultat obtenu est « All Terrain Bike ».</span><span class="sxs-lookup"><span data-stu-id="e52c9-128">The return result is "All Terrain Bike".</span></span>  
  
```  
REPLACE("Mountain Bike", "Mountain","All Terrain")  
```  
  
 <span data-ttu-id="e52c9-129">L’exemple suivant supprime la chaîne « Bike » de la colonne **Product** .</span><span class="sxs-lookup"><span data-stu-id="e52c9-129">This example removes the string "Bike" from the **Product** column.</span></span>  
  
```  
REPLACE(Product, "Bike","")  
```  
  
 <span data-ttu-id="e52c9-130">L’exemple suivant remplace des valeurs dans la colonne **DaysToManufacture** .</span><span class="sxs-lookup"><span data-stu-id="e52c9-130">This example replaces values in the **DaysToManufacture** column.</span></span> <span data-ttu-id="e52c9-131">La colonne a un type de données integer et l’expression comprend la conversion de **DaysToManufacture** vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="e52c9-131">The column has an integer data type and the expression includes casting **DaysToManufacture** to the DT_WSTR data type.</span></span>  
  
```  
REPLACE((DT_WSTR,8)DaysToManufacture,"6","5")  
```  
  
## <a name="see-also"></a><span data-ttu-id="e52c9-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e52c9-132">See Also</span></span>  
 <span data-ttu-id="e52c9-133">[SUBSTRING &#40;expression SSIS&#41;](substring-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="e52c9-133">[SUBSTRING &#40;SSIS Expression&#41;](substring-ssis-expression.md) </span></span>  
 [<span data-ttu-id="e52c9-134">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e52c9-134">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
