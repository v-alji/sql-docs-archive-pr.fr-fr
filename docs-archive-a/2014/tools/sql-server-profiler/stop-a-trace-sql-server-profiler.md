---
title: Arrêter une trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], stopping
- stopping traces
ms.assetid: 47c4f33d-63e0-4444-bec8-4c1c91f8e25c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 501ea4a4838f8e2ea42fc475c486466d48020a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703572"
---
# <a name="stop-a-trace-sql-server-profiler"></a><span data-ttu-id="c0084-102">Arrêter une trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c0084-102">Stop a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="c0084-103">Cette rubrique explique comment arrêter l'exécution d'une trace par le biais du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0084-103">This topic describes how to stop a trace that is running by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="c0084-104">Le fait d'arrêter une trace arrête la capture des données.</span><span class="sxs-lookup"><span data-stu-id="c0084-104">Stopping a trace stops data from being captured.</span></span> <span data-ttu-id="c0084-105">Une fois qu'une trace est arrêtée, elle ne peut pas être redémarrée sans perdre les données déjà capturées, à moins que celles-ci figurent dans un fichier ou une table de trace.</span><span class="sxs-lookup"><span data-stu-id="c0084-105">After a trace is stopped, it cannot be restarted without losing previously captured data, unless the data has been captured to a trace file or trace table.</span></span> <span data-ttu-id="c0084-106">Vous pouvez également enregistrer les données collectées dans une table ou un fichier après l'arrêt d'une trace.</span><span class="sxs-lookup"><span data-stu-id="c0084-106">You can also save the collected data to a table or file after stopping a trace.</span></span> <span data-ttu-id="c0084-107">Toutes les propriétés de trace antérieurement sélectionnées sont conservées en cas d'arrêt d'une trace.</span><span class="sxs-lookup"><span data-stu-id="c0084-107">All trace properties that were previously selected are preserved when a trace is stopped.</span></span> <span data-ttu-id="c0084-108">Lorsqu'une trace est arrêtée, vous pouvez modifier le nom, les événements, les colonnes et les filtres.</span><span class="sxs-lookup"><span data-stu-id="c0084-108">When a trace is stopped, you can change the name, events, columns, and filters.</span></span>  
  
### <a name="to-stop-a-trace"></a><span data-ttu-id="c0084-109">Pour arrêter une trace</span><span class="sxs-lookup"><span data-stu-id="c0084-109">To stop a trace</span></span>  
  
1.  <span data-ttu-id="c0084-110">Sélectionnez une trace en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c0084-110">Select a trace that is running.</span></span>  
  
2.  <span data-ttu-id="c0084-111">Dans le menu **Fichier** , cliquez sur **Arrêter la trace**.</span><span class="sxs-lookup"><span data-stu-id="c0084-111">On the **File** menu, click **Stop Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0084-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c0084-112">See Also</span></span>  
 [<span data-ttu-id="c0084-113">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c0084-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
