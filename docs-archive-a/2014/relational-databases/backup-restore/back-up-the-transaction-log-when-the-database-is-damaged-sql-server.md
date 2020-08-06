---
title: Sauvegarder le journal des transactions quand la base de données est endommagée (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], damaged
- backing up [SQL Server]. damaged database
- transaction log backups [SQL Server], damaged databases
ms.assetid: 9b8873cc-df54-4336-ab9b-8f525132c2b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea712e6bc4e73119a4f07a7775f9f25e212f8534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600102"
---
# <a name="back-up-the-transaction-log-when-the-database-is-damaged-sql-server"></a><span data-ttu-id="74e87-102">Sauvegarder le journal des transactions lorsque la base de données est endommagée (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="74e87-102">Back Up the Transaction Log When the Database Is Damaged (SQL Server)</span></span>
  <span data-ttu-id="74e87-103">Cette rubrique explique comment sauvegarder un journal des transactions lorsque la base de données est endommagée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74e87-103">This topic describes how to back up a transaction log when the database is damaged in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="74e87-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="74e87-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="74e87-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="74e87-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="74e87-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="74e87-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="74e87-107">Recommandations</span><span class="sxs-lookup"><span data-stu-id="74e87-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="74e87-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="74e87-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="74e87-109">**Pour sauvegarder le journal des transactions lorsque la base de données est endommagée, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="74e87-109">**To back up the transaction log when the database is damaged, using:**</span></span>  
  
     [<span data-ttu-id="74e87-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74e87-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="74e87-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74e87-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="74e87-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="74e87-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="74e87-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="74e87-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="74e87-114">L'instruction BACKUP n'est pas autorisée dans une transaction explicite ou implicite.</span><span class="sxs-lookup"><span data-stu-id="74e87-114">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="74e87-115">Recommandations</span><span class="sxs-lookup"><span data-stu-id="74e87-115">Recommendations</span></span>  
  
-   <span data-ttu-id="74e87-116">Pour une base de données en mode de récupération complète ou utilisant les journaux de transactions, vous devez généralement effectuer une sauvegarde de la fin du journal avant d'entamer la restauration de la base de données.</span><span class="sxs-lookup"><span data-stu-id="74e87-116">For a database that uses either the full or bulk-logged recovery model, you generally need to back up the tail of the log before beginning to restore the database.</span></span> <span data-ttu-id="74e87-117">Vous devez également effectuer une sauvegarde de la fin du journal de la base de données primaire avant de basculer vers une configuration de la copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="74e87-117">You also should back up the tail of the log of the primary database before failing over a log shipping configuration.</span></span> <span data-ttu-id="74e87-118">La restauration de la sauvegarde de la fin du journal en tant que sauvegarde finale de fichier journal avant la récupération de la base de données permet d'éviter les pertes de données après une défaillance.</span><span class="sxs-lookup"><span data-stu-id="74e87-118">Restoring the tail-log backup as the final log backup before recovering the database avoids work loss after a failure.</span></span> <span data-ttu-id="74e87-119">Pour plus d’informations sur les sauvegardes de la fin du journal, consultez [Sauvegardes de la fin du journal &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74e87-119">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="74e87-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="74e87-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="74e87-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="74e87-121">Permissions</span></span>  
 <span data-ttu-id="74e87-122">Les autorisations BACKUP DATABASE et BACKUP LOG reviennent par défaut aux membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="74e87-122">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="74e87-123">Des problèmes de propriété et d'autorisations sur le fichier physique de l'unité de sauvegarde sont susceptibles de perturber une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="74e87-123">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="74e87-124">doit être en mesure de lire et d'écrire sur l'unité ; le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute doit avoir des autorisations d'écriture.</span><span class="sxs-lookup"><span data-stu-id="74e87-124">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="74e87-125">Toutefois, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), qui ajoute une entrée pour une unité de sauvegarde dans les tables système, ne vérifie pas les autorisations d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="74e87-125">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="74e87-126">De tels problèmes pour le fichier physique de l'unité de sauvegarde peuvent n'apparaître que lorsque la ressource physique est sollicitée au moment de la sauvegarde ou de la restauration.</span><span class="sxs-lookup"><span data-stu-id="74e87-126">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="74e87-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74e87-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-the-tail-of-the-transaction-log"></a><span data-ttu-id="74e87-128">Pour effectuer une sauvegarde de fichier journal de transactions après défaillance</span><span class="sxs-lookup"><span data-stu-id="74e87-128">To back up the tail of the transaction log</span></span>  
  
1.  <span data-ttu-id="74e87-129">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="74e87-129">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="74e87-130">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="74e87-130">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="74e87-131">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**.</span><span class="sxs-lookup"><span data-stu-id="74e87-131">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="74e87-132">La boîte de dialogue **Sauvegarder la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="74e87-132">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="74e87-133">Dans la zone de liste **Base de données** , vérifiez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="74e87-133">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="74e87-134">Vous pouvez éventuellement sélectionner une autre base de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="74e87-134">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="74e87-135">Vérifiez que le mode de récupération est **FULL** ou **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="74e87-135">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="74e87-136">Dans la zone de liste **Type de sauvegarde** , sélectionnez **Journal des transactions**.</span><span class="sxs-lookup"><span data-stu-id="74e87-136">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="74e87-137">Laissez l'option **Sauvegarde de copie uniquement** désactivée.</span><span class="sxs-lookup"><span data-stu-id="74e87-137">Leave **Copy Only Backup** deselected.</span></span>  
  
8.  <span data-ttu-id="74e87-138">Dans la zone **Jeu de sauvegarde** , acceptez le nom du jeu de sauvegarde par défaut proposé dans la zone de texte **Nom** , ou attribuez-lui un autre nom.</span><span class="sxs-lookup"><span data-stu-id="74e87-138">In the **Backup set** area, either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="74e87-139">Dans la zone de texte **Description** , entrez une description de la sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="74e87-139">In the **Description** text box, enter a description for the tail-log backup.</span></span>  
  
10. <span data-ttu-id="74e87-140">Indiquez quand le jeu de sauvegarde arrivera à expiration :</span><span class="sxs-lookup"><span data-stu-id="74e87-140">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="74e87-141">Pour que le jeu de sauvegarde expire au bout d’un nombre de jours spécifique, cliquez sur **Après** (option par défaut) et entrez le nombre de jours souhaité pour l’expiration du jeu après sa création.</span><span class="sxs-lookup"><span data-stu-id="74e87-141">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="74e87-142">Cette valeur doit être comprise entre 0 et 99999 jours ; une valeur de 0 jour signifie que le jeu de sauvegarde n'expirera jamais.</span><span class="sxs-lookup"><span data-stu-id="74e87-142">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="74e87-143">La valeur par défaut est définie dans l’option **Délai de rétention par défaut du support de sauvegarde (jours)** de la boîte de dialogue **Propriétés du serveur** (page**Paramètres de base de données** ).</span><span class="sxs-lookup"><span data-stu-id="74e87-143">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="74e87-144">Pour accéder à cette base de données, cliquez avec le bouton droit sur le nom du serveur dans l’Explorateur d’objets et sélectionnez Propriétés. Ensuite, sélectionnez la page **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="74e87-144">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="74e87-145">Pour que le jeu de sauvegarde expire à une date spécifique, cliquez sur **Le**et entrez la date d'expiration souhaitée.</span><span class="sxs-lookup"><span data-stu-id="74e87-145">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="74e87-146">Choisissez le type de destination de la sauvegarde : **Disque** ou **Bande**.</span><span class="sxs-lookup"><span data-stu-id="74e87-146">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="74e87-147">Pour sélectionner les chemins d'accès à 64 lecteurs de bande ou de disque au maximum contenant un seul support de sauvegarde, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="74e87-147">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="74e87-148">Les chemins d'accès sélectionnés apparaissent dans la zone de liste **Sauvegarde sur** .</span><span class="sxs-lookup"><span data-stu-id="74e87-148">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="74e87-149">Pour supprimer une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="74e87-149">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="74e87-150">Pour afficher le contenu d'une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Sommaire**.</span><span class="sxs-lookup"><span data-stu-id="74e87-150">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="74e87-151">Sur la page **Options** , sélectionnez une option **Remplacer le support** en cliquant sur un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="74e87-151">On the **Options** page, select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="74e87-152">**Sauvegarder sur le support de sauvegarde existant**</span><span class="sxs-lookup"><span data-stu-id="74e87-152">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="74e87-153">Pour cette option, cliquez sur **Ajouter au jeu de sauvegarde existant** ou sur **Remplacer tous les jeux de sauvegarde existants**.</span><span class="sxs-lookup"><span data-stu-id="74e87-153">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span>  
  
         <span data-ttu-id="74e87-154">Vous pouvez aussi activer la case à cocher **Vérifier le nom du support de sauvegarde et la date d'expiration du jeu de sauvegarde** pour forcer l'opération de sauvegarde à vérifier la date et l'heure de l'expiration du jeu de supports ou du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="74e87-154">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="74e87-155">Vous pouvez éventuellement entrer un nom dans la zone de texte **Nom du support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="74e87-155">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="74e87-156">Si aucun nom n'est spécifié, un support de sauvegarde avec un nom vide est créé.</span><span class="sxs-lookup"><span data-stu-id="74e87-156">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="74e87-157">Si vous spécifiez un nom pour le support de sauvegarde, ce support (bande ou disque) est vérifié pour voir si le nom réel correspond bien au nom que vous entrez ici.</span><span class="sxs-lookup"><span data-stu-id="74e87-157">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="74e87-158">Si vous n'entrez pas de nom et que vous activez la case à cocher pour demander la vérification par rapport au support, le nom du support sera également vide sur le support.</span><span class="sxs-lookup"><span data-stu-id="74e87-158">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="74e87-159">**Sauvegarder sur un nouveau support de sauvegarde et effacer tous les jeux de sauvegarde existants**</span><span class="sxs-lookup"><span data-stu-id="74e87-159">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="74e87-160">Pour cette option, entrez un nom dans la zone de texte **Nouveau nom du support de sauvegarde** et décrivez éventuellement le jeu de supports dans la zone de texte **Description du nouveau support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="74e87-160">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
     <span data-ttu-id="74e87-161">Pour plus d’informations sur les options de supports de sauvegarde, consultez [Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74e87-161">For more information about media set options, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
13. <span data-ttu-id="74e87-162">Dans la section **Fiabilité** , vous pouvez éventuellement activer les cases à cocher :</span><span class="sxs-lookup"><span data-stu-id="74e87-162">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="74e87-163">**Vérifier la sauvegarde en fin d'opération**;</span><span class="sxs-lookup"><span data-stu-id="74e87-163">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="74e87-164">**Effectuer une somme de contrôle avant d'écrire sur le support**.</span><span class="sxs-lookup"><span data-stu-id="74e87-164">**Perform checksum before writing to media**.</span></span>  
  
    -   <span data-ttu-id="74e87-165">**Continuer lors d'erreurs de somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="74e87-165">**Continue on checksum error**</span></span>  
  
     <span data-ttu-id="74e87-166">Pour plus d’informations sur les sommes de contrôle, consultez [Erreurs de support possibles pendant les opérations de sauvegarde et de restauration &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74e87-166">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="74e87-167">Dans la section **Journal des transactions** , activez la case à cocher **Sauvegarder la fin du journal et laisser la base de données dans l'état de restauration**.</span><span class="sxs-lookup"><span data-stu-id="74e87-167">In the **Transaction log** section, check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
     <span data-ttu-id="74e87-168">Cela équivaut à spécifier l'instruction [BACKUP](/sql/t-sql/statements/backup-transact-sql) suivante :</span><span class="sxs-lookup"><span data-stu-id="74e87-168">This is equivalent to specifying the following [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
     `BACKUP LOG <database_name> TO <backup_device> WITH NORECOVERY`  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="74e87-169">Lors de la restauration, la boîte de dialogue Restaurer la base de données affiche le type de sauvegarde de la fin du journal en tant que **Journal des transactions (copie uniquement)** .</span><span class="sxs-lookup"><span data-stu-id="74e87-169">At restore time, the Restore Database dialog box displays the type of a tail-log backup as **Transaction Log (Copy Only)**.</span></span>  
  
15. <span data-ttu-id="74e87-170">Si vous effectuez la sauvegarde sur un lecteur de bande (spécifié dans la section **Destination** de la page **Général** ), l’option **Décharger la bande après la sauvegarde** est active.</span><span class="sxs-lookup"><span data-stu-id="74e87-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="74e87-171">Vous pouvez cliquer sur cette option pour activer l'option **Rembobiner la bande avant de décharger** .</span><span class="sxs-lookup"><span data-stu-id="74e87-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
16. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="74e87-172">et versions ultérieures prennent en charge la [compression de la sauvegarde](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74e87-172">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="74e87-173">Par défaut, la compression d’une sauvegarde dépend de la valeur de l’option de configuration de serveur **Compression par défaut des sauvegardes** .</span><span class="sxs-lookup"><span data-stu-id="74e87-173">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="74e87-174">Toutefois, quelle que soit la valeur par défaut actuelle au niveau du serveur, vous pouvez compresser une sauvegarde en activant **Compresser la sauvegarde**, et vous pouvez empêcher la compression en activant **Ne pas compresser la sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="74e87-174">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="74e87-175">**Pour consulter la valeur par défaut de compression de la sauvegarde actuelle**</span><span class="sxs-lookup"><span data-stu-id="74e87-175">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="74e87-176">Afficher ou configurer la compression par défaut des sauvegardes (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="74e87-176">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="74e87-177">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74e87-177">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-backup-of-the-currently-active-transaction-log"></a><span data-ttu-id="74e87-178">Pour créer une sauvegarde du journal des transactions actif</span><span class="sxs-lookup"><span data-stu-id="74e87-178">To create a backup of the currently active transaction log</span></span>  
  
1.  <span data-ttu-id="74e87-179">Exécutez l'instruction BACKUP LOG pour sauvegarder le journal des transactions actif en cours, en spécifiant :</span><span class="sxs-lookup"><span data-stu-id="74e87-179">Execute the BACKUP LOG statement to back up the currently active transaction log, specifying:</span></span>  
  
    -   <span data-ttu-id="74e87-180">le nom de la base de données à laquelle appartient le journal des transactions à sauvegarder ;</span><span class="sxs-lookup"><span data-stu-id="74e87-180">The name of the database to which the transaction log to back up belongs.</span></span>  
  
    -   <span data-ttu-id="74e87-181">l'unité de sauvegarde dans laquelle sera écrite la sauvegarde du journal des transactions ;</span><span class="sxs-lookup"><span data-stu-id="74e87-181">The backup device where the transaction log backup will be written.</span></span>  
  
    -   <span data-ttu-id="74e87-182">la clause NO_TRUNCATE.</span><span class="sxs-lookup"><span data-stu-id="74e87-182">The NO_TRUNCATE clause.</span></span>  
  
         <span data-ttu-id="74e87-183">Cette clause permet la sauvegarde de la partie active du journal des transactions même si la base de données est inaccessible, à condition que le journal des transactions soit accessible et qu'il ne soit pas endommagé.</span><span class="sxs-lookup"><span data-stu-id="74e87-183">This clause allows the active part of the transaction log to be backed up even if the database is inaccessible, provided that the transaction log file is accessible and undamaged.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="74e87-184">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="74e87-184">Example (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74e87-185">Cet exemple utilise le mode de récupération simple, [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74e87-185">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], which uses the simple recovery model.</span></span> <span data-ttu-id="74e87-186">Pour autoriser les sauvegardes de fichier journal, avant d'effectuer une sauvegarde complète de base de données, la base de données a été configurée pour utiliser le mode de récupération complète.</span><span class="sxs-lookup"><span data-stu-id="74e87-186">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="74e87-187">Pour plus d’informations, consultez [Afficher ou modifier le mode de récupération d’une base de données &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74e87-187">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="74e87-188">Cet exemple sauvegarde le journal des transactions actif lorsqu'une base de données est endommagée et inaccessible, à la condition que le journal des transactions soit intact et accessible.</span><span class="sxs-lookup"><span data-stu-id="74e87-188">This example backs up the currently active transaction log when a database is damaged and inaccessible, if the transaction log is undamaged and accessible.</span></span>  
  
```scr  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1  
   WITH NO_TRUNCATE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="74e87-189"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74e87-189">See Also</span></span>  
 <span data-ttu-id="74e87-190">[Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="74e87-190">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="74e87-191">[Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="74e87-191">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="74e87-192">[Sauvegarder la base de données &#40;page Options de sauvegarde&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="74e87-192">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="74e87-193">[Sauvegarder la base de données &#40;page Général&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="74e87-193">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="74e87-194">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="74e87-194">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="74e87-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="74e87-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="74e87-196">[Restaurations de fichiers &#40;mode de récupération simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="74e87-196">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="74e87-197">Restaurations de fichiers &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="74e87-197">File Restores &#40;Full Recovery Model&#41;</span></span>](file-restores-full-recovery-model.md)  
  
  
