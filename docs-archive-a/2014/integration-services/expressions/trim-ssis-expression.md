---
title: TRIM (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- TRIM function
- trailing blanks
ms.assetid: 7dd9081d-a3d4-483a-bf7e-bf2bd7692d39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 42cef8a816f399e39ac99061f34c394156bde45f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701328"
---
# <a name="trim-ssis-expression"></a><span data-ttu-id="2af4b-102">TRIM (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="2af4b-102">TRIM (SSIS Expression)</span></span>
  <span data-ttu-id="2af4b-103">Renvoie une chaîne de type caractère après la suppression des espaces de début et de fin.</span><span class="sxs-lookup"><span data-stu-id="2af4b-103">Returns a character expression after removing leading and trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2af4b-104">La fonction TRIM ne supprime pas les espaces blancs tels que les caractères de tabulation ou de saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="2af4b-104">TRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="2af4b-105">Le codage Unicode founit des points de code pour divers types d'espaces, mais cette fonction ne reconnaît que le point de code Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="2af4b-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="2af4b-106">Ainsi, lorsque les chaînes du jeu de caractères codés sur deux octets (DBCS) sont converties en Unicode, elles peuvent comporter d'autres caractères d'espaces que 0x0020 si bien que la fonction ne peut pas les supprimer.</span><span class="sxs-lookup"><span data-stu-id="2af4b-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="2af4b-107">Pour éliminer tout type d'espace, utilisez par exemple la méthode de suppression des espaces (Trim) de Microsoft Visual Basic .NET dans un script exécuté à partir du composant Script.</span><span class="sxs-lookup"><span data-stu-id="2af4b-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET Trim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af4b-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2af4b-108">Syntax</span></span>  
  
```  
  
TRIM(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="2af4b-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="2af4b-109">Arguments</span></span>  
 <span data-ttu-id="2af4b-110">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="2af4b-110">*character_expression*</span></span>  
 <span data-ttu-id="2af4b-111">Expression de caractères dont les espaces doivent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="2af4b-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2af4b-112">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="2af4b-112">Result Types</span></span>  
 <span data-ttu-id="2af4b-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="2af4b-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2af4b-114">Notes</span><span class="sxs-lookup"><span data-stu-id="2af4b-114">Remarks</span></span>  
 <span data-ttu-id="2af4b-115">La fonction TRIM renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="2af4b-115">TRIM returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="2af4b-116">La fonction TRIM fonctionne seulement avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="2af4b-116">TRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="2af4b-117">Un argument *character_expression* qui est un littéral de chaîne ou une colonne de données avec le type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que TRIM effectue son opération.</span><span class="sxs-lookup"><span data-stu-id="2af4b-117">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TRIM performs its operation.</span></span> <span data-ttu-id="2af4b-118">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="2af4b-118">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="2af4b-119">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2af4b-119">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2af4b-120">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="2af4b-120">Expression Examples</span></span>  
 <span data-ttu-id="2af4b-121">L'exemple suivant supprime les espaces de début et de fin d'un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="2af4b-121">This example removes leading and trailing spaces from a string literal.</span></span> <span data-ttu-id="2af4b-122">Le résultat obtenu est «New York».</span><span class="sxs-lookup"><span data-stu-id="2af4b-122">The return result is "New York".</span></span>  
  
```  
TRIM("   New York   ")  
```  
  
 <span data-ttu-id="2af4b-123">L'exemple suivant supprime les espaces de début et de fin de la concaténation des colonnes **FirstName** et **LastName** .</span><span class="sxs-lookup"><span data-stu-id="2af4b-123">This example removes leading and trailing spaces from the result of concatenating the **FirstName** and **LastName** columns.</span></span> <span data-ttu-id="2af4b-124">La chaîne vide entre les colonnes **FirstName** et **LastName** n'est pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="2af4b-124">The empty string between **FirstName** and **LastName** is not removed.</span></span>  
  
```  
TRIM(FirstName + " "+ LastName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="2af4b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2af4b-125">See Also</span></span>  
 <span data-ttu-id="2af4b-126">[LTRIM &#40;expression SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="2af4b-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="2af4b-127">[RTRIM &#40;expression SSIS&#41;](rtrim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="2af4b-127">[RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="2af4b-128">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2af4b-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
