---
title: Relire jusqu’à un point d’arrêt (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- breakpoints [SQL Server]
- traces [SQL Server], replaying
ms.assetid: 3caf751e-df3b-40c7-b5e8-4490ae178e0c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f33b6862847b042a2613d8c2aa035dd5805493ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705732"
---
# <a name="replay-to-a-breakpoint-sql-server-profiler"></a><span data-ttu-id="3d769-102">Relecture jusqu'à un point d'arrêt (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="3d769-102">Replay to a Breakpoint (SQL Server Profiler)</span></span>
  <span data-ttu-id="3d769-103">Cette rubrique explique comment définir des points d'arrêt dans un fichier ou une table de trace que vous souhaitez relire à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d769-103">This topic describes how to set breakpoints in a trace file or table that you want to replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="3d769-104">La définition de points d'arrêt dans un fichier ou une table de trace avant de démarrer la relecture de cette dernière vous permet de suspendre la relecture de la trace lorsque surviennent des événements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3d769-104">Setting breakpoints in a trace file or table before you start to replay the trace, enables you to pause replay of the trace at specific events.</span></span> <span data-ttu-id="3d769-105">L'utilisation de points d'arrêt pendant la relecture d'une trace n'empêche pas le débogage. Vous pouvez en effet fractionner la relecture de scripts de trace longs en petits segments, qui peuvent être analysés de façon incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="3d769-105">Using breakpoints while replaying a trace supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-a-breakpoint"></a><span data-ttu-id="3d769-106">Pour relire jusqu'à un point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="3d769-106">To replay to a breakpoint</span></span>  
  
1.  <span data-ttu-id="3d769-107">Ouvrez le fichier de trace ou la table de trace à relire.</span><span class="sxs-lookup"><span data-stu-id="3d769-107">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="3d769-108">Pour plus d’informations, consultez [Ouvrir un fichier de trace &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou l'Assistant Paramétrage du [Ouvrir une table de trace &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="3d769-108">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="3d769-109">Vérifiez que le fichier de trace ou la table de trace que vous ouvrez contient les classes d'événements nécessaires pour la relecture.</span><span class="sxs-lookup"><span data-stu-id="3d769-109">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="3d769-110">Pour plus d’informations, consultez [Conditions préalables à la relecture](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d769-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="3d769-111">Dans la fenêtre de trace, cliquez sur un événement à utiliser comme point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="3d769-111">In the trace window, click an event that you want to use as a breakpoint.</span></span> <span data-ttu-id="3d769-112">Pour définir un point d'arrêt, employez l'une des trois méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3d769-112">Use one of the following three methods to set a breakpoint:</span></span>  
  
    -   <span data-ttu-id="3d769-113">Appuyez sur F9.</span><span class="sxs-lookup"><span data-stu-id="3d769-113">Press F9.</span></span>  
  
    -   <span data-ttu-id="3d769-114">Dans le menu **Relire** , cliquez sur **Basculer le point d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="3d769-114">On the **Replay** menu, click **Toggle Breakpoint**.</span></span>  
  
    -   <span data-ttu-id="3d769-115">Cliquez avec le bouton droit sur l’événement, puis cliquez sur **Basculer le point d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="3d769-115">Right-click the event, and then click **Toggle Breakpoint**.</span></span>  
  
     <span data-ttu-id="3d769-116">Une puce rouge apparaît en regard de l'événement de trace sélectionné, indiquant qu'il s'agit du point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="3d769-116">A red bullet appears next to the selected trace event, indicating that it is the trace breakpoint.</span></span>  
  
     <span data-ttu-id="3d769-117">Répétez cette étape pour définir plusieurs points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="3d769-117">Repeat this step to set several breakpoints.</span></span>  
  
3.  <span data-ttu-id="3d769-118">Dans le menu **Relire** , cliquez sur **Démarrer**, puis connectez-vous au serveur sur lequel vous souhaitez relire la trace.</span><span class="sxs-lookup"><span data-stu-id="3d769-118">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="3d769-119">Dans la boîte de dialogue **Configuration de la relecture** , vérifiez les paramètres, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d769-119">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3d769-120">La relecture démarre pour s'interrompre une fois le point d'arrêt atteint.</span><span class="sxs-lookup"><span data-stu-id="3d769-120">The replay starts, pausing when the breakpoint is reached.</span></span>  
  
5.  <span data-ttu-id="3d769-121">Appuyez sur F5 pour reprendre la relecture jusqu'au point d'arrêt suivant.</span><span class="sxs-lookup"><span data-stu-id="3d769-121">Press F5 to resume the replay and proceed to the next breakpoint.</span></span>  
  
6.  <span data-ttu-id="3d769-122">Répétez l'étape 5 jusqu'à la fin de la trace.</span><span class="sxs-lookup"><span data-stu-id="3d769-122">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d769-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d769-123">See Also</span></span>  
 <span data-ttu-id="3d769-124">[Relire jusqu’à un curseur &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="3d769-124">[Replay to a Cursor &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="3d769-125">[Relire des traces](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="3d769-125">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="3d769-126">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="3d769-126">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
