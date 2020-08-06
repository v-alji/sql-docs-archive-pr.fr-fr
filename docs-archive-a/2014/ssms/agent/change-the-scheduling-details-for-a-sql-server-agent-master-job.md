---
title: Modifier les informations de planification pour un travail maître SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: f5414451-4d8e-464b-bd9e-f2b70c6899b3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 85546bc93e6626bfcc85a28f06a4c2fe24fe9fd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614338"
---
# <a name="change-the-scheduling-details-for-a-sql-server-agent-master-job"></a><span data-ttu-id="967ff-102">Change the Scheduling Details for a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="967ff-102">Change the Scheduling Details for a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="967ff-103">Cette rubrique explique comment modifier les informations de planification pour une définition de travail dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="967ff-103">This topic describes how to change the scheduling details for a job definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="967ff-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="967ff-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="967ff-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="967ff-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="967ff-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="967ff-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="967ff-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="967ff-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="967ff-108">**Pour modifier les détails de planification d'une définition de travail à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="967ff-108">**To change the scheduling details for a job definition, using:**</span></span>  
  
     [<span data-ttu-id="967ff-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="967ff-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="967ff-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="967ff-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="967ff-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="967ff-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="967ff-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="967ff-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="967ff-113">Un travail maître [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne peut pas être ciblé sur des serveurs locaux et distants à la fois.</span><span class="sxs-lookup"><span data-stu-id="967ff-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="967ff-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="967ff-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="967ff-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="967ff-115">Permissions</span></span>  
 <span data-ttu-id="967ff-116">Vous pouvez modifier uniquement les travaux dont vous êtes propriétaire, à moins d'être membre du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="967ff-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="967ff-117">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="967ff-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="967ff-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="967ff-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="967ff-119">Pour modifier les détails de planification d'une définition de travail</span><span class="sxs-lookup"><span data-stu-id="967ff-119">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="967ff-120">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur qui contient le travail dont vous souhaitez modifier la planification.</span><span class="sxs-lookup"><span data-stu-id="967ff-120">In **Object Explorer,** click the plus sign to expand the server that contains the job whose schedule you want to edit.</span></span>  
  
2.  <span data-ttu-id="967ff-121">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="967ff-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="967ff-122">Cliquez sur le signe plus (+) pour développer le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="967ff-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="967ff-123">Cliquez avec le bouton droit sur le travail dont vous souhaitez modifier la planification, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="967ff-123">Right-click the job whose schedule you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="967ff-124">Dans la boîte de dialogue **Propriétés du travail-**_Job_name_ , sous **Sélectionner une page**, sélectionnez **planifications**.</span><span class="sxs-lookup"><span data-stu-id="967ff-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Schedules**.</span></span> <span data-ttu-id="967ff-125">Pour plus d’informations sur les options disponibles sur cette page, consultez [Propriétés du travail : nouvelle tâche &#40;les planifications&#41;](job-properties-new-job-schedules-page.md).</span><span class="sxs-lookup"><span data-stu-id="967ff-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md).</span></span>  
  
6.  <span data-ttu-id="967ff-126">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="967ff-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="967ff-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="967ff-127">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="967ff-128">Pour modifier les détails de planification d'une définition de travail</span><span class="sxs-lookup"><span data-stu-id="967ff-128">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="967ff-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="967ff-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="967ff-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="967ff-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="967ff-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="967ff-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled status of the NightlyJobs schedule to 0   
    -- and sets the owner to terrid.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_schedule  
        @name = 'NightlyJobs',  
        @enabled = 0,  
        @owner_login_name = 'terrid' ;  
    GO  
    ```  
  
 <span data-ttu-id="967ff-132">Pour plus d’informations, consultez [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="967ff-132">For more information, see [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span></span>  
  
  
