---
title: Créer une étape de travail Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: 69c571a7-debe-4063-9d38-e4b6a1e8e84c
author: stevestein
ms.author: sstein
ms.openlocfilehash: b83ee944d2ca5c10ff1b77f3e6e6da6054b5c99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705891"
---
# <a name="create-a-transact-sql-job-step"></a><span data-ttu-id="e5d5d-102">Create a Transact-SQL Job Step</span><span class="sxs-lookup"><span data-stu-id="e5d5d-102">Create a Transact-SQL Job Step</span></span>
  <span data-ttu-id="e5d5d-103">Cette rubrique explique comment créer une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étape de travail de l’agent qui exécute [!INCLUDE[tsql](../../includes/tsql-md.md)] des scripts dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de, de ou de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="e5d5d-104">Ces scripts d'étape de travail peuvent appeler des procédures stockées et des procédures stockées étendues.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-104">These job step scripts may call stored procedures and extended stored procedures.</span></span> <span data-ttu-id="e5d5d-105">Une même étape de travail [!INCLUDE[tsql](../../includes/tsql-md.md)] peut contenir plusieurs traitements et commandes GO incorporées.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-105">A single [!INCLUDE[tsql](../../includes/tsql-md.md)] job step can contain multiple batches and embedded GO commands.</span></span> <span data-ttu-id="e5d5d-106">Pour plus d'informations sur la création d'un travail, consultez [Création de travaux](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e5d5d-106">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
 <span data-ttu-id="e5d5d-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="e5d5d-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e5d5d-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="e5d5d-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e5d5d-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e5d5d-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e5d5d-110">**Pour créer une étape de travail Transact-SQL, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="e5d5d-110">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="e5d5d-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5d5d-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e5d5d-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5d5d-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e5d5d-113">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e5d5d-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e5d5d-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e5d5d-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e5d5d-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e5d5d-115">Security</span></span>  
 <span data-ttu-id="e5d5d-116">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e5d5d-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e5d5d-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5d5d-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="e5d5d-118">Pour créer une étape de travail Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5d5d-118">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="e5d5d-119">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e5d5d-120">Développez **SQL Server Agent**, créez un travail ou cliquez avec le bouton droit de la souris sur un travail existant, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-120">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e5d5d-121">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur la page **Étapes** , puis sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-121">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e5d5d-122">Dans la boîte de dialogue **Nouvelle étape du travail** , tapez un **nom d'étape**de travail.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-122">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="e5d5d-123">Dans la liste **Type** , cliquez sur **Script Transact-SQL (TSQL)**.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-123">In the **Type** list, click **Transact-SQL Script (TSQL)**.</span></span>  
  
6.  <span data-ttu-id="e5d5d-124">Dans la zone **Commande** , tapez les traitements de commandes [!INCLUDE[tsql](../../includes/tsql-md.md)] ou cliquez sur **Ouvrir** pour sélectionner un fichier [!INCLUDE[tsql](../../includes/tsql-md.md)] à utiliser comme commande.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-124">In the **Command** box, type the [!INCLUDE[tsql](../../includes/tsql-md.md)] command batches, or click **Open** to select a [!INCLUDE[tsql](../../includes/tsql-md.md)] file to use as the command.</span></span>  
  
7.  <span data-ttu-id="e5d5d-125">Cliquez sur **Analyser** pour vérifier votre syntaxe.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-125">Click **Parse** to check your syntax.</span></span>  
  
8.  <span data-ttu-id="e5d5d-126">Le message « Analyse réussie » s'affiche si votre syntaxe est correcte.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-126">The message "Parse succeeded" is displayed when your syntax is correct.</span></span> <span data-ttu-id="e5d5d-127">Si le système trouve une erreur, corrigez la syntaxe avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-127">If an error is found, correct the syntax before continuing.</span></span>  
  
9. <span data-ttu-id="e5d5d-128">Cliquez sur la page **Avancé** pour définir les options d'étape de travail, telles que l'action à exécuter lorsque l'étape de travail aboutit ou échoue, le nombre de tentatives d'exécution de l'étape de travail que doit effectuer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le fichier ou la table où [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut écrire la sortie de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-128">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file or table where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="e5d5d-129">Seuls les membres du rôle de serveur fixe **sysadmin** peuvent écrire une sortie d'étape de travail dans un fichier du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-129">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span> <span data-ttu-id="e5d5d-130">Tous les utilisateurs de SQL Server Agent peuvent consigner une sortie dans une table.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-130">All SQL Server Agent users can log output to a table.</span></span>  
  
10. <span data-ttu-id="e5d5d-131">Si vous êtes membre du rôle de serveur fixe **sysadmin** et voulez exécuter cette étape de travail avec une connexion SQL différente, sélectionnez la connexion SQL dans la liste **Exécuter en tant qu'utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="e5d5d-131">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e5d5d-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5d5d-132">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="e5d5d-133">Pour créer une étape de travail Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5d5d-133">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="e5d5d-134">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5d5d-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e5d5d-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e5d5d-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses Transact-SQL  
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
  
 <span data-ttu-id="e5d5d-137">Pour plus d’informations, consultez [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e5d5d-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e5d5d-138">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e5d5d-138">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="e5d5d-139">**Pour créer une étape de travail Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="e5d5d-139">**To create a Transact-SQL job step**</span></span>  
  
 <span data-ttu-id="e5d5d-140">Utilisez la classe `JobStep` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5d5d-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
