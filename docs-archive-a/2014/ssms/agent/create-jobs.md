---
title: Créer des travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: 465fb7fc-7622-4252-a178-ea51691c935b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 706b9348eed5b190f99543a74e7019dc1bde5978
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699240"
---
# <a name="create-jobs"></a><span data-ttu-id="39586-102">Créer des travaux</span><span class="sxs-lookup"><span data-stu-id="39586-102">Create Jobs</span></span>
  <span data-ttu-id="39586-103">Un travail est constitué d'une série d'opérations spécifiques exécutées de manière séquentielle par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="39586-103">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="39586-104">Un travail peut effectuer diverses activités, notamment exécuter des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , des applications d'invite de commandes, des scripts Microsoft ActiveX, des packages Integration Services, des commandes et des requêtes Analysis Services ou des tâches de réplication.</span><span class="sxs-lookup"><span data-stu-id="39586-104">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command prompt applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="39586-105">Les travaux peuvent exécuter des tâches répétitives ou planifiables, et même notifier automatiquement les utilisateurs de l'état d'un travail en déclenchant des alertes, ce qui simplifie de manière significative l'administration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39586-105">Jobs can run repetitive or schedulable tasks, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="39586-106">Pour créer un travail, l'utilisateur doit être membre de l'un des rôles de base de données fixes de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="39586-106">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="39586-107">Un travail ne peut être modifié que par son propriétaire ou par les membres du rôle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="39586-107">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="39586-108">Les membres du rôle **sysadmin** peuvent attribuer la propriété du travail à d’autres utilisateurs et peuvent exécuter n’importe quel travail, quel qu’en soit le propriétaire.</span><span class="sxs-lookup"><span data-stu-id="39586-108">Members of the **sysadmin** role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span> <span data-ttu-id="39586-109">Pour plus d’informations sur les rôles de base de données fixe de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consultez [Rôles de base de données fixe de SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="39586-109">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="39586-110">Les travaux peuvent être écrits de manière à s'exécuter sur l'instance locale de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou sur plusieurs instances à l'échelle d'une entreprise.</span><span class="sxs-lookup"><span data-stu-id="39586-110">Jobs can be written to run on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or on multiple instances across an enterprise.</span></span> <span data-ttu-id="39586-111">Pour exécuter des travaux sur plusieurs serveurs, vous devez configurer au moins un serveur maître et un ou plusieurs serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="39586-111">To run jobs on multiple servers, you must set up at least one master server and one or more target servers.</span></span> <span data-ttu-id="39586-112">Pour plus d’informations sur les serveurs maîtres et cibles, consultez [Administration automatisée à l’échelle d’une entreprise](automated-administration-across-an-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="39586-112">For more information about master and target servers, see [Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="39586-113">Agent enregistre dans l’historique des travaux les informations relatives aux travaux et aux étapes de travail.</span><span class="sxs-lookup"><span data-stu-id="39586-113">Agent records job and job step information in the job history.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="39586-114">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="39586-114">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39586-115">**Description**</span><span class="sxs-lookup"><span data-stu-id="39586-115">**Description**</span></span>|<span data-ttu-id="39586-116">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="39586-116">**Topic**</span></span>|  
|<span data-ttu-id="39586-117">Explique comment créer un travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39586-117">Describes how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="39586-118">Créer un travail</span><span class="sxs-lookup"><span data-stu-id="39586-118">Create a Job</span></span>](create-a-job.md)|  
|<span data-ttu-id="39586-119">Explique comment réattribuer la propriété des travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="39586-119">Describes how to reassign ownership of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>|[<span data-ttu-id="39586-120">Attribuer la propriété d'un travail à d'autres utilisateurs</span><span class="sxs-lookup"><span data-stu-id="39586-120">Give Others Ownership of a Job</span></span>](give-others-ownership-of-a-job.md)|  
|<span data-ttu-id="39586-121">Décrit la façon de définir le journal de l'historique des travaux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39586-121">Describes how to set up the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="39586-122">Set Up the Job History Log</span><span class="sxs-lookup"><span data-stu-id="39586-122">Set Up the Job History Log</span></span>](set-up-the-job-history-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="39586-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39586-123">See Also</span></span>  
 <span data-ttu-id="39586-124">[Gérer les étapes de travail](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="39586-124">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="39586-125">[Administration automatisée à l'échelle d'une entreprise](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="39586-125">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 <span data-ttu-id="39586-126">[Créer et attacher des planifications à des travaux](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="39586-126">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 <span data-ttu-id="39586-127">[Exécuter des travaux](run-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="39586-127">[Run Jobs](run-jobs.md) </span></span>  
 [<span data-ttu-id="39586-128">Afficher ou modifier les travaux</span><span class="sxs-lookup"><span data-stu-id="39586-128">View or Modify Jobs</span></span>](view-or-modify-jobs.md)  
  
  
