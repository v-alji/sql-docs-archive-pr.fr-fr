---
title: Suspendre une trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- pausing traces
- temporarily stopping traces
- traces [SQL Server], pausing
- stopping traces
ms.assetid: 432b9b0c-b5e7-47f3-a71b-310fb3bf2445
author: stevestein
ms.author: sstein
ms.openlocfilehash: cdc9dbbd01099b1d33787a72b0bd59b65cea722e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694928"
---
# <a name="pause-a-trace-sql-server-profiler"></a><span data-ttu-id="e8a7b-102">Suspendre une trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="e8a7b-102">Pause a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="e8a7b-103">Le fait de marquer une pause dans une trace empêche la capture de nouvelles données d’événement jusqu'au redémarrage de la trace.</span><span class="sxs-lookup"><span data-stu-id="e8a7b-103">Pausing a trace prevents further event data from being captured until the trace is restarted.</span></span>  
  
 <span data-ttu-id="e8a7b-104">Lorsque vous suspendez une trace, vous empêchez  la capture des données d’événements jusqu'à ce que vous redémarriez la trace.</span><span class="sxs-lookup"><span data-stu-id="e8a7b-104">When you pause a trace, you prevent event data from being captured until the trace is restarted.</span></span> <span data-ttu-id="e8a7b-105">Le redémarrage d'une trace permet de reprendre les opérations de trace.</span><span class="sxs-lookup"><span data-stu-id="e8a7b-105">Restarting a trace lets trace operations resume.</span></span> <span data-ttu-id="e8a7b-106">Aucune donnée de trace précédente n'est perdue après le redémarrage.</span><span class="sxs-lookup"><span data-stu-id="e8a7b-106">No previously captured data is lost after a restart.</span></span> <span data-ttu-id="e8a7b-107">Lors du redémarrage de la trace, la capture des données reprend à partir du point où elle s'était arrêtée.</span><span class="sxs-lookup"><span data-stu-id="e8a7b-107">When the trace is restarted, data capturing resumes from that point onward.</span></span> <span data-ttu-id="e8a7b-108">Lorsqu'une trace est suspendue, vous pouvez modifier le nom, les événements, les colonnes et les filtres.</span><span class="sxs-lookup"><span data-stu-id="e8a7b-108">While a trace is paused, you can change the name, events, columns, and filters.</span></span> <span data-ttu-id="e8a7b-109">Toutefois, vous ne pouvez pas modifier les destinations des données de la trace, ni la connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="e8a7b-109">However, you cannot change the destinations to which you are sending the trace data, nor change the server connection.</span></span>  
  
### <a name="to-pause-a-trace"></a><span data-ttu-id="e8a7b-110">Pour interrompre une trace</span><span class="sxs-lookup"><span data-stu-id="e8a7b-110">To pause a trace</span></span>  
  
1.  <span data-ttu-id="e8a7b-111">Sélectionnez une fenêtre contenant une trace en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e8a7b-111">Select a window that contains a running trace.</span></span>  
  
2.  <span data-ttu-id="e8a7b-112">Dans le menu **Fichier** , cliquez sur **Suspendre la trace**.</span><span class="sxs-lookup"><span data-stu-id="e8a7b-112">On the **File** menu, click **Pause Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a7b-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8a7b-113">See Also</span></span>  
 [<span data-ttu-id="e8a7b-114">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="e8a7b-114">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
