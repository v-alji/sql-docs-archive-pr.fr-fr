---
title: ISNULL (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- null values [Integration Services]
- ISNULL function
ms.assetid: 88dbf49e-1307-4dda-b9db-ff1632053550
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 51eda21b5c9b85c5f9cfd613d0d92df9729fe620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701430"
---
# <a name="isnull-ssis-expression"></a><span data-ttu-id="2d9fc-102">ISNULL (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="2d9fc-102">ISNULL (SSIS Expression)</span></span>
  <span data-ttu-id="2d9fc-103">Renvoie une valeur booléenne basée sur le test du caractère NULL d'une expression.</span><span class="sxs-lookup"><span data-stu-id="2d9fc-103">Returns a Boolean result based on whether an expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d9fc-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2d9fc-104">Syntax</span></span>  
  
```  
  
ISNULL(expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="2d9fc-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="2d9fc-105">Arguments</span></span>  
 <span data-ttu-id="2d9fc-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="2d9fc-106">*expression*</span></span>  
 <span data-ttu-id="2d9fc-107">Expression valide d'un type de données quelconque.</span><span class="sxs-lookup"><span data-stu-id="2d9fc-107">Is a valid expression of any data type.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2d9fc-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="2d9fc-108">Result Types</span></span>  
 <span data-ttu-id="2d9fc-109">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="2d9fc-109">DT_BOOL</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="2d9fc-110">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="2d9fc-110">Expression Examples</span></span>  
 <span data-ttu-id="2d9fc-111">L'exemple suivant renvoie TRUE si la colonne **DiscontinuedDate** contient une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="2d9fc-111">This example returns TRUE if the **DiscontinuedDate** column contains a null value.</span></span>  
  
```  
ISNULL(DiscontinuedDate)  
```  
  
 <span data-ttu-id="2d9fc-112">L'exemple suivant renvoie « Unknown last name » si la valeur de la colonne **LastName** est NULL, sinon il renvoie la valeur de **LastName**.</span><span class="sxs-lookup"><span data-stu-id="2d9fc-112">This example returns "Unknown last name" if the value in the **LastName** column is null, otherwise it returns the value in **LastName**.</span></span>  
  
```  
ISNULL(LastName)? "Unknown last name":LastName  
```  
  
 <span data-ttu-id="2d9fc-113">L'exemple suivant renvoie toujours TRUE si la colonne **DaysToManufacture** est NULL, quelle que soit la valeur de la variable **AddDays**.</span><span class="sxs-lookup"><span data-stu-id="2d9fc-113">This example always returns TRUE if the **DaysToManufacture** column is null, regardless of the value of the variable **AddDays**.</span></span>  
  
```  
ISNULL(DaysToManufacture + @AddDays)  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d9fc-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d9fc-114">See Also</span></span>  
 <span data-ttu-id="2d9fc-115">[Fonctions &#40;expression SSIS&#41;](functions-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="2d9fc-115">[Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md) </span></span>  
 [<span data-ttu-id="2d9fc-116">COALESCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2d9fc-116">COALESCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/coalesce-transact-sql)  
  
  
