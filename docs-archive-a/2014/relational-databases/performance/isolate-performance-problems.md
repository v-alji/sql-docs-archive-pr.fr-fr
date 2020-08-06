---
title: Isoler les problèmes de performance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- isolating performance problems [SQL Server]
- monitoring performance [SQL Server], isolating problems
- database monitoring [SQL Server], isolating problems
- tuning databases [SQL Server], isolating problems
- monitoring server performance [SQL Server], isolating problems
- database performance [SQL Server], isolating problems
- server performance [SQL Server], isolating problems
ms.assetid: 2eb425cb-9166-4027-ae08-c8fc2d236f44
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b42d780a8174ab57d00de72e8b00ef7af0abc17e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701100"
---
# <a name="isolate-performance-problems"></a><span data-ttu-id="ac792-102">Isoler les problèmes de performance</span><span class="sxs-lookup"><span data-stu-id="ac792-102">Isolate Performance Problems</span></span>
  <span data-ttu-id="ac792-103">Il est souvent plus efficace d’utiliser plusieurs outils [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou Microsoft Windows ensemble pour isoler les problèmes de performance de base de données que d’utiliser un seul outil à la fois.</span><span class="sxs-lookup"><span data-stu-id="ac792-103">It is often more effective to use several [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Microsoft Windows tools together to isolate database performance problems than to use one tool at a time.</span></span> <span data-ttu-id="ac792-104">Par exemple, la fonctionnalité graphique Plan d'exécution, également appelée plan d'exécution de requêtes, vous aide à reconnaître rapidement les blocages dans une seule requête.</span><span class="sxs-lookup"><span data-stu-id="ac792-104">For example, the graphical Execution Plan feature, also called Showplan, helps you quickly recognize deadlocks in a single query.</span></span> <span data-ttu-id="ac792-105">Toutefois, vous pouvez reconnaître d'autres problèmes de performance plus facilement si vous utilisez les fonctions de surveillance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et de Windows en même temps.</span><span class="sxs-lookup"><span data-stu-id="ac792-105">However, you can recognize some other performance problems more easily if you use the monitoring features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows together.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="ac792-106">permet de surveiller et de résoudre les problèmes liés à Transact-SQL et à l’application.</span><span class="sxs-lookup"><span data-stu-id="ac792-106">can be used to monitor and troubleshoot Transact-SQL and application-related problems.</span></span> <span data-ttu-id="ac792-107">Le Moniteur système permet de surveiller les problèmes liés au matériel ou à d'autres aspects du système.</span><span class="sxs-lookup"><span data-stu-id="ac792-107">System Monitor can be used to monitor hardware and other system-related problems.</span></span>  
  
 <span data-ttu-id="ac792-108">Vous pouvez surveiller les éléments suivants pour résoudre les problèmes :</span><span class="sxs-lookup"><span data-stu-id="ac792-108">You can monitor the following areas to troubleshoot problems:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ac792-109">ou les traitements [!INCLUDE[tsql](../../includes/tsql-md.md)] envoyés par les applications des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ac792-109">stored procedures or batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements submitted by user applications.</span></span>  
  
-   <span data-ttu-id="ac792-110">L'activité de l'utilisateur, notamment les verrous de blocage et les blocages.</span><span class="sxs-lookup"><span data-stu-id="ac792-110">User activity, such as blocking locks or deadlocks.</span></span>  
  
-   <span data-ttu-id="ac792-111">L'activité matérielle, notamment l'utilisation du disque.</span><span class="sxs-lookup"><span data-stu-id="ac792-111">Hardware activity, such as disk usage.</span></span>  
  
 <span data-ttu-id="ac792-112">Vous pouvez identifier les problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="ac792-112">Problems can include:</span></span>  
  
-   <span data-ttu-id="ac792-113">des erreurs dans le développement d'une application liées à des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] mal rédigées ;</span><span class="sxs-lookup"><span data-stu-id="ac792-113">Application development errors involving incorrectly written [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
-   <span data-ttu-id="ac792-114">des erreurs matérielles, notamment des erreurs de disque ou de réseau ;</span><span class="sxs-lookup"><span data-stu-id="ac792-114">Hardware errors, such as disk- or network-related errors.</span></span>  
  
-   <span data-ttu-id="ac792-115">un blocage excessif dû à une base de données mal conçue.</span><span class="sxs-lookup"><span data-stu-id="ac792-115">Excessive blocking due to an incorrectly designed database.</span></span>  
  
## <a name="tools-for-common-performance-problems"></a><span data-ttu-id="ac792-116">Outils pour les problèmes de performance classiques</span><span class="sxs-lookup"><span data-stu-id="ac792-116">Tools for Common Performance Problems</span></span>  
 <span data-ttu-id="ac792-117">Il est très important aussi de sélectionner exactement le problème de performance que vous souhaitez faire surveiller ou régler par chaque outil.</span><span class="sxs-lookup"><span data-stu-id="ac792-117">Equally important is careful selection of the performance problem that you want each tool to monitor or tune.</span></span> <span data-ttu-id="ac792-118">L'outil et l'utilitaire dépendent du type de problème de performance à résoudre.</span><span class="sxs-lookup"><span data-stu-id="ac792-118">The tool and the utility depend on the type of performance problem you want to resolve.</span></span>  
  
 <span data-ttu-id="ac792-119">Les rubriques suivantes décrivent différents outils de surveillance et de réglage et les problèmes correspondants.</span><span class="sxs-lookup"><span data-stu-id="ac792-119">The following topics describe a variety of monitoring and tuning tools and the problems they uncover.</span></span>  
  
 [<span data-ttu-id="ac792-120">Identifier les goulots d’étranglement</span><span class="sxs-lookup"><span data-stu-id="ac792-120">Identify Bottlenecks</span></span>](identify-bottlenecks.md)  
  
 [<span data-ttu-id="ac792-121">Surveiller l’utilisation de la mémoire</span><span class="sxs-lookup"><span data-stu-id="ac792-121">Monitor Memory Usage</span></span>](../performance-monitor/monitor-memory-usage.md)  
  
  
