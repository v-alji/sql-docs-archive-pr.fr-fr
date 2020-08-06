---
title: Rétablir une base de données dans l’état d’un instantané de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], reverting to
- reverting databases
ms.assetid: 8f74dd31-c9ca-4537-8760-0c7648f0787d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1c78da3d7c559309c0563760e7062f01cf784648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604542"
---
# <a name="revert-a-database-to-a-database-snapshot"></a><span data-ttu-id="75dcf-102">Rétablir une base de données dans l'état d'un instantané de base de données</span><span class="sxs-lookup"><span data-stu-id="75dcf-102">Revert a Database to a Database Snapshot</span></span>
  <span data-ttu-id="75dcf-103">Si les données d'une base de données en ligne sont endommagées, dans certains cas, rétablir la base de données dans l'état d'un instantané précédant le problème peut être une bonne solution plutôt que de restaurer la base de données à partir d'une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="75dcf-103">If data in an online database becomes damaged, in some cases, reverting the database to a database snapshot that predates the damage might be an appropriate alternative to restoring the database from a backup.</span></span> <span data-ttu-id="75dcf-104">Par exemple, rétablir une base de données peut être utile pour annuler une grave erreur de l'utilisateur, telle que la suppression d'une table.</span><span class="sxs-lookup"><span data-stu-id="75dcf-104">For example, reverting a database might be useful for reverse a recent serious user error, such as a dropped table.</span></span> <span data-ttu-id="75dcf-105">Toutefois, toutes les modifications apportées depuis la création de l'instantané sont perdues.</span><span class="sxs-lookup"><span data-stu-id="75dcf-105">However, all changes made after the snapshot was created are lost.</span></span>  
  
-   <span data-ttu-id="75dcf-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="75dcf-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="75dcf-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="75dcf-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="75dcf-108">Composants requis</span><span class="sxs-lookup"><span data-stu-id="75dcf-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="75dcf-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="75dcf-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="75dcf-110">**Pour rétablir une base de données dans l’état d’un instantané de base de données, avec :**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="75dcf-110">**To Revert a Database to a Database Snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="75dcf-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="75dcf-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="75dcf-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="75dcf-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="75dcf-113">Le rétablissement n'est pas pris en charge dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="75dcf-113">Reverting is unsupported under the following conditions:</span></span>  
  
-   <span data-ttu-id="75dcf-114">La base de données doit actuellement posséder un seul instantané de base de données, que vous prévoyez de rétablir.</span><span class="sxs-lookup"><span data-stu-id="75dcf-114">The database must currently have only one database snapshot, to which you plan to revert.</span></span>  
  
-   <span data-ttu-id="75dcf-115">Des groupes de fichiers compressés ou en lecture seule existent dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-115">Any read-only or compressed filegroups exist in the database.</span></span>  
  
-   <span data-ttu-id="75dcf-116">Des fichiers sont maintenant hors connexion alors qu'ils étaient en ligne lors de la création de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="75dcf-116">Any files are now offline but were online when the snapshot was created.</span></span>  
  
 <span data-ttu-id="75dcf-117">Avant de rétablir une base de données, tenez compte des limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="75dcf-117">Before reverting a database, consider the following limitations:</span></span>  
  
-   <span data-ttu-id="75dcf-118">Le rétablissement n'est pas destiné à la récupération des supports.</span><span class="sxs-lookup"><span data-stu-id="75dcf-118">Reverting is not intended for media recovery.</span></span> <span data-ttu-id="75dcf-119">.</span><span class="sxs-lookup"><span data-stu-id="75dcf-119">.</span></span> <span data-ttu-id="75dcf-120">L'instantané de base de données est une copie incomplète des fichiers de base de données, donc si la base de données ou l'instantané de base de données est endommagé, le rétablissement à partir d'un instantané sera probablement impossible.</span><span class="sxs-lookup"><span data-stu-id="75dcf-120">A database snapshot is an incomplete copy of the database files, so if either the database or the database snapshot is corrupted, reverting from a snapshot is likely to be impossible.</span></span> <span data-ttu-id="75dcf-121">En outre, même lorsque le rétablissement est possible, il est peu probable qu'il permette de corriger le problème en cas de corruption.</span><span class="sxs-lookup"><span data-stu-id="75dcf-121">Furthermore, even when it is possible, reverting in the event of corruption is unlikely to correct the problem.</span></span> <span data-ttu-id="75dcf-122">Par conséquent, effectuer des sauvegardes régulières et tester votre plan de restauration sont essentiels pour la protection d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-122">Therefore, taking regular backups and testing your restore plan are essential to protect a database.</span></span> <span data-ttu-id="75dcf-123">Pour plus d’informations, consultez [Sauvegarder et restaurer des bases de données SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="75dcf-123">For more information, see [Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75dcf-124">Si vous devez restaurer la base de données source jusqu'à la date et l'heure où vous avez créé un instantané de base de données, utilisez le mode de récupération complète et implémentez une stratégie de sauvegarde qui vous permette une telle opération.</span><span class="sxs-lookup"><span data-stu-id="75dcf-124">If you need to be able to restore the source database to the point in time at which you created a database snapshot, use the full recovery model and implement a backup policy that enables you to do that.</span></span>  
  
-   <span data-ttu-id="75dcf-125">La base de données source d'origine est remplacée par la base de données rétablie, donc toutes les mises à jour de la base de données depuis la création de l'instantané sont perdues.</span><span class="sxs-lookup"><span data-stu-id="75dcf-125">The original source database is overwritten by the reverted database, so any updates to the database since the snapshot's creation are lost.</span></span>  
  
-   <span data-ttu-id="75dcf-126">L'opération de retour à un état antérieur remplace également l'ancien fichier journal puis le reconstruit.</span><span class="sxs-lookup"><span data-stu-id="75dcf-126">The revert operation also overwrites the old log file and rebuilds the log.</span></span> <span data-ttu-id="75dcf-127">De ce fait, vous ne pouvez plus restaurer la base de données par progression jusqu'à l'erreur de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="75dcf-127">Consequently, you cannot roll the reverted database forward to the point of user error.</span></span> <span data-ttu-id="75dcf-128">Aussi, nous vous recommandons de sauvegarder le journal avant de rétablir une base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-128">Therefore, we recommend that you back up the log before reverting a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75dcf-129">Bien que vous ne puissiez pas restaurer le journal original pour restaurer la base de données par progression, les informations qu'il contient peuvent être utiles pour reconstituer les données perdues.</span><span class="sxs-lookup"><span data-stu-id="75dcf-129">Although you cannot restore the original log to roll forward the database, the information in the original log file can be useful for reconstructing lost data.</span></span>  
  
-   <span data-ttu-id="75dcf-130">Le retour à un état antérieur brise la chaîne de sauvegarde du journal.</span><span class="sxs-lookup"><span data-stu-id="75dcf-130">Reverting breaks the log backup chain.</span></span> <span data-ttu-id="75dcf-131">Aussi, avant d'effectuer les sauvegardes du journal de la base de données ainsi récupérée, vous devez d'abord effectuer une sauvegarde de base de données complète ou une sauvegarde de fichiers.</span><span class="sxs-lookup"><span data-stu-id="75dcf-131">Therefore, before you can take log backups of the reverted database, you must first take a full database backup or file backup.</span></span> <span data-ttu-id="75dcf-132">Nous recommandons une sauvegarde de base de données complète.</span><span class="sxs-lookup"><span data-stu-id="75dcf-132">We recommend a full database backup.</span></span>  
  
-   <span data-ttu-id="75dcf-133">Au cours d'une opération de retour à un état antérieur, l'instantané et la base de données source sont tous deux inaccessibles.</span><span class="sxs-lookup"><span data-stu-id="75dcf-133">During a revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="75dcf-134">Elles sont marquées comme étant en cours de restauration.</span><span class="sxs-lookup"><span data-stu-id="75dcf-134">The source database and snapshot are both marked "In restore."</span></span> <span data-ttu-id="75dcf-135">En cas d'erreur pendant cette opération, lorsque la base de données redémarrera, la restauration tentera de se terminer.</span><span class="sxs-lookup"><span data-stu-id="75dcf-135">If an error occurs during the revert operation, when the database starts up again, the revert operation will try to finish reverting.</span></span>  
  
-   <span data-ttu-id="75dcf-136">Les métadonnées d'une base de données ainsi restituée sont les mêmes qu'au moment de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="75dcf-136">The metadata of a reverted database is the same as the metadata at the time of the snapshot.</span></span>  
  
-   <span data-ttu-id="75dcf-137">Le rétablissement supprime tous les catalogues de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="75dcf-137">Reverting drops all the full-text catalogs.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="75dcf-138">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="75dcf-138">Prerequisites</span></span>  
 <span data-ttu-id="75dcf-139">Vérifiez que la base de données source et l'instantané de base de données remplissent les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="75dcf-139">Ensure that the source database and database snapshot meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="75dcf-140">Vérifiez que la base de données n'a pas été endommagée.</span><span class="sxs-lookup"><span data-stu-id="75dcf-140">Verify that the database has not become corrupted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75dcf-141">Si la base de données a été endommagée, vous devez la restaurer à partir des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="75dcf-141">If the database has been corrupted, you will need to restore it from backups.</span></span> <span data-ttu-id="75dcf-142">Pour plus d’informations, consultez [Restaurations complètes de bases de données &#40;mode de récupération simple&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) ou [Restaurations complètes de bases de données &#40;mode de récupération complète&#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="75dcf-142">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span></span>  
  
-   <span data-ttu-id="75dcf-143">Identifiez un instantané récent, créé avant l'erreur.</span><span class="sxs-lookup"><span data-stu-id="75dcf-143">Identify a recent snapshot that was created before the error.</span></span> <span data-ttu-id="75dcf-144">Pour plus d’informations, consultez [Afficher un instantané de base de données &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="75dcf-144">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
-   <span data-ttu-id="75dcf-145">Supprimez tous les autres instantanés qui existent actuellement sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-145">Drop any other snapshots that currently exist on the database.</span></span> <span data-ttu-id="75dcf-146">Pour plus d’informations, consultez [Supprimer un instantané de base de données &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="75dcf-146">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="75dcf-147">Sécurité</span><span class="sxs-lookup"><span data-stu-id="75dcf-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="75dcf-148">Autorisations</span><span class="sxs-lookup"><span data-stu-id="75dcf-148">Permissions</span></span>  
 <span data-ttu-id="75dcf-149">Tout utilisateur qui dispose des autorisations RESTORE DATABASE sur la base de données source peut la rétablir dans l'état qui était le sien au moment où l'instantané a été créé.</span><span class="sxs-lookup"><span data-stu-id="75dcf-149">Any user who has RESTORE DATABASE permissions on the source database can revert it to its state when a database snapshot was created.</span></span>  
  
##  <a name="how-to-revert-a-database-to-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="75dcf-150">Comment rétablir une base de données dans l'état d'un instantané de base de données (à l'aide de Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="75dcf-150">How to Revert a Database to a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="75dcf-151">**Pour rétablir une base de données dans l'état d'un instantané de base de données**</span><span class="sxs-lookup"><span data-stu-id="75dcf-151">**To revert a database to a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75dcf-152">Pour obtenir un exemple de cette procédure, consultez [Exemples (Transact-SQL)](#TsqlExample)plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="75dcf-152">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="75dcf-153">Identifiez l'instantané de base de données auquel vous souhaitez restaurer la base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-153">Identify the database snapshot to which you want to revert the database.</span></span> <span data-ttu-id="75dcf-154">Vous pouvez afficher les instantanés sur une base de données dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (consultez [Afficher un instantané de base de données &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="75dcf-154">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span></span> <span data-ttu-id="75dcf-155">En outre, vous pouvez identifier la base de données source d’un affichage à partir de la colonne **source_database_id** de l’affichage catalogue [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="75dcf-155">Also, you can identify the source database of a view from the **source_database_id** column of the [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
2.  <span data-ttu-id="75dcf-156">Supprimez tous les autres instantanés de base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-156">Drop any other database snapshots.</span></span>  
  
     <span data-ttu-id="75dcf-157">Pour plus d’informations sur la suppression de captures instantanées, consultez [Supprimer un instantané de base de données &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="75dcf-157">For information on dropping snapshots, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span> <span data-ttu-id="75dcf-158">Si la base de données utilise le mode de restauration complète, vous devez sauvegarder le journal avant de rétablir la base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-158">If the database uses the full recovery model, before reverting, you should back up the log.</span></span> <span data-ttu-id="75dcf-159">Pour plus d’informations, consultez [Sauvegarder un journal des transactions &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) ou [Sauvegarder le journal des transactions lorsque la base de données est endommagée &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="75dcf-159">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) or [Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="75dcf-160">Effectuez l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="75dcf-160">Perform the revert operation.</span></span>  
  
     <span data-ttu-id="75dcf-161">Une opération de restauration nécessite des autorisations RESTORE DATABASE sur la base de données source.</span><span class="sxs-lookup"><span data-stu-id="75dcf-161">A revert operation requires RESTORE DATABASE permissions on the source database.</span></span> <span data-ttu-id="75dcf-162">Pour restaurer la base de données, utilisez l'instruction Transact-SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="75dcf-162">To revert the database, use the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="75dcf-163">RESTORE DATABASE *nom_base_de_données* FROM DATABASE_SNAPSHOT **=** _nom_instantané_base_de_données_</span><span class="sxs-lookup"><span data-stu-id="75dcf-163">RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=**_database_snapshot_name_</span></span>  
  
     <span data-ttu-id="75dcf-164">Où *nom_base_de_données* est la base de données source et *nom_instantané_base_de_données* le nom de l’instantané auquel vous souhaitez rétablir la base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-164">Where *database_name* is the source database and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="75dcf-165">Notez que dans cette instruction, vous devez spécifier un nom d'instantané et non un périphérique de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="75dcf-165">Notice that in this statement, you must specify a snapshot name rather than a backup device.</span></span>  
  
     <span data-ttu-id="75dcf-166">Pour plus d’informations, consultez [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="75dcf-166">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75dcf-167">Pendant l'opération de restauration, l'instantané et la base de données source ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="75dcf-167">During the revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="75dcf-168">La base de données source et l'instantané sont tous deux signalés « In restore (en restauration) ».</span><span class="sxs-lookup"><span data-stu-id="75dcf-168">The source database and snapshot are both marked as "In restore."</span></span> <span data-ttu-id="75dcf-169">Si une erreur se produit pendant l'opération de restauration, cette dernière tentera d'aboutir lors du redémarrage de la base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-169">If an error occurs during the revert operation, it will try to finish reverting when the database starts up again.</span></span>  
  
4.  <span data-ttu-id="75dcf-170">Si le propriétaire de la base de données a changé depuis la création de l'instantané de base de données, il convient de mettre à jour le propriétaire de la base de données restaurée.</span><span class="sxs-lookup"><span data-stu-id="75dcf-170">If the database owner changed since creation of the database snapshot, you may want to update the database owner of the reverted database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75dcf-171">La base de données restaurée conserve les autorisations et la configuration (par exemple, le propriétaire de la base de données et le mode de récupération) de l'instantané de base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-171">The reverted database retains the permissions and configuration (such as database owner and recovery model) of the database snapshot.</span></span>  
  
5.  <span data-ttu-id="75dcf-172">Démarrez la base de données.</span><span class="sxs-lookup"><span data-stu-id="75dcf-172">Start the database.</span></span>  
  
6.  <span data-ttu-id="75dcf-173">En option, sauvegardez la base de données restaurée, notamment si elle utilise le mode de récupération complète (ou utilisant les journaux de transactions).</span><span class="sxs-lookup"><span data-stu-id="75dcf-173">Optionally, back up the reverted database, especially if it uses the full (or bulk-logged) recovery model.</span></span> <span data-ttu-id="75dcf-174">Pour sauvegarder une base de données, consultez [Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="75dcf-174">To back up a database, see [Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="75dcf-175">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="75dcf-175">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="75dcf-176">Cette section présente les exemples suivants de rétablissement d'une base de données à un état antérieur par le biais d'un instantané de base de données :</span><span class="sxs-lookup"><span data-stu-id="75dcf-176">This section contains the following examples of reverting a database to a database snapshot:</span></span>  
  
-   <span data-ttu-id="75dcf-177">R.</span><span class="sxs-lookup"><span data-stu-id="75dcf-177">A.</span></span> [<span data-ttu-id="75dcf-178">Rétablissement d'un instantané sur la base de données AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="75dcf-178">Reverting a snapshot on the AdventureWorks database</span></span>](#Reverting_AW)  
  
-   <span data-ttu-id="75dcf-179">B.</span><span class="sxs-lookup"><span data-stu-id="75dcf-179">B.</span></span> [<span data-ttu-id="75dcf-180">Rétablissement d'un instantané sur la base de données Sales (Ventes)</span><span class="sxs-lookup"><span data-stu-id="75dcf-180">Reverting a snapshot on the Sales database</span></span>](#Reverting_Sales)  
  
####  <a name="a-reverting-a-snapshot-on-the-adventureworks-database"></a><a name="Reverting_AW"></a> <span data-ttu-id="75dcf-181">A.</span><span class="sxs-lookup"><span data-stu-id="75dcf-181">A.</span></span> <span data-ttu-id="75dcf-182">Rétablissement d'un instantané sur la base de données AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="75dcf-182">Reverting a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="75dcf-183">L'exemple suivant part du principe qu'un seul instantané existe actuellement sur la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75dcf-183">This example assumes that only one snapshot currently exists on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="75dcf-184">Pour l’exemple qui crée l’instantané auquel la base de données est ici rétablie, consultez [Créer un instantané de base de données &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="75dcf-184">For the example that creates the snapshot to which the database is reverted here, see [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
USE master;  
-- Reverting AdventureWorks to AdventureWorks_dbss1800  
RESTORE DATABASE AdventureWorks from   
DATABASE_SNAPSHOT = 'AdventureWorks_dbss1800';  
GO  
```  
  
####  <a name="b-reverting-a-snapshot-on-the-sales-database"></a><a name="Reverting_Sales"></a> <span data-ttu-id="75dcf-185">B.</span><span class="sxs-lookup"><span data-stu-id="75dcf-185">B.</span></span> <span data-ttu-id="75dcf-186">Rétablissement d'un instantané sur la base de données Sales (Ventes)</span><span class="sxs-lookup"><span data-stu-id="75dcf-186">Reverting a snapshot on the Sales database</span></span>  
 <span data-ttu-id="75dcf-187">Cet exemple suppose que deux instantanés existent actuellement sur la base de données **Sales** : **sales_snapshot0600** et **sales_snapshot1200**.</span><span class="sxs-lookup"><span data-stu-id="75dcf-187">This example assumes that two snapshots currently exist on the **Sales** database: **sales_snapshot0600** and **sales_snapshot1200**.</span></span> <span data-ttu-id="75dcf-188">Cet exemple supprime l'instantané le plus ancien et rétablit la base de données au moyen de l'instantané le plus récent.</span><span class="sxs-lookup"><span data-stu-id="75dcf-188">The example deletes the older of the snapshots and reverts the database to the more recent snapshot.</span></span>  
  
 <span data-ttu-id="75dcf-189">Pour voir le code servant à créer la base de données et les instantanés donnés en exemple ici, consultez :</span><span class="sxs-lookup"><span data-stu-id="75dcf-189">For the code for creating the sample database and snapshots on which this example depends, see:</span></span>  
  
-   <span data-ttu-id="75dcf-190">Pour la base de données **Sales** et l’instantané **sales_snapshot0600**, consultez « Création d’une base de données avec des groupes de fichiers » et « Création d’un instantané de base de données » dans [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="75dcf-190">For the **Sales** database and the **sales_snapshot0600** snapshot, see "Creating a database with filegroups" and "Creating a database snapshot" in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
-   <span data-ttu-id="75dcf-191">Pour la base de données **sales_snapshot1200** , consultez « Création d’un instantané de la base de données Sales (Ventes) » dans [Créer un instantané de base de données &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="75dcf-191">For the **sales_snapshot1200** snapshot, see "Creating a snapshot on the Sales database" in [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
--Test to see if sales_snapshot0600 exists and if it   
-- does, delete it.  
IF EXISTS (SELECT dbid FROM sys.databases  
    WHERE NAME='sales_snapshot0600')  
    DROP DATABASE SalesSnapshot0600;  
GO  
-- Reverting Sales to sales_snapshot1200  
USE master;  
RESTORE DATABASE Sales FROM DATABASE_SNAPSHOT = 'sales_snapshot1200';  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="75dcf-192">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="75dcf-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="75dcf-193">Créer un instantané de base de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="75dcf-193">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="75dcf-194">Afficher un instantané de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="75dcf-194">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="75dcf-195">Supprimer un instantané de base de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="75dcf-195">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="75dcf-196">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75dcf-196">See Also</span></span>  
 <span data-ttu-id="75dcf-197">[Instantanés de base de données &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="75dcf-197">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="75dcf-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="75dcf-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="75dcf-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="75dcf-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="75dcf-200">Mise en miroir et instantanés de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="75dcf-200">Database Mirroring and Database Snapshots &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-and-database-snapshots-sql-server.md)  
  
  
