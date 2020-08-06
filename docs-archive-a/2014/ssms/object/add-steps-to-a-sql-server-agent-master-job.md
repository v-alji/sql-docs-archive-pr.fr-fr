---
title: Ajouter des étapes à un travail maître SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9cc1e8ab-7ddc-427b-859e-203aa7e24642
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccff8d6f4faa7bef549b5a179a957ce798250dbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599773"
---
# <a name="add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="f01a5-102">Add Steps to a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="f01a5-102">Add Steps to a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="f01a5-103">Cette rubrique explique comment ajouter des étapes à un travail maître SQL Server Agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f01a5-103">This topic describes how to add steps to a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f01a5-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f01a5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f01a5-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f01a5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f01a5-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f01a5-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f01a5-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f01a5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f01a5-108">**Pour ajouter des étapes à un travail maître SQL Server Agent à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="f01a5-108">**To add steps to a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="f01a5-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f01a5-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f01a5-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f01a5-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f01a5-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f01a5-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f01a5-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f01a5-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f01a5-113">Un travail maître [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne peut pas être ciblé sur des serveurs locaux et distants à la fois.</span><span class="sxs-lookup"><span data-stu-id="f01a5-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f01a5-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f01a5-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f01a5-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f01a5-115">Permissions</span></span>  
 <span data-ttu-id="f01a5-116">Vous pouvez modifier uniquement les travaux dont vous êtes propriétaire, à moins d'être membre du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f01a5-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="f01a5-117">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](../agent/implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f01a5-117">For detailed information, see [Implement SQL Server Agent Security](../agent/implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f01a5-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f01a5-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="f01a5-119">Pour ajouter des étapes à un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f01a5-119">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="f01a5-120">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur qui contient le travail auquel vous souhaitez ajouter des étapes.</span><span class="sxs-lookup"><span data-stu-id="f01a5-120">In **Object Explorer,** click the plus sign to expand the server that contains the job to which you want to add steps.</span></span>  
  
2.  <span data-ttu-id="f01a5-121">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f01a5-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f01a5-122">Cliquez sur le signe plus (+) pour développer le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="f01a5-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="f01a5-123">Cliquez avec le bouton droit sur le travail auquel vous voulez ajouter des étapes, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f01a5-123">Right-click the job to which you want to add steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="f01a5-124">Dans la boîte de dialogue **Propriétés du travail -** _nom_travail_, sous **Sélectionner une page**, sélectionnez **Étapes**.</span><span class="sxs-lookup"><span data-stu-id="f01a5-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span> <span data-ttu-id="f01a5-125">Pour plus d’informations sur les options disponibles sur cette page, consultez [Propriétés du travail : nouvelle tâche &#40;étapes&#41;](../agent/job-properties-new-job-steps-page.md).</span><span class="sxs-lookup"><span data-stu-id="f01a5-125">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](../agent/job-properties-new-job-steps-page.md).</span></span>  

6.  <span data-ttu-id="f01a5-126">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f01a5-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f01a5-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f01a5-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="f01a5-128">Pour ajouter des étapes à un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f01a5-128">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="f01a5-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f01a5-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f01a5-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f01a5-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f01a5-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f01a5-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a job step that changes database access to read-only for the Sales database.   
    -- specifies 5 retry attempts, with each retry to occur after a 5 minute wait.   
    -- assumes that the Weekly Sales Data Backup job already exists  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="f01a5-132">Pour plus d’informations, consultez [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f01a5-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
  
