---
title: Créer des planifications et les attacher à des travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server]
- scheduling jobs [SQL Server]
- jobs [SQL Server], scheduling
- CPU [SQL Server], idle conditions
- automatic job processing
- SQL Server Agent jobs, scheduling
- idle time [SQL Server]
ms.assetid: 079c2984-0052-4a37-a2b8-4ece56e6b6b5
author: stevestein
ms.author: sstein
ms.openlocfilehash: ced47013b6552725e6350b113a3722b066016a6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699258"
---
# <a name="create-and-attach-schedules-to-jobs"></a><span data-ttu-id="d9bd3-102">Créer des planifications et les attacher à des travaux</span><span class="sxs-lookup"><span data-stu-id="d9bd3-102">Create and Attach Schedules to Jobs</span></span>
  <span data-ttu-id="d9bd3-103">La planification des travaux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent consiste à définir la ou les conditions qui déclenchent leur exécution sans intervention de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-103">Scheduling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs means defining the condition or conditions that cause the job to begin running without user interaction.</span></span> <span data-ttu-id="d9bd3-104">Vous pouvez planifier l'exécution automatique d'un travail en lui créant une planification ou en lui attachant une planification existante.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-104">You can schedule a job to run automatically by creating a new schedule for the job, or by attaching an existing schedule to the job.</span></span>  
  
 <span data-ttu-id="d9bd3-105">Il existe deux méthodes pour créer une planification :</span><span class="sxs-lookup"><span data-stu-id="d9bd3-105">There are two ways to create a schedule:</span></span>  
  
-   <span data-ttu-id="d9bd3-106">Créez la planification en même temps que vous créez un travail.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-106">Create the schedule while you are creating a job.</span></span>  
  
-   <span data-ttu-id="d9bd3-107">Créez la planification dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-107">Create the schedule in Object Explorer.</span></span>  
  
 <span data-ttu-id="d9bd3-108">Une fois la planification créée, vous pouvez l'attacher à plusieurs travaux, même si elle a été conçue pour un travail spécifique.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-108">After a schedule has been created, you can attach that schedule to multiple jobs, even if the schedule was created for a specific job.</span></span> <span data-ttu-id="d9bd3-109">Vous pouvez également détacher une planification d'un travail.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-109">You can also detach schedules from jobs.</span></span>  
  
 <span data-ttu-id="d9bd3-110">Une planification peut être définie par rapport à une heure ou un événement.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-110">A schedule can be based upon time or an event.</span></span> <span data-ttu-id="d9bd3-111">Par exemple, vous pouvez planifier l'exécution d'un travail aux moments suivants :</span><span class="sxs-lookup"><span data-stu-id="d9bd3-111">For example, you can schedule a job to run at the following times:</span></span>  
  
-   <span data-ttu-id="d9bd3-112">au moment où l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] démarre ;</span><span class="sxs-lookup"><span data-stu-id="d9bd3-112">Whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts.</span></span>  
  
-   <span data-ttu-id="d9bd3-113">au moment où l'utilisation de l'UC atteint le niveau d'inactivité que vous avez défini ;</span><span class="sxs-lookup"><span data-stu-id="d9bd3-113">Whenever CPU utilization of the computer is at a level you have defined as idle.</span></span>  
  
-   <span data-ttu-id="d9bd3-114">ponctuellement, à une date et une heure spécifiques ;</span><span class="sxs-lookup"><span data-stu-id="d9bd3-114">One time, at a specific date and time.</span></span>  
  
-   <span data-ttu-id="d9bd3-115">Selon une planification récurrente.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-115">On a recurring schedule.</span></span>  
  
 <span data-ttu-id="d9bd3-116">Vous pouvez remplacer vos planifications du travail par des alertes qui répondent à un événement par l'exécution d'un travail.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-116">As an alternative to job schedules, you can also create an alert that responds to an event by running a job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9bd3-117">Une seule instance du travail peut être exécutée à la fois.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-117">Only one instance of the job can be run at a time.</span></span> <span data-ttu-id="d9bd3-118">Si vous exécutez un travail manuellement alors qu'il est en train de s'exécuter d'après une planification, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] refuse la demande.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-118">If you try to run a job manually while it is running as scheduled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refuses the request.</span></span>  
  
 <span data-ttu-id="d9bd3-119">Pour empêcher l'exécution d'un travail planifié, vous devez effectuer l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9bd3-119">To prevent a scheduled job from running, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="d9bd3-120">désactiver la planification ;</span><span class="sxs-lookup"><span data-stu-id="d9bd3-120">Disable the schedule.</span></span>  
  
-   <span data-ttu-id="d9bd3-121">désactiver le travail ;</span><span class="sxs-lookup"><span data-stu-id="d9bd3-121">Disable the job.</span></span>  
  
-   <span data-ttu-id="d9bd3-122">détacher la planification du travail ;</span><span class="sxs-lookup"><span data-stu-id="d9bd3-122">Detach the schedule from the job.</span></span>  
  
-   <span data-ttu-id="d9bd3-123">arrêter le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ;</span><span class="sxs-lookup"><span data-stu-id="d9bd3-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
-   <span data-ttu-id="d9bd3-124">supprimer la planification.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-124">Delete the schedule.</span></span>  
  
 <span data-ttu-id="d9bd3-125">Si la planification n'est pas activée, le travail peut toujours s'exécuter en réponse à une alerte ou lorsqu'un utilisateur l'exécute manuellement.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-125">If the schedule is not enabled, the job can still run in response to an alert or when a user runs the job manually.</span></span> <span data-ttu-id="d9bd3-126">Lorsqu'une planification du travail n'est pas activée, elle ne l'est pas pour aucun travail qui l'utilise normalement.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-126">When a job schedule is not enabled, the schedule is not enabled for any job that uses the schedule.</span></span>  
  
 <span data-ttu-id="d9bd3-127">Une planification désactivée doit être réactivée de manière explicite.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-127">You must explicitly re-enable a schedule that has been disabled.</span></span> <span data-ttu-id="d9bd3-128">Le simple fait de modifier une planification ne la réactive pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-128">Editing the schedule does not automatically re-enable the schedule.</span></span>  
  
## <a name="scheduling-start-dates"></a><span data-ttu-id="d9bd3-129">Planification de dates de début</span><span class="sxs-lookup"><span data-stu-id="d9bd3-129">Scheduling Start Dates</span></span>  
 <span data-ttu-id="d9bd3-130">La date de début d'une planification doit être supérieure ou égale à 19900101.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-130">The start date of a schedule must be greater than or equal to 19900101.</span></span>  
  
 <span data-ttu-id="d9bd3-131">Lorsque vous attachez une planification à un travail, vous devez examiner la date de début utilisée par la planification la première fois qu'elle exécute le travail.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-131">When you are attaching a schedule to a job, you should review the start date that the schedule uses to run the job for the first time.</span></span> <span data-ttu-id="d9bd3-132">La date de début dépend du jour et de l'heure auxquels vous attachez la planification au travail.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-132">The start date depends upon the day and time when you attach the schedule to the job.</span></span> <span data-ttu-id="d9bd3-133">Par exemple, supposons que vous créez une planification qui s'exécute un lundi sur deux à 8h00.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-133">For example, you create a schedule that runs every other Monday at 8:00 A.M.</span></span> <span data-ttu-id="d9bd3-134">Si vous créez un travail à 10h00</span><span class="sxs-lookup"><span data-stu-id="d9bd3-134">If you create a job at 10:00 A.M.</span></span> <span data-ttu-id="d9bd3-135">le lundi 3 mars 2008, la date de début de la planification est le lundi 17 mars 2008.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-135">on Monday, March 3, 2008, the schedule start date is Monday, March 17, 2008.</span></span> <span data-ttu-id="d9bd3-136">Si vous créez un autre travail le mardi 4 mars 2008, la date de début de la planification est le lundi 10 mars 2008.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-136">If you create another job on Tuesday, March 4, 2008, the schedule start date is Monday, March 10, 2008.</span></span>  
  
 <span data-ttu-id="d9bd3-137">Une fois la planification attachée à un travail, vous pouvez modifier sa date de début.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-137">You can change the schedule start date after you attach the schedule to a job.</span></span>  
  
## <a name="cpu-idle-schedules"></a><span data-ttu-id="d9bd3-138">Planifications pendant l'inactivité de l'UC</span><span class="sxs-lookup"><span data-stu-id="d9bd3-138">CPU Idle Schedules</span></span>  
 <span data-ttu-id="d9bd3-139">Pour augmenter les ressources de l'UC, vous pouvez définir une condition d'inactivité de l'UC pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-139">To maximize CPU resources, you can define a CPU idle condition for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d9bd3-140">Agent utilise ce paramètre pour déterminer le meilleur moment pour l’exécution des travaux.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-140">Agent uses the CPU idle condition setting to determine the best time to run jobs.</span></span> <span data-ttu-id="d9bd3-141">Par exemple, vous pouvez planifier un travail de reconstruction des index lorsque l'UC est inactive et pendant des périodes de production moins chargées.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-141">For example, you can schedule a job to rebuild indexes during CPU idle time and slow production periods.</span></span>  
  
 <span data-ttu-id="d9bd3-142">Avant de définir des travaux à exécuter pendant l'inactivité de l'UC, déterminez la charge de l'UC en situation d'utilisation normale.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-142">Before you define jobs to run during CPU idle time, determine the load on the CPU during normal processing.</span></span> <span data-ttu-id="d9bd3-143">Pour ce faire, utilisez le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou l'Analyseur de performances pour surveiller le trafic serveur et rassembler les statistiques.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-143">To do this, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor server traffic and collect statistics.</span></span> <span data-ttu-id="d9bd3-144">Ensuite, à l'aide des informations rassemblées, déterminez le pourcentage et la durée d'inactivité de l'UC.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-144">You can then use the information you gather to set the CPU idle time percentage and duration.</span></span>  
  
 <span data-ttu-id="d9bd3-145">Définissez l'inactivité de l'UC comme un pourcentage en dessous duquel l'utilisation de l'UC doit se maintenir pendant une période donnée.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-145">Define the CPU idle condition as a percentage below which CPU usage must remain for a specified time.</span></span> <span data-ttu-id="d9bd3-146">Définissez ensuite la durée.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-146">Next, set the amount of time.</span></span> <span data-ttu-id="d9bd3-147">Lorsque le taux d'utilisation de l'UC reste inférieur au pourcentage spécifié pendant un certain temps (défini par l'utilisateur), l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] démarre tous les travaux dont l'exécution est planifiée aux moments d'inactivité de l'UC.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-147">When the CPU usage is below the specified percentage for the specified amount of time, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts all jobs that have a CPU idle time schedule.</span></span> <span data-ttu-id="d9bd3-148">Pour plus d’informations sur l’utilisation de ou de l' [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Analyseur de performances pour surveiller l’utilisation de l’UC, consultez [surveiller l’utilisation du processeur](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span><span class="sxs-lookup"><span data-stu-id="d9bd3-148">For more information on using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor CPU usage, see [Monitor CPU Usage](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d9bd3-149">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="d9bd3-149">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9bd3-150">**Description**</span><span class="sxs-lookup"><span data-stu-id="d9bd3-150">**Description**</span></span>|<span data-ttu-id="d9bd3-151">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="d9bd3-151">**Topic**</span></span>|  
|<span data-ttu-id="d9bd3-152">Décrit la méthode à suivre pour créer la planification d'un travail [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-152">Describes how to create a schedule for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="d9bd3-153">Créer une planification</span><span class="sxs-lookup"><span data-stu-id="d9bd3-153">Create a Schedule</span></span>](create-a-schedule.md)|  
|<span data-ttu-id="d9bd3-154">Décrit la méthode à suivre pour planifier un travail [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-154">Describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="d9bd3-155">Planifier un travail</span><span class="sxs-lookup"><span data-stu-id="d9bd3-155">Schedule a Job</span></span>](schedule-a-job.md)|  
|<span data-ttu-id="d9bd3-156">Indique comment définir la condition d'inactivité de l'UC pour votre serveur.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-156">Explains how to define the CPU idle condition for your server.</span></span>|[<span data-ttu-id="d9bd3-157">Définir le seuil et la durée d’inactivité de l’UC &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d9bd3-157">Set CPU Idle Time and Duration &#40;SQL Server Management Studio&#41;</span></span>](set-cpu-idle-time-and-duration-sql-server-management-studio.md)|  
  
## <a name="see-also"></a><span data-ttu-id="d9bd3-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9bd3-158">See Also</span></span>  
 <span data-ttu-id="d9bd3-159">[sp_help_jobschedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d9bd3-159">[sp_help_jobschedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span></span>  
 [<span data-ttu-id="d9bd3-160">dbo.sysJobSchedules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d9bd3-160">dbo.sysjobschedules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobschedules-transact-sql)  
  
  
