---
title: Créer des traces manuelles à l’aide de procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: f6f47fa2-7c17-41d4-9f69-9be144d56832
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e2840dced22ccdba8fe71cc87c05d7fd6fb4be58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611003"
---
# <a name="create-manual-traces-using-stored-procedures"></a><span data-ttu-id="f7bac-102">Créer des traces manuelles à l'aide de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="f7bac-102">Create Manual Traces using Stored Procedures</span></span>
  <span data-ttu-id="f7bac-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournit des procédures stockées système [!INCLUDE[tsql](../../includes/tsql-md.md)] pour créer des traces sur une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7bac-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create traces on an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="f7bac-104">Ces procédures stockées système permettent, à partir de vos propres applications, de créer des traces manuellement au lieu d'utiliser le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7bac-104">These system stored procedures can be used from within your own applications to create traces manually, instead of using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f7bac-105">Vous pouvez ainsi écrire des applications personnalisées spécifiques des besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="f7bac-105">This allows you to write custom applications specific to the needs of your enterprise.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7bac-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f7bac-106">In This Section</span></span>  
 <span data-ttu-id="f7bac-107">Le tableau suivant répertorie les procédures stockées système pour tracer une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7bac-107">The following table lists the system stored procedures for tracing an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
|<span data-ttu-id="f7bac-108">Procédure stockée</span><span class="sxs-lookup"><span data-stu-id="f7bac-108">Stored procedure</span></span>|<span data-ttu-id="f7bac-109">Tâche réalisée</span><span class="sxs-lookup"><span data-stu-id="f7bac-109">Task performed</span></span>|  
|----------------------|--------------------|  
|[<span data-ttu-id="f7bac-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bac-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-geteventinfo-transact-sql)|<span data-ttu-id="f7bac-111">Retourne des informations sur les événements inclus dans une trace.</span><span class="sxs-lookup"><span data-stu-id="f7bac-111">Returns information about events included in a trace.</span></span>|  
|[<span data-ttu-id="f7bac-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bac-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql)|<span data-ttu-id="f7bac-113">Retourne des informations sur une trace spécifiée ou toutes les traces existantes.</span><span class="sxs-lookup"><span data-stu-id="f7bac-113">Returns information about a specified trace or all existing traces.</span></span>|  
|[<span data-ttu-id="f7bac-114">sp_trace_create &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bac-114">sp_trace_create &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql)|<span data-ttu-id="f7bac-115">Crée une définition de trace.</span><span class="sxs-lookup"><span data-stu-id="f7bac-115">Creates a trace definition.</span></span> <span data-ttu-id="f7bac-116">La nouvelle trace est à l'état arrêté.</span><span class="sxs-lookup"><span data-stu-id="f7bac-116">The new trace will be in a stopped state.</span></span>|  
|[<span data-ttu-id="f7bac-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bac-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)|<span data-ttu-id="f7bac-118">Crée un événement défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f7bac-118">Creates a user-defined event.</span></span>|  
|[<span data-ttu-id="f7bac-119">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bac-119">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)|<span data-ttu-id="f7bac-120">Ajoute une classe d'événements ou une colonne de données à une trace ou en supprime une.</span><span class="sxs-lookup"><span data-stu-id="f7bac-120">Adds an event class or data column to a trace, or removes one from it.</span></span>|  
|[<span data-ttu-id="f7bac-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bac-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)|<span data-ttu-id="f7bac-122">Démarre, arrête ou ferme une trace.</span><span class="sxs-lookup"><span data-stu-id="f7bac-122">Starts, stops, or closes a trace.</span></span>|  
|[<span data-ttu-id="f7bac-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bac-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql)|<span data-ttu-id="f7bac-124">Retourne des informations relatives aux filtres appliqués à une trace.</span><span class="sxs-lookup"><span data-stu-id="f7bac-124">Returns information about filters applied to a trace.</span></span>|  
|[<span data-ttu-id="f7bac-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bac-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)|<span data-ttu-id="f7bac-126">Applique un nouveau filtre ou un filtre modifié à une trace.</span><span class="sxs-lookup"><span data-stu-id="f7bac-126">Applies a new or modified filter to a trace.</span></span>|  
  
 <span data-ttu-id="f7bac-127">**Pour définir votre propre trace à l'aide de procédures stockées**</span><span class="sxs-lookup"><span data-stu-id="f7bac-127">**To define your own trace using stored procedures**</span></span>  
  
1.  <span data-ttu-id="f7bac-128">Spécifiez les événements à capturer à l’aide de **sp_trace_setevent**.</span><span class="sxs-lookup"><span data-stu-id="f7bac-128">Specify the events to capture using **sp_trace_setevent**.</span></span>  
  
2.  <span data-ttu-id="f7bac-129">Spécifiez les filtres d'événements, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="f7bac-129">Specify any event filters.</span></span> <span data-ttu-id="f7bac-130">Pour plus d’informations, consultez [Définir un filtre de trace &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="f7bac-130">For more information, see [Set a Trace Filter &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span></span>  
  
3.  <span data-ttu-id="f7bac-131">Spécifiez la destination des données d’événement capturées à l’aide de **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="f7bac-131">Specify the destination for the captured event data using **sp_trace_create**.</span></span>  
  
 <span data-ttu-id="f7bac-132">Pour obtenir un exemple d’utilisation de procédures stockées de trace, consultez [Créer une trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f7bac-132">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span></span>  
  
 <span data-ttu-id="f7bac-133">**Pour définir les valeurs par défaut des définitions de trace**</span><span class="sxs-lookup"><span data-stu-id="f7bac-133">**To set trace definition defaults**</span></span>  
  
 [<span data-ttu-id="f7bac-134">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f7bac-134">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
 <span data-ttu-id="f7bac-135">**Pour définir les valeurs par défaut de l'affichage des traces**</span><span class="sxs-lookup"><span data-stu-id="f7bac-135">**To set trace display defaults**</span></span>  
  
 [<span data-ttu-id="f7bac-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f7bac-136">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="f7bac-137">**Pour créer une trace**</span><span class="sxs-lookup"><span data-stu-id="f7bac-137">**To create a trace**</span></span>  
  
 [<span data-ttu-id="f7bac-138">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f7bac-138">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
 [<span data-ttu-id="f7bac-139">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f7bac-139">Transact-SQL</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
 <span data-ttu-id="f7bac-140">**Pour ajouter ou supprimer des événements à un modèle de trace**</span><span class="sxs-lookup"><span data-stu-id="f7bac-140">**To add or remove events from a trace template**</span></span>  
  
 [<span data-ttu-id="f7bac-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f7bac-141">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="f7bac-142">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f7bac-142">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
