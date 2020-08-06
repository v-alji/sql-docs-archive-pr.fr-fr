---
title: Créer un plan de maintenance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- maintenance plans [SQL Server], creating
ms.assetid: a945cb65-ba7a-42f4-bbd9-6ec675745523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3df0c1cd06427deb051a9c4214d03084b44c6f9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612315"
---
# <a name="create-a-maintenance-plan"></a><span data-ttu-id="20c98-102">Créer un plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="20c98-102">Create a Maintenance Plan</span></span>
  <span data-ttu-id="20c98-103">Cette rubrique explique comment créer un plan de serveur ou de maintenance multiserveur unique dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20c98-103">This topic describes how to create a single server or multiserver maintenance plan in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="20c98-104">Avec [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], vous pouvez créer ces plans de maintenance de deux manières : avec l'Assistant Plan de maintenance ou au moyen de l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="20c98-104">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can create these maintenance plans in one of two ways: by either using the Maintenance Plan Wizard or the design surface.</span></span> <span data-ttu-id="20c98-105">L'Assistant est conseillé pour créer des plans de maintenance de base, tandis que la zone de conception permet d'utiliser un flux de travail optimisé.</span><span class="sxs-lookup"><span data-stu-id="20c98-105">The Wizard is best for creating basic maintenance plans, while creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="20c98-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="20c98-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="20c98-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="20c98-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="20c98-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="20c98-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="20c98-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="20c98-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="20c98-110">**Pour créer un plan de maintenance à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="20c98-110">**To create a maintenance plan, using:**</span></span>  
  
     [<span data-ttu-id="20c98-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="20c98-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="20c98-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="20c98-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="20c98-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="20c98-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="20c98-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="20c98-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="20c98-115">Pour créer un plan de maintenance multiserveurs, vous devez configurer un environnement multiserveurs contenant un serveur maître et un ou plusieurs serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="20c98-115">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="20c98-116">Les plans de maintenance multiserveurs doivent être créés et conservés sur le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="20c98-116">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="20c98-117">Ces plans peuvent être consultés mais ne peuvent pas être conservés sur les serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="20c98-117">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="20c98-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="20c98-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="20c98-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="20c98-119">Permissions</span></span>  
 <span data-ttu-id="20c98-120">Pour créer ou gérer des plans de maintenance, vous devez être membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="20c98-120">To create or manage Maintenance Plans, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="20c98-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="20c98-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-maintenance-plan-using-the-maintenance-plan-wizard"></a><span data-ttu-id="20c98-122">Pour créer un plan de maintenance à l'aide de l'Assistant Plan de Maintenance</span><span class="sxs-lookup"><span data-stu-id="20c98-122">To create a maintenance plan using the Maintenance Plan Wizard</span></span>  
  
1.  <span data-ttu-id="20c98-123">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer un plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="20c98-123">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="20c98-124">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="20c98-124">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="20c98-125">Cliquez avec le bouton droit sur le dossier **Plans de maintenance** et sélectionnez **Assistant Plan de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="20c98-125">Right-click the **Maintenance Plans** folder and select **Maintenance Plan Wizard**.</span></span>  
  
4.  <span data-ttu-id="20c98-126">Suivez les procédures indiquées par l'Assistant pour créer un plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="20c98-126">Follow the steps of the wizard to create a maintenance plan.</span></span> <span data-ttu-id="20c98-127">Pour plus d’informations, consultez [Use the Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="20c98-127">For more information, see [Use the Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md).</span></span>  
  
#### <a name="to-create-a-maintenance-plan-using-the-design-surface"></a><span data-ttu-id="20c98-128">Pour créer un plan de maintenance à l'aide de la surface de dessin</span><span class="sxs-lookup"><span data-stu-id="20c98-128">To create a maintenance plan using the design surface</span></span>  
  
1.  <span data-ttu-id="20c98-129">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer un plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="20c98-129">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="20c98-130">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="20c98-130">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="20c98-131">Cliquez avec le bouton droit sur le dossier **Plans de maintenance** et sélectionnez **Nouveau plan de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="20c98-131">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="20c98-132">Créez un plan de maintenance en suivant les étapes de la rubrique [Créer un plan de maintenance &#40;aire de conception de plan de maintenance&#41;](create-a-maintenance-plan-maintenance-plan-design-surface.md).</span><span class="sxs-lookup"><span data-stu-id="20c98-132">Create a maintenance plan following the steps in [Create a Maintenance Plan &#40;Maintenance Plan Design Surface&#41;](create-a-maintenance-plan-maintenance-plan-design-surface.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="20c98-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="20c98-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="20c98-134">Pour créer un plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="20c98-134">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="20c98-135">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20c98-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="20c98-136">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="20c98-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="20c98-137">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="20c98-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    --  Adds a new job, executed by the SQL Server Agent service, called "HistoryCleanupTask_1".  
    EXEC dbo.sp_add_job  
       @job_name = N'HistoryCleanupTask_1',   
       @enabled = 1,   
       @description = N'Clean up old task history' ;   
    GO  
    -- Adds a job step for reorganizing all of the indexes in the HumanResources.Employee table to the HistoryCleanupTask_1 job.   
    EXEC dbo.sp_add_jobstep  
        @job_name = N'HistoryCleanupTask_1',   
        @step_name = N'Reorganize all indexes on HumanResources.Employee table',   
        @subsystem = N'TSQL',   
        @command = N'USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_LoginID ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_rowguid ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX IX_Employee_OrganizationNode ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX PK_Employee_BusinessEntityID ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    ',   
        @retry_attempts = 5,   
        @retry_interval = 5 ;   
    GO  
    -- Creates a schedule named RunOnce that executes every day when the time on the server is 23:00.   
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',   
        @freq_type = 4,   
        @freq_interval = 1,   
        @active_start_time = 233000 ;   
    GO  
    -- Attaches the RunOnce schedule to the job HistoryCleanupTask_1.   
    EXEC sp_attach_schedule  
       @job_name = N'HistoryCleanupTask_1'  
       @schedule_name = N'RunOnce' ;   
    GO  
  
    ```  
  
 <span data-ttu-id="20c98-138">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="20c98-138">For more information, see:</span></span>  
  
-   [<span data-ttu-id="20c98-139">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="20c98-139">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="20c98-140">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="20c98-140">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="20c98-141">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="20c98-141">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="20c98-142">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="20c98-142">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
  
