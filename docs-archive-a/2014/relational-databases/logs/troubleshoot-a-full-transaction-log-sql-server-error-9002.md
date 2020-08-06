---
title: Résoudre les problèmes liés à un journal des transactions saturé (erreur SQL Server 9002) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], full
- troubleshooting [SQL Server], full transaction log
- 9002 (Database Engine error)
- transaction logs [SQL Server], truncation
- backing up transaction logs [SQL Server], full logs
- transaction logs [SQL Server], full log
- full transaction logs [SQL Server]
ms.assetid: 0f23aa84-475d-40df-bed3-c923f8c1b520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d03e259bd0aff8fce02558dbe08efb56748493c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600885"
---
# <a name="troubleshoot-a-full-transaction-log-sql-server-error-9002"></a><span data-ttu-id="90d60-102">Résoudre les problèmes liés à un journal des transactions saturé (erreur SQL Server 9002)</span><span class="sxs-lookup"><span data-stu-id="90d60-102">Troubleshoot a Full Transaction Log (SQL Server Error 9002)</span></span>
  <span data-ttu-id="90d60-103">Cette rubrique décrit les réactions possibles et émet quelques suggestions qui vous aideront à éviter cette situation dans le futur.</span><span class="sxs-lookup"><span data-stu-id="90d60-103">This topic discusses possible responses to a full transaction log and suggests how to avoid it in the future.</span></span> <span data-ttu-id="90d60-104">Quand le journal des transactions est saturé, le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] émet une erreur 9002.</span><span class="sxs-lookup"><span data-stu-id="90d60-104">When the transaction log becomes full, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] issues a 9002 error.</span></span> <span data-ttu-id="90d60-105">Le journal peut être renseigné lorsque la base de données est en ligne ou en cours de récupération.</span><span class="sxs-lookup"><span data-stu-id="90d60-105">The log can fill when the database is online or in recovery.</span></span> <span data-ttu-id="90d60-106">Si le journal se remplit tandis que la base de données est en ligne, la base de données reste en ligne mais elle peut uniquement être lue, et pas être mise à jour.</span><span class="sxs-lookup"><span data-stu-id="90d60-106">If the log fills while the database is online, the database remains online but can only be read, not updated.</span></span> <span data-ttu-id="90d60-107">Si le journal se remplit en cours de récupération, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] marque la base de données comme RESOURCE PENDING.</span><span class="sxs-lookup"><span data-stu-id="90d60-107">If the log fills during recovery, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] marks the database as RESOURCE PENDING.</span></span> <span data-ttu-id="90d60-108">Dans les deux cas, une intervention de l'utilisateur est nécessaire pour libérer de l'espace disque.</span><span class="sxs-lookup"><span data-stu-id="90d60-108">In either case, user action is required to make log space available.</span></span>  
  
## <a name="responding-to-a-full-transaction-log"></a><span data-ttu-id="90d60-109">Réagir à un journal des transactions complet</span><span class="sxs-lookup"><span data-stu-id="90d60-109">Responding to a Full Transaction Log</span></span>  
 <span data-ttu-id="90d60-110">La réponse adéquate à un journal des transactions saturé dépend en partie de la ou des conditions qui ont motivé le remplissage du journal.</span><span class="sxs-lookup"><span data-stu-id="90d60-110">The appropriate response to a full transaction log depends partly on what condition or conditions caused the log to fill.</span></span> <span data-ttu-id="90d60-111">Pour découvrir les raisons qui empêchent de tronquer le journal dans une situation donnée, utilisez les colonnes **log_reuse_wait** et **log_reuse_wait_desc** de l’affichage catalogue **sys.database**.</span><span class="sxs-lookup"><span data-stu-id="90d60-111">To discover what is preventing log truncation in a given case, use the **log_reuse_wait** and **log_reuse_wait_desc** columns of the **sys.database** catalog view.</span></span> <span data-ttu-id="90d60-112">Pour plus d’informations, consultez [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="90d60-112">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span> <span data-ttu-id="90d60-113">Pour obtenir une description des facteurs susceptibles de retarder la troncation du journal, consultez [Journal des transactions &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="90d60-113">For descriptions of factors that can delay log truncation, see [The Transaction Log &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90d60-114">Si la base de données était en mode de récupération quand l’erreur 9002 s’est produite, récupérez la base de données à l’aide de l’instruction ALTER DATABASE *nom_base_de_données* SET ONLINE après avoir résolu le problème.</span><span class="sxs-lookup"><span data-stu-id="90d60-114">If the database was in recovery when the 9002 error occurred, after resolving the problem, recover the database by using ALTER DATABASE *database_name* SET ONLINE.</span></span>  
  
 <span data-ttu-id="90d60-115">D'autres solutions possibles en cas de saturation du journal des transactions sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="90d60-115">Alternatives for responding to a full transaction log include:</span></span>  
  
-   <span data-ttu-id="90d60-116">Sauvegarde du journal.</span><span class="sxs-lookup"><span data-stu-id="90d60-116">Backing up the log.</span></span>  
  
-   <span data-ttu-id="90d60-117">Libération de l'espace disque pour que le journal puisse croître automatiquement.</span><span class="sxs-lookup"><span data-stu-id="90d60-117">Freeing disk space so that the log can automatically grow.</span></span>  
  
-   <span data-ttu-id="90d60-118">Déplacement du fichier journal vers une unité dotée d'un espace disque suffisant.</span><span class="sxs-lookup"><span data-stu-id="90d60-118">Moving the log file to a disk drive with sufficient space.</span></span>  
  
-   <span data-ttu-id="90d60-119">Augmentation de la taille du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="90d60-119">Increasing the size of a log file.</span></span>  
  
-   <span data-ttu-id="90d60-120">Ajout d'un fichier journal sur un autre disque.</span><span class="sxs-lookup"><span data-stu-id="90d60-120">Adding a log file on a different disk.</span></span>  
  
-   <span data-ttu-id="90d60-121">Achèvement ou suppression d'une transaction longue.</span><span class="sxs-lookup"><span data-stu-id="90d60-121">Completing or killing a long-running transaction.</span></span>  
  
 <span data-ttu-id="90d60-122">Ces solutions sont abordées dans les sections qui suivent.</span><span class="sxs-lookup"><span data-stu-id="90d60-122">These alternatives are discussed in the following sections.</span></span> <span data-ttu-id="90d60-123">Optez pour une solution adaptée à votre situation.</span><span class="sxs-lookup"><span data-stu-id="90d60-123">Choose a response that fits your situation best.</span></span>  
  
### <a name="backing-up-the-log"></a><span data-ttu-id="90d60-124">Sauvegarde du journal</span><span class="sxs-lookup"><span data-stu-id="90d60-124">Backing up the Log</span></span>  
 <span data-ttu-id="90d60-125">Si vous travaillez en mode de restauration complète ou en mode de récupération utilisant les journaux de transactions et si vous n'avez pas sauvegardé récemment le journal des transactions, la création d'une sauvegarde est ce qui empêche la troncation du journal.</span><span class="sxs-lookup"><span data-stu-id="90d60-125">Under the full recovery model or bulk-logged recovery model, if the transaction log has not been backed up recently, backup might be what is preventing log truncation.</span></span> <span data-ttu-id="90d60-126">Si le journal n’a jamais été sauvegardé, vous devez créer deux sauvegardes du journal pour autoriser le [!INCLUDE[ssDE](../../includes/ssde-md.md)] à le tronquer à l’endroit exact de la dernière sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="90d60-126">If the log has never been backed up, you must create two log backups to permit the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to truncate the log to the point of the last backup.</span></span> <span data-ttu-id="90d60-127">Le fait de tronquer le journal permet de libérer de l'espace pour les nouveaux enregistrements de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="90d60-127">Truncating the log frees space for new log records.</span></span> <span data-ttu-id="90d60-128">Pour empêcher le journal de se remplir à nouveau, effectuez les sauvegardes régulièrement.</span><span class="sxs-lookup"><span data-stu-id="90d60-128">To keep the log from filling up again, take log backups frequently.</span></span>  
  
 <span data-ttu-id="90d60-129">**Pour créer une sauvegarde du journal des transactions**</span><span class="sxs-lookup"><span data-stu-id="90d60-129">**To create a transaction log backup**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90d60-130">Si la base de données est endommagée, consultez [Sauvegardes de la fin du journal &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="90d60-130">If the database is damaged, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="90d60-131">Sauvegarder un journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90d60-131">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="90d60-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="90d60-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
### <a name="freeing-disk-space"></a><span data-ttu-id="90d60-133">Libération d’espace disque</span><span class="sxs-lookup"><span data-stu-id="90d60-133">Freeing Disk Space</span></span>  
 <span data-ttu-id="90d60-134">Vous pouvez libérer de l'espace sur le disque où est stocké le fichier journal des transactions de la base de données en supprimant ou en déplaçant d'autres fichiers.</span><span class="sxs-lookup"><span data-stu-id="90d60-134">You might be able to free disk space on the disk drive that contains the transaction log file for the database by deleting or moving other files.</span></span> <span data-ttu-id="90d60-135">Ceci permet au système de récupération d'augmenter automatiquement la taille du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="90d60-135">The freed disk space allows the recovery system to enlarge the log file automatically.</span></span>  
  
### <a name="moving-the-log-file-to-a-different-disk"></a><span data-ttu-id="90d60-136">Déplacement du fichier journal vers un autre disque</span><span class="sxs-lookup"><span data-stu-id="90d60-136">Moving the Log File to a Different Disk</span></span>  
 <span data-ttu-id="90d60-137">Si vous ne pouvez pas libérer suffisamment d'espace disque sur le lecteur où le fichier journal se trouve actuellement, essayez de déplacer ce fichier sur une autre unité disposant d'espace suffisant.</span><span class="sxs-lookup"><span data-stu-id="90d60-137">If you cannot free enough disk space on the drive that currently contains the log file, consider moving the file to another drive with sufficient space.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90d60-138">Les fichiers journaux ne doivent jamais être placés sur des systèmes de fichiers compressés.</span><span class="sxs-lookup"><span data-stu-id="90d60-138">Log files should never be placed on compressed file systems.</span></span>  
  
 <span data-ttu-id="90d60-139">**Pour déplacer un fichier journal**</span><span class="sxs-lookup"><span data-stu-id="90d60-139">**To move a log file**</span></span>  
  
-   [<span data-ttu-id="90d60-140">Déplacer des fichiers de bases de données</span><span class="sxs-lookup"><span data-stu-id="90d60-140">Move Database Files</span></span>](../databases/move-database-files.md)  
  
### <a name="increasing-the-size-of-a-log-file"></a><span data-ttu-id="90d60-141">Augmentation de la taille d'un fichier journal</span><span class="sxs-lookup"><span data-stu-id="90d60-141">Increasing the Size of a Log File</span></span>  
 <span data-ttu-id="90d60-142">Si le disque du journal dispose d'espace libre, vous pouvez augmenter la taille du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="90d60-142">If space is available on the log disk, you can increase the size of the log file.</span></span> <span data-ttu-id="90d60-143">La taille maximale pour les fichiers journaux est de deux téraoctets (To) par fichier journal.</span><span class="sxs-lookup"><span data-stu-id="90d60-143">The maximum size for log files is two terabytes (TB) per log file.</span></span>  
  
 <span data-ttu-id="90d60-144">**Pour augmenter la taille du fichier**</span><span class="sxs-lookup"><span data-stu-id="90d60-144">**To increase the file size**</span></span>  
  
 <span data-ttu-id="90d60-145">Si la fonctionnalité de croissance automatique est désactivée, que la base de données est en ligne et que l'espace disque disponible est suffisant, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="90d60-145">If autogrow is disabled, the database is online, and sufficient space is available on the disk, either:</span></span>  
  
-   <span data-ttu-id="90d60-146">Augmentez manuellement la taille du fichier pour générer un seul incrément de croissance.</span><span class="sxs-lookup"><span data-stu-id="90d60-146">Manually increase the file size to produce a single growth increment.</span></span>  
  
-   <span data-ttu-id="90d60-147">Activez la croissance automatique à l'aide de l'instruction ALTER DATABASE pour définir un incrément de croissance différent de zéro pour l'option FILEGROWTH.</span><span class="sxs-lookup"><span data-stu-id="90d60-147">Turn on autogrow by using the ALTER DATABASE statement to set a non-zero growth increment for the FILEGROWTH option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90d60-148">Dans les deux cas, si la limite de taille actuelle est atteinte, augmentez la valeur MAXSIZE.</span><span class="sxs-lookup"><span data-stu-id="90d60-148">In either case, if the current size limit has been reached, increase the MAXSIZE value.</span></span>  
  
### <a name="adding-a-log-file-on-a-different-disk"></a><span data-ttu-id="90d60-149">Ajout d'un fichier journal sur un autre disque</span><span class="sxs-lookup"><span data-stu-id="90d60-149">Adding a Log File on a Different Disk</span></span>  
 <span data-ttu-id="90d60-150">Ajoutez un nouveau fichier journal à la base de données d'un autre disque doté d'un espace suffisant à l'aide de l'instruction ALTER DATABASE <nom_base_de_données> ADD LOG FILE.</span><span class="sxs-lookup"><span data-stu-id="90d60-150">Add a new log file to the database on a different disk that has sufficient space by using ALTER DATABASE <database_name> ADD LOG FILE.</span></span>  
  
 <span data-ttu-id="90d60-151">**Pour ajouter un fichier journal**</span><span class="sxs-lookup"><span data-stu-id="90d60-151">**To add a log file**</span></span>  
  
-   [<span data-ttu-id="90d60-152">Ajouter des fichiers de données ou journaux à une base de données</span><span class="sxs-lookup"><span data-stu-id="90d60-152">Add Data or Log Files to a Database</span></span>](../databases/add-data-or-log-files-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="90d60-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90d60-153">See Also</span></span>  
 <span data-ttu-id="90d60-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="90d60-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="90d60-155">[Gérer la taille du fichier journal des transactions](manage-the-size-of-the-transaction-log-file.md) </span><span class="sxs-lookup"><span data-stu-id="90d60-155">[Manage the Size of the Transaction Log File](manage-the-size-of-the-transaction-log-file.md) </span></span>  
 <span data-ttu-id="90d60-156">[Sauvegardes des journaux de transactions &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90d60-156">[Transaction Log Backups &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="90d60-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="90d60-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-log-file-recover-suspect-db-transact-sql)  
  
  
