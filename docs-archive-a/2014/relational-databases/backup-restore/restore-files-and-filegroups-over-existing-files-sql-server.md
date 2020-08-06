---
title: Restaurer des fichiers et groupes de fichiers en remplaçant des fichiers existants (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring files [SQL Server], how-to topics
- restoring files [SQL Server], steps
- file restores [SQL Server], how-to topics
- filegroups [SQL Server], restoring
- restoring filegroups [SQL Server]
- overwriting filegroups
- overwriting files
ms.assetid: 517e07eb-9685-4b06-90af-b1cc496700b7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc72ae3ae2472fe579755fa624e9af6953c7aed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604573"
---
# <a name="restore-files-and-filegroups-over-existing-files-sql-server"></a><span data-ttu-id="29cdd-102">Restaurer des fichiers et groupes de fichiers en remplaçant des fichiers existants (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="29cdd-102">Restore Files and Filegroups over Existing Files (SQL Server)</span></span>
  <span data-ttu-id="29cdd-103">Cette rubrique explique comment restaurer des fichiers et groupes de fichiers en remplaçant les fichiers existants dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29cdd-103">This topic describes how to restore files and filegroups over existing files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="29cdd-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="29cdd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="29cdd-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="29cdd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="29cdd-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="29cdd-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="29cdd-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="29cdd-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="29cdd-108">**Pour restaurer des fichiers et groupes de fichiers en remplaçant des fichiers existants, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="29cdd-108">**To restore files and filegroups over existing files, using:**</span></span>  
  
     [<span data-ttu-id="29cdd-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29cdd-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="29cdd-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29cdd-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29cdd-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="29cdd-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="29cdd-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="29cdd-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="29cdd-113">L’administrateur système chargé de restaurer les fichiers et groupes de fichiers doit être la seule personne utilisant la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="29cdd-113">The system administrator who is restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="29cdd-114">La commande RESTORE n'est pas autorisée dans une transaction explicite ou implicite.</span><span class="sxs-lookup"><span data-stu-id="29cdd-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="29cdd-115">Que vous soyez en mode de récupération complète ou en mode de récupération utilisant les journaux de transactions, pour pouvoir restaurer des fichiers, vous devez d'abord sauvegarder le journal des transactions actif (appelé fin du journal).</span><span class="sxs-lookup"><span data-stu-id="29cdd-115">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="29cdd-116">Pour plus d’informations, consultez [Sauvegarder un journal des transactions &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="29cdd-116">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="29cdd-117">Pour restaurer une base de données chiffrée, vous devez avoir accès au certificat ou à la clé asymétrique qui a servi à chiffrer la base de données.</span><span class="sxs-lookup"><span data-stu-id="29cdd-117">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="29cdd-118">Sans le certificat et la clé asymétrique, la base de données ne peut pas être restaurée.</span><span class="sxs-lookup"><span data-stu-id="29cdd-118">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="29cdd-119">En conséquence, le certificat utilisé pour chiffrer la clé de chiffrement de base de données doit être conservé tant que la sauvegarde est utile.</span><span class="sxs-lookup"><span data-stu-id="29cdd-119">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="29cdd-120">Pour plus d'informations, consultez [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="29cdd-120">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29cdd-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="29cdd-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="29cdd-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="29cdd-122">Permissions</span></span>  
 <span data-ttu-id="29cdd-123">Si la base de données restaurée n'existe pas, l'utilisateur doit posséder les autorisations CREATE DATABASE afin de pouvoir exécuter RESTORE.</span><span class="sxs-lookup"><span data-stu-id="29cdd-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="29cdd-124">Si la base de données existe, les autorisations RESTORE reviennent par défaut aux membres des rôles serveur fixe **sysadmin** et **dbcreator** et au propriétaire (**dbo**) de la base de données (pour l’option FROM DATABASE_SNAPSHOT, la base de données existe toujours).</span><span class="sxs-lookup"><span data-stu-id="29cdd-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="29cdd-125">Les autorisations RESTORE sont attribuées aux rôles dont les informations d'appartenance sont toujours immédiatement accessibles à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="29cdd-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="29cdd-126">Étant donné que l’appartenance au rôle de base de données fixe ne peut être contrôlée que quand la base de données est accessible et non endommagée, ce qui n’est pas toujours le cas lorsque RESTORE est exécuté, les membres du rôle de base de données fixe **db_owner** ne détiennent pas d’autorisations RESTORE.</span><span class="sxs-lookup"><span data-stu-id="29cdd-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="29cdd-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29cdd-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups-over-existing-files"></a><span data-ttu-id="29cdd-128">Pour restaurer des fichiers et groupes de fichiers en remplaçant des fichiers existants</span><span class="sxs-lookup"><span data-stu-id="29cdd-128">To restore files and filegroups over existing files</span></span>  
  
1.  <span data-ttu-id="29cdd-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], développez cette instance, puis développez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="29cdd-129">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="29cdd-130">Cliquez avec le bouton droit sur la base de données de votre choix, pointez sur **Tâches**et sur **Restaurer**, puis cliquez sur **Fichiers et groupes de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="29cdd-130">Right-click the database that you want, point to **Tasks**, point to **Restore**, and then click **Files and Filegroups**.</span></span>  
  
3.  <span data-ttu-id="29cdd-131">Sur la page **Général** , dans la zone de liste **Vers la base de données** , entrez la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="29cdd-131">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="29cdd-132">Vous pouvez entrer une nouvelle base de données ou choisir une base de données existante dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="29cdd-132">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="29cdd-133">La liste contient toutes les bases de données sur le serveur, à l'exception des bases de données système **master** et **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="29cdd-133">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
4.  <span data-ttu-id="29cdd-134">Pour préciser la source et l'emplacement des jeux de sauvegarde à restaurer, cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="29cdd-134">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="29cdd-135">**À partir de la base de données**</span><span class="sxs-lookup"><span data-stu-id="29cdd-135">**From database**</span></span>  
  
         <span data-ttu-id="29cdd-136">Entrez un nom de base de données dans la zone de liste.</span><span class="sxs-lookup"><span data-stu-id="29cdd-136">Enter a database name in the list box.</span></span> <span data-ttu-id="29cdd-137">Cette liste ne contient que les bases de données ayant été sauvegardées d'après l'historique de sauvegarde de **msdb** .</span><span class="sxs-lookup"><span data-stu-id="29cdd-137">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="29cdd-138">**À partir de l'unité**</span><span class="sxs-lookup"><span data-stu-id="29cdd-138">**From device**</span></span>  
  
         <span data-ttu-id="29cdd-139">Cliquez sur le bouton de recherche.</span><span class="sxs-lookup"><span data-stu-id="29cdd-139">Click the browse button.</span></span> <span data-ttu-id="29cdd-140">Dans la boîte de dialogue **Spécifier les unités de sauvegarde** , sélectionnez l'un des types d'unités proposés dans la zone de liste **Type de support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="29cdd-140">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="29cdd-141">Pour sélectionner une ou plusieurs unités pour la zone de liste **Support de sauvegarde** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="29cdd-141">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="29cdd-142">Après avoir ajouté les unités souhaitées à la zone de liste **Support de sauvegarde** , cliquez sur **OK** pour revenir à la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="29cdd-142">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
5.  <span data-ttu-id="29cdd-143">Dans la grille **Sélectionnez les jeux de sauvegarde à restaurer** , sélectionnez les sauvegardes à restaurer.</span><span class="sxs-lookup"><span data-stu-id="29cdd-143">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="29cdd-144">Cette grille affiche les sauvegardes disponibles pour l'emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="29cdd-144">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="29cdd-145">Par défaut, un plan de récupération est suggéré.</span><span class="sxs-lookup"><span data-stu-id="29cdd-145">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="29cdd-146">Pour ignorer le plan de récupération suggéré, vous pouvez modifier les sélections dans la grille.</span><span class="sxs-lookup"><span data-stu-id="29cdd-146">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="29cdd-147">Les sauvegardes qui dépendent d'une sauvegarde désélectionnée sont automatiquement désélectionnées.</span><span class="sxs-lookup"><span data-stu-id="29cdd-147">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="29cdd-148">En-tête de colonne</span><span class="sxs-lookup"><span data-stu-id="29cdd-148">Column head</span></span>|<span data-ttu-id="29cdd-149">Valeurs</span><span class="sxs-lookup"><span data-stu-id="29cdd-149">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="29cdd-150">**Restauration**</span><span class="sxs-lookup"><span data-stu-id="29cdd-150">**Restore**</span></span>|<span data-ttu-id="29cdd-151">Les cases à cocher sélectionnées correspondent aux jeux de sauvegarde à restaurer.</span><span class="sxs-lookup"><span data-stu-id="29cdd-151">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="29cdd-152">**Nom**</span><span class="sxs-lookup"><span data-stu-id="29cdd-152">**Name**</span></span>|<span data-ttu-id="29cdd-153">Nom du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="29cdd-153">The name of the backup set.</span></span>|  
    |<span data-ttu-id="29cdd-154">**Type de fichier**</span><span class="sxs-lookup"><span data-stu-id="29cdd-154">**File Type**</span></span>|<span data-ttu-id="29cdd-155">Spécifie le type des données figurant dans la sauvegarde : **Données**, **Journal**, ou **Données Filestream**.</span><span class="sxs-lookup"><span data-stu-id="29cdd-155">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="29cdd-156">Les données qui sont contenues dans les tables sont dans les fichiers **Données** .</span><span class="sxs-lookup"><span data-stu-id="29cdd-156">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="29cdd-157">Les données du journal des transactions sont dans les fichiers **Journaux** .</span><span class="sxs-lookup"><span data-stu-id="29cdd-157">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="29cdd-158">Les données des objets BLOB (Binary Large Object) qui sont stockées dans le système de fichiers se trouvent dans des fichiers **Données Filestream** .</span><span class="sxs-lookup"><span data-stu-id="29cdd-158">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="29cdd-159">**Type**</span><span class="sxs-lookup"><span data-stu-id="29cdd-159">**Type**</span></span>|<span data-ttu-id="29cdd-160">Type de sauvegarde effectuée : **Complète**, **Différentielle** ou **Journal des transactions**.</span><span class="sxs-lookup"><span data-stu-id="29cdd-160">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="29cdd-161">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="29cdd-161">**Server**</span></span>|<span data-ttu-id="29cdd-162">Nom de l'instance Base de données-Moteur ayant effectué l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="29cdd-162">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="29cdd-163">**Nom logique du fichier**</span><span class="sxs-lookup"><span data-stu-id="29cdd-163">**File Logical Name**</span></span>|<span data-ttu-id="29cdd-164">Comme son nom l'indique.</span><span class="sxs-lookup"><span data-stu-id="29cdd-164">The logical name of the file.</span></span>|  
    |<span data-ttu-id="29cdd-165">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="29cdd-165">**Database**</span></span>|<span data-ttu-id="29cdd-166">Nom de la base de données impliquée dans la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="29cdd-166">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="29cdd-167">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="29cdd-167">**Start Date**</span></span>|<span data-ttu-id="29cdd-168">Date et heure de lancement de l'opération de sauvegarde, présentée conformément aux paramètres régionaux du client.</span><span class="sxs-lookup"><span data-stu-id="29cdd-168">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="29cdd-169">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="29cdd-169">**Finish Date**</span></span>|<span data-ttu-id="29cdd-170">Date et heure de fin de l'opération de sauvegarde, exprimée d'après les paramètres régionaux du client.</span><span class="sxs-lookup"><span data-stu-id="29cdd-170">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="29cdd-171">**Taille**</span><span class="sxs-lookup"><span data-stu-id="29cdd-171">**Size**</span></span>|<span data-ttu-id="29cdd-172">Taille du jeu de sauvegarde, exprimée en octets.</span><span class="sxs-lookup"><span data-stu-id="29cdd-172">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="29cdd-173">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="29cdd-173">**User Name**</span></span>|<span data-ttu-id="29cdd-174">Nom de l'utilisateur qui a exécuté l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="29cdd-174">The name of the user who performed the backup operation.</span></span>|  
  
6.  <span data-ttu-id="29cdd-175">Dans le volet **Sélectionner une page** , cliquez sur la page **Options** .</span><span class="sxs-lookup"><span data-stu-id="29cdd-175">In the **Select a page** pane, click the **Options** page.</span></span>  
  
7.  <span data-ttu-id="29cdd-176">Dans le panneau **Options de restauration** , sélectionnez **Remplacer la base de données existante (WITH REPLACE)** .</span><span class="sxs-lookup"><span data-stu-id="29cdd-176">In the **Restore options** panel, select **Overwrite the existing database (WITH REPLACE)**.</span></span> <span data-ttu-id="29cdd-177">L'opération de restauration remplace les bases de données existantes et leurs fichiers associés, même si une autre base de données ou un autre fichier existant porte le même nom.</span><span class="sxs-lookup"><span data-stu-id="29cdd-177">The restore operation overwrites any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="29cdd-178">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29cdd-178">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups-over-existing-files"></a><span data-ttu-id="29cdd-179">Pour restaurer des fichiers et groupes de fichiers en remplaçant des fichiers existants</span><span class="sxs-lookup"><span data-stu-id="29cdd-179">To restore files and filegroups over existing files</span></span>  
  
1.  <span data-ttu-id="29cdd-180">Exécutez l’instruction RESTORE DATABASE pour restaurer la sauvegarde du fichier ou du groupe de fichiers, en spécifiant :</span><span class="sxs-lookup"><span data-stu-id="29cdd-180">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="29cdd-181">le nom de la base de données à restaurer ;</span><span class="sxs-lookup"><span data-stu-id="29cdd-181">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="29cdd-182">l'unité de sauvegarde à partir de laquelle sera restaurée la sauvegarde complète de la base de données ;</span><span class="sxs-lookup"><span data-stu-id="29cdd-182">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="29cdd-183">La clause FILE pour chaque fichier à restaurer.</span><span class="sxs-lookup"><span data-stu-id="29cdd-183">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="29cdd-184">La clause FILEGROUP pour chaque groupe de fichiers à restaurer.</span><span class="sxs-lookup"><span data-stu-id="29cdd-184">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="29cdd-185">L'option REPLACE pour spécifier que chaque fichier peut être restauré en écrasant des fichiers existants possédant le même nom et situés au même emplacement.</span><span class="sxs-lookup"><span data-stu-id="29cdd-185">The REPLACE option to specify that each file can be restored over existing files of the same name and location.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="29cdd-186">Utilisez cette option avec précaution.</span><span class="sxs-lookup"><span data-stu-id="29cdd-186">Use the REPLACE option cautiously.</span></span> <span data-ttu-id="29cdd-187">Pour plus d'informations, consultez .</span><span class="sxs-lookup"><span data-stu-id="29cdd-187">For more information, see .</span></span>  
  
    -   <span data-ttu-id="29cdd-188">l'option NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="29cdd-188">The NORECOVERY option.</span></span> <span data-ttu-id="29cdd-189">Si les fichiers n'ont pas été modifiés depuis la création de la sauvegarde, spécifiez la clause RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="29cdd-189">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="29cdd-190">Si les fichiers ont été modifiés depuis la création de la sauvegarde du fichier, exécutez l'instruction RESTORE LOG pour appliquer la sauvegarde du journal des transactions, en spécifiant :</span><span class="sxs-lookup"><span data-stu-id="29cdd-190">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="29cdd-191">le nom de la base de données à laquelle sera appliqué le journal des transactions ;</span><span class="sxs-lookup"><span data-stu-id="29cdd-191">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="29cdd-192">l'unité de sauvegarde à partir de laquelle sera restaurée la sauvegarde du journal des transactions ;</span><span class="sxs-lookup"><span data-stu-id="29cdd-192">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="29cdd-193">la clause NORECOVERY si vous devez appliquer une autre sauvegarde du journal des transactions après la sauvegarde en cours. Dans les autres cas, spécifiez la clause RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="29cdd-193">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="29cdd-194">Les sauvegardes du journal des transactions, lorsqu’elles sont appliquées, doivent couvrir le temps de sauvegarde des fichiers et groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="29cdd-194">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="29cdd-195">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="29cdd-195">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="29cdd-196">L'exemple suivant illustre la restauration des fichiers et des groupes de fichiers pour la base de données `MyNwind` , ainsi que le remplacement des fichiers existants qui portent le même nom.</span><span class="sxs-lookup"><span data-stu-id="29cdd-196">The following example restores the files and filegroups for the `MyNwind` database, and replaces any existing files of the same name.</span></span> <span data-ttu-id="29cdd-197">Deux journaux de transactions seront également appliqués pour restaurer la base de données à l'heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="29cdd-197">Two transaction logs will also be applied to restore the database to the current time.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyNwind.  
RESTORE DATABASE MyNwind  
   FILE = 'MyNwind_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyNwind_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyNwind_1  
   WITH NORECOVERY,  
   REPLACE;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="29cdd-198"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29cdd-198">See Also</span></span>  
 <span data-ttu-id="29cdd-199">[Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="29cdd-199">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="29cdd-200">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="29cdd-200">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="29cdd-201">[Restaurer des fichiers et des groupes de fichiers &#40;SQL Server&#41;](restore-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="29cdd-201">[Restore Files and Filegroups &#40;SQL Server&#41;](restore-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="29cdd-202">Copier des bases de données avec la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="29cdd-202">Copy Databases with Backup and Restore</span></span>](../databases/copy-databases-with-backup-and-restore.md)  
  
  
