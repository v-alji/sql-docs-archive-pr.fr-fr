---
title: Relire un seul événement à la fois (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- events [SQL Server], replaying single event at a time
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 220fb192-9636-41a2-b15c-62af6cab8fff
author: stevestein
ms.author: sstein
ms.openlocfilehash: 457bc94d9d8eae470fb60b450d30441c07e676df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705751"
---
# <a name="replay-a-single-event-at-a-time-sql-server-profiler"></a><span data-ttu-id="0a452-102">Relire un seul événement à la fois (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="0a452-102">Replay a Single Event at a Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="0a452-103">Cette rubrique décrit comment relire un événement à la fois dans un fichier ou une table de trace au moyen du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a452-103">This topic describes how to replay one event at a time in a replay trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-replay-a-single-event-at-a-time"></a><span data-ttu-id="0a452-104">Pour relire un seul événement à la fois</span><span class="sxs-lookup"><span data-stu-id="0a452-104">To replay a single event at a time</span></span>  
  
1.  <span data-ttu-id="0a452-105">Ouvrez le fichier de trace ou la table de trace à relire.</span><span class="sxs-lookup"><span data-stu-id="0a452-105">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="0a452-106">Pour plus d’informations, consultez [Ouvrir un fichier de trace &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou l'Assistant Paramétrage du [Ouvrir une table de trace &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="0a452-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="0a452-107">Vérifiez que le fichier de trace ou la table de trace que vous ouvrez contient les classes d'événements nécessaires pour la relecture.</span><span class="sxs-lookup"><span data-stu-id="0a452-107">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="0a452-108">Pour plus d’informations, consultez [Conditions préalables à la relecture](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a452-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="0a452-109">Dans le menu **Relire** , cliquez sur **Étape**et connectez-vous à l’instance du serveur dont vous voulez relire la trace.</span><span class="sxs-lookup"><span data-stu-id="0a452-109">On the **Replay** menu, click **Step**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="0a452-110">Dans la boîte de dialogue **Configuration de la relecture** , vérifiez les paramètres, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a452-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span> <span data-ttu-id="0a452-111">Pour plus d’informations sur la spécification des paramètres dans la boîte de dialogue **Configuration de la relecture**, consultez [Relire un fichier de trace &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) ou [Relire une table de trace &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="0a452-111">For more information about specifying settings on the **Replay Configuration** dialog box, see [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) or [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span></span>  
  
4.  <span data-ttu-id="0a452-112">Pour relire le premier événement, cliquez sur **OK** dans la boîte de dialogue **Configuration de la relecture** .</span><span class="sxs-lookup"><span data-stu-id="0a452-112">To replay the first event, click **OK** in the **Replay Configuration** dialog box.</span></span>  
  
5.  <span data-ttu-id="0a452-113">Pour relire des événements ultérieurs, dans le menu **Relire** , cliquez sur **Étape**ou appuyez sur F10.</span><span class="sxs-lookup"><span data-stu-id="0a452-113">To replay subsequent events, on the **Replay** menu, click **Step**, or press F10.</span></span> <span data-ttu-id="0a452-114">Continuez à cliquer sur **Étape** ou à appuyer sur F10 pour chaque événement.</span><span class="sxs-lookup"><span data-stu-id="0a452-114">Repeat clicking **Step** or pressing F10 for each event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a452-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a452-115">See Also</span></span>  
 <span data-ttu-id="0a452-116">[Relire des traces](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="0a452-116">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="0a452-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="0a452-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
