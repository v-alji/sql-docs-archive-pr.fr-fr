---
title: Restaurer des fichiers et des groupes de fichiers (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restorefilesandfilegrps.general.f1
- sql12.swb.restorefilesandfilegrps.options.f1
- sql12.swb.bselectfilegrpsfiles.f1
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], restoring files and filegroups
- restoring [SQL Server], files
ms.assetid: 72603b21-3065-4b56-8b01-11b707911b05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2576f1326cb50fa197b1623aaa1326d70137823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699803"
---
# <a name="restore-files-and-filegroups-sql-server"></a><span data-ttu-id="5f845-102">Restaurer des fichiers et des groupes de fichiers (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5f845-102">Restore Files and Filegroups (SQL Server)</span></span>
  <span data-ttu-id="5f845-103">Cette rubrique explique comment restaurer des fichiers et des groupes de fichiers dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f845-103">This topic describes how to restore files and filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5f845-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5f845-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5f845-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5f845-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5f845-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5f845-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="5f845-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5f845-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5f845-108">**Pour restaurer des fichiers et des groupes de fichiers, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5f845-108">**To restore files and filegroups, using:**</span></span>  
  
     [<span data-ttu-id="5f845-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f845-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5f845-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f845-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5f845-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5f845-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5f845-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5f845-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5f845-113">L’administrateur système restaurant les fichiers et groupes de fichiers doit être la seule personne utilisant la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="5f845-113">The system administrator restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="5f845-114">La commande RESTORE n'est pas autorisée dans une transaction explicite ou implicite.</span><span class="sxs-lookup"><span data-stu-id="5f845-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="5f845-115">En mode de récupération simple, le fichier doit appartenir à un groupe de fichiers en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5f845-115">Under the simple recovery model, the file must belong to a read-only filegroup.</span></span>  
  
-   <span data-ttu-id="5f845-116">Que vous soyez en mode de récupération complète ou en mode de récupération utilisant les journaux de transactions, pour pouvoir restaurer des fichiers, vous devez d'abord sauvegarder le journal des transactions actif (appelé fin du journal).</span><span class="sxs-lookup"><span data-stu-id="5f845-116">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="5f845-117">Pour plus d’informations, consultez [Sauvegarder un journal des transactions &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5f845-117">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="5f845-118">Pour restaurer une base de données chiffrée, vous devez avoir accès au certificat ou à la clé asymétrique qui a servi à chiffrer la base de données.</span><span class="sxs-lookup"><span data-stu-id="5f845-118">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="5f845-119">Sans le certificat et la clé asymétrique, la base de données ne peut pas être restaurée.</span><span class="sxs-lookup"><span data-stu-id="5f845-119">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="5f845-120">En conséquence, le certificat utilisé pour chiffrer la clé de chiffrement de base de données doit être conservé tant que la sauvegarde est utile.</span><span class="sxs-lookup"><span data-stu-id="5f845-120">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="5f845-121">Pour plus d'informations, consultez [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="5f845-121">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5f845-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5f845-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5f845-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5f845-123">Permissions</span></span>  
 <span data-ttu-id="5f845-124">Si la base de données restaurée n'existe pas, l'utilisateur doit posséder les autorisations CREATE DATABASE afin de pouvoir exécuter RESTORE.</span><span class="sxs-lookup"><span data-stu-id="5f845-124">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="5f845-125">Si la base de données existe, les autorisations RESTORE reviennent par défaut aux membres des rôles serveur fixe **sysadmin** et **dbcreator** et au propriétaire (**dbo**) de la base de données (pour l’option FROM DATABASE_SNAPSHOT, la base de données existe toujours).</span><span class="sxs-lookup"><span data-stu-id="5f845-125">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="5f845-126">Les autorisations RESTORE sont attribuées aux rôles dont les informations d'appartenance sont toujours immédiatement accessibles à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="5f845-126">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="5f845-127">Étant donné que l’appartenance au rôle de base de données fixe ne peut être contrôlée que quand la base de données est accessible et non endommagée, ce qui n’est pas toujours le cas lorsque RESTORE est exécuté, les membres du rôle de base de données fixe **db_owner** ne détiennent pas d’autorisations RESTORE.</span><span class="sxs-lookup"><span data-stu-id="5f845-127">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5f845-128">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f845-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="5f845-129">Pour restaurer des fichiers et des groupes de fichiers</span><span class="sxs-lookup"><span data-stu-id="5f845-129">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="5f845-130">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="5f845-130">After you connect to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="5f845-131">Développez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="5f845-131">Expand **Databases**.</span></span> <span data-ttu-id="5f845-132">Selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système**et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="5f845-132">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="5f845-133">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Restaurer**.</span><span class="sxs-lookup"><span data-stu-id="5f845-133">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="5f845-134">Cliquez sur **Fichiers et groupes de fichiers**pour ouvrir la boîte de dialogue **Restaurer des fichiers et des groupes de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="5f845-134">Click **Files and Filegroups**, which opens the **Restore Files and Filegroups** dialog box.</span></span>  
  
5.  <span data-ttu-id="5f845-135">Sur la page **Général** , dans la zone de liste **Vers la base de données** , entrez la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="5f845-135">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="5f845-136">Vous pouvez entrer une nouvelle base de données ou choisir une base de données existante dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="5f845-136">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="5f845-137">La liste contient toutes les bases de données sur le serveur, à l'exception des bases de données système **master** et **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="5f845-137">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
6.  <span data-ttu-id="5f845-138">Pour préciser la source et l'emplacement des jeux de sauvegarde à restaurer, cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f845-138">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="5f845-139">**À partir de la base de données**</span><span class="sxs-lookup"><span data-stu-id="5f845-139">**From database**</span></span>  
  
         <span data-ttu-id="5f845-140">Entrez un nom de base de données dans la zone de liste.</span><span class="sxs-lookup"><span data-stu-id="5f845-140">Enter a database name in the list box.</span></span> <span data-ttu-id="5f845-141">Cette liste ne contient que les bases de données ayant été sauvegardées d'après l'historique de sauvegarde de **msdb** .</span><span class="sxs-lookup"><span data-stu-id="5f845-141">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="5f845-142">**À partir de l'unité**</span><span class="sxs-lookup"><span data-stu-id="5f845-142">**From device**</span></span>  
  
         <span data-ttu-id="5f845-143">Cliquez sur le bouton de recherche.</span><span class="sxs-lookup"><span data-stu-id="5f845-143">Click the browse button.</span></span> <span data-ttu-id="5f845-144">Dans la boîte de dialogue **Spécifier les unités de sauvegarde** , sélectionnez l'un des types d'unités proposés dans la zone de liste **Type de support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="5f845-144">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="5f845-145">Pour sélectionner une ou plusieurs unités pour la zone de liste **Support de sauvegarde** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5f845-145">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="5f845-146">Après avoir ajouté les unités souhaitées à la zone de liste **Support de sauvegarde** , cliquez sur **OK** pour revenir à la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="5f845-146">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
7.  <span data-ttu-id="5f845-147">Dans la grille **Sélectionnez les jeux de sauvegarde à restaurer** , sélectionnez les sauvegardes à restaurer.</span><span class="sxs-lookup"><span data-stu-id="5f845-147">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="5f845-148">Cette grille affiche les sauvegardes disponibles pour l'emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f845-148">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="5f845-149">Par défaut, un plan de récupération est suggéré.</span><span class="sxs-lookup"><span data-stu-id="5f845-149">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="5f845-150">Pour ignorer le plan de récupération suggéré, vous pouvez modifier les sélections dans la grille.</span><span class="sxs-lookup"><span data-stu-id="5f845-150">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="5f845-151">Les sauvegardes qui dépendent d'une sauvegarde désélectionnée sont automatiquement désélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5f845-151">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="5f845-152">En-tête de colonne</span><span class="sxs-lookup"><span data-stu-id="5f845-152">Column head</span></span>|<span data-ttu-id="5f845-153">Valeurs</span><span class="sxs-lookup"><span data-stu-id="5f845-153">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="5f845-154">**Restauration**</span><span class="sxs-lookup"><span data-stu-id="5f845-154">**Restore**</span></span>|<span data-ttu-id="5f845-155">Les cases à cocher sélectionnées correspondent aux jeux de sauvegarde à restaurer.</span><span class="sxs-lookup"><span data-stu-id="5f845-155">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="5f845-156">**Nom**</span><span class="sxs-lookup"><span data-stu-id="5f845-156">**Name**</span></span>|<span data-ttu-id="5f845-157">Nom du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5f845-157">The name of the backup set.</span></span>|  
    |<span data-ttu-id="5f845-158">**Type de fichier**</span><span class="sxs-lookup"><span data-stu-id="5f845-158">**File Type**</span></span>|<span data-ttu-id="5f845-159">Spécifie le type des données figurant dans la sauvegarde : **Données**, **Journal**, ou **Données Filestream**.</span><span class="sxs-lookup"><span data-stu-id="5f845-159">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="5f845-160">Les données qui sont contenues dans les tables sont dans les fichiers **Données** .</span><span class="sxs-lookup"><span data-stu-id="5f845-160">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="5f845-161">Les données du journal des transactions sont dans les fichiers **Journaux** .</span><span class="sxs-lookup"><span data-stu-id="5f845-161">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="5f845-162">Les données des objets BLOB (Binary Large Object) qui sont stockées dans le système de fichiers se trouvent dans des fichiers **Données Filestream** .</span><span class="sxs-lookup"><span data-stu-id="5f845-162">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="5f845-163">**Type**</span><span class="sxs-lookup"><span data-stu-id="5f845-163">**Type**</span></span>|<span data-ttu-id="5f845-164">Type de sauvegarde effectuée : **Complète**, **Différentielle** ou **Journal des transactions**.</span><span class="sxs-lookup"><span data-stu-id="5f845-164">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="5f845-165">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="5f845-165">**Server**</span></span>|<span data-ttu-id="5f845-166">Nom de l'instance Base de données-Moteur ayant effectué l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5f845-166">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="5f845-167">**Nom logique du fichier**</span><span class="sxs-lookup"><span data-stu-id="5f845-167">**File Logical Name**</span></span>|<span data-ttu-id="5f845-168">Comme son nom l'indique.</span><span class="sxs-lookup"><span data-stu-id="5f845-168">The logical name of the file.</span></span>|  
    |<span data-ttu-id="5f845-169">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="5f845-169">**Database**</span></span>|<span data-ttu-id="5f845-170">Nom de la base de données impliquée dans la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5f845-170">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="5f845-171">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="5f845-171">**Start Date**</span></span>|<span data-ttu-id="5f845-172">Date et heure de lancement de l'opération de sauvegarde, présentée conformément aux paramètres régionaux du client.</span><span class="sxs-lookup"><span data-stu-id="5f845-172">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="5f845-173">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="5f845-173">**Finish Date**</span></span>|<span data-ttu-id="5f845-174">Date et heure de fin de l'opération de sauvegarde, exprimée d'après les paramètres régionaux du client.</span><span class="sxs-lookup"><span data-stu-id="5f845-174">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="5f845-175">**Taille**</span><span class="sxs-lookup"><span data-stu-id="5f845-175">**Size**</span></span>|<span data-ttu-id="5f845-176">Taille du jeu de sauvegarde, exprimée en octets.</span><span class="sxs-lookup"><span data-stu-id="5f845-176">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="5f845-177">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="5f845-177">**User Name**</span></span>|<span data-ttu-id="5f845-178">Nom de l'utilisateur qui a exécuté l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5f845-178">The name of the user who performed the backup operation.</span></span>|  
  
8.  <span data-ttu-id="5f845-179">Pour afficher ou sélectionner les options avancées, cliquez sur **Options** dans le volet **Sélectionner une page**.</span><span class="sxs-lookup"><span data-stu-id="5f845-179">To view or select the advanced options, click **Options** in the **Select a page pane**.</span></span>  
  
9. <span data-ttu-id="5f845-180">Dans le panneau **Options de restauration** , choisissez les options suivantes si elles s'appliquent à votre situation.</span><span class="sxs-lookup"><span data-stu-id="5f845-180">In the **Restore options** panel, you can choose any of the following options, if appropriate for your situation.</span></span>  
  
     <span data-ttu-id="5f845-181">**Restaurer en tant que groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="5f845-181">**Restore as filegroup**</span></span>  
     <span data-ttu-id="5f845-182">Indique qu'un groupe de fichiers entier doit être restauré.</span><span class="sxs-lookup"><span data-stu-id="5f845-182">Indicates that an entire filegroup is being restored.</span></span>  
  
     <span data-ttu-id="5f845-183">**Remplacer la base de données existante**</span><span class="sxs-lookup"><span data-stu-id="5f845-183">**Overwrite the existing database**</span></span>  
     <span data-ttu-id="5f845-184">Indique que la restauration doit remplacer les bases de données existantes et leurs fichiers associés, même si une autre base de données ou un autre fichier existant porte le même nom.</span><span class="sxs-lookup"><span data-stu-id="5f845-184">Specifies that the restore operation should overwrite any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
     <span data-ttu-id="5f845-185">L'activation de cette option revient à utiliser l'option REPLACE dans une instruction RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f845-185">Selecting this option is equivalent to using the REPLACE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="5f845-186">**Demander confirmation avant chaque restauration de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="5f845-186">**Prompt before restoring each backup**</span></span>  
     <span data-ttu-id="5f845-187">Demande une confirmation avant la restauration de chaque jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5f845-187">Asks you for confirmation before restoring each backup set.</span></span>  
  
     <span data-ttu-id="5f845-188">Cette option est particulièrement utile lorsque vous devez permuter des jeux de supports différents, lorsque, par exemple, le serveur n'a qu'un seul périphérique à bandes.</span><span class="sxs-lookup"><span data-stu-id="5f845-188">This option is particularly useful where you must swap tapes for different media sets, such as when the server has one tape device.</span></span>  
  
     <span data-ttu-id="5f845-189">**Restreindre l'accès à la base de données restaurée**</span><span class="sxs-lookup"><span data-stu-id="5f845-189">**Restrict access to the restored database**</span></span>  
     <span data-ttu-id="5f845-190">Limite l’accès à la base de données restaurée aux membres de **db_owner**, **dbcreator**ou **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="5f845-190">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
     <span data-ttu-id="5f845-191">La sélection de cette option équivaut à utiliser l'option RESTRICTED_USER dans une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE.</span><span class="sxs-lookup"><span data-stu-id="5f845-191">Selecting this option is synonymous to using the RESTRICTED_USER option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
10. <span data-ttu-id="5f845-192">Le cas échéant, vous pouvez restaurer la base de données vers un nouvel emplacement, en spécifiant une nouvelle destination de restauration pour chaque fichier dans la grille **Restaurer les fichiers de la base de données en tant que** .</span><span class="sxs-lookup"><span data-stu-id="5f845-192">Optionally, you can restore the database to a new location by specifying a new restore destination for each file in the **Restore database files as** grid.</span></span>  
  
    |<span data-ttu-id="5f845-193">En-tête de colonne</span><span class="sxs-lookup"><span data-stu-id="5f845-193">Column head</span></span>|<span data-ttu-id="5f845-194">Valeurs</span><span class="sxs-lookup"><span data-stu-id="5f845-194">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="5f845-195">**Nom du fichier d'origine**</span><span class="sxs-lookup"><span data-stu-id="5f845-195">**Original File Name**</span></span>|<span data-ttu-id="5f845-196">Chemin d'accès complet d'un fichier de sauvegarde source.</span><span class="sxs-lookup"><span data-stu-id="5f845-196">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="5f845-197">**Type de fichier**</span><span class="sxs-lookup"><span data-stu-id="5f845-197">**File Type**</span></span>|<span data-ttu-id="5f845-198">Spécifie le type des données figurant dans la sauvegarde : **Données**, **Journal**, ou **Données Filestream**.</span><span class="sxs-lookup"><span data-stu-id="5f845-198">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="5f845-199">Les données qui sont contenues dans les tables sont dans les fichiers **Données** .</span><span class="sxs-lookup"><span data-stu-id="5f845-199">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="5f845-200">Les données du journal des transactions sont dans les fichiers **Journaux** .</span><span class="sxs-lookup"><span data-stu-id="5f845-200">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="5f845-201">Les données des objets BLOB (Binary Large Object) qui sont stockées dans le système de fichiers se trouvent dans des fichiers **Données Filestream** .</span><span class="sxs-lookup"><span data-stu-id="5f845-201">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="5f845-202">**Restaurer sous**</span><span class="sxs-lookup"><span data-stu-id="5f845-202">**Restore As**</span></span>|<span data-ttu-id="5f845-203">Chemin d'accès complet du fichier de base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="5f845-203">The full path of the database file to be restored.</span></span> <span data-ttu-id="5f845-204">Pour définir un nouveau fichier de restauration, cliquez sur la zone de texte et modifiez le chemin d'accès et le nom de fichier proposés.</span><span class="sxs-lookup"><span data-stu-id="5f845-204">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="5f845-205">La modification du chemin d'accès ou du nom de fichier dans la colonne **Restaurer sous** équivaut à utiliser l'option MOVE dans une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE.</span><span class="sxs-lookup"><span data-stu-id="5f845-205">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
11. <span data-ttu-id="5f845-206">Le volet **État de récupération** détermine l'état de la base de données à l'issue de l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="5f845-206">The **Recovery state** panel determines the state of the database after the restore operation.</span></span>  
  
     <span data-ttu-id="5f845-207">**Laisser la base de données opérationnelle en restaurant les transactions non validées. Les journaux des transactions supplémentaires ne peuvent pas être restaurés. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="5f845-207">**Leave the database ready for use by rolling back the uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
     <span data-ttu-id="5f845-208">Récupère la base de données.</span><span class="sxs-lookup"><span data-stu-id="5f845-208">Recovers the database.</span></span> <span data-ttu-id="5f845-209">Il s'agit du comportement par défaut.</span><span class="sxs-lookup"><span data-stu-id="5f845-209">This is the default behavior.</span></span> <span data-ttu-id="5f845-210">Ne choisissez cette option que si vous restaurez toutes les sauvegardes nécessaires maintenant.</span><span class="sxs-lookup"><span data-stu-id="5f845-210">Choose this option only if you are restoring all of the necessary backups now.</span></span> <span data-ttu-id="5f845-211">Cette option revient à spécifier WITH RECOVERY dans une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE.</span><span class="sxs-lookup"><span data-stu-id="5f845-211">This option is equivalent to specifying WITH RECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="5f845-212">**Laisser la base de données non opérationnelle, et ne pas restaurer les transactions non validées. Les journaux des transactions supplémentaires peuvent être restaurés. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="5f845-212">**Leave the database non-operational, and don't roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
     <span data-ttu-id="5f845-213">Laisse la base de données en état de restauration.</span><span class="sxs-lookup"><span data-stu-id="5f845-213">Leaves the database in the restoring state.</span></span> <span data-ttu-id="5f845-214">Pour restaurer la base de données, vous devez exécuter une autre restauration en utilisant l'option RESTORE WITH RECOVERY précédente (voir ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="5f845-214">To recover the database, you will need to perform another restore using the preceding RESTORE WITH RECOVERY option (see above).</span></span> <span data-ttu-id="5f845-215">Cette option revient à spécifier WITH NORECOVERY dans une instruction RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f845-215">This option is equivalent to specifying WITH NORECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="5f845-216">Si vous sélectionnez cette option, l'option **Conserver les paramètres de réplication** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="5f845-216">If you select this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
     <span data-ttu-id="5f845-217">**Laisser la base de données en lecture seule. Annulez les transactions non validées, mais enregistrez l'opération d'annulation dans un fichier pour pouvoir annuler les effets de la restauration. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="5f845-217">**Leave the database in read-only mode. Roll back the uncommitted transactions, but save the rollback operation in a file so the recovery effects can be undone. (RESTORE WITH STANDBY)**</span></span>  
     <span data-ttu-id="5f845-218">Laisse la base de données dans un état de secours.</span><span class="sxs-lookup"><span data-stu-id="5f845-218">Leaves the database in a standby state.</span></span> <span data-ttu-id="5f845-219">Cette option revient à spécifier WITH STANDBY dans une instruction RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f845-219">This option is equivalent to specifying WITH STANDBY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="5f845-220">Cette option nécessite de définir un fichier d'annulation.</span><span class="sxs-lookup"><span data-stu-id="5f845-220">Choosing this option requires that you specify a standby file.</span></span>  
  
     <span data-ttu-id="5f845-221">**Fichier journal des annulations de la restauration**</span><span class="sxs-lookup"><span data-stu-id="5f845-221">**Rollback undo file**</span></span>  
     <span data-ttu-id="5f845-222">Définissez un fichier d’annulation dans la zone de texte **Fichier journal des annulations de la restauration** .</span><span class="sxs-lookup"><span data-stu-id="5f845-222">Specify a standby file name in the **Rollback undo file** text box.</span></span> <span data-ttu-id="5f845-223">Cette option est nécessaire si vous laissez la base de données en lecture seule (RESTORE WITH STANDBY).</span><span class="sxs-lookup"><span data-stu-id="5f845-223">This option is required if you leave the database in read-only mode (RESTORE WITH STANDBY).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5f845-224">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f845-224">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="5f845-225">Pour restaurer des fichiers et des groupes de fichiers</span><span class="sxs-lookup"><span data-stu-id="5f845-225">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="5f845-226">Exécutez l’instruction RESTORE DATABASE pour restaurer la sauvegarde du fichier ou du groupe de fichiers, en spécifiant :</span><span class="sxs-lookup"><span data-stu-id="5f845-226">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="5f845-227">le nom de la base de données à restaurer ;</span><span class="sxs-lookup"><span data-stu-id="5f845-227">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="5f845-228">l'unité de sauvegarde à partir de laquelle sera restaurée la sauvegarde complète de la base de données ;</span><span class="sxs-lookup"><span data-stu-id="5f845-228">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="5f845-229">La clause FILE pour chaque fichier à restaurer.</span><span class="sxs-lookup"><span data-stu-id="5f845-229">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="5f845-230">La clause FILEGROUP pour chaque groupe de fichiers à restaurer.</span><span class="sxs-lookup"><span data-stu-id="5f845-230">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="5f845-231">la clause NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5f845-231">The NORECOVERY clause.</span></span> <span data-ttu-id="5f845-232">Si les fichiers n'ont pas été modifiés depuis la création de la sauvegarde, spécifiez la clause RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5f845-232">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="5f845-233">Si les fichiers ont été modifiés depuis la création de la sauvegarde du fichier, exécutez l'instruction RESTORE LOG pour appliquer la sauvegarde du journal des transactions, en spécifiant :</span><span class="sxs-lookup"><span data-stu-id="5f845-233">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="5f845-234">le nom de la base de données à laquelle sera appliqué le journal des transactions ;</span><span class="sxs-lookup"><span data-stu-id="5f845-234">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="5f845-235">l'unité de sauvegarde à partir de laquelle sera restaurée la sauvegarde du journal des transactions ;</span><span class="sxs-lookup"><span data-stu-id="5f845-235">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="5f845-236">la clause NORECOVERY si vous devez appliquer une autre sauvegarde du journal des transactions après la sauvegarde en cours. Dans les autres cas, spécifiez la clause RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5f845-236">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="5f845-237">Les sauvegardes du journal des transactions, lorsqu'elles sont appliquées, doivent couvrir la période de sauvegarde des fichiers et groupes de fichiers jusqu'à la fin du journal (sauf si TOUS les fichiers de base de données sont restaurés).</span><span class="sxs-lookup"><span data-stu-id="5f845-237">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up until the end of log (unless ALL database files are restored).</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="5f845-238">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5f845-238">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="5f845-239">Cet exemple restaure les fichiers et les groupes de fichiers pour la base de données `MyDatabase` .</span><span class="sxs-lookup"><span data-stu-id="5f845-239">This example restores the files and filegroups for the `MyDatabase` database.</span></span> <span data-ttu-id="5f845-240">Pour restaurer la base de données à l'heure actuelle, deux journaux de transactions sont appliqués.</span><span class="sxs-lookup"><span data-stu-id="5f845-240">To restore the database to the current time, two transaction logs are applied.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyDatabase.  
RESTORE DATABASE MyDatabase  
   FILE = 'MyDatabase_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyDatabase_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyDatabase_1  
   WITH NORECOVERY;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f845-241"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f845-241">See Also</span></span>  
 <span data-ttu-id="5f845-242">[Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="5f845-242">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="5f845-243">[Sauvegarder des fichiers et des groupes de fichiers &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f845-243">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="5f845-244">[Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f845-244">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="5f845-245">[Sauvegarder un journal des transactions &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f845-245">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="5f845-246">[Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f845-246">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="5f845-247">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5f845-247">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
