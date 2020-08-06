---
title: Restauration de fichiers (mode de récupération simple) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- simple recovery model [SQL Server]
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- Transact-SQL restore sequence
- restoring files [SQL Server], simple recovery model
- file restores [SQL Server], simple recovery model
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: b6d07386-7c6f-4cc6-be32-93289adbd3d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ed48f48f531e727de5d6e1403ef47f5399f874d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699828"
---
# <a name="file-restores-simple-recovery-model"></a><span data-ttu-id="fa9ff-102">Restauration de fichiers (mode de récupération simple)</span><span class="sxs-lookup"><span data-stu-id="fa9ff-102">File Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="fa9ff-103">Cette rubrique ne concerne que les bases de données en mode simple contenant au moins un groupe de fichiers secondaire en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-103">This topic is relevant only for simple-model databases that contain at least one read-only secondary filegroup.</span></span>  
  
 <span data-ttu-id="fa9ff-104">Le but d'une restauration de fichiers est de restaurer un ou plusieurs fichiers endommagés sans restaurer l'ensemble de la base de données.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="fa9ff-105">Dans le cadre du mode de récupération simple, les sauvegardes de fichiers sont prises en charge uniquement pour les fichiers en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-105">Under the simple recovery model, file backups are supported only for read-only files.</span></span> <span data-ttu-id="fa9ff-106">Le groupe de fichiers primaire et les groupes de fichiers secondaires en lecture-écriture sont toujours restaurés conjointement lors de la restauration d'une sauvegarde partielle ou d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-106">The primary filegroup and read/write secondary filegroups are always restored together, by restoring a database or partial backup.</span></span>  
  
 <span data-ttu-id="fa9ff-107">Les scénarios de restauration de fichiers sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="fa9ff-107">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="fa9ff-108">Restauration de fichiers hors ligne</span><span class="sxs-lookup"><span data-stu-id="fa9ff-108">Offline file restore</span></span>  
  
     <span data-ttu-id="fa9ff-109">Dans une *restauration de fichiers hors ligne*, la base de données est hors connexion pendant la restauration des fichiers ou des groupes de fichiers endommagés.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-109">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="fa9ff-110">À la fin de la séquence de restauration, la base de données est mise en ligne.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-110">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="fa9ff-111">Toutes les éditions de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] prennent en charge la restauration de fichiers hors connexion.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-111">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="fa9ff-112">Restauration de fichiers en ligne</span><span class="sxs-lookup"><span data-stu-id="fa9ff-112">Online file restore</span></span>  
  
     <span data-ttu-id="fa9ff-113">Dans une *restauration de fichiers en ligne*, si la base de données est en ligne au moment de la restauration, elle reste en ligne durant la restauration de fichiers.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-113">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="fa9ff-114">Toutefois, chaque groupe de fichiers dans lequel un fichier est restauré est hors connexion pendant l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-114">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="fa9ff-115">Une fois que tous les fichiers d'un groupe de fichiers hors connexion sont récupérés, le groupe de fichiers est automatiquement mis en ligne.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-115">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="fa9ff-116">Pour plus d’informations sur la prise en charge de la restauration de fichiers et de pages en ligne, consultez [Fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="fa9ff-116">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="fa9ff-117">Pour plus d’informations sur les restaurations en ligne, consultez [Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fa9ff-117">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="fa9ff-118">Si vous voulez que la base de données soit hors connexion pour une restauration de fichiers, mettez celle-ci hors connexion avant de démarrer la séquence de restauration en exécutant l’instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) suivante : ALTER DATABASE *nom_base_de_données* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-118">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  

  
##  <a name="overview-of-file-and-filegroup-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="fa9ff-119">Vue d'ensemble de la restauration de fichiers et de groupes de fichiers en mode de récupération simple</span><span class="sxs-lookup"><span data-stu-id="fa9ff-119">Overview of File and Filegroup Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="fa9ff-120">Un scénario de restauration de fichiers consiste en une séquence de restauration unique qui copie, restaure par progression et récupère les données appropriées comme suit :</span><span class="sxs-lookup"><span data-stu-id="fa9ff-120">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data as follows:</span></span>  
  
1.  <span data-ttu-id="fa9ff-121">Restauration de chaque fichier endommagé à partir de sa toute dernière sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-121">Restore each damaged file from its most recent file backup.</span></span>  
  
2.  <span data-ttu-id="fa9ff-122">Restauration de la toute dernière sauvegarde de fichiers différentielle de chaque fichier restauré et récupération de la base de données.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-122">Restore the most recent differential file backup for each restored file and recover the database.</span></span>  
  
### <a name="transact-sql-steps-for-file-restore-sequence-simple-recovery-model"></a><span data-ttu-id="fa9ff-123">Étapes Transact-SQL pour une séquence de restauration de fichier (mode de récupération simple)</span><span class="sxs-lookup"><span data-stu-id="fa9ff-123">Transact-SQL Steps for File Restore Sequence (Simple Recovery Model)</span></span>  
 <span data-ttu-id="fa9ff-124">Cette section présente les options [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) essentielles pour une séquence de restauration de fichiers simple.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-124">This section shows the essential [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a simple file-restore sequence.</span></span> <span data-ttu-id="fa9ff-125">La syntaxe et les détails qui ne sont pas pertinents sont omis.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-125">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="fa9ff-126">La séquence de restauration contient uniquement deux instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa9ff-126">The restore sequence contains only two [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="fa9ff-127">La première instruction restaure un fichier secondaire, le fichier `A`, qui est restauré avec WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="fa9ff-127">The first statement restores a secondary file, file `A`, which is restored using WITH NORECOVERY.</span></span> <span data-ttu-id="fa9ff-128">La seconde opération restaure deux autres fichiers, `B` et `C` , qui sont restaurés avec WITH RECOVERY depuis une unité de sauvegarde différente :</span><span class="sxs-lookup"><span data-stu-id="fa9ff-128">The second operation restores two other files, `B` and `C` which are restored using WITH RECOVERY from a different backup device:</span></span>  
  
1.  <span data-ttu-id="fa9ff-129">RESTORE DATABASE *base_de_données* FILE **=** _nom_fichier_A_</span><span class="sxs-lookup"><span data-stu-id="fa9ff-129">RESTORE DATABASE *database* FILE **=**_name_of_file_A_</span></span>  
  
     <span data-ttu-id="fa9ff-130">FROM *sauvegarde_de_fichier_A*</span><span class="sxs-lookup"><span data-stu-id="fa9ff-130">FROM *file_backup_of_file_A*</span></span>  
  
     <span data-ttu-id="fa9ff-131">WITH NORECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="fa9ff-131">WITH NORECOVERY **;**</span></span>  
  
2.  <span data-ttu-id="fa9ff-132">RESTORE DATABASE *base_de_données* FILE **=** _nom_fichier_B_ **,** _nom_fichier_C_</span><span class="sxs-lookup"><span data-stu-id="fa9ff-132">RESTORE DATABASE *database* FILE **=**_name_of_file_B_**,**_name_of_file_C_</span></span>  
  
     <span data-ttu-id="fa9ff-133">FROM *sauvegarde_des_fichiers_B_et_C*</span><span class="sxs-lookup"><span data-stu-id="fa9ff-133">FROM *file_backup_of_files_B_and_C*</span></span>  
  
     <span data-ttu-id="fa9ff-134">WITH RECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="fa9ff-134">WITH RECOVERY **;**</span></span>  
  
### <a name="examples"></a><span data-ttu-id="fa9ff-135">Exemples</span><span class="sxs-lookup"><span data-stu-id="fa9ff-135">Examples</span></span>  
  
-   [<span data-ttu-id="fa9ff-136">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="fa9ff-136">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="fa9ff-137">Exemple : restauration hors ligne du groupe de fichiers primaire et d’un autre groupe de fichiers &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="fa9ff-137">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fa9ff-138">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="fa9ff-138">Related Tasks</span></span>  
 <span data-ttu-id="fa9ff-139">**Pour restaurer des fichiers et des groupes de fichiers**</span><span class="sxs-lookup"><span data-stu-id="fa9ff-139">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="fa9ff-140">Restaurer des fichiers et groupes de fichiers en remplaçant des fichiers existants &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa9ff-140">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="fa9ff-141">Restaurer des fichiers et des groupes de fichiers &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa9ff-141">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="fa9ff-142">Restaurer des fichiers et des groupes de fichiers &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa9ff-142">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="fa9ff-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="fa9ff-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="fa9ff-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa9ff-144">See Also</span></span>  
 <span data-ttu-id="fa9ff-145">[Sauvegarde et restauration : interopérabilité et coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fa9ff-145">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="fa9ff-146">[Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fa9ff-146">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="fa9ff-147">[Sauvegardes de fichiers complètes &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fa9ff-147">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="fa9ff-148">[Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fa9ff-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="fa9ff-149">[Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fa9ff-149">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="fa9ff-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa9ff-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="fa9ff-151">[Restaurations complètes de bases de données &#40;mode de récupération simple&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="fa9ff-151">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="fa9ff-152">Restaurations fragmentaires &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa9ff-152">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
