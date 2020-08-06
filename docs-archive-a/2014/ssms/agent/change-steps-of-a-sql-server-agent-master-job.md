---
title: Modifier les étapes d’un travail maître SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 8f1a0ee6-49ff-4080-94ca-d661daeff2a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a9defc17b5b39ab8a322b6da29960eb9968c2e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614340"
---
# <a name="change-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="3a58a-102">Modifier les étapes d'un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="3a58a-102">Change Steps of a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="3a58a-103">Cette rubrique explique comment modifier les étapes d'un travail maître SQL Server Agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l 'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a58a-103">This topic describes how to make changes to the steps of a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3a58a-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="3a58a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3a58a-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="3a58a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3a58a-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="3a58a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3a58a-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="3a58a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3a58a-108">**Pour modifier les étapes d'un travail maître SQL Server Agent à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="3a58a-108">**To make changes to the steps of a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="3a58a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a58a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3a58a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a58a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3a58a-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="3a58a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3a58a-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="3a58a-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3a58a-113">Un travail maître [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne peut pas être ciblé sur des serveurs locaux et distants à la fois.</span><span class="sxs-lookup"><span data-stu-id="3a58a-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3a58a-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="3a58a-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3a58a-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="3a58a-115">Permissions</span></span>  
 <span data-ttu-id="3a58a-116">Vous pouvez modifier uniquement les travaux dont vous êtes propriétaire, à moins d'être membre du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3a58a-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="3a58a-117">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="3a58a-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3a58a-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a58a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="3a58a-119">Pour modifier les étapes d'un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="3a58a-119">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="3a58a-120">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur qui contient le travail dont vous souhaitez modifier les étapes.</span><span class="sxs-lookup"><span data-stu-id="3a58a-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify steps.</span></span>  
  
2.  <span data-ttu-id="3a58a-121">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3a58a-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="3a58a-122">Cliquez sur le signe plus (+) pour développer le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="3a58a-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="3a58a-123">Cliquez avec le bouton droit sur le travail dont vous voulez modifier les étapes, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3a58a-123">Right-click the job where you want to modify steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="3a58a-124">Dans la boîte de dialogue **Propriétés du travail-**_Job_name_ , sous **Sélectionner une page**, sélectionnez **étapes**.</span><span class="sxs-lookup"><span data-stu-id="3a58a-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="3a58a-125">Cliquez sur **modifier** pour ouvrir la boîte **de dialogue Propriétés de l’étape du travail-**_job_step_name_ .</span><span class="sxs-lookup"><span data-stu-id="3a58a-125">Click **Edit** to open the **Job Step Properties -**_job_step_name_ dialog box.</span></span> <span data-ttu-id="3a58a-126">Pour plus d’informations sur les options disponibles dans cette boîte de dialogue, consultez Propriétés de l’étape du travail [: nouvelle étape du travail &#40;page général&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) et propriétés de l' [étape du travail : nouvelle étape du travail &#40;page avancé&#41;](job-step-properties-new-job-step-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="3a58a-126">For more information on the available options in this dialog box, see [Job Step Properties: New Job Step &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) and [Job Step Properties: New Job Step &#40;Advanced Page&#41;](job-step-properties-new-job-step-advanced-page.md).</span></span>  
  
7.  <span data-ttu-id="3a58a-127">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a58a-127">When finished, click **OK**.</span></span>  
  
8.  <span data-ttu-id="3a58a-128">Dans la boîte de dialogue **Propriétés du travail-**_job_name_ , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a58a-128">In the **Job Properties -**_job_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3a58a-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a58a-129">Using Transact-SQL</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="3a58a-130">Pour modifier les étapes d'un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="3a58a-130">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="3a58a-131">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a58a-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a58a-132">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="3a58a-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a58a-133">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3a58a-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the number of retry attempts for the first step of the Weekly Sales Data Backup job.   
    -- After running this example, the number of retry attempts is 10   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1,  
        @retry_attempts = 10 ;  
    GO  
    ```  
  
 <span data-ttu-id="3a58a-134">Pour plus d’informations, consultez [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a58a-134">For more information, see [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span></span>  
  
  
