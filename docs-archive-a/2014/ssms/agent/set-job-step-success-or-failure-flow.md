---
title: Définir un flux en cas de réussite ou d’échec de l’étape de travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, action flow logic
- successful jobs [SQL Server]
- failed jobs [SQL Server]
- jobs [SQL Server Agent], action flow logic
ms.assetid: 23041ccf-8a07-41d3-85b9-c449a54b7e1e
author: stevestein
ms.author: sstein
ms.openlocfilehash: fddc5820676cb231b6f0cd5f7151e24d8eceaefa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710095"
---
# <a name="set-job-step-success-or-failure-flow"></a><span data-ttu-id="55f86-102">Set Job Step Success or Failure Flow</span><span class="sxs-lookup"><span data-stu-id="55f86-102">Set Job Step Success or Failure Flow</span></span>
  <span data-ttu-id="55f86-103">Lorsque [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vous créez des travaux de l’agent, vous pouvez spécifier l’action à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] entreprendre si une défaillance se produit pendant l’exécution du travail.</span><span class="sxs-lookup"><span data-stu-id="55f86-103">When creating [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you can specify what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take if a failure occurs during job execution.</span></span> <span data-ttu-id="55f86-104">Déterminez l'action que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit effectuer en cas de réussite ou d'échec de chaque étape de travail.</span><span class="sxs-lookup"><span data-stu-id="55f86-104">Determine the action that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take upon the success or failure of each job step.</span></span> <span data-ttu-id="55f86-105">Procédez ensuite comme suit pour définir le déroulement logique des actions de l'étape de travail en utilisant l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55f86-105">Then use the following procedure to configure the job step action flow logic by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
-   <span data-ttu-id="55f86-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="55f86-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="55f86-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="55f86-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="55f86-108">**Pour définir un flux en cas de réussite ou d'échec de l'étape de travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="55f86-108">**To set job step success or failure flow, using:**</span></span>  
  
     [<span data-ttu-id="55f86-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55f86-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="55f86-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55f86-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="55f86-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="55f86-111">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="55f86-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="55f86-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="55f86-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="55f86-113">Security</span></span>  
 <span data-ttu-id="55f86-114">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="55f86-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="55f86-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55f86-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="55f86-116">Pour définir un flux en cas de réussite ou d'échec de l'étape de travail</span><span class="sxs-lookup"><span data-stu-id="55f86-116">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="55f86-117">Dans l' **Explorateur d'objets**, développez **Agent SQL Server**, puis **Travaux**.</span><span class="sxs-lookup"><span data-stu-id="55f86-117">In **Object Explorer**, expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
2.  <span data-ttu-id="55f86-118">Cliquez avec le bouton droit sur le travail à modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="55f86-118">Right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="55f86-119">Cliquez sur la page **Étapes** , puis sur une étape et enfin sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="55f86-119">Select the **Steps** page, click a step, and then click **Edit**.</span></span>  
  
4.  <span data-ttu-id="55f86-120">Dans la boîte de dialogue **Propriétés de l'étape de travail** , cliquez sur la page **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="55f86-120">In the **Job Step Properties** dialog box, select the **Advanced** page.</span></span>  
  
5.  <span data-ttu-id="55f86-121">Dans la boîte de dialogue **Action en cas de succès**, cliquez sur l’action à exécuter si l’étape de travail réussit.</span><span class="sxs-lookup"><span data-stu-id="55f86-121">In the **On success action**list, click the action to perform if the job step completes successfully.</span></span>  
  
6.  <span data-ttu-id="55f86-122">Dans la zone **Tentatives de reprises** , saisissez le nombre de fois (entre 0 et 9999) qu'il faut répéter l'étape de travail avant de la considérer comme un échec.</span><span class="sxs-lookup"><span data-stu-id="55f86-122">In the **Retry attempts** box, enter the number of times from 0 through 9999 that the job step should be repeated before it is considered to have failed.</span></span> <span data-ttu-id="55f86-123">Si vous tapez une valeur supérieure à 0 dans la zone **Tentatives de reprises** , entrez dans la zone **Intervalle de reprise (minutes)** , le nombre de minutes d’attente, compris entre 1 et 9999, avant que le travail fasse l’objet d’un nouvel essai.</span><span class="sxs-lookup"><span data-stu-id="55f86-123">If you entered a value greater than 0 in the **Retry attempts** box, enter in the **Retry interval (minutes)** box the number of minutes from 1 through 9999 that must pass before the job step is retried.</span></span>  
  
7.  <span data-ttu-id="55f86-124">Dans la liste **Action en cas d'échec** , cliquez sur l'action à exécuter si l'étape de travail échoue.</span><span class="sxs-lookup"><span data-stu-id="55f86-124">In the **On failure action** list, click the action to perform if the job step fails.</span></span>  
  
8.  <span data-ttu-id="55f86-125">Si le travail est un script [!INCLUDE[tsql](../../includes/tsql-md.md)] , vous pouvez choisir les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="55f86-125">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="55f86-126">Dans la zone **Fichier de sortie** , tapez le nom du fichier de sortie dans lequel la sortie du script sera écrite.</span><span class="sxs-lookup"><span data-stu-id="55f86-126">In the **Output file** box, enter the name of an output file to which the script output will be written.</span></span> <span data-ttu-id="55f86-127">Par défaut, les données du fichier sont remplacées chaque fois que l'étape de travail s'exécute.</span><span class="sxs-lookup"><span data-stu-id="55f86-127">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="55f86-128">Si vous ne voulez pas remplacer les données, activez **Ajouter la sortie au fichier existant**.</span><span class="sxs-lookup"><span data-stu-id="55f86-128">If you do not want the output file overwritten, check **Append output to existing file**.</span></span>  
  
    -   <span data-ttu-id="55f86-129">Activez **Enregistrer un journal dans la table** pour enregistrer l'étape de travail dans une table de base de données.</span><span class="sxs-lookup"><span data-stu-id="55f86-129">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="55f86-130">Par défaut, le contenu de la table est remplacé chaque fois que l'étape de travail s'exécute.</span><span class="sxs-lookup"><span data-stu-id="55f86-130">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="55f86-131">Si vous ne voulez pas remplacer les données, activez **Ajouter la sortie à l'entrée existante dans la table**.</span><span class="sxs-lookup"><span data-stu-id="55f86-131">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="55f86-132">Une fois l'étape de travail exécutée, vous pouvez afficher le contenu de la table en cliquant sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="55f86-132">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="55f86-133">Activez **Inclure la sortie de l'étape dans l'historique** pour inclure la sortie dans l'historique de l'étape.</span><span class="sxs-lookup"><span data-stu-id="55f86-133">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="55f86-134">Le résultat ne sera affiché que s'il n'y a pas d'erreur.</span><span class="sxs-lookup"><span data-stu-id="55f86-134">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="55f86-135">De même, le résultat peut être tronqué.</span><span class="sxs-lookup"><span data-stu-id="55f86-135">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="55f86-136">Si la liste **Exécuter en tant qu'utilisateur** est disponible, sélectionnez le compte proxy ayant les informations d'identification que le travail utilisera.</span><span class="sxs-lookup"><span data-stu-id="55f86-136">If the **Run as user** list is available, select the proxy account with the credentials that the job will use.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="55f86-137">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55f86-137">Using Transact-SQL</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="55f86-138">Pour définir un flux en cas de réussite ou d'échec de l'étape de travail</span><span class="sxs-lookup"><span data-stu-id="55f86-138">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="55f86-139">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55f86-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="55f86-140">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="55f86-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="55f86-141">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="55f86-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @on_success_action = 1;  
    GO  
    ```  
  
 <span data-ttu-id="55f86-142">Pour plus d’informations, consultez [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55f86-142">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="55f86-143">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="55f86-143">Using SQL Server Management Objects</span></span>  

### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="55f86-144">Pour définir un flux en cas de réussite ou d'échec de l'étape de travail</span><span class="sxs-lookup"><span data-stu-id="55f86-144">To set job step success or failure flow</span></span>
  
 <span data-ttu-id="55f86-145">Utilisez la classe `JobStep` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55f86-145">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="55f86-146">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="55f86-146">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
