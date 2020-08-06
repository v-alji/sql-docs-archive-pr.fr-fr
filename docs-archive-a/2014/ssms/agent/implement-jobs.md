---
title: Implémenter des travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent]
- SQL Server Agent jobs
- SQL Server Agent jobs, about jobs
- jobs [SQL Server Agent], about jobs
ms.assetid: 69e06724-25c7-4fb3-8a5b-3d4596f21756
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1925b3113db8d7c57ac4344958c0247763cfd1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600455"
---
# <a name="implement-jobs"></a><span data-ttu-id="10544-102">Implémenter des travaux</span><span class="sxs-lookup"><span data-stu-id="10544-102">Implement Jobs</span></span>
  <span data-ttu-id="10544-103">Vous pouvez utiliser les travaux de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pour automatiser les tâches d'administration régulières et les exécuter de façon récurrente, dans le but de rendre l'administration plus efficace.</span><span class="sxs-lookup"><span data-stu-id="10544-103">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to automate routine administrative tasks and run them on a recurring basis, making administration more efficient.</span></span>  
  
 <span data-ttu-id="10544-104">Un travail est constitué d'une série d'opérations spécifiques exécutées de manière séquentielle par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="10544-104">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="10544-105">Un travail peut effectuer une grande variété d'activités, y compris l'exécution de scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , d'applications de ligne de commande, de scripts Microsoft ActiveX, de packages Integration Services, de commandes et de requêtes Analysis Services ou de tâches de réplication.</span><span class="sxs-lookup"><span data-stu-id="10544-105">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command-line applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="10544-106">Les travaux peuvent exécuter des tâches répétitives ou des tâches planifiables ; en outre, ils peuvent notifier leur état automatiquement aux utilisateurs en générant des alertes, ce qui simplifie grandement l'administration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10544-106">Jobs can run repetitive tasks or those that can be scheduled, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="10544-107">Vous pouvez exécuter un travail manuellement ou le configurer de manière à ce qu'il s'exécute en fonction d'une planification ou en réponse à des alertes.</span><span class="sxs-lookup"><span data-stu-id="10544-107">You can run a job manually, or you can configure it to run according to a schedule or in response to alerts.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="10544-108">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="10544-108">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10544-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="10544-109">**Description**</span></span>|<span data-ttu-id="10544-110">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="10544-110">**Topic**</span></span>|  
|<span data-ttu-id="10544-111">Contient des informations sur la création de travaux et l'affectation de propriétés.</span><span class="sxs-lookup"><span data-stu-id="10544-111">Contains information about creating jobs and assigning ownership.</span></span>|[<span data-ttu-id="10544-112">Créer des travaux</span><span class="sxs-lookup"><span data-stu-id="10544-112">Create Jobs</span></span>](create-jobs.md)|  
|<span data-ttu-id="10544-113">Contient des informations sur l'organisation des travaux en catégories.</span><span class="sxs-lookup"><span data-stu-id="10544-113">Contains information about organizing jobs into categories.</span></span>|[<span data-ttu-id="10544-114">organiser les travaux</span><span class="sxs-lookup"><span data-stu-id="10544-114">Organize Jobs</span></span>](organize-jobs.md)|  
|<span data-ttu-id="10544-115">Contient des informations relatives aux différents types d'étapes de travail que vous pouvez gérer et à la procédure à suivre à cet effet.</span><span class="sxs-lookup"><span data-stu-id="10544-115">Contains information about the different kinds of job steps you can create and how to manage them.</span></span>|[<span data-ttu-id="10544-116">Gérer les étapes de travail</span><span class="sxs-lookup"><span data-stu-id="10544-116">Manage Job Steps</span></span>](manage-job-steps.md)|  
|<span data-ttu-id="10544-117">Contient des informations relatives à la planification du démarrage de l'exécution des travaux et à leur fréquence d'exécution.</span><span class="sxs-lookup"><span data-stu-id="10544-117">Contains information about how to define when jobs start running and how often they should run.</span></span>|[<span data-ttu-id="10544-118">Créer des planifications et les attacher à des travaux</span><span class="sxs-lookup"><span data-stu-id="10544-118">Create and Attach Schedules to Jobs</span></span>](create-and-attach-schedules-to-jobs.md)|  
|<span data-ttu-id="10544-119">Contient des informations relatives à l'exécution manuelle des travaux (sans planification).</span><span class="sxs-lookup"><span data-stu-id="10544-119">Contains information about manually running jobs (without a schedule).</span></span>|[<span data-ttu-id="10544-120">Exécuter des travaux</span><span class="sxs-lookup"><span data-stu-id="10544-120">Run Jobs</span></span>](run-jobs.md)|  
|<span data-ttu-id="10544-121">Contient des informations relatives à la configuration du comportement de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par rapport aux travaux.</span><span class="sxs-lookup"><span data-stu-id="10544-121">Contains information about how you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to jobs.</span></span> <span data-ttu-id="10544-122">Par exemple, vous pouvez configurer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent de manière à notifier aux administrateurs l'achèvement des travaux.</span><span class="sxs-lookup"><span data-stu-id="10544-122">For example, you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to notify administrators when jobs are finished.</span></span>|[<span data-ttu-id="10544-123">Spécifier des réponses à un travail</span><span class="sxs-lookup"><span data-stu-id="10544-123">Specify Job Responses</span></span>](specify-job-responses.md)|  
|<span data-ttu-id="10544-124">Contient des informations relatives à la visualisation des travaux existants, à leur historique une fois exécutés et à leur modification.</span><span class="sxs-lookup"><span data-stu-id="10544-124">Contains information about how to view existing jobs, their history once executes, and how to modify them.</span></span>|[<span data-ttu-id="10544-125">Afficher ou modifier les travaux</span><span class="sxs-lookup"><span data-stu-id="10544-125">View or Modify Jobs</span></span>](view-or-modify-jobs.md)|  
|<span data-ttu-id="10544-126">Contient des informations sur la suppression de travaux.</span><span class="sxs-lookup"><span data-stu-id="10544-126">Contains information about how to delete jobs.</span></span>|[<span data-ttu-id="10544-127">Supprimer des travaux</span><span class="sxs-lookup"><span data-stu-id="10544-127">Delete Jobs</span></span>](delete-jobs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="10544-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10544-128">See Also</span></span>  
 [<span data-ttu-id="10544-129">Implémenter la sécurité de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="10544-129">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
