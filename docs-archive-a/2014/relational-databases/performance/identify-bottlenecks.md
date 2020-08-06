---
title: Identifier les goulots d’étranglement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource bottlenecks [SQL Server]
- database monitoring [SQL Server], bottlenecks
- performance [SQL Server], bottlenecks
- tuning databases [SQL Server], bottlenecks
- monitoring server performance [SQL Server], bottlenecks
- monitoring performance [SQL Server], bottlenecks
- database performance [SQL Server], bottlenecks
- server performance [SQL Server], bottlenecks
- bottlenecks [SQL Server]
- identifying bottlenecks [SQL Server]
ms.assetid: db079e65-ee80-4105-aec9-f8230d0d6635
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e941b3f4a1185177cef007eb6a02a71ae1adece7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696743"
---
# <a name="identify-bottlenecks"></a><span data-ttu-id="51f65-102">Identifier les goulots d'étranglement</span><span class="sxs-lookup"><span data-stu-id="51f65-102">Identify Bottlenecks</span></span>
  <span data-ttu-id="51f65-103">L'accès simultané aux ressources partagées provoque des goulots d'étranglement.</span><span class="sxs-lookup"><span data-stu-id="51f65-103">Simultaneous access to shared resources causes bottlenecks.</span></span> <span data-ttu-id="51f65-104">En général, les goulots d'étranglement sont inévitables et existent dans tous les systèmes logiciels.</span><span class="sxs-lookup"><span data-stu-id="51f65-104">In general, bottlenecks are present in every software system and are inevitable.</span></span> <span data-ttu-id="51f65-105">Toutefois, des demandes excessives sur les ressources partagées engendrent un temps de réponse médiocre, qui impose de les identifier et de les ajuster.</span><span class="sxs-lookup"><span data-stu-id="51f65-105">However, excessive demands on shared resources cause poor response time and must be identified and tuned.</span></span>  
  
 <span data-ttu-id="51f65-106">Les causes des goulots d'étranglement sont notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="51f65-106">Causes of bottlenecks include:</span></span>  
  
-   <span data-ttu-id="51f65-107">ressources insuffisantes nécessitant l'ajout ou la mise à niveau de composants ;</span><span class="sxs-lookup"><span data-stu-id="51f65-107">Insufficient resources, requiring additional or upgraded components.</span></span>  
  
-   <span data-ttu-id="51f65-108">répartition inégale des charges de travail entre les ressources de même type (ce qui peut être le cas lorsqu'un disque est monopolisé) ;</span><span class="sxs-lookup"><span data-stu-id="51f65-108">Resources of the same type among which workloads are not distributed evenly; for example, one disk is being monopolized.</span></span>  
  
-   <span data-ttu-id="51f65-109">ressources défectueuses ;</span><span class="sxs-lookup"><span data-stu-id="51f65-109">Malfunctioning resources.</span></span>  
  
-   <span data-ttu-id="51f65-110">ressources configurées incorrectement.</span><span class="sxs-lookup"><span data-stu-id="51f65-110">Incorrectly configured resources.</span></span>  
  
## <a name="analyzing-bottlenecks"></a><span data-ttu-id="51f65-111">Analyse des goulots d'étranglement</span><span class="sxs-lookup"><span data-stu-id="51f65-111">Analyzing Bottlenecks</span></span>  
 <span data-ttu-id="51f65-112">La durée excessive de divers événements représente un indicateur des goulots d'étranglement susceptibles d'être ajustés.</span><span class="sxs-lookup"><span data-stu-id="51f65-112">Excessive durations for various events are indicators of bottlenecks that can be tuned.</span></span>  
  
 <span data-ttu-id="51f65-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="51f65-113">For example:</span></span>  
  
-   <span data-ttu-id="51f65-114">un composant peut empêcher le chargement d'un autre composant, augmentant ainsi le temps nécessaire pour terminer le chargement ;</span><span class="sxs-lookup"><span data-stu-id="51f65-114">Some other component may prevent the load from reaching this component thereby increasing the time to complete the load.</span></span>  
  
-   <span data-ttu-id="51f65-115">les demandes de client peuvent prendre plus longtemps en raison d'encombrements sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="51f65-115">Client requests may take longer due to network congestion.</span></span>  
  
 <span data-ttu-id="51f65-116">Voici cinq domaines clés à surveiller lors du suivi des performances du serveur pour identifier les goulots d'étranglement.</span><span class="sxs-lookup"><span data-stu-id="51f65-116">Following are five key areas to monitor when tracking server performance to identify bottlenecks.</span></span>  
  
|<span data-ttu-id="51f65-117">Domaine possible de goulet d'étranglement</span><span class="sxs-lookup"><span data-stu-id="51f65-117">Possible bottleneck area</span></span>|<span data-ttu-id="51f65-118">Effets sur le serveur</span><span class="sxs-lookup"><span data-stu-id="51f65-118">Effects on the server</span></span>|  
|------------------------------|---------------------------|  
|<span data-ttu-id="51f65-119">Utilisation de la mémoire</span><span class="sxs-lookup"><span data-stu-id="51f65-119">Memory usage</span></span>|<span data-ttu-id="51f65-120">Une quantité de mémoire insuffisante, allouée ou disponible pour Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , dégrade les performances.</span><span class="sxs-lookup"><span data-stu-id="51f65-120">Insufficient memory allocated or available to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] degrades performance.</span></span> <span data-ttu-id="51f65-121">Les données doivent être lues sur le disque plutôt que directement à partir du cache de données.</span><span class="sxs-lookup"><span data-stu-id="51f65-121">Data must be read from the disk rather than directly from the data cache.</span></span> <span data-ttu-id="51f65-122">Les systèmes d'exploitation Microsoft Windows font un usage excessif des fichiers d'échange : ils transfèrent des données en provenance et à destination du disque chaque fois que les pages sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="51f65-122">Microsoft Windows operating systems perform excessive paging by swapping data to and from the disk as the pages are needed.</span></span>|  
|<span data-ttu-id="51f65-123">Utilisation du processeur</span><span class="sxs-lookup"><span data-stu-id="51f65-123">CPU utilization</span></span>|<span data-ttu-id="51f65-124">Un taux d'utilisation processeur régulièrement élevé peut indiquer que les requêtes [!INCLUDE[tsql](../../includes/tsql-md.md)] doivent être ajustées ou que l'unité centrale doit être mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="51f65-124">A chronically high CPU utilization rate may indicate that [!INCLUDE[tsql](../../includes/tsql-md.md)] queries need to be tuned or that a CPU upgrade is needed.</span></span>|  
|<span data-ttu-id="51f65-125">Entrées/Sorties disque (E/S)</span><span class="sxs-lookup"><span data-stu-id="51f65-125">Disk input/output (I/O)</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="51f65-126">Les requêtes peuvent être ajustées pour éviter les E/S superflues, par exemple en utilisant des index.</span><span class="sxs-lookup"><span data-stu-id="51f65-126">queries can be tuned to reduce unnecessary I/O; for example, by employing indexes.</span></span>|  
|<span data-ttu-id="51f65-127">Connexions utilisateur</span><span class="sxs-lookup"><span data-stu-id="51f65-127">User connections</span></span>|<span data-ttu-id="51f65-128">Un nombre trop important d'utilisateurs peuvent accéder au serveur en même temps, provoquant une dégradation des performances.</span><span class="sxs-lookup"><span data-stu-id="51f65-128">Too many users may be accessing the server simultaneously causing performance degradation.</span></span>|  
|<span data-ttu-id="51f65-129">Verrous bloquants</span><span class="sxs-lookup"><span data-stu-id="51f65-129">Blocking locks</span></span>|<span data-ttu-id="51f65-130">Des applications mal conçues peuvent provoquer des blocages et nuire à la simultanéité, provoquant ainsi des temps de réponse plus longs et des débits de transactions plus faibles.</span><span class="sxs-lookup"><span data-stu-id="51f65-130">Incorrectly designed applications can cause locks and hamper concurrency, thus causing longer response times and lower transaction throughput rates.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51f65-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51f65-131">See Also</span></span>  
 <span data-ttu-id="51f65-132">[Surveiller l'utilisation de l'UC](../performance-monitor/monitor-cpu-usage.md) </span><span class="sxs-lookup"><span data-stu-id="51f65-132">[Monitor CPU Usage](../performance-monitor/monitor-cpu-usage.md) </span></span>  
 <span data-ttu-id="51f65-133">[Surveiller l'utilisation du disque](../performance-monitor/monitor-disk-usage.md) </span><span class="sxs-lookup"><span data-stu-id="51f65-133">[Monitor Disk Usage](../performance-monitor/monitor-disk-usage.md) </span></span>  
 <span data-ttu-id="51f65-134">[Surveiller l'utilisation de la mémoire](../performance-monitor/monitor-memory-usage.md) </span><span class="sxs-lookup"><span data-stu-id="51f65-134">[Monitor Memory Usage](../performance-monitor/monitor-memory-usage.md) </span></span>  
 <span data-ttu-id="51f65-135">[SQL Server, objet General Statistics](../performance-monitor/sql-server-general-statistics-object.md) </span><span class="sxs-lookup"><span data-stu-id="51f65-135">[SQL Server, General Statistics Object](../performance-monitor/sql-server-general-statistics-object.md) </span></span>  
 [<span data-ttu-id="51f65-136">SQL Server, objet Locks</span><span class="sxs-lookup"><span data-stu-id="51f65-136">SQL Server, Locks Object</span></span>](../performance-monitor/sql-server-locks-object.md)  
  
  
