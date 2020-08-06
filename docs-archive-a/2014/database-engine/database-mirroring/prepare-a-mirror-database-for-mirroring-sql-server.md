---
title: Préparer une base de données miroir pour la mise en miroir (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], preparing for mirroring
- logins [SQL Server], database mirroring
- mirror database [SQL Server]
ms.assetid: 8676f9d8-c451-419b-b934-786997d46c2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf46b4f6fd8e7af55e1930ef6063c4754673fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701844"
---
# <a name="prepare-a-mirror-database-for-mirroring-sql-server"></a><span data-ttu-id="c5841-102">Préparer une base de données miroir pour la mise en miroir (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c5841-102">Prepare a Mirror Database for Mirroring (SQL Server)</span></span>
  <span data-ttu-id="c5841-103">Avant qu'une session de mise en miroir de bases de données puisse commencer, le propriétaire de la base de données ou l'administrateur système doit s'assurer que la base de données miroir a été créée et qu'elle est prête pour la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-103">Before a database mirroring session can start, the database owner or system administrator must make sure that the mirror database has been created and is ready for mirroring.</span></span> <span data-ttu-id="c5841-104">La création d'une nouvelle base de données miroir requiert au minimum la réalisation d'une sauvegarde complète de la base de données principale puis d'une sauvegarde du journal, ainsi que la restauration de ces deux sauvegardes sur l'instance du serveur miroir, en utilisant WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c5841-104">Creating a new mirror database minimally requires taking a full backup of the principal database and a subsequent log backup and restoring them both onto the mirror server instance, using WITH NORECOVERY.</span></span>  
  
 <span data-ttu-id="c5841-105">Cette rubrique explique comment préparer une base de données miroir dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5841-105">This topic describes how to prepare a mirror database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c5841-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c5841-106">Before You Begin</span></span>  
  
###  <a name="requirements"></a><a name="Requirements"></a> <span data-ttu-id="c5841-107">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c5841-107">Requirements</span></span>  
  
-   <span data-ttu-id="c5841-108">Les instances du serveur miroir et du serveur principal doivent exécuter la même version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5841-108">The principal and mirror server instances must be running on the same version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c5841-109">Bien qu'il soit possible que le serveur miroir possède une version ultérieure de SQL Server, cette configuration est recommandée uniquement lors d'une mise à niveau planifiée avec soin.</span><span class="sxs-lookup"><span data-stu-id="c5841-109">While it is possible for the mirror server to have a higher version of SQL Server, this configuration is only recommended during a carefully planned upgrade process.</span></span> <span data-ttu-id="c5841-110">Dans une telle configuration, vous courez le risque d'un basculement automatique, dans lequel le déplacement des données est automatiquement interrompu, car les données n'ont pas accès à une version antérieure de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5841-110">In such a configuration, you run the risk of an automatic failover, in which data movement is automatically suspended because data cannot move to a lower version of SQL Server.</span></span> <span data-ttu-id="c5841-111">Pour plus d'informations, voir [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-111">For more information, see [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span></span>  
  
-   <span data-ttu-id="c5841-112">Les instances du serveur miroir et du serveur principal doivent exécuter la même édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5841-112">The principal and mirror server instances must be running on the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c5841-113">Pour plus d’informations sur la prise en charge de la mise en miroir de bases de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], consultez [Fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-113">For information about support for database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="c5841-114">La base de données doit utiliser le mode de récupération complète.</span><span class="sxs-lookup"><span data-stu-id="c5841-114">The database must use the full recovery model.</span></span>  
  
     <span data-ttu-id="c5841-115">Pour plus d’informations, consultez [Afficher ou modifier le mode de récupération d’une base de données &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) ou [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) et [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c5841-115">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) or [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) and [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="c5841-116">Le nom de la base de données miroir doit être le même que celui de la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c5841-116">The name of the mirror database must be the same as the name of the principal database.</span></span>  
  
-   <span data-ttu-id="c5841-117">La base de données miroir doit être dans l'état RESTORING pour que la mise en miroir fonctionne.</span><span class="sxs-lookup"><span data-stu-id="c5841-117">The mirror database must be in the RESTORING state for mirroring to work.</span></span> <span data-ttu-id="c5841-118">Lors de la préparation d'une base de données miroir, vous devez utiliser RESTORE WITH NORECOVERY pour chaque opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="c5841-118">When preparing a mirror database, you must use RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="c5841-119">Au minimum, vous devrez restaurer avec RESTORE WITH NORECOVERY une sauvegarde complète de la base de données principale, suivie de toutes les sauvegardes de journaux suivantes.</span><span class="sxs-lookup"><span data-stu-id="c5841-119">Minimally, you will need to restore WITH NORECOVERY a full backup of the principal database, followed by all subsequent log backups.</span></span>  
  
-   <span data-ttu-id="c5841-120">Le système dans lequel vous envisagez de créer la base de données miroir doit posséder un lecteur de disque avec suffisamment d'espace pour contenir la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-120">The system where you plan to create the mirror database must possesses a disk drive with sufficient space to hold the mirror database.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c5841-121">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c5841-121">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c5841-122">Vous ne pouvez pas mettre en miroir les bases de données système **master**, **msdb**, **temp**ou **model** .</span><span class="sxs-lookup"><span data-stu-id="c5841-122">You cannot mirror the **master**, **msdb**, **temp**, or **model** system databases.</span></span>  
  
-   <span data-ttu-id="c5841-123">Vous ne pouvez pas mettre en miroir une base de données qui appartient à un [groupes de disponibilité AlwaysOn (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-123">You cannot mirror a database that belongs to an [AlwaysOn Availability Groups (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c5841-124">Recommandations</span><span class="sxs-lookup"><span data-stu-id="c5841-124">Recommendations</span></span>  
  
-   <span data-ttu-id="c5841-125">Utilisez une sauvegarde complète très récente ou une sauvegarde différentielle récente de la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c5841-125">Use a very recent full database backup or a recent differential database backup of the principal database.</span></span>  
  
-   <span data-ttu-id="c5841-126">Si un travail de sauvegarde du journal est planifié pour s'exécuter très fréquemment sur la base de données principale, vous pouvez être amené à désactiver le travail de sauvegarde tant que la mise en miroir n'a pas commencé.</span><span class="sxs-lookup"><span data-stu-id="c5841-126">If a log backup job is scheduled to run very frequently on the principal database, you might have to disable the backup job until mirroring has started.</span></span>  
  
-   <span data-ttu-id="c5841-127">Si possible, le chemin d'accès (y compris la lettre de lecteur) de la base de données miroir doit être identique au chemin d'accès de la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c5841-127">If possible, the path (including the drive letter) of the mirror database should be identical to the path of the principal database.</span></span>  
  
     <span data-ttu-id="c5841-128">Si les chemins d'accès des fichiers doivent différer, par exemple, si la base de données principale se trouve sur le lecteur « F: », mais que le système miroir n'a pas de lecteur F:, vous devez inclure l'option MOVE dans l'instruction RESTORE STATEMENT.</span><span class="sxs-lookup"><span data-stu-id="c5841-128">If the file paths must differ, for example, if the principal database is on drive 'F:' but the mirror system lacks an F: drive, you must include the MOVE option in the RESTORE STATEMENT.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c5841-129">Pour pouvoir ajouter un fichier pendant une session de mise en miroir sans compromettre la session, il faut que le chemin d'accès au fichier existe sur les deux serveurs.</span><span class="sxs-lookup"><span data-stu-id="c5841-129">Adding a file during a mirroring session without impacting the session requires that the path of the file exists on both servers.</span></span> <span data-ttu-id="c5841-130">Par conséquent, si vous déplacez des fichiers de base de données lors de la création de la base de données miroir, une opération d'ajout de fichier ultérieure peut échouer sur la base de données miroir et entraîner la suspension de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-130">Therefore, if you move the database files when creating the mirror database, a later add-file operation might fail on the mirror database and cause mirroring to be suspended.</span></span> <span data-ttu-id="c5841-131">Pour plus d’informations sur le traitement d’un échec d’opération de création de fichier, consultez [Résoudre des problèmes de configuration de mise en miroir de bases de données &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-131">For information about dealing with a failed create-file operation, see [Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="c5841-132">Si la base de données principale comporte des catalogues de texte intégral, nous vous recommandons de consulter [Mise en miroir de bases de données et catalogues de texte intégral &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-132">If the principal database has any full-text catalogs, we recommend that you see [Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span></span>  
  
-   <span data-ttu-id="c5841-133">Dans le cas d'une base de données de production, effectuez toujours les sauvegardes sur une unité distincte.</span><span class="sxs-lookup"><span data-stu-id="c5841-133">For a production database, always back up to a separate device.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c5841-134">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c5841-134">Security</span></span>  
 <span data-ttu-id="c5841-135">TRUSTWORTHY a la valeur OFF lorsqu'une base de données est sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="c5841-135">TRUSTWORTHY is set to OFF when a database is backed up.</span></span> <span data-ttu-id="c5841-136">Par conséquent, la propriété TRUSTWORTHY d'une nouvelle base de données miroir a toujours la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="c5841-136">Therefore, TRUSTWORTHY is always OFF on a new mirror database.</span></span> <span data-ttu-id="c5841-137">Si la base de données doit être fiable après un basculement, des opérations de configuration supplémentaires sont requises.</span><span class="sxs-lookup"><span data-stu-id="c5841-137">If the database needs to be trustworthy after a failover, additional setup steps are necessary.</span></span> <span data-ttu-id="c5841-138">Pour plus d’informations, consultez [Configurer une base de données miroir pour utiliser la propriété Trustworthy &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-138">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
 <span data-ttu-id="c5841-139">Pour plus d’informations sur l’activation du déchiffrement automatique de la clé principale d’une base de données miroir, consultez [Configurer une base de données miroir chiffrée](set-up-an-encrypted-mirror-database.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-139">For information about enabling automatic decryption of the database master key of a mirror database, see [Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c5841-140">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c5841-140">Permissions</span></span>  
 <span data-ttu-id="c5841-141">Propriétaire de base de données ou administrateur système.</span><span class="sxs-lookup"><span data-stu-id="c5841-141">Database owner or system administrator.</span></span>  
  
##  <a name="to-prepare-an-existing-mirror-database-to-restart-mirroring"></a><a name="PrepareToRestartMirroring"></a> <span data-ttu-id="c5841-142">Pour préparer une base de données miroir existante pour redémarrer la mise en miroir</span><span class="sxs-lookup"><span data-stu-id="c5841-142">To Prepare an Existing Mirror Database to Restart Mirroring</span></span>  
 <span data-ttu-id="c5841-143">Si la mise en miroir a été supprimée et que la base de données miroir est toujours à l'état RECOVERING, vous pouvez redémarrer la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-143">If mirroring has been removed and the mirror database is still in the RECOVERING state, you can restart mirroring.</span></span>  
  
1.  <span data-ttu-id="c5841-144">Prenez au moins une sauvegarde du journal sur la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c5841-144">Take at least one log backup on the principal database.</span></span> <span data-ttu-id="c5841-145">Pour plus d’informations, consultez [Sauvegarder un journal des transactions &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-145">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="c5841-146">Sur la base de données miroir, restaurez à l'aide de RESTORE WITH NORECOVERY toutes les sauvegardes des journaux effectuées sur la base de données principale depuis la suppression de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-146">On the mirror database, use RESTORE WITH NORECOVERY to restore all log backups taken on the principal database since mirroring was removed.</span></span> <span data-ttu-id="c5841-147">Pour plus d’informations, consultez [Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-147">For more information, see [Restore a Transaction Log Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span></span>  
  
##  <a name="to-prepare-a-new-mirror-database"></a><a name="CombinedProcedure"></a> <span data-ttu-id="c5841-148">Pour préparer une nouvelle base de données miroir</span><span class="sxs-lookup"><span data-stu-id="c5841-148">To Prepare a New Mirror Database</span></span>  
 <span data-ttu-id="c5841-149">**Pour préparer une base de données miroir**</span><span class="sxs-lookup"><span data-stu-id="c5841-149">**To prepare a mirror database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5841-150">Pour obtenir un exemple [!INCLUDE[tsql](../../includes/tsql-md.md)] de cette procédure, consultez [Exemple (Transact-SQL)](#TsqlExample), plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="c5841-150">For a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="c5841-151">Connectez-vous à l'instance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="c5841-151">Connect to principal server instance.</span></span>  
  
2.  <span data-ttu-id="c5841-152">Créez une sauvegarde complète ou une sauvegarde différentielle de la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c5841-152">Create either a full database backup or a differential database backup of the principal database.</span></span>  
  
    -   [<span data-ttu-id="c5841-153">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-153">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
    -   <span data-ttu-id="c5841-154">[Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-154">[Create a Differential Database Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="c5841-155">En général, vous devez prendre au moins une sauvegarde du journal sur la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c5841-155">Typically, you need to take at least one log backup on the principal database.</span></span> <span data-ttu-id="c5841-156">Toutefois, une sauvegarde du journal peut s'avérer superflue, si la base de données vient d'être créée et qu'aucune sauvegarde du journal n'a été encore réalisée ou si le mode de récupération vient d'être modifié de SIMPLE à FULL.</span><span class="sxs-lookup"><span data-stu-id="c5841-156">However, a log backup might be unnecessary, if the database has just been created and no log backup has been taken yet, or if the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
    -   [<span data-ttu-id="c5841-157">Sauvegarder un journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-157">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
4.  <span data-ttu-id="c5841-158">À moins que les sauvegardes se trouvent sur un lecteur réseau accessible à partir des deux systèmes, copiez les sauvegardes de la base de données et des journaux sur le système qui hébergera l'instance de serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-158">Unless the backups are on a network drive that is accessible from both systems, copy the database and log backups to the system that will host the mirror server instance.</span></span>  
  
5.  <span data-ttu-id="c5841-159">Connectez-vous à l'instance de serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-159">Connect to mirror server instance.</span></span>  
  
6.  <span data-ttu-id="c5841-160">À l'aide de RESTORE WITH NORECOVERY, créez la base de données miroir en restaurant la sauvegarde complète de la base de données et, éventuellement, la sauvegarde différentielle de base de données la plus récente, sur l'instance de serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-160">Using RESTORE WITH NORECOVERY, create the mirror database by restoring the full database backup and, optionally, the most recent differential database backup, onto the mirror server instance.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5841-161">Si vous restaurez le groupe de fichiers de base de données par groupe de fichiers, veillez à restaurer l'intégralité de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c5841-161">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
    -   [<span data-ttu-id="c5841-162">Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-162">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
    -   <span data-ttu-id="c5841-163">[RESTORE &amp;#40;Transact-SQL&amp;#41;](/sql/t-sql/statements/restore-statements-transact-sql) et [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c5841-163">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
7.  <span data-ttu-id="c5841-164">À l'aide de RESTORE WITH NORECOVERY, appliquez les autres sauvegardes de fichiers journaux ou sauvegardes en attente à la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-164">Using RESTORE WITH NORECOVERY, apply any outstanding log backup or backups to the mirror database.</span></span>  
  
    -   [<span data-ttu-id="c5841-165">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-165">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="c5841-166">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c5841-166">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="c5841-167">Avant de démarrer une session de mise en miroir de bases de données, vous devez créer la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-167">Before you can start a database mirroring session, you must create the mirror database.</span></span> <span data-ttu-id="c5841-168">Vous devez procéder à cette opération avant de démarrer la session de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-168">You should do this just before starting the mirroring session.</span></span>  
  
 <span data-ttu-id="c5841-169">L'exemple suivant utilise la base de données d'exemple [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] qui emploie par défaut le mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="c5841-169">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="c5841-170">Pour utiliser la mise en miroir de base de données sur la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , modifiez-la afin qu'elle utilise le mode de restauration complète :</span><span class="sxs-lookup"><span data-stu-id="c5841-170">To use database mirroring with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="c5841-171">Après avoir changé le mode de récupération de SIMPLE à FULL, créez une sauvegarde complète qui pourra être utilisée pour créer la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-171">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the mirror database.</span></span> <span data-ttu-id="c5841-172">Dans la mesure où le mode de récupération vient d'être modifié, l'option WITH FORMAT est spécifiée pour créer un nouveau support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c5841-172">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="c5841-173">Il peut se révéler utile de séparer les sauvegardes effectuées en mode de récupération complète des sauvegardes préalablement effectuées en mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="c5841-173">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="c5841-174">Pour les besoins de cet exemple, le fichier de sauvegarde (`C:\AdventureWorks.bak`) est créé sur le même lecteur que la base de données.</span><span class="sxs-lookup"><span data-stu-id="c5841-174">For the purpose of this example, the backup file (`C:\AdventureWorks.bak`) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5841-175">Dans le cas d'une base de données de production, il est conseillé de toujours effectuer les sauvegardes sur une unité distincte.</span><span class="sxs-lookup"><span data-stu-id="c5841-175">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="c5841-176">Sur l'instance de serveur principal (sur `PARTNERHOST1`), créez une sauvegarde complète de la base de données principale comme suit :</span><span class="sxs-lookup"><span data-stu-id="c5841-176">On the principal server instance (on `PARTNERHOST1`), create a full backup of the principal database as follows:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="c5841-177">Copiez cette sauvegarde complète sur le serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-177">Copy the full backup to the mirror server.</span></span>  
  
4.  <span data-ttu-id="c5841-178">À l'aide de RESTORE WITH NORECOVERY, restaurez la sauvegarde complète sur l'instance de serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-178">Using RESTORE WITH NORECOVERY, restore the full backup onto the mirror server instance.</span></span> <span data-ttu-id="c5841-179">La commande de restauration dépend si les chemins d'accès aux bases de données principale et miroir sont identiques ou non.</span><span class="sxs-lookup"><span data-stu-id="c5841-179">The restore command depends on whether the paths of principal and mirror databases are identical.</span></span>  
  
    -   <span data-ttu-id="c5841-180">**Si les chemins d'accès sont identiques :**</span><span class="sxs-lookup"><span data-stu-id="c5841-180">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="c5841-181">Sur l'instance de serveur miroir (sur `PARTNERHOST5`), restaurez la sauvegarde complète comme suit :</span><span class="sxs-lookup"><span data-stu-id="c5841-181">On the mirror server instance (on `PARTNERHOST5`), restore the full backup as follows:</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks   
            FROM DISK = 'C:\AdventureWorks.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="c5841-182">**Si les chemins d'accès sont différents :**</span><span class="sxs-lookup"><span data-stu-id="c5841-182">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="c5841-183">Si le chemin d'accès de la base de données miroir n'est pas le même que celui de la base de données principale (lettres de lecteurs distinctes, par exemple), la création de la base de données miroir requiert l'intégration d'une clause MOVE dans l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="c5841-183">If the path of the mirror database differs from the path of the principal database (for instance, their drive letters differ), creating the mirror database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="c5841-184">Si les chemins d'accès des bases de données principale et miroir diffèrent, vous ne pouvez pas ajouter de fichier.</span><span class="sxs-lookup"><span data-stu-id="c5841-184">If the path names of the principal and mirror databases differ, you cannot add a file.</span></span> <span data-ttu-id="c5841-185">La raison tient à la réception du journal pour l'opération d'ajout de fichier puisque l'instance de serveur miroir tente de placer le nouveau fichier dans l'emplacement utilisé par la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c5841-185">This is because on receiving the log for the add file operation, the mirror server instance attempts to place the new file in the location used by the principal database.</span></span>  
  
         <span data-ttu-id="c5841-186">Par exemple, la commande ci-dessous restaure une sauvegarde d’une base de données principale qui réside dans C:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\ dans un emplacement différent, D:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, où la base de données miroir doit résider.</span><span class="sxs-lookup"><span data-stu-id="c5841-186">For example, the following command restores a backup of a principal database residing in C:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\ to a different location, D:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, where the mirror database is to reside.</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks  
           FROM DISK='C:\AdventureWorks.bak'  
           WITH NORECOVERY,   
              MOVE 'AdventureWorks_Data' TO   
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Data.mdf',   
              MOVE 'AdventureWorks_Log' TO  
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Log.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="c5841-187">Après avoir créé la sauvegarde complète, vous devez créer une sauvegarde du journal sur la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="c5841-187">After you create the full backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="c5841-188">Par exemple, l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante sauvegarde le journal dans le même fichier utilisé par la sauvegarde complète antérieure :</span><span class="sxs-lookup"><span data-stu-id="c5841-188">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding full backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="c5841-189">Avant de démarrer la mise en miroir, vous devez appliquer la sauvegarde du journal requise (et toutes les sauvegardes de journal ultérieures).</span><span class="sxs-lookup"><span data-stu-id="c5841-189">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="c5841-190">Par exemple, l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] ci-dessous restaure le premier journal à partir de `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="c5841-190">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="c5841-191">Si des sauvegardes de journal supplémentaires se produisent avant le démarrage de la mise en miroir, vous devez également restaurer toutes ces sauvegardes de journal, dans l'ordre, sur le serveur miroir, en utilisant WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c5841-191">If any additional log backups occur before you start mirroring, you must also restore all of those log backups, in sequence, to the mirror server using WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="c5841-192">Par exemple, l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] ci-dessous restaure deux journaux supplémentaires à partir de `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="c5841-192">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores two additional logs from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
 <span data-ttu-id="c5841-193">Pour voir un exemple de configuration de la mise en miroir d’une base de données illustrant la configuration de la sécurité, la préparation de la base de données miroir, la configuration des serveurs partenaires et l’ajout d’un témoin, consultez [Configuration de la mise en miroir d’une base de données &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-193">For a complete example of setting up database mirroring, showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-preparing-a-mirror-database"></a><a name="FollowUp"></a> <span data-ttu-id="c5841-194">Suivi : Après avoir préparé une base de données miroir</span><span class="sxs-lookup"><span data-stu-id="c5841-194">Follow Up: After Preparing a Mirror Database</span></span>  
  
1.  <span data-ttu-id="c5841-195">Si des sauvegardes de fichier journal supplémentaires ont été effectuées depuis votre opération RESTORE LOG la plus récente, vous devez appliquer manuellement chaque sauvegarde de journal supplémentaire, à l'aide de RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c5841-195">If any additional log backups have been taken since your most recent RESTORE LOG operation, you must manually apply every additional log backup, using RESTORE WITH NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="c5841-196">Démarrez la session de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-196">Start the mirroring session.</span></span> <span data-ttu-id="c5841-197">Pour plus d’informations, consultez [Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) ou de [Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-197">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) or [Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="c5841-198">Si vous avez désactivé le travail de sauvegarde sur la base de données principale, réactivez le travail.</span><span class="sxs-lookup"><span data-stu-id="c5841-198">If you disabled the backup job on the principal database, reenable the job.</span></span>  
  
4.  <span data-ttu-id="c5841-199">Si la base de données doit être fiable après un basculement, des opérations de configuration supplémentaires sont requises après le début de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c5841-199">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span> <span data-ttu-id="c5841-200">Pour plus d’informations, consultez [Configurer une base de données miroir pour utiliser la propriété Trustworthy &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c5841-200">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c5841-201">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="c5841-201">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c5841-202">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-202">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="c5841-203">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-203">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="c5841-204">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-204">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="c5841-205">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-205">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="c5841-206">Configurer une base de données miroir chiffrée</span><span class="sxs-lookup"><span data-stu-id="c5841-206">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
-   [<span data-ttu-id="c5841-207">Configurer une base de données miroir pour utiliser la propriété Trustworthy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-207">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="c5841-208">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c5841-208">See Also</span></span>  
 <span data-ttu-id="c5841-209">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c5841-209">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="c5841-210">[Sécurité de transport pour la mise en miroir de bases de données et les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="c5841-210">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="c5841-211">[Configuration de la mise en miroir d’une base de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c5841-211">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="c5841-212">[Sauvegarder et restaurer des catalogues et des index de recherche en texte intégral](../../relational-databases/indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="c5841-212">[Back Up and Restore Full-Text Catalogs and Indexes](../../relational-databases/indexes/indexes.md) </span></span>  
 <span data-ttu-id="c5841-213">[Mise en miroir de bases de données et catalogues de texte intégral &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c5841-213">[Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span></span>  
 <span data-ttu-id="c5841-214">[Mise en miroir de bases de données et réplication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c5841-214">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="c5841-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5841-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="c5841-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5841-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="c5841-217">Arguments RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5841-217">RESTORE Arguments &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-arguments-transact-sql)  
  
  
