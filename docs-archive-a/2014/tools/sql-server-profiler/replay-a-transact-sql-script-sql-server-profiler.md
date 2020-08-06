---
title: Relire un script Transact-SQL (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- scripts [SQL Server], traces
- replaying traces
ms.assetid: 9c0eb222-e6e3-4bc1-a25f-a41e962d361b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5abf22a1201ac927f12ef9e4cfdd1f6d3026d00a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705740"
---
# <a name="replay-a-transact-sql-script-sql-server-profiler"></a><span data-ttu-id="76eb3-102">Relire un script Transact-SQL (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="76eb3-102">Replay a Transact-SQL Script (SQL Server Profiler)</span></span>
  <span data-ttu-id="76eb3-103">Lorsque vous testez d'éventuelles solutions à un problème de performances, utilisez le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour lire des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , et comparer les performances avant et après les modifications.</span><span class="sxs-lookup"><span data-stu-id="76eb3-103">When you test possible solutions to a performance problem, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, and compare performance before and after your changes.</span></span>  
  
### <a name="to-replay-a-transact-sql-script"></a><span data-ttu-id="76eb3-104">Relecture d'un script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="76eb3-104">To replay a Transact-SQL script</span></span>  
  
1.  <span data-ttu-id="76eb3-105">Dans le menu **Fichier** , pointez sur **Ouvrir**, puis cliquez sur **Fichier de script**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-105">On the **File** menu, point to **Open**, and then click **Script File**.</span></span>  
  
2.  <span data-ttu-id="76eb3-106">Sélectionnez le fichier de script [!INCLUDE[tsql](../../includes/tsql-md.md)] que vous souhaitez ouvrir.</span><span class="sxs-lookup"><span data-stu-id="76eb3-106">Select the [!INCLUDE[tsql](../../includes/tsql-md.md)] script file you want to open.</span></span> <span data-ttu-id="76eb3-107">Vérifiez que le script [!INCLUDE[tsql](../../includes/tsql-md.md)] contient les événements nécessaires pour la relecture.</span><span class="sxs-lookup"><span data-stu-id="76eb3-107">Make sure that the [!INCLUDE[tsql](../../includes/tsql-md.md)] script contains events necessary for replay.</span></span> <span data-ttu-id="76eb3-108">Pour plus d’informations, consultez [Conditions préalables à la relecture](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76eb3-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
3.  <span data-ttu-id="76eb3-109">Dans le menu **Relire** , cliquez sur **Démarrer**, puis connectez-vous au serveur où vous souhaitez relire le script.</span><span class="sxs-lookup"><span data-stu-id="76eb3-109">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the script.</span></span>  
  
4.  <span data-ttu-id="76eb3-110">Dans la boîte de dialogue **Configuration de la relecture** , vérifiez les paramètres, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76eb3-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76eb3-111">See Also</span></span>  
 <span data-ttu-id="76eb3-112">[Relire des traces](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="76eb3-112">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="76eb3-113">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="76eb3-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
