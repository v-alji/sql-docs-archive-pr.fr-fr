---
title: Supprimer des étapes d’un travail maître SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 871e6162-1221-464d-8f7f-7e454dcd9edb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5996971225ee0b300b307c5af24dec464dbfd43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614308"
---
# <a name="remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="74eff-102">Remove Steps from a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="74eff-102">Remove Steps from a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="74eff-103">Cette rubrique explique comment supprimer des étapes d'un travail maître SQL Server Agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74eff-103">This topic describes how to remove steps from a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="74eff-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="74eff-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="74eff-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="74eff-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="74eff-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="74eff-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="74eff-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="74eff-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="74eff-108">**Pour supprimer des étapes d'un travail maître SQL Server Agent à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="74eff-108">**To remove steps from a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="74eff-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74eff-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="74eff-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74eff-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="74eff-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="74eff-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="74eff-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="74eff-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="74eff-113">Un travail maître [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne peut pas être ciblé sur des serveurs locaux et distants à la fois.</span><span class="sxs-lookup"><span data-stu-id="74eff-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="74eff-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="74eff-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="74eff-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="74eff-115">Permissions</span></span>  
 <span data-ttu-id="74eff-116">Vous pouvez modifier uniquement les travaux dont vous êtes propriétaire, à moins d'être membre du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="74eff-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="74eff-117">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="74eff-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="74eff-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74eff-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="74eff-119">Pour supprimer des étapes d'un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="74eff-119">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="74eff-120">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur qui contient le travail dont vous souhaitez supprimer les étapes.</span><span class="sxs-lookup"><span data-stu-id="74eff-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to delete steps.</span></span>  
  
2.  <span data-ttu-id="74eff-121">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="74eff-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="74eff-122">Cliquez sur le signe plus (+) pour développer le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="74eff-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="74eff-123">Cliquez avec le bouton droit sur le travail dont vous voulez supprimer les étapes, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="74eff-123">Right-click the job where you want to delete steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="74eff-124">Dans la boîte de dialogue **Propriétés du travail-**_Job_name_ , sous **Sélectionner une page**, sélectionnez **étapes**.</span><span class="sxs-lookup"><span data-stu-id="74eff-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="74eff-125">Sous **Liste des étapes du travail**, sélectionnez l'étape du travail à supprimer et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="74eff-125">Under **Job step list**, select the job step you want to delete and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="74eff-126">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="74eff-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="74eff-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74eff-127">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="74eff-128">Pour supprimer des étapes d'un travail maître SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="74eff-128">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="74eff-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74eff-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="74eff-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="74eff-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="74eff-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="74eff-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes job step 1 from the job Weekly Sales Data Backup   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="74eff-132">Pour plus d’informations, consultez [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="74eff-132">For more information, see [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span></span>  
  
  
