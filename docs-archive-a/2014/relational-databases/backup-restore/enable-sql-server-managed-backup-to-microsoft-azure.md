---
title: Configuration de la SQL Server la gestion de sauvegarde sur Azure | Microsoft Docs
ms.custom: ''
ms.date: 08/04/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 68ebb53e-d5ad-4622-af68-1e150b94516e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9e3b86fde91028106263310aad8a1952fc041a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613477"
---
# <a name="setting-up-sql-server-managed-backup-to-azure"></a><span data-ttu-id="82580-102">Configuration de la sauvegarde managée SQL Server sur Azure</span><span class="sxs-lookup"><span data-stu-id="82580-102">Setting up SQL Server Managed Backup to Azure</span></span>
  <span data-ttu-id="82580-103">Cette rubrique contient deux didacticiels :</span><span class="sxs-lookup"><span data-stu-id="82580-103">This topic includes two tutorials:</span></span>  
  
 <span data-ttu-id="82580-104">Configurer la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] au niveau de la base de données, activer les notifications par courrier électronique et surveiller l'activité de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="82580-104">Set up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="82580-105">Configurer la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] au niveau de l'instance, activer les notifications par courrier électronique et surveiller l'activité de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="82580-105">Setting up  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the instance level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="82580-106">Pour obtenir un didacticiel sur la configuration [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] des groupes de disponibilité, consultez Configuration de la [SQL Server gestion de la sauvegarde sur Microsoft Azure pour les groupes de disponibilité](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="82580-106">For a tutorial on setting up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for Availability Groups, see [Setting up SQL Server Managed Backup to Microsoft Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
## <a name="setting-up-ss_smartbackup"></a><span data-ttu-id="82580-107">Configuration de la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82580-107">Setting Up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span></span>  
  
### <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><span data-ttu-id="82580-108">Activer et configurer la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] pour une base de données</span><span class="sxs-lookup"><span data-stu-id="82580-108">Enable and Configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="82580-109">Ce didacticiel décrit les étapes à suivre pour activer et configurer la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] pour une base de données (TestDB), puis pour activer la surveillance de l'état d'intégrité de la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82580-109">This tutorial describes the steps necessary to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a database (TestDB), followed by steps to enable monitoring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="82580-110">**Autorisations :**</span><span class="sxs-lookup"><span data-stu-id="82580-110">**Permissions:**</span></span>  
  
-   <span data-ttu-id="82580-111">Requiert l’appartenance au rôle de base de données **db_backupoperator** , avec les autorisations **ALTER ANY CREDENTIAL** et les `EXECUTE` autorisations sur **sp_delete_backuphistory**procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="82580-111">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="82580-112">Requiert des autorisations **Select** sur la fonction **smart_admin. fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="82580-112">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="82580-113">Requiert `EXECUTE` des autorisations sur la procédure stockée **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="82580-113">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="82580-114">En outre, nécessite les autorisations `VIEW SERVER STATE`, car elle appelle en interne d'autres objets système qui nécessitent cette autorisation.</span><span class="sxs-lookup"><span data-stu-id="82580-114">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  
  
-   <span data-ttu-id="82580-115">Requiert `EXECUTE` des autorisations sur `smart_admin.sp_set_instance_backup` les `smart_admin.sp_backup_master_switch` procédures stockées et.</span><span class="sxs-lookup"><span data-stu-id="82580-115">Requires `EXECUTE` permissions on the `smart_admin.sp_set_instance_backup` and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  


1.  <span data-ttu-id="82580-116">**Créez un compte de stockage Microsoft Azure :** Les sauvegardes sont stockées dans le service de stockage Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="82580-116">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="82580-117">Vous devez d’abord créer un compte de stockage Microsoft Azure, si vous n’avez pas encore de compte.</span><span class="sxs-lookup"><span data-stu-id="82580-117">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="82580-118">SQL Server 2014 utilise des objets BLOB de pages, qui sont différents des objets BLOB de blocs et d’ajout.</span><span class="sxs-lookup"><span data-stu-id="82580-118">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="82580-119">Par conséquent, vous devez créer un compte à usage général, et non un compte d’objet BLOB.</span><span class="sxs-lookup"><span data-stu-id="82580-119">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="82580-120">Pour plus d’informations, consultez la rubrique [À propos des comptes de stockage Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="82580-120">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="82580-121">Notez le nom du compte de stockage et les clés d'accès.</span><span class="sxs-lookup"><span data-stu-id="82580-121">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="82580-122">Le nom du compte de stockage et les informations de clé d'accès sont utilisés pour créer un objet contenant les informations d'identification SQL.</span><span class="sxs-lookup"><span data-stu-id="82580-122">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="82580-123">Les informations d'identification SQL servent à authentifier le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="82580-123">The SQL Credential is used to authenticate to the storage account.</span></span>  
 
2.  <span data-ttu-id="82580-124">**Créer des informations d’identification SQL :** Créez des informations d’identification SQL en utilisant le nom du compte de stockage comme identité et la clé d’accès de stockage comme mot de passe.</span><span class="sxs-lookup"><span data-stu-id="82580-124">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="82580-125">**Assurez-vous SQL Server Agent Service est démarré et en cours d’exécution :**  Démarrez SQL Server Agent s’il n’est pas en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="82580-125">**Ensure SQL Server Agent service is Started and Running:**  Start SQL Server Agent if it is not currently running.</span></span>  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="82580-126">nécessite l'exécution de SQL Server Agent sur l'instance pour effectuer les opérations de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="82580-126">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="82580-127">Vous pouvez configurer l'exécution automatique de SQL Server Agent, pour vous assurer que les opérations de sauvegarde se déroulent régulièrement.</span><span class="sxs-lookup"><span data-stu-id="82580-127">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="82580-128">**Déterminez la période de rétention :** Déterminez la période de conservation des fichiers de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="82580-128">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="82580-129">La période de rétention est spécifiée en jours, sur une plage de 1 à 30.</span><span class="sxs-lookup"><span data-stu-id="82580-129">The retention period is specified in days and can range from 1 to 30.</span></span>  
  
5.  <span data-ttu-id="82580-130">**Activer et configurer [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Démarrez SQL Server Management Studio et connectez-vous à l’instance où la base de données est installée.</span><span class="sxs-lookup"><span data-stu-id="82580-130">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance where the database is installed.</span></span> <span data-ttu-id="82580-131">Dans la fenêtre de requête, exécutez l'instruction suivante après avoir modifié les valeurs du nom de la base de données, des informations d'identification SQL, de la période de rétention et des options de chiffrement selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="82580-131">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="82580-132">Pour plus d’informations sur la création d’un certificat pour le chiffrement, consultez l’étape **créer un certificat de sauvegarde** dans [créer une sauvegarde chiffrée](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="82580-132">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@retention_days=30   
                    ,@credential_name='MyCredential'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
                    ,@enable_backup=1;  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="82580-133">est maintenant activée sur la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="82580-133">is now enabled on the database you specified.</span></span> <span data-ttu-id="82580-134">Un délai de 15 minutes au maximum peut être nécessaire pour le démarrage des opérations de sauvegarde sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="82580-134">It may take up to 15 minutes for the backup operations on the database to start to run.</span></span>  
  
6.  <span data-ttu-id="82580-135">**Passez en revue la configuration par défaut des événements étendus :** Vérifiez les paramètres des événements étendus en exécutant l’instruction Transact-SQL suivante.</span><span class="sxs-lookup"><span data-stu-id="82580-135">**Review Extended Event Default Configuration:** Review the Extended Event settings by running the following transact-SQL statement.</span></span>  
  
    ```  
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="82580-136">Les événements du canal d'administration, opérationnel et analytique doivent être activés par défaut et ne doivent pas pouvoir être désactivés.</span><span class="sxs-lookup"><span data-stu-id="82580-136">You should see that Admin, Operational, and Analytical channel events are enabled by default and cannot be disabled.</span></span> <span data-ttu-id="82580-137">Cela est en principe suffisant pour surveiller les événements qui nécessitent une intervention manuelle.</span><span class="sxs-lookup"><span data-stu-id="82580-137">This should be sufficient to monitor the events that require manual intervention.</span></span>  <span data-ttu-id="82580-138">Vous pouvez activer les événements de débogage, mais les canaux de débogage comprennent des événements d'information et de débogage que la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] utilise pour détecter et résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="82580-138">You can enable debug events, but the debug channels include informational and debug events that [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] uses to detect issues and solve them.</span></span> <span data-ttu-id="82580-139">Pour plus d’informations, consultez [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="82580-139">For more information, see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
7.  <span data-ttu-id="82580-140">**Activez et configurez les notifications de l’état d’intégrité :** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] fournit une procédure stockée qui crée un travail d’agent pour envoyer des notifications par e-mail des erreurs ou des avertissements susceptibles de nécessiter une intervention.</span><span class="sxs-lookup"><span data-stu-id="82580-140">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span> <span data-ttu-id="82580-141">Les étapes suivantes décrivent la procédure d'activation et de configuration des notifications par courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="82580-141">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="82580-142">Configurez la messagerie de base de données si elle n'est pas déjà activée sur l'instance.</span><span class="sxs-lookup"><span data-stu-id="82580-142">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="82580-143">Pour plus d'informations, consultez [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="82580-143">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="82580-144">Configurez la notification SQL Server Agent afin qu'elle utilise la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="82580-144">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="82580-145">Pour plus d’informations, consultez [Configurer la messagerie de SQL Server Agent en vue de l’utilisation de la messagerie de base de données](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="82580-145">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="82580-146">**Activez les notifications par e-mail afin de recevoir les erreurs de sauvegarde et les avertissements :** Dans la fenêtre de requête, exécutez les instructions Transact-SQL suivantes :</span><span class="sxs-lookup"><span data-stu-id="82580-146">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email1;email2>'  
  
        ```  
  
         <span data-ttu-id="82580-147">Pour plus d’informations et pour obtenir un exemple de script complet, consultez [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="82580-147">For more information, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
8.  <span data-ttu-id="82580-148">**Affichez les fichiers de sauvegarde dans le compte de Stockage Microsoft Azure**. Connectez-vous au compte de stockage depuis SQL Server Management Studio ou depuis le Portail de gestion Azure.</span><span class="sxs-lookup"><span data-stu-id="82580-148">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="82580-149">Vous verrez un conteneur pour l'instance de SQL Server qui héberge la base de données que vous avez configurée pour utiliser la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82580-149">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="82580-150">Vous pourrez voir aussi une base de données et une sauvegarde de journal 15 minutes après l'activation de la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="82580-150">You may also see a database and a log backup within 15 minutes of enabling [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the database.</span></span>  
  
9. <span data-ttu-id="82580-151">**Supervisez l’état d’intégrité :**  Vous pouvez le superviser au moyen des notifications par e-mail configurées précédemment, ou en supervisant activement les événements enregistrés.</span><span class="sxs-lookup"><span data-stu-id="82580-151">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="82580-152">Voici quelques exemples d'instructions Transact SQL utilisées pour afficher les événements :</span><span class="sxs-lookup"><span data-stu-id="82580-152">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'  
  
    ```  
  
    ```  
    -- to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="82580-153">Les étapes de cette section sont propres à la configuration initiale de la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="82580-153">The steps described in this section are specifically for configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the first time on the database.</span></span> <span data-ttu-id="82580-154">Vous pouvez modifier les configurations existantes à l’aide de la même procédure stockée système **smart_admin. sp_set_db_backup** et fournir les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="82580-154">You can modify the existing configurations using the same system stored procedure **smart_admin.sp_set_db_backup** and provide the new values.</span></span> <span data-ttu-id="82580-155">Pour plus d’informations, consultez [SQL Server la sauvegarde managée vers Microsoft Azure paramètres de rétention et de stockage](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span><span class="sxs-lookup"><span data-stu-id="82580-155">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span></span>  
  
### <a name="enable-ss_smartbackup-for-the-instance-with-default-settings"></a><span data-ttu-id="82580-156">Activer la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] pour l'instance avec des paramètres par défaut</span><span class="sxs-lookup"><span data-stu-id="82580-156">Enable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the Instance with Default Settings</span></span>  
 <span data-ttu-id="82580-157">Ce didacticiel décrit les étapes à suivre pour activer et configurer [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] pour l’instance « MyInstance » \\ .</span><span class="sxs-lookup"><span data-stu-id="82580-157">This tutorial describes the steps to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the instance, 'MyInstance',\\.</span></span> <span data-ttu-id="82580-158">Il inclut les étapes pour activer la surveillance de l'état d'intégrité de la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82580-158">It includes steps to enable monitoring the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="82580-159">**Autorisations :**</span><span class="sxs-lookup"><span data-stu-id="82580-159">**Permissions:**</span></span>  
  
-   <span data-ttu-id="82580-160">Requiert l’appartenance au rôle de base de données **db_backupoperator** , avec les autorisations **ALTER ANY CREDENTIAL** et les `EXECUTE` autorisations sur **sp_delete_backuphistory**procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="82580-160">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="82580-161">Requiert des autorisations **Select** sur la fonction **smart_admin. fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="82580-161">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="82580-162">Requiert `EXECUTE` des autorisations sur la procédure stockée **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="82580-162">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="82580-163">En outre, nécessite les autorisations `VIEW SERVER STATE`, car elle appelle en interne d'autres objets système qui nécessitent cette autorisation.</span><span class="sxs-lookup"><span data-stu-id="82580-163">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  


1.  <span data-ttu-id="82580-164">**Créez un compte de stockage Microsoft Azure :** Les sauvegardes sont stockées dans le service de stockage Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="82580-164">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="82580-165">Vous devez d’abord créer un compte de stockage Microsoft Azure, si vous n’avez pas encore de compte.</span><span class="sxs-lookup"><span data-stu-id="82580-165">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="82580-166">SQL Server 2014 utilise des objets BLOB de pages, qui sont différents des objets BLOB de blocs et d’ajout.</span><span class="sxs-lookup"><span data-stu-id="82580-166">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="82580-167">Par conséquent, vous devez créer un compte à usage général, et non un compte d’objet BLOB.</span><span class="sxs-lookup"><span data-stu-id="82580-167">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="82580-168">Pour plus d’informations, consultez la rubrique [À propos des comptes de stockage Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="82580-168">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="82580-169">Notez le nom du compte de stockage et les clés d'accès.</span><span class="sxs-lookup"><span data-stu-id="82580-169">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="82580-170">Le nom du compte de stockage et les informations de clé d'accès sont utilisés pour créer un objet contenant les informations d'identification SQL.</span><span class="sxs-lookup"><span data-stu-id="82580-170">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="82580-171">Les informations d'identification SQL servent à authentifier le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="82580-171">The SQL Credential is used to authenticate to the storage account.</span></span>  
  
2.  <span data-ttu-id="82580-172">**Créer des informations d’identification SQL :** Créez des informations d’identification SQL en utilisant le nom du compte de stockage comme identité et la clé d’accès de stockage comme mot de passe.</span><span class="sxs-lookup"><span data-stu-id="82580-172">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="82580-173">**Vérifiez que le service SQL Server Agent est démarré et exécuté :** Démarrez SQL Server Agent s’il n’est pas exécuté actuellement.</span><span class="sxs-lookup"><span data-stu-id="82580-173">**Ensure SQL Server Agent service is Started and Running:** Start SQL Server Agent if it is not currently running.</span></span> [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="82580-174">nécessite l'exécution de SQL Server Agent sur l'instance pour effectuer les opérations de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="82580-174">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="82580-175">Vous pouvez configurer l'exécution automatique de SQL Server Agent, pour vous assurer que les opérations de sauvegarde se déroulent régulièrement.</span><span class="sxs-lookup"><span data-stu-id="82580-175">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="82580-176">**Déterminez la période de rétention :** Déterminez la période de conservation des fichiers de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="82580-176">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="82580-177">La période de rétention est spécifiée en jours, sur une plage de 1 à 30.</span><span class="sxs-lookup"><span data-stu-id="82580-177">The retention period is specified in days and can range from 1 to 30.</span></span> <span data-ttu-id="82580-178">Après l'activation de la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] au niveau de l'instance avec les paramètres par défaut, toutes les nouvelles bases de données créées héritent de ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="82580-178">Once [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] is enabled at the instance level with the defaults all new databases created thereafter will inherit the settings.</span></span> <span data-ttu-id="82580-179">Seules les bases de données employant le mode de récupération complète ou le mode de récupération utilisant les journaux de transactions sont prises en charge et sont configurées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="82580-179">Only databases that are set to full or bulk-logged recovery models are supported and will be configured automatically.</span></span> <span data-ttu-id="82580-180">Vous pouvez désactiver la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] pour une base de données spécifique à tout moment si vous ne souhaitez pas que la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] soit configurée.</span><span class="sxs-lookup"><span data-stu-id="82580-180">You may disable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a specific database at any time if you  do not want [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configured.</span></span> <span data-ttu-id="82580-181">Vous pouvez également modifier la configuration d'une base de données spécifique en configurant la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="82580-181">You can also change the configuration for a specific database by configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
5.  <span data-ttu-id="82580-182">**Activer et configurer [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Démarrez SQL Server Management Studio et connectez-vous à l’instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82580-182">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance of SQL Server.</span></span> <span data-ttu-id="82580-183">Dans la fenêtre de requête, exécutez l'instruction suivante après avoir modifié les valeurs du nom de la base de données, des informations d'identification SQL, de la période de rétention et des options de chiffrement selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="82580-183">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and the encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="82580-184">Pour plus d’informations sur la création d’un certificat pour le chiffrement, consultez l’étape **créer un certificat de sauvegarde** dans [créer une sauvegarde chiffrée](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="82580-184">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    Go  
       EXEC smart_admin.sp_set_instance_backup  
                     @enable_backup=1  
                    ,@retention_days=30   
                    ,@credential_name='sqlbackuptoURL'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert';  
    GO  
  
    ```  
  
     <span data-ttu-id="82580-185">La [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] est maintenant activée sur l'instance.</span><span class="sxs-lookup"><span data-stu-id="82580-185">[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] is now enabled on the instance.</span></span>  
  
6.  <span data-ttu-id="82580-186">Vérifiez les paramètres de configuration en exécutant l'instruction Transact-SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="82580-186">Verify the configuration settings by running the following Transact-SQL statement:</span></span>  
  
    ```  
    Use msdb;  
    GO  
    SELECT * FROM smart_admin.fn_backup_instance_config ();  
  
    ```  
  
7.  <span data-ttu-id="82580-187">Créez une nouvelle base de données sur l'instance.</span><span class="sxs-lookup"><span data-stu-id="82580-187">Create a new database on the instance.</span></span> <span data-ttu-id="82580-188">Exécutez l'instruction Transact-SQL suivante pour afficher les paramètres de configuration de la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] pour la base de données :</span><span class="sxs-lookup"><span data-stu-id="82580-188">Run the following Transact-SQL statement to view the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configuration settings for the database:</span></span>  
  
    ```  
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('NewDB')  
    ```  
  
     <span data-ttu-id="82580-189">Un délai de 15 minutes au maximum peut être nécessaire pour l'affichage des paramètres et le démarrage des opérations de sauvegarde sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="82580-189">It may take up to 15 minutes for the settings to show and backup operations on the database to start to run.</span></span>  
  
8.  <span data-ttu-id="82580-190">**Activez et configurez les notifications de l’état d’intégrité :** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] fournit une procédure stockée qui crée un travail d’agent pour envoyer des notifications par e-mail des erreurs ou des avertissements susceptibles de nécessiter une intervention.</span><span class="sxs-lookup"><span data-stu-id="82580-190">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span>  <span data-ttu-id="82580-191">Pour recevoir ces notifications, vous devez activer l'exécution de la procédure stockée qui crée un travail SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="82580-191">To receive such notifications, you must enable run the stored procedure which creates a SQL Server Agent Job.</span></span> <span data-ttu-id="82580-192">Les étapes suivantes décrivent la procédure d'activation et de configuration des notifications par courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="82580-192">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="82580-193">Configurez la messagerie de base de données si elle n'est pas déjà activée sur l'instance.</span><span class="sxs-lookup"><span data-stu-id="82580-193">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="82580-194">Pour plus d'informations, consultez [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="82580-194">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="82580-195">Configurez la notification SQL Server Agent afin qu'elle utilise la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="82580-195">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="82580-196">Pour plus d’informations, consultez [Configurer la messagerie de SQL Server Agent en vue de l’utilisation de la messagerie de base de données](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="82580-196">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="82580-197">**Activez les notifications par e-mail afin de recevoir les erreurs de sauvegarde et les avertissements :** Dans la fenêtre de requête, exécutez les instructions Transact-SQL suivantes :</span><span class="sxs-lookup"><span data-stu-id="82580-197">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email address>'  
  
        ```  
  
         <span data-ttu-id="82580-198">Pour plus d’informations sur la façon de surveiller, et un exemple de script complet, consultez [monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="82580-198">For more information about how to monitor, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
9. <span data-ttu-id="82580-199">**Affichez les fichiers de sauvegarde dans le compte de Stockage Microsoft Azure**. Connectez-vous au compte de stockage depuis SQL Server Management Studio ou depuis le Portail de gestion Azure.</span><span class="sxs-lookup"><span data-stu-id="82580-199">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="82580-200">Vous verrez un conteneur pour l'instance de SQL Server qui héberge la base de données que vous avez configurée pour utiliser la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82580-200">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="82580-201">Vous pourrez voir aussi une base de données et une sauvegarde de journal 15 minutes après la création de la base de données.</span><span class="sxs-lookup"><span data-stu-id="82580-201">You may also see a database and a log backup within 15 minutes of creating a new database.</span></span>  
  
10. <span data-ttu-id="82580-202">**Supervisez l’état d’intégrité :**  Vous pouvez le superviser au moyen des notifications par e-mail configurées précédemment, ou en supervisant activement les événements enregistrés.</span><span class="sxs-lookup"><span data-stu-id="82580-202">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="82580-203">Voici quelques exemples d'instructions Transact SQL utilisées pour afficher les événements :</span><span class="sxs-lookup"><span data-stu-id="82580-203">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'  
  
    ```  
  
    ```  
    --  to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="82580-204">Les paramètres par défaut de la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] peuvent être remplacés pour une base de données spécifique en les configurant directement au niveau de cette base de données.</span><span class="sxs-lookup"><span data-stu-id="82580-204">[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] default settings can be overridden for a specific database by configuring the settings specifically at the database level.</span></span> <span data-ttu-id="82580-205">Vous pouvez également interrompre et reprendre temporairement le service de [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82580-205">You can also pause and resume [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] service temporarily.</span></span> <span data-ttu-id="82580-206">Pour plus d’informations, consultez [SQL Server gestion de la sauvegarde vers Microsoft Azure paramètres de rétention et de stockage](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="82580-206">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)</span></span>  
  
  
