---
title: Préparer manuellement une base de données secondaire pour un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.configsecondarydbs.f1
- sql12.swb.availabilitygroup.preparedbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 9f2feb3c-ea9b-4992-8202-2aeed4f9a6dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3da3f7332bdabce65785b2844157dd4639389254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603638"
---
# <a name="manually-prepare-a-secondary-database-for-an-availability-group-sql-server"></a><span data-ttu-id="5c900-102">Préparer manuellement une base de données secondaire pour un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5c900-102">Manually Prepare a Secondary Database for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="5c900-103">Cette rubrique explique comment préparer une base de données secondaire pour un groupe de disponibilité AlwaysOn dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c900-103">This topic describes how to prepare a secondary database for an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="5c900-104">La préparation d'une base de données secondaire s'effectue en deux étapes : (1) restauration d'une sauvegarde de base de données récente de la base de données primaire et des sauvegardes de journaux suivantes sur chaque instance de serveur qui héberge le réplica secondaire, à l'aide de RESTORE WITH NORECOVERY, et (2) attachement de la base de données restaurée au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="5c900-104">Preparing a secondary database requires two steps: (1) restoring a recent database backup of the primary database and subsequent log backups onto each server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY, and (2) joining the restored database to the availability group.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="5c900-105">Si vous disposez d'une configuration de copie des journaux de transaction, vous pouvez peut-être convertir la base de données principale pour la copie des journaux de transaction et une ou plusieurs de ses bases de données secondaires en base de données principale AlwaysOn et une ou plusieurs bases de données secondaires AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="5c900-105">If you have an existing log shipping configuration, you might be able to convert the log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and one or more AlwaysOn secondary databases.</span></span> <span data-ttu-id="5c900-106">Pour plus d’informations, consultez [Configuration requise pour la migration de la copie des journaux de session vers groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5c900-106">For more information, see [Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span></span>  
  
-   <span data-ttu-id="5c900-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5c900-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5c900-108">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="5c900-108">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="5c900-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="5c900-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5c900-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5c900-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5c900-111">**Pour préparer une base de données secondaire, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5c900-111">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="5c900-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c900-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5c900-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c900-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="5c900-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c900-114">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="5c900-115">Tâches connexes de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="5c900-115">Related Backup and Restore Tasks</span></span>](#RelatedTasks)  
  
-   <span data-ttu-id="5c900-116">**Suivi :** [Après avoir préparé une base de données secondaire](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5c900-116">**Follow Up:** [After Preparing a Secondary Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5c900-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5c900-117">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="5c900-118">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="5c900-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="5c900-119">Assurez-vous que le système dans lequel vous envisagez de placer la base de données possède un lecteur de disque avec suffisamment d'espace pour les bases de données secondaires.</span><span class="sxs-lookup"><span data-stu-id="5c900-119">Make sure that the system where you plan to place database possesses a disk drive with sufficient space for the secondary databases.</span></span>  
  
-   <span data-ttu-id="5c900-120">Le nom de la base de données secondaire doit être identique au nom de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-120">The name of the secondary database must be the same as the name of the primary database.</span></span>  
  
-   <span data-ttu-id="5c900-121">Utilisez RESTORE WITH NORECOVERY pour chaque opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="5c900-121">Use RESTORE WITH NORECOVERY for every restore operation.</span></span>  
  
-   <span data-ttu-id="5c900-122">Si la base de données secondaire doit résider sur un chemin d'accès de fichier différent (lettre de lecteur incluse) de celui de la base de données primaire, la commande de restauration doit également utiliser l'option WITH MOVE pour chacun des fichiers de base de données afin de les spécifier au chemin d'accès de la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-122">If the secondary database needs to reside on a different file path (including the drive letter) than the primary database, the restore command must also use the WITH MOVE option for each of the database files to specify them to the path of the secondary database.</span></span>  
  
-   <span data-ttu-id="5c900-123">Si vous restaurez le groupe de fichiers de base de données par groupe de fichiers, veillez à restaurer l'intégralité de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5c900-123">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
-   <span data-ttu-id="5c900-124">Après la restauration de la base de données, vous devez restaurer (WITH NORECOVERY) chaque sauvegarde de journal créée depuis la dernière sauvegarde de données restaurée.</span><span class="sxs-lookup"><span data-stu-id="5c900-124">After restoring the database, you must restore (WITH NORECOVERY) every log backup created since the last restored data backup.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5c900-125">Recommandations</span><span class="sxs-lookup"><span data-stu-id="5c900-125">Recommendations</span></span>  
  
-   <span data-ttu-id="5c900-126">Sur les instances autonomes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], nous recommandons, si possible, que le chemin d'accès au fichier (y compris la lettre de lecteur) d'une base de données secondaire particulière soit identique au chemin d'accès de la base de données primaire correspondante.</span><span class="sxs-lookup"><span data-stu-id="5c900-126">On stand-alone instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], we recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span> <span data-ttu-id="5c900-127">Cela est dû au fait que, si vous déplacez les fichiers de base de données lors de la création d'une base de données secondaire, une opération ultérieure d'ajout de fichier peut échouer sur la base de données secondaire et provoquer l'interruption de la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-127">This is because if you move the database files when creating a secondary database, a later add-file operation might fail on the secondary database and cause the secondary database to be suspended.</span></span>  
  
-   <span data-ttu-id="5c900-128">Avant de préparer vos bases de données secondaires, il est fortement recommandé d'interrompre les sauvegardes de fichiers journaux planifiées sur les bases de données dans le groupe de disponibilité jusqu'à ce que l'initialisation des réplicas secondaires soit terminée.</span><span class="sxs-lookup"><span data-stu-id="5c900-128">Before preparing your secondary databases, we strongly recommend that you suspend scheduled log backups on the databases in the availability group until the initialization of secondary replicas has completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5c900-129">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5c900-129">Security</span></span>  
 <span data-ttu-id="5c900-130">Lorsqu’une base de données est sauvegardée, la valeur OFF est attribuée à la [Propriété Trustworthy de la base de données](../../../relational-databases/security/trustworthy-database-property.md) .</span><span class="sxs-lookup"><span data-stu-id="5c900-130">When a database is backed up, the [TRUSTWORTHY database property](../../../relational-databases/security/trustworthy-database-property.md) is set to OFF.</span></span> <span data-ttu-id="5c900-131">Par conséquent, la propriété TRUSTWORTHY d'une base de données nouvellement restaurée a toujours la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="5c900-131">Therefore, TRUSTWORTHY is always OFF on a newly restored database.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5c900-132">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5c900-132">Permissions</span></span>  
 <span data-ttu-id="5c900-133">Les autorisations BACKUP DATABASE et BACKUP LOG reviennent par défaut aux membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="5c900-133">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span> <span data-ttu-id="5c900-134">Pour plus d’informations, consultez [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5c900-134">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="5c900-135">Lorsque la base de données en cours de restauration n'existe pas dans l'instance de serveur, l'instruction RESTORE nécessite des autorisations CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="5c900-135">When the database being restored does not exist on the server instance, the RESTORE statement requires CREATE DATABASE permissions.</span></span> <span data-ttu-id="5c900-136">Pour plus d’informations, consultez [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5c900-136">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5c900-137">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c900-137">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c900-138"> Si les chemins d'accès de fichier de sauvegarde et de restauration sont identiques entre l'instance de serveur qui héberge le réplica principal et chaque instance qui héberge un réplica secondaire, vous devriez être en mesure de créer des bases de données secondaires à l'aide de l' [Assistant Nouveau groupe de disponibilité](use-the-availability-group-wizard-sql-server-management-studio.md), l' [Assistant Ajouter un réplica au groupe de disponibilité](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)ou l' [Assistant Ajouter une base de données au groupe de disponibilité](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5c900-138">If the backup and restore file paths are identical between the server instance that hosts the primary replica and every instance that hosts a secondary replica, you should be able create secondary databases by using [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md).</span></span>  
  
 <span data-ttu-id="5c900-139">**Pour préparer une base de données secondaire**</span><span class="sxs-lookup"><span data-stu-id="5c900-139">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="5c900-140">À moins d'avoir déjà une sauvegarde de base de données récente de la base de données primaire, créez une nouvelle sauvegarde complète ou différentielle de base de données.</span><span class="sxs-lookup"><span data-stu-id="5c900-140">Unless you already have a recent database backup of the primary database, create a new full or differential database backup.</span></span> <span data-ttu-id="5c900-141">À titre de recommandation, placez cette sauvegarde et toutes les sauvegardes du journal réalisées ultérieurement sur le partage réseau recommandé.</span><span class="sxs-lookup"><span data-stu-id="5c900-141">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="5c900-142">Créez au moins une nouvelle sauvegarde du journal de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-142">Create at least one new log backup of the primary database.</span></span>  
  
3.  <span data-ttu-id="5c900-143">Sur l'instance de serveur qui héberge le réplica secondaire, restaurez la sauvegarde complète de la base de données primaire (et éventuellement une sauvegarde différentielle) suivies de toutes les sauvegardes de journaux suivantes.</span><span class="sxs-lookup"><span data-stu-id="5c900-143">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by any subsequent log backups.</span></span>  
  
     <span data-ttu-id="5c900-144">Dans la page **Options de RESTORE DATABASE** , sélectionnez **Laisser la base de données non opérationnelle, et ne pas restaurer les transactions non validées. Les journaux des transactions supplémentaires peuvent être restaurés. (RESTORE WITH NORECOVERY)**.</span><span class="sxs-lookup"><span data-stu-id="5c900-144">On the **RESTORE DATABASEOptions** page, select **Leave the database non-operational, and do not roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**.</span></span>  
  
     <span data-ttu-id="5c900-145">Si les chemins d'accès de fichier de la base de données primaire et de la base de données secondaire diffèrent, par exemple, si la base de données primaire se trouve sur le lecteur « F: », mais que l'instance de serveur qui héberge le réplica secondaire ne dispose pas de lecteur F:, incluez l'option MOVE dans votre clause WITH.</span><span class="sxs-lookup"><span data-stu-id="5c900-145">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
4.  <span data-ttu-id="5c900-146">Pour terminer la configuration de la base de données secondaire, vous devez attacher la base de données secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="5c900-146">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="5c900-147">Pour plus d’informations, consultez [Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5c900-147">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c900-148">Pour plus d'informations sur l'exécution de ces opérations de sauvegarde et de restauration, consultez [Tâches connexes de sauvegarde et de restauration](#RelatedTasks), plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="5c900-148">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this section.</span></span>  
  
###  <a name="related-backup-and-restore-tasks"></a><a name="RelatedTasks"></a><span data-ttu-id="5c900-149">Tâches de sauvegarde et de restauration connexes</span><span class="sxs-lookup"><span data-stu-id="5c900-149">Related Backup and Restore Tasks</span></span>  
 <span data-ttu-id="5c900-150">**Pour créer une sauvegarde de base de données**</span><span class="sxs-lookup"><span data-stu-id="5c900-150">**To create a database backup**</span></span>  
  
-   [<span data-ttu-id="5c900-151">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c900-151">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="5c900-152">Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c900-152">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="5c900-153">**Pour créer une sauvegarde du journal**</span><span class="sxs-lookup"><span data-stu-id="5c900-153">**To create a log backup**</span></span>  
  
-   [<span data-ttu-id="5c900-154">Sauvegarder un journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c900-154">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
 <span data-ttu-id="5c900-155">**Pour restaurer des sauvegardes**</span><span class="sxs-lookup"><span data-stu-id="5c900-155">**To restore backups**</span></span>  
  
-   [<span data-ttu-id="5c900-156">Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5c900-156">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="5c900-157">Restaurer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c900-157">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="5c900-158">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c900-158">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="5c900-159">Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c900-159">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5c900-160">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c900-160">Using Transact-SQL</span></span>  
 <span data-ttu-id="5c900-161">**Pour préparer une base de données secondaire**</span><span class="sxs-lookup"><span data-stu-id="5c900-161">**To prepare a secondary database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c900-162">Pour obtenir un exemple de cette procédure, consultez [Exemple (Transact-SQL)](#ExampleTsql), plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5c900-162">For an example of this procedure, see [Example (Transact-SQL)](#ExampleTsql), earlier in this topic.</span></span>  
  
1.  <span data-ttu-id="5c900-163">À moins de disposer d'une sauvegarde complète récente de la base de données primaire, connectez-vous à l'instance de serveur qui héberge le réplica principal et créez une sauvegarde complète de base de données.</span><span class="sxs-lookup"><span data-stu-id="5c900-163">Unless you have a recent full backup of the primary database, connect to the server instance that hosts the primary replica and create a full database backup.</span></span> <span data-ttu-id="5c900-164">À titre de recommandation, placez cette sauvegarde et toutes les sauvegardes du journal réalisées ultérieurement sur le partage réseau recommandé.</span><span class="sxs-lookup"><span data-stu-id="5c900-164">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="5c900-165">Sur l'instance de serveur qui héberge le réplica secondaire, restaurez la sauvegarde complète de la base de données primaire (et éventuellement une sauvegarde différentielle) suivies de toutes les sauvegardes de journaux suivantes.</span><span class="sxs-lookup"><span data-stu-id="5c900-165">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by all subsequent log backups.</span></span> <span data-ttu-id="5c900-166">Utilisez WITH NORECOVERY pour chaque opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="5c900-166">Use WITH NORECOVERY for every restore operation.</span></span>  
  
     <span data-ttu-id="5c900-167">Si les chemins d'accès de fichier de la base de données primaire et de la base de données secondaire diffèrent, par exemple, si la base de données primaire se trouve sur le lecteur « F: », mais que l'instance de serveur qui héberge le réplica secondaire ne dispose pas de lecteur F:, incluez l'option MOVE dans votre clause WITH.</span><span class="sxs-lookup"><span data-stu-id="5c900-167">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
3.  <span data-ttu-id="5c900-168">Si des sauvegardes de journal ont été effectuées sur la base de données primaire après la sauvegarde du journal requise, vous devez également les copier sur l'instance de serveur qui héberge le réplica secondaire et appliquer chacune de ces sauvegardes de journal à la base de données secondaire, en commençant par la première et en utilisant systématiquement RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5c900-168">If any log backups have been taken on the primary database since the required log backup, you must also copy these to the server instance that hosts the secondary replica and apply each of those log backups to the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c900-169">Une sauvegarde du journal n'existerait pas si la base de données primaire venait d'être créée et qu'aucune sauvegarde du journal n'avait encore été réalisée ou que le mode de récupération venait d'être modifié de simple à complet.</span><span class="sxs-lookup"><span data-stu-id="5c900-169">A log backup would not exist if the primary database has just been created and no log backup has been taken yet or if the recovery model has just been changed from simple to full.</span></span>  
  
4.  <span data-ttu-id="5c900-170">Pour terminer la configuration de la base de données secondaire, vous devez attacher la base de données secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="5c900-170">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="5c900-171">Pour plus d’informations, consultez [Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5c900-171">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c900-172">Pour plus d'informations sur l'exécution de ces opérations de sauvegarde et de restauration, consultez [Tâches connexes de sauvegarde et de restauration](#RelatedTasks), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5c900-172">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this topic.</span></span>  
  
###  <a name="transact-sql-example"></a><a name="ExampleTsql"></a><span data-ttu-id="5c900-173">Exemple Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c900-173">Transact-SQL Example</span></span>  
 <span data-ttu-id="5c900-174">L'exemple suivant prépare une base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-174">The following example prepares a secondary database.</span></span> <span data-ttu-id="5c900-175">L'exemple suivant utilise la base de données d'exemple [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] qui emploie par défaut le mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="5c900-175">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="5c900-176">Pour utiliser la base de données [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , modifiez-la afin qu'elle utilise le mode de récupération complète :</span><span class="sxs-lookup"><span data-stu-id="5c900-176">To use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```sql
    USE master;  
    GO  
    ALTER DATABASE MyDB1   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="5c900-177">Après avoir changé le mode de récupération de la base de données de SIMPLE à FULL, créez une sauvegarde complète qui pourra être utilisée pour créer la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-177">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the secondary database.</span></span> <span data-ttu-id="5c900-178">Dans la mesure où le mode de récupération vient d'être modifié, l'option WITH FORMAT est spécifiée pour créer un nouveau support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5c900-178">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="5c900-179">Il peut se révéler utile de séparer les sauvegardes effectuées en mode de récupération complète des sauvegardes préalablement effectuées en mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="5c900-179">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="5c900-180">Pour les besoins de cet exemple, le fichier de sauvegarde (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) est créé sur le même lecteur que la base de données.</span><span class="sxs-lookup"><span data-stu-id="5c900-180">For the purpose of this example, the backup file (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c900-181">Dans le cas d'une base de données de production, il est conseillé de toujours effectuer les sauvegardes sur une unité distincte.</span><span class="sxs-lookup"><span data-stu-id="5c900-181">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="5c900-182">Sur l'instance de serveur qui héberge le réplica principal (`INSTANCE01`), créez une sauvegarde complète de la base de données primaire comme suit :</span><span class="sxs-lookup"><span data-stu-id="5c900-182">On the server instance that hosts the primary replica (`INSTANCE01`), create a full backup of the primary database as follows:</span></span>  
  
    ```sql
    BACKUP DATABASE MyDB1   
        TO DISK = 'C:\MyDB1.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="5c900-183">Copiez la sauvegarde complète sur l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-183">Copy the full backup to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="5c900-184">Restaurez la sauvegarde complète, à l'aide de RESTORE WITH NORECOVERY, sur l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-184">Restore the full backup, using RESTORE WITH NORECOVERY, onto the server instance that hosts the secondary replica.</span></span> <span data-ttu-id="5c900-185">La commande de restauration varie selon que les chemins d'accès des bases de données primaire et secondaire sont identiques ou non.</span><span class="sxs-lookup"><span data-stu-id="5c900-185">The restore command depends on whether the paths of primary and secondary databases are identical.</span></span>  
  
    -   <span data-ttu-id="5c900-186">**Si les chemins d'accès sont identiques :**</span><span class="sxs-lookup"><span data-stu-id="5c900-186">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="5c900-187">Sur l'ordinateur qui héberge le réplica secondaire, restaurez la sauvegarde complète comme suit :</span><span class="sxs-lookup"><span data-stu-id="5c900-187">On the computer that hosts the secondary replica, restore the full backup as follows:</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1   
            FROM DISK = 'C:\MyDB1.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="5c900-188">**Si les chemins d'accès sont différents :**</span><span class="sxs-lookup"><span data-stu-id="5c900-188">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="5c900-189">Si le chemin d'accès de la base de données secondaire n'est pas le même que celui de la base de données primaire (lettres de lecteurs différentes, par exemple), la création de la base de données secondaire requiert l'intégration d'une clause MOVE dans l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="5c900-189">If the path of the secondary database differs from the path of the primary database (for instance, their drive letters differ), creating the secondary database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="5c900-190">Si les chemins d'accès des bases de données primaire et secondaire diffèrent, vous ne pouvez pas ajouter de fichier.</span><span class="sxs-lookup"><span data-stu-id="5c900-190">If the path names of the primary and secondary databases differ, you cannot add a file.</span></span> <span data-ttu-id="5c900-191">La raison tient à la réception du journal pour l'opération d'ajout de fichier, puisque l'instance de serveur du réplica secondaire tente de placer le nouveau fichier dans le même chemin d'accès que celui utilisé par la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-191">This is because on receiving the log for the add file operation, the server instance of the secondary replica attempts to place the new file in the same path as used by the primary database.</span></span>  
  
         <span data-ttu-id="5c900-192">Par exemple, la commande ci-dessous restaure une sauvegarde d'une base de données primaire qui réside dans le répertoire de données de l'instance par défaut de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="5c900-192">For example, the following command restores a backup of a primary database that resides in the data directory of the default instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span></span> <span data-ttu-id="5c900-193">L’opération de restauration de la base de données doit déplacer la base de données dans le répertoire de données d’une instance distante de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] nommée (*AlwaysOn1*), qui héberge le réplica secondaire sur un autre nœud de cluster.</span><span class="sxs-lookup"><span data-stu-id="5c900-193">The restore database operation must move the database to the data directory of a remote instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] named  (*AlwaysOn1*), which hosts the secondary replica on another cluster node.</span></span> <span data-ttu-id="5c900-194">Là, les données et les fichiers journaux sont restaurés dans le répertoire *C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA* .</span><span class="sxs-lookup"><span data-stu-id="5c900-194">There, the data and log files are restored to the *C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA* directory .</span></span> <span data-ttu-id="5c900-195">L'opération de restauration utilise WITH NORECOVERY, afin de laisser la base de données secondaire dans la base de données de restauration.</span><span class="sxs-lookup"><span data-stu-id="5c900-195">The restore operation uses WITH NORECOVERY, to leave the secondary database in the restoring database.</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1  
          FROM DISK='C:\MyDB1.bak'  
         WITH NORECOVERY,   
            MOVE 'MyDB1_Data' TO   
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.mdf',   
            MOVE 'MyDB1_Log' TO  
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="5c900-196">Après avoir restauré la sauvegarde complète, vous devez créer une sauvegarde du journal sur la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-196">After you restore the full backup, you must create a log backup on the primary database.</span></span> <span data-ttu-id="5c900-197">Par exemple, l’instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] suivante sauvegarde le journal dans un fichier de sauvegarde nommé *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="5c900-197">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement backs up the log to the a backup file named *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    BACKUP LOG MyDB1   
      TO DISK = 'E:\MyDB1_log.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="5c900-198">Avant de pouvoir joindre la base de données au réplica secondaire, vous devez appliquer la sauvegarde du journal requise (et toutes les sauvegardes de journal ultérieures).</span><span class="sxs-lookup"><span data-stu-id="5c900-198">Before you can join the database to the secondary replica, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="5c900-199">Par exemple, l’instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] suivante restaure le premier journal à partir de *C:\MyDB1.bak*:</span><span class="sxs-lookup"><span data-stu-id="5c900-199">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores the first log from *C:\MyDB1.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="5c900-200">Si des sauvegardes de journal supplémentaires se produisent avant la jointure de la base de données au réplica secondaire, vous devez également restaurer toutes ces sauvegardes de journal, dans l'ordre, dans l'instance de serveur qui héberge le réplica secondaire à l'aide de RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5c900-200">If any additional log backups occur before the database joins the secondary replica, you must also restore all of those log backups, in sequence, to the server instance that hosts the secondary replica using RESTORE WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="5c900-201">Par exemple, l’instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] suivante restaure deux journaux supplémentaires à partir de *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="5c900-201">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores two additional logs from *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="5c900-202">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c900-202">Using PowerShell</span></span>  
 <span data-ttu-id="5c900-203">**Pour préparer une base de données secondaire**</span><span class="sxs-lookup"><span data-stu-id="5c900-203">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="5c900-204">Si vous devez créer une sauvegarde récente de la base de données primaire, accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="5c900-204">If you need to create a recent backup of the primary database, change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="5c900-205">Utilisez l'applet de commande `Backup-SqlDatabase` pour créer chacune des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="5c900-205">Use the `Backup-SqlDatabase` cmdlet to create each of the backups.</span></span>  
  
3.  <span data-ttu-id="5c900-206">Remplacez le répertoire (`cd`) par l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="5c900-206">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="5c900-207">Pour restaurer la base de données et les sauvegardes de journaux de chaque base de données primaire, utilisez l'applet de commande `restore-SqlDatabase`, en spécifiant le paramètre de restauration `NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="5c900-207">To restore the database and log backups of each primary database, use the `restore-SqlDatabase` cmdlet, specifying the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="5c900-208">Si les chemins d'accès de fichier diffèrent entre les ordinateurs qui hébergent le réplica principal et le réplica secondaire cible, utilisez également le paramètre de restauration `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="5c900-208">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c900-209">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c900-209">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="5c900-210">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5c900-210">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
5.  <span data-ttu-id="5c900-211">Pour terminer la configuration de la base de données secondaire, vous devez l'attacher au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="5c900-211">To complete configuration of the secondary database, you need to join it to the availability group.</span></span> <span data-ttu-id="5c900-212">Pour plus d’informations, consultez [Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5c900-212">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="5c900-213">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5c900-213">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="5c900-214">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c900-214">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="sample-backup-and-restore-script-and-command"></a><a name="ExamplePSscript"></a><span data-ttu-id="5c900-215">Exemple de commande et de script de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="5c900-215">Sample Backup and Restore Script and Command</span></span>  
 <span data-ttu-id="5c900-216">Les commandes PowerShell suivantes effectuent une sauvegarde complète de base de données et de son journal des transactions dans un partage réseau et restaurent ces sauvegardes depuis ce partage.</span><span class="sxs-lookup"><span data-stu-id="5c900-216">The following PowerShell commands back up a full database backup and transaction log to a network share and restore those backups from that share.</span></span> <span data-ttu-id="5c900-217">Dans cet exemple, on suppose que le chemin d'accès de fichier dans lequel la base de données est restaurée est identique au chemin d'accès de fichier dans lequel la base de données a été sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="5c900-217">This example assumes that the file path to which the database is restored is the same as the file path on which the database was backed up.</span></span>  
  
```powershell
# Create database backup  
Backup-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -ServerInstance "SourceMachine\Instance"  
# Create log backup  
Backup-SqlDatabase -Database "MyDB1" -BackupAction "Log" -BackupFile "\\share\backups\MyDB1.trn" -ServerInstance "SourceMachine\Instance"  
# Restore database backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -NoRecovery -ServerInstance "DestinationMachine\Instance"  
# Restore log backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.trn" -RestoreAction "Log" -NoRecovery -ServerInstance "DestinationMachine\Instance"
```  
  
##  <a name="follow-up-after-preparing-a-secondary-database"></a><a name="FollowUp"></a><span data-ttu-id="5c900-218">Suivi : après avoir préparé une base de données secondaire</span><span class="sxs-lookup"><span data-stu-id="5c900-218">Follow Up: After Preparing a Secondary Database</span></span>  
 <span data-ttu-id="5c900-219">Pour terminer la configuration de la base de données secondaire, attachez la base de données nouvellement restaurée au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="5c900-219">To complete configuration of the secondary database, join the newly restored database to the availability group.</span></span> <span data-ttu-id="5c900-220">Pour plus d’informations, consultez [Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5c900-220">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c900-221">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c900-221">See Also</span></span>  
 <span data-ttu-id="5c900-222">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5c900-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="5c900-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5c900-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="5c900-224">[Arguments RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5c900-224">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="5c900-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5c900-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="5c900-226">Résoudre les problèmes liés à l’échec d’une opération d’ajout de fichier &#40;groupes de disponibilité AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="5c900-226">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
