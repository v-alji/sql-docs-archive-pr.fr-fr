---
title: GETUTCDATE (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], GETUTCDATE
- current date
- UTC time
- GETUTCDATE function
ms.assetid: 2282339c-c24f-493e-8e66-181ea8af5ad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f157ab5641e521a42cb3c96c96446b31de5dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701466"
---
# <a name="getutcdate-ssis-expression"></a><span data-ttu-id="1a7de-102">GETUTCDATE (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="1a7de-102">GETUTCDATE (SSIS Expression)</span></span>
  <span data-ttu-id="1a7de-103">Renvoie la date actuelle du système en temps UTC (Universal Time Coordinate ou Greenwich Mean Time) au format DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="1a7de-103">Returns the current date of the system in UTC time (Universal Time Coordinate or Greenwich Mean Time) using a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="1a7de-104">La fonction GETUTCDATE ne comprend aucun argument.</span><span class="sxs-lookup"><span data-stu-id="1a7de-104">The GETUTCDATE function takes no arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a7de-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1a7de-105">Syntax</span></span>  
  
```  
  
GETUTCDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="1a7de-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="1a7de-106">Arguments</span></span>  
 <span data-ttu-id="1a7de-107">None</span><span class="sxs-lookup"><span data-stu-id="1a7de-107">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1a7de-108">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="1a7de-108">Result Types</span></span>  
 <span data-ttu-id="1a7de-109">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="1a7de-109">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="1a7de-110">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="1a7de-110">Expression Examples</span></span>  
 <span data-ttu-id="1a7de-111">L'exemple suivant renvoie l'année de la date actuelle en temps UTC.</span><span class="sxs-lookup"><span data-stu-id="1a7de-111">This example returns the year of the current date in UTC time.</span></span>  
  
```  
DATEPART("year",GETUTCDATE())  
```  
  
 <span data-ttu-id="1a7de-112">L’exemple suivant retourne le nombre de jours entre une date de la colonne **ModifiedDate** et la date UTC actuelle.</span><span class="sxs-lookup"><span data-stu-id="1a7de-112">This example returns the number of days between a date in the **ModifiedDate** column and the current UTC date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETUTCDATE())  
```  
  
 <span data-ttu-id="1a7de-113">L'exemple suivant ajoute trois mois à la date UTC actuelle.</span><span class="sxs-lookup"><span data-stu-id="1a7de-113">This example adds three months to the current UTC date.</span></span>  
  
```  
DATEADD("Month",3,GETUTCDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a7de-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a7de-114">See Also</span></span>  
 <span data-ttu-id="1a7de-115">[GETDATE &#40;expression SSIS&#41;](getdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1a7de-115">[GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="1a7de-116">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1a7de-116">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
