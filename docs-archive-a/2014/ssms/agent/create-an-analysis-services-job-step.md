---
title: Créer une étape de travail Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [Analysis Services]
ms.assetid: 03d4bb86-514b-4a55-97b9-c2c0fa08b428
author: stevestein
ms.author: sstein
ms.openlocfilehash: ed0e63c22d4cad270bcb544b03decba269e4f43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699263"
---
# <a name="create-an-analysis-services-job-step"></a><span data-ttu-id="c0a49-102">Créer une étape de travail Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c0a49-102">Create an Analysis Services Job Step</span></span>
  <span data-ttu-id="c0a49-103">Cette rubrique explique comment créer et définir les étapes de travail de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] qui exécutent les commande et les requêtes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)] ou de SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="c0a49-103">This topic describes how to create and define [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services commands and queries by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="c0a49-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c0a49-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c0a49-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c0a49-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c0a49-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c0a49-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c0a49-107">**Pour créer des étapes de travail SQL Server à l'aide de commande et/ou de requêtes Analysis Services, avec :**</span><span class="sxs-lookup"><span data-stu-id="c0a49-107">**To create a SQL Server job steps using Analysis Services commands and/or queries, with:**</span></span>  
  
     [<span data-ttu-id="c0a49-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0a49-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="c0a49-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0a49-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="c0a49-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c0a49-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c0a49-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c0a49-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c0a49-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c0a49-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c0a49-113">Si l'étape de travail utilise une commande Analysis Services, l'instruction de commande doit être une méthode **EXECUTE** XML pour Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c0a49-113">If the job step uses an Analysis Services command, the command statement must be an XML for Analysis Services **Execute** method.</span></span> <span data-ttu-id="c0a49-114">L’instruction ne peut pas contenir d’enveloppe SOAP (Simple Object Access Protocol) complète ni de méthode **Discover** XML pour Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c0a49-114">The statement may not contain a complete Simple Object Access Protocol (SOAP) envelope or an XML for Analysis **Discover** method.</span></span> <span data-ttu-id="c0a49-115">Si [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] prend en charge les enveloppes SOAP (Simple Object Access Protocol) complètes et la méthode **Discover** , ce n'est pas le cas des étapes de travail de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="c0a49-115">While [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] supports complete SOAP envelopes and the **Discover** method, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps do not.</span></span> <span data-ttu-id="c0a49-116">Pour plus d’informations sur XML pour Analysis Services, consultez [Vue d’ensemble de XMLA (XML for Analysis)](https://msdn.microsoft.com/library/ms187190.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0a49-116">For more information about XML for Analysis Services, see [XML for Analysis Overview (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span></span>  
  
-   <span data-ttu-id="c0a49-117">Si l'étape de travail utilise une requête Analysis Services, l'instruction de requête doit être une requête MDX (expressions multidimensionnelles).</span><span class="sxs-lookup"><span data-stu-id="c0a49-117">If the job step uses an Analysis Services query, the query statement must be a multidimensional expressions (MDX) query.</span></span> <span data-ttu-id="c0a49-118">Pour plus d’informations sur MDX, consultez [principes de base des requêtes mdx &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="c0a49-118">For more information about MDX, see [MDX Query Fundamentals &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c0a49-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c0a49-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c0a49-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c0a49-120">Permissions</span></span>  
  
-   <span data-ttu-id="c0a49-121">Pour exécuter une étape de travail qui utilise le sous-système Analysis Services, un utilisateur doit être membre du rôle serveur fixe **sysadmin** ou avoir accès à un compte proxy valide, défini pour utiliser ce sous-système.</span><span class="sxs-lookup"><span data-stu-id="c0a49-121">To run a job step that uses the Analysis Services subsystem, a user must be a member of the **sysadmin** fixed server role or have access to a valid proxy account defined to use this subsystem.</span></span> <span data-ttu-id="c0a49-122">De plus, le compte du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ou du proxy doit correspondre à un compte administrateur Analysis Services et à un compte de domaine Windows valide.</span><span class="sxs-lookup"><span data-stu-id="c0a49-122">In addition, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account or the proxy must be an Analysis Services administrator and a valid Windows domain account.</span></span>  
  
-   <span data-ttu-id="c0a49-123">Seuls les membres du rôle serveur fixe **sysadmin** peuvent écrire les données de sortie de l'étape de travail dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="c0a49-123">Only members of the **sysadmin** fixed server role can write job step output to a file.</span></span> <span data-ttu-id="c0a49-124">Si l'étape de travail est exécutée par des utilisateurs membres du rôle de base de données **SQLAgentUserRole** de la base de données **msdb** , les données de sortie peuvent uniquement être écrites dans une table.</span><span class="sxs-lookup"><span data-stu-id="c0a49-124">If the job step is run by users who are members of the **SQLAgentUserRole** database role in the **msdb** database, then the output can be written only to a table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="c0a49-125">L’agent écrit la sortie de l’étape de travail dans la table **sysjobstepslog** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="c0a49-125">Agent writes job step output to the **sysjobstepslog** table in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="c0a49-126">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c0a49-126">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="c0a49-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0a49-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="c0a49-128">Pour créer une étape de travail de commande Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c0a49-128">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="c0a49-129">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="c0a49-129">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c0a49-130">Développez **SQL Server Agent**, créez un travail ou cliquez avec le bouton droit de la souris sur un travail existant, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-130">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="c0a49-131">Pour plus d’informations sur la création d’un travail, consultez [Créer des travaux](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="c0a49-131">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="c0a49-132">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur la page **Étapes** , puis sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-132">In the **Job Properties** dialog box, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="c0a49-133">Dans la boîte de dialogue **Nouvelle étape du travail** , tapez le **Nom de l'étape**du travail.</span><span class="sxs-lookup"><span data-stu-id="c0a49-133">In the **New Job Step** dialog box, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="c0a49-134">Dans la liste **Type** , cliquez sur **Commande SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-134">In the **Type** list, click **SQL Server Analysis Services Command**.</span></span>  
  
6.  <span data-ttu-id="c0a49-135">Dans la liste **Exécuter en tant que** , sélectionnez un proxy qui a été défini pour utiliser le sous-système de commandes Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c0a49-135">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Command subsystem.</span></span> <span data-ttu-id="c0a49-136">Un utilisateur qui est membre du rôle serveur fixe **sysadmin** peut également sélectionner **Compte du service Agent SQL** pour exécuter cette étape de travail.</span><span class="sxs-lookup"><span data-stu-id="c0a49-136">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="c0a49-137">Sélectionnez le **Serveur** sur lequel l'étape du travail s'exécutera, ou tapez le nom du serveur.</span><span class="sxs-lookup"><span data-stu-id="c0a49-137">Select the **Server** where the job step will run, or type the server name.</span></span>  
  
8.  <span data-ttu-id="c0a49-138">Dans la zone **Commande** , tapez l'instruction à exécuter ou cliquez sur **Ouvrir** pour sélectionner une instruction.</span><span class="sxs-lookup"><span data-stu-id="c0a49-138">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="c0a49-139">Cliquez sur la page **Avancé** pour définir les options de cette étape de travail, comme les actions que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit mener si l'étape de travail réussit ou échoue, combien de fois l'étape de travail doit être tentée, et à quel emplacement les données de sortie de l'étape de travail doivent être écrites.</span><span class="sxs-lookup"><span data-stu-id="c0a49-139">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="c0a49-140">Pour créer une étape de travail de requête Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c0a49-140">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="c0a49-141">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="c0a49-141">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c0a49-142">Développez **SQL Server Agent**, créez un travail ou cliquez avec le bouton droit de la souris sur un travail existant, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-142">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="c0a49-143">Pour plus d’informations sur la création d’un travail, consultez [Créer des travaux](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="c0a49-143">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="c0a49-144">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur la page **Étapes** , puis sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-144">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="c0a49-145">Dans la boîte de dialogue **Nouvelle étape du travail** , tapez un **nom d'étape**de travail.</span><span class="sxs-lookup"><span data-stu-id="c0a49-145">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="c0a49-146">Dans la liste **Type** , cliquez sur **Requête SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-146">In the **Type** list, click **SQL Server Analysis Services Query**.</span></span>  
  
6.  <span data-ttu-id="c0a49-147">Dans la liste **Exécuter en tant que** , sélectionnez un proxy qui a été défini pour utiliser le sous-système de requêtes Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c0a49-147">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Query subsystem.</span></span> <span data-ttu-id="c0a49-148">Un utilisateur qui est membre du rôle serveur fixe **sysadmin** peut également sélectionner **Compte du service Agent SQL** pour exécuter cette étape de travail.</span><span class="sxs-lookup"><span data-stu-id="c0a49-148">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="c0a49-149">Sélectionnez le **Serveur** et la **Base de données** sur lesquels l'étape du travail s'exécutera, ou tapez le nom du serveur ou de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c0a49-149">Select the **Server** and the **Database** where the job step will run, or type the server or database name.</span></span>  
  
8.  <span data-ttu-id="c0a49-150">Dans la zone **Commande** , tapez l'instruction à exécuter ou cliquez sur **Ouvrir** pour sélectionner une instruction.</span><span class="sxs-lookup"><span data-stu-id="c0a49-150">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="c0a49-151">Cliquez sur la page **Avancé** pour définir les options de cette étape de travail, comme les actions que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit mener si l'étape de travail réussit ou échoue, combien de fois l'étape de travail doit être tentée, et à quel emplacement les données de sortie de l'étape de travail doivent être écrites.</span><span class="sxs-lookup"><span data-stu-id="c0a49-151">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="c0a49-152">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0a49-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="c0a49-153">Pour créer une étape de travail de commande Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c0a49-153">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="c0a49-154">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0a49-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0a49-155">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0a49-156">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-156">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses XMLA to create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database ',  
        @subsystem = N'ANALYSISCOMMAND',  
        @command = N' <Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
        <ParentObject>  
            <DatabaseID>AdventureWorks2012</DatabaseID>  
        </ParentObject>  
        <ObjectDefinition>  
            <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
                <ID>AdventureWorks2012</ID>  
                <Name>Adventure Works 2012</Name>  
                <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorks2012;Integrated Security=True</ConnectionString>  
                <ImpersonationInfo>  
                    <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
                </ImpersonationInfo>  
                <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
                <Timeout>PT0S</Timeout>  
            </DataSource>  
        </ObjectDefinition>  
    </Create>', ;  
    GO  
    ```  
  
 <span data-ttu-id="c0a49-157">Pour plus d’informations, consultez [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0a49-157">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="c0a49-158">Pour créer une étape de travail de requête Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c0a49-158">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="c0a49-159">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0a49-159">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0a49-160">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-160">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c0a49-161">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c0a49-161">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses MDX to return data  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Returns the Internet sales amount by state',  
        @subsystem = N'ANALYSISQUERY',  
        @command = N' SELECT  
       [Measures].[Internet Sales Amount] ON COLUMNS,  
       [Customer].[State-Province].Members ON ROWS  
    FROM [AdventureWorks2012]',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="c0a49-162">Pour plus d’informations, consultez [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0a49-162">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="c0a49-163">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c0a49-163">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="c0a49-164">**Pour créer une étape de travail exécutant un script PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c0a49-164">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="c0a49-165">Utilisez la classe `JobStep` à l'aide d'un langage de programmation que vous choisissez, comme XMLA ou MDX.</span><span class="sxs-lookup"><span data-stu-id="c0a49-165">Use the `JobStep` class by using a programming language that you choose, such as XMLA or MDX.</span></span> <span data-ttu-id="c0a49-166">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0a49-166">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
