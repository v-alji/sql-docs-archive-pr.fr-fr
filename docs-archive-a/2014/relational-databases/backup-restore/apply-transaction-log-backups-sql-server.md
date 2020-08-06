---
title: Appliquer les sauvegardes du journal de transactions (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], log backups
- transaction log backups [SQL Server], applying backups
- online restores [SQL Server], log backups
- transaction log backups [SQL Server], quantity needed for restore sequence
- backups [SQL Server], log backups
ms.assetid: 9b12be51-5469-46f9-8e86-e938e10aa3a1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54c91106f8ca6f15539b4103220860143882c3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604591"
---
# <a name="apply-transaction-log-backups-sql-server"></a><span data-ttu-id="43a47-102">Appliquer les sauvegardes du journal de transactions (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="43a47-102">Apply Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="43a47-103">Cette rubrique concerne uniquement le mode de récupération complète ou le mode de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="43a47-103">The topic is relevant only for the full recovery model or bulk-logged recovery model.</span></span>  
  
 <span data-ttu-id="43a47-104">Cette rubrique décrit l'application de sauvegardes du journal des transaction dans le cadre de la restauration d'une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43a47-104">This topic describes applying transaction log backups as part of restoring a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="43a47-105">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="43a47-105">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="43a47-106">Conditions requises pour la restauration des sauvegardes du journal des transactions</span><span class="sxs-lookup"><span data-stu-id="43a47-106">Requirements for Restoring Transaction Log Backups</span></span>](#Requirements)  
  
-   [<span data-ttu-id="43a47-107">Récupération et journaux des transactions</span><span class="sxs-lookup"><span data-stu-id="43a47-107">Recovery and Transaction Logs</span></span>](#RecoveryAndTlogs)  
  
-   [<span data-ttu-id="43a47-108">Utilisation des sauvegardes du journal des transactions pour effectuer une restauration jusqu'au point d'échec</span><span class="sxs-lookup"><span data-stu-id="43a47-108">Using Log Backups to Restore to the Point of Failure</span></span>](#PITrestore)  
  
-   [<span data-ttu-id="43a47-109">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="43a47-109">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="requirements-for-restoring-transaction-log-backups"></a><a name="Requirements"></a><span data-ttu-id="43a47-110">Conditions requises pour la restauration des sauvegardes du journal des transactions</span><span class="sxs-lookup"><span data-stu-id="43a47-110">Requirements for Restoring Transaction Log Backups</span></span>  
 <span data-ttu-id="43a47-111">Pour appliquer une sauvegarde du journal des transactions, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="43a47-111">To apply a transaction log backup, the following requirements must be met:</span></span>  
  
-   <span data-ttu-id="43a47-112">**Sauvegardes de journal en nombre suffisant pour une séquence de restauration :** Vous devez disposer de suffisamment d'enregistrements de journal sauvegardés pour exécuter une séquence de restauration.</span><span class="sxs-lookup"><span data-stu-id="43a47-112">**Enough Log Backups for a Restore Sequence :** You must have enough log records backed up to complete a restore sequence.</span></span> <span data-ttu-id="43a47-113">Les sauvegardes de journal nécessaires, notamment la [sauvegarde de la fin du journal](tail-log-backups-sql-server.md) le cas échéant, doivent être disponibles avant le début de la séquence de restauration.</span><span class="sxs-lookup"><span data-stu-id="43a47-113">The necessary log backups, including the [tail-log backup](tail-log-backups-sql-server.md) where required, must be available before the start of the restore sequence.</span></span>  
  
-   <span data-ttu-id="43a47-114">**Ordre de restauration correct :**  La sauvegarde différentielle ou la sauvegarde complète de base de données effectuée juste avant doit d'abord être restaurée.</span><span class="sxs-lookup"><span data-stu-id="43a47-114">**Correct restore order:**  The immediately previous full database backup or differential database backup must be restored first.</span></span> <span data-ttu-id="43a47-115">Puis, tous les journaux de transactions créés après cette sauvegarde complète ou différentielle de base de données doivent être restaurés dans l'ordre chronologique.</span><span class="sxs-lookup"><span data-stu-id="43a47-115">Then, all transaction logs that are created after that full or differential database backup must be restored in chronological order.</span></span> <span data-ttu-id="43a47-116">Si une sauvegarde du journal des transactions dans cette séquence de journaux de transactions consécutifs est perdue ou endommagée, vous ne pouvez restaurer que les journaux des transactions antérieurs au journal des transactions manquant.</span><span class="sxs-lookup"><span data-stu-id="43a47-116">If a transaction log backup in this log chain is lost or damaged, you can restore only transaction logs before the missing transaction log.</span></span>  
  
-   <span data-ttu-id="43a47-117">**Base de données pas encore récupérée :**  La base de données ne peut pas être récupérée tant que le dernier journal des transactions n'a pas été appliqué.</span><span class="sxs-lookup"><span data-stu-id="43a47-117">**Database not yet recovered:**  The database cannot be recovered until after the final transaction log has been applied.</span></span> <span data-ttu-id="43a47-118">Si vous récupérez la base de données après avoir restauré l'une des sauvegardes du journal des transactions intermédiaires, c'est-à-dire avant la fin de la séquence de journaux de transactions consécutifs, vous ne pouvez pas restaurer la base de données au-delà de ce point sans redémarrer toute la séquence de restauration, en commençant par la sauvegarde complète de base de données.</span><span class="sxs-lookup"><span data-stu-id="43a47-118">If you recover the database after restoring one of the intermediate transaction log backups, that before the end of the log chain, you cannot restore the database past that point without restarting the complete restore sequence, starting with the full database backup.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="43a47-119">Il est recommandé de restaurer toutes les sauvegardes des journaux (RESTORE LOG *nom_base_de_données* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="43a47-119">A best practice is to restore all the log backups (RESTORE LOG *database_name* WITH NORECOVERY).</span></span> <span data-ttu-id="43a47-120">Ensuite, après la restauration de la dernière sauvegarde du journal, récupérez la base de données dans une opération séparée (RESTORE DATABASE *nom_base_de_données* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="43a47-120">Then, after restoring the last log backup, recover the database in a separate operation (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span>  
  
##  <a name="recovery-and-transaction-logs"></a><a name="RecoveryAndTlogs"></a><span data-ttu-id="43a47-121">Récupération et journaux des transactions</span><span class="sxs-lookup"><span data-stu-id="43a47-121">Recovery and Transaction Logs</span></span>  
 <span data-ttu-id="43a47-122">Lorsque vous terminez l'opération de restauration et récupérez la base de données, la récupération annule toutes les transactions incomplètes.</span><span class="sxs-lookup"><span data-stu-id="43a47-122">When you finish the restore operation and recover the database, recovery rolls back all incomplete transactions.</span></span> <span data-ttu-id="43a47-123">Cette phase se nomme *phase de restauration*.</span><span class="sxs-lookup"><span data-stu-id="43a47-123">This is known as the *undo phase*.</span></span> <span data-ttu-id="43a47-124">Cette opération est nécessaire pour restaurer l'intégrité de la base de données.</span><span class="sxs-lookup"><span data-stu-id="43a47-124">Rolling back is required to restore the integrity of the database.</span></span> <span data-ttu-id="43a47-125">Après la restauration, la base de données passe en ligne, et aucune autre sauvegarde du journal des transactions ne peut être appliquée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="43a47-125">After rollback, the database goes online, and no more transaction log backups can be applied to the database.</span></span>  
  
 <span data-ttu-id="43a47-126">Par exemple, une série de sauvegardes du journal des transactions contient une transaction longue.</span><span class="sxs-lookup"><span data-stu-id="43a47-126">For example, a series of transaction log backups contain a long-running transaction.</span></span> <span data-ttu-id="43a47-127">Le démarrage de la transaction est enregistré dans la première sauvegarde du journal des transactions, mais la fin de la transaction est enregistrée dans la seconde sauvegarde du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="43a47-127">The start of the transaction is recorded in the first transaction log backup, but the end of the transaction is recorded in the second transaction log backup.</span></span> <span data-ttu-id="43a47-128">Il n’y a pas d'enregistrement d’une opération de validation ou de restauration dans la première sauvegarde du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="43a47-128">There is no record of a commit or rollback operation in the first transaction log backup.</span></span> <span data-ttu-id="43a47-129">Si une opération de récupération est exécutée lors de l'application de la première sauvegarde du journal des transactions, la longue transaction est traitée comme incomplète, et les modifications de données enregistrées dans la première sauvegarde du journal des transactions pour la transaction sont restaurées.</span><span class="sxs-lookup"><span data-stu-id="43a47-129">If a recovery operation runs when the first transaction log backup is applied, the long-running transaction is treated as incomplete, and data modifications recorded in the first transaction log backup for the transaction are rolled back.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="43a47-130">ne permet pas l'application de la deuxième sauvegarde du journal des transactions après ce stade.</span><span class="sxs-lookup"><span data-stu-id="43a47-130">does not allow for the second transaction log backup to be applied after this point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43a47-131">Dans certains cas, vous pouvez ajouter un fichier de façon explicite pendant la restauration du journal.</span><span class="sxs-lookup"><span data-stu-id="43a47-131">In some circumstances, you can explicitly add a file during log restore.</span></span>  
  
##  <a name="using-log-backups-to-restore-to-the-point-of-failure"></a><a name="PITrestore"></a><span data-ttu-id="43a47-132">Utilisation des sauvegardes de journaux pour restaurer jusqu’au point de défaillance</span><span class="sxs-lookup"><span data-stu-id="43a47-132">Using Log Backups to Restore to the Point of Failure</span></span>  
 <span data-ttu-id="43a47-133">Supposons la séquence d'événements suivante.</span><span class="sxs-lookup"><span data-stu-id="43a47-133">Assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="43a47-134">Temps</span><span class="sxs-lookup"><span data-stu-id="43a47-134">Time</span></span>|<span data-ttu-id="43a47-135">Événement</span><span class="sxs-lookup"><span data-stu-id="43a47-135">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="43a47-136">8h00</span><span class="sxs-lookup"><span data-stu-id="43a47-136">8:00 A.M.</span></span>|<span data-ttu-id="43a47-137">Sauvegardez la base de données pour créer une sauvegarde complète de base de données.</span><span class="sxs-lookup"><span data-stu-id="43a47-137">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="43a47-138">Midi</span><span class="sxs-lookup"><span data-stu-id="43a47-138">Noon</span></span>|<span data-ttu-id="43a47-139">Sauvegarde du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="43a47-139">Back up transaction log.</span></span>|  
|<span data-ttu-id="43a47-140">16h00</span><span class="sxs-lookup"><span data-stu-id="43a47-140">4:00 P.M.</span></span>|<span data-ttu-id="43a47-141">Sauvegarde du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="43a47-141">Back up transaction log.</span></span>|  
|<span data-ttu-id="43a47-142">18h00</span><span class="sxs-lookup"><span data-stu-id="43a47-142">6:00 P.M.</span></span>|<span data-ttu-id="43a47-143">Sauvegardez la base de données pour créer une sauvegarde complète de base de données.</span><span class="sxs-lookup"><span data-stu-id="43a47-143">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="43a47-144">20h00</span><span class="sxs-lookup"><span data-stu-id="43a47-144">8:00 P.M.</span></span>|<span data-ttu-id="43a47-145">Sauvegarde du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="43a47-145">Back up transaction log.</span></span>|  
|<span data-ttu-id="43a47-146">21h45</span><span class="sxs-lookup"><span data-stu-id="43a47-146">9:45 P.M.</span></span>|<span data-ttu-id="43a47-147">Une défaillance se produit.</span><span class="sxs-lookup"><span data-stu-id="43a47-147">Failure occurs.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="43a47-148">Pour une explication de cet exemple de cette séquence de sauvegardes, consultez [Sauvegardes des journaux de transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="43a47-148">For an explanation of this example sequence of backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="43a47-149">Pour restaurer la base de données à son état à 21:45</span><span class="sxs-lookup"><span data-stu-id="43a47-149">To restore the database to its state at 9:45 P.M.</span></span> <span data-ttu-id="43a47-150">(point d'échec), les autres procédures suivantes peuvent être utilisées :</span><span class="sxs-lookup"><span data-stu-id="43a47-150">(the point of failure), either of the following alternative procedures can be used:</span></span>  
  
 <span data-ttu-id="43a47-151">**Solution 1 : restaurer la base de données en utilisant la sauvegarde complète de base de données la plus récente**</span><span class="sxs-lookup"><span data-stu-id="43a47-151">**Alternative 1: Restore the database by using the most recent full database backup**</span></span>  
  
1.  <span data-ttu-id="43a47-152">Créez une sauvegarde de la fin du journal du journal des transactions actuellement actif comme point d'échec.</span><span class="sxs-lookup"><span data-stu-id="43a47-152">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="43a47-153">Ne restaurez pas la sauvegarde complète</span><span class="sxs-lookup"><span data-stu-id="43a47-153">Do not restore the 8:00 A.M.</span></span> <span data-ttu-id="43a47-154">de base de données de 18h00.</span><span class="sxs-lookup"><span data-stu-id="43a47-154">full database backup.</span></span> <span data-ttu-id="43a47-155">Restaurez plutôt la sauvegarde complète de base de données la plus récente</span><span class="sxs-lookup"><span data-stu-id="43a47-155">Instead, restore the more recent 6:00 P.M.</span></span> <span data-ttu-id="43a47-156">de 18h00, puis appliquez la sauvegarde du journal de 20h00</span><span class="sxs-lookup"><span data-stu-id="43a47-156">full database backup, and then apply the 8:00 P.M.</span></span> <span data-ttu-id="43a47-157">et la sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="43a47-157">log backup and the tail-log backup.</span></span>  
  
 <span data-ttu-id="43a47-158">**Solution 2 : restaurer la base de données en utilisant une sauvegarde complète de base de données antérieure**</span><span class="sxs-lookup"><span data-stu-id="43a47-158">**Alternative 2: Restore the database by using an earlier full database backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43a47-159">Cette autre solution est utile si un problème vous empêche d'utiliser la sauvegarde complète</span><span class="sxs-lookup"><span data-stu-id="43a47-159">This alternative process is useful if a problem prevents you from using the 6:00 P.M.</span></span> <span data-ttu-id="43a47-160">de base de données de 18h00.</span><span class="sxs-lookup"><span data-stu-id="43a47-160">full database backup.</span></span> <span data-ttu-id="43a47-161">Ce processus prend plus de temps que la restauration de la sauvegarde complète</span><span class="sxs-lookup"><span data-stu-id="43a47-161">This process takes longer than restoring from the 6:00 P.M.</span></span> <span data-ttu-id="43a47-162">de base de données de 18h00.</span><span class="sxs-lookup"><span data-stu-id="43a47-162">full database backup.</span></span>  
  
1.  <span data-ttu-id="43a47-163">Créez une sauvegarde de la fin du journal du journal des transactions actuellement actif comme point d'échec.</span><span class="sxs-lookup"><span data-stu-id="43a47-163">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="43a47-164">Restaurez la sauvegarde complète</span><span class="sxs-lookup"><span data-stu-id="43a47-164">Restore the 8:00 A.M.</span></span> <span data-ttu-id="43a47-165">de base de données de 8h00, puis restaurez dans l'ordre les quatre sauvegardes du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="43a47-165">full database backup, and then restore all four transaction log backups in sequence.</span></span> <span data-ttu-id="43a47-166">Cette procédure restaure par progression toutes les transactions achevées jusqu'à 21h45.</span><span class="sxs-lookup"><span data-stu-id="43a47-166">This rolls forward all completed transactions up to 9:45 P.M.</span></span>  
  
     <span data-ttu-id="43a47-167">Cette solution souligne la sécurité redondante offerte par le maintien d'une séquence de sauvegardes de journaux de transactions dans une série de sauvegardes complètes de base de données.</span><span class="sxs-lookup"><span data-stu-id="43a47-167">This alternative points out the redundant security offered by maintaining a chain of transaction log backups across a series of full database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43a47-168">Dans certains cas, vous pouvez utiliser des journaux de transactions pour restaurer une base de données à un point spécifique dans le temps.</span><span class="sxs-lookup"><span data-stu-id="43a47-168">In some cases, you can also use transaction logs to restore a database to a specific point in time.</span></span> <span data-ttu-id="43a47-169">Pour plus d’informations, consultez [Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="43a47-169">For more information, [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="43a47-170">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="43a47-170">Related Tasks</span></span>  
 <span data-ttu-id="43a47-171">**Pour appliquer une sauvegarde du journal des transactions**</span><span class="sxs-lookup"><span data-stu-id="43a47-171">**To apply a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="43a47-172">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43a47-172">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="43a47-173">**Pour effectuer une restauration au point de récupération**</span><span class="sxs-lookup"><span data-stu-id="43a47-173">**To restore to your recovery point**</span></span>  
  
-   [<span data-ttu-id="43a47-174">Restaurer une base de données jusqu’au point d’échec en mode de récupération complète &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43a47-174">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="43a47-175">Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="43a47-175">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   <span data-ttu-id="43a47-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="43a47-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
-   [<span data-ttu-id="43a47-177">Récupération de bases de données associées contenant une transaction marquée</span><span class="sxs-lookup"><span data-stu-id="43a47-177">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="43a47-178">Récupérer un numéro séquentiel dans le journal &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43a47-178">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
 <span data-ttu-id="43a47-179">**Pour récupérer une base de données après la restauration de sauvegardes à l'aide de WITH NORECOVERY**</span><span class="sxs-lookup"><span data-stu-id="43a47-179">**To recover a database after restoring backups using WITH NORECOVERY**</span></span>  
  
-   [<span data-ttu-id="43a47-180">Récupérer une base de données sans restaurer les données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43a47-180">Recover a Database Without Restoring Data &#40;Transact-SQL&#41;</span></span>](recover-a-database-without-restoring-data-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="43a47-181">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43a47-181">See Also</span></span>  
 [<span data-ttu-id="43a47-182">Journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43a47-182">The Transaction Log &#40;SQL Server&#41;</span></span>](../logs/the-transaction-log-sql-server.md)  
  
  
