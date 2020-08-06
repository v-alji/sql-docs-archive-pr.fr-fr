---
title: Créer des graphiques, des alertes, des journaux et des rapports | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], charts and reports
- charts [SQL Server]
- reports [SQL Server]
- reports [SQL Server], creating
- Windows System Monitor [SQL Server], charts and reports
- logs [SQL Server], System Monitor
- System Monitor [SQL Server], logs
- Windows System Monitor [SQL Server], logs
ms.assetid: c9162b37-e5dc-43d1-a3aa-1e9ebc69fecc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a0c95c3f483a8af3e3e68d9c5c7d3caf44350d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707411"
---
# <a name="create-charts-alerts-logs-and-reports"></a><span data-ttu-id="c5266-102">Créer des graphiques, des alertes, des journaux et des rapports</span><span class="sxs-lookup"><span data-stu-id="c5266-102">Create Charts, Alerts, Logs, and Reports</span></span>
  <span data-ttu-id="c5266-103">Le Moniteur système vous permet de créer des graphiques, des alertes, des journaux et des rapports pour surveiller une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5266-103">System Monitor lets you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="charts"></a><span data-ttu-id="c5266-104">Graphiques</span><span class="sxs-lookup"><span data-stu-id="c5266-104">Charts</span></span>  
 <span data-ttu-id="c5266-105">Les graphiques permettent de surveiller les performances en cours des objets et des compteurs sélectionnés (par exemple l'utilisation de l'UC ou les E/S du disque).</span><span class="sxs-lookup"><span data-stu-id="c5266-105">Charts can monitor the current performance of selected objects and counters; for example, the CPU usage or disk I/O.</span></span> <span data-ttu-id="c5266-106">Il est possible d'ajouter à un graphique diverses combinaisons d'objets et de compteurs du Moniteur système.</span><span class="sxs-lookup"><span data-stu-id="c5266-106">You can add to a chart various combinations of System Monitor objects and counters.</span></span> <span data-ttu-id="c5266-107">Vous pouvez également ajouter des objets et compteurs [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows à un graphique.</span><span class="sxs-lookup"><span data-stu-id="c5266-107">You also can add [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows objects and counters to a chart.</span></span>  
  
 <span data-ttu-id="c5266-108">Chaque graphique représente un sous-ensemble des informations à surveiller.</span><span class="sxs-lookup"><span data-stu-id="c5266-108">Each chart represents a subset of information you want to monitor.</span></span> <span data-ttu-id="c5266-109">Par exemple, un premier graphique peut assurer le suivi des statistiques d'utilisation de la mémoire et un deuxième celui des E/S du disque.</span><span class="sxs-lookup"><span data-stu-id="c5266-109">For example, one chart can track memory usage statistics and a second chart can track disk I/O statistics.</span></span>  
  
 <span data-ttu-id="c5266-110">L'utilisation d'un graphique peut s'avérer utile pour les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="c5266-110">Using a chart can be useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="c5266-111">rechercher l'explication de la lenteur ou de l'inefficacité d'un ordinateur ou d'une application ;</span><span class="sxs-lookup"><span data-stu-id="c5266-111">Investigating why a computer or application is slow or inefficient.</span></span>  
  
-   <span data-ttu-id="c5266-112">surveiller les systèmes en continu pour détecter des problèmes de performances intermittents ;</span><span class="sxs-lookup"><span data-stu-id="c5266-112">Continually monitoring systems to find intermittent performance problems.</span></span>  
  
-   <span data-ttu-id="c5266-113">comprendre pourquoi la capacité doit être accrue ;</span><span class="sxs-lookup"><span data-stu-id="c5266-113">Discovering why you need to increase capacity.</span></span>  
  
-   <span data-ttu-id="c5266-114">afficher une tendance sous forme de courbe ;</span><span class="sxs-lookup"><span data-stu-id="c5266-114">Displaying a trend as a line chart.</span></span>  
  
-   <span data-ttu-id="c5266-115">afficher une comparaison sous forme d'histogramme.</span><span class="sxs-lookup"><span data-stu-id="c5266-115">Displaying a comparison as a histogram chart.</span></span>  
  
 <span data-ttu-id="c5266-116">Les graphiques sont utiles pour une surveillance à cours terme et en temps réel d'un ordinateur local ou distant (par exemple pour surveiller un événement lorsqu'il se produit).</span><span class="sxs-lookup"><span data-stu-id="c5266-116">Charts are useful for short-term, real-time monitoring of a local or remote computer (for example, when you want to monitor an event as it occurs).</span></span>  
  
## <a name="alerts"></a><span data-ttu-id="c5266-117">Alertes</span><span class="sxs-lookup"><span data-stu-id="c5266-117">Alerts</span></span>  
 <span data-ttu-id="c5266-118">En utilisant des alertes, le Moniteur système peut suivre des événements spécifiques et vous les signaler si vous le lui avez demandé.</span><span class="sxs-lookup"><span data-stu-id="c5266-118">Using alerts, System Monitor tracks specific events and notifies you of these events as requested.</span></span> <span data-ttu-id="c5266-119">Un journal d'alerte peut surveiller les performances en cours des compteurs sélectionnés et les instances des objets de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5266-119">An alert log can monitor the current performance of selected counters and instances for objects in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c5266-120">Quand un compteur dépasse une valeur donnée, le journal enregistre la date et l'heure de l'événement.</span><span class="sxs-lookup"><span data-stu-id="c5266-120">When a counter exceeds a given value, the log records the date and time of the event.</span></span> <span data-ttu-id="c5266-121">Un événement peut également générer une alerte sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="c5266-121">An event can also generate a network alert.</span></span> <span data-ttu-id="c5266-122">Vous pouvez spécifier le programme qui sera exécuté la première fois, ou à chaque fois, qu'un événement se produit.</span><span class="sxs-lookup"><span data-stu-id="c5266-122">You can have a specified program run the first time or every time an event occurs.</span></span> <span data-ttu-id="c5266-123">Par exemple, une alerte peut envoyer un message sur le réseau à tous les administrateurs du système pour les avertir que l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est bientôt à court d'espace disque.</span><span class="sxs-lookup"><span data-stu-id="c5266-123">For example, an alert can send a network message to all system administrators that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is getting low on disk space.</span></span>  
  
## <a name="logs"></a><span data-ttu-id="c5266-124">Journaux d’activité</span><span class="sxs-lookup"><span data-stu-id="c5266-124">Logs</span></span>  
 <span data-ttu-id="c5266-125">Les journaux vous permettent d'enregistrer les informations relatives à l'activité en cours des objets et des ordinateurs sélectionnés afin de les afficher et de les analyser ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="c5266-125">Logs allow you to record information on the current activity of selected objects and computers for later viewing and analysis.</span></span> <span data-ttu-id="c5266-126">Vous pouvez regrouper des données de plusieurs systèmes dans un seul fichier journal.</span><span class="sxs-lookup"><span data-stu-id="c5266-126">You can collect data from multiple systems into a single log file.</span></span> <span data-ttu-id="c5266-127">Par exemple, vous pouvez créer divers journaux afin de réunir les informations relatives aux performances des objets sélectionnés sur divers ordinateurs en vue d'une analyse future.</span><span class="sxs-lookup"><span data-stu-id="c5266-127">For example, you can create different logs to accumulate information about the performance of selected objects on various computers for future analysis.</span></span> <span data-ttu-id="c5266-128">Vous pouvez sauvegarder ces sélections sous un nom de fichier et les réutiliser pour créer, à des fins de comparaison, un autre journal contenant des informations similaires.</span><span class="sxs-lookup"><span data-stu-id="c5266-128">You can save these selections under a file name and reuse them when you want to create another log of similar information for comparison.</span></span>  
  
 <span data-ttu-id="c5266-129">Les fichiers journaux sont riches en informations utiles pour le dépannage ou la planification.</span><span class="sxs-lookup"><span data-stu-id="c5266-129">Log files provide a wealth of information for troubleshooting or planning.</span></span> <span data-ttu-id="c5266-130">Alors que les graphiques, les alertes, et les rapports relatifs à l'activité en cours offrent une réponse instantanée, les fichiers journaux vous permettent de suivre les compteurs sur une longue durée.</span><span class="sxs-lookup"><span data-stu-id="c5266-130">Whereas charts, alerts, and reports on current activity provide instant feedback, log files enable you to track counters over a long period of time.</span></span> <span data-ttu-id="c5266-131">Ainsi, vous pouvez étudier les informations plus en détail, afin de documenter les performances du système.</span><span class="sxs-lookup"><span data-stu-id="c5266-131">Thus, you can examine information more thoroughly and document system performance.</span></span>  
  
## <a name="reports"></a><span data-ttu-id="c5266-132">Rapports</span><span class="sxs-lookup"><span data-stu-id="c5266-132">Reports</span></span>  
 <span data-ttu-id="c5266-133">Les rapports vous permettent d'afficher les valeurs de compteurs et d'instances qui varient constamment pour les objets sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="c5266-133">Reports allow you to display constantly changing counter and instance values for selected objects.</span></span> <span data-ttu-id="c5266-134">Les valeurs apparaissent en colonnes pour chaque instance.</span><span class="sxs-lookup"><span data-stu-id="c5266-134">Values appear in columns for each instance.</span></span> <span data-ttu-id="c5266-135">Vous pouvez définir l'intervalle séparant chaque rapport, imprimer des instantanés et exporter des données.</span><span class="sxs-lookup"><span data-stu-id="c5266-135">You can adjust report intervals, print snapshots, and export data.</span></span> <span data-ttu-id="c5266-136">Utilisez les rapports pour afficher les nombres bruts.</span><span class="sxs-lookup"><span data-stu-id="c5266-136">Use reports when you need to display the raw numbers.</span></span>  
  
 <span data-ttu-id="c5266-137">Pour plus d'informations sur la création des graphiques, alertes, journaux et rapports, ou encore sur les objets et compteurs de Windows, consultez la documentation de Windows.</span><span class="sxs-lookup"><span data-stu-id="c5266-137">For more information about creating charts, alerts, logs, and reports, or about Windows objects and counters, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5266-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c5266-138">See Also</span></span>  
 [<span data-ttu-id="c5266-139">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="c5266-139">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
