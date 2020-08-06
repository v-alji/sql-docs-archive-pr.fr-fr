---
title: + (Ajouter) (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- + (add)
- add operator (+)
- adding expressions
ms.assetid: 44df4154-fed5-4e7f-9995-e703a0164f6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fe1e8f2118e6328582cb24abfd44eef5f3b15f79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611931"
---
# <a name="-add-ssis"></a><span data-ttu-id="82ec0-102">+ (Addition) (SSIS)</span><span class="sxs-lookup"><span data-stu-id="82ec0-102">+ (Add) (SSIS)</span></span>
  <span data-ttu-id="82ec0-103">Additionne deux expressions numériques.</span><span class="sxs-lookup"><span data-stu-id="82ec0-103">Adds two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82ec0-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="82ec0-104">Syntax</span></span>  
  
```  
  
numeric_expression1 + numeric_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="82ec0-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="82ec0-105">Arguments</span></span>  
 <span data-ttu-id="82ec0-106">*numeric_expression1, numeric_ expression2*</span><span class="sxs-lookup"><span data-stu-id="82ec0-106">*numeric_expression1, numeric_ expression2*</span></span>  
 <span data-ttu-id="82ec0-107">Toute expression valide d'un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="82ec0-107">Is any valid expression of a numeric data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="82ec0-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="82ec0-108">Result Types</span></span>  
 <span data-ttu-id="82ec0-109">Déterminés par les types de données des deux arguments.</span><span class="sxs-lookup"><span data-stu-id="82ec0-109">Determined by data types of the two arguments.</span></span> <span data-ttu-id="82ec0-110">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="82ec0-110">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82ec0-111">Notes</span><span class="sxs-lookup"><span data-stu-id="82ec0-111">Remarks</span></span>  
 <span data-ttu-id="82ec0-112">Si l'un des opérandes est NULL, le résultat est NULL.</span><span class="sxs-lookup"><span data-stu-id="82ec0-112">If either operand is null, the result is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="82ec0-113">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="82ec0-113">Expression Examples</span></span>  
 <span data-ttu-id="82ec0-114">L'exemple suivant additionne des littéraux numériques.</span><span class="sxs-lookup"><span data-stu-id="82ec0-114">This example adds numeric literals.</span></span>  
  
```  
5 + 6.09 + 7.0  
```  
  
 <span data-ttu-id="82ec0-115">L'exemple suivant additionne les valeurs des colonnes **VacationHours** et **SickLeaveHours** .</span><span class="sxs-lookup"><span data-stu-id="82ec0-115">This example adds values in the **VacationHours** and **SickLeaveHours** columns.</span></span>  
  
```  
VacationHours + SickLeaveHours  
```  
  
 <span data-ttu-id="82ec0-116">L'exemple suivant ajoute une valeur calculée à la colonne **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="82ec0-116">This example adds a calculated value to the **StandardCost** column.</span></span> <span data-ttu-id="82ec0-117">La variable **Profit%** doit figurer entre crochets car elle contient le caractère « % ».</span><span class="sxs-lookup"><span data-stu-id="82ec0-117">The variable **Profit%** must be enclosed in brackets because the name includes the % character.</span></span> <span data-ttu-id="82ec0-118">Pour plus d’informations, consultez [Identificateurs &#40;SSIS&#41;](identifiers-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="82ec0-118">For more information, see [Identifiers &#40;SSIS&#41;](identifiers-ssis.md).</span></span>  
  
```  
StandardCost + (StandardCost * @[Profit%])  
```  
  
## <a name="see-also"></a><span data-ttu-id="82ec0-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82ec0-119">See Also</span></span>  
 <span data-ttu-id="82ec0-120">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="82ec0-120">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="82ec0-121">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="82ec0-121">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
