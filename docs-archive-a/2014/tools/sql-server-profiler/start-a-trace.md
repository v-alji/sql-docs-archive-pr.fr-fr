---
title: Démarrer une trace | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, stopping traces
- pausing traces
- Profiler [SQL Server Profiler], stopping traces
- Profiler [SQL Server Profiler], starting traces
- traces [SQL Server], starting
- SQL Server Profiler, pausing traces
- traces [SQL Server], stopping
- Profiler [SQL Server Profiler], pausing traces
- traces [SQL Server], pausing
- SQL Server Profiler, starting traces
- stopping traces
- starting traces
ms.assetid: aeeb38eb-229a-4c8b-ad66-57e9ce45fb6a
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2b75519631269a1213077a4e295ac73fca1b950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703583"
---
# <a name="start-a-trace"></a><span data-ttu-id="25a24-102">Démarrer une trace</span><span class="sxs-lookup"><span data-stu-id="25a24-102">Start a Trace</span></span>
  <span data-ttu-id="25a24-103">Après avoir défini une nouvelle trace ou créé un modèle en utilisant le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], vous pouvez démarrer, suspendre ou arrêter la capture des données en utilisant la définition de la nouvelle trace ou le modèle.</span><span class="sxs-lookup"><span data-stu-id="25a24-103">After you have defined a new trace or created a template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can start, pause, or stop capturing data by using the new trace definition or template.</span></span>  
  
## <a name="starting-a-trace"></a><span data-ttu-id="25a24-104">Démarrage d’une trace</span><span class="sxs-lookup"><span data-stu-id="25a24-104">Starting a Trace</span></span>  
 <span data-ttu-id="25a24-105">Lorsque vous démarrez une trace et que la source définie est une instance de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ou des [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crée une file d'attente qui fournit un espace de stockage temporaire pour les événements serveur capturés.</span><span class="sxs-lookup"><span data-stu-id="25a24-105">When you start a trace and the defined source is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates a queue that provides a temporary holding place for captured server events.</span></span>  
  
 <span data-ttu-id="25a24-106">Lorsque vous utilisez le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour accéder à Trace SQL, une nouvelle fenêtre de trace s'ouvre (si aucune n'est ouverte) au démarrage d'une trace et les données sont capturées immédiatement.</span><span class="sxs-lookup"><span data-stu-id="25a24-106">When you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to access SQL Trace, a new trace window opens (if one is not already open) when a trace is started, and data is immediately captured.</span></span>  
  
 <span data-ttu-id="25a24-107">Lorsque vous utilisez des procédures stockées système [!INCLUDE[tsql](../../includes/tsql-md.md)] pour accéder à Trace SQL, vous devez démarrer une trace chaque fois qu'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] démarre pour capturer des données.</span><span class="sxs-lookup"><span data-stu-id="25a24-107">When you use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to access SQL Trace, you must start a trace every time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts for data to be captured.</span></span> <span data-ttu-id="25a24-108">Lorsqu’une trace est démarrée, vous pouvez modifier uniquement le nom de la trace.</span><span class="sxs-lookup"><span data-stu-id="25a24-108">When a trace has been started, you can modify only the name of the trace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25a24-109">Lorsque vous utilisez des traces existantes, vous pouvez afficher les propriétés, mais pas les modifier.</span><span class="sxs-lookup"><span data-stu-id="25a24-109">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="25a24-110">Pour modifier les propriétés, arrêtez ou suspendez la trace.</span><span class="sxs-lookup"><span data-stu-id="25a24-110">To modify the properties, stop or pause the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a24-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25a24-111">See Also</span></span>  
 <span data-ttu-id="25a24-112">[Démarrer automatiquement une trace après s’être connecté à un serveur &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="25a24-112">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="25a24-113">[Suspendre une trace &#40;SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="25a24-113">[Pause a Trace &#40;SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="25a24-114">[Arrêter une trace &#40;SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="25a24-114">[Stop a Trace &#40;SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="25a24-115">[Effacer une fenêtre de trace &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="25a24-115">[Clear a Trace Window &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="25a24-116">Exécuter une trace après qu’elle a été suspendue ou arrêtée &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="25a24-116">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
  
