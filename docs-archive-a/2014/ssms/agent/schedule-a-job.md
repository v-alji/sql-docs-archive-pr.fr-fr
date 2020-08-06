---
title: Planifier un travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scheduling jobs [SQL Server]
- SQL Server Agent jobs, scheduling
- jobs [SQL Server Agent], scheduling
ms.assetid: f626390a-a3df-4970-b7a7-a0529e4a109c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1077766d6853ed7c029b8eefa76515c89ad861fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699174"
---
# <a name="schedule-a-job"></a><span data-ttu-id="ee73a-102">Schedule a Job</span><span class="sxs-lookup"><span data-stu-id="ee73a-102">Schedule a Job</span></span>
  <span data-ttu-id="ee73a-103">Cette rubrique décrit la méthode à suivre pour planifier un travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee73a-103">This topic describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
-   <span data-ttu-id="ee73a-104">**Avant de commencer :** ,</span><span class="sxs-lookup"><span data-stu-id="ee73a-104">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="ee73a-105">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ee73a-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ee73a-106">**Pour planifier un travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="ee73a-106">**To schedule a job, using:**</span></span>  
  
     [<span data-ttu-id="ee73a-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee73a-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="ee73a-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee73a-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="ee73a-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="ee73a-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ee73a-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ee73a-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ee73a-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ee73a-111">Security</span></span>  
 <span data-ttu-id="ee73a-112">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="ee73a-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="ee73a-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee73a-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-and-attach-a-schedule-to-a-job"></a><span data-ttu-id="ee73a-114">Pour créer une planification et l'attacher à un travail</span><span class="sxs-lookup"><span data-stu-id="ee73a-114">To create and attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="ee73a-115">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="ee73a-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ee73a-116">Développez **Agent SQL Server**, **Travaux**, cliquez avec le bouton droit de la souris sur le travail à planifier, puis sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ee73a-116">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ee73a-117">Sélectionnez la page **Planifications** , puis cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="ee73a-117">Select the **Schedules** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="ee73a-118">Dans la zone **Nom** , attribuez-lui un nom.</span><span class="sxs-lookup"><span data-stu-id="ee73a-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="ee73a-119">Désactivez la case à cocher **Activé** si vous ne souhaitez pas que la planification entre en vigueur directement après sa création.</span><span class="sxs-lookup"><span data-stu-id="ee73a-119">Clear the **Enabled** check box if you do not want the schedule to take effect immediately following its creation.</span></span>  
  
6.  <span data-ttu-id="ee73a-120">Pour **Type de planification**, sélectionnez l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ee73a-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="ee73a-121">Cliquez sur **Lancer automatiquement au démarrage de l'Agent SQL Server** pour démarrer le travail en même temps que le service Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee73a-121">Click **Start automatically when SQL Server Agent starts** to start the job when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is started.</span></span>  
  
    -   <span data-ttu-id="ee73a-122">Cliquez sur **Démarrer dès que les processeurs sont inactifs** pour démarrer le travail lorsque les processeurs se trouvent à l'état inactif.</span><span class="sxs-lookup"><span data-stu-id="ee73a-122">Click **Start whenever the CPUs become idle** to start the job when the CPUs reach an idle condition.</span></span>  
  
    -   <span data-ttu-id="ee73a-123">Cliquez sur **Périodique** si vous voulez que la planification s'exécute de façon répétée.</span><span class="sxs-lookup"><span data-stu-id="ee73a-123">Click **Recurring** if you want a schedule to run repeatedly.</span></span> <span data-ttu-id="ee73a-124">Pour définir la planification périodique, renseignez les groupes **Fréquence**, **Fréquence quotidienne**et **Durée** dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ee73a-124">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="ee73a-125">Cliquez sur **Une fois** si vous voulez que la planification s'exécute une seule fois.</span><span class="sxs-lookup"><span data-stu-id="ee73a-125">Click **One time** if you want the schedule to run only once.</span></span> <span data-ttu-id="ee73a-126">Pour définir la planification **Une fois** , renseignez le groupe **Une seule occurrence** dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ee73a-126">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog.</span></span>  
  
#### <a name="to-attach-a-schedule-to-a-job"></a><span data-ttu-id="ee73a-127">Pour attacher une planification à un travail</span><span class="sxs-lookup"><span data-stu-id="ee73a-127">To attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="ee73a-128">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="ee73a-128">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ee73a-129">Développez **Agent SQL Server**et **Travaux**, cliquez avec le bouton droit sur le travail à planifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ee73a-129">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ee73a-130">Sélectionnez la page **Planifications** , puis cliquez sur **Choisir**.</span><span class="sxs-lookup"><span data-stu-id="ee73a-130">Select the **Schedules** page, and then click **Pick**.</span></span>  
  
4.  <span data-ttu-id="ee73a-131">Sélectionnez la planification à attacher, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee73a-131">Select the schedule that you want to attach, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ee73a-132">Dans la boîte de dialogue **Propriétés du travail** , double-cliquez sur la planification attachée.</span><span class="sxs-lookup"><span data-stu-id="ee73a-132">In the **Job Properties** dialog box, double-click the attached schedule.</span></span>  
  
6.  <span data-ttu-id="ee73a-133">Vérifiez que le paramètre **Date de début** est défini correctement.</span><span class="sxs-lookup"><span data-stu-id="ee73a-133">Verify that **Start date** is set correctly.</span></span> <span data-ttu-id="ee73a-134">Si ce n'est pas le cas, définissez la date de début de la planification, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee73a-134">If it is not, set the date when you want for the schedule to start, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="ee73a-135">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee73a-135">In the **Job Properties** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="ee73a-136">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee73a-136">Using Transact-SQL</span></span>  
  
#### <a name="to-schedule-a-job"></a><span data-ttu-id="ee73a-137">Pour planifier un travail</span><span class="sxs-lookup"><span data-stu-id="ee73a-137">To schedule a job</span></span>  
  
1.  <span data-ttu-id="ee73a-138">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee73a-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ee73a-139">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ee73a-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ee73a-140">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ee73a-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    -- creates a schedule named NightlyJobs.   
    -- Jobs that use this schedule execute every day when the time on the server is 01:00.   
    EXEC sp_add_schedule  
        @schedule_name = N'NightlyJobs' ,  
        @freq_type = 4,  
        @freq_interval = 1,  
        @active_start_time = 010000 ;  
    GO  
    -- attaches the schedule to the job BackupDatabase  
    EXEC sp_attach_schedule  
       @job_name = N'BackupDatabase',  
       @schedule_name = N'NightlyJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="ee73a-141">Pour plus d’informations, consultez [sp_add_schedule &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) et [sp_attach_schedule &#40;transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ee73a-141">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) and [sp_attach_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="ee73a-142">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="ee73a-142">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="ee73a-143">Utilisez la classe `JobSchedule` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee73a-143">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="ee73a-144">Pour plus d’informations, consultez[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="ee73a-144">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
