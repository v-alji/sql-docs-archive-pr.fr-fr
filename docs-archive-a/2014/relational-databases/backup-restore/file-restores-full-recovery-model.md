---
title: Restaurations de fichiers (mode de récupération complète) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- full recovery model [SQL Server], performing restores
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- file restores [SQL Server], full recovery model
- restoring files [SQL Server], full recovery model
- Transact-SQL restore sequence
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: d2236a2a-4cf1-4c3f-b542-f73f6096e15c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 488515ec900867f13d33580402e36a3f98747bb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699833"
---
# <a name="file-restores-full-recovery-model"></a><span data-ttu-id="91977-102">Restaurations de fichiers (mode de récupération complète)</span><span class="sxs-lookup"><span data-stu-id="91977-102">File Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="91977-103">Cette rubrique concerne uniquement les bases de données contenant plusieurs fichiers ou groupes de fichiers en modes de restauration complète ou de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="91977-103">This topic is relevant only for databases that contain multiple files or filegroups under the full or bulk-load recovery model.</span></span>  
  
 <span data-ttu-id="91977-104">Le but d'une restauration de fichiers est de restaurer un ou plusieurs fichiers endommagés sans restaurer l'ensemble de la base de données.</span><span class="sxs-lookup"><span data-stu-id="91977-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="91977-105">Un scénario de restauration de fichiers consiste en une séquence de restauration unique qui copie, restaure par progression et récupère les données appropriées.</span><span class="sxs-lookup"><span data-stu-id="91977-105">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data</span></span>  
  
 <span data-ttu-id="91977-106">Si le groupe de fichiers en cours de restauration est en lecture-écriture, une séquence ininterrompue de sauvegardes de journal doit être appliquée après la restauration de la dernière sauvegarde de données ou différentielle.</span><span class="sxs-lookup"><span data-stu-id="91977-106">If the filegroup that is being restored is read/write, an unbroken chain of log backups must be applied after the last data or differential backup is restored.</span></span> <span data-ttu-id="91977-107">Cette opération restaure le groupe de fichiers par progression jusqu'aux enregistrements de journal dans les enregistrements actifs en cours du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="91977-107">This brings the filegroup forward to the log records in the current active log records in the log file.</span></span> <span data-ttu-id="91977-108">Le point de récupération est généralement situé vers la fin du journal, mais pas nécessairement.</span><span class="sxs-lookup"><span data-stu-id="91977-108">The recovery point is typically near the end of log, but not necessarily.</span></span>  
  
 <span data-ttu-id="91977-109">Si le groupe de fichiers en cours de restauration est en lecture seule, l'application de sauvegardes de journal est souvent inutile et ignorée.</span><span class="sxs-lookup"><span data-stu-id="91977-109">If the filegroup that is being restored is read-only, usually applying log backups is unnecessary and is skipped.</span></span> <span data-ttu-id="91977-110">Si la sauvegarde a été réalisée après la mise en lecture seule du fichier, il s'agit de la dernière sauvegarde à restaurer.</span><span class="sxs-lookup"><span data-stu-id="91977-110">If the backup was taken after the file became read-only, that is the last backup to restore.</span></span> <span data-ttu-id="91977-111">La récupération par progression s'arrête au point cible.</span><span class="sxs-lookup"><span data-stu-id="91977-111">Roll forward stops at the target point.</span></span>  
  
 <span data-ttu-id="91977-112">Les scénarios de restauration de fichiers sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="91977-112">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="91977-113">Restauration de fichiers hors ligne</span><span class="sxs-lookup"><span data-stu-id="91977-113">Offline file restore</span></span>  
  
     <span data-ttu-id="91977-114">Dans une *restauration de fichiers hors ligne*, la base de données est hors connexion pendant la restauration des fichiers ou des groupes de fichiers endommagés.</span><span class="sxs-lookup"><span data-stu-id="91977-114">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="91977-115">À la fin de la séquence de restauration, la base de données est mise en ligne.</span><span class="sxs-lookup"><span data-stu-id="91977-115">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="91977-116">Toutes les éditions de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] prennent en charge la restauration de fichiers hors connexion.</span><span class="sxs-lookup"><span data-stu-id="91977-116">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="91977-117">Restauration de fichiers en ligne</span><span class="sxs-lookup"><span data-stu-id="91977-117">Online file restore</span></span>  
  
     <span data-ttu-id="91977-118">Dans une *restauration de fichiers en ligne*, si la base de données est en ligne au moment de la restauration, elle reste en ligne durant la restauration de fichiers.</span><span class="sxs-lookup"><span data-stu-id="91977-118">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="91977-119">Toutefois, chaque groupe de fichiers dans lequel un fichier est restauré est hors connexion pendant l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="91977-119">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="91977-120">Une fois que tous les fichiers d'un groupe de fichiers hors connexion sont récupérés, le groupe de fichiers est automatiquement mis en ligne.</span><span class="sxs-lookup"><span data-stu-id="91977-120">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="91977-121">Pour plus d’informations sur la prise en charge de la restauration de fichiers et de pages en ligne, consultez [Fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="91977-121">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="91977-122">Pour plus d’informations sur les restaurations en ligne, consultez [Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="91977-122">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="91977-123">Si vous voulez que la base de données soit hors connexion pour une restauration de fichiers, mettez celle-ci hors connexion avant de démarrer la séquence de restauration en exécutant l’instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) suivante : ALTER DATABASE *nom_base_de_données* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="91977-123">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  
  
  
##  <a name="restoring-damaged-files-from-file-backups"></a><a name="Overview"></a> <span data-ttu-id="91977-124">Restauration de fichiers endommagés à partir de sauvegardes de fichiers</span><span class="sxs-lookup"><span data-stu-id="91977-124">Restoring Damaged Files from File Backups</span></span>  
  
1.  <span data-ttu-id="91977-125">Avant de restaurer un ou plusieurs fichiers endommagés, essayez de créer une [sauvegarde de la fin du journal](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="91977-125">Before restoring one or more damaged files, attempt to create a [tail-log backup](tail-log-backups-sql-server.md).</span></span>  
  
     <span data-ttu-id="91977-126">Si l'enregistrement a été endommagé, il est impossible de créer une sauvegarde de la fin du journal, et vous devez restaurer la base de données.</span><span class="sxs-lookup"><span data-stu-id="91977-126">If the log has been damaged, a tail-log backup cannot be created, and you must restore the whole database.</span></span>  
  
     <span data-ttu-id="91977-127">Pour plus d’informations sur la sauvegarde d’un journal de transactions, consultez [Sauvegardes des journaux de transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="91977-127">For information about how to back up a transaction log, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="91977-128">Lors d'une restauration de fichiers hors connexion, vous devez toujours effectuer une sauvegarde de la fin du journal avant de restaurer les fichiers.</span><span class="sxs-lookup"><span data-stu-id="91977-128">For an offline file restore, you must always take a tail-log backup before the file restore.</span></span> <span data-ttu-id="91977-129">Lors d'une restauration de fichiers en ligne, vous devez toujours effectuer la sauvegarde de journal après la restauration des fichiers</span><span class="sxs-lookup"><span data-stu-id="91977-129">For an online file restore, you must always take the log backup after the file restore.</span></span> <span data-ttu-id="91977-130">Cette opération est nécessaire pour permettre au fichier d'être récupéré dans un état cohérent avec le reste de la base de données.</span><span class="sxs-lookup"><span data-stu-id="91977-130">This log backup is necessary to allow for the file to be recovered to a state consistent with the rest of the database.</span></span>  
  
2.  <span data-ttu-id="91977-131">Restaurez chaque fichier endommagé à partir de la sauvegarde la plus récente de ce fichier.</span><span class="sxs-lookup"><span data-stu-id="91977-131">Restore each damaged file from the most recent file backup of that file.</span></span>  
  
3.  <span data-ttu-id="91977-132">Restaurez la sauvegarde différentielle de fichiers la plus récente, si elle existe, pour chaque fichier restauré.</span><span class="sxs-lookup"><span data-stu-id="91977-132">Restore the most recent differential file backup, if any, for each restored file.</span></span>  
  
4.  <span data-ttu-id="91977-133">Restaurez dans l'ordre les sauvegardes du journal des transactions, en commençant par la sauvegarde correspondant aux fichiers restaurés les plus anciens jusqu'à la sauvegarde de la fin du journal créée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="91977-133">Restore transaction log backups in sequence, starting with the backup that covers the oldest of the restored files and ending with the tail-log backup created in step 1.</span></span>  
  
     <span data-ttu-id="91977-134">Vous devez restaurer les sauvegardes du journal des transactions créées après les sauvegardes de fichiers pour rendre à la base de données sa cohérence.</span><span class="sxs-lookup"><span data-stu-id="91977-134">You must restore the transaction log backups that were created after the file backups to bring the database to a consistent state.</span></span> <span data-ttu-id="91977-135">Les sauvegardes du journal des transactions peuvent être rapidement restaurées par progression, car seuls les changements concernant les fichiers restaurés sont appliqués.</span><span class="sxs-lookup"><span data-stu-id="91977-135">The transaction log backups can be rolled forward quickly, because only the changes that apply to the restored files are applied.</span></span> <span data-ttu-id="91977-136">La restauration de fichiers individuels est parfois une meilleure option que la restauration intégrale d'une base de données parce que les fichiers non endommagés ne sont pas copiés puis restaurés par progression.</span><span class="sxs-lookup"><span data-stu-id="91977-136">Restoring individual files can be better than restoring the whole database, because undamaged files are not copied and then rolled forward.</span></span> <span data-ttu-id="91977-137">Cependant, la lecture de la séquence complète des sauvegardes de journaux reste nécessaire.</span><span class="sxs-lookup"><span data-stu-id="91977-137">However, the whole chain of log backups still has to be read.</span></span>  
  
5.  <span data-ttu-id="91977-138">Récupérez la base de données.</span><span class="sxs-lookup"><span data-stu-id="91977-138">Recover the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91977-139">Les sauvegardes de fichiers peuvent également servir à restaurer la base de données à un état antérieur dans le temps.</span><span class="sxs-lookup"><span data-stu-id="91977-139">File backups can be used to restore the database to an earlier point in time.</span></span> <span data-ttu-id="91977-140">Pour cela, vous devez restaurer un jeu complet de sauvegardes de fichiers, puis restaurer dans l'ordre les sauvegardes du journal des transactions pour atteindre un moment cible postérieur à la fin de la dernière sauvegarde de fichiers restaurée.</span><span class="sxs-lookup"><span data-stu-id="91977-140">To do this, you must restore a complete set of file backups, and then restore transaction log backups in sequence to reach a target point that is after the end of the most recent restored file backup.</span></span> <span data-ttu-id="91977-141">Pour plus d’informations sur la récupération jusqu’à une date et heure, consultez [Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="91977-141">For more information about point-in-time recovery, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
## <a name="transact-sql-restore-sequence-for-an-offline-file-restore-full-recovery-model"></a><span data-ttu-id="91977-142">Séquence de restauration Transact-SQL pour une restauration de fichiers hors connexion (mode de restauration complète)</span><span class="sxs-lookup"><span data-stu-id="91977-142">Transact-SQL Restore Sequence for an Offline File Restore (Full Recovery Model)</span></span>  
 <span data-ttu-id="91977-143">Un scénario de restauration de fichiers consiste en une séquence de restauration unique qui copie, restaure par progression et récupère les données appropriées.</span><span class="sxs-lookup"><span data-stu-id="91977-143">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data.</span></span>  
  
 <span data-ttu-id="91977-144">Cette section présente les options [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) essentielles pour une séquence de restauration de fichiers.</span><span class="sxs-lookup"><span data-stu-id="91977-144">This section shows the essential [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a file-restore sequence.</span></span> <span data-ttu-id="91977-145">La syntaxe et les détails qui ne sont pas pertinents sont omis.</span><span class="sxs-lookup"><span data-stu-id="91977-145">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="91977-146">L'exemple de séquence de restauration suivant illustre une restauration hors ligne de deux fichiers secondaires, `A` et `B`, à l'aide de WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="91977-146">The following sample restore sequence shows an offline restore of two secondary files, `A` and `B`, using WITH NORECOVERY.</span></span> <span data-ttu-id="91977-147">Ensuite, deux sauvegardes de journal sont appliquées à l'aide de NORECOVERY, suivies de la sauvegarde de la fin du journal qui est restaurée à l'aide de WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="91977-147">Next, two log backups are applied with NORECOVERY, followed with the tail-log backup, and this is restored using WITH RECOVERY.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91977-148">L'exemple de séquence de restauration suivant commence par placer le fichier hors connexion, puis crée une sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="91977-148">The following sample restore sequence starts by taking the file offline and then creates a tail-log backup.</span></span>  
  
```  
--Take the file offline.  
ALTER DATABASE database_name MODIFY FILE SET OFFLINE;  
-- Back up the currently active transaction log.  
BACKUP LOG database_name  
   TO <tail_log_backup>  
   WITH NORECOVERY;  
GO   
-- Restore the files.  
RESTORE DATABASE database_name FILE=name   
   FROM <file_backup_of_file_A>   
   WITH NORECOVERY;  
RESTORE DATABASE database_name FILE=<name> ......  
   FROM <file_backup_of_file_B>   
   WITH NORECOVERY;  
-- Restore the log backups.  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <tail_log_backup>   
   WITH RECOVERY;  
```  
  
## <a name="examples"></a><span data-ttu-id="91977-149">Exemples</span><span class="sxs-lookup"><span data-stu-id="91977-149">Examples</span></span>  
  
-   [<span data-ttu-id="91977-150">Exemple : restauration en ligne d’un fichier en lecture/écriture &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="91977-150">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="91977-151">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="91977-151">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="91977-152">Exemple : restauration hors ligne du groupe de fichiers primaire et d’un autre groupe de fichiers &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="91977-152">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="91977-153">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="91977-153">Related Tasks</span></span>  
 <span data-ttu-id="91977-154">**Pour restaurer des fichiers et des groupes de fichiers**</span><span class="sxs-lookup"><span data-stu-id="91977-154">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="91977-155">Restaurer des fichiers à un nouvel emplacement &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="91977-155">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="91977-156">Restaurer des fichiers et des groupes de fichiers &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="91977-156">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="91977-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="91977-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="91977-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="91977-158">See Also</span></span>  
 <span data-ttu-id="91977-159">[Sauvegarde et restauration : interopérabilité et coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91977-159">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="91977-160">[Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91977-160">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="91977-161">[Sauvegardes de fichiers complètes &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91977-161">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="91977-162">[Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91977-162">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="91977-163">[Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91977-163">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="91977-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="91977-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="91977-165">[Restaurations complètes de bases de données &#40;mode de récupération simple&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="91977-165">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="91977-166">Restaurations fragmentaires &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="91977-166">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
