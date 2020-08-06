---
title: LTRIM (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- LTRIM function
ms.assetid: d082f42a-d7e7-49f5-a503-ac44ba630832
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 678d9d93eb1dcd7649d2085b651a08418bbcd6a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604648"
---
# <a name="ltrim-ssis-expression"></a><span data-ttu-id="22c6a-102">LTRIM (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="22c6a-102">LTRIM (SSIS Expression)</span></span>
  <span data-ttu-id="22c6a-103">Renvoie une chaîne de caractères après avoir supprimé les espaces de début.</span><span class="sxs-lookup"><span data-stu-id="22c6a-103">Returns a character expression after removing leading spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22c6a-104">La fonction LTRIM ne supprime pas les espaces blancs tels que les caractères de tabulation ou de saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="22c6a-104">LTRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="22c6a-105">Le codage Unicode founit des points de code pour divers types d'espaces, mais cette fonction ne reconnaît que le point de code Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="22c6a-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="22c6a-106">Ainsi, lorsque les chaînes du jeu de caractères codés sur deux octets (DBCS) sont converties en Unicode, elles peuvent comporter d'autres caractères d'espaces que 0x0020 si bien que la fonction ne peut pas les supprimer.</span><span class="sxs-lookup"><span data-stu-id="22c6a-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="22c6a-107">Pour éliminer tout type d'espace, utilisez par exemple la méthode de suppression des espaces de début (LTrim) de Microsoft Visual Basic .NET dans un script exécuté à partir du composant Script.</span><span class="sxs-lookup"><span data-stu-id="22c6a-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET LTrim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c6a-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="22c6a-108">Syntax</span></span>  
  
```  
  
LTRIM(character expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="22c6a-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="22c6a-109">Arguments</span></span>  
 <span data-ttu-id="22c6a-110">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="22c6a-110">*character_expression*</span></span>  
 <span data-ttu-id="22c6a-111">Expression de caractères dont les espaces doivent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="22c6a-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="22c6a-112">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="22c6a-112">Result Types</span></span>  
 <span data-ttu-id="22c6a-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="22c6a-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22c6a-114">Notes</span><span class="sxs-lookup"><span data-stu-id="22c6a-114">Remarks</span></span>  
 <span data-ttu-id="22c6a-115">La fonction LTRIM n'est opérationnelle qu'avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="22c6a-115">LTRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="22c6a-116">Un argument *expression_caractères* qui est un littéral de chaîne ou une colonne de données avec le type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que LTRIM effectue son opération.</span><span class="sxs-lookup"><span data-stu-id="22c6a-116">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LTRIM performs its operation.</span></span> <span data-ttu-id="22c6a-117">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="22c6a-117">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="22c6a-118">Pour plus d’informations, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md) et [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="22c6a-118">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="22c6a-119">La fonction LTRIM renvoie un résultat NULL si l'argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="22c6a-119">LTRIM returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="22c6a-120">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="22c6a-120">Expression Examples</span></span>  
 <span data-ttu-id="22c6a-121">L'exemple suivant supprime les espaces de début d'un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="22c6a-121">This example removes leading spaces from a string literal.</span></span> <span data-ttu-id="22c6a-122">Le résultat obtenu est «Hello».</span><span class="sxs-lookup"><span data-stu-id="22c6a-122">The return result is "Hello".</span></span>  
  
```  
LTRIM("    Hello")  
```  
  
 <span data-ttu-id="22c6a-123">L'exemple suivant supprime les espaces de début de la colonne **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="22c6a-123">This example removes leading spaces from the **FirstName** column.</span></span>  
  
```  
LTRIM(FirstName)  
```  
  
 <span data-ttu-id="22c6a-124">L'exemple suivant supprime les espaces de début de la variable **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="22c6a-124">This example removes leading spaces from the **FirstName** variable.</span></span>  
  
```  
LTRIM(@FirstName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="22c6a-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22c6a-125">See Also</span></span>  
 <span data-ttu-id="22c6a-126">[RTRIM &#40;expression SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="22c6a-126">[RTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="22c6a-127">[TRIM &#40;expression SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="22c6a-127">[TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="22c6a-128">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="22c6a-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
