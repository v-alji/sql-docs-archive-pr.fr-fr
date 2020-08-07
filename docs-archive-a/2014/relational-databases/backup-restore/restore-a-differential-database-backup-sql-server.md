---
title: Restaurer une sauvegarde différentielle de base de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- restoring databases [SQL Server], full differential backups
- database backups [SQL Server], full differential backups
- database restores [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
ms.assetid: 0dd971a4-ee38-4dd3-9f30-ef77fc58dd11
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a8eab18d84efc1a990715e0d5488085252f93a7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612419"
---
# <a name="restore-a-differential-database-backup-sql-server"></a><span data-ttu-id="1886d-102">Restaurer une sauvegarde différentielle de base de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1886d-102">Restore a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="1886d-103">Cette rubrique explique comment restaurer une sauvegarde différentielle de base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1886d-103">This topic describes how to restore a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1886d-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="1886d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1886d-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="1886d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1886d-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="1886d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1886d-107">Composants requis</span><span class="sxs-lookup"><span data-stu-id="1886d-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="1886d-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1886d-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1886d-109">**Pour restaurer une sauvegarde différentielle de base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="1886d-109">**To restore a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="1886d-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1886d-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1886d-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1886d-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="1886d-112">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="1886d-112">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1886d-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="1886d-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1886d-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="1886d-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1886d-115">La commande RESTORE n'est pas autorisée dans une transaction explicite ou implicite.</span><span class="sxs-lookup"><span data-stu-id="1886d-115">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="1886d-116">Les sauvegardes créées avec une version plus récente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peuvent pas être restaurées dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1886d-116">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1886d-117">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vous pouvez restaurer une base de données utilisateur à partir d'une sauvegarde de base de données créée à l'aide de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="1886d-117">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can restore a user database from a database backup that was created by using [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1886d-118">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1886d-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="1886d-119">Que vous soyez en mode de récupération complète ou en mode de récupération utilisant les journaux de transactions, pour pouvoir restaurer une base de données, vous devez d'abord sauvegarder le journal des transactions actif (appelé fin du journal).</span><span class="sxs-lookup"><span data-stu-id="1886d-119">Under the full or bulk-logged recovery model, before you can restore a database, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="1886d-120">Pour plus d’informations, consultez [Sauvegarder un journal des transactions &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1886d-120">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1886d-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1886d-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1886d-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="1886d-122">Permissions</span></span>  
 <span data-ttu-id="1886d-123">Si la base de données restaurée n'existe pas, l'utilisateur doit posséder les autorisations CREATE DATABASE afin de pouvoir exécuter RESTORE.</span><span class="sxs-lookup"><span data-stu-id="1886d-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="1886d-124">Si la base de données existe, les autorisations RESTORE reviennent par défaut aux membres des rôles serveur fixe **sysadmin** et **dbcreator** et au propriétaire (**dbo**) de la base de données (pour l’option FROM DATABASE_SNAPSHOT, la base de données existe toujours).</span><span class="sxs-lookup"><span data-stu-id="1886d-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="1886d-125">Les autorisations RESTORE sont attribuées aux rôles dont les informations d'appartenance sont toujours immédiatement accessibles à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="1886d-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="1886d-126">Étant donné que l’appartenance au rôle de base de données fixe ne peut être contrôlée que quand la base de données est accessible et non endommagée, ce qui n’est pas toujours le cas lorsque RESTORE est exécuté, les membres du rôle de base de données fixe **db_owner** ne détiennent pas d’autorisations RESTORE.</span><span class="sxs-lookup"><span data-stu-id="1886d-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1886d-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1886d-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="1886d-128">Pour restaurer une sauvegarde différentielle de base de données</span><span class="sxs-lookup"><span data-stu-id="1886d-128">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="1886d-129">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="1886d-129">After you connect to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1886d-130">Développez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="1886d-130">Expand **Databases**.</span></span> <span data-ttu-id="1886d-131">Selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système**et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="1886d-131">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="1886d-132">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="1886d-132">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span>  
  
4.  <span data-ttu-id="1886d-133">Dans la page **Général** , utilisez la section **Source** pour préciser la source et l'emplacement des jeux de sauvegarde à restaurer.</span><span class="sxs-lookup"><span data-stu-id="1886d-133">On the **General** page, use the **Source** section to specify the source and location of the backup sets to restore.</span></span> <span data-ttu-id="1886d-134">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1886d-134">Select one of the following options:</span></span>  
  
    -   <span data-ttu-id="1886d-135">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="1886d-135">**Database**</span></span>  
  
         <span data-ttu-id="1886d-136">Sélectionnez la base de données à restaurer dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="1886d-136">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="1886d-137">La liste contient uniquement les bases de données qui ont été sauvegardées selon l'historique de sauvegarde **msdb** .</span><span class="sxs-lookup"><span data-stu-id="1886d-137">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1886d-138">Si la sauvegarde est prise à partir d'un serveur différent, le serveur de destination ne disposera pas des informations d'historique de sauvegarde pour la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1886d-138">If the backup is taken from a different server, the destination server will not have the backup history information for the specified database.</span></span> <span data-ttu-id="1886d-139">Dans ce cas, sélectionnez **Unité** pour spécifier manuellement le fichier ou l'unité à restaurer.</span><span class="sxs-lookup"><span data-stu-id="1886d-139">In this case, select **Device** to manually specify the file or device to restore.</span></span>  
  
    -   <span data-ttu-id="1886d-140">**Appareil**</span><span class="sxs-lookup"><span data-stu-id="1886d-140">**Device**</span></span>  
  
         <span data-ttu-id="1886d-141">Cliquez sur le bouton Parcourir ( **...** ) pour ouvrir la boîte de dialogue **Sélectionner les unités de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="1886d-141">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="1886d-142">Dans la zone **Type du média de sauvegarde** , sélectionnez l'un des types d'unités proposés.</span><span class="sxs-lookup"><span data-stu-id="1886d-142">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="1886d-143">Pour sélectionner une ou plusieurs unités pour la zone **Support de sauvegarde** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1886d-143">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="1886d-144">Après avoir ajouté les unités souhaitées à la zone de liste **Support de sauvegarde** , cliquez sur **OK** pour revenir à la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="1886d-144">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
         <span data-ttu-id="1886d-145">Dans la zone de liste **Source : Appareil : Base de données**, sélectionnez le nom de la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="1886d-145">In the **Source: Device: Database** list box, select the name of the database which should be restored.</span></span>  
  
         <span data-ttu-id="1886d-146">**Remarque** Cette liste n'est disponible que lorsque **Unité** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1886d-146">**Note** This list is only available when **Device** is selected.</span></span> <span data-ttu-id="1886d-147">Seules les bases de données qui ont des copies de sauvegarde sur l'unité sélectionnée seront disponibles.</span><span class="sxs-lookup"><span data-stu-id="1886d-147">Only databases that have backups on the selected device will be available.</span></span>  
  
5.  <span data-ttu-id="1886d-148">Dans la section **Destination** , la zone **Base de données** est automatiquement renseignée avec le nom de la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="1886d-148">In the **Destination** section, the **Database** box is automatically populated with the name of the database to be restored.</span></span> <span data-ttu-id="1886d-149">Pour changer le nom de la base de données, entrez le nouveau nom dans la zone **Base de données** .</span><span class="sxs-lookup"><span data-stu-id="1886d-149">To change the name of the database, enter the new name in the **Database** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1886d-150">Pour arrêter la restauration à un moment précis, cliquez sur **Chronologie** pour accéder à la boîte de dialogue **Chronologie de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="1886d-150">To stop the restore at a specific point in time, click **Timeline** to access the **Backup Timeline** dialog box.</span></span> <span data-ttu-id="1886d-151">Pour obtenir de l’aide concernant l’arrêt d’une restauration de base de données à un moment précis dans le temps, consultez [Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="1886d-151">For help with stopping a database restore at a specific point in time, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
6.  <span data-ttu-id="1886d-152">Dans la grille **Jeux de sauvegarde à restaurer** , sélectionnez les sauvegardes par la sauvegarde différentielle que vous souhaitez restaurer.</span><span class="sxs-lookup"><span data-stu-id="1886d-152">In the **Backup sets to restore** grid, select the backups through the differential backup that you wish to restore.</span></span>  
  
     <span data-ttu-id="1886d-153">Pour plus d’informations sur les colonnes de la grille **Jeux de sauvegarde à restaurer** , consultez [Restaurer la base de données &#40;page Général&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="1886d-153">For information about the columns in the **Backup sets to restore** grid, see [Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
7.  <span data-ttu-id="1886d-154">Dans la page **Options** , dans le volet **Options de restauration** , vous pouvez choisir les options suivantes si elles s'appliquent à votre situation :</span><span class="sxs-lookup"><span data-stu-id="1886d-154">On the **Options** page, in the **Restore options** panel, you can select any of the following options, if appropriate for your situation:</span></span>  
  
    -   <span data-ttu-id="1886d-155">**Remplacer la base de données existante (WITH REPLACE)**</span><span class="sxs-lookup"><span data-stu-id="1886d-155">**Overwrite the existing database (WITH REPLACE)**</span></span>  
  
    -   <span data-ttu-id="1886d-156">**Conserver les paramètres de la réplication (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="1886d-156">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
    -   <span data-ttu-id="1886d-157">**Demander confirmation avant chaque restauration de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="1886d-157">**Prompt before restoring each backup**</span></span>  
  
    -   <span data-ttu-id="1886d-158">**Restreindre l'accès à la base de données restaurée (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="1886d-158">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
     <span data-ttu-id="1886d-159">Pour plus d’informations sur ces options, consultez [Restaurer la base de données &#40;page Options&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="1886d-159">For more information about these options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
8.  <span data-ttu-id="1886d-160">Sélectionnez une option pour la zone **État de récupération** .</span><span class="sxs-lookup"><span data-stu-id="1886d-160">Select an option for the **Recovery state** box.</span></span> <span data-ttu-id="1886d-161">Cette zone détermine l'état de la base de données à l'issue de l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="1886d-161">This box determines the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="1886d-162">**RESTORE WITH RECOVERY** est le comportement par défaut qui laisse la base de données opérationnelle en annulant les transactions non validées.</span><span class="sxs-lookup"><span data-stu-id="1886d-162">**RESTORE WITH RECOVERY** is the default behavior which leaves the database ready for use by rolling back the uncommitted transactions.</span></span> <span data-ttu-id="1886d-163">Les journaux des transactions supplémentaires ne peuvent pas être restaurés.</span><span class="sxs-lookup"><span data-stu-id="1886d-163">Additional transaction logs cannot be restored.</span></span> <span data-ttu-id="1886d-164">Choisissez cette option si vous restaurez toutes les sauvegardes nécessaires maintenant.</span><span class="sxs-lookup"><span data-stu-id="1886d-164">Select this option if you are restoring all of the necessary backups now.</span></span>  
  
    -   <span data-ttu-id="1886d-165">**RESTORE WITH NORECOVERY** qui laisse la base de données non opérationnelle et n’annule pas les transactions non validées.</span><span class="sxs-lookup"><span data-stu-id="1886d-165">**RESTORE WITH NORECOVERY** which leaves the database non-operational, and does not roll back the uncommitted transactions.</span></span> <span data-ttu-id="1886d-166">Les journaux des transactions supplémentaires peuvent être restaurés.</span><span class="sxs-lookup"><span data-stu-id="1886d-166">Additional transaction logs can be restored.</span></span> <span data-ttu-id="1886d-167">La base de données ne peut pas être utilisée tant qu'elle n'est pas récupérée.</span><span class="sxs-lookup"><span data-stu-id="1886d-167">The database cannot be used until it is recovered.</span></span>  
  
    -   <span data-ttu-id="1886d-168">**RESTORE WITH STANDBY** qui laisse la base de données en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="1886d-168">**RESTORE WITH STANDBY** which leaves the database in read-only mode.</span></span> <span data-ttu-id="1886d-169">Elle annule les transactions non validées, mais enregistre les actions d'annulation dans un fichier afin de rendre réversibles les effets de la récupération.</span><span class="sxs-lookup"><span data-stu-id="1886d-169">It undoes uncommitted transactions, but saves the undo actions in a standby file so that recovery effects can be reverted.</span></span>  
  
     <span data-ttu-id="1886d-170">Pour obtenir des descriptions des options, consultez [Restaurer la base de données &#40;page Options&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="1886d-170">For descriptions of the options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
9. <span data-ttu-id="1886d-171">Les opérations de restauration échoueront s'il existe des connexions actives à la base de données.</span><span class="sxs-lookup"><span data-stu-id="1886d-171">Restore operations will fail if there are active connections to the database.</span></span> <span data-ttu-id="1886d-172">Activez l'option **Fermer les connexions existantes** pour garantir que toutes les connexions actives entre [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et la base de données sont fermées.</span><span class="sxs-lookup"><span data-stu-id="1886d-172">Check the **Close existing connections option** to ensure that all active connections between [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and the database are closed.</span></span>  
  
10. <span data-ttu-id="1886d-173">Sélectionnez **Demander confirmation avant chaque restauration de sauvegarde** si vous souhaitez être invité entre chaque opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="1886d-173">Select **Prompt before restoring each backup** if you wish to be prompted between each restore operation.</span></span> <span data-ttu-id="1886d-174">Cela n'est généralement pas nécessaire à moins que la base de données ne soit volumineuse et que vous ne souhaitiez surveiller l'état de l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="1886d-174">This is not usually necessary unless the database is large and you wish to monitor the status of the restore operation.</span></span>  
  
11. <span data-ttu-id="1886d-175">Utilisez éventuellement la page **Fichiers** pour restaurer la base de données à un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="1886d-175">Optionally, use the **Files** page to restore the database to a new location.</span></span> <span data-ttu-id="1886d-176">Pour obtenir de l’aide concernant le déplacement d’une base de données, consultez [Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1886d-176">For help with moving a database, see [Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1886d-177">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1886d-177">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="1886d-178">Pour restaurer une sauvegarde différentielle de base de données</span><span class="sxs-lookup"><span data-stu-id="1886d-178">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="1886d-179">Exécutez l'instruction RESTORE DATABASE, en spécifiant la clause NORECOVERY, pour restaurer la sauvegarde complète de la base de données précédant la sauvegarde différentielle.</span><span class="sxs-lookup"><span data-stu-id="1886d-179">Execute the RESTORE DATABASE statement, specifying the NORECOVERY clause, to restore the full database backup that comes before the differential database backup.</span></span> <span data-ttu-id="1886d-180">Pour plus d’informations, consultez [Procédure : Restaurer une sauvegarde complète](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1886d-180">For more information, see [How to: Restore a Full Backup](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="1886d-181">Exécutez l'instruction RESTORE DATABASE pour restaurer la sauvegarde différentielle de la base de données, en spécifiant :</span><span class="sxs-lookup"><span data-stu-id="1886d-181">Execute the RESTORE DATABASE statement to restore the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="1886d-182">le nom de la base de données à laquelle s'applique la sauvegarde différentielle ;</span><span class="sxs-lookup"><span data-stu-id="1886d-182">The name of the database to which the differential database backup is applied.</span></span>  
  
    -   <span data-ttu-id="1886d-183">l’unité de sauvegarde à partir de laquelle la sauvegarde différentielle est restaurée ;</span><span class="sxs-lookup"><span data-stu-id="1886d-183">The backup device where the differential database backup is restored from.</span></span>  
  
    -   <span data-ttu-id="1886d-184">la clause NORECOVERY si vous devez appliquer des sauvegardes du journal des transactions après restauration de la sauvegarde différentielle.</span><span class="sxs-lookup"><span data-stu-id="1886d-184">The NORECOVERY clause if you have transaction log backups to apply after the differential database backup is restored.</span></span> <span data-ttu-id="1886d-185">Dans le cas contraire, spécifiez la clause RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1886d-185">Otherwise, specify the RECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="1886d-186">Avec le mode de restauration complète ou de récupération utilisant les journaux de transactions, la restauration d'une sauvegarde différentielle restaure la base de données au point où la sauvegarde différentielle a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="1886d-186">With the full or bulk-logged recovery model, restoring a differential database backup restores the database to the point at which the differential database backup was completed.</span></span> <span data-ttu-id="1886d-187">Pour restaurer jusqu'au point de défaillance, vous devez appliquer toutes les sauvegardes du journal des transactions créées après la dernière sauvegarde différentielle.</span><span class="sxs-lookup"><span data-stu-id="1886d-187">To recover to the point of failure, you must apply all transaction log backups created after the last differential database backup was created.</span></span> <span data-ttu-id="1886d-188">Pour plus d’informations, consultez [Appliquer les sauvegardes du journal de transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1886d-188">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="1886d-189">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1886d-189">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-restoring-a-differential-database-backup"></a><span data-ttu-id="1886d-190">R.</span><span class="sxs-lookup"><span data-stu-id="1886d-190">A.</span></span> <span data-ttu-id="1886d-191">Restauration d'une sauvegarde différentielle de base de données</span><span class="sxs-lookup"><span data-stu-id="1886d-191">Restoring a differential database backup</span></span>  
 <span data-ttu-id="1886d-192">Cet exemple illustre la restauration et la sauvegarde différentielle de la base de données `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="1886d-192">This example restores a database and differential database backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost, and restore full database,   
-- specifying the original full database backup and NORECOVERY,   
-- which allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   RECOVERY;  
GO  
```  
  
#### <a name="b-restoring-a-database-differential-database-and-transaction-log-backup"></a><span data-ttu-id="1886d-193">B.</span><span class="sxs-lookup"><span data-stu-id="1886d-193">B.</span></span> <span data-ttu-id="1886d-194">Restauration d'une base de données, d'une base de données différentielle et d'une sauvegarde du journal des transactions</span><span class="sxs-lookup"><span data-stu-id="1886d-194">Restoring a database, differential database, and transaction log backup</span></span>  
 <span data-ttu-id="1886d-195">Cet exemple illustre la restauration d'une base de données, la sauvegarde différentielle d'une base de données et la sauvegarde du journal des transactions de la base de données `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="1886d-195">This example restores a database, differential database, and transaction log backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost at this point. Now restore the full   
-- database. Specify the original full database backup and NORECOVERY.  
-- NORECOVERY allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   NORECOVERY;  
GO  
-- Now restore each transaction log backup created after  
-- the differential database backup.  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log1  
   WITH NORECOVERY;  
GO  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log2  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1886d-196">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="1886d-196">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1886d-197">Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1886d-197">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="1886d-198">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1886d-198">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="1886d-199"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1886d-199">See Also</span></span>  
 <span data-ttu-id="1886d-200">[Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1886d-200">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="1886d-201">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1886d-201">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
