---
title: Utiliser SQL Server Profiler pour analyser Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 8b77dafc-4584-4e93-8ad7-299304391bfd
author: minewiskan
ms.author: owend
ms.openlocfilehash: e144c1d858670f8a46b164ffc9885e6e082c4b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602411"
---
# <a name="use-sql-server-profiler-to-monitor-analysis-services"></a><span data-ttu-id="d07a6-102">Utiliser SQL Server Profiler pour contrôler Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d07a6-102">Use SQL Server Profiler to Monitor Analysis Services</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="d07a6-103">Le assure le suivi des événements de processus du moteur, notamment le début d’un lot ou d’une transaction, et capture des données à propos de ces événements, ce qui vous permet de surveiller l’activité des serveurs et des bases de données (par exemple, les requêtes des utilisateurs ou les connexions).</span><span class="sxs-lookup"><span data-stu-id="d07a6-103">tracks engine process events, such as the start of a batch or a transaction, and it captures data about those events, thus enabling you to monitor server and database activity (for example, user queries or login activity).</span></span> <span data-ttu-id="d07a6-104">Vous pouvez capturer les données du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] dans une table ou un fichier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , en vue d'une analyse ultérieure, et relire les événements capturés sur la même instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou sur une autre instance pour voir exactement ce qui s'est passé.</span><span class="sxs-lookup"><span data-stu-id="d07a6-104">You can capture [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] data to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or a file for later analysis, and you can also replay the events captured on the same or another [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to see exactly what happened.</span></span> <span data-ttu-id="d07a6-105">Vous pouvez relire les événements en temps réel ou pas à pas.</span><span class="sxs-lookup"><span data-stu-id="d07a6-105">You can replay events in real time or on a step-by-step basis.</span></span> <span data-ttu-id="d07a6-106">Il est également très utile d'exécuter sur la même machine les événements de trace et les compteurs de performances.</span><span class="sxs-lookup"><span data-stu-id="d07a6-106">It is also very useful to run the trace events along with the Performance counters on the same machine.</span></span> <span data-ttu-id="d07a6-107">SQL Profiler peut corréler les deux en fonction de l'heure et les afficher ensemble sur une même chronologie.</span><span class="sxs-lookup"><span data-stu-id="d07a6-107">The profiler can correlate these two based on time and display them together along a single timeline.</span></span> <span data-ttu-id="d07a6-108">Les événements de trace vous donneront plus de détails, tandis que les compteurs de performances vous fourniront une vue agrégée.</span><span class="sxs-lookup"><span data-stu-id="d07a6-108">Trace events will give you more details while Performance counters give you an aggregate view.</span></span> <span data-ttu-id="d07a6-109">Pour plus d’informations sur la création et l’exécution de traces, consultez [Créer des traces de SQL Server Profiler pour la relecture &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d07a6-109">For information about how to create and run traces, see [Create Profiler Traces for Replay &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span></span>  
  
 <span data-ttu-id="d07a6-110">Le tableau suivant décrit les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="d07a6-110">The following table describes the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d07a6-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d07a6-111">In This Section</span></span>  
  
|<span data-ttu-id="d07a6-112">Rubrique</span><span class="sxs-lookup"><span data-stu-id="d07a6-112">Topic</span></span>|<span data-ttu-id="d07a6-113">Description</span><span class="sxs-lookup"><span data-stu-id="d07a6-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d07a6-114">Introduction à la surveillance d’Analysis Services à l’aide de SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="d07a6-114">Introduction to Monitoring Analysis Services with SQL Server Profiler</span></span>](introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)|<span data-ttu-id="d07a6-115">Explique comment utiliser le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour contrôler une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d07a6-115">Describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to monitor an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>|  
|[<span data-ttu-id="d07a6-116">Créer des traces de SQL Server Profiler pour la relecture &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d07a6-116">Create Profiler Traces for Replay &#40;Analysis Services&#41;</span></span>](create-profiler-traces-for-replay-analysis-services.md)|<span data-ttu-id="d07a6-117">Indique les conditions requises pour créer une trace afin d'effectuer une relecture en utilisant le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d07a6-117">Describes the requirements for creating a trace for replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="d07a6-118">Événements de trace Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d07a6-118">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)|<span data-ttu-id="d07a6-119">Décrit les classes d'événements [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d07a6-119">Describes [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] event classes.</span></span> <span data-ttu-id="d07a6-120">Ces classes d'événements sont associées aux actions générées par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et utilisées pour les relectures de traces.</span><span class="sxs-lookup"><span data-stu-id="d07a6-120">These event classes map to actions generated by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and are used for trace replays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d07a6-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d07a6-121">See Also</span></span>  
 [<span data-ttu-id="d07a6-122">Monitor an Analysis Services Instance</span><span class="sxs-lookup"><span data-stu-id="d07a6-122">Monitor an Analysis Services Instance</span></span>](monitor-an-analysis-services-instance.md)  
  
  
