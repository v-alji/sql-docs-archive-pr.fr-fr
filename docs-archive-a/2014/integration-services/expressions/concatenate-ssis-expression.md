---
title: + (Concaténer) (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- concatenation [Integration Services]
- + (concatenate operator)
- concatenate operator (+)
ms.assetid: 0fed6334-7a4f-42dc-a611-191fcaa0e443
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1c01f82a50962f42862db836171b0ad683c97453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701484"
---
# <a name="-concatenate-ssis-expression"></a><span data-ttu-id="c9a4d-102">+ (Concaténer) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="c9a4d-102">+ (Concatenate) (SSIS Expression)</span></span>
  <span data-ttu-id="c9a4d-103">Concatène deux expressions en une seule.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-103">Concatenates two expressions into one expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a4d-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c9a4d-104">Syntax</span></span>  
  
```  
  
character_expression1 + character_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9a4d-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="c9a4d-105">Arguments</span></span>  
 <span data-ttu-id="c9a4d-106">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="c9a4d-106">*expression1, expression2*</span></span>  
 <span data-ttu-id="c9a4d-107">Toute expression valide de type de données DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-107">Is any valid DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c9a4d-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="c9a4d-108">Result Types</span></span>  
 <span data-ttu-id="c9a4d-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="c9a4d-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9a4d-110">Notes</span><span class="sxs-lookup"><span data-stu-id="c9a4d-110">Remarks</span></span>  
 <span data-ttu-id="c9a4d-111">L'expression peut utiliser l'un des types de données DT_STR et DT_WSTR (ou les deux).</span><span class="sxs-lookup"><span data-stu-id="c9a4d-111">The expression can use either or both of the DT_STR and DT_WSTR data types.</span></span>  
  
 <span data-ttu-id="c9a4d-112">La concaténation des types de données DT_STR et DT_WSTR renvoie un résultat de type DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-112">The concatenation of the DT_STR and DT_WSTR data types returns a result of the DT_WSTR type.</span></span> <span data-ttu-id="c9a4d-113">La longueur de la chaîne est la somme des longueurs des chaînes d'origine exprimée en caractères.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-113">The length of the string is the sum of the lengths of the original strings expressed in characters.</span></span>  
  
 <span data-ttu-id="c9a4d-114">Seules les données des types de données chaîne DT_STR et DT_WSTR ou de types de données BLOB (Binary Large Object Block) DT_TEXT, DT_NTEXT et DT_IMAGE peuvent être concaténées.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-114">Only data with the string data types DT_STR and DT_WSTR or the Binary Large Object Block (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE can be concatenated.</span></span> <span data-ttu-id="c9a4d-115">Les autres types de données doivent être explicitement convertis dans l'un de ces types de données pour que la concaténation puisse être effectuée.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-115">Other data types must be explicitly converted to one of these data types before concatenation occurs.</span></span> <span data-ttu-id="c9a4d-116">Pour plus d’informations sur les conversions valides entre les types de données, consultez [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c9a4d-116">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="c9a4d-117">Les deux expressions doivent être du même type de données, ou l'une des expressions doit être implicitement convertible vers le type de données de l'autre expression.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-117">Both expressions must be of the same data type, or one expression must be implicitly convertible to the data type of the other expression.</span></span> <span data-ttu-id="c9a4d-118">Par exemple, si la chaîne « La date de commande est » et la colonne **OrderDate** sont concaténées, les valeurs de la colonne **OrderDate** sont implicitement converties vers un type de données string.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-118">For example, if the string "Order date is " and the column **OrderDate** are concatenated, the values in **OrderDate** are implicitly converted to a string data type.</span></span> <span data-ttu-id="c9a4d-119">Deux valeurs numériques ne peuvent être concaténées que si elles sont toutes deux explicitement converties en un type de données chaîne.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-119">To concatenate two numeric values, both numeric values must be explicitly cast to a string data type.</span></span>  
  
 <span data-ttu-id="c9a4d-120">Une concaténation ne peut utiliser qu'un seul type de données BLOB : DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-120">A concatenation can use only one BLOB data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="c9a4d-121">Si l'un des éléments est NULL, le résultat est NULL.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-121">If either element is null, the result is null.</span></span>  
  
 <span data-ttu-id="c9a4d-122">Les littéraux de chaîne doivent être placés entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-122">String literals must be enclosed in quotation marks.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c9a4d-123">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="c9a4d-123">Expression Examples</span></span>  
 <span data-ttu-id="c9a4d-124">L'exemple suivant concatène les valeurs des colonnes **FirstName** et **LastName** en les séparant par un espace.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-124">This example concatenates the values in the **FirstName** and **LastName** columns and inserts a space between them.</span></span>  
  
```  
FirstName + ' ' + LastName  
```  
  
 <span data-ttu-id="c9a4d-125">L’exemple suivant concatène les variables **ZIPCode** et **ZIPCode+4**.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-125">This example concatenates the variables **ZIPCode** and **ZIPCode+4**.</span></span> <span data-ttu-id="c9a4d-126">Les deux variables sont de type de données chaîne.</span><span class="sxs-lookup"><span data-stu-id="c9a4d-126">Both variables have a string data type.</span></span> <span data-ttu-id="c9a4d-127">La variable**ZIPCode+4** doit figurer entre crochets car elle contient le caractère « + ».</span><span class="sxs-lookup"><span data-stu-id="c9a4d-127">**ZIPCode+4** must be enclosed in brackets because the variable name includes the + character.</span></span>  
  
```  
@ZIPCcode + "-" + @[ZipCode+4]  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9a4d-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9a4d-128">See Also</span></span>  
 <span data-ttu-id="c9a4d-129">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="c9a4d-129">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="c9a4d-130">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c9a4d-130">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
