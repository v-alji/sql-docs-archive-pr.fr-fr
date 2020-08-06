---
title: Déplacer des bases de données utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- editions [SQL Server], moving databases between
- moving full-text catalogs
- scheduled disk maintenace [SQL Server]
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- moving user databases
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: ad9a4e92-13fb-457d-996a-66ffc2d55b79
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c2b82c3bec13c82aa30aebd175ef78f8136ee04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604549"
---
# <a name="move-user-databases"></a><span data-ttu-id="7deac-102">Déplacer des bases de données utilisateur</span><span class="sxs-lookup"><span data-stu-id="7deac-102">Move User Databases</span></span>
  <span data-ttu-id="7deac-103">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez déplacer les fichiers de données, les fichiers journaux et les fichiers de catalogues de texte intégral d’une base de données utilisateur vers un nouvel emplacement, en spécifiant le nouvel emplacement de fichier dans la clause FILENAME de l’instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="7deac-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move the data, log, and full-text catalog files of a user database to a new location by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="7deac-104">Cette méthode s'applique au déplacement des fichiers de base de données dans la même instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7deac-104">This method applies to moving database files within the same instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7deac-105">Pour déplacer une base de données vers une autre instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou vers un autre serveur, utilisez les opérations de [sauvegarde et de restauration](../backup-restore/back-up-and-restore-of-sql-server-databases.md) ou les [opérations de détachement et d'attachement](move-a-database-using-detach-and-attach-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7deac-105">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach operations](move-a-database-using-detach-and-attach-transact-sql.md).</span></span>  
  
## <a name="considerations"></a><span data-ttu-id="7deac-106">Considérations</span><span class="sxs-lookup"><span data-stu-id="7deac-106">Considerations</span></span>  
 <span data-ttu-id="7deac-107">Lorsque vous déplacez une base de données sur une autre instance de serveur, pour garantir une expérience cohérente aux utilisateurs et aux applications, vous devrez peut-être recréer tout ou partie des métadonnées de la base de données.</span><span class="sxs-lookup"><span data-stu-id="7deac-107">When you move a database onto another server instance, to provide a consistent experience to users and applications, you might have to re-create some or all the metadata for the database.</span></span> <span data-ttu-id="7deac-108">Pour plus d’informations, consultez [Gérer les métadonnées durant la mise à disposition d’une base de données sur une autre instance de serveur &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="7deac-108">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
 <span data-ttu-id="7deac-109">Certaines fonctionnalités du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] modifient la façon dont le [!INCLUDE[ssDE](../../includes/ssde-md.md)] stocke les informations dans les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="7deac-109">Some features of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] change the way that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores information in the database files.</span></span> <span data-ttu-id="7deac-110">Ces fonctionnalités sont limitées à des éditions spécifiques de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7deac-110">These features are restricted to specific editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7deac-111">Une base de données qui contient ces fonctionnalités ne peut pas être déplacée vers une édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui ne les prend pas en charge.</span><span class="sxs-lookup"><span data-stu-id="7deac-111">A database that contains these features cannot be moved to an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that does not support them.</span></span> <span data-ttu-id="7deac-112">Utilisez la vue de gestion dynamique sys.dm_db_persisted_sku_features pour répertorier toutes les fonctions spécifiques à l'édition activées dans la base de données actuelle.</span><span class="sxs-lookup"><span data-stu-id="7deac-112">Use the sys.dm_db_persisted_sku_features dynamic management view to list all edition-specific features that are enabled in the current database.</span></span>  
  
 <span data-ttu-id="7deac-113">Les procédures de cette rubrique requièrent le nom logique des fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="7deac-113">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="7deac-114">Pour obtenir ce nom, interrogez la colonne name dans l’affichage catalogue [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="7deac-114">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="7deac-115">À partir de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], les catalogues de texte intégral sont intégrés dans la base de données plutôt que stockés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="7deac-115">Starting with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], full-text catalogs are integrated into the database rather than being stored in the file system.</span></span> <span data-ttu-id="7deac-116">Les catalogues de texte intégral se déplacent automatiquement lorsque vous déplacez une base de données.</span><span class="sxs-lookup"><span data-stu-id="7deac-116">The full-text catalogs now move automatically when you move a database.</span></span>  
  
## <a name="planned-relocation-procedure"></a><span data-ttu-id="7deac-117">Procédure de déplacement planifié</span><span class="sxs-lookup"><span data-stu-id="7deac-117">Planned Relocation Procedure</span></span>  
 <span data-ttu-id="7deac-118">Pour déplacer un fichier journal ou un fichier de données dans le cadre d'un déplacement planifié, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7deac-118">To move a data or log file as part of a planned relocation, follow these steps:</span></span>  
  
1.  <span data-ttu-id="7deac-119">Exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="7deac-119">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET OFFLINE;  
    ```  
  
2.  <span data-ttu-id="7deac-120">Déplacez le ou les fichiers vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="7deac-120">Move the file or files to the new location.</span></span>  
  
3.  <span data-ttu-id="7deac-121">Pour chaque fichier déplacé, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="7deac-121">For each file moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name, FILENAME = 'new_path\os_file_name' );  
    ```  
  
4.  <span data-ttu-id="7deac-122">Exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="7deac-122">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET ONLINE;  
    ```  
  
5.  <span data-ttu-id="7deac-123">Vérifiez le changement de fichier en exécutant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="7deac-123">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="relocation-for-scheduled-disk-maintenance"></a><span data-ttu-id="7deac-124">Déplacement en vue d'une maintenance de disque planifiée</span><span class="sxs-lookup"><span data-stu-id="7deac-124">Relocation for Scheduled Disk Maintenance</span></span>  
 <span data-ttu-id="7deac-125">Pour déplacer un fichier dans le cadre d'un processus de maintenance de disque planifié, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7deac-125">To relocate a file as part of a scheduled disk maintenance process, follow these steps:</span></span>  
  
1.  <span data-ttu-id="7deac-126">Pour chaque fichier à déplacer, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="7deac-126">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
2.  <span data-ttu-id="7deac-127">Arrêtez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou éteignez le système pour que la maintenance ait lieu.</span><span class="sxs-lookup"><span data-stu-id="7deac-127">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="7deac-128">Pour plus d'informations, consultez [Démarrer, arrêter, suspendre, reprendre, redémarrer les services SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="7deac-128">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="7deac-129">Déplacez le ou les fichiers vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="7deac-129">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="7deac-130">Redémarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou le serveur.</span><span class="sxs-lookup"><span data-stu-id="7deac-130">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="7deac-131">Pour plus d'informations, consultez [Démarrer, arrêter, suspendre, reprendre, redémarrer le moteur de base de données, SQL Server Agent ou le service SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)</span><span class="sxs-lookup"><span data-stu-id="7deac-131">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)</span></span>  
  
5.  <span data-ttu-id="7deac-132">Vérifiez le changement de fichier en exécutant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="7deac-132">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="failure-recovery-procedure"></a><span data-ttu-id="7deac-133">Procédure de récupération après défaillance</span><span class="sxs-lookup"><span data-stu-id="7deac-133">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="7deac-134">Si un fichier doit être déplacé dans un nouvel emplacement en raison d'une défaillance matérielle, suivez la procédure décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7deac-134">If a file must be moved because of a hardware failure, use the following steps to relocate the file to a new location.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7deac-135">Si la base de données ne démarre pas – elle est en mode suspect ou dans un état de non récupération, seuls les membres du rôle fixe sysadmin peuvent déplacer le fichier.</span><span class="sxs-lookup"><span data-stu-id="7deac-135">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="7deac-136">Arrêtez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si elle est démarrée.</span><span class="sxs-lookup"><span data-stu-id="7deac-136">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="7deac-137">Démarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode de récupération de la base de données master uniquement en tapant une des commandes suivantes à l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="7deac-137">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span>  
  
    -   <span data-ttu-id="7deac-138">Dans le cas d'une instance par défaut (MSSQLSERVER), exécutez la commande ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7deac-138">For the default (MSSQLSERVER) instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="7deac-139">Dans le cas d'une instance nommée, exécutez la commande ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7deac-139">For a named instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="7deac-140">Pour plus d'informations, consultez [Démarrer, arrêter, suspendre, reprendre, redémarrer les services SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="7deac-140">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="7deac-141">Pour chaque fichier à déplacer, utilisez les commandes **sqlcmd** ou [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] pour exécuter l’instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="7deac-141">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
     <span data-ttu-id="7deac-142">Pour plus d’informations sur l’utilisation de l’utilitaire **sqlcmd** , consultez [Utiliser l’utilitaire sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="7deac-142">For more information about how to use the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="7deac-143">Quittez l’utilitaire **sqlcmd** ou [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7deac-143">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="7deac-144">Arrêtez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7deac-144">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
6.  <span data-ttu-id="7deac-145">Déplacez le ou les fichiers vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="7deac-145">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="7deac-146">Démarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7deac-146">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7deac-147">Par exemple, exécutez : `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="7deac-147">For example, run: `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="7deac-148">Vérifiez le changement de fichier en exécutant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="7deac-148">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="examples"></a><span data-ttu-id="7deac-149">Exemples</span><span class="sxs-lookup"><span data-stu-id="7deac-149">Examples</span></span>  
 <span data-ttu-id="7deac-150">L'exemple suivant déplace le fichier journal [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] vers un nouvel emplacement dans le cadre d'un déplacement planifié.</span><span class="sxs-lookup"><span data-stu-id="7deac-150">The following example moves the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] log file to a new location as part of a planned relocation.</span></span>  
  
```  
USE master;  
GO  
-- Return the logical file name.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
GO  
ALTER DATABASE AdventureWorks2012 SET OFFLINE;  
GO  
-- Physically move the file to a new location.  
-- In the following statement, modify the path specified in FILENAME to  
-- the new location of the file on your server.  
ALTER DATABASE AdventureWorks2012   
    MODIFY FILE ( NAME = AdventureWorks2012_Log,   
                  FILENAME = 'C:\NewLoc\AdventureWorks2012_Log.ldf');  
GO  
ALTER DATABASE AdventureWorks2012 SET ONLINE;  
GO  
--Verify the new location.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
```  
  
## <a name="see-also"></a><span data-ttu-id="7deac-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7deac-151">See Also</span></span>  
 <span data-ttu-id="7deac-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7deac-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="7deac-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7deac-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="7deac-154">[Attacher et détacher une base de données &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7deac-154">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="7deac-155">[Déplacer des bases de données système](system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="7deac-155">[Move System Databases](system-databases.md) </span></span>  
 <span data-ttu-id="7deac-156">[Déplacer des fichiers de bases de données](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="7deac-156">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="7deac-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7deac-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="7deac-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7deac-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="7deac-159">Démarrer, arrêter, suspendre, reprendre, redémarrer le moteur de base de données, SQL Server Agent ou le service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="7deac-159">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
