---
title: Créer une étape de travail de script ActiveX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ActiveX scripting jobs [SQL Server]
- job steps [Analysis Services]
ms.assetid: e6c46c6b-2d61-4571-bc8e-a831cd6e6302
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6604ba75af7acdd5bd2521433e8310c74150ce8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695263"
---
# <a name="create-an-activex-script-job-step"></a><span data-ttu-id="301c1-102">Créer une étape de travail de script ActiveX</span><span class="sxs-lookup"><span data-stu-id="301c1-102">Create an ActiveX Script Job Step</span></span>
  <span data-ttu-id="301c1-103">Cette rubrique explique comment créer et définir une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étape de travail de l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] qui exécute un script ActiveX à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , de ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="301c1-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that executes an ActiveX script by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="301c1-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="301c1-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="301c1-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="301c1-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="301c1-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="301c1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="301c1-107">**Pour créer une étape de travail Transact-SQL, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="301c1-107">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="301c1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="301c1-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="301c1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="301c1-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="301c1-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="301c1-110">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="301c1-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="301c1-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="301c1-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="301c1-112">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="301c1-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="301c1-113">Security</span></span>  
 <span data-ttu-id="301c1-114">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="301c1-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="301c1-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="301c1-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="301c1-116">Pour créer une étape de travail de script ActiveX</span><span class="sxs-lookup"><span data-stu-id="301c1-116">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="301c1-117">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="301c1-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="301c1-118">Développez **SQL Server Agent**, créez un travail ou cliquez avec le bouton droit de la souris sur un travail existant, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="301c1-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="301c1-119">Pour plus d'informations sur la création d'un travail, consultez [Création de travaux](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="301c1-119">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="301c1-120">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur la page **Étapes** , puis sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="301c1-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="301c1-121">Dans la boîte de dialogue **Nouvelle étape du travail** , tapez un **nom d'étape**de travail.</span><span class="sxs-lookup"><span data-stu-id="301c1-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="301c1-122">Dans la liste **Type** , cliquez sur **Script ActiveX**.</span><span class="sxs-lookup"><span data-stu-id="301c1-122">In the **Type** list, click **ActiveX Script**.</span></span>  
  
6.  <span data-ttu-id="301c1-123">Dans la liste **Exécuter en tant que** , sélectionnez le compte proxy avec les informations d'identification que le travail utilisera.</span><span class="sxs-lookup"><span data-stu-id="301c1-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="301c1-124">Sélectionnez le **langage** dans lequel le script est écrit.</span><span class="sxs-lookup"><span data-stu-id="301c1-124">Select the **Language** in which the script was written.</span></span> <span data-ttu-id="301c1-125">Vous pouvez également cliquer sur **Autre** , puis taper le nom du langage de script [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX dans lequel le script va être écrit.</span><span class="sxs-lookup"><span data-stu-id="301c1-125">Alternatively, click **Other** and then enter the name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX scripting language in which the script will be written.</span></span>  
  
8.  <span data-ttu-id="301c1-126">Dans la zone **Commande** , tapez la syntaxe du script qui sera exécuté pour l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="301c1-126">In the **Command** box, enter the script syntax that will be executed for the job step.</span></span> <span data-ttu-id="301c1-127">Vous pouvez aussi cliquer sur **Ouvrir** et sélectionner un fichier contenant la syntaxe du script.</span><span class="sxs-lookup"><span data-stu-id="301c1-127">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
9. <span data-ttu-id="301c1-128">Cliquez sur la page **Avancé** pour paramétrer les options suivantes pour l'étape de travail : l'action à exécuter si l'étape de travail échoue ou réussit, le nombre de tentatives d'exécution de l'étape de travail que doit effectuer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et la fréquence de ces tentatives.</span><span class="sxs-lookup"><span data-stu-id="301c1-128">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="301c1-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="301c1-129">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-activex-script-job-step"></a><span data-ttu-id="301c1-130">Pour créer une étape de travail de script ActiveX</span><span class="sxs-lookup"><span data-stu-id="301c1-130">To create an ActiveX Script job step</span></span>  
  
1.  <span data-ttu-id="301c1-131">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="301c1-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="301c1-132">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="301c1-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="301c1-133">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="301c1-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- create an ActiveX Script job step written in VBScript that creates a restore point  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a restore point',  
        @subsystem = N'ACTIVESCRIPTING',  
        @command = N'Const RESTORE_POINT = 20  
  
    strComputer = "."  
    Set objWMIService = GetObject("winmgmts:" _  
        & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\default")  
  
    Set objItem = objWMIService.Get("SystemRestore")  
    errResults = objItem.Restore(RESTORE_POINT)',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="301c1-134">Pour plus d’informations, consultez [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="301c1-134">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="301c1-135">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="301c1-135">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="301c1-136">**Pour créer une étape de travail de script ActiveX**</span><span class="sxs-lookup"><span data-stu-id="301c1-136">**To create an ActiveX Script job step**</span></span>  
  
 <span data-ttu-id="301c1-137">Utilisez la classe `JobStep` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="301c1-137">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
