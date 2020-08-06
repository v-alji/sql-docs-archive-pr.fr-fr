---
title: Créer un travail de SQL Server Agent pour archiver les messages et les journaux d’événements de la messagerie de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- archiving mail messages and attachments [SQL Server]
- removing mail messages and attachements
- Database Mail [SQL Server], archiving
- saving mail messages and attachments
ms.assetid: 8f8f0fba-f750-4533-9b76-a9cdbcdc3b14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b958b280c358a8aeb752600dee1c2aee31d14db1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603549"
---
# <a name="create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs"></a><span data-ttu-id="83ae2-102">Créer un travail d'Agent SQL Server pour archiver les messages et les journaux d'événements de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="83ae2-102">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>
  <span data-ttu-id="83ae2-103">Des copies des messages de la messagerie de base de données et de leurs pièces jointes sont conservées dans les tables **msdb** avec le journal d'événements de la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="83ae2-103">Copies of Database Mail messages and their attachments are retained in **msdb** tables along with the Database Mail event log.</span></span> <span data-ttu-id="83ae2-104">Il peut être utile d'archiver périodiquement les messages et les événements dont vous n'avez plus besoin afin de réduire la taille des tables.</span><span class="sxs-lookup"><span data-stu-id="83ae2-104">Periodically you might want to reduce the size of the tables and archive messages and events that are no longer needed.</span></span> <span data-ttu-id="83ae2-105">Les procédures suivantes permettent de créer un travail de l'Agent SQL Server pour automatiser le processus.</span><span class="sxs-lookup"><span data-stu-id="83ae2-105">The following procedures create a SQL Server Agent job to automate the process.</span></span>  
  
-   <span data-ttu-id="83ae2-106">**Avant de commencer :**  , [Conditions préalables](#Prerequisites), [Recommandations](#Recommendations), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="83ae2-106">**Before you begin:**  , [Prerequisites](#Prerequisites), [Recommendations](#Recommendations), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="83ae2-107">**Pour archiver les messages et les journaux Database Mail à l’aide de :**  [SQL Server Agent](#Process_Overview)</span><span class="sxs-lookup"><span data-stu-id="83ae2-107">**To Archive Database Mail messages and logs using :**  [SQL Server Agent](#Process_Overview)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="83ae2-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="83ae2-108">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="83ae2-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="83ae2-109">Prerequisites</span></span>  
 <span data-ttu-id="83ae2-110">Les nouvelles tables de stockage des données d'archive peuvent se trouver dans une base de données d'archive spéciale.</span><span class="sxs-lookup"><span data-stu-id="83ae2-110">The new tables to store the archive data might be located in a special archive database.</span></span> <span data-ttu-id="83ae2-111">Vous pouvez également exporter les lignes vers un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="83ae2-111">Alternatively the rows could be exported to a text file.</span></span>  
 
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="83ae2-112">Recommandations</span><span class="sxs-lookup"><span data-stu-id="83ae2-112">Recommendations</span></span>  
 <span data-ttu-id="83ae2-113">Dans votre environnement de production, vous pouvez ajouter des fonctionnalités supplémentaires de vérification des erreurs et faire envoyer un message électronique aux opérateurs en cas d'échec du travail.</span><span class="sxs-lookup"><span data-stu-id="83ae2-113">In your production environment, you might want to add additional error checking and send an e-mail message to operators if the job fails.</span></span>  
  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="83ae2-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="83ae2-114">Permissions</span></span>  
 <span data-ttu-id="83ae2-115">Vous devez être membre du rôle serveur fixe **sysadmin** pour pouvoir exécuter les procédures stockées décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="83ae2-115">You must be a member of the **sysadmin** fixed server role to execute the stored procedures described in this topic.</span></span>  
  
  
###  <a name="overview-of-the-process"></a><a name="Process_Overview"></a> <span data-ttu-id="83ae2-116">Vue d'ensemble du processus</span><span class="sxs-lookup"><span data-stu-id="83ae2-116">Overview of the Process</span></span>  
  
-   <span data-ttu-id="83ae2-117">La première procédure crée un travail intitulé Archiver la messagerie de base de données avec les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="83ae2-117">The first procedure creates a job named Archive Database Mail with the following steps.</span></span>  
  
    1.  <span data-ttu-id="83ae2-118">Copiez tous les messages contenus dans les tables de la messagerie de base de données vers une nouvelle table nommée d’après le mois précédent au format **DBMailArchive_** _<année_mois>_ .</span><span class="sxs-lookup"><span data-stu-id="83ae2-118">Copy all messages from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_**_<year_month>_.</span></span>  
  
    2.  <span data-ttu-id="83ae2-119">Copiez les pièces jointes associées aux messages copiés à la première étape, à partir des tables de la messagerie de base de données vers une nouvelle table nommée d’après le mois précédent au format **DBMailArchive_Attachments_** _<année_mois>_ .</span><span class="sxs-lookup"><span data-stu-id="83ae2-119">Copy the attachments related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Attachments_**_<year_month>_.</span></span>  
  
    3.  <span data-ttu-id="83ae2-120">Copiez les événements du journal des événements de la messagerie de base de données qui sont associés aux messages copiés à la première étape, à partir des tables de la messagerie de base de données vers une nouvelle table nommée d’après le mois précédent au format **DBMailArchive_Log_** _<année_mois>_ .</span><span class="sxs-lookup"><span data-stu-id="83ae2-120">Copy the events from the Database Mail event log that are related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Log_**_<year_month>_.</span></span>  
  
    4.  <span data-ttu-id="83ae2-121">Supprimez des tables de la messagerie de base de données les enregistrements des éléments de messagerie transférés.</span><span class="sxs-lookup"><span data-stu-id="83ae2-121">Delete the records of the transferred mail items from the Database Mail tables.</span></span>  
  
    5.  <span data-ttu-id="83ae2-122">Supprimez du journal des événements de la messagerie de base de données les événements associés aux éléments de messagerie transférés.</span><span class="sxs-lookup"><span data-stu-id="83ae2-122">Delete the events related to the transferred mail items from the Database Mail event log.</span></span>  
  
-   <span data-ttu-id="83ae2-123">Planifiez une exécution périodique du travail.</span><span class="sxs-lookup"><span data-stu-id="83ae2-123">Schedule the job to run periodically.</span></span>  
 
  
## <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="83ae2-124">Pour créer un travail de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="83ae2-124">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="83ae2-125">Dans l’Explorateur d’objets, développez l’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , cliquez avec le bouton droit sur **Travaux**, puis cliquez sur **Nouveau travail**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-125">In Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, and then click **New Job**.</span></span>  
  
2.  <span data-ttu-id="83ae2-126">Dans la boîte de dialogue **Nouveau travail** , dans la zone **Nom** , tapez **Archiver la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-126">In the **New Job** dialog box, in the **Name** box, type **Archive Database Mail**.</span></span>  
  
3.  <span data-ttu-id="83ae2-127">Dans la zone **Propriétaire** , confirmez que le propriétaire est membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="83ae2-127">In the **Owner** box, confirm that the owner is a member of the **sysadmin** fixed server role.</span></span>  
  
4.  <span data-ttu-id="83ae2-128">Dans la zone **Catégorie** , cliquez sur **Maintenance de la base de données**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-128">In the **Category** box, click the **Database Maintenance**.</span></span>  
  
5.  <span data-ttu-id="83ae2-129">Dans la zone **Description** , tapez **Archiver les messages de la messagerie de base de données**, puis cliquez sur **Étapes**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-129">In the **Description** box, type **Archive Database Mail messages**, and then click **Steps**.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-messages"></a><span data-ttu-id="83ae2-130">Pour créer une étape permettant d'archiver les messages de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="83ae2-130">To create a step to archive the Database Mail messages</span></span>  
  
1.  <span data-ttu-id="83ae2-131">Dans la page **Étapes** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-131">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="83ae2-132">Dans la zone **Nom de l'étape** , tapez **Copier les éléments de la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-132">In the **Step name** box, type **Copy Database Mail Items**.</span></span>  
  
3.  <span data-ttu-id="83ae2-133">Dans la zone **Type** , sélectionnez **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="83ae2-133">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="83ae2-134">Dans la zone **Base de données** , sélectionnez **msdb**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-134">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="83ae2-135">Dans la zone **Commande** , tapez l'instruction suivante pour créer une table nommée d'après le mois précédent, contenant les lignes antérieures au début du mois actuel :</span><span class="sxs-lookup"><span data-stu-id="83ae2-135">In the **Command** box, type the following statement to create a table named after the previous month, containing rows older than the start of the current month:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_' + @LastMonth + '] FROM sysmail_allitems WHERE send_request_date < ''' + @CopyDate +'''';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="83ae2-136">Cliquez sur **OK** pour enregistrer l'étape.</span><span class="sxs-lookup"><span data-stu-id="83ae2-136">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-attachments"></a><span data-ttu-id="83ae2-137">Pour créer une étape permettant d'archiver les pièces jointes de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="83ae2-137">To create a step to archive the Database Mail attachments</span></span>  
  
1.  <span data-ttu-id="83ae2-138">Dans la page **Étapes** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-138">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="83ae2-139">Dans la zone **Nom de l'étape** , tapez **Copier les pièces jointes de la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-139">In the **Step name** box, type **Copy Database Mail Attachments**.</span></span>  
  
3.  <span data-ttu-id="83ae2-140">Dans la zone **Type** , sélectionnez **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="83ae2-140">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="83ae2-141">Dans la zone **Base de données** , sélectionnez **msdb**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-141">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="83ae2-142">Dans la zone **Commande** , tapez l'instruction suivante pour créer une table de pièces jointes nommée d'après le mois précédent, contenant les pièces jointes qui correspondent aux messages transférés à l'étape précédente :</span><span class="sxs-lookup"><span data-stu-id="83ae2-142">In the **Command** box, type the following statement to create an attachments table named after the previous month, containing the attachments that correspond to the messages transferred in the previous step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Attachments_' + @LastMonth + '] FROM sysmail_attachments   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="83ae2-143">Cliquez sur **OK** pour enregistrer l'étape.</span><span class="sxs-lookup"><span data-stu-id="83ae2-143">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-log"></a><span data-ttu-id="83ae2-144">Pour créer une étape permettant d'archiver le journal de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="83ae2-144">To create a step to archive the Database Mail log</span></span>  
  
1.  <span data-ttu-id="83ae2-145">Dans la page **Étapes** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-145">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="83ae2-146">Dans la zone **Nom de l'étape** , tapez **Copier le journal de la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-146">In the **Step name** box, type **Copy Database Mail Log**.</span></span>  
  
3.  <span data-ttu-id="83ae2-147">Dans la zone **Type** , sélectionnez **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="83ae2-147">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="83ae2-148">Dans la zone **Base de données** , sélectionnez **msdb**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-148">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="83ae2-149">Dans la zone **Commande** , tapez l'instruction suivante pour créer une table de journal nommée d'après le mois précédent, contenant les entrées de journal qui correspondent aux messages transférés à l'étape antérieure :</span><span class="sxs-lookup"><span data-stu-id="83ae2-149">In the **Command** box, type the following statement to create a log table named after the previous month, containing the log entries that correspond to the messages transferred in the earlier step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Log_' + @LastMonth + '] FROM sysmail_Event_Log   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="83ae2-150">Cliquez sur **OK** pour enregistrer l'étape.</span><span class="sxs-lookup"><span data-stu-id="83ae2-150">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-rows-from-database-mail"></a><span data-ttu-id="83ae2-151">Pour créer une étape permettant de supprimer les lignes archivées du journal de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="83ae2-151">To create a step to remove the archived rows from Database Mail</span></span>  
  
1.  <span data-ttu-id="83ae2-152">Dans la page **Étapes** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-152">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="83ae2-153">Dans la zone **Nom de l'étape** , tapez **Supprimer les lignes de la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-153">In the **Step name** box, type **Remove rows from Database Mail**.</span></span>  
  
3.  <span data-ttu-id="83ae2-154">Dans la zone **Type** , sélectionnez **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="83ae2-154">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="83ae2-155">Dans la zone **Base de données** , sélectionnez **msdb**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-155">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="83ae2-156">Dans la zone **Commande** , tapez l'instruction suivante pour supprimer des tables de la messagerie de base de données les lignes antérieures au mois actuel :</span><span class="sxs-lookup"><span data-stu-id="83ae2-156">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail tables:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_mailitems_sp @sent_before = @CopyDate ;  
    ```  
  
6.  <span data-ttu-id="83ae2-157">Cliquez sur **OK** pour enregistrer l'étape.</span><span class="sxs-lookup"><span data-stu-id="83ae2-157">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-items-from-database-mail-event-log"></a><span data-ttu-id="83ae2-158">Pour créer une étape permettant de supprimer les éléments archivés du journal des événements de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="83ae2-158">To create a step to remove the archived items from Database Mail event log</span></span>  
  
1.  <span data-ttu-id="83ae2-159">Dans la page **Étapes** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-159">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="83ae2-160">Dans la zone **Nom de l'étape** , tapez **Supprimer les lignes du journal des événements de la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-160">In the **Step Name** box type **Remove rows from Database Mail event log**.</span></span>  
  
3.  <span data-ttu-id="83ae2-161">Dans la zone **Type** , sélectionnez **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="83ae2-161">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="83ae2-162">Dans la zone **Commande** , tapez l'instruction suivante pour supprimer du journal des événements de la messagerie de base de données les lignes antérieures au mois actuel :</span><span class="sxs-lookup"><span data-stu-id="83ae2-162">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail event log:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_log_sp @logged_before = @CopyDate ;  
    ```  
  
5.  <span data-ttu-id="83ae2-163">Cliquez sur **OK** pour enregistrer l'étape.</span><span class="sxs-lookup"><span data-stu-id="83ae2-163">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-schedule-the-job-to-run-periodically"></a><span data-ttu-id="83ae2-164">Pour planifier une exécution périodique du travail</span><span class="sxs-lookup"><span data-stu-id="83ae2-164">To schedule the job to run periodically</span></span>  
  
1.  <span data-ttu-id="83ae2-165">Dans la boîte de dialogue **Nouveau travail** , cliquez sur **Planifications**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-165">In the **New Job** dialog box, click **Schedules**.</span></span>  
  
2.  <span data-ttu-id="83ae2-166">Dans la page **Planifications** , cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-166">On the **Schedules** page, click **New**.</span></span>  
  
3.  <span data-ttu-id="83ae2-167">Dans la zone **Nom** , tapez **Archiver la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-167">In the **Name** box, type **Archive Database Mail**.</span></span>  
  
4.  <span data-ttu-id="83ae2-168">Dans la zone **Type de planification** , sélectionnez **Périodique**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-168">In the **Schedule type** box, select **Recurring**.</span></span>  
  
5.  <span data-ttu-id="83ae2-169">Dans la zone **Fréquence** , sélectionnez les options appropriées pour exécuter périodiquement le travail, par exemple une fois par mois.</span><span class="sxs-lookup"><span data-stu-id="83ae2-169">In the **Frequency** area, select the options to run the job periodically, for example once every month.</span></span>  
  
6.  <span data-ttu-id="83ae2-170">Dans la zone **Fréquence quotidienne**, sélectionnez **Une fois à \<time>** .</span><span class="sxs-lookup"><span data-stu-id="83ae2-170">In the **Daily frequency** area, select **Occurs once at \<time>**.</span></span>  
  
7.  <span data-ttu-id="83ae2-171">Vérifiez que les autres options sont configurées à votre convenance, puis cliquez sur **OK** pour enregistrer la planification.</span><span class="sxs-lookup"><span data-stu-id="83ae2-171">Verify that the other options are configured as you wish, and then click **OK** to save the schedule.</span></span>  
  
8.  <span data-ttu-id="83ae2-172">Cliquez sur **OK** pour enregistrer le travail.</span><span class="sxs-lookup"><span data-stu-id="83ae2-172">Click **OK** to save the job.</span></span>  
  
  
  
  
