---
title: Créer une étape de travail CmdExec | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CmdExec jobs
ms.assetid: b48da5b4-6fe7-4eb7-bade-dc7d697c6d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48c557b8ea4228d27b73d361c50aac62232d1e00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604807"
---
# <a name="create-a-cmdexec-job-step"></a><span data-ttu-id="97df3-102">Créer une étape de travail CmdExec</span><span class="sxs-lookup"><span data-stu-id="97df3-102">Create a CmdExec Job Step</span></span>
  <span data-ttu-id="97df3-103">Cette rubrique explique comment créer et définir une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étape de travail de l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] qui utilise un programme exécutable ou une commande de système d’exploitation à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="97df3-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that uses an executable program or operating system command by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="97df3-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="97df3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="97df3-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="97df3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="97df3-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="97df3-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="97df3-107">**Pour créer une étape de travail CmdExec, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="97df3-107">**To create a CmdExec job step, using:**</span></span>  
  
     [<span data-ttu-id="97df3-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97df3-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="97df3-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97df3-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="97df3-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="97df3-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="97df3-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="97df3-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="97df3-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="97df3-112">Security</span></span>  
 <span data-ttu-id="97df3-113">Par défaut, seuls les membres du rôle de serveur fixe **sysadmin** peuvent créer des étapes de travail CmdExec.</span><span class="sxs-lookup"><span data-stu-id="97df3-113">By default, only members of the **sysadmin** fixed server role can create CmdExec job steps.</span></span> <span data-ttu-id="97df3-114">Ces étapes de travail s'exécutent sous le contexte du compte de service SQL Server Agent à moins que l'utilisateur **sysadmin** crée un compte proxy.</span><span class="sxs-lookup"><span data-stu-id="97df3-114">These job steps run under the context of the SQL Server Agent service account unless the **sysadmin** user creates a proxy account.</span></span> <span data-ttu-id="97df3-115">Les utilisateurs qui ne sont pas membres du rôle **sysadmin** peuvent créer des étapes de travail CmdExec s'ils peuvent accéder à un compte proxy CmdExec.</span><span class="sxs-lookup"><span data-stu-id="97df3-115">Users who are not members of the **sysadmin** role can create CmdExec job steps if they have access to a CmdExec proxy account.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="97df3-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="97df3-116">Permissions</span></span>  
 <span data-ttu-id="97df3-117">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="97df3-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="97df3-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97df3-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="97df3-119">Pour créer une étape de travail CmdExec</span><span class="sxs-lookup"><span data-stu-id="97df3-119">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="97df3-120">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="97df3-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="97df3-121">Développez **SQL Server Agent**, créez un travail ou cliquez avec le bouton droit de la souris sur un travail existant, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="97df3-121">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="97df3-122">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur la page **Étapes** , puis sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="97df3-122">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="97df3-123">Dans la boîte de dialogue **Nouvelle étape du travail** , tapez un **nom d'étape**de travail.</span><span class="sxs-lookup"><span data-stu-id="97df3-123">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="97df3-124">Dans la liste **Type** , choisissez **Système d’exploitation (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="97df3-124">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
6.  <span data-ttu-id="97df3-125">Dans la liste **Exécuter en tant que** , sélectionnez le compte proxy avec les informations d'identification que doit utiliser le travail.</span><span class="sxs-lookup"><span data-stu-id="97df3-125">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="97df3-126">Par défaut, les étapes de travail CmdExec s'exécutent dans le contexte du compte de service SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="97df3-126">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
7.  <span data-ttu-id="97df3-127">Dans la zone **Traiter le code de sortie d'une commande réussie** , entrez une valeur comprise entre 0 et 999999.</span><span class="sxs-lookup"><span data-stu-id="97df3-127">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
8.  <span data-ttu-id="97df3-128">Dans la zone **Commande** , saisissez la commande du système d'exploitation ou le programme exécutable.</span><span class="sxs-lookup"><span data-stu-id="97df3-128">In the **Command** box, enter the operating system command or executable program.</span></span> <span data-ttu-id="97df3-129">Consultez « Utilisation de Transact T-SQL » pour obtenir un exemple.</span><span class="sxs-lookup"><span data-stu-id="97df3-129">See "Using Transact T-SQL for an example.</span></span>  
  
9. <span data-ttu-id="97df3-130">Cliquez sur la page **Avancé** pour définir les options d'étape de travail, telles que l'action à exécuter lorsque l'étape de travail aboutit ou échoue, le nombre de tentatives d'exécution de l'étape de travail que doit effectuer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le fichier où [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut écrire la sortie de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="97df3-130">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="97df3-131">Seuls les membres du rôle de serveur fixe **sysadmin** peuvent écrire une sortie d'étape de travail dans un fichier du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="97df3-131">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="97df3-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97df3-132">Using Transact-SQL</span></span>  
  
### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="97df3-133">Pour créer une étape de travail CmdExec</span><span class="sxs-lookup"><span data-stu-id="97df3-133">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="97df3-134">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97df3-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="97df3-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="97df3-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="97df3-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="97df3-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses CmdExec  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'CMDEXEC',  
        @command = C:\clickme_scripts\SQL11\PostBOLReorg GetHsX.exe',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="97df3-137">Pour plus d’informations, consultez [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="97df3-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="97df3-138">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="97df3-138">Using SQL Server Management Objects</span></span>  

### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="97df3-139">Pour créer une étape de travail CmdExec</span><span class="sxs-lookup"><span data-stu-id="97df3-139">To create a CmdExec job step</span></span>
  
 <span data-ttu-id="97df3-140">Utilisez la classe `JobStep` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97df3-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
