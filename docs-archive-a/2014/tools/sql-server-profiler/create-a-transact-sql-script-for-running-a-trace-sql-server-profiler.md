---
title: Créer un script Transact-SQL pour exécuter une trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], running
- scripts [SQL Server], traces
ms.assetid: 6b0e2519-998d-40d5-b8ba-5e6a773f91a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3d4b4bebb2a3e05e3de12e59c53ccca9c980afd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694936"
---
# <a name="create-a-transact-sql-script-for-running-a-trace-sql-server-profiler"></a><span data-ttu-id="c9617-102">Créer un script Transact-SQL pour exécuter une trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c9617-102">Create a Transact-SQL Script for Running a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="c9617-103">Cette rubrique explique comment créer un script Transact-SQL à partir d'une table ou d'un fichier de trace existant à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9617-103">This topic describes how to create a Transact-SQL script from an existing trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-transact-sql-script-to-run-a-trace"></a><span data-ttu-id="c9617-104">Pour créer un script Transact-SQL afin d'exécuter une trace</span><span class="sxs-lookup"><span data-stu-id="c9617-104">To create a Transact-SQL script to run a trace</span></span>  
  
1.  <span data-ttu-id="c9617-105">Ouvrez un fichier ou une table de trace.</span><span class="sxs-lookup"><span data-stu-id="c9617-105">Open a trace file or table.</span></span> <span data-ttu-id="c9617-106">Pour plus d’informations, consultez [Ouvrir un fichier de trace &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou l'Assistant Paramétrage du [Ouvrir une table de trace &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="c9617-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="c9617-107">Dans le menu**Fichier**, pointez sur **Exporter**, sur **Générer un script de la définition de la trace**, puis cliquez sur la version correspondant au serveur dont vous souhaitez effectuer le suivi.</span><span class="sxs-lookup"><span data-stu-id="c9617-107">On the**File**menu, point to **Export**, point to **Script Trace Definition**, and then click the version that corresponds to the server you want to trace.</span></span>  
  
3.  <span data-ttu-id="c9617-108">Dans la boîte de dialogue **Enregistrer sous** , entrez un nom pour le fichier de script, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c9617-108">In the **Save As** dialog box, enter a name for the script file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9617-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9617-109">See Also</span></span>  
 <span data-ttu-id="c9617-110">[Modèles et autorisations du générateur de SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="c9617-110">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="c9617-111">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c9617-111">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
