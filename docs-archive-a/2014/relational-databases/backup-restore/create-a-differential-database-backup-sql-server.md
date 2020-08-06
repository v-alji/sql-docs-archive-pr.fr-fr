---
title: Créer une sauvegarde différentielle de base de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- database backups [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
- backups [SQL Server], creating
ms.assetid: 70f49794-b217-4519-9f2a-76ed61fa9f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c3fb53d90ce633498bc518282d1ff03ce0b926e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614665"
---
# <a name="create-a-differential-database-backup-sql-server"></a><span data-ttu-id="8680f-102">Créer une sauvegarde différentielle de base de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8680f-102">Create a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="8680f-103">Cette rubrique explique comment créer une sauvegarde différentielle de base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8680f-103">This topic describes how to create a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8680f-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="8680f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8680f-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="8680f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8680f-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8680f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8680f-107">Composants requis</span><span class="sxs-lookup"><span data-stu-id="8680f-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="8680f-108">Recommandations</span><span class="sxs-lookup"><span data-stu-id="8680f-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="8680f-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8680f-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8680f-110">**Pour créer une sauvegarde différentielle de base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="8680f-110">**To create a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="8680f-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8680f-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8680f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8680f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8680f-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8680f-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8680f-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8680f-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8680f-115">L'instruction BACKUP n'est pas autorisée dans une transaction explicite ou implicite.</span><span class="sxs-lookup"><span data-stu-id="8680f-115">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="8680f-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="8680f-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="8680f-117">La création d'une sauvegarde différentielle de base de données suppose l'existence d'une sauvegarde complète de base de données préalable.</span><span class="sxs-lookup"><span data-stu-id="8680f-117">Creating a differential database backup requires that a previous full database backup exist.</span></span> <span data-ttu-id="8680f-118">Si la base de données sélectionnée n'a jamais été sauvegardée, exécutez une sauvegarde complète de base de données avant de créer des sauvegardes différentielles.</span><span class="sxs-lookup"><span data-stu-id="8680f-118">If the selected database has never been backed up, run a full database backup before creating any differential backups.</span></span> <span data-ttu-id="8680f-119">Pour plus d’informations, consultez [Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8680f-119">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="8680f-120">Recommandations</span><span class="sxs-lookup"><span data-stu-id="8680f-120">Recommendations</span></span>  
  
-   <span data-ttu-id="8680f-121">À mesure que la taille des sauvegardes différentielles augmente, la restauration d'une sauvegarde différentielle peut accroître considérablement le temps nécessaire à la restauration d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="8680f-121">As the differential backups increase in size, restoring a differential backup can significantly increase the time that is required to restore a database.</span></span> <span data-ttu-id="8680f-122">Nous vous recommandons donc d'effectuer une nouvelle sauvegarde complète selon une périodicité fixe pour établir une nouvelle base différentielle des données.</span><span class="sxs-lookup"><span data-stu-id="8680f-122">Therefore, we recommend that you take a new full backup at set intervals to establish a new differential base for the data.</span></span> <span data-ttu-id="8680f-123">Par exemple, vous pouvez effectuer une sauvegarde complète hebdomadaire de la base de données dans son entier (soit une sauvegarde complète de la base de données), puis des séries régulières de sauvegardes de bases de données différentielles au cours de la semaine.</span><span class="sxs-lookup"><span data-stu-id="8680f-123">For example, you might take a weekly full backup of the whole database (that is, a full database backup) followed by a regular series of differential database backups during the week.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8680f-124">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8680f-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8680f-125">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8680f-125">Permissions</span></span>  
 <span data-ttu-id="8680f-126">Les autorisations BACKUP DATABASE et BACKUP LOG reviennent par défaut aux membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="8680f-126">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="8680f-127">Des problèmes de propriété et d'autorisations sur le fichier physique de l'unité de sauvegarde sont susceptibles de perturber une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8680f-127">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8680f-128">doit être en mesure de lire et d'écrire sur l'unité ; le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute doit avoir des autorisations d'écriture.</span><span class="sxs-lookup"><span data-stu-id="8680f-128">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="8680f-129">Toutefois, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), qui ajoute une entrée pour une unité de sauvegarde dans les tables système, ne vérifie pas les autorisations d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="8680f-129">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="8680f-130">De tels problèmes pour le fichier physique de l'unité de sauvegarde peuvent n'apparaître que lorsque la ressource physique est sollicitée au moment de la sauvegarde ou de la restauration.</span><span class="sxs-lookup"><span data-stu-id="8680f-130">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8680f-131">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8680f-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="8680f-132">Pour créer une sauvegarde différentielle de base de données</span><span class="sxs-lookup"><span data-stu-id="8680f-132">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="8680f-133">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="8680f-133">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="8680f-134">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="8680f-134">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="8680f-135">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**.</span><span class="sxs-lookup"><span data-stu-id="8680f-135">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="8680f-136">La boîte de dialogue **Sauvegarder la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="8680f-136">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="8680f-137">Dans la zone de liste **Base de données** , vérifiez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="8680f-137">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="8680f-138">Vous pouvez éventuellement sélectionner une autre base de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8680f-138">You can optionally select a different database from the list.</span></span>  
  
     <span data-ttu-id="8680f-139">Vous pouvez effectuer une sauvegarde différentielle pour n'importe quel mode de récupération (complet, simple ou utilisant les journaux de transactions).</span><span class="sxs-lookup"><span data-stu-id="8680f-139">You can perform a differential backup for any recovery model (full, bulk-logged, or simple).</span></span>  
  
5.  <span data-ttu-id="8680f-140">Dans la zone de liste **Type de sauvegarde** , sélectionnez **Différentielle**.</span><span class="sxs-lookup"><span data-stu-id="8680f-140">In the **Backup type** list box, select **Differential**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8680f-141">Lorsque l'option **Différentielle** est sélectionnée, vérifiez que la case à cocher **Sauvegarde de copie uniquement** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="8680f-141">When **Differential** is selected, verify that the **Copy Only Backup** check box is cleared.</span></span>  
  
6.  <span data-ttu-id="8680f-142">Pour l'option **Composant de sauvegarde**, cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="8680f-142">For **Backup component**, click **Database**.</span></span>  
  
7.  <span data-ttu-id="8680f-143">Acceptez le nom du jeu de sauvegarde par défaut proposé dans la zone de texte **Nom** , ou attribuez-lui un autre nom.</span><span class="sxs-lookup"><span data-stu-id="8680f-143">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
8.  <span data-ttu-id="8680f-144">Dans la zone de texte **Description** , vous avez la possibilité de saisir une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8680f-144">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
9. <span data-ttu-id="8680f-145">Indiquez quand le jeu de sauvegarde arrivera à expiration :</span><span class="sxs-lookup"><span data-stu-id="8680f-145">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="8680f-146">Pour que le jeu de sauvegarde expire au bout d’un nombre de jours spécifique, cliquez sur **Après** (option par défaut) et entrez le nombre de jours souhaité pour l’expiration du jeu après sa création.</span><span class="sxs-lookup"><span data-stu-id="8680f-146">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="8680f-147">Cette valeur doit être comprise entre 0 et 99999 jours ; une valeur de 0 jour signifie que le jeu de sauvegarde n'expirera jamais.</span><span class="sxs-lookup"><span data-stu-id="8680f-147">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="8680f-148">La valeur par défaut est définie dans l’option **Délai de rétention par défaut du support de sauvegarde (jours)** de la boîte de dialogue **Propriétés du serveur** (page**Paramètres de base de données** ).</span><span class="sxs-lookup"><span data-stu-id="8680f-148">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="8680f-149">Pour y accéder, cliquez avec le bouton droit sur le nom du serveur dans l’Explorateur d’objets et sélectionnez les propriétés. Ensuite, sélectionnez la page **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="8680f-149">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="8680f-150">Pour que le jeu de sauvegarde expire à une date spécifique, cliquez sur **Le**et entrez la date d'expiration souhaitée.</span><span class="sxs-lookup"><span data-stu-id="8680f-150">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
10. <span data-ttu-id="8680f-151">Choisissez le type de destination de la sauvegarde : **Disque** ou **Bande**.</span><span class="sxs-lookup"><span data-stu-id="8680f-151">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="8680f-152">Pour sélectionner le chemin d'accès des lecteurs de disque ou de bande (dans la limite de 64) contenant un support de sauvegarde unique, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8680f-152">To select the path of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="8680f-153">Les chemins d'accès sélectionnés apparaissent dans la zone de liste **Sauvegarde sur** .</span><span class="sxs-lookup"><span data-stu-id="8680f-153">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="8680f-154">Pour supprimer une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="8680f-154">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="8680f-155">Pour afficher le contenu d'une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Sommaire**.</span><span class="sxs-lookup"><span data-stu-id="8680f-155">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
11. <span data-ttu-id="8680f-156">Pour afficher ou sélectionner les options avancées, cliquez sur **Options** dans le volet **Sélectionner une page** .</span><span class="sxs-lookup"><span data-stu-id="8680f-156">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
12. <span data-ttu-id="8680f-157">Sélectionnez une option **Remplacer le support** en cliquant sur un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="8680f-157">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="8680f-158">**Sauvegarder sur le support de sauvegarde existant**</span><span class="sxs-lookup"><span data-stu-id="8680f-158">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="8680f-159">Pour cette option, cliquez sur **Ajouter au jeu de sauvegarde existant** ou sur **Remplacer tous les jeux de sauvegarde existants**.</span><span class="sxs-lookup"><span data-stu-id="8680f-159">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="8680f-160">Vous pouvez aussi activer la case à cocher **Vérifier le nom du support de sauvegarde et la date d'expiration du jeu de sauvegarde** puis entrer si vous le souhaitez un nom dans la zone de texte **Nom du support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="8680f-160">Optionally, check the **Check media set name and backup set expiration** check box and, optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="8680f-161">Si aucun nom n'est spécifié, un support de sauvegarde avec un nom vide est créé.</span><span class="sxs-lookup"><span data-stu-id="8680f-161">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="8680f-162">Si vous spécifiez un nom de support de sauvegarde, le système vérifie si le nom réel du support (bande ou disque) correspond au nom que vous entrez ici.</span><span class="sxs-lookup"><span data-stu-id="8680f-162">If you specify a media set name, the media (tape or disk) is checked to see if the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="8680f-163">Si vous n'entrez pas de nom et que vous activez la case à cocher pour demander la vérification par rapport au support, le nom du support sera également vide sur le support.</span><span class="sxs-lookup"><span data-stu-id="8680f-163">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="8680f-164">**Sauvegarder sur un nouveau support de sauvegarde et effacer tous les jeux de sauvegarde existants**</span><span class="sxs-lookup"><span data-stu-id="8680f-164">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="8680f-165">Pour cette option, entrez un nom dans la zone de texte **Nouveau nom du support de sauvegarde** et décrivez éventuellement le jeu de supports dans la zone de texte **Description du nouveau support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="8680f-165">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
13. <span data-ttu-id="8680f-166">Dans la section **Fiabilité** , vous pouvez éventuellement activer les cases à cocher :</span><span class="sxs-lookup"><span data-stu-id="8680f-166">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="8680f-167">**Vérifier la sauvegarde en fin d'opération**;</span><span class="sxs-lookup"><span data-stu-id="8680f-167">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="8680f-168">**Effectuer une somme de contrôle avant d'écrire sur le support**et éventuellement **Continuer lors d'erreurs de somme de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="8680f-168">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="8680f-169">Pour plus d’informations sur les sommes de contrôle, consultez [Erreurs de support possibles pendant les opérations de sauvegarde et de restauration &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8680f-169">For information about checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="8680f-170">Si vous effectuez la sauvegarde sur un lecteur de bande (spécifié dans la section **Destination** de la page **Général** ), l’option **Décharger la bande après la sauvegarde** est active.</span><span class="sxs-lookup"><span data-stu-id="8680f-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="8680f-171">Vous pouvez cliquer sur cette option pour activer l'option **Rembobiner la bande avant de décharger** .</span><span class="sxs-lookup"><span data-stu-id="8680f-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8680f-172">Les options de la section **Journal des transactions** sont inactives, à moins que vous ne sauvegardiez un journal des transactions (comme spécifié dans la section **Type de sauvegarde** de la page **Général** ).</span><span class="sxs-lookup"><span data-stu-id="8680f-172">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
15. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="8680f-173">et versions ultérieures prennent en charge la [compression de la sauvegarde](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8680f-173">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="8680f-174">Par défaut, la compression d’une sauvegarde dépend de la valeur de l’option de configuration de serveur **Compression par défaut des sauvegardes** .</span><span class="sxs-lookup"><span data-stu-id="8680f-174">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="8680f-175">Toutefois, quelle que soit la valeur par défaut actuelle au niveau du serveur, vous pouvez compresser une sauvegarde en activant **Compresser la sauvegarde**, et vous pouvez empêcher la compression en activant **Ne pas compresser la sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="8680f-175">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="8680f-176">**Pour consulter la valeur par défaut de compression de la sauvegarde actuelle**</span><span class="sxs-lookup"><span data-stu-id="8680f-176">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="8680f-177">Afficher ou configurer la compression par défaut des sauvegardes (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="8680f-177">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
    > [!NOTE]  
    >  <span data-ttu-id="8680f-178">Vous pouvez également utiliser l'Assistant Plan de maintenance pour créer des sauvegardes différentielles de base de données.</span><span class="sxs-lookup"><span data-stu-id="8680f-178">Alternatively, you can use the Maintenance Plan Wizard to create differential database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8680f-179">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8680f-179">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="8680f-180">Pour créer une sauvegarde différentielle de base de données</span><span class="sxs-lookup"><span data-stu-id="8680f-180">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="8680f-181">Exécutez l'instruction BACKUP DATABASE pour créer une sauvegarde différentielle de base de données, en spécifiant les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="8680f-181">Execute the BACKUP DATABASE statement to create the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="8680f-182">le nom de la base de données à sauvegarder ;</span><span class="sxs-lookup"><span data-stu-id="8680f-182">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="8680f-183">l'unité de sauvegarde où est écrite la sauvegarde complète de la base de données.</span><span class="sxs-lookup"><span data-stu-id="8680f-183">The backup device where the full database backup is written.</span></span>  
  
    -   <span data-ttu-id="8680f-184">la clause DIFFERENTIAL afin de préciser que seules les parties de la base de données qui ont été modifiées après la création de la dernière sauvegarde complète de la base de données sont sauvegardées.</span><span class="sxs-lookup"><span data-stu-id="8680f-184">The DIFFERENTIAL clause, to specify that only the parts of the database that have changed after the last full database backup was created are backed up.</span></span>  
  
     <span data-ttu-id="8680f-185">La syntaxe requise est la suivante :</span><span class="sxs-lookup"><span data-stu-id="8680f-185">The required syntax is:</span></span>  
  
     <span data-ttu-id="8680f-186">BACKUP DATABASE *nom_base_de_données* TO <appareil_sauvegarde> WITH DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="8680f-186">BACKUP DATABASE *database_name* TO <backup_device> WITH DIFFERENTIAL</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="8680f-187">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8680f-187">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="8680f-188">Cet exemple crée une sauvegarde complète et différentielle de la base de données `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="8680f-188">This example creates a full and a differential database backup for the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Create a full database backup first.  
BACKUP DATABASE MyAdvWorks   
   TO MyAdvWorks_1   
   WITH INIT;  
GO  
-- Time elapses.  
-- Create a differential database backup, appending the backup  
-- to the backup device containing the full database backup.  
BACKUP DATABASE MyAdvWorks  
   TO MyAdvWorks_1  
   WITH DIFFERENTIAL;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8680f-189"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8680f-189">See Also</span></span>  
 <span data-ttu-id="8680f-190">[Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8680f-190">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="8680f-191">[Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8680f-191">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="8680f-192">[Sauvegarder des fichiers et des groupes de fichiers &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8680f-192">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="8680f-193">[Restaurer une sauvegarde différentielle de base de données &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8680f-193">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="8680f-194">[Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8680f-194">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="8680f-195">[Plans de maintenance](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="8680f-195">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="8680f-196">Sauvegardes de fichiers complètes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8680f-196">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
  
  
