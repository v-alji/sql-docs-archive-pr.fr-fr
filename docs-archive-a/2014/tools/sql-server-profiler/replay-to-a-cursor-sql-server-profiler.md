---
title: Relire jusqu’à un curseur (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- replaying cursors
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 89eadc41-4424-4a1c-ba61-0b52c851cdb1
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfc5ba06b60100bf8ecc8d04909371021a5b00e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705731"
---
# <a name="replay-to-a-cursor-sql-server-profiler"></a><span data-ttu-id="febcc-102">Relire jusqu'à un curseur (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="febcc-102">Replay to a Cursor (SQL Server Profiler)</span></span>
  <span data-ttu-id="febcc-103">Cette rubrique indique comment relire des fichiers ou des tables de trace suspendus lorsqu'un curseur est atteint à l'aide de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="febcc-103">This topic describes how to replay trace files or tables that pause when a cursor is reached by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="febcc-104">La suspension de traces sur des curseurs simplifie le débogage car vous pouvez ainsi fractionner la relecture de longs scripts de trace en courts segments se prêtant à l'analyse incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="febcc-104">Pausing traces at cursors supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-the-cursor"></a><span data-ttu-id="febcc-105">Pour relire jusqu'au curseur</span><span class="sxs-lookup"><span data-stu-id="febcc-105">To replay to the cursor</span></span>  
  
1.  <span data-ttu-id="febcc-106">Ouvrez le fichier de trace ou la table de trace à relire.</span><span class="sxs-lookup"><span data-stu-id="febcc-106">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="febcc-107">Pour plus d’informations, consultez [Ouvrir un fichier de trace &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou l'Assistant Paramétrage du [Ouvrir une table de trace &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="febcc-107">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="febcc-108">Vérifiez que le fichier de trace ou la table de trace que vous ouvrez contient les classes d'événements nécessaires pour la relecture.</span><span class="sxs-lookup"><span data-stu-id="febcc-108">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="febcc-109">Pour plus d’informations, consultez [Conditions préalables à la relecture](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="febcc-109">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="febcc-110">Dans la fenêtre de trace, cliquez sur un événement.</span><span class="sxs-lookup"><span data-stu-id="febcc-110">In the trace window, click an event.</span></span>  
  
3.  <span data-ttu-id="febcc-111">Dans le menu **Relire** , cliquez sur **Exécuter jusqu’au curseur**, puis connectez-vous au serveur où vous souhaitez relire la trace.</span><span class="sxs-lookup"><span data-stu-id="febcc-111">On the **Replay** menu, click **Run to Cursor**, and then connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="febcc-112">Dans la boîte de dialogue **Configuration de la relecture** , vérifiez les paramètres, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="febcc-112">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="febcc-113">La relecture commence, puis marque une pause lorsque le premier curseur est atteint.</span><span class="sxs-lookup"><span data-stu-id="febcc-113">The replay starts, pausing when the first cursor is reached.</span></span>  
  
5.  <span data-ttu-id="febcc-114">Appuyez sur F5 pour reprendre la trace.</span><span class="sxs-lookup"><span data-stu-id="febcc-114">Press F5 to resume the trace.</span></span>  
  
6.  <span data-ttu-id="febcc-115">Répétez l'étape 5 jusqu'à la fin de la trace.</span><span class="sxs-lookup"><span data-stu-id="febcc-115">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febcc-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="febcc-116">See Also</span></span>  
 <span data-ttu-id="febcc-117">[Relire jusqu’à un point d’arrêt &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="febcc-117">[Replay to a Breakpoint &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="febcc-118">[Relire des traces](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="febcc-118">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="febcc-119">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="febcc-119">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
