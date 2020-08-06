---
title: Relire les traces | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, replaying traces
- Run to Cursor option
- Toggle Breakpoint option
- traces [SQL Server], replaying
- replaying traces
- playback engine [SQL Server Profiler]
- events [SQL Server], replaying traces
- Profiler [SQL Server Profiler], replaying traces
ms.assetid: da958d3c-7f3e-44c9-aecc-8a9493bea7c0
author: stevestein
ms.author: sstein
ms.openlocfilehash: c485317d1343958f9c430b73d858130097d44d75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705728"
---
# <a name="replay-traces"></a><span data-ttu-id="f59a0-102">Relire des traces</span><span class="sxs-lookup"><span data-stu-id="f59a0-102">Replay Traces</span></span>
  <span data-ttu-id="f59a0-103">La relecture est la capacité de reproduire une activité capturée dans une trace.</span><span class="sxs-lookup"><span data-stu-id="f59a0-103">Replay is the ability to reproduce activity that has been captured in a trace.</span></span> <span data-ttu-id="f59a0-104">Lorsque vous créez ou modifiez une trace, vous pouvez enregistrer cette trace dans un fichier pour la relire ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="f59a0-104">When you create or edit a trace, you can save the trace to a file and replay it later.</span></span> <span data-ttu-id="f59a0-105">Vous pouvez utiliser le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour relire l’activité de trace d’un ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="f59a0-105">You can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay trace activity from a single computer.</span></span> <span data-ttu-id="f59a0-106">Pour les charges de travail importantes, utilisez Distributed Replay Utility pour relire les données de trace de plusieurs ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="f59a0-106">For large workloads, use the Distributed Replay Utility to replay trace data from multiple computers.</span></span>  
  
 <span data-ttu-id="f59a0-107">Cette section décrit comment utiliser les fonctionnalités de relecture du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f59a0-107">This section describes how to use the replay features of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f59a0-108">Pour plus d’informations sur Distributed Replay Utility, consultez [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="f59a0-108">For more information about the Distributed Replay Utility, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="f59a0-109">contient un moteur de lecture à plusieurs threads capable de simuler les connexions utilisateur et l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f59a0-109">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="f59a0-110">La relecture est utile pour résoudre les problèmes d'applications ou de processus.</span><span class="sxs-lookup"><span data-stu-id="f59a0-110">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="f59a0-111">Lorsque vous avez identifié le problème et mis en œuvre les corrections, exécutez la trace qui a détecté le problème potentiel sur l'application ou le processus corrigé.</span><span class="sxs-lookup"><span data-stu-id="f59a0-111">When you have identified the problem and implemented corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="f59a0-112">Relisez ensuite la trace d'origine et comparez les résultats.</span><span class="sxs-lookup"><span data-stu-id="f59a0-112">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="f59a0-113">La relecture de trace prend en charge le débogage à l’aide des options **Basculer le point d’arrêt** et **Exécuter jusqu’au curseur** du menu [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Replay**.</span><span class="sxs-lookup"><span data-stu-id="f59a0-113">Trace replay supports debugging by using the **Toggle Breakpoint** and the **Run to Cursor** options on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Replay** menu.</span></span> <span data-ttu-id="f59a0-114">Ces options améliorent en particulier l'analyse des scripts longs, car elles peuvent diviser la relecture de la trace en segments courts de façon à pouvoir les analyser de manière incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="f59a0-114">These options especially improve the analysis of long scripts because they can break the replay of the trace into short segments so they can be analyzed incrementally.</span></span>  
  
 <span data-ttu-id="f59a0-115">Pour plus d’informations sur les autorisations nécessaires pour relire des traces, consultez [Autorisations nécessaires pour exécuter SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="f59a0-115">For information about the permissions required to replay traces, see [Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f59a0-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f59a0-116">In This Section</span></span>  
  
|<span data-ttu-id="f59a0-117">Rubrique</span><span class="sxs-lookup"><span data-stu-id="f59a0-117">Topic</span></span>|<span data-ttu-id="f59a0-118">Description</span><span class="sxs-lookup"><span data-stu-id="f59a0-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f59a0-119">Conditions préalables à la relecture</span><span class="sxs-lookup"><span data-stu-id="f59a0-119">Replay Requirements</span></span>](replay-requirements.md)|<span data-ttu-id="f59a0-120">Décrit les événements qui doivent être inclus dans la définition d'une trace pour qu'elle puisse être relue à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f59a0-120">Describes the events that must be included in a trace definition so that it can be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="f59a0-121">Options de relecture &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="f59a0-121">Replay Options &#40;SQL Server Profiler&#41;</span></span>](replay-options-sql-server-profiler.md)|<span data-ttu-id="f59a0-122">Décrit les options que vous pouvez définir dans la boîte de dialogue **Configuration de la relecture** de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f59a0-122">Describes the options you can set in the **Replay Configuration** dialog box of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="f59a0-123">Considérations sur la relecture des traces &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="f59a0-123">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)|<span data-ttu-id="f59a0-124">Décrit les événements de trace qui ne peuvent pas être relus avec le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] et les effets de la relecture des traces sur les performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="f59a0-124">Describes trace events that can not be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and the effects on server performance of replaying traces.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f59a0-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f59a0-125">See Also</span></span>  
 [<span data-ttu-id="f59a0-126">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="f59a0-126">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
