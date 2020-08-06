---
title: SQL Server, Broker Activation (objet) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Broker Activation
- Broker Activation object
ms.assetid: cd9b6880-c924-42c7-b333-09c303317c0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4048c2baecaeb4bde7a1e215a15e8c51a60a01bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699521"
---
# <a name="sql-server-broker-activation-object"></a><span data-ttu-id="c4f74-102">SQL Server: Broker Activation (objet)</span><span class="sxs-lookup"><span data-stu-id="c4f74-102">SQL Server, Broker Activation Object</span></span>
  <span data-ttu-id="c4f74-103">L'objet de performance **SQLServer:BrokerActivation** contient des compteurs de performances qui fournissent des informations sur l'activation des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="c4f74-103">The **SQLServer:BrokerActivation** performance object contains performance counters that report information on stored procedure activation.</span></span> <span data-ttu-id="c4f74-104">Le tableau ci-dessous répertorie les compteurs inclus dans cet objet.</span><span class="sxs-lookup"><span data-stu-id="c4f74-104">The table below lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="c4f74-105">Compteurs de SQL Server Broker Activation</span><span class="sxs-lookup"><span data-stu-id="c4f74-105">SQL Server Broker Activation counters</span></span>|<span data-ttu-id="c4f74-106">Description</span><span class="sxs-lookup"><span data-stu-id="c4f74-106">Description</span></span>|  
|-------------------------------------------|-----------------|  
|<span data-ttu-id="c4f74-107">**Appels de procédures stockées/s**</span><span class="sxs-lookup"><span data-stu-id="c4f74-107">**Stored Procedures Invoked/sec**</span></span>|<span data-ttu-id="c4f74-108">Ce compteur indique le nombre total de procédures stockées d'activation appelées par seconde par tous les moniteurs de file d'attente de l'instance.</span><span class="sxs-lookup"><span data-stu-id="c4f74-108">This counter reports the total number of activation stored procedures invoked by all queue monitors in the instance per second.</span></span>|  
|<span data-ttu-id="c4f74-109">**Limite de tâches atteinte**</span><span class="sxs-lookup"><span data-stu-id="c4f74-109">**Task Limit Reached**</span></span>|<span data-ttu-id="c4f74-110">Ce compteur indique le nombre total de fois qu'un démarrage d'une nouvelle tâche par un moniteur de file d'attente a avorté du fait que le nombre maximal de tâches pour cette file est déjà en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c4f74-110">This counter reports the total number of times that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="c4f74-111">**Limite de tâches atteinte/s**</span><span class="sxs-lookup"><span data-stu-id="c4f74-111">**Task Limit Reached/sec**</span></span>|<span data-ttu-id="c4f74-112">Ce compteur indique le nombre de fois par seconde qu'un démarrage d'une nouvelle tâche par un moniteur de file d'attente a avorté du fait que le nombre maximal de tâches pour cette file est déjà en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c4f74-112">This counter reports the number of times per second that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="c4f74-113">**Tâches abandonnées/s**</span><span class="sxs-lookup"><span data-stu-id="c4f74-113">**Tasks Aborted/sec**</span></span>|<span data-ttu-id="c4f74-114">Ce compteur signale le nombre de tâches de procédures stockées d'activation s'étant soldées par une erreur ou ayant été abandonnées par un moniteur de file d'attente du fait de la non-réception de messages.</span><span class="sxs-lookup"><span data-stu-id="c4f74-114">This counter reports the number of activation stored procedure tasks that end with an error, or are aborted by a queue monitor for failing to receive messages.</span></span>|  
|<span data-ttu-id="c4f74-115">**Tâches en cours d'exécution**</span><span class="sxs-lookup"><span data-stu-id="c4f74-115">**Tasks Running**</span></span>|<span data-ttu-id="c4f74-116">Ce compteur fait état du nombre de procédures stockées d'activation en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c4f74-116">This counter reports the number of activation stored procedures that are currently running.</span></span>|  
|<span data-ttu-id="c4f74-117">**Tâches démarrées/s**</span><span class="sxs-lookup"><span data-stu-id="c4f74-117">**Tasks Started/sec**</span></span>|<span data-ttu-id="c4f74-118">Ce compteur indique le nombre de procédures stockées d'activation appelées par seconde par tous les moniteurs de file d'attente de l'instance.</span><span class="sxs-lookup"><span data-stu-id="c4f74-118">This counter reports the number of activation stored procedures started per second by all queue monitors in the instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4f74-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4f74-119">See Also</span></span>  
 <span data-ttu-id="c4f74-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4f74-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span></span>  
 <span data-ttu-id="c4f74-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4f74-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span></span>  
 [<span data-ttu-id="c4f74-122">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="c4f74-122">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
