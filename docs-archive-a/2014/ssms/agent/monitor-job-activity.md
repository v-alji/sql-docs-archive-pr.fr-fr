---
title: Surveiller l’activité des travaux | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- jobs [SQL Server Agent], monitoring
- monitoring [SQL Server], jobs
- activity monitoring [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- SQL Server Agent Job Activity Monitor
- SQL Server Agent jobs, monitoring
- performance [SQL Server], jobs
- current activity
ms.assetid: 71cb432b-631d-4b8b-9965-e731b3d8266d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5088e029e90b4556c1559f8c948e8a8734762749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603784"
---
# <a name="monitor-job-activity"></a><span data-ttu-id="ed653-102">Surveiller l'activité des travaux</span><span class="sxs-lookup"><span data-stu-id="ed653-102">Monitor Job Activity</span></span>
  <span data-ttu-id="ed653-103">Vous pouvez surveiller l'activité en cours de tous les travaux définis sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide du moniteur d'activité des travaux de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="ed653-103">You can monitor the current activity of all defined jobs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job Activity Monitor.</span></span>  
  
## <a name="sql-server-agent-sessions"></a><span data-ttu-id="ed653-104">Sessions de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="ed653-104">SQL Server Agent Sessions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ed653-105">Agent crée une session à chaque démarrage du service.</span><span class="sxs-lookup"><span data-stu-id="ed653-105">Agent creates a new session each time the service starts.</span></span> <span data-ttu-id="ed653-106">Quand une session est créée, la table **sysjobactivity** de la base de données **msdb** est remplie avec tous les travaux définis existants.</span><span class="sxs-lookup"><span data-stu-id="ed653-106">When a new session is created, the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="ed653-107">Cette table conserve la dernière activité des travaux lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent est redémarré.</span><span class="sxs-lookup"><span data-stu-id="ed653-107">This table preserves the last activity for jobs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is restarted.</span></span> <span data-ttu-id="ed653-108">Chaque session enregistre l'activité normale de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent du début à la fin du travail.</span><span class="sxs-lookup"><span data-stu-id="ed653-108">Each session records [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent normal job activity from the start of the job to its finish.</span></span> <span data-ttu-id="ed653-109">Les informations relatives à ces sessions sont stockées dans la table **syssessions** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="ed653-109">Information about these sessions is stored in the **syssessions** table of the **msdb** database.</span></span>  
  
## <a name="job-activity-monitor"></a><span data-ttu-id="ed653-110">Moniteur d'activité des travaux</span><span class="sxs-lookup"><span data-stu-id="ed653-110">Job Activity Monitor</span></span>  
 <span data-ttu-id="ed653-111">Le moniteur d’activité des travaux vous permet de visualiser la table **sysjobactivity** à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed653-111">The Job Activity Monitor allows you to view the **sysjobactivity** table by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ed653-112">Vous pouvez visualiser tous les travaux sur le serveur ou définir des filtres afin de limiter le nombre de travaux affichés.</span><span class="sxs-lookup"><span data-stu-id="ed653-112">You can view all jobs on the server, or you can define filters to limit the number of jobs displayed.</span></span> <span data-ttu-id="ed653-113">Vous pouvez également trier les informations sur les travaux en cliquant sur un en-tête de colonne dans la grille **Activité du travail de l’Agent** .</span><span class="sxs-lookup"><span data-stu-id="ed653-113">You can also sort the job information by clicking on a column heading in the **Agent Job Activity** grid.</span></span> <span data-ttu-id="ed653-114">Par exemple, quand vous sélectionnez l’en-tête de colonne **Dernière exécution** , vous pouvez visualiser les travaux dans l’ordre de leur dernière exécution.</span><span class="sxs-lookup"><span data-stu-id="ed653-114">For example, when you select the **Last Run** column heading, you can view the jobs in the order that they were last run.</span></span> <span data-ttu-id="ed653-115">Vous pouvez cliquer sur l'en-tête de la colonne pour classer les travaux en fonction de la date de leur dernière exécution, dans l'ordre croissant ou décroissant.</span><span class="sxs-lookup"><span data-stu-id="ed653-115">Clicking the column heading again toggles the jobs in ascending and descending order based on their last run date.</span></span>  
  
 <span data-ttu-id="ed653-116">Le moniteur d'activité des travaux vous permet d'effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed653-116">Using the Job Activity Monitor you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ed653-117">Démarrer et arrêter des travaux.</span><span class="sxs-lookup"><span data-stu-id="ed653-117">Start and stop jobs.</span></span>  
  
-   <span data-ttu-id="ed653-118">Visualiser les propriétés des travaux.</span><span class="sxs-lookup"><span data-stu-id="ed653-118">View job properties.</span></span>  
  
-   <span data-ttu-id="ed653-119">Visualiser l'historique d'un travail spécifique.</span><span class="sxs-lookup"><span data-stu-id="ed653-119">View the history for a specific job.</span></span>  
  
-   <span data-ttu-id="ed653-120">Actualiser les informations de la grille **Activité du travail de l’Agent** manuellement ou définir un intervalle d’actualisation automatique en cliquant sur **Afficher les paramètres d’actualisation**.</span><span class="sxs-lookup"><span data-stu-id="ed653-120">Refresh the information in the **Agent Job Activity** grid manually or set an automatic refresh interval by clicking **View refresh settings**.</span></span>  
  
 <span data-ttu-id="ed653-121">Utilisez le moniteur d'activité des travaux pour connaître les travaux dont l'exécution a été planifiée, le dernier résultat des travaux exécutés pendant la session actuelle et les travaux en cours d'exécution ou inactifs.</span><span class="sxs-lookup"><span data-stu-id="ed653-121">Use the Job Activity Monitor when you want to find out what jobs are scheduled to run, the last outcome of jobs that have run during the current session, and to find out which jobs are currently running or idle.</span></span> <span data-ttu-id="ed653-122">Si le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent échoue de manière inattendue, vous pouvez déterminer quels étaient les travaux en cours d'exécution en consultant la session précédente dans le moniteur d'activité des travaux.</span><span class="sxs-lookup"><span data-stu-id="ed653-122">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service fails unexpectedly, you can determine which jobs were in the middle of being executed by looking at the previous session in the Job Activity Monitor.</span></span>  
  
 <span data-ttu-id="ed653-123">Pour ouvrir le moniteur d’activité des travaux, développez **SQL Server Agent** dans l’Explorateur d’objets de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , cliquez avec le bouton droit sur **Moniteur d’activité des travaux**, puis cliquez sur **Afficher l’activité du travail**.</span><span class="sxs-lookup"><span data-stu-id="ed653-123">To open the Job Activity Monitor, expand **SQL Server Agent** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Object Explorer, right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
 <span data-ttu-id="ed653-124">Vous pouvez également visualiser l’activité des travaux de la session actuelle à l’aide de la procédure stockée **sp_help_jobactivity**.</span><span class="sxs-lookup"><span data-stu-id="ed653-124">You can also view job activity for the current session by using the stored procedure **sp_help_jobactivity**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ed653-125">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ed653-125">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed653-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="ed653-126">**Description**</span></span>|<span data-ttu-id="ed653-127">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="ed653-127">**Topic**</span></span>|  
|<span data-ttu-id="ed653-128">Explique comment afficher l'état d'exécution des travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed653-128">Describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="ed653-129">Afficher l’activité du travail</span><span class="sxs-lookup"><span data-stu-id="ed653-129">View Job Activity</span></span>](view-job-activity.md)|  
  
## <a name="see-also"></a><span data-ttu-id="ed653-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed653-130">See Also</span></span>  
 <span data-ttu-id="ed653-131">[Afficher l’activité du travail](view-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="ed653-131">[View Job Activity](view-job-activity.md) </span></span>  
 <span data-ttu-id="ed653-132">[dbo.sysjobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed653-132">[dbo.sysjobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span></span>  
 <span data-ttu-id="ed653-133">[Sessionsdbo.sys&#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed653-133">[dbo.syssessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span></span>  
 [<span data-ttu-id="ed653-134">sp_help_jobactivity &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ed653-134">sp_help_jobactivity &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql)  
  
  
