---
title: Créer un travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: b35af2b6-6594-40d1-9861-4d5dd906048c
author: stevestein
ms.author: sstein
ms.openlocfilehash: de74f032924fbb0b6643bd8f3d482481ffb1f983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600470"
---
# <a name="create-a-job"></a><span data-ttu-id="8f8f1-102">Création d’un travail</span><span class="sxs-lookup"><span data-stu-id="8f8f1-102">Create a Job</span></span>
  <span data-ttu-id="8f8f1-103">Cette rubrique explique comment créer un travail de l'Agent SQL Server dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)] ou de SQL Server Management Objects (SMO).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-103">This topic describes how to create a SQL Server Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="8f8f1-104">Pour ajouter des étapes de travail, des planifications, des alertes et des notifications à envoyer aux opérateurs, utilisez les liens d'accès aux rubriques figurant dans la section Voir aussi.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-104">To add job steps, schedules, alerts, and notifications that can be sent to operators, see the links to topics in the See Also section.</span></span>  
  
-   <span data-ttu-id="8f8f1-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="8f8f1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8f8f1-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8f8f1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8f8f1-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8f8f1-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8f8f1-108">**Pour créer un travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="8f8f1-108">**To create a job, using:**</span></span>  
  
     <span data-ttu-id="8f8f1-109">[SQL Server Management Studio](#SSMSProcedure),</span><span class="sxs-lookup"><span data-stu-id="8f8f1-109">[SQL Server Management Studio](#SSMSProcedure),</span></span>  
  
     [<span data-ttu-id="8f8f1-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8f8f1-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="8f8f1-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="8f8f1-111">SQL Server Management Objects</span></span>](#SMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8f8f1-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8f8f1-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8f8f1-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8f8f1-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8f8f1-114">Pour créer un travail, l'utilisateur doit être membre de l'un des rôles de base de données fixes de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="8f8f1-114">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="8f8f1-115">Un travail ne peut être modifié que par son propriétaire ou par les membres du rôle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="8f8f1-115">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="8f8f1-116">Pour plus d’informations sur les rôles de base de données fixe de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consultez [Rôles de base de données fixe de SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-116">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
-   <span data-ttu-id="8f8f1-117">L'attribution d'un travail à une autre connexion ne garantit pas que le nouveau propriétaire dispose des autorisations nécessaires pour exécuter le travail.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-117">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
-   <span data-ttu-id="8f8f1-118">Les travaux locaux sont mis en cache par l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] local.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-118">Local jobs are cached by the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="8f8f1-119">Ainsi, toutes les modifications obligent implicitement l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à remettre le travail dans le cache.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-119">Therefore, any modifications implicitly force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to re-cache the job.</span></span> <span data-ttu-id="8f8f1-120">Étant donné que l’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne met pas le travail en mémoire cache tant que la procédure stockée **sp_add_jobserver** n’est pas appelée, il est plus efficace d’appeler **sp_add_jobserver** en dernier.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not cache the job until **sp_add_jobserver** is called, it is more efficient to call **sp_add_jobserver** last.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8f8f1-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8f8f1-121">Security</span></span>  
  
-   <span data-ttu-id="8f8f1-122">Vous devez être administrateur système pour modifier le propriétaire d'un travail.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-122">You must be a system administrator to change the owner of a job.</span></span>  
  
-   <span data-ttu-id="8f8f1-123">Pour des raisons de sécurité, seul le propriétaire du travail ou un membre du rôle **sysadmin** peut modifier la définition du travail.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-123">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="8f8f1-124">Seuls les membres du rôle serveur fixe **sysadmin** peuvent attribuer la propriété du travail à d'autres utilisateurs et peuvent exécuter n'importe quel travail, quel qu'en soit le propriétaire.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-124">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f8f1-125">Si vous transférez la propriété d’un travail à un utilisateur qui n’est pas membre du rôle serveur fixe **sysadmin** et que ce travail exécute des étapes qui nécessitent des comptes proxy (par exemple l’exécution de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), vérifiez que l’utilisateur en question a accès à ce compte proxy, sinon le travail échouera.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-125">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8f8f1-126">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8f8f1-126">Permissions</span></span>  
 <span data-ttu-id="8f8f1-127">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-127">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8f8f1-128">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f8f1-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="8f8f1-129">Pour créer un travail de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f8f1-129">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="8f8f1-130">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer un travail SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-130">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="8f8f1-131">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-131">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="8f8f1-132">Cliquez avec le bouton droit sur le dossier **travaux** et sélectionnez **nouveau travail...**.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-132">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="8f8f1-133">Dans la boîte de dialogue **Nouveau travail** , sur la page **Général** , modifiez les propriétés générales du travail.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-133">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="8f8f1-134">Pour plus d’informations sur les options disponibles dans cette page, consultez [Propriétés du travail et nouveau travail &#40;page général&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="8f8f1-134">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="8f8f1-135">Sur la page **Étapes** , organisez les étapes de travail.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-135">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="8f8f1-136">Pour plus d’informations sur les options disponibles dans cette page, consultez la [page Propriétés du travail : nouvelle tâche &#40;étapes&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="8f8f1-136">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="8f8f1-137">Sur la page **Planifications** , organisez les planifications du travail.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-137">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="8f8f1-138">Pour plus d’informations sur les options disponibles dans cette page, consultez [Propriétés du travail : nouvelle page planifications de la &#40;des travaux&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="8f8f1-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="8f8f1-139">Sur la page **Alertes** , organisez les alertes pour le travail.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-139">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="8f8f1-140">Pour plus d’informations sur les options disponibles sur cette page, consultez [Propriétés du travail : nouvelle tâche &#40;les alertes&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="8f8f1-140">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="8f8f1-141">Sur la page **Notifications** , définissez des actions que l'Agent [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devra exécuter une fois le travail terminé.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-141">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="8f8f1-142">Pour plus d’informations sur les options disponibles sur cette page, consultez [Propriétés du travail : nouvelle tâche &#40;page notifications&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-142">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="8f8f1-143">Sur la page **Cibles** , gérez les serveurs cibles pour le travail.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-143">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="8f8f1-144">Pour plus d’informations sur les options disponibles dans cette page, consultez [Propriétés du travail : nouvelle tâche &#40;cibles&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-144">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="8f8f1-145">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-145">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8f8f1-146">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8f8f1-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="8f8f1-147">Pour créer un travail de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f8f1-147">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="8f8f1-148">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f8f1-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8f8f1-149">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8f8f1-150">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backup';  
    GO  
    ```  
  
 <span data-ttu-id="8f8f1-151">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="8f8f1-151">For more information, see:</span></span>  
  
-   [<span data-ttu-id="8f8f1-152">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8f8f1-152">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="8f8f1-153">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8f8f1-153">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="8f8f1-154">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8f8f1-154">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="8f8f1-155">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8f8f1-155">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="8f8f1-156">sp_add_jobserver &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8f8f1-156">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProcedure"></a><span data-ttu-id="8f8f1-157">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="8f8f1-157">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="8f8f1-158">**Pour créer un travail de l'Agent SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8f8f1-158">**To create a SQL Server Agent job**</span></span>  
  
 <span data-ttu-id="8f8f1-159">Appelez la méthode `Create` de la classe `Job` à l'aide d'un langage de programmation tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-159">Call the `Create` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="8f8f1-160">Pour obtenir un exemple de code, consultez [Planification des tâches administratives automatiques dans l’Agent SQL Server](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-160">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
##  <a name="SSMSProc2"></a>  
