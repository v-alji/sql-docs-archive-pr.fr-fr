---
title: Créer un travail principal SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], master jobs
- jobs [SQL Server Agent], creating
- master SQL Server Agent job [SQL Server]
ms.assetid: c12ab23f-d7ee-43a5-8cd2-0a9121292bcd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8a6503caec3f153878e360ee29ce09a5c099ade5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700565"
---
# <a name="create-a-sql-server-agent-master-job"></a><span data-ttu-id="f289c-102">Créer un travail principal SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f289c-102">Create a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="f289c-103">Cette rubrique explique comment créer un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travail de l’agent maître dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f289c-103">This topic describes how to create a master [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f289c-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f289c-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f289c-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f289c-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f289c-106">Les modifications apportées aux travaux principaux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doivent être appliquées à tous les serveurs cibles concernés.</span><span class="sxs-lookup"><span data-stu-id="f289c-106">Changes to master [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs must be propagated to all involved target servers.</span></span> <span data-ttu-id="f289c-107">Étant donné que les serveurs cibles ne téléchargent pas le travail tant que ces cibles ne sont pas spécifiées, [!INCLUDE[msCoName](../../includes/msconame-md.md)] vous recommande d'achever toutes les étapes et planifications de travail pour un travail donné avant de spécifier des serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="f289c-107">Because target servers do not initially download a job until those targets are specified, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you complete all job steps and job schedules for a particular job before you specify any target servers.</span></span> <span data-ttu-id="f289c-108">Sinon, vous devez demander manuellement que les serveurs cibles retéléchargent le travail modifié, soit en exécutant la procédure stockée **sp_post_msx_operation** , soit en modifiant le travail à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f289c-108">Otherwise, you must manual request that the target servers download the modified job again, either by executing the **sp_post_msx_operation** stored procedure or modifying the job using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f289c-109">Pour plus d’informations, consultez [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) ou [modifier un travail](modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="f289c-109">For more information, see [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) or [Modify a Job](modify-a-job.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f289c-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f289c-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f289c-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f289c-111">Permissions</span></span>  
 <span data-ttu-id="f289c-112">Les travaux distribués dont les étapes sont associées à un proxy sont exécutés dans le contexte du compte proxy du serveur cible.</span><span class="sxs-lookup"><span data-stu-id="f289c-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="f289c-113">Assurez-vous que les conditions suivantes sont remplies ou que les étapes de travail associées à un proxy ne seront pas téléchargées du serveur maître vers la cible :</span><span class="sxs-lookup"><span data-stu-id="f289c-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="f289c-114">La sous-clé de Registre **\ HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Microsoft SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) a la valeur 1 (true).</span><span class="sxs-lookup"><span data-stu-id="f289c-114">The registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="f289c-115">Par défaut, la valeur de cette sous-clé est 0 (False).</span><span class="sxs-lookup"><span data-stu-id="f289c-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="f289c-116">Il existe sur le serveur cible un compte proxy possédant le même nom que le compte proxy du serveur maître sur lequel l'étape du travail est exécutée.</span><span class="sxs-lookup"><span data-stu-id="f289c-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="f289c-117">Si les étapes du travail utilisant des comptes proxy échouent pendant leur téléchargement à partir du serveur maître vers le serveur cible, vous pouvez vérifier la colonne **error_message** dans la table **sysdownloadlist** de la base de données **msdb** pour les messages d’erreur suivants :</span><span class="sxs-lookup"><span data-stu-id="f289c-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="f289c-118">« L'étape du travail nécessite un compte proxy, cependant la mise en correspondance de proxy est désactivée sur le serveur cible. »</span><span class="sxs-lookup"><span data-stu-id="f289c-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span> <span data-ttu-id="f289c-119">Pour corriger ce problème, affectez à la sous-clé de Registre **AllowDownloadedJobsToMatchProxyName** la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="f289c-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="f289c-120">« Proxy introuvable. »</span><span class="sxs-lookup"><span data-stu-id="f289c-120">"Proxy not found."</span></span> <span data-ttu-id="f289c-121">Pour résoudre ce problème, vérifiez qu'un compte proxy portant le même nom que le compte proxy du serveur maître sous lequel l'étape s'exécute existe sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="f289c-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f289c-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f289c-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="f289c-123">Pour créer un travail principal SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f289c-123">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="f289c-124">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer un travail SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="f289c-124">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="f289c-125">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f289c-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f289c-126">Cliquez avec le bouton droit sur le dossier **travaux** et sélectionnez **nouveau travail...**.</span><span class="sxs-lookup"><span data-stu-id="f289c-126">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="f289c-127">Dans la boîte de dialogue **Nouveau travail** , sur la page **Général** , modifiez les propriétés générales du travail.</span><span class="sxs-lookup"><span data-stu-id="f289c-127">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="f289c-128">Pour plus d’informations sur les options disponibles dans cette page, consultez [Propriétés du travail et nouveau travail &#40;page général&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="f289c-128">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="f289c-129">Sur la page **Étapes** , organisez les étapes de travail.</span><span class="sxs-lookup"><span data-stu-id="f289c-129">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="f289c-130">Pour plus d’informations sur les options disponibles dans cette page, consultez la [page Propriétés du travail : nouvelle tâche &#40;étapes&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="f289c-130">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="f289c-131">Sur la page **Planifications** , organisez les planifications du travail.</span><span class="sxs-lookup"><span data-stu-id="f289c-131">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="f289c-132">Pour plus d’informations sur les options disponibles dans cette page, consultez [Propriétés du travail : nouvelle page planifications de la &#40;des travaux&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="f289c-132">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="f289c-133">Sur la page **Alertes** , organisez les alertes pour le travail.</span><span class="sxs-lookup"><span data-stu-id="f289c-133">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="f289c-134">Pour plus d’informations sur les options disponibles sur cette page, consultez [Propriétés du travail : nouvelle tâche &#40;les alertes&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="f289c-134">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="f289c-135">Sur la page **Notifications** , définissez des actions que l'Agent [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devra exécuter une fois le travail terminé.</span><span class="sxs-lookup"><span data-stu-id="f289c-135">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="f289c-136">Pour plus d’informations sur les options disponibles sur cette page, consultez [Propriétés du travail : nouvelle tâche &#40;page notifications&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="f289c-136">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="f289c-137">Sur la page **Cibles** , gérez les serveurs cibles pour le travail.</span><span class="sxs-lookup"><span data-stu-id="f289c-137">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="f289c-138">Pour plus d’informations sur les options disponibles dans cette page, consultez [Propriétés du travail : nouvelle tâche &#40;cibles&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="f289c-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="f289c-139">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f289c-139">When finished, click **OK**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f289c-140">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f289c-140">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="f289c-141">Pour créer un travail principal SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f289c-141">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="f289c-142">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f289c-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f289c-143">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f289c-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f289c-144">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f289c-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- Adds a new job executed by the SQLServerAgent service called 'Weekly Sales Data Backup'  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    -- Adds a step (operation) to the 'Weekly Sales Data Backup' job.  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    -- Creates a schedule called RunOnce  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    -- Sets the 'RunOnce' schedule to the "Weekly Sales Data Backup' Job  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2  
    -- assumes that SEATTLE2 is registered as a target server for the current instance.  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="f289c-145">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="f289c-145">For more information, see:</span></span>  
  
-   [<span data-ttu-id="f289c-146">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f289c-146">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="f289c-147">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f289c-147">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="f289c-148">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f289c-148">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="f289c-149">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f289c-149">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="f289c-150">sp_add_jobserver &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f289c-150">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  

  
  
