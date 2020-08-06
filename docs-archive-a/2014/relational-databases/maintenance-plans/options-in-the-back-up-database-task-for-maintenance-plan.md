---
title: Sauvegarder la base de données, tâche (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.backup.f1
- sql12.swb.maint.maintplanproperties.logbackup.f1
helpviewer_keywords:
- Back Up Database Task dialog box
ms.assetid: ed1ef012-fa14-4ba5-bafe-d1527ba065b3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 952730f09deeede360dff5e2bd83f8cdc8a20a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603972"
---
# <a name="back-up-database-task-maintenance-plan"></a><span data-ttu-id="d58c0-102">Tâche Sauvegarder la base de données (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="d58c0-102">Back Up Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="d58c0-103">Utilisez la boîte de dialogue **Tâche Sauvegarder la base de données** pour ajouter une tâche de sauvegarde au plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="d58c0-103">Use the **Back Up Database Task** dialog to add a backup task to the maintenance plan.</span></span> <span data-ttu-id="d58c0-104">La sauvegarde de la base de données est importante pour pallier son endommagement possible à la suite d'une défaillance matérielle ou logicielle (ou d'erreurs des utilisateurs), en permettant sa restauration à partir d'une copie de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d58c0-104">Backing up the database is important in case of system or hardware failure (or user errors) that cause the database to be damaged in some way, thus requiring a backed-up copy to be restored.</span></span> <span data-ttu-id="d58c0-105">Cette tâche vous permet d'effectuer des sauvegardes des journaux des transactions, des sauvegardes de groupe de fichiers et de fichiers, des sauvegardes différentielles et complètes.</span><span class="sxs-lookup"><span data-stu-id="d58c0-105">This task allows you to perform full, differential, files and filegroups, and transaction log backups.</span></span>  
  
 <span data-ttu-id="d58c0-106">**Pour créer une tâche de sauvegarde de base de données**</span><span class="sxs-lookup"><span data-stu-id="d58c0-106">**To create a backup database task**</span></span>  
  
-   [<span data-ttu-id="d58c0-107">Créer un plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="d58c0-107">Create a Maintenance Plan</span></span>](create-a-maintenance-plan.md)  
  
## <a name="options"></a><span data-ttu-id="d58c0-108">Options</span><span class="sxs-lookup"><span data-stu-id="d58c0-108">Options</span></span>  
 <span data-ttu-id="d58c0-109">**Connection**</span><span class="sxs-lookup"><span data-stu-id="d58c0-109">**Connection**</span></span>  
 <span data-ttu-id="d58c0-110">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="d58c0-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="d58c0-111">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="d58c0-111">**New**</span></span>  
 <span data-ttu-id="d58c0-112">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="d58c0-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="d58c0-113">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d58c0-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="d58c0-114">**Bases de données**</span><span class="sxs-lookup"><span data-stu-id="d58c0-114">**Databases**</span></span>  
 <span data-ttu-id="d58c0-115">Spécifie les bases de données faisant l'objet de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="d58c0-115">Specify the databases affected by this task.</span></span> <span data-ttu-id="d58c0-116">Quand vous sélectionnez cette option, la liste déroulante comprend les options suivantes : **Toutes les bases de données**, **Toutes les bases de données système**, **Toutes les bases de données utilisateur**, **Ces bases de données**.</span><span class="sxs-lookup"><span data-stu-id="d58c0-116">When selected, the drop down list provides the following options: **All databases**, **All system databases**, **All user databases**, **These specific databases**.</span></span>  
  
 <span data-ttu-id="d58c0-117">**Toutes les bases de données**</span><span class="sxs-lookup"><span data-stu-id="d58c0-117">**All databases**</span></span>  
 <span data-ttu-id="d58c0-118">Génère un plan de maintenance qui exécute les tâches de maintenance sur toutes les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d58c0-118">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="d58c0-119">**Toutes les bases de données système (master, model et msdb)**</span><span class="sxs-lookup"><span data-stu-id="d58c0-119">**All system databases (master, msdb, model)**</span></span>  
 <span data-ttu-id="d58c0-120">Génère un plan de maintenance qui exécute les tâches de maintenance sur chacune des bases de données système de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d58c0-120">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span> <span data-ttu-id="d58c0-121">Aucune tâche de maintenance n'est exécutée sur les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d58c0-121">No maintenance tasks are run against user-created databases.</span></span>  
  
 <span data-ttu-id="d58c0-122">**Toutes les bases de données utilisateur (autre que master, model et msdb)**</span><span class="sxs-lookup"><span data-stu-id="d58c0-122">**All user databases (excluding master, model, msdb, tempdb)**</span></span>  
 <span data-ttu-id="d58c0-123">Génère un plan de maintenance qui exécute des tâches de maintenance sur toutes les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d58c0-123">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="d58c0-124">Aucune tâche de maintenance n'est exécutée sur les bases de données système de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d58c0-124">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
 <span data-ttu-id="d58c0-125">**Ces bases de données**</span><span class="sxs-lookup"><span data-stu-id="d58c0-125">**These databases**</span></span>  
 <span data-ttu-id="d58c0-126">Génère un plan de maintenance qui n'exécute les tâches de maintenance que sur les bases de données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="d58c0-126">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="d58c0-127">Si vous choisissez cette option, sélectionnez au moins une base de données.</span><span class="sxs-lookup"><span data-stu-id="d58c0-127">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="d58c0-128">**Type de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="d58c0-128">**Backup type**</span></span>  
 <span data-ttu-id="d58c0-129">Affiche le type de sauvegarde à effectuer.</span><span class="sxs-lookup"><span data-stu-id="d58c0-129">Shows the type of backup to be performed.</span></span>  
  
 <span data-ttu-id="d58c0-130">**Composant de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="d58c0-130">**Backup component**</span></span>  
 <span data-ttu-id="d58c0-131">Sélectionnez **Base de données** pour sauvegarder la totalité de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d58c0-131">Select **Database** to back up the entire database.</span></span> <span data-ttu-id="d58c0-132">Sélectionnez **Fichier et groupes de fichiers** pour sauvegarder seulement une partie de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d58c0-132">Select **File and filegroups** to back up only a portion of the database.</span></span> <span data-ttu-id="d58c0-133">Spécifiez ensuite le nom du fichier ou du groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d58c0-133">If selected, provide the file or filegroup name.</span></span> <span data-ttu-id="d58c0-134">Si vous avez sélectionné plusieurs bases de données dans la zone **Base de données** , ne spécifiez que **Bases de données** pour **Composant de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="d58c0-134">When multiple databases are selected in the **Databases** box, only specify **Databases** for the **Backup components**.</span></span> <span data-ttu-id="d58c0-135">Pour exécuter des sauvegardes de fichiers ou de groupes de fichiers, créez une tâche pour chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="d58c0-135">To perform file or filegroup backups, create a task for each database.</span></span>  
  
 <span data-ttu-id="d58c0-136">**Expiration du jeu de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="d58c0-136">**Backup set will expire**</span></span>  
 <span data-ttu-id="d58c0-137">Indique la date à laquelle le jeu de sauvegarde peut être écrasé par un autre jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d58c0-137">Specify when the backup set can be overwritten by another backup set.</span></span>  
  
 <span data-ttu-id="d58c0-138">**Sauvegarde sur**</span><span class="sxs-lookup"><span data-stu-id="d58c0-138">**Back up to**</span></span>  
 <span data-ttu-id="d58c0-139">Sauvegarde la base de données dans un fichier ou sur une bande.</span><span class="sxs-lookup"><span data-stu-id="d58c0-139">Back up the database to a file or to tape.</span></span> <span data-ttu-id="d58c0-140">Seuls les périphériques à bande connectés à l'ordinateur sur lequel figure la base de données sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="d58c0-140">Only tape devices attached to the computer containing the database are available.</span></span>  
  
 <span data-ttu-id="d58c0-141">**Sauvegarder les bases de données sur un ou plusieurs fichiers**</span><span class="sxs-lookup"><span data-stu-id="d58c0-141">**Back up databases across one or more files**</span></span>  
 <span data-ttu-id="d58c0-142">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue **Sélectionner la destination de la sauvegarde** , puis indiquez un ou plusieurs emplacements sur le disque ou sur un périphérique à bandes.</span><span class="sxs-lookup"><span data-stu-id="d58c0-142">Click **Add** to open the **Select Backup Destination** dialog box, and provide one or more a disk location, or tape device.</span></span>  
  
 <span data-ttu-id="d58c0-143">**Si des fichiers de sauvegarde existent**</span><span class="sxs-lookup"><span data-stu-id="d58c0-143">**If backup files exist**</span></span>  
 <span data-ttu-id="d58c0-144">Sélectionnez **Ajouter** pour ajouter cette sauvegarde à la fin du fichier.</span><span class="sxs-lookup"><span data-stu-id="d58c0-144">Select **Append** to add this backup to the end of the file.</span></span> <span data-ttu-id="d58c0-145">Sélectionnez **Remplacer**pour supprimer toutes les anciennes sauvegardes du fichier et les remplacer par la nouvelle.</span><span class="sxs-lookup"><span data-stu-id="d58c0-145">Select **Overwrite**, to remove any old backup in the file and replace them with this new backup.</span></span>  
  
 <span data-ttu-id="d58c0-146">**Créer un fichier de sauvegarde pour chaque base de données**</span><span class="sxs-lookup"><span data-stu-id="d58c0-146">**Create a backup file for every database**</span></span>  
 <span data-ttu-id="d58c0-147">Crée un fichier de sauvegarde à l'emplacement spécifié dans la zone Dossier.</span><span class="sxs-lookup"><span data-stu-id="d58c0-147">Create a backup file in the location specified in the folder box.</span></span> <span data-ttu-id="d58c0-148">Un fichier unique est créé pour chaque base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d58c0-148">One file will be created for each database selected.</span></span>  
  
 <span data-ttu-id="d58c0-149">**Créer un sous-répertoire pour chaque base de données**</span><span class="sxs-lookup"><span data-stu-id="d58c0-149">**Create a sub-directory for each database**</span></span>  
 <span data-ttu-id="d58c0-150">Sélectionnez cette option pour placer chaque base de données dans un sous-dossier.</span><span class="sxs-lookup"><span data-stu-id="d58c0-150">Select to place each database in a subfolder.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d58c0-151">Bien que les plans de maintenance puissent créer des sous-répertoires, les tâches de maintenance ne peuvent pas en supprimer.</span><span class="sxs-lookup"><span data-stu-id="d58c0-151">Although maintenance plans can create subdirectories, maintenance tasks cannot delete subdirectories.</span></span> <span data-ttu-id="d58c0-152">Cette fonctionnalité réduit la possibilité d'une attaque malveillante qui utilise la tâche de nettoyage de maintenance pour supprimer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="d58c0-152">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d58c0-153">Le sous-répertoire hérite les autorisations du répertoire parent.</span><span class="sxs-lookup"><span data-stu-id="d58c0-153">The subdirectory inherits permissions from the parent directory.</span></span> <span data-ttu-id="d58c0-154">Limitez les autorisations pour éviter les accès non autorisés.</span><span class="sxs-lookup"><span data-stu-id="d58c0-154">Restrict permissions to avoid unauthorized access.</span></span>  
  
 <span data-ttu-id="d58c0-155">**Folder**</span><span class="sxs-lookup"><span data-stu-id="d58c0-155">**Folder**</span></span>  
 <span data-ttu-id="d58c0-156">Spécifiez le dossier dans lequel seront placés les fichiers de base de données créés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="d58c0-156">Specify the folder to contain the automatically created database files.</span></span>  
  
 <span data-ttu-id="d58c0-157">**Extension du fichier de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="d58c0-157">**Backup file extension**</span></span>  
 <span data-ttu-id="d58c0-158">Spécifiez l'extension à utiliser pour les fichiers de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d58c0-158">Specify the extension to use for the backup files.</span></span> <span data-ttu-id="d58c0-159">La valeur par défaut est **.bak**.</span><span class="sxs-lookup"><span data-stu-id="d58c0-159">The default is **.bak**.</span></span>  
  
 <span data-ttu-id="d58c0-160">**Vérifier l'intégrité de la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="d58c0-160">**Verify backup integrity**</span></span>  
 <span data-ttu-id="d58c0-161">Vérifie si le jeu de sauvegarde est complet et que tous les volumes sont lisibles.</span><span class="sxs-lookup"><span data-stu-id="d58c0-161">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="d58c0-162">**Sauvegarder la fin du journal et laisser la base de données dans l'état de restauration**</span><span class="sxs-lookup"><span data-stu-id="d58c0-162">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="d58c0-163">Effectue une sauvegarde de journal comme dernière étape avant la restauration d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="d58c0-163">Perform a log backup as the last step before restoring a database.</span></span> <span data-ttu-id="d58c0-164">Pour plus d’informations, consultez [Sauvegardes de la fin du journal &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d58c0-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="d58c0-165">**Définir la compression de la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="d58c0-165">**Set backup compression**</span></span>  
 <span data-ttu-id="d58c0-166">Dans [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (ou une version ultérieure), sélectionnez l’une des valeurs de [compression de sauvegarde](../backup-restore/backup-compression-sql-server.md) suivantes :</span><span class="sxs-lookup"><span data-stu-id="d58c0-166">In [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (or a later version), select one the following [backup compression](../backup-restore/backup-compression-sql-server.md) values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d58c0-167">**Utiliser le paramètre du serveur par défaut**</span><span class="sxs-lookup"><span data-stu-id="d58c0-167">**Use the default server setting**</span></span>|<span data-ttu-id="d58c0-168">Cliquez sur cette option pour utiliser la valeur par défaut au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="d58c0-168">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="d58c0-169">Cette valeur par défaut est définie par l’option de configuration de serveur **Compression par défaut des sauvegardes** .</span><span class="sxs-lookup"><span data-stu-id="d58c0-169">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="d58c0-170">Pour plus d’informations sur l’affichage du paramétrage actuel de cette option, consultez [Afficher ou configurer l’option de configuration du serveur valeur par défaut de compression de la sauvegarde](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="d58c0-170">For information about how to view the current setting of this option,  see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="d58c0-171">**Compresser la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="d58c0-171">**Compress backup**</span></span>|<span data-ttu-id="d58c0-172">Cliquez sur cette option pour compresser la sauvegarde, indépendamment de la valeur par défaut au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="d58c0-172">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="d58c0-173">**\*\* Important \*\*** Par défaut, la compression augmente considérablement l’utilisation de l’UC et l’UC supplémentaire consommée par le processus de compression peut nuire aux opérations simultanées.</span><span class="sxs-lookup"><span data-stu-id="d58c0-173">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely affect concurrent operations.</span></span> <span data-ttu-id="d58c0-174">Par conséquent, il peut être préférable de créer une sauvegarde compressée de priorité basse dans une session où l’utilisation de l’UC est limitée par [Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="d58c0-174">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="d58c0-175">Pour plus d'informations, consultez [Utiliser Resource Governor pour limiter l’utilisation de l’UC par compression de la sauvegarde &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d58c0-175">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="d58c0-176">**Ne pas compresser la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="d58c0-176">**Do not compress backup**</span></span>|<span data-ttu-id="d58c0-177">Cliquez sur cette option pour créer une sauvegarde non compressée, indépendamment de la valeur par défaut au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="d58c0-177">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
 <span data-ttu-id="d58c0-178">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="d58c0-178">**View T-SQL**</span></span>  
 <span data-ttu-id="d58c0-179">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="d58c0-179">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d58c0-180">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="d58c0-180">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="d58c0-181">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="d58c0-181">New Connection Dialog Box</span></span>  
 <span data-ttu-id="d58c0-182">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="d58c0-182">**Connection name**</span></span>  
 <span data-ttu-id="d58c0-183">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="d58c0-183">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="d58c0-184">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="d58c0-184">**Select or enter a server name**</span></span>  
 <span data-ttu-id="d58c0-185">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="d58c0-185">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="d58c0-186">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="d58c0-186">**Refresh**</span></span>  
 <span data-ttu-id="d58c0-187">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="d58c0-187">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="d58c0-188">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="d58c0-188">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="d58c0-189">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="d58c0-189">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="d58c0-190">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="d58c0-190">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="d58c0-191">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="d58c0-191">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="d58c0-192">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="d58c0-192">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="d58c0-193">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d58c0-193">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="d58c0-194">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d58c0-194">This option is not available.</span></span>  
  
 <span data-ttu-id="d58c0-195">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="d58c0-195">**User name**</span></span>  
 <span data-ttu-id="d58c0-196">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="d58c0-196">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="d58c0-197">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d58c0-197">This option is not available.</span></span>  
  
 <span data-ttu-id="d58c0-198">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="d58c0-198">**Password**</span></span>  
 <span data-ttu-id="d58c0-199">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="d58c0-199">Provide a password to use when authenticating.</span></span> <span data-ttu-id="d58c0-200">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d58c0-200">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d58c0-201">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d58c0-201">See Also</span></span>  
 [<span data-ttu-id="d58c0-202">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d58c0-202">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  
  
