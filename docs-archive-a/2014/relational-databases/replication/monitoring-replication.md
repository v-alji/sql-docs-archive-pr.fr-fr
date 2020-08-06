---
title: Surveillance de la réplication | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], about monitoring replication
- transactional replication, monitoring
- monitoring [SQL Server replication]
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
- replication [SQL Server], monitoring
- administering replication, monitoring
ms.assetid: f182f43a-6af8-45bc-a708-08d5f7a6984a
author: rothja
ms.author: jroth
ms.openlocfilehash: df2760e4ce04c95f38ceb9dfe9fa9f79c4c467f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702811"
---
# <a name="monitoring-replication"></a><span data-ttu-id="3f8f1-102">Surveillance (réplication)</span><span class="sxs-lookup"><span data-stu-id="3f8f1-102">Monitoring (Replication)</span></span>
  <span data-ttu-id="3f8f1-103">L'analyse d'une topologie de réplication est un aspect important du déploiement de la réplication.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-103">Monitoring a replication topology is an important aspect of deploying replication.</span></span> <span data-ttu-id="3f8f1-104">L'activité de la réplication étant distribuée, il est essentiel de faire le suivi de cette activité et des états à travers tous les ordinateurs impliqués dans la réplication.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-104">Because replication activity is distributed, it is essential to track activity and status across all computers involved in replication.</span></span> <span data-ttu-id="3f8f1-105">Les outils suivants peuvent être utilisés pour surveiller la réplication :</span><span class="sxs-lookup"><span data-stu-id="3f8f1-105">The following tools can be used to monitor replication:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)]<span data-ttu-id="3f8f1-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)]Moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="3f8f1-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] Replication Monitor</span></span>  
  
     <span data-ttu-id="3f8f1-107">Le moniteur de réplication est l'outil le plus important pour la surveillance de la réplication ; il donne une vision orientée serveur de publication de toute l'activité de réplication.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-107">Replication Monitor is the most important tool for monitoring replication, presenting a Publisher-focused view of all replication activity.</span></span> <span data-ttu-id="3f8f1-108">Pour plus d’informations, consultez [analyser les performances avec le moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="3f8f1-108">For more information, see [Monitor performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)] <span data-ttu-id="3f8f1-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f8f1-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span></span>  
  
     [!INCLUDE[ssManStudio](../../includes/ssManStudio-md.md)] <span data-ttu-id="3f8f1-110">donne accès au moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-110">provides access to Replication Monitor.</span></span> <span data-ttu-id="3f8f1-111">Il vous permet aussi d’afficher l’état actuel et le dernier message journalisé par les agents suivants ; il vous permet également de démarrer et d’arrêter chaque agent : Agent de lecture du journal, Agent d’instantané, Agent de fusion et Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-111">It also allows you to view the current status and last message logged by the following agents and allows you start and stop each agent: Log Reader Agent, Snapshot Agent, Merge Agent, and Distribution Agent.</span></span> <span data-ttu-id="3f8f1-112">Pour plus d’informations, voir [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span><span class="sxs-lookup"><span data-stu-id="3f8f1-112">For more information, see [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="3f8f1-113">et Replication Management Objects</span><span class="sxs-lookup"><span data-stu-id="3f8f1-113">and Replication Management Objects (RMO)</span></span>  
  
     <span data-ttu-id="3f8f1-114">Les deux interfaces vous permettent de surveiller tous les types de réplication à partir du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-114">Both interfaces allow you to monitor all types of replication from the Distributor.</span></span> <span data-ttu-id="3f8f1-115">La réplication de fusion donne également la possibilité de surveiller la réplication à partir de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-115">Merge replication also provides the ability to monitor replication from the Subscriber.</span></span>  
  
-   <span data-ttu-id="3f8f1-116">Alertes pour les événements des agents de réplication</span><span class="sxs-lookup"><span data-stu-id="3f8f1-116">Alerts for replication agent events</span></span>  
  
     <span data-ttu-id="3f8f1-117">La réplication fournit plusieurs alertes prédéfinies pour les événements des agents de réplication ; vous pouvez si nécessaire créer des alertes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-117">Replication provides a number of predefined alerts for replication agent events, and you can create additional alerts if necessary.</span></span> <span data-ttu-id="3f8f1-118">Les alertes peuvent être utilisées pour déclencher une réponse automatisée à un événement et/ou envoyer une notification à un administrateur.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-118">Alerts can be used to trigger an automated response to an event and/or notify an administrator.</span></span> <span data-ttu-id="3f8f1-119">Pour plus d’informations, consultez [Utiliser les alertes pour les événements des agents de réplication](agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="3f8f1-119">For more information, see [Use Alerts for Replication Agent Events](agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
-   <span data-ttu-id="3f8f1-120">Moniteur système</span><span class="sxs-lookup"><span data-stu-id="3f8f1-120">System Monitor</span></span>  
  
     <span data-ttu-id="3f8f1-121">Le Moniteur système peut être utilisé pour surveiller les performances à travers plusieurs compteurs dédiés à la réplication.</span><span class="sxs-lookup"><span data-stu-id="3f8f1-121">System Monitor can be useful for monitoring performance, providing a number of counters for replication.</span></span> <span data-ttu-id="3f8f1-122">Pour plus d’informations, voir [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="3f8f1-122">For more information, see [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f8f1-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f8f1-123">See Also</span></span>  
 <span data-ttu-id="3f8f1-124">[FAQ sur l’administration de la réplication](administration/frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="3f8f1-124">[Replication Administration FAQ](administration/frequently-asked-questions-for-replication-administrators.md) </span></span>  
 [<span data-ttu-id="3f8f1-125">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="3f8f1-125">Best Practices for Replication Administration</span></span>](administration/best-practices-for-replication-administration.md)   

  
  
