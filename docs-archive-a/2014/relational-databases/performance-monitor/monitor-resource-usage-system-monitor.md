---
title: Analyser l’utilisation des ressources (Moniteur système) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], resource usage
- System Monitor [SQL Server], about Windows System Monitor
- resource usage monitoring [SQL Server]
- System Monitor [SQL Server]
- counters [SQL Server], resource usage subjects
- performance counters [SQL Server], resource usage subjects
- Windows System Monitor [SQL Server], about Windows System Monitor
- monitoring [SQL Server], server resource usage
- monitoring resource usage [SQL Server]
- Windows System Monitor [SQL Server]
- database monitoring [SQL Server], resource usage
- database performance [SQL Server], resource usage
- tuning databases [SQL Server], resource usage
- server performance [SQL Server], resource usage
ms.assetid: f2993a28-0b81-46f2-aec0-6877fe990387
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d691091a41e3161c733902824bf439b6788cc4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613998"
---
# <a name="monitor-resource-usage-system-monitor"></a><span data-ttu-id="acf7c-102">Analyser l'utilisation des ressources (Moniteur système)</span><span class="sxs-lookup"><span data-stu-id="acf7c-102">Monitor Resource Usage (System Monitor)</span></span>
  <span data-ttu-id="acf7c-103">Si vous utilisez le système d'exploitation Microsoft Windows Server, faites appel à l'outil graphique Moniteur système pour mesurer les performances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acf7c-103">If you are running Microsoft Windows server operating system, use the System Monitor graphical tool to measure the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="acf7c-104">Vous pouvez afficher les objets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , les compteurs de performance ainsi que le comportement d’autres objets, tels que les processeurs, la mémoire, le cache, les threads et les processus.</span><span class="sxs-lookup"><span data-stu-id="acf7c-104">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects, performance counters, and the behavior of other objects, such as processors, memory, cache, threads, and processes.</span></span> <span data-ttu-id="acf7c-105">Chacun de ces objets dispose d'un jeu de compteurs qui mesurent l'utilisation du dispositif, la longueur des files d'attente, les temporisations et d'autres indicateurs de débit et de congestion interne.</span><span class="sxs-lookup"><span data-stu-id="acf7c-105">Each of these objects has an associated set of counters that measure device usage, queue lengths, delays, and other indicators of throughput and internal congestion.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="acf7c-106">Le Moniteur système a remplacé l'Analyseur de performances après Windows NT 4.0.</span><span class="sxs-lookup"><span data-stu-id="acf7c-106">System Monitor replaced Performance Monitor after Windows NT 4.0.</span></span>  
  
## <a name="benefits-of-system-monitor"></a><span data-ttu-id="acf7c-107">Avantages du Moniteur système</span><span class="sxs-lookup"><span data-stu-id="acf7c-107">Benefits of System Monitor</span></span>  
 <span data-ttu-id="acf7c-108">Le Moniteur système peut s'avérer utile pour surveiller les compteurs du système d'exploitation Windows et de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] simultanément afin déterminer toute corrélation entre les performances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et celles de Windows.</span><span class="sxs-lookup"><span data-stu-id="acf7c-108">System Monitor can be useful to monitor Windows operating system and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] counters at the same time to determine any correlation between the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows.</span></span> <span data-ttu-id="acf7c-109">Par exemple, la surveillance des compteurs d'E/S de disque de Windows et des compteurs de gestionnaire de tampons [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en même temps peut révéler le comportement de l'ensemble du système.</span><span class="sxs-lookup"><span data-stu-id="acf7c-109">For example, monitoring the Windows disk input/output (I/O) counters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Buffer Manager counters at the same time can reveal the behavior of the entire system.</span></span>  
  
 <span data-ttu-id="acf7c-110">Le Moniteur système vous permet d'obtenir des statistiques sur l'activité et sur les performances actuelles de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="acf7c-110">System Monitor allows you to obtain statistics on current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity and performance.</span></span> <span data-ttu-id="acf7c-111">Le Moniteur système vous permet :</span><span class="sxs-lookup"><span data-stu-id="acf7c-111">Using System Monitor, you can:</span></span>  
  
-   <span data-ttu-id="acf7c-112">d'afficher simultanément des données provenant d'un nombre illimité d'ordinateurs ;</span><span class="sxs-lookup"><span data-stu-id="acf7c-112">View data simultaneously from any number of computers.</span></span>  
  
-   <span data-ttu-id="acf7c-113">d'afficher et de modifier les graphiques pour refléter l'activité en cours, et d'afficher les valeurs des compteurs actualisés selon une fréquence choisie par l'utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="acf7c-113">View and change charts to reflect current activity, and show counter values that are updated at a frequency that the user defines.</span></span>  
  
-   <span data-ttu-id="acf7c-114">d'exporter les données provenant de graphiques, des journaux, des journaux d'alertes et des rapports vers un tableur ou des applications de base de données afin de les traiter ou de les imprimer ultérieurement ;</span><span class="sxs-lookup"><span data-stu-id="acf7c-114">Export data from charts, logs, alert logs, and reports to spreadsheet or database applications for further manipulation and printing.</span></span>  
  
-   <span data-ttu-id="acf7c-115">d'ajouter des alertes système qui répertorient un événement dans le journal d'alerte et peuvent vous en avertir par l'émission d'une alerte réseau ;</span><span class="sxs-lookup"><span data-stu-id="acf7c-115">Add system alerts that list an event in the alert log and can notify you by issuing a network alert.</span></span>  
  
-   <span data-ttu-id="acf7c-116">d'exécuter un programme prédéfini la première fois ou chaque fois que la valeur d'un compteur est supérieure ou inférieure à une valeur définie par l'utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="acf7c-116">Run a predefined application the first time or every time a counter value goes over or under a user-defined value.</span></span>  
  
-   <span data-ttu-id="acf7c-117">de créer des fichiers journaux contenant des données relatives à différents objets provenant de différents ordinateurs ;</span><span class="sxs-lookup"><span data-stu-id="acf7c-117">Create log files that contain data about various objects from different computers.</span></span>  
  
-   <span data-ttu-id="acf7c-118">d'ajouter à un fichier sélectionné des sections d'autres fichiers journaux afin de créer un fichier d'archive à long terme ;</span><span class="sxs-lookup"><span data-stu-id="acf7c-118">Append to one file selected sections from other existing log files to form a long-term archive.</span></span>  
  
-   <span data-ttu-id="acf7c-119">d'afficher les rapports d'activité en cours ou de créer des rapports à partir de fichiers journaux existants ;</span><span class="sxs-lookup"><span data-stu-id="acf7c-119">View current-activity reports, or create reports from existing log files.</span></span>  
  
-   <span data-ttu-id="acf7c-120">de sauvegarder les paramètres individuels de graphiques, d'alertes, de journaux ou de rapports, ou la totalité de la structure de l'espace de travail afin de pouvoir les réutiliser.</span><span class="sxs-lookup"><span data-stu-id="acf7c-120">Save individual chart, alert, log, or report settings, or the entire workspace setup for reuse.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="acf7c-121">Le Moniteur système a remplacé l'Analyseur de performances après Windows NT 4.0.</span><span class="sxs-lookup"><span data-stu-id="acf7c-121">System Monitor replaced the Performance Monitor after Windows NT 4.0.</span></span> <span data-ttu-id="acf7c-122">Vous pouvez utiliser soit le Moniteur système, soit l'Analyseur de performances pour effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="acf7c-122">You can use either the System Monitor or Performance Monitor to do these tasks.</span></span>  
  
## <a name="system-monitor-performance"></a><span data-ttu-id="acf7c-123">Performances du Moniteur système</span><span class="sxs-lookup"><span data-stu-id="acf7c-123">System Monitor Performance</span></span>  
 <span data-ttu-id="acf7c-124">Quand vous surveillez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le système d'exploitation Microsoft Windows pour étudier leurs performances, trois grands domaines doivent avant tout retenir votre attention :</span><span class="sxs-lookup"><span data-stu-id="acf7c-124">When you monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the Microsoft Windows operating system to investigate performance-related issues, concentrate your initial efforts in three main areas:</span></span>  
  
-   <span data-ttu-id="acf7c-125">Activité du disque</span><span class="sxs-lookup"><span data-stu-id="acf7c-125">Disk activity</span></span>  
  
-   <span data-ttu-id="acf7c-126">Utilisation des processeurs</span><span class="sxs-lookup"><span data-stu-id="acf7c-126">Processor utilization</span></span>  
  
-   <span data-ttu-id="acf7c-127">Utilisation de la mémoire</span><span class="sxs-lookup"><span data-stu-id="acf7c-127">Memory usage</span></span>  
  
 <span data-ttu-id="acf7c-128">La surveillance d'un ordinateur sur lequel est exécuté le Moniteur système peut affecter légèrement les performances de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="acf7c-128">Monitoring a computer on which System Monitor is running can affect computer performance slightly.</span></span> <span data-ttu-id="acf7c-129">Par conséquent, enregistrez les données générées par le Moniteur système sur un autre disque (ou ordinateur) afin de réduire l'impact résultant sur l'ordinateur surveillé, ou exécutez le Moniteur système depuis un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="acf7c-129">Therefore, either log the System Monitor data to another disk (or computer) so that it reduces the effect on the computer being monitored, or run System Monitor from a remote computer.</span></span> <span data-ttu-id="acf7c-130">Surveillez seulement les compteurs qui vous intéressent.</span><span class="sxs-lookup"><span data-stu-id="acf7c-130">Monitor only the counters in which you are interested.</span></span> <span data-ttu-id="acf7c-131">Si vous surveillez un nombre trop élevé de compteurs, le processus de surveillance consomme davantage de ressources au détriment des performances de l'ordinateur surveillé.</span><span class="sxs-lookup"><span data-stu-id="acf7c-131">If you monitor too many counters, resource usage overhead is added to the monitoring process and affects the performance of the computer that is being monitored.</span></span>  
  
## <a name="system-monitor-tasks"></a><span data-ttu-id="acf7c-132">Tâches du Moniteur système</span><span class="sxs-lookup"><span data-stu-id="acf7c-132">System Monitor Tasks</span></span>  
  
|<span data-ttu-id="acf7c-133">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="acf7c-133">Task Description</span></span>|<span data-ttu-id="acf7c-134">Rubrique</span><span class="sxs-lookup"><span data-stu-id="acf7c-134">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="acf7c-135">Décrit quand utiliser le Moniteur système et présente la surcharge de performances lorsque vous utilisez le Moniteur système.</span><span class="sxs-lookup"><span data-stu-id="acf7c-135">Describes when to use System Monitor and discusses performance overhead when you use System Monitor.</span></span>|[<span data-ttu-id="acf7c-136">Exécuter le Moniteur système</span><span class="sxs-lookup"><span data-stu-id="acf7c-136">Run System Monitor</span></span>](run-system-monitor.md)|  
|<span data-ttu-id="acf7c-137">Décrit comment surveiller les compteurs de disque afin de déterminer l'activité des disque et la quantité d'E/S générées par leurs composants SQL Server.</span><span class="sxs-lookup"><span data-stu-id="acf7c-137">Describes how to monitor disk counters to determine disk activity and the amount of I/O generated by their SQL Server components.</span></span>|[<span data-ttu-id="acf7c-138">Surveiller l’utilisation du disque</span><span class="sxs-lookup"><span data-stu-id="acf7c-138">Monitor Disk Usage</span></span>](monitor-disk-usage.md)|  
|<span data-ttu-id="acf7c-139">Décrit comment surveiller une instance de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afin de déterminer si les taux d'utilisation de l'unité centrale restent dans des limites normales.</span><span class="sxs-lookup"><span data-stu-id="acf7c-139">Describes how to monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to determine whether CPU usage rates are within normal ranges.</span></span>|[<span data-ttu-id="acf7c-140">Surveiller l’utilisation de l’UC</span><span class="sxs-lookup"><span data-stu-id="acf7c-140">Monitor CPU Usage</span></span>](monitor-cpu-usage.md)|  
|<span data-ttu-id="acf7c-141">Décrit comment surveiller une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vous assurer que l'utilisation de la mémoire reste dans des limites normales.</span><span class="sxs-lookup"><span data-stu-id="acf7c-141">Describes how to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to confirm that memory usage is within typical ranges.</span></span>|[<span data-ttu-id="acf7c-142">Surveiller l’utilisation de la mémoire</span><span class="sxs-lookup"><span data-stu-id="acf7c-142">Monitor Memory Usage</span></span>](monitor-memory-usage.md)|  
|<span data-ttu-id="acf7c-143">Décrit comment créer une alerte qui est émise lorsque la valeur seuil d'un compteur du Moniteur système est atteinte.</span><span class="sxs-lookup"><span data-stu-id="acf7c-143">Describes how to create an alert that is raised when a threshold value for a System Monitor counter has been reached.</span></span>|[<span data-ttu-id="acf7c-144">Créer une alerte de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="acf7c-144">Create a SQL Server Database Alert</span></span>](create-a-sql-server-database-alert.md)|  
|<span data-ttu-id="acf7c-145">Décrit comment créer des graphiques, des alertes, des journaux et des rapports pour surveiller une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acf7c-145">Describes how to you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="acf7c-146">Créer des graphiques, des alertes, des journaux et des rapports</span><span class="sxs-lookup"><span data-stu-id="acf7c-146">Create Charts, Alerts, Logs, and Reports</span></span>](create-charts-alerts-logs-and-reports.md)|  
|<span data-ttu-id="acf7c-147">Répertorie les objets et compteurs utilisés pour analyser l'activité des ordinateurs exécutant une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acf7c-147">Lists objects and counters that System Monitor uses to monitor activity in computers running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="acf7c-148">Utiliser des objets SQL Server</span><span class="sxs-lookup"><span data-stu-id="acf7c-148">Use SQL Server Objects</span></span>](use-sql-server-objects.md)|  
|<span data-ttu-id="acf7c-149">Répertorie les objets et les compteurs que le Moniteur système utilise pour analyser l'activité de l'OLTP en mémoire.</span><span class="sxs-lookup"><span data-stu-id="acf7c-149">Lists objects and counters that System Monitor uses to monitor In-Memory OLTP activity.</span></span>|[<span data-ttu-id="acf7c-150">Les compteurs de performances de l’OLTP en mémoire &#40;de XTP&#41;</span><span class="sxs-lookup"><span data-stu-id="acf7c-150">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)|  
  
  
