---
title: Points d'arrêt Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoints
ms.assetid: c234430f-bd94-4d0d-9e74-2bf11681fa50
author: rothja
ms.author: jroth
ms.openlocfilehash: c9595c9627ac3cc445b1193881c2d5b772e9b71d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612751"
---
# <a name="transact-sql-breakpoints"></a><span data-ttu-id="18b71-102">Points d'arrêt Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18b71-102">Transact-SQL Breakpoints</span></span>
  <span data-ttu-id="18b71-103">Les points d'arrêt spécifient que le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] suspend l'exécution à une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] spécifique ; vous pouvez ensuite consulter l'état des éléments de code à ce point.</span><span class="sxs-lookup"><span data-stu-id="18b71-103">Breakpoints specify that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, you can then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="18b71-104">Points d’arrêt</span><span class="sxs-lookup"><span data-stu-id="18b71-104">Breakpoints</span></span>  
 <span data-ttu-id="18b71-105">En exécutant le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] , vous pouvez basculer un point d'arrêt sur des instructions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="18b71-105">When running the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can toggle a breakpoint on specific statements.</span></span> <span data-ttu-id="18b71-106">Lorsque l'exécution atteint une instruction avec un point d'arrêt, le débogueur suspend l'exécution afin que vous puissiez afficher des informations de débogage telles que les valeurs présentes dans les variables et les paramètres.</span><span class="sxs-lookup"><span data-stu-id="18b71-106">When execution reaches a statement with a breakpoint, the debugger pauses execution so you can view debugging information, such as the values present in variables and parameters.</span></span>  
  
 <span data-ttu-id="18b71-107">Vous pouvez gérer les points d’arrêt individuellement dans la fenêtre de l’éditeur ou collectivement via la fenêtre **Points d’arrêt** .</span><span class="sxs-lookup"><span data-stu-id="18b71-107">You can manage breakpoints individually in the editor window, or collectively by using the **Breakpoints** window.</span></span> <span data-ttu-id="18b71-108">Vous pouvez modifier des points d'arrêt afin de spécifier des éléments tels que les conditions spécifiques sous lesquelles l'exécution doit être suspendue ou les actions à prendre si le point d'arrêt est exécuté.</span><span class="sxs-lookup"><span data-stu-id="18b71-108">You can edit breakpoints to specify items such as specific conditions under which execution should pause, or the actions to be taken if the breakpoint is executed.</span></span>  
  
## <a name="breakpoint-tasks"></a><span data-ttu-id="18b71-109">Tâches de point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="18b71-109">Breakpoint Tasks</span></span>  
  
|<span data-ttu-id="18b71-110">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="18b71-110">Task Description</span></span>|<span data-ttu-id="18b71-111">Rubrique</span><span class="sxs-lookup"><span data-stu-id="18b71-111">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="18b71-112">Explique comment spécifier l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suite à laquelle vous souhaitez que le débogueur soit suspendu.</span><span class="sxs-lookup"><span data-stu-id="18b71-112">Describes how to specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement on which you want the debugger to pause.</span></span>|[<span data-ttu-id="18b71-113">Basculer un point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="18b71-113">Toggle a Breakpoint</span></span>](../spatial/point.md)|  
|<span data-ttu-id="18b71-114">Explique comment désactiver temporairement un point d'arrêt et le réactiver ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="18b71-114">Describes how to temporarily deactivate a breakpoint, and later reactivate it.</span></span> <span data-ttu-id="18b71-115">Explique également comment supprimer un point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="18b71-115">Also describes how to delete a breakpoint.</span></span>|[<span data-ttu-id="18b71-116">Activer, désactiver et supprimer des points d’arrêt</span><span class="sxs-lookup"><span data-stu-id="18b71-116">Enable, Disable, and Delete Breakpoints</span></span>](enable-disable-and-delete-breakpoints.md)|  
|<span data-ttu-id="18b71-117">Explique comment spécifier une condition qui définit si le point d'arrêt entraîne un arrêt d'après l'évaluation d'une expression Transact-SQL spécifiée.</span><span class="sxs-lookup"><span data-stu-id="18b71-117">Describes how to specify a condition, which defines whether breakpoint breaks based on the evaluation of a specified Transact-SQL expression.</span></span>|[<span data-ttu-id="18b71-118">Spécifier une condition de point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="18b71-118">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)|  
|<span data-ttu-id="18b71-119">Explique comment spécifier un nombre d'accès qui provoque uniquement l'arrêt d'un point d'arrêt lorsque l'instruction contenant le point d'arrêt a été exécutée un nombre spécifié de fois.</span><span class="sxs-lookup"><span data-stu-id="18b71-119">Describes how to specify a hit count, which causes a breakpoint to break only when the statement containing the breakpoint has been executed a specified number of times.</span></span>|[<span data-ttu-id="18b71-120">Spécifier un nombre d’accès</span><span class="sxs-lookup"><span data-stu-id="18b71-120">Specify a Hit Count</span></span>](specify-a-hit-count.md)|  
|<span data-ttu-id="18b71-121">Explique comment spécifier un filtre qui provoque uniquement l'arrêt d'un point d'arrêt pour les processus ou les threads spécifiés.</span><span class="sxs-lookup"><span data-stu-id="18b71-121">Describes how to specify a filter, which causes a breakpoint to break for only specified processes or threads.</span></span>|[<span data-ttu-id="18b71-122">Pour spécifier un filtre de point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="18b71-122">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)|  
|<span data-ttu-id="18b71-123">Explique comment spécifier une action **Lorsqu’il est atteint** , c’est-à-dire une opération personnalisée qui est effectuée lors de l’exécution de l’instruction de point d’arrêt.</span><span class="sxs-lookup"><span data-stu-id="18b71-123">Describes how to specify a **When Hit** action, which is a custom operation that is performed when the breakpoint statement is executed.</span></span> <span data-ttu-id="18b71-124">Citons en exemple l'impression d'un message.</span><span class="sxs-lookup"><span data-stu-id="18b71-124">An example would be to print a message.</span></span>|[<span data-ttu-id="18b71-125">Spécifier une action de point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="18b71-125">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)|  
|<span data-ttu-id="18b71-126">Explique comment modifier l'emplacement d'un point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="18b71-126">Describes how to edit the location of a breakpoint.</span></span>|[<span data-ttu-id="18b71-127">Modifier un emplacement de point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="18b71-127">Edit a Breakpoint Location</span></span>](edit-a-breakpoint-location.md)|  
  
## <a name="see-also"></a><span data-ttu-id="18b71-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="18b71-128">See Also</span></span>  
 [<span data-ttu-id="18b71-129">Informations du débogueur Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18b71-129">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
