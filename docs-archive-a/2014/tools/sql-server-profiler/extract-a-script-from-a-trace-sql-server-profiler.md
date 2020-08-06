---
title: Extraire un script d’une trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], traces
- extracting script from trace [SQL Server]
ms.assetid: 431126a6-ff91-4818-8763-4442152bd571
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6633fafb8a39b189093044ef39694afa601af7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694927"
---
# <a name="extract-a-script-from-a-trace-sql-server-profiler"></a><span data-ttu-id="98aa1-102">Extraire un script d'une trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="98aa1-102">Extract a Script from a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="98aa1-103">Cette rubrique explique comment extraire des événements [!INCLUDE[tsql](../../includes/tsql-md.md)] d'un fichier ou d'une table de trace et comment les enregistrer sous forme de fichier de script [!INCLUDE[tsql](../../includes/tsql-md.md)] , dans le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98aa1-103">This topic describes how to extract [!INCLUDE[tsql](../../includes/tsql-md.md)] events from a trace file or table and save them as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-extract-a-transact-sql-script-from-a-trace-file-or-table"></a><span data-ttu-id="98aa1-104">Pour extraire un script Transact-SQL à partir d'un fichier ou d'une table de trace</span><span class="sxs-lookup"><span data-stu-id="98aa1-104">To extract a Transact-SQL script from a trace file or table</span></span>  
  
1.  <span data-ttu-id="98aa1-105">Ouvrez un fichier ou une table de trace contenant les événements [!INCLUDE[tsql](../../includes/tsql-md.md)] que vous voulez enregistrer sous forme de fichier de script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98aa1-105">Open a trace file or table that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] events that you want to save to a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="98aa1-106">Pour plus d’informations, consultez [Ouvrir un fichier de trace &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou l'Assistant Paramétrage du [Ouvrir une table de trace &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="98aa1-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="98aa1-107">Dans le menu **Fichier** , pointez sur **Exporter**, sur **Extraire les événements SQL Server**, puis cliquez sur **Extraire les événements Transact-SQL**.</span><span class="sxs-lookup"><span data-stu-id="98aa1-107">On the **File** menu, point to **Export**, point to **Extract SQL Server Events**, and then click **Extract Transact-SQL Events**.</span></span>  
  
3.  <span data-ttu-id="98aa1-108">Dans la boîte de dialogue **Enregistrer sous** , attribuez un nom au fichier [!INCLUDE[tsql](../../includes/tsql-md.md)] , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="98aa1-108">In the **Save As** dialog box, type a name for the [!INCLUDE[tsql](../../includes/tsql-md.md)] file, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98aa1-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98aa1-109">See Also</span></span>  
 [<span data-ttu-id="98aa1-110">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="98aa1-110">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
