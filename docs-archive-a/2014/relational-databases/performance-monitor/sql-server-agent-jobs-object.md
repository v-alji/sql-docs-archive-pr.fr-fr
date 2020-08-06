---
title: SQL Server Agent, objet Jobs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLAgent:Jobs
- Jobs object
ms.assetid: 225b5e2d-4a78-4178-b2b6-b419df83c4aa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 82ee57eba20d44c08eadc125e9dfd69e73c35751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602791"
---
# <a name="sql-server-agent-jobs-object"></a><span data-ttu-id="8f4b1-102">Agent SQL Server, Objet Jobs</span><span class="sxs-lookup"><span data-stu-id="8f4b1-102">SQL Server Agent, Jobs Object</span></span>
  <span data-ttu-id="8f4b1-103">L'objet de performances **Jobs** de SQL Server Agent contient des compteurs qui fournissent des informations sur les travaux de SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-103">The SQL Server Agent **Jobs** performance object contains performance counters that report information about SQL Server Agent jobs.</span></span> <span data-ttu-id="8f4b1-104">Le tableau ci-dessous répertorie les compteurs inclus dans cet objet.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="8f4b1-105">Le tableau ci-dessous contient les compteurs **SQLAgent:Jobs** .</span><span class="sxs-lookup"><span data-stu-id="8f4b1-105">The table below contains the **SQLAgent:Jobs** counters.</span></span>  
  
|<span data-ttu-id="8f4b1-106">Nom</span><span class="sxs-lookup"><span data-stu-id="8f4b1-106">Name</span></span>|<span data-ttu-id="8f4b1-107">Description</span><span class="sxs-lookup"><span data-stu-id="8f4b1-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="8f4b1-108">**Travaux actifs**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-108">**Active Jobs**</span></span>|<span data-ttu-id="8f4b1-109">Nombre de travaux en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-109">This counter reports the number of jobs currently running.</span></span>|  
|<span data-ttu-id="8f4b1-110">**Travaux non réussis**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-110">**Failed jobs**</span></span>|<span data-ttu-id="8f4b1-111">Nombre de travaux qui se sont terminés par un échec.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-111">This counter reports the number of jobs that exited with failure.</span></span>|  
|<span data-ttu-id="8f4b1-112">**Taux de travaux réussis**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-112">**Job success rate**</span></span>|<span data-ttu-id="8f4b1-113">Pourcentage de travaux exécutés et terminés.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-113">This counter reports the percentage of executed jobs that completed successfully.</span></span>|  
|<span data-ttu-id="8f4b1-114">**Travaux activés/minute**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-114">**Jobs activated/minute**</span></span>|<span data-ttu-id="8f4b1-115">Nombre de travaux lancés au cours de la dernière minute.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-115">This counter reports the number of jobs launched within the last minute.</span></span>|  
|<span data-ttu-id="8f4b1-116">**Travaux en attente**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-116">**Queued jobs**</span></span>|<span data-ttu-id="8f4b1-117">Nombre de travaux prêts à l'exécution par l'Agent SQL Server, mais dont l'exécution n'a pas commencé.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-117">This counter reports the number of jobs that are ready for SQL Server Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="8f4b1-118">**Travaux réussis**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-118">**Successful jobs**</span></span>|<span data-ttu-id="8f4b1-119">Nombre de travaux terminés.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-119">This counter reports the number of jobs that exited with success.</span></span>|  
  
 <span data-ttu-id="8f4b1-120">Chaque compteur de l'objet contient les instances suivantes :</span><span class="sxs-lookup"><span data-stu-id="8f4b1-120">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="8f4b1-121">Instance</span><span class="sxs-lookup"><span data-stu-id="8f4b1-121">Instance</span></span>|<span data-ttu-id="8f4b1-122">Description</span><span class="sxs-lookup"><span data-stu-id="8f4b1-122">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8f4b1-123">**_Total**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-123">**_Total**</span></span>|<span data-ttu-id="8f4b1-124">Informations sur tous les travaux.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-124">Information for all jobs.</span></span>|  
|<span data-ttu-id="8f4b1-125">**Alertes**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-125">**Alerts**</span></span>|<span data-ttu-id="8f4b1-126">Informations sur les travaux lancés par des alertes.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-126">Information for jobs started by alerts.</span></span>|  
|<span data-ttu-id="8f4b1-127">**Autres**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-127">**Others**</span></span>|<span data-ttu-id="8f4b1-128">Informations sur les travaux qui n'ont pas été lancés par des alertes ou des planifications.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-128">Information for jobs that were not started by alerts or schedules.</span></span> <span data-ttu-id="8f4b1-129">Il s’agit généralement de travaux lancés manuellement au moyen de **sp_start_job**.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-129">Typically these are jobs started manually using **sp_start_job**.</span></span>|  
|<span data-ttu-id="8f4b1-130">**Planifications**</span><span class="sxs-lookup"><span data-stu-id="8f4b1-130">**Schedules**</span></span>|<span data-ttu-id="8f4b1-131">Informations sur les travaux lancés par des planifications.</span><span class="sxs-lookup"><span data-stu-id="8f4b1-131">Information for jobs started by schedules.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f4b1-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f4b1-132">See Also</span></span>  
 <span data-ttu-id="8f4b1-133">[Implémenter des travaux](../../ssms/agent/implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="8f4b1-133">[Implement Jobs](../../ssms/agent/implement-jobs.md) </span></span>  
 <span data-ttu-id="8f4b1-134">[Utiliser des objets de performance](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="8f4b1-134">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="8f4b1-135">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="8f4b1-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
