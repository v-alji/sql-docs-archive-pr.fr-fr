---
title: Utiliser des objets de performance | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- SQL Server Agent service, monitoring
- SQL Server Agent service, performance objects
- SQL Server Agent, performance objects
- performance objects [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- performance counters [SQL Server], SQL Server Agent
- counters [SQL Server], SQL Server Agent
ms.assetid: 830b843a-6b2a-4620-a51b-98358e9fc54b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7c1fe3f4a7d9a5fec901f84d8e913e49a4dbd1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611485"
---
# <a name="use-performance-objects"></a><span data-ttu-id="6ee65-102">Utiliser des objets de performance</span><span class="sxs-lookup"><span data-stu-id="6ee65-102">Use Performance Objects</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6ee65-103">Agent comprend des compteurs et des objets de performance qui permettent de surveiller le fonctionnement du service.</span><span class="sxs-lookup"><span data-stu-id="6ee65-103">Agent includes performance objects and counters to monitor how the service is performing.</span></span> <span data-ttu-id="6ee65-104">Ces objets de performance vous permettent d'utiliser un outil Windows, en l'occurrence l'Analyseur de performances, pour identifier la tâche réalisée en arrière-plan par le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="6ee65-104">These performance objects allow you to use Performance Monitor, a Windows tool, to identify what the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is doing in the background.</span></span> <span data-ttu-id="6ee65-105">Par exemple, vous pouvez identifier le nombre de travaux actifs en cours d'exécution par le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent afin de déterminer ceux qui sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="6ee65-105">For example, you can identify how many active jobs the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is currently running to identify those jobs that are blocked.</span></span>  
  
 <span data-ttu-id="6ee65-106">Les compteurs et les objets de performance du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sont disponibles pour chaque instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installée sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6ee65-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects and counters exist for each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is installed on a computer.</span></span> <span data-ttu-id="6ee65-107">Un objet de performance est nommé en fonction de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qu'il représente.</span><span class="sxs-lookup"><span data-stu-id="6ee65-107">Performance objects are named according to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that each object represents.</span></span>  
  
 <span data-ttu-id="6ee65-108">Le tableau suivant décrit la dénomination des objets de performance du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent :</span><span class="sxs-lookup"><span data-stu-id="6ee65-108">The following table shows how the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects are named:</span></span>  
  
|<span data-ttu-id="6ee65-109">Type d’instance</span><span class="sxs-lookup"><span data-stu-id="6ee65-109">Instance type</span></span>|<span data-ttu-id="6ee65-110">Nom d’objet</span><span class="sxs-lookup"><span data-stu-id="6ee65-110">Object name</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="6ee65-111">Par défaut</span><span class="sxs-lookup"><span data-stu-id="6ee65-111">Default</span></span>|<span data-ttu-id="6ee65-112">**SQLAgent:** *objet*:*compteur*</span><span class="sxs-lookup"><span data-stu-id="6ee65-112">**SQLAgent:** *object*:*counter*</span></span>|  
|<span data-ttu-id="6ee65-113">named</span><span class="sxs-lookup"><span data-stu-id="6ee65-113">Named</span></span>|<span data-ttu-id="6ee65-114">**SQLAgent$**</span><span class="sxs-lookup"><span data-stu-id="6ee65-114">**SQLAgent$**</span></span><br /> <span data-ttu-id="6ee65-115">***instance_name* :** *objet*:*compteur*</span><span class="sxs-lookup"><span data-stu-id="6ee65-115">***instance_name* :** *object*:*counter*</span></span>|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6ee65-116">comprend les objets de performance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent suivants.</span><span class="sxs-lookup"><span data-stu-id="6ee65-116">includes the following performance objects for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
|<span data-ttu-id="6ee65-117">Nom d’objet</span><span class="sxs-lookup"><span data-stu-id="6ee65-117">Object name</span></span>|<span data-ttu-id="6ee65-118">Description</span><span class="sxs-lookup"><span data-stu-id="6ee65-118">Description</span></span>|  
|-----------------|-----------------|  
|[<span data-ttu-id="6ee65-119">SQLAgent:Jobs</span><span class="sxs-lookup"><span data-stu-id="6ee65-119">SQLAgent:Jobs</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobs-object.md)|<span data-ttu-id="6ee65-120">Informations de performance relatives aux travaux démarrés, aux taux de réussite et à l'état actuel</span><span class="sxs-lookup"><span data-stu-id="6ee65-120">Performance information about jobs that have been started, success rates, and current status</span></span>|  
|[<span data-ttu-id="6ee65-121">SQLAgent:JobSteps</span><span class="sxs-lookup"><span data-stu-id="6ee65-121">SQLAgent:JobSteps</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobsteps-object.md)|<span data-ttu-id="6ee65-122">Informations d'état relatives aux étapes de travail</span><span class="sxs-lookup"><span data-stu-id="6ee65-122">Status information about job steps</span></span>|  
|[<span data-ttu-id="6ee65-123">SQLAgent:Alerts</span><span class="sxs-lookup"><span data-stu-id="6ee65-123">SQLAgent:Alerts</span></span>](../../relational-databases/performance-monitor/sql-server-agent-alerts-object.md)|<span data-ttu-id="6ee65-124">Informations relatives au nombre d'alertes et de notifications</span><span class="sxs-lookup"><span data-stu-id="6ee65-124">Information about number of alerts and notifications</span></span>|  
|[<span data-ttu-id="6ee65-125">SQLAgent:Statistics</span><span class="sxs-lookup"><span data-stu-id="6ee65-125">SQLAgent:Statistics</span></span>](../../relational-databases/performance-monitor/sql-server-agent-statistics-object.md)|<span data-ttu-id="6ee65-126">Informations générales sur les performances</span><span class="sxs-lookup"><span data-stu-id="6ee65-126">General performance information</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ee65-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ee65-127">See Also</span></span>  
 <span data-ttu-id="6ee65-128">[Surveiller et régler les performances](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span><span class="sxs-lookup"><span data-stu-id="6ee65-128">[Monitor and Tune for Performance](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span></span>  
 [<span data-ttu-id="6ee65-129">Démarrer le Moniteur système &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="6ee65-129">Start System Monitor &#40;Windows&#41;</span></span>](../../relational-databases/performance/start-system-monitor-windows.md)  
  
  
