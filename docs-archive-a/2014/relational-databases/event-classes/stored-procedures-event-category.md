---
title: Procédures stockées, catégorie d’événements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Stored Procedures event category [SQL Server]
- SQL Server event classes, Stored Procedures event category
- event classes [SQL Server], Stored Procedures event category
ms.assetid: 71bebaa3-a05a-4695-b349-078cecd0949a
author: stevestein
ms.author: sstein
ms.openlocfilehash: df2e0d9a4c077ff16eba09bc5ebb6447d5d27595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710647"
---
# <a name="stored-procedures-event-category"></a><span data-ttu-id="9dcaa-102">Catégorie d'événements Procédures stockées</span><span class="sxs-lookup"><span data-stu-id="9dcaa-102">Stored Procedures Event Category</span></span>
  <span data-ttu-id="9dcaa-103">La catégorie d’événements **Procédures stockées** contient des événements de procédure stockée généraux.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-103">The **Stored Procedures** event category contains general stored procedure events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9dcaa-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9dcaa-104">In This Section</span></span>  
  
|<span data-ttu-id="9dcaa-105">Rubrique</span><span class="sxs-lookup"><span data-stu-id="9dcaa-105">Topic</span></span>|<span data-ttu-id="9dcaa-106">Description</span><span class="sxs-lookup"><span data-stu-id="9dcaa-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9dcaa-107">Classe d'événements RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="9dcaa-107">RPC:Completed Event Class</span></span>](rpc-completed-event-class.md)|<span data-ttu-id="9dcaa-108">Indique qu'un appel de procédure distante (RPC) s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-108">Indicates that a remote procedure call (RPC) has been completed.</span></span>|  
|[<span data-ttu-id="9dcaa-109">PreConnect:Completed, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="9dcaa-109">PreConnect:Completed Event Class</span></span>](preconnect-completed-event-class.md)|<span data-ttu-id="9dcaa-110">Indique quand la fonction classifieur de Resource Governor termine de s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-110">Indicates when the Resource Governor classifier function finishes execution.</span></span>|  
|[<span data-ttu-id="9dcaa-111">PreConnect:Starting, classe d'événements</span><span class="sxs-lookup"><span data-stu-id="9dcaa-111">PreConnect:Starting Event Class</span></span>](preconnect-starting-event-class.md)|<span data-ttu-id="9dcaa-112">Indique quand la fonction classifieur de Resource Governor commence à s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-112">Indicates when the Resource Governor classifier function starts execution.</span></span>|  
|[<span data-ttu-id="9dcaa-113">Classe d'événements RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="9dcaa-113">RPC Output Parameter Event Class</span></span>](rpc-output-parameter-event-class.md)|<span data-ttu-id="9dcaa-114">Trace les valeurs de paramètres de sortie des appels de procédure distante après l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-114">Traces the output parameter values of remote procedure calls after execution.</span></span>|  
|[<span data-ttu-id="9dcaa-115">Classe d'événements RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="9dcaa-115">RPC:Starting Event Class</span></span>](rpc-starting-event-class.md)|<span data-ttu-id="9dcaa-116">Indique le démarrage d'un appel de procédure distante.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-116">Indicates that a remote procedure call is starting.</span></span>|  
|[<span data-ttu-id="9dcaa-117">Classe d'événements SP:CacheHit</span><span class="sxs-lookup"><span data-stu-id="9dcaa-117">SP:CacheHit Event Class</span></span>](sp-cachehit-event-class.md)|<span data-ttu-id="9dcaa-118">Indique que la procédure stockée se trouve dans le cache.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-118">Indicates that the stored procedure is in the cache.</span></span>|  
|[<span data-ttu-id="9dcaa-119">Classe d'événements SP:CacheInsert</span><span class="sxs-lookup"><span data-stu-id="9dcaa-119">SP:CacheInsert Event Class</span></span>](sp-cacheinsert-event-class.md)|<span data-ttu-id="9dcaa-120">Indique que la procédure stockée a été placée dans le cache.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-120">Indicates that the stored procedure has been brought into the cache.</span></span>|  
|[<span data-ttu-id="9dcaa-121">Classe d'événements SP:CacheMiss</span><span class="sxs-lookup"><span data-stu-id="9dcaa-121">SP:CacheMiss Event Class</span></span>](sp-cachemiss-event-class.md)|<span data-ttu-id="9dcaa-122">Indique que la procédure stockée est introuvable dans le cache.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-122">Indicates that the stored procedure was not found in the cache.</span></span>|  
|[<span data-ttu-id="9dcaa-123">Classe d'événements SP:CacheRemove</span><span class="sxs-lookup"><span data-stu-id="9dcaa-123">SP:CacheRemove Event Class</span></span>](sp-cacheremove-event-class.md)|<span data-ttu-id="9dcaa-124">Indique que la procédure stockée a été supprimée du cache.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-124">Indicates that the stored procedure has been removed from the cache.</span></span>|  
|[<span data-ttu-id="9dcaa-125">Classe d'événements SP:Completed</span><span class="sxs-lookup"><span data-stu-id="9dcaa-125">SP:Completed Event Class</span></span>](sp-completed-event-class.md)|<span data-ttu-id="9dcaa-126">Indique que l'exécution de la procédure stockée s'est terminée.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-126">Indicates that execution of the stored procedure has completed.</span></span>|  
|[<span data-ttu-id="9dcaa-127">Classe d'événements SP:Recompile</span><span class="sxs-lookup"><span data-stu-id="9dcaa-127">SP:Recompile Event Class</span></span>](sp-recompile-event-class.md)|<span data-ttu-id="9dcaa-128">Indique que la procédure stockée a été recompilée.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-128">Indicates that the stored procedure has been recompiled.</span></span>|  
|[<span data-ttu-id="9dcaa-129">Classe d'événements SP:Starting</span><span class="sxs-lookup"><span data-stu-id="9dcaa-129">SP:Starting Event Class</span></span>](sp-starting-event-class.md)|<span data-ttu-id="9dcaa-130">Indique que l'exécution de la procédure stockée démarre.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-130">Indicates that execution of the stored procedure is starting.</span></span>|  
|[<span data-ttu-id="9dcaa-131">Classe d'événements SP:StmtCompleted</span><span class="sxs-lookup"><span data-stu-id="9dcaa-131">SP:StmtCompleted Event Class</span></span>](sp-stmtcompleted-event-class.md)|<span data-ttu-id="9dcaa-132">Indique qu'une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] d'une procédure stockée s'est terminée.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-132">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has completed.</span></span>|  
|[<span data-ttu-id="9dcaa-133">SP:StmtStarting, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="9dcaa-133">SP:StmtStarting Event Class</span></span>](sp-stmtstarting-event-class.md)|<span data-ttu-id="9dcaa-134">Indique qu'une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] d'une procédure stockée a commencé.</span><span class="sxs-lookup"><span data-stu-id="9dcaa-134">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has started.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9dcaa-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9dcaa-135">See Also</span></span>  
 <span data-ttu-id="9dcaa-136">[Événements étendus](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="9dcaa-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="9dcaa-137">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dcaa-137">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
