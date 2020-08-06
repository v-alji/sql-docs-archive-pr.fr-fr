---
title: Créer une étape de travail exécutant un script PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], job steps
- jobs [SQL Server Agent], PowerShell
- job steps [PowerShell]
- SQL Server Agent jobs, PowerShell steps
ms.assetid: 50afcf84-fae0-4eb5-9b0f-f2cf144c1433
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4232cdfa584fdcc2e13786ecc9bd00f0c6fe7066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604809"
---
# <a name="create-a-powershell-script-job-step"></a><span data-ttu-id="5c594-102">Create a PowerShell Script Job Step</span><span class="sxs-lookup"><span data-stu-id="5c594-102">Create a PowerShell Script Job Step</span></span>
  <span data-ttu-id="5c594-103">Cette rubrique explique comment créer et définir une étape de travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui exécute un script PowerShell dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c594-103">This topic describes how to create and define a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes a PowerShell script in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5c594-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5c594-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5c594-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5c594-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5c594-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5c594-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5c594-107">**Pour créer une étape de travail exécutant un script PowerShell, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5c594-107">**To create a PowerShell Script job step, using:**</span></span>  
  
     [<span data-ttu-id="5c594-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c594-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="5c594-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c594-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="5c594-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="5c594-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5c594-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5c594-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5c594-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5c594-112">Security</span></span>  
 <span data-ttu-id="5c594-113">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5c594-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="5c594-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c594-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="5c594-115">Pour créer une étape de travail exécutant un script PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c594-115">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="5c594-116">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="5c594-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5c594-117">Développez **SQL Server Agent**, créez un travail ou cliquez avec le bouton droit de la souris sur un travail existant, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5c594-117">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="5c594-118">Pour plus d'informations sur la création d'un travail, consultez [Création de travaux](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="5c594-118">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="5c594-119">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur la page **Étapes** , puis sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5c594-119">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="5c594-120">Dans la boîte de dialogue **Nouvelle étape du travail** , tapez un **nom d'étape**de travail.</span><span class="sxs-lookup"><span data-stu-id="5c594-120">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="5c594-121">Dans la liste **Type** , cliquez sur **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5c594-121">In the **Type** list, click **PowerShell**.</span></span>  
  
6.  <span data-ttu-id="5c594-122">Dans la liste **Exécuter en tant que** , sélectionnez le compte proxy avec les informations d'identification que le travail utilisera.</span><span class="sxs-lookup"><span data-stu-id="5c594-122">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="5c594-123">Dans la zone **Commande** , tapez la syntaxe du script PowerShell qui sera exécuté pour l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="5c594-123">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="5c594-124">Vous pouvez aussi cliquer sur **Ouvrir** et sélectionner un fichier contenant la syntaxe du script.</span><span class="sxs-lookup"><span data-stu-id="5c594-124">Alternately, click **Open** and select a file containing the script syntax.</span></span> <span data-ttu-id="5c594-125">Pour obtenir un exemple de script PowerShell, consultez **Utilisation de Transact-SQL** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="5c594-125">For an example of a PowerShell script, see **Using Transact-SQL** below.</span></span>  
  
8.  <span data-ttu-id="5c594-126">Cliquez sur la page **Avancé** pour paramétrer les options suivantes pour l'étape de travail : l'action à exécuter si l'étape de travail échoue ou réussit, le nombre de tentatives d'exécution de l'étape de travail que doit effectuer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et la fréquence de ces tentatives.</span><span class="sxs-lookup"><span data-stu-id="5c594-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="5c594-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c594-127">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="5c594-128">Pour créer une étape de travail exécutant un script PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c594-128">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="5c594-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c594-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5c594-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5c594-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5c594-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5c594-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a PowerShell job step that finds the processes that use more than 1000 MB of memory and kills them  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Kills all processes that use more than 1000 MB of memory',  
        @subsystem = N'PowerShell',  
        @command = N'Get-Process | Where-Object { $_.WS -gt 1000MB } | Stop-Process',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="5c594-132">Pour plus d’informations, consultez [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5c594-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="5c594-133">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="5c594-133">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="5c594-134">**Pour créer une étape de travail exécutant un script PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5c594-134">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="5c594-135">Utilisez la classe `JobStep` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c594-135">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
