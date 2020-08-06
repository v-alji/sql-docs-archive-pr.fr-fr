---
title: Exécuter le travail de SQL Server Agent, tâche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqlserveragentjobtask.f1
helpviewer_keywords:
- Execute SQL Server Agent Job task [Integration Services]
- jobs [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: 3aa3bc0e-1a1c-452e-81b8-b4e3422ea053
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d0c66eb7022312fa3ec3d161f63a9aee92b840f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610795"
---
# <a name="execute-sql-server-agent-job-task"></a><span data-ttu-id="7069c-102">Tâche Exécuter le travail de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="7069c-102">Execute SQL Server Agent Job Task</span></span>
  <span data-ttu-id="7069c-103">La tâche Exécuter le travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exécute des travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7069c-103">The Execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job task runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7069c-104">Agent est un service Windows [!INCLUDE[msCoName](../../includes/msconame-md.md)] qui exécute des travaux définis dans une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7069c-104">Agent is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows service that runs jobs that have been defined in an instance of SQL Server.</span></span> <span data-ttu-id="7069c-105">Vous pouvez créer des travaux qui exécutent des instructions Transact-SQL et des scripts ActiveX, réalisent des tâches de maintenance des services [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et de réplication ou exécutent des packages.</span><span class="sxs-lookup"><span data-stu-id="7069c-105">You can create jobs that execute Transact-SQL statements and ActiveX scripts, perform [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and Replication maintenance tasks, or run packages.</span></span> <span data-ttu-id="7069c-106">Vous pouvez également configurer une tâche pour surveiller [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et déclencher des alertes.</span><span class="sxs-lookup"><span data-stu-id="7069c-106">You can also configure a job to monitor [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and fire alerts.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7069c-107">Les travaux de l’Agent sont généralement utilisés pour automatiser des tâches à caractère répétitif.</span><span class="sxs-lookup"><span data-stu-id="7069c-107">Agent jobs are typically used to automate tasks that you perform repeatedly.</span></span> <span data-ttu-id="7069c-108">Pour plus d’informations, consultez [Implémenter des travaux](../../ssms/agent/implement-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="7069c-108">For more information, see [Implement Jobs](../../ssms/agent/implement-jobs.md).</span></span>  
  
 <span data-ttu-id="7069c-109">Grâce à la tâche Exécuter le travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , un package peut effectuer des tâches d'administration liées aux composants [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7069c-109">By using the Execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job task, a package can perform administrative tasks related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="7069c-110">Par exemple, un travail d’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut exécuter une procédure stockée système telle que **sp_enum_dtspackages** pour obtenir la liste des packages stockés dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="7069c-110">For example, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job can run a system stored procedure such as **sp_enum_dtspackages** to obtain a list of packages in a folder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7069c-111">Agent doit être en cours d’exécution pour que les travaux d’administration locaux ou multiserveurs puissent être exécutés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="7069c-111">Agent must be running before local or multiserver administrative jobs can run automatically.</span></span>  
  
 <span data-ttu-id="7069c-112">Cette tâche encapsule la procédure système **sp_start_job** et transmet le nom du travail d’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à la procédure en guise d’argument.</span><span class="sxs-lookup"><span data-stu-id="7069c-112">This task encapsulates the **sp_start_job** system procedure and passes the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job to the procedure as an argument.</span></span> <span data-ttu-id="7069c-113">Pour plus d’informations, consultez [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7069c-113">For more information, see [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span></span>  
  
## <a name="configuring-the-execute-sql-server-agent-job-task"></a><span data-ttu-id="7069c-114">Configuration de la tâche d'exécution de travail d'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="7069c-114">Configuring the Execute SQL Server Agent Job Task</span></span>  
 <span data-ttu-id="7069c-115">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7069c-115">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="7069c-116">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7069c-116">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7069c-117">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="7069c-117">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7069c-118">Tâche Exécuter le travail de l’Agent SQL Server &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="7069c-118">Execute SQL Server Agent Job Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/execute-sql-server-agent-job-task-maintenance-plan.md)  
  
 <span data-ttu-id="7069c-119">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="7069c-119">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7069c-120">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="7069c-120">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
