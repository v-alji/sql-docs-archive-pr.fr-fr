---
title: Restaurations complètes de bases de données (mode de récupération complète) | Microsoft Docs
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
- restoring [SQL Server], database
- full recovery model [SQL Server], performing restores
- log backups [SQL Server[
ms.assetid: 5b4c471c-b972-498e-aba9-92cf7a0ea881
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea6ec9f196acd0a64a0b785024bd6426cd6a5381
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614679"
---
# <a name="complete-database-restores-full-recovery-model"></a><span data-ttu-id="ba605-102">Restaurations complètes de bases de données (mode de récupération complète)</span><span class="sxs-lookup"><span data-stu-id="ba605-102">Complete Database Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="ba605-103">Lors d'une restauration complète de base de données, le but est de restaurer la totalité de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ba605-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="ba605-104">L'ensemble de la base de données est hors ligne pendant la durée de la restauration.</span><span class="sxs-lookup"><span data-stu-id="ba605-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="ba605-105">Avant qu'une partie quelconque de la base de données ne puisse être mise en ligne, toutes les données sont récupérées dans un état cohérent où toutes les parties de la base de données sont chronologiquement synchronisées et aucune transaction non validée n'existe.</span><span class="sxs-lookup"><span data-stu-id="ba605-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="ba605-106">Dans le mode de récupération complète, après avoir restauré vos sauvegardes de données, vous devez restaurer toutes les sauvegardes ultérieures des journaux de transactions, puis récupérer la base de données.</span><span class="sxs-lookup"><span data-stu-id="ba605-106">Under the full recovery model, after you restore your data backup or backups, you must restore all subsequent transaction log backups and then recover the database.</span></span> <span data-ttu-id="ba605-107">Vous pouvez restaurer une base de données vers un *point de récupération* spécifique dans l'une de ces sauvegardes de fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="ba605-107">You can restore a database to a specific *recovery point* within one of these log backups.</span></span> <span data-ttu-id="ba605-108">Ce point de récupération peut correspondre à une date et une heure spécifiques, une transaction marquée ou un numéro séquentiel dans le journal (LSN, Log Sequence Number).</span><span class="sxs-lookup"><span data-stu-id="ba605-108">The recovery point can be a specific date and time, a marked transaction, or a log sequence number (LSN).</span></span>  
  
 <span data-ttu-id="ba605-109">Lorsque vous restaurez une base de données, en particulier en mode de restauration complète ou de récupération utilisant les journaux des transactions, vous devez utiliser une séquence de restauration unique.</span><span class="sxs-lookup"><span data-stu-id="ba605-109">When restoring a database, particularly under the full recovery model or bulk-logged recovery model, you should use a single restore sequence.</span></span> <span data-ttu-id="ba605-110">Une *séquence de restauration* consiste en une ou plusieurs opérations de restauration déplaçant des données entre une ou plusieurs phases de restauration.</span><span class="sxs-lookup"><span data-stu-id="ba605-110">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ba605-111">Nous vous recommandons de ne pas attacher ni restaurer de bases de données provenant de sources inconnues ou non approuvées.</span><span class="sxs-lookup"><span data-stu-id="ba605-111">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="ba605-112">Ces bases de données peuvent contenir du code malveillant qui peut exécuter du code [!INCLUDE[tsql](../../includes/tsql-md.md)] imprévisible ou causer des erreurs en modifiant le schéma ou la structure physique de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ba605-112">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="ba605-113">Avant d’utiliser une base de données issue d’une source inconnue ou non approuvée, exécutez [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sur la base de données sur un serveur autre qu’un serveur de production et examinez également le code, notamment les procédures stockées ou le code défini par l’utilisateur, de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ba605-113">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
 <span data-ttu-id="ba605-114">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="ba605-114">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="ba605-115">Restauration d’une base de données jusqu’au point de défaillance</span><span class="sxs-lookup"><span data-stu-id="ba605-115">Restoring a Database to the Point of Failure</span></span>](#PointOfFailure)  
  
-   [<span data-ttu-id="ba605-116">Restauration d’une base de données jusqu’à un point dans une sauvegarde de fichier journal</span><span class="sxs-lookup"><span data-stu-id="ba605-116">Restoring a Database to a Point Within a Log Backup</span></span>](#PointWithinBackup)  
  
-   [<span data-ttu-id="ba605-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ba605-117">Related Tasks</span></span>](#RelatedTasks)  
  
> [!NOTE]  
>  <span data-ttu-id="ba605-118">Pour plus d’informations sur la prise en charge de sauvegardes provenant de versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez la section « Prise en charge de la compatibilité » de [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba605-118">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="restoring-a-database-to-the-point-of-failure"></a><a name="PointOfFailure"></a> <span data-ttu-id="ba605-119">Restauration d'une base de données jusqu'au point de défaillance</span><span class="sxs-lookup"><span data-stu-id="ba605-119">Restoring a Database to the Point of Failure</span></span>  
 <span data-ttu-id="ba605-120">Généralement, la récupération d'une base de données jusqu'au point de défaillance comprend les étapes de base suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba605-120">Typically, recovering a database to the point of failure involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="ba605-121">Sauvegardez le journal des transactions actives (connu sous le nom de fin du journal).</span><span class="sxs-lookup"><span data-stu-id="ba605-121">Back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="ba605-122">Cela entraîne la création d'une sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="ba605-122">This creates a tail-log backup.</span></span> <span data-ttu-id="ba605-123">Si le journal des transactions actives n'est pas disponible, toutes les transactions contenues dans cette partie du journal sont perdues.</span><span class="sxs-lookup"><span data-stu-id="ba605-123">If the active transaction log is unavailable, all transactions in that part of the log are lost.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ba605-124">Dans le mode de récupération utilisant les journaux de transactions, la sauvegarde de tout journal contenant des opérations journalisées en bloc nécessite un accès à tous les fichiers de données dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="ba605-124">Under the bulk-logged recovery model, backing up any log that contains bulk-logged operations requires access to all data files in the database.</span></span> <span data-ttu-id="ba605-125">Si les fichiers de données ne sont pas accessibles, le journal des transactions ne peut pas être sauvegardé.</span><span class="sxs-lookup"><span data-stu-id="ba605-125">If the data files cannot be accessed, the transaction log cannot be backed up.</span></span> <span data-ttu-id="ba605-126">Dans ce cas, vous devez répéter manuellement tous les changements effectués depuis la dernière sauvegarde du journal.</span><span class="sxs-lookup"><span data-stu-id="ba605-126">In that case, you have to manually redo all changes that were made since the most recent log backup.</span></span>  
  
     <span data-ttu-id="ba605-127">Pour plus d’informations, consultez [Sauvegardes de la fin du journal &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba605-127">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="ba605-128">Restaurez la sauvegarde complète de base de données la plus récente sans récupérer la base de données (RESTORE DATABASE *nom_base_de_données* FROM *unité_sauvegarde* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="ba605-128">Restore the most recent full database backup without recovering the database (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span></span>  
  
3.  <span data-ttu-id="ba605-129">S’il existe des sauvegardes différentielles, restaurez la plus récente sans récupérer la base de données (RESTORE DATABASE *nom_base_de_données* FROM *unité_sauvegarde_différentielle* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="ba605-129">If differential backups exist, restore the most recent one without recovering the database (RESTORE DATABASE *database_name* FROM *differential_backup_device* WITH NORECOVERY).</span></span>  
  
     <span data-ttu-id="ba605-130">La restauration de la sauvegarde différentielle la plus récente réduit le nombre de sauvegardes de fichiers journaux qui doivent être restaurées.</span><span class="sxs-lookup"><span data-stu-id="ba605-130">Restoring the most recent differential backup reduces the number of log backups that must be restored.</span></span>  
  
4.  <span data-ttu-id="ba605-131">En commençant par la première sauvegarde du journal des transactions qui a été créée après la sauvegarde que vous venez de restaurer, restaurez les journaux en séquence avec l'instruction NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="ba605-131">Starting with the first transaction log backup that was created after the backup you just restored, restore the logs in sequence with NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="ba605-132">Récupérez la base de données (RESTORE DATABASE *nom_base_de_données* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="ba605-132">Recover the database (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span> <span data-ttu-id="ba605-133">Cette étape peut également être combinée avec la restauration de la dernière sauvegarde du journal.</span><span class="sxs-lookup"><span data-stu-id="ba605-133">Alternatively, this step can be combined with restoring the last log backup.</span></span>  
  
 <span data-ttu-id="ba605-134">L'illustration suivante montre cette séquence de restauration.</span><span class="sxs-lookup"><span data-stu-id="ba605-134">The following illustration shows this restore sequence.</span></span> <span data-ttu-id="ba605-135">Après une défaillance (1), une sauvegarde de la fin du journal est créée (2).</span><span class="sxs-lookup"><span data-stu-id="ba605-135">After a failure occurs (1), a tail-log backup is created (2).</span></span> <span data-ttu-id="ba605-136">Ensuite, la base de données est restaurée jusqu'au point de défaillance.</span><span class="sxs-lookup"><span data-stu-id="ba605-136">Next, the database is restored to the point of the failure.</span></span> <span data-ttu-id="ba605-137">Cela implique la restauration d'une sauvegarde de base de données suivie d'une sauvegarde différentielle, ainsi que de chaque sauvegarde de journal effectuée après la sauvegarde différentielle, y compris la sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="ba605-137">This involves restoring a database backup, a subsequent differential backup, and every log backup taken after the differential backup, including the tail-log backup.</span></span>  
  
 <span data-ttu-id="ba605-138">![Restauration de base de données complète au moment d'une défaillance](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Restauration de base de données complète au moment d'une défaillance")</span><span class="sxs-lookup"><span data-stu-id="ba605-138">![Complete database restore to the time of a failure](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Complete database restore to the time of a failure")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba605-139">Quand vous restaurez une sauvegarde de base de données sur une instance de serveur différente, consultez [Copier des bases de données avec la sauvegarde et la restauration](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="ba605-139">When you restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="ba605-140">Syntaxe de base de l'instruction Transact-SQL RESTORE</span><span class="sxs-lookup"><span data-stu-id="ba605-140">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="ba605-141">La syntaxe [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] de base pour la séquence de restauration dans l’illustration précédente est la suivante :</span><span class="sxs-lookup"><span data-stu-id="ba605-141">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for the restore sequence in the preceding illustration is as follows:</span></span>  
  
1.  <span data-ttu-id="ba605-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="ba605-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span></span>  
  
2.  <span data-ttu-id="ba605-143">RESTORE DATABASE *base_de_données* FROM *sauvegarde_base_de_données_complète* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="ba605-143">RESTORE DATABASE *database* FROM *full_differential_backup* WITH NORECOVERY;</span></span>  
  
3.  <span data-ttu-id="ba605-144">RESTORE LOG *base_de_données* FROM *sauvegarde_journal* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="ba605-144">RESTORE LOG *database* FROM *log_backup* WITH NORECOVERY;</span></span>  
  
     <span data-ttu-id="ba605-145">Répétez cette étape de restauration pour chaque sauvegarde de fichier journal supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="ba605-145">Repeat this restore-log step for each additional log backup.</span></span>  
  
4.  <span data-ttu-id="ba605-146">RESTORE DATABASE *database* WITH RECOVERY;</span><span class="sxs-lookup"><span data-stu-id="ba605-146">RESTORE DATABASE *database* WITH RECOVERY;</span></span>  
  
###  <a name="example-recovering-to-the-point-of-failure-transact-sql"></a><a name="ExampleToPoFTsql"></a> <span data-ttu-id="ba605-147">Exemple : récupération jusqu’au point de défaillance (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ba605-147">Example: Recovering to the Point of Failure (Transact-SQL)</span></span>  
 <span data-ttu-id="ba605-148">L'exemple [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant indique les principales options d'une séquence de restauration qui restaure la base de données jusqu'au point de défaillance.</span><span class="sxs-lookup"><span data-stu-id="ba605-148">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] example shows the essential options in a restore sequence that restores the database to the point of failure.</span></span> <span data-ttu-id="ba605-149">L'exemple crée une sauvegarde de la fin du journal de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ba605-149">The example creates a tail-log backup of the database.</span></span> <span data-ttu-id="ba605-150">Ensuite, il restaure une sauvegarde complète de base de données et une sauvegarde de fichier journal, puis restaure la sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="ba605-150">Next, the example restores a full database backup and log backup and then restores the tail-log backup.</span></span> <span data-ttu-id="ba605-151">L'exemple récupère la base de données dans une dernière étape séparée.</span><span class="sxs-lookup"><span data-stu-id="ba605-151">The example recovers the database in a separate, final step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba605-152">Cet exemple utilise une sauvegarde de base de données et une sauvegarde du journal créées dans la section « Utilisation des sauvegardes de base de données en mode de récupération complète » dans [Sauvegardes complètes de bases de données &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba605-152">This example uses a database backup and log backup that is created in the "Using Database Backups Under the Full Recovery Model" section in [Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span></span> <span data-ttu-id="ba605-153">Avant la sauvegarde de la base de données, l'exemple de base de données de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] a été défini pour utiliser le mode de récupération complète.</span><span class="sxs-lookup"><span data-stu-id="ba605-153">Before the database backup, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database was set to use the full recovery model.</span></span>  
  
```  
USE master;  
--Create tail-log backup.  
BACKUP LOG AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'    
   WITH NORECOVERY;   
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=1,   
    NORECOVERY;  
  
--Restore the regular log backup (from backup set 2).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=2,   
    NORECOVERY;  
  
--Restore the tail-log backup (from backup set 3).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'  
  WITH FILE=3,   
    NORECOVERY;  
GO  
--recover the database:  
RESTORE DATABASE AdventureWorks2012 WITH RECOVERY;  
GO  
```  
  
##  <a name="restoring-a-database-to-a-point-within-a-log-backup"></a><a name="PointWithinBackup"></a> <span data-ttu-id="ba605-154">Restauration d'une base de données jusqu'à un point dans une sauvegarde de fichier journal</span><span class="sxs-lookup"><span data-stu-id="ba605-154">Restoring a Database to a Point Within a Log Backup</span></span>  
 <span data-ttu-id="ba605-155">En mode de récupération complète, une restauration complète de base de données peut généralement être récupérée jusqu'à une date et une heure, une transaction marquée ou un LSN dans une sauvegarde de fichier journal.</span><span class="sxs-lookup"><span data-stu-id="ba605-155">Under the full recovery model, a complete database restore can usually be recovered to a point of time, a marked transaction, or an LSN within a log backup.</span></span> <span data-ttu-id="ba605-156">Cependant, en mode de récupération utilisant les journaux des transactions, si la sauvegarde du journal contient des modifications journalisées en bloc, la récupération jusqu'à une date et heure est impossible.</span><span class="sxs-lookup"><span data-stu-id="ba605-156">However, under the bulk-logged recovery model, if the log backup contains bulk-logged changes, point-in-time recovery is not possible.</span></span>  
  
### <a name="sample-point-in-time-restore-scenarios"></a><span data-ttu-id="ba605-157">Exemples de scénarios de restauration jusqu'à une date et heure</span><span class="sxs-lookup"><span data-stu-id="ba605-157">Sample Point-in-Time Restore Scenarios</span></span>  
 <span data-ttu-id="ba605-158">L'exemple suivant suppose un système de bases de données critique pour lequel une sauvegarde complète est créée chaque nuit à minuit, une sauvegarde différentielle chaque heure tous les jours du lundi au samedi et une sauvegarde du journal des transactions toutes les 10 minutes pendant la journée.</span><span class="sxs-lookup"><span data-stu-id="ba605-158">The following example assumes a mission-critical database system for which a full database backup is created daily at midnight, a differential database backup is created on the hour, Monday through Saturday, and transaction log backups are created every 10 minutes throughout the day.</span></span> <span data-ttu-id="ba605-159">Pour restaurer la base de données telle qu'elle était à 5h19 mercredi :</span><span class="sxs-lookup"><span data-stu-id="ba605-159">To restore the database to the state is was in at 5:19 A.M.</span></span> <span data-ttu-id="ba605-160">Vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba605-160">Wednesday, do the following:</span></span>  
  
1.  <span data-ttu-id="ba605-161">Restaurez la sauvegarde complète de la base de données créée mardi à minuit.</span><span class="sxs-lookup"><span data-stu-id="ba605-161">Restore the full database backup that was created Tuesday at midnight.</span></span>  
  
2.  <span data-ttu-id="ba605-162">Restaurez la sauvegarde différentielle de base de données créée à 5h00</span><span class="sxs-lookup"><span data-stu-id="ba605-162">Restore the differential database backup that was created at 5:00 A.M.</span></span> <span data-ttu-id="ba605-163">mercredi.</span><span class="sxs-lookup"><span data-stu-id="ba605-163">on Wednesday.</span></span>  
  
3.  <span data-ttu-id="ba605-164">Appliquez la sauvegarde de journal des transactions qui a été créée à 5h10</span><span class="sxs-lookup"><span data-stu-id="ba605-164">Apply the transaction log backup that was created at 5:10 A.M.</span></span> <span data-ttu-id="ba605-165">mercredi.</span><span class="sxs-lookup"><span data-stu-id="ba605-165">on Wednesday.</span></span>  
  
4.  <span data-ttu-id="ba605-166">Appliquez la sauvegarde de journal des transactions qui a été créée à 5h20</span><span class="sxs-lookup"><span data-stu-id="ba605-166">Apply the transaction log backup that was created 5:20 A.M.</span></span> <span data-ttu-id="ba605-167">mercredi, en précisant que la procédure de récupération ne s'applique qu'aux transactions ayant eu lieu avant 5h19.</span><span class="sxs-lookup"><span data-stu-id="ba605-167">on Wednesday, specifying that the recovery process applies only to transactions that occurred before 5:19 A.M.</span></span>  
  
 <span data-ttu-id="ba605-168">Puis, si la base de données doit être restaurée à son état initial à 3h04 le jeudi matin,</span><span class="sxs-lookup"><span data-stu-id="ba605-168">Alternatively, if the database needs to be restored to its state at 3:04 A.M.</span></span> <span data-ttu-id="ba605-169">mais que la sauvegarde différentielle créée le jeudi à 3h00 n'est pas disponible,</span><span class="sxs-lookup"><span data-stu-id="ba605-169">Thursday, but the differential database backup that was created at 3:00 A.M.</span></span> <span data-ttu-id="ba605-170">effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba605-170">Thursday is unavailable, do the following:</span></span>  
  
1.  <span data-ttu-id="ba605-171">Restaurez la sauvegarde de base de données qui a été créée mercredi à minuit.</span><span class="sxs-lookup"><span data-stu-id="ba605-171">Restore the database backup that was created Wednesday at midnight.</span></span>  
  
2.  <span data-ttu-id="ba605-172">Restaurez la sauvegarde différentielle de base de données créée à 2h00</span><span class="sxs-lookup"><span data-stu-id="ba605-172">Restore the differential database backup that was created at 2:00 A.M.</span></span> <span data-ttu-id="ba605-173">jeudi.</span><span class="sxs-lookup"><span data-stu-id="ba605-173">on Thursday.</span></span>  
  
3.  <span data-ttu-id="ba605-174">Appliquez toutes les sauvegardes de journal des transactions créées entre 2h10</span><span class="sxs-lookup"><span data-stu-id="ba605-174">Apply all the transaction log backups created from 2:10 A.M.</span></span> <span data-ttu-id="ba605-175">et 3h00</span><span class="sxs-lookup"><span data-stu-id="ba605-175">to 3:00 A.M.</span></span> <span data-ttu-id="ba605-176">jeudi.</span><span class="sxs-lookup"><span data-stu-id="ba605-176">on Thursday.</span></span>  
  
4.  <span data-ttu-id="ba605-177">Appliquez la sauvegarde de journal des transactions qui a été créée à 3h10</span><span class="sxs-lookup"><span data-stu-id="ba605-177">Apply the transaction log backup that was created at 3:10 A.M.</span></span> <span data-ttu-id="ba605-178">jeudi, en arrêtant le processus de récupération à 3h04.</span><span class="sxs-lookup"><span data-stu-id="ba605-178">on Thursday, stopping the recovery process at 3:04 A.M.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba605-179">Pour obtenir un exemple de restauration de point-à-temps, consultez [Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="ba605-179">For an example of a point-in-time restore, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ba605-180">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ba605-180">Related Tasks</span></span>  
 <span data-ttu-id="ba605-181">**Pour restaurer une sauvegarde complète de base de données**</span><span class="sxs-lookup"><span data-stu-id="ba605-181">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="ba605-182">Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ba605-182">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="ba605-183">Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba605-183">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="ba605-184">**Pour restaurer une sauvegarde différentielle de base de données**</span><span class="sxs-lookup"><span data-stu-id="ba605-184">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="ba605-185">Restaurer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba605-185">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="ba605-186">**Pour restaurer une sauvegarde de journal des transactions**</span><span class="sxs-lookup"><span data-stu-id="ba605-186">**To restore a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="ba605-187">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba605-187">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="ba605-188">**Pour restaurer une sauvegarde à l'aide de SMO (SQL Server Management Objects)**</span><span class="sxs-lookup"><span data-stu-id="ba605-188">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
 <span data-ttu-id="ba605-189">**Pour restaurer une base de données jusqu'à un point dans une sauvegarde de fichier journal**</span><span class="sxs-lookup"><span data-stu-id="ba605-189">**To restore a database to a point within a log backup**</span></span>  
  
-   [<span data-ttu-id="ba605-190">Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="ba605-190">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="ba605-191">Récupération de bases de données associées contenant une transaction marquée</span><span class="sxs-lookup"><span data-stu-id="ba605-191">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="ba605-192">Récupérer un numéro séquentiel dans le journal &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba605-192">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba605-193">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba605-193">See Also</span></span>  
 <span data-ttu-id="ba605-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba605-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="ba605-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba605-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ba605-196">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba605-196">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ba605-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba605-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="ba605-198">[Sauvegardes complètes de bases de données &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba605-198">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ba605-199">[Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba605-199">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ba605-200">[Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba605-200">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="ba605-201">Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba605-201">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
