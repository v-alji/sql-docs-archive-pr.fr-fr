---
title: Créer une planification | Microsoft Docs
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
- schedules [SQL Server], jobs
ms.assetid: 8c7ef3b3-c06d-4a27-802d-ed329dc86ef3
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac71a61163dceb06697b61ef24fce2117d57cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613276"
---
# <a name="create-a-schedule"></a><span data-ttu-id="afe4a-102">Créer une planification</span><span class="sxs-lookup"><span data-stu-id="afe4a-102">Create a Schedule</span></span>
  <span data-ttu-id="afe4a-103">Vous pouvez créer une planification pour les travaux de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)]ou de SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="afe4a-103">You can create a schedule for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="afe4a-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="afe4a-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="afe4a-105">Sécurité</span><span class="sxs-lookup"><span data-stu-id="afe4a-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="afe4a-106">**Pour créer une planification, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="afe4a-106">**To create a schedule, using:**</span></span>  
  
     [<span data-ttu-id="afe4a-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afe4a-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="afe4a-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afe4a-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="afe4a-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="afe4a-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="afe4a-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="afe4a-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="afe4a-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="afe4a-111">Security</span></span>  
 <span data-ttu-id="afe4a-112">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="afe4a-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="afe4a-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afe4a-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="afe4a-114">Pour créer une planification</span><span class="sxs-lookup"><span data-stu-id="afe4a-114">To create a schedule</span></span>  
  
1.  <span data-ttu-id="afe4a-115">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="afe4a-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="afe4a-116">Développez **SQL Server Agent**, cliquez avec le bouton droit sur **Travaux**, puis sélectionnez **Gérer les planifications**.</span><span class="sxs-lookup"><span data-stu-id="afe4a-116">Expand **SQL Server Agent**, right-click **Jobs**, and select **Manage Schedules**.</span></span>  
  
3.  <span data-ttu-id="afe4a-117">Dans la boîte de dialogue **Gérer les planifications** , cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="afe4a-117">In the **Manage Schedules** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="afe4a-118">Dans la zone **Nom** , attribuez-lui un nom.</span><span class="sxs-lookup"><span data-stu-id="afe4a-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="afe4a-119">Si vous ne souhaitez pas que la planification entre en vigueur immédiatement après sa création, désactivez la case à cocher **Activé** .</span><span class="sxs-lookup"><span data-stu-id="afe4a-119">If you do not want the schedule to take effect immediately after it has been created, clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="afe4a-120">Pour **Type de planification**, sélectionnez l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="afe4a-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="afe4a-121">Pour lancer le travail lorsque les processeurs atteignent une condition d'inactivité, cliquez sur **Démarrer dès que les processeurs sont inactifs**.</span><span class="sxs-lookup"><span data-stu-id="afe4a-121">To start the job when the CPUs reach an idle condition, click **Start whenever the CPUs become idle**.</span></span>  
  
    -   <span data-ttu-id="afe4a-122">Si vous voulez qu'une planification s'exécute de façon répétée, cliquez sur **Périodique**.</span><span class="sxs-lookup"><span data-stu-id="afe4a-122">If you want a schedule to run repeatedly, click **Recurring**.</span></span> <span data-ttu-id="afe4a-123">Pour définir la planification périodique, renseignez les groupes **Fréquence**, **Fréquence quotidienne**et **Durée** dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="afe4a-123">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="afe4a-124">Si vous souhaitez que la planification ne s'exécute qu'une seule fois, cliquez sur **Une fois**.</span><span class="sxs-lookup"><span data-stu-id="afe4a-124">If you want the schedule to run only one time, click **One time**.</span></span> <span data-ttu-id="afe4a-125">Pour définir la planification **Une fois** , renseignez le groupe **Une seule occurrence** dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="afe4a-125">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="afe4a-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afe4a-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="afe4a-127">Pour créer une planification</span><span class="sxs-lookup"><span data-stu-id="afe4a-127">To create a schedule</span></span>  
  
1.  <span data-ttu-id="afe4a-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afe4a-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="afe4a-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="afe4a-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="afe4a-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="afe4a-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a schedule named RunOnce.   
    -- The schedule runs one time, at 23:30 on the day that the schedule is created.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
  
    GO  
    ```  
  
 <span data-ttu-id="afe4a-131">Pour plus d’informations, consultez [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="afe4a-131">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="afe4a-132">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="afe4a-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="afe4a-133">**Pour créer une planification**</span><span class="sxs-lookup"><span data-stu-id="afe4a-133">**To create a schedule**</span></span>  
  
 <span data-ttu-id="afe4a-134">Utilisez la classe `JobSchedule` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afe4a-134">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="afe4a-135">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="afe4a-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
