---
title: GETDATE (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- current date
- GETDATE function
- dates [Integration Services], GETDATE
ms.assetid: 6d20ec93-3244-4d63-baf6-70eff7bd598c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0acb384a8c3c3dfdae55c7172f341f9e32765e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604052"
---
# <a name="getdate-ssis-expression"></a><span data-ttu-id="1ca01-102">GETDATE (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="1ca01-102">GETDATE (SSIS Expression)</span></span>
  <span data-ttu-id="1ca01-103">Renvoie la date actuelle du système dans un format DT_DBTIMESTAMP.</span><span class="sxs-lookup"><span data-stu-id="1ca01-103">Returns the current date of the system in a DT_DBTIMESTAMP format.</span></span> <span data-ttu-id="1ca01-104">La fonction GETDATE ne prend aucun argument.</span><span class="sxs-lookup"><span data-stu-id="1ca01-104">The GETDATE function takes no arguments.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ca01-105">La fonction GETDATE retourne un résultat d'une longueur de 29 caractères.</span><span class="sxs-lookup"><span data-stu-id="1ca01-105">The length of the return result from the GETDATE function is 29 characters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ca01-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1ca01-106">Syntax</span></span>  
  
```  
  
GETDATE()  
```  
  
## <a name="arguments"></a><span data-ttu-id="1ca01-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="1ca01-107">Arguments</span></span>  
 <span data-ttu-id="1ca01-108">None</span><span class="sxs-lookup"><span data-stu-id="1ca01-108">None</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1ca01-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="1ca01-109">Result Types</span></span>  
 <span data-ttu-id="1ca01-110">DT_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="1ca01-110">DT_DBTIMESTAMP</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="1ca01-111">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="1ca01-111">Expression Examples</span></span>  
 <span data-ttu-id="1ca01-112">L'exemple suivant renvoie l'année de la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="1ca01-112">This example returns the year of the current date.</span></span>  
  
```  
DATEPART("year",GETDATE())  
```  
  
 <span data-ttu-id="1ca01-113">L’exemple suivant renvoie le nombre de jours entre une date de la colonne **ModifiedDate** et la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="1ca01-113">This example returns the number of days between a date in the **ModifiedDate** column and the current date.</span></span>  
  
```  
DATEDIFF("dd",ModifiedDate,GETDATE())  
```  
  
 <span data-ttu-id="1ca01-114">L'exemple suivant ajoute trois mois à la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="1ca01-114">This example adds three months to the current date.</span></span>  
  
```  
DATEADD("Month",3,GETDATE())  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ca01-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ca01-115">See Also</span></span>  
 <span data-ttu-id="1ca01-116">[GETUTCDATE &#40;expression SSIS&#41;](getutcdate-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="1ca01-116">[GETUTCDATE &#40;SSIS Expression&#41;](getutcdate-ssis-expression.md) </span></span>  
 [<span data-ttu-id="1ca01-117">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1ca01-117">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
