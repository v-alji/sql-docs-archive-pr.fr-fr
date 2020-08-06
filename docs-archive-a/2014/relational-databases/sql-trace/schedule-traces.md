---
title: Planifier les traces | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], events
- traces [SQL Server]
- traces [SQL Server], stopping
- events [SQL Server], filters
- scheduling traces [SQL Server]
- traces [SQL Server], scheduling
- stopping traces
ms.assetid: 620b79db-924b-4502-8af3-39efcfca245d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a698d88db35c84f7611293cf45807203c883865a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611714"
---
# <a name="schedule-traces"></a><span data-ttu-id="b1bcb-102">Planifier les traces</span><span class="sxs-lookup"><span data-stu-id="b1bcb-102">Schedule Traces</span></span>
  <span data-ttu-id="b1bcb-103">Vous pouvez planifier les traces de deux façons dans Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1bcb-103">There are two ways to schedule tracing in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b1bcb-104">Vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="b1bcb-104">You can:</span></span>  
  
-   <span data-ttu-id="b1bcb-105">Activer une heure d'arrêt de la trace.</span><span class="sxs-lookup"><span data-stu-id="b1bcb-105">Enable a trace stop time.</span></span>  
  
-   <span data-ttu-id="b1bcb-106">Utiliser l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour planifier la trace.</span><span class="sxs-lookup"><span data-stu-id="b1bcb-106">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to schedule a trace.</span></span>  
  
## <a name="specifying-a-stop-time"></a><span data-ttu-id="b1bcb-107">Spécification d'une heure d'arrêt</span><span class="sxs-lookup"><span data-stu-id="b1bcb-107">Specifying a Stop Time</span></span>  
 <span data-ttu-id="b1bcb-108">Vous pouvez spécifier une heure d'arrêt de la trace si vous utilisez des procédures stockées [!INCLUDE[tsql](../../includes/tsql-md.md)] ou si vous utilisez [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1bcb-108">You can specify a trace stop time if you use [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures or if you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="b1bcb-109">Vous devez définir l'heure d'arrêt lorsque vous configurez initialement la trace.</span><span class="sxs-lookup"><span data-stu-id="b1bcb-109">The stop time must be set when the trace is originally configured.</span></span>  
  
## <a name="scheduling-traces-by-using-sql-server-agent"></a><span data-ttu-id="b1bcb-110">Planification des traces à l'aide de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1bcb-110">Scheduling Traces by Using SQL Server Agent</span></span>  
 <span data-ttu-id="b1bcb-111">La meilleure façon de planifier les traces consiste à utiliser l’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour démarrer la trace, puis à spécifier une heure d’arrêt de la trace à l’aide de la procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)]**sp_trace_setstatus**ou du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1bcb-111">The best way to schedule traces is to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to start the trace and then specify a trace stop time by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure **sp_trace_setstatus**, or [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="b1bcb-112">**Pour définir un filtre d'heure de fin pour une trace**</span><span class="sxs-lookup"><span data-stu-id="b1bcb-112">**To set an end time filter for a trace**</span></span>  
  
 [<span data-ttu-id="b1bcb-113">Filtrer des événements en fonction de leur heure de fin &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="b1bcb-113">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
 [<span data-ttu-id="b1bcb-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1bcb-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="b1bcb-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1bcb-115">See Also</span></span>  
 [<span data-ttu-id="b1bcb-116">Tâches d’administration automatisée &#40;SQL Server Agent&#41;</span><span class="sxs-lookup"><span data-stu-id="b1bcb-116">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../../ssms/agent/sql-server-agent.md)  
  
  
