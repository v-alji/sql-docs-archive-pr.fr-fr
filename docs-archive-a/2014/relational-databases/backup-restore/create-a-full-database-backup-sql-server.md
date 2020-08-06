---
title: Créer une sauvegarde complète de base de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], full backups
- backing up databases [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- database backups [SQL Server], SQL Server Management Studio
ms.assetid: 586561fc-dfbb-4842-84f8-204a9100a534
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f406464680a1669133dc87bdfb231c644d33fbdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708456"
---
# <a name="create-a-full-database-backup-sql-server"></a><span data-ttu-id="ba66b-102">Créer une sauvegarde complète de base de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ba66b-102">Create a Full Database Backup (SQL Server)</span></span>
  <span data-ttu-id="ba66b-103">Cette rubrique explique comment créer une sauvegarde de base de données complète dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)]ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba66b-103">This topic describes how to create a full database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba66b-104">Pour plus d’informations sur la sauvegarde de SQL Server dans le service de stockage d’objets BLOB Azure, consultez, [SQL Server sauvegarde et restauration avec le service de stockage d’objets BLOB Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="ba66b-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ba66b-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ba66b-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ba66b-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ba66b-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ba66b-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ba66b-108">Recommandations</span><span class="sxs-lookup"><span data-stu-id="ba66b-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="ba66b-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ba66b-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ba66b-110">**Pour créer une sauvegarde de base de données complète, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="ba66b-110">**To create a full database backup, using:**</span></span>  
  
     [<span data-ttu-id="ba66b-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba66b-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ba66b-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ba66b-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="ba66b-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba66b-113">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="ba66b-114">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ba66b-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ba66b-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ba66b-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ba66b-116">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ba66b-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ba66b-117">L'instruction BACKUP n'est pas autorisée dans une transaction explicite ou implicite.</span><span class="sxs-lookup"><span data-stu-id="ba66b-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="ba66b-118">Les sauvegardes créées avec une version plus récente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peuvent pas être restaurées dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba66b-118">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="ba66b-119">Pour plus d’informations, consultez [Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-119">For more information, see [Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ba66b-120">Recommandations</span><span class="sxs-lookup"><span data-stu-id="ba66b-120">Recommendations</span></span>  
  
-   <span data-ttu-id="ba66b-121">À mesure que la taille d'une base de données augmente, les sauvegardes complètes de base de données nécessitent davantage de temps et d'espace de stockage.</span><span class="sxs-lookup"><span data-stu-id="ba66b-121">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="ba66b-122">Par conséquent, pour les bases de données volumineuses, il est conseillé de compléter les sauvegardes complètes avec une série de *sauvegardes différentielles de base de données*.</span><span class="sxs-lookup"><span data-stu-id="ba66b-122">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="ba66b-123">Pour plus d’informations, consultez [Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-123">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="ba66b-124">Vous pouvez estimer la taille d’une sauvegarde complète de base de données en utilisant la procédure stockée système [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ba66b-124">You can estimate the size of a full database backup by using the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure.</span></span>  
  
-   <span data-ttu-id="ba66b-125">Par défaut, chaque opération de sauvegarde réussie ajoute une entrée au journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et au journal des événements système.</span><span class="sxs-lookup"><span data-stu-id="ba66b-125">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="ba66b-126">Si vous sauvegardez très fréquemment le journal, ces messages de réussite peuvent rapidement s'accumuler, créer des journaux d'erreurs très volumineux et compliquer la recherche d'autres messages.</span><span class="sxs-lookup"><span data-stu-id="ba66b-126">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="ba66b-127">Dans de tels cas, vous pouvez supprimer ces entrées de journal en utilisant l'indicateur de trace 3226 si aucun de vos scripts ne dépend de ces entrées.</span><span class="sxs-lookup"><span data-stu-id="ba66b-127">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="ba66b-128">Pour plus d’informations, consultez [Indicateurs de trace &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba66b-128">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ba66b-129">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ba66b-129">Security</span></span>  
 <span data-ttu-id="ba66b-130">TRUSTWORTHY a la valeur OFF pour une sauvegarde de base de données.</span><span class="sxs-lookup"><span data-stu-id="ba66b-130">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="ba66b-131">Pour plus d’informations sur la façon d’affecter la valeur ON à TRUSTWORTHY, consultez [Options ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="ba66b-131">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="ba66b-132">À compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], les options `PASSWORD` et `MEDIAPASSWORD` sont supprimées pour la création de sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="ba66b-132">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] the `PASSWORD` and `MEDIAPASSWORD` options are discontinued for creating backups.</span></span> <span data-ttu-id="ba66b-133">Vous pouvez toujours restaurer les sauvegardes créées avec des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="ba66b-133">You can still restore backups created with passwords.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ba66b-134">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ba66b-134">Permissions</span></span>  
 <span data-ttu-id="ba66b-135">Les autorisations BACKUP DATABASE et BACKUP LOG reviennent par défaut aux membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-135">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="ba66b-136">Des problèmes de propriété et d'autorisations sur le fichier physique de l'unité de sauvegarde sont susceptibles de perturber une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ba66b-136">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ba66b-137">doit être en mesure de lire et d'écrire sur l'unité ; le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute doit avoir des autorisations d'écriture.</span><span class="sxs-lookup"><span data-stu-id="ba66b-137">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="ba66b-138">Toutefois, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), qui ajoute une entrée pour une unité de sauvegarde dans les tables système, ne vérifie pas les autorisations d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="ba66b-138">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="ba66b-139">De tels problèmes pour le fichier physique de l'unité de sauvegarde peuvent n'apparaître que lorsque la ressource physique est sollicitée au moment de la sauvegarde ou de la restauration.</span><span class="sxs-lookup"><span data-stu-id="ba66b-139">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ba66b-140">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba66b-140">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba66b-141"> Si vous spécifiez une tâche de sauvegarde à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vous pouvez générer le script [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) correspondant en cliquant sur le bouton **Script** et en sélectionnant une destination de script.</span><span class="sxs-lookup"><span data-stu-id="ba66b-141">When you specify a back up task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and selecting a script destination.</span></span>  
  
#### <a name="to-back-up-a-database"></a><span data-ttu-id="ba66b-142">Pour sauvegarder une base de données</span><span class="sxs-lookup"><span data-stu-id="ba66b-142">To back up a database</span></span>  
  
1.  <span data-ttu-id="ba66b-143">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="ba66b-143">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ba66b-144">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="ba66b-144">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="ba66b-145">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-145">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="ba66b-146">La boîte de dialogue **Sauvegarder la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="ba66b-146">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="ba66b-147">Dans la `Database` zone de liste, vérifiez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ba66b-147">In the `Database` list box, verify the database name.</span></span> <span data-ttu-id="ba66b-148">Vous pouvez éventuellement sélectionner une autre base de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ba66b-148">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="ba66b-149">Vous pouvez effectuer une sauvegarde de base de données pour tout mode de récupération (**FULL**, **BULK_LOGGED**ou **SIMPLE**).</span><span class="sxs-lookup"><span data-stu-id="ba66b-149">You can perform a database backup for any recovery model (**FULL**, **BULK_LOGGED**, or **SIMPLE**).</span></span>  
  
6.  <span data-ttu-id="ba66b-150">Dans la zone de liste **Type de sauvegarde**, sélectionnez **Complète**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-150">In the **Backup type** list box, select **Full**.</span></span>  
  
     <span data-ttu-id="ba66b-151">Notez qu’après la création d’une sauvegarde de base de données complète, vous pouvez créer une sauvegarde de base de données différentielle. Pour plus d’informations, consultez [Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-151">Note that after creating a full database backup, you can create a differential database backup; for more information, see [Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span></span>  
  
7.  <span data-ttu-id="ba66b-152">Vous pouvez si vous le souhaitez sélectionner **Sauvegarde de copie uniquement** pour créer une sauvegarde de copie uniquement.</span><span class="sxs-lookup"><span data-stu-id="ba66b-152">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="ba66b-153">Une *sauvegarde de copie uniquement* est une sauvegarde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indépendante du mécanisme des sauvegardes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conventionnelles.</span><span class="sxs-lookup"><span data-stu-id="ba66b-153">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="ba66b-154">Pour plus d’informations, consultez [Sauvegardes de copie uniquement &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-154">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ba66b-155">Lorsque l'option **Différentielle** est sélectionnée, vous ne pouvez pas créer de sauvegarde de copie uniquement.</span><span class="sxs-lookup"><span data-stu-id="ba66b-155">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="ba66b-156">Pour **composant de sauvegarde**, cliquez sur `Database` .</span><span class="sxs-lookup"><span data-stu-id="ba66b-156">For **Backup component**, click `Database`.</span></span>  
  
9. <span data-ttu-id="ba66b-157">Acceptez le nom du jeu de sauvegarde par défaut proposé dans la zone de texte **Nom** , ou attribuez-lui un autre nom.</span><span class="sxs-lookup"><span data-stu-id="ba66b-157">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
10. <span data-ttu-id="ba66b-158">Dans la zone de texte **Description** , vous avez la possibilité de saisir une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ba66b-158">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
11. <span data-ttu-id="ba66b-159">Choisissez le type de destination de la sauvegarde en cliquant sur **Disque**, **Bande** ou **URL**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-159">Choose the type of backup destination by clicking **Disk**, **Tape** or **URL**.</span></span> <span data-ttu-id="ba66b-160">Pour sélectionner les chemins d'accès à 64 lecteurs de bande ou de disque au maximum contenant un seul support de sauvegarde, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-160">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="ba66b-161">Les chemins d'accès sélectionnés apparaissent dans la zone de liste **Sauvegarde sur** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-161">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="ba66b-162">Pour supprimer une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-162">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="ba66b-163">Pour afficher le contenu d'une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Sommaire**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-163">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="ba66b-164">Pour afficher ou sélectionner les options de support, cliquez sur **Options de support** dans le volet **Sélectionner une page** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-164">To view or select the media options, click **Media Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="ba66b-165">Sélectionnez une option **Remplacer le support** en cliquant sur un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ba66b-165">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="ba66b-166">**Sauvegarder sur le support de sauvegarde existant**</span><span class="sxs-lookup"><span data-stu-id="ba66b-166">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="ba66b-167">Pour cette option, cliquez sur **Ajouter au jeu de sauvegarde existant** ou sur **Remplacer tous les jeux de sauvegarde existants**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-167">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="ba66b-168">Pour plus d’informations, consultez [Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-168">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="ba66b-169">Vous pouvez aussi activer la case à cocher **Vérifier le nom du support de sauvegarde et la date d'expiration du jeu de sauvegarde** pour forcer l'opération de sauvegarde à vérifier la date et l'heure de l'expiration du jeu de supports ou du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ba66b-169">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="ba66b-170">Vous pouvez éventuellement entrer un nom dans la zone de texte **Nom du support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-170">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="ba66b-171">Si aucun nom n'est spécifié, un support de sauvegarde avec un nom vide est créé.</span><span class="sxs-lookup"><span data-stu-id="ba66b-171">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="ba66b-172">Si vous spécifiez un nom pour le support de sauvegarde, ce support (bande ou disque) est vérifié pour voir si le nom réel correspond bien au nom que vous entrez ici.</span><span class="sxs-lookup"><span data-stu-id="ba66b-172">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="ba66b-173">Cette option est désactivée si vous avez sélectionné **URL** comme destination de la sauvegarde dans la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-173">This option is disabled if you selected **URL** as the backup destination in the **General** page.</span></span> <span data-ttu-id="ba66b-174">Pour plus d’informations, consultez [Sauvegarder la base de données &#40;page Options de support&#41;](back-up-database-media-options-page.md)</span><span class="sxs-lookup"><span data-stu-id="ba66b-174">For more information, see [Back Up Database &#40;Media Options Page&#41;](back-up-database-media-options-page.md)</span></span>  
        >   
        >  <span data-ttu-id="ba66b-175">Si vous envisagez d'utiliser le chiffrement, ne sélectionnez pas cette option.</span><span class="sxs-lookup"><span data-stu-id="ba66b-175">If you plan to use encryption, do not select this option.</span></span> <span data-ttu-id="ba66b-176">Si vous sélectionnez cette option, les options de chiffrement dans la page **Options de sauvegarde** seront désactivées.</span><span class="sxs-lookup"><span data-stu-id="ba66b-176">If you select this option, the encryption options in the **Backup Options** page will be disabled.</span></span> <span data-ttu-id="ba66b-177">Le chiffrement n'est pas pris en charge lors de l'ajout à un jeu de sauvegarde existant.</span><span class="sxs-lookup"><span data-stu-id="ba66b-177">Encryption is not supported when appending to the existing backup set.</span></span>  
  
    -   <span data-ttu-id="ba66b-178">**Sauvegarder sur un nouveau support de sauvegarde et effacer tous les jeux de sauvegarde existants**</span><span class="sxs-lookup"><span data-stu-id="ba66b-178">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="ba66b-179">Pour cette option, entrez un nom dans la zone de texte **Nouveau nom du support de sauvegarde** et décrivez éventuellement le jeu de supports dans la zone de texte **Description du nouveau support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-179">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="ba66b-180">Cette option est désactivée si vous avez sélectionné **URL** dans la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-180">This option is disabled if you selected **URL** in the **General** page.</span></span> <span data-ttu-id="ba66b-181">Ces actions ne sont pas prises en charge lors de la sauvegarde dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="ba66b-181">These actions are not supported when backing up to Azure storage.</span></span>  
  
14. <span data-ttu-id="ba66b-182">Dans la section **fiabilité** , vérifiez éventuellement :</span><span class="sxs-lookup"><span data-stu-id="ba66b-182">In the **Reliability** section, optionally check:</span></span>  
  
    -   <span data-ttu-id="ba66b-183">**Vérifier la sauvegarde en fin d'opération**;</span><span class="sxs-lookup"><span data-stu-id="ba66b-183">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="ba66b-184">**Effectuer une somme de contrôle avant d'écrire sur le support**et éventuellement **Continuer lors d'erreurs de somme de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-184">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="ba66b-185">Pour plus d’informations sur les sommes de contrôle, consultez [Erreurs de support possibles pendant les opérations de sauvegarde et de restauration &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-185">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="ba66b-186">Si vous effectuez la sauvegarde sur un lecteur de bande (spécifié dans la section **Destination** de la page **Général** ), l’option **Décharger la bande après la sauvegarde** est active.</span><span class="sxs-lookup"><span data-stu-id="ba66b-186">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="ba66b-187">Vous pouvez cliquer sur cette option pour activer l'option **Rembobiner la bande avant de décharger** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-187">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ba66b-188">Les options de la section **Journal des transactions** sont inactives, à moins que vous ne sauvegardiez un journal des transactions (comme spécifié dans la section **Type de sauvegarde** de la page **Général** ).</span><span class="sxs-lookup"><span data-stu-id="ba66b-188">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
16. <span data-ttu-id="ba66b-189">Pour afficher ou sélectionner les options de sauvegarde, cliquez sur **Options de sauvegarde** dans le volet **Sélectionner une page**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-189">To view or select the backup options, click **Backup Options** in the **Select a page** pane.</span></span>  
  
17. <span data-ttu-id="ba66b-190">Spécifiez le moment où le jeu de sauvegarde va expirer et pourra être remplacé sans ignorer explicitement la vérification des données d'expiration :</span><span class="sxs-lookup"><span data-stu-id="ba66b-190">Specify when the backup set will expire and can be overwritten without explicitly skipping verification of the expiration data:</span></span>  
  
    -   <span data-ttu-id="ba66b-191">Pour que le jeu de sauvegarde expire au bout d’un nombre de jours spécifique, cliquez sur **Après** (option par défaut) et entrez le nombre de jours souhaité pour l’expiration du jeu après sa création.</span><span class="sxs-lookup"><span data-stu-id="ba66b-191">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="ba66b-192">Cette valeur doit être comprise entre 0 et 99999 jours ; une valeur de 0 jour signifie que le jeu de sauvegarde n'expirera jamais.</span><span class="sxs-lookup"><span data-stu-id="ba66b-192">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="ba66b-193">La valeur par défaut est définie dans l’option **Délai de rétention par défaut du support de sauvegarde (jours)** de la boîte de dialogue **Propriétés du serveur** (page Paramètres de base de données).</span><span class="sxs-lookup"><span data-stu-id="ba66b-193">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (Database Settings Page).</span></span> <span data-ttu-id="ba66b-194">Pour y accéder, cliquez avec le bouton droit sur le nom du serveur dans l’Explorateur d’objets et sélectionnez les propriétés. Ensuite, sélectionnez la page **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-194">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="ba66b-195">Pour que le jeu de sauvegarde expire à une date spécifique, cliquez sur **Le**et entrez la date d'expiration souhaitée.</span><span class="sxs-lookup"><span data-stu-id="ba66b-195">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
         <span data-ttu-id="ba66b-196">Pour plus d’informations sur les dates d’expiration des sauvegardes, consultez [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba66b-196">For more information about backup expiration dates, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
18. [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="ba66b-197">et versions ultérieures prennent en charge la [compression de la sauvegarde](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-197">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="ba66b-198">Par défaut, la compression d’une sauvegarde dépend de la valeur de l’option de configuration de serveur **Compression par défaut des sauvegardes** .</span><span class="sxs-lookup"><span data-stu-id="ba66b-198">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="ba66b-199">Toutefois, quelle que soit la valeur par défaut actuelle au niveau du serveur, vous pouvez compresser une sauvegarde en activant **Compresser la sauvegarde**, et vous pouvez empêcher la compression en activant **Ne pas compresser la sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="ba66b-199">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="ba66b-200">**Pour consulter ou modifier la valeur par défaut de compression de la sauvegarde actuelle**</span><span class="sxs-lookup"><span data-stu-id="ba66b-200">**To view or change the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="ba66b-201">Afficher ou configurer la compression par défaut des sauvegardes (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="ba66b-201">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
19. <span data-ttu-id="ba66b-202">Spécifiez si utiliser le chiffrement pour la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ba66b-202">Specify whether to use encryption for the backup.</span></span> <span data-ttu-id="ba66b-203">Sélectionnez l'algorithme de chiffrement à utiliser pour l'étape de chiffrement et fournissez un certificat ou une clé asymétrique dans la liste des certificats ou clés numériques existants.</span><span class="sxs-lookup"><span data-stu-id="ba66b-203">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="ba66b-204">Le chiffrement est pris en charge dans SQL Server 2014 ou les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="ba66b-204">Encryption is supported in SQL Server 2014 or later.</span></span> <span data-ttu-id="ba66b-205">Pour plus d’informations sur les options de chiffrement, consultez [Sauvegarder la base de données &#40;page Options de sauvegarde&#41;](back-up-database-backup-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-205">For more details on the Encryption options, see [Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba66b-206">Vous pouvez également utiliser l'Assistant Plan de maintenance pour créer des sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="ba66b-206">Alternatively, you can use the Maintenance Plan Wizard to create database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ba66b-207">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ba66b-207">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-full-database-backup"></a><span data-ttu-id="ba66b-208">Pour créer une sauvegarde de base de données complète</span><span class="sxs-lookup"><span data-stu-id="ba66b-208">To create a full database backup</span></span>  
  
1.  <span data-ttu-id="ba66b-209">Exécutez l'instruction BACKUP DATABASE en spécifiant les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ba66b-209">Execute the BACKUP DATABASE statement to create the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="ba66b-210">le nom de la base de données à sauvegarder ;</span><span class="sxs-lookup"><span data-stu-id="ba66b-210">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="ba66b-211">l'unité de sauvegarde où est écrite la sauvegarde complète de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ba66b-211">The backup device where the full database backup is written.</span></span>  
  
     <span data-ttu-id="ba66b-212">La syntaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] de base nécessaire pour une sauvegarde de base de données complète est la suivante :</span><span class="sxs-lookup"><span data-stu-id="ba66b-212">The basic [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for a full database backup is:</span></span>  
  
     <span data-ttu-id="ba66b-213">BACKUP DATABASE *database*</span><span class="sxs-lookup"><span data-stu-id="ba66b-213">BACKUP DATABASE *database*</span></span>  
  
     <span data-ttu-id="ba66b-214">TO *unité_sauvegarde* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="ba66b-214">TO *backup_device* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="ba66b-215">[ WITH *options_with* [ **,** ...*o* ] ] ;</span><span class="sxs-lookup"><span data-stu-id="ba66b-215">[ WITH *with_options* [ **,**...*o* ] ] ;</span></span>  
  
    |<span data-ttu-id="ba66b-216">Option</span><span class="sxs-lookup"><span data-stu-id="ba66b-216">Option</span></span>|<span data-ttu-id="ba66b-217">Description</span><span class="sxs-lookup"><span data-stu-id="ba66b-217">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="ba66b-218">*database*</span><span class="sxs-lookup"><span data-stu-id="ba66b-218">*database*</span></span>|<span data-ttu-id="ba66b-219">Base de données à sauvegarder</span><span class="sxs-lookup"><span data-stu-id="ba66b-219">Is the database that is to be backed up.</span></span>|  
    |<span data-ttu-id="ba66b-220">*unité_sauvegarde* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="ba66b-220">*backup_device* [ **,**...*n* ]</span></span>|<span data-ttu-id="ba66b-221">Spécifie une liste de 1 à 64 unités de sauvegarde à utiliser pour l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ba66b-221">Specifies a list of from 1 to 64 backup devices to use for the backup operation.</span></span> <span data-ttu-id="ba66b-222">Vous pouvez spécifier une unité de sauvegarde physique ou une unité de sauvegarde logique correspondante, si celle-ci est déjà définie.</span><span class="sxs-lookup"><span data-stu-id="ba66b-222">You can specify a physical backup device, or you can specify a corresponding logical backup device, if already defined.</span></span> <span data-ttu-id="ba66b-223">Pour spécifier une unité de sauvegarde physique, utilisez l'option DISK ou TAPE :</span><span class="sxs-lookup"><span data-stu-id="ba66b-223">To specify a physical backup device, use the DISK or TAPE option:</span></span><br /><br /> <span data-ttu-id="ba66b-224">{ DISK &#124; TAPE } **=** _nom_unité_sauvegarde_physique_</span><span class="sxs-lookup"><span data-stu-id="ba66b-224">{ DISK &#124; TAPE } **=**_physical_backup_device_name_</span></span><br /><br /> <span data-ttu-id="ba66b-225">Pour plus d’informations, consultez [Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-225">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>|  
    |<span data-ttu-id="ba66b-226">WITH *options_with* [ **,** ...*o* ]</span><span class="sxs-lookup"><span data-stu-id="ba66b-226">WITH *with_options* [ **,**...*o* ]</span></span>|<span data-ttu-id="ba66b-227">Spécifie éventuellement une ou plusieurs options supplémentaires, *o*.</span><span class="sxs-lookup"><span data-stu-id="ba66b-227">Optionally, specifies one or more additional options, *o*.</span></span> <span data-ttu-id="ba66b-228">Pour obtenir des informations de base sur les options, consultez l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="ba66b-228">For information about some of the basic with options, see step 2.</span></span>|  
  
2.  <span data-ttu-id="ba66b-229">Spécifiez éventuellement une ou plusieurs options WITH.</span><span class="sxs-lookup"><span data-stu-id="ba66b-229">Optionally, specify one or more WITH options.</span></span> <span data-ttu-id="ba66b-230">Quelques options WITH de base sont décrites ici.</span><span class="sxs-lookup"><span data-stu-id="ba66b-230">A few basic WITH options are described here.</span></span> <span data-ttu-id="ba66b-231">Pour obtenir des informations sur toutes les options WITH, consultez [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba66b-231">For information about all the WITH options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
    -   <span data-ttu-id="ba66b-232">Options WITH de base relatives au jeu de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="ba66b-232">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="ba66b-233">{ COMPRESSION | NO_COMPRESSION }</span><span class="sxs-lookup"><span data-stu-id="ba66b-233">{ COMPRESSION | NO_COMPRESSION }</span></span>  
         <span data-ttu-id="ba66b-234">Dans [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] et versions ultérieures uniquement, spécifie si la [compression de la sauvegarde](backup-compression-sql-server.md) est effectuée sur cette sauvegarde, remplaçant la valeur par défaut au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="ba66b-234">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] and later only, specifies whether [backup compression](backup-compression-sql-server.md) is performed on this backup, overriding the server-level default.</span></span>  
  
         <span data-ttu-id="ba66b-235">ENCRYPTION (ALGORITHM,  SERVER CERTIFICATE |ASYMMETRIC KEY)</span><span class="sxs-lookup"><span data-stu-id="ba66b-235">ENCRYPTION (ALGORITHM,  SERVER CERTIFICATE |ASYMMETRIC KEY)</span></span>  
         <span data-ttu-id="ba66b-236">Dans SQL Server 2014 ou les versions ultérieures, spécifiez l'algorithme de chiffrement à utiliser, ainsi que le certificat ou la clé asymétrique pour sécuriser le chiffrement.</span><span class="sxs-lookup"><span data-stu-id="ba66b-236">In SQL Server 2014 or later only, specify the encryption algorithm to use, and the Certificate or Asymmetric key to use to secure the encryption.</span></span>  
  
         <span data-ttu-id="ba66b-237">DESCRIPTION **=** { **' *`text`* '**  |  **@** _text_variable_ }</span><span class="sxs-lookup"><span data-stu-id="ba66b-237">DESCRIPTION **=** { **'*`text`*'** | **@**_text_variable_ }</span></span>  
         <span data-ttu-id="ba66b-238">Spécifie le texte au format libre servant à décrire le jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ba66b-238">Specifies the free-form text that describes the backup set.</span></span> <span data-ttu-id="ba66b-239">La chaîne peut compter jusqu'à 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="ba66b-239">The string can have a maximum of 255 characters.</span></span>  
  
         <span data-ttu-id="ba66b-240">Nom **=** { *backup_set_name*  |  **@** _backup_set_name_var_ }</span><span class="sxs-lookup"><span data-stu-id="ba66b-240">NAME **=** { *backup_set_name* | **@**_backup_set_name_var_ }</span></span>  
         <span data-ttu-id="ba66b-241">Spécifie le nom du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ba66b-241">Specifies the name of the backup set.</span></span> <span data-ttu-id="ba66b-242">Les noms peuvent contenir jusqu'à 128 caractères.</span><span class="sxs-lookup"><span data-stu-id="ba66b-242">Names can have a maximum of 128 characters.</span></span> <span data-ttu-id="ba66b-243">Si l'option NAME n'est pas spécifiée, le nom reste vide.</span><span class="sxs-lookup"><span data-stu-id="ba66b-243">If NAME is not specified, it is blank.</span></span>  
  
    -   <span data-ttu-id="ba66b-244">Options WITH de base relatives au jeu de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="ba66b-244">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="ba66b-245">Par défaut, l'option BACKUP ajoute la sauvegarde à un support de sauvegarde existant, préservant les jeux de sauvegarde existants.</span><span class="sxs-lookup"><span data-stu-id="ba66b-245">By default, BACKUP appends the backup to an existing media set, preserving existing backup sets.</span></span> <span data-ttu-id="ba66b-246">Pour spécifier explicitement ceci, utilisez l'option NOINIT.</span><span class="sxs-lookup"><span data-stu-id="ba66b-246">To explicitly specify this, use the NOINIT option.</span></span> <span data-ttu-id="ba66b-247">Pour plus d’informations sur l’ajout à des jeux de sauvegarde existants, consultez [Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba66b-247">For information about appending to existing backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="ba66b-248">Une autre méthode pour formater le support de sauvegarde consiste à utiliser l'option FORMAT :</span><span class="sxs-lookup"><span data-stu-id="ba66b-248">Alternatively, to format the backup media, use the FORMAT option:</span></span>  
  
         <span data-ttu-id="ba66b-249">FORMAT [ **,** MEDIANAME **=** { *media_name*  |  **@** _media_name_variable_ }] [ **,** MediaDescription **=** { *Text*  |  **@** _text_variable_ }]</span><span class="sxs-lookup"><span data-stu-id="ba66b-249">FORMAT [ **,** MEDIANAME**=** { *media_name* | **@**_media_name_variable_ } ] [ **,** MEDIADESCRIPTION **=** { *text* | **@**_text_variable_ } ]</span></span>  
         <span data-ttu-id="ba66b-250">Utilisez la clause FORMAT si vous utilisez le support pour la première fois ou si vous souhaitez écraser toutes les données existantes.</span><span class="sxs-lookup"><span data-stu-id="ba66b-250">Use the FORMAT clause when you are using media for the first time or you want to overwrite all existing data.</span></span> <span data-ttu-id="ba66b-251">Assignez éventuellement un nom et une description au nouveau support.</span><span class="sxs-lookup"><span data-stu-id="ba66b-251">Optionally, assign the new media a media name and description.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="ba66b-252">Soyez extrêmement vigilant lorsque vous utilisez la clause FORMAT de l'instruction BACKUP, car elle entraîne la destruction de toutes les sauvegardes préalablement stockées sur le support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ba66b-252">Use extreme caution when you are using the FORMAT clause of the BACKUP statement because this destroys any backups that were previously stored on the backup media.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="ba66b-253">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ba66b-253">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-backing-up-to-a-disk-device"></a><span data-ttu-id="ba66b-254">R.</span><span class="sxs-lookup"><span data-stu-id="ba66b-254">A.</span></span> <span data-ttu-id="ba66b-255">Sauvegarde sur une unité de disque</span><span class="sxs-lookup"><span data-stu-id="ba66b-255">Backing up to a disk device</span></span>  
 <span data-ttu-id="ba66b-256">L'exemple suivant sauvegarde entièrement la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sur disque, à l'aide de `FORMAT` , pour créer une nouveau jeu de supports.</span><span class="sxs-lookup"><span data-stu-id="ba66b-256">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to disk, by using `FORMAT` to create a new media set.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH FORMAT,  
      MEDIANAME = 'Z_SQLServerBackups',  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="b-backing-up-to-a-tape-device"></a><span data-ttu-id="ba66b-257">B.</span><span class="sxs-lookup"><span data-stu-id="ba66b-257">B.</span></span> <span data-ttu-id="ba66b-258">Sauvegarde sur un périphérique à bandes</span><span class="sxs-lookup"><span data-stu-id="ba66b-258">Backing up to a tape device</span></span>  
 <span data-ttu-id="ba66b-259">L'exemple suivant sauvegarde la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]complète sur bande, en ajoutant la sauvegarde aux sauvegardes précédentes.</span><span class="sxs-lookup"><span data-stu-id="ba66b-259">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]database to tape, appending the backup to the previous backups.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO TAPE = '\\.\Tape0'  
   WITH NOINIT,  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="c-backing-up-to-a-logical-tape-device"></a><span data-ttu-id="ba66b-260">C.</span><span class="sxs-lookup"><span data-stu-id="ba66b-260">C.</span></span> <span data-ttu-id="ba66b-261">Sauvegarde sur un périphérique à bandes logique</span><span class="sxs-lookup"><span data-stu-id="ba66b-261">Backing up to a logical tape device</span></span>  
 <span data-ttu-id="ba66b-262">L'exemple suivant crée une unité de sauvegarde logique pour un périphérique à bandes.</span><span class="sxs-lookup"><span data-stu-id="ba66b-262">The following example creates a logical backup device for a tape drive.</span></span> <span data-ttu-id="ba66b-263">Il sauvegarde ensuite la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] complète sur ce périphérique.</span><span class="sxs-lookup"><span data-stu-id="ba66b-263">The example then backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to that device.</span></span>  
  
```sql  
-- Create a logical backup device,   
-- AdventureWorks2012_Bak_Tape, for tape device \\.\tape0.  
USE master;  
GO  
EXEC sp_addumpdevice 'tape', 'AdventureWorks2012_Bak_Tape', '\\.\tape0'; USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO AdventureWorks2012_Bak_Tape  
   WITH FORMAT,  
      MEDIANAME = 'AdventureWorks2012_Bak_Tape',  
      MEDIADESCRIPTION = '\\.\tape0',   
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="ba66b-264">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba66b-264">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="ba66b-265">Utilisez l'applet de commande `Backup-SqlDatabase`.</span><span class="sxs-lookup"><span data-stu-id="ba66b-265">Use the `Backup-SqlDatabase` cmdlet.</span></span> <span data-ttu-id="ba66b-266">Pour indiquer explicitement qu’il s’agit d’une sauvegarde complète de base de données, spécifiez le paramètre **-BackupAction** avec sa valeur par défaut, `Database` .</span><span class="sxs-lookup"><span data-stu-id="ba66b-266">To explicitly indicate that this is a full database backup, specify the **-BackupAction**  parameter with its default value, `Database`.</span></span> <span data-ttu-id="ba66b-267">Ce paramètre est facultatif pour les sauvegardes complètes de base de données.</span><span class="sxs-lookup"><span data-stu-id="ba66b-267">This parameter is optional for full database backups.</span></span>  
  
     <span data-ttu-id="ba66b-268">L'exemple suivant crée une sauvegarde complète de la base de données `MyDB` à l'emplacement de sauvegarde par défaut de l'instance de serveur `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="ba66b-268">The following example creates a full database backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span> <span data-ttu-id="ba66b-269">Cet exemple spécifie, de manière facultative, `-BackupAction Database`.</span><span class="sxs-lookup"><span data-stu-id="ba66b-269">Optionally, this example specifies `-BackupAction Database`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Database  
    ```  
  
 <span data-ttu-id="ba66b-270">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ba66b-270">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="ba66b-271">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba66b-271">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ba66b-272">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ba66b-272">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ba66b-273">Sauvegarder une base de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ba66b-273">Back Up a Database (SQL Server)</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="ba66b-274">Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba66b-274">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="ba66b-275">Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ba66b-275">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="ba66b-276">Restaurer une sauvegarde de base de données en mode de récupération simple &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ba66b-276">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="ba66b-277">Restaurer une base de données jusqu’au point d’échec en mode de récupération complète &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ba66b-277">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="ba66b-278">Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba66b-278">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="ba66b-279">Utiliser l'Assistant Plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="ba66b-279">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba66b-280"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba66b-280">See Also</span></span>  
 <span data-ttu-id="ba66b-281">[Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba66b-281">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="ba66b-282">[Sauvegardes des journaux de transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba66b-282">[Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ba66b-283">[Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba66b-283">[Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span></span>  
 <span data-ttu-id="ba66b-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba66b-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="ba66b-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba66b-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ba66b-286">[Sauvegarder la base de données &#40;page Général&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="ba66b-286">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="ba66b-287">[Sauvegarder la base de données &#40;page Options de sauvegarde&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="ba66b-287">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="ba66b-288">[Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba66b-288">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="ba66b-289">Sauvegardes complètes de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba66b-289">Full Database Backups &#40;SQL Server&#41;</span></span>](full-database-backups-sql-server.md)  
