---
title: Restaurations de base de données complètes (mode de récupération simple) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- complete database restores
- database restores [SQL Server], complete database
- restoring databases [SQL Server], complete database
- simple recovery model [SQL Server]
- restoring [SQL Server], database
ms.assetid: 49828927-1727-4d1d-9ef5-3de43f68c026
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67eee8d7d6f44c9ff83795bf2a8bd612309bf0a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614676"
---
# <a name="complete-database-restores-simple-recovery-model"></a><span data-ttu-id="3e697-102">Restaurations complètes de bases de données (mode de récupération simple)</span><span class="sxs-lookup"><span data-stu-id="3e697-102">Complete Database Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="3e697-103">Lors d'une restauration complète de base de données, le but est de restaurer la totalité de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e697-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="3e697-104">L'ensemble de la base de données est hors ligne pendant la durée de la restauration.</span><span class="sxs-lookup"><span data-stu-id="3e697-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="3e697-105">Avant qu'une partie quelconque de la base de données ne puisse être mise en ligne, toutes les données sont récupérées dans un état cohérent où toutes les parties de la base de données sont chronologiquement synchronisées et aucune transaction non validée n'existe.</span><span class="sxs-lookup"><span data-stu-id="3e697-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="3e697-106">En mode de récupération simple, la base de données ne peut pas être restaurée à un certain point chronologique dans une sauvegarde spécifique.</span><span class="sxs-lookup"><span data-stu-id="3e697-106">Under the simple recovery model, the database cannot be restored to a specific point in time within a specific backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3e697-107">Nous vous recommandons de ne pas attacher ni restaurer de bases de données provenant de sources inconnues ou non approuvées.</span><span class="sxs-lookup"><span data-stu-id="3e697-107">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="3e697-108">Ces bases de données peuvent contenir du code malveillant qui peut exécuter du code [!INCLUDE[tsql](../../../includes/tsql-md.md)] imprévisible ou causer des erreurs en modifiant le schéma ou la structure physique de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e697-108">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="3e697-109">Avant d’utiliser une base de données issue d’une source inconnue ou non approuvée, exécutez [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sur la base de données sur un serveur autre qu’un serveur de production et examinez également le code, notamment les procédures stockées ou le code défini par l’utilisateur, de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e697-109">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="3e697-110">Pour plus d’informations sur la prise en charge de sauvegardes provenant de versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez la section « Prise en charge de la compatibilité » de [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e697-110">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="overview-of-database-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="3e697-111">Vue d'ensemble de la restauration de la base de données en mode de récupération simple</span><span class="sxs-lookup"><span data-stu-id="3e697-111">Overview of Database Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="3e697-112">Une restauration de base de données complète en mode de récupération simple s'effectue à l'aide d'une ou de deux instructions [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , selon qu'il faille ou non restaurer une sauvegarde de base de données différentielle.</span><span class="sxs-lookup"><span data-stu-id="3e697-112">A full database restore under the simple recovery model involves one or two [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statements, depending on whether you want to restore a differential database backup.</span></span> <span data-ttu-id="3e697-113">Si vous utilisez uniquement une sauvegarde complète de base de données, restaurez simplement la sauvegarde la plus récente, tel qu'indiqué dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="3e697-113">If you are using only a full database backup, just restore the most recent backup, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="3e697-114">![Restauration d’une sauvegarde de base de données complète uniquement](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Restauration d’une sauvegarde de base de données complète uniquement")</span><span class="sxs-lookup"><span data-stu-id="3e697-114">![Restoring only a full database backup](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Restoring only a full database backup")</span></span>  
  
 <span data-ttu-id="3e697-115">Si vous utilisez également une sauvegarde de base de données différentielle, restaurez la sauvegarde complète de base de données la plus récente sans récupérer la base de données, puis restaurez la sauvegarde de base de données différentielle la plus récente et récupérez la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e697-115">If you are also using a differential database backup, restore the most recent full database backup without recovering the database, and then restore the most recent differential database backup and recover the database.</span></span> <span data-ttu-id="3e697-116">L'illustration ci-dessous montre ce processus.</span><span class="sxs-lookup"><span data-stu-id="3e697-116">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="3e697-117">![Restauration de sauvegardes complètes et différentielles d’une base de données](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Restauration de sauvegardes complètes et différentielles d'une base de données")</span><span class="sxs-lookup"><span data-stu-id="3e697-117">![Restoring full and differential database backups](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Restoring full and differential database backups")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e697-118">Si vous envisagez de restaurer une sauvegarde de base de données sur une instance de serveur différente, consultez [Copier des bases de données avec la sauvegarde et la restauration](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="3e697-118">If you plan to restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="3e697-119">Syntaxe de base de l'instruction Transact-SQL RESTORE</span><span class="sxs-lookup"><span data-stu-id="3e697-119">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="3e697-120">La syntaxe [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) de base pour la restauration d’une sauvegarde complète de base de données est :</span><span class="sxs-lookup"><span data-stu-id="3e697-120">The basic [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a full database backup is:</span></span>  
  
 <span data-ttu-id="3e697-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span><span class="sxs-lookup"><span data-stu-id="3e697-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e697-122">Utilisez la commande WITH NORECOVERY si vous envisagez de restaurer aussi une sauvegarde de base de données différentielle.</span><span class="sxs-lookup"><span data-stu-id="3e697-122">Use WITH NORECOVERY if you plan to also restore a differential database backup.</span></span>  
  
 <span data-ttu-id="3e697-123">La syntaxe de base [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) pour la restauration d'une sauvegarde de base de données est :</span><span class="sxs-lookup"><span data-stu-id="3e697-123">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a database backup is:</span></span>  
  
 <span data-ttu-id="3e697-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="3e697-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span></span>  
  
###  <a name="example-transact-sql"></a><a name="Example"></a> <span data-ttu-id="3e697-125">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e697-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="3e697-126">L'exemple ci-dessous illustre d'abord l'utilisation de l'instruction [BACKUP](/sql/t-sql/statements/backup-transact-sql) pour créer une sauvegarde complète et une sauvegarde différentielle de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e697-126">The following example first shows how to use the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to create a full database backup and a differential database backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="3e697-127">L'exemple restaure ensuite ces sauvegardes dans l'ordre.</span><span class="sxs-lookup"><span data-stu-id="3e697-127">The example then restores these backups in sequence.</span></span> <span data-ttu-id="3e697-128">La base de données est restaurée dans l'état qui était le sien à la fin de la sauvegarde différentielle de base de données.</span><span class="sxs-lookup"><span data-stu-id="3e697-128">The database is restored to its state as of the time that the differential database backup finished.</span></span>  
  
 <span data-ttu-id="3e697-129">L'exemple illustre les options importantes d'une séquence de restauration dans le cadre d'un scénario de restauration complète de base de données.</span><span class="sxs-lookup"><span data-stu-id="3e697-129">The example shows the critical options in a restore sequence for the complete database restore scenario.</span></span> <span data-ttu-id="3e697-130">Une *séquence de restauration* consiste en une ou plusieurs opérations de restauration déplaçant des données entre une ou plusieurs phases de restauration.</span><span class="sxs-lookup"><span data-stu-id="3e697-130">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span> <span data-ttu-id="3e697-131">La syntaxe et les détails qui ne sont pas pertinents sont omis.</span><span class="sxs-lookup"><span data-stu-id="3e697-131">Syntax and details that are not relevant to this purpose are omitted.</span></span> <span data-ttu-id="3e697-132">Si vous récupérez une base de données, nous vous recommandons de spécifier explicitement l'option RECOVERY par souci de clarté, bien qu'il s'agisse de l'option par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e697-132">When you recover a database, we recommend explicitly specifying the RECOVERY option for clarity, even though it is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e697-133">L’exemple commence par une instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) qui affecte au mode de récupération la valeur `SIMPLE`.</span><span class="sxs-lookup"><span data-stu-id="3e697-133">The example starts with an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement that sets the recovery model to `SIMPLE`.</span></span>  
  
```  
USE master;  
--Make sure the database is using the simple recovery model.  
ALTER DATABASE AdventureWorks2012 SET RECOVERY SIMPLE;  
GO  
-- Back up the full AdventureWorks2012 database.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
  WITH FORMAT;  
GO  
--Create a differential database backup.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'  
   WITH DIFFERENTIAL;  
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=1, NORECOVERY;  
--Restore the differential backup (from backup set 2).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=2, RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3e697-134">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3e697-134">Related Tasks</span></span>  
 <span data-ttu-id="3e697-135">**Pour restaurer une sauvegarde complète de base de données**</span><span class="sxs-lookup"><span data-stu-id="3e697-135">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="3e697-136">Restaurer une sauvegarde de base de données en mode de récupération simple &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e697-136">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="3e697-137">Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e697-137">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="3e697-138">Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e697-138">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="3e697-139">**Pour restaurer une sauvegarde différentielle de base de données**</span><span class="sxs-lookup"><span data-stu-id="3e697-139">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="3e697-140">Restaurer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e697-140">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="3e697-141">**Pour restaurer une sauvegarde à l'aide de SMO (SQL Server Management Objects)**</span><span class="sxs-lookup"><span data-stu-id="3e697-141">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  

  
## <a name="see-also"></a><span data-ttu-id="3e697-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e697-142">See Also</span></span>  
 <span data-ttu-id="3e697-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e697-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="3e697-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e697-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="3e697-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e697-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="3e697-146">[Sauvegardes complètes de bases de données &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e697-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="3e697-147">[Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e697-147">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="3e697-148">[Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e697-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="3e697-149">Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e697-149">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
