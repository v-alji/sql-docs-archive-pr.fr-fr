---
title: Modifier le ou les serveurs cibles associés à un travail maître SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 176e73b6-08aa-48ec-b349-e84b431e65cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6b7b5ab114366cdafe40b7a70f523fef43eb11d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614324"
---
# <a name="modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="c804e-102">Modifier les serveurs cibles associés à un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c804e-102">Modify the Target Server(s) Associated with a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="c804e-103">Cette rubrique explique comment modifier les serveurs cibles associés à un travail maître de SQL Server Agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c804e-103">This topic describes how to modify the target server(s) associated with a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c804e-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c804e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c804e-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c804e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c804e-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c804e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c804e-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c804e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c804e-108">**Pour modifier les serveurs cibles associés à un travail maître SQL Server Agent à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="c804e-108">**To modify the target server(s) associated with a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="c804e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c804e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c804e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c804e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c804e-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c804e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c804e-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c804e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c804e-113">Un travail maître [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne peut pas être ciblé sur des serveurs locaux et distants à la fois.</span><span class="sxs-lookup"><span data-stu-id="c804e-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c804e-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c804e-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c804e-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c804e-115">Permissions</span></span>  
 <span data-ttu-id="c804e-116">Vous pouvez modifier uniquement les travaux dont vous êtes propriétaire, à moins d'être membre du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c804e-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="c804e-117">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c804e-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c804e-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c804e-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="c804e-119">Pour modifier les serveurs cibles associés à un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c804e-119">To modify the target server(s) associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="c804e-120">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur qui contient le travail dans lequel vous souhaitez modifier le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="c804e-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify the target server.</span></span>  
  
2.  <span data-ttu-id="c804e-121">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c804e-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="c804e-122">Cliquez sur le signe plus (+) pour développer le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="c804e-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="c804e-123">Cliquez avec le bouton droit sur le travail dans lequel vous voulez modifier le serveur cible, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c804e-123">Right-click the job where you want to modify the target server and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="c804e-124">Dans la boîte de dialogue **Propriétés du travail-**_Job_name_ , sous **Sélectionner une page**, sélectionnez **cibles**.</span><span class="sxs-lookup"><span data-stu-id="c804e-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Targets**.</span></span> <span data-ttu-id="c804e-125">Pour plus d’informations sur les options disponibles dans cette page, consultez [Propriétés du travail : nouvelle tâche &#40;cibles&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="c804e-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
6.  <span data-ttu-id="c804e-126">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c804e-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c804e-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c804e-127">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-target-server-currently-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="c804e-128">Pour exécuter un serveur cible actuellement associé à un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c804e-128">To delete a target server currently associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="c804e-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c804e-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c804e-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c804e-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c804e-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c804e-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes the server SEATTLE2 from processing the Weekly Sales Backupsjob   
    -- assumes that the Weekly Sales Backups job exists  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="c804e-132">Pour plus d’informations, consultez [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c804e-132">For more information, see [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span></span>  
  
#### <a name="to-associate-a-target-server-with-the-current-sql-server-agent-master-job"></a><span data-ttu-id="c804e-133">Pour associer un serveur cible au travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c804e-133">To associate a target server with the current SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="c804e-134">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c804e-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c804e-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c804e-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c804e-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c804e-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2   
    -- assumes that the Weekly Sales Backups job already exists and that   
    -- SEATTLE2 is registered as a target server for the current instance  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="c804e-137">Pour plus d’informations, consultez [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c804e-137">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
  
