---
title: Surveiller une instance de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- monitoring [Analysis Services - multidimensional data]
- multidimensional data [Analysis Services], monitoring
- monitoring performance [SQL Server], SQL Server Profiler
- performance [SQL Server], monitoring tools
ms.assetid: 2f0ab717-05f3-427e-b8cd-a8bdca374add
author: minewiskan
ms.author: owend
ms.openlocfilehash: b98037ea9f26c339cdf7aba22c37e2cfb3dfbb97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611993"
---
# <a name="monitor-an-analysis-services-instance"></a><span data-ttu-id="b4d91-102">Analyser une instance Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b4d91-102">Monitor an Analysis Services Instance</span></span>
  <span data-ttu-id="b4d91-103">Surveillez les performances de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en utilisant [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou l’Analyseur de performances, une application parfois désignée sous l’appellation **PerfMon**.</span><span class="sxs-lookup"><span data-stu-id="b4d91-103">You can monitor the performance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor, an application sometimes referred to as **PerfMon**.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="b4d91-104">vous permet de créer et de gérer des traces, ainsi que d’analyser et relire les résultats de trace.</span><span class="sxs-lookup"><span data-stu-id="b4d91-104">lets you create and manage traces and analyze and replay trace results.</span></span> <span data-ttu-id="b4d91-105">L'Analyseur de performances rend compte de l'état du serveur, indexé en fonction de certains compteurs qui sont présentés dans la prochaine section.</span><span class="sxs-lookup"><span data-stu-id="b4d91-105">Performance Monitor reports on server status, as indexed through certain counters, which are discussed in the next section.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4d91-106">Pour plus d’informations sur la surveillance, consultez le [Guide des opérations SQL Server 2008 R2](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="b4d91-106">For more information about monitoring, see the [SQL Server 2008 R2 Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4d91-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b4d91-107">In This Section</span></span>  
 <span data-ttu-id="b4d91-108">Pour plus d'informations sur la surveillance, cliquez sur les liens suivants.</span><span class="sxs-lookup"><span data-stu-id="b4d91-108">Follow these links to learn more about monitoring.</span></span>  
  
 [<span data-ttu-id="b4d91-109">Événements de trace Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b4d91-109">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)  
  
 [<span data-ttu-id="b4d91-110">Utiliser SQL Server Profiler pour surveiller Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b4d91-110">Use SQL Server Profiler to Monitor Analysis Services</span></span>](use-sql-server-profiler-to-monitor-analysis-services.md)  
  
 [<span data-ttu-id="b4d91-111">Utilisez SQL Server des événements étendus &#40;&#41; XEvents pour surveiller Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b4d91-111">Use SQL Server Extended Events &#40;XEvents&#41; to Monitor Analysis Services</span></span>](../instances/monitor-analysis-services-with-sql-server-extended-events.md)  
  
 [<span data-ttu-id="b4d91-112">Utiliser des vues de gestion dynamique &#40;DMV&#41; pour surveiller Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b4d91-112">Use Dynamic Management Views &#40;DMVs&#41; to Monitor Analysis Services</span></span>](use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
  
 [<span data-ttu-id="b4d91-113">Compteurs de performance &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="b4d91-113">Performance Counters &#40;SSAS&#41;</span></span>](performance-counters-ssas.md)  
  
  
