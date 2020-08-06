---
title: Sauvegarder un journal des transactions (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction log backups [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- backing up transaction logs [SQL Server], SQL Server Management Studio
ms.assetid: 3426b5eb-6327-4c7f-88aa-37030be69fbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b57ca40b08718cda5095249991e0d424e6593a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604593"
---
# <a name="back-up-a-transaction-log-sql-server"></a><span data-ttu-id="52f1d-102">Sauvegarder un journal des transactions (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="52f1d-102">Back Up a Transaction Log (SQL Server)</span></span>
  <span data-ttu-id="52f1d-103">Cette rubrique explique comment sauvegarder un journal des transactions dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)]ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52f1d-103">This topic describes how to back up a transaction log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="52f1d-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="52f1d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="52f1d-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="52f1d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="52f1d-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="52f1d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="52f1d-107">Recommandations</span><span class="sxs-lookup"><span data-stu-id="52f1d-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="52f1d-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="52f1d-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="52f1d-109">**Pour sauvegarder un journal des transactions, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="52f1d-109">**To back up a transaction log, using:**</span></span>  
  
     [<span data-ttu-id="52f1d-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="52f1d-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="52f1d-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="52f1d-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="52f1d-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="52f1d-112">PowerShell</span></span>](#PowerShellProcedure)  
  
    > [!NOTE]  
    >  <span data-ttu-id="52f1d-113"> Vous pouvez également utiliser l'[Assistant Plan de maintenance](../maintenance-plans/use-the-maintenance-plan-wizard.md)pour créer des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="52f1d-113">Alternatively, you can use the[Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md)to create backups.</span></span>  
  
-   [<span data-ttu-id="52f1d-114">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="52f1d-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="52f1d-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="52f1d-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="52f1d-116">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="52f1d-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="52f1d-117">L'instruction BACKUP n'est pas autorisée dans une transaction explicite ou implicite.</span><span class="sxs-lookup"><span data-stu-id="52f1d-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="52f1d-118">Recommandations</span><span class="sxs-lookup"><span data-stu-id="52f1d-118">Recommendations</span></span>  
  
-   <span data-ttu-id="52f1d-119">Si une base de données est configurée pour le mode de récupération complète ou le mode de récupération utilisant les journaux de transactions, vous devez sauvegarder le journal des transactions assez régulièrement pour protéger vos données et éviter une saturation de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="52f1d-119">If a database uses either the full or bulk-logged recovery model, you must back up the transaction log regularly enough to protect your data and to keep the transaction log from filling.</span></span> <span data-ttu-id="52f1d-120">Cela tronque le journal et prend en charge la restauration de la base de données à un point précis dans le temps.</span><span class="sxs-lookup"><span data-stu-id="52f1d-120">This truncates the log and supports restoring the database to a specific point in time.</span></span>  
  
-   <span data-ttu-id="52f1d-121">Par défaut, chaque opération de sauvegarde réussie ajoute une entrée au journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et au journal des événements système.</span><span class="sxs-lookup"><span data-stu-id="52f1d-121">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="52f1d-122">Si vous sauvegardez très fréquemment le journal, ces messages de réussite peuvent rapidement s'accumuler, créer des journaux d'erreurs très volumineux et compliquer la recherche d'autres messages.</span><span class="sxs-lookup"><span data-stu-id="52f1d-122">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="52f1d-123">Dans de tels cas, vous pouvez supprimer ces entrées de journal en utilisant l'indicateur de trace 3226 si aucun de vos scripts ne dépend de ces entrées.</span><span class="sxs-lookup"><span data-stu-id="52f1d-123">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="52f1d-124">Pour plus d’informations, consultez [Indicateurs de trace &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="52f1d-124">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="52f1d-125">Sécurité</span><span class="sxs-lookup"><span data-stu-id="52f1d-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="52f1d-126">Autorisations</span><span class="sxs-lookup"><span data-stu-id="52f1d-126">Permissions</span></span>  
 <span data-ttu-id="52f1d-127">Les autorisations BACKUP DATABASE et BACKUP LOG reviennent par défaut aux membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="52f1d-127">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="52f1d-128">Des problèmes de propriété et d'autorisations sur le fichier physique de l'unité de sauvegarde sont susceptibles de perturber une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52f1d-128">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="52f1d-129">doit être en mesure de lire et d'écrire sur l'unité ; le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute doit avoir des autorisations d'écriture.</span><span class="sxs-lookup"><span data-stu-id="52f1d-129">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="52f1d-130">Toutefois, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), qui ajoute une entrée pour une unité de sauvegarde dans les tables système, ne vérifie pas les autorisations d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="52f1d-130">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="52f1d-131">De tels problèmes pour le fichier physique de l'unité de sauvegarde peuvent n'apparaître que lorsque la ressource physique est sollicitée au moment de la sauvegarde ou de la restauration.</span><span class="sxs-lookup"><span data-stu-id="52f1d-131">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="52f1d-132">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="52f1d-132">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="52f1d-133">Pour sauvegarder un journal des transactions</span><span class="sxs-lookup"><span data-stu-id="52f1d-133">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="52f1d-134">Après vous être connecté à l'instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], dans l'Explorateur d'objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="52f1d-134">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="52f1d-135">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="52f1d-135">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="52f1d-136">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-136">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="52f1d-137">La boîte de dialogue **Sauvegarder la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="52f1d-137">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="52f1d-138">Dans la zone de liste **Base de données** , vérifiez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="52f1d-138">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="52f1d-139">Vous pouvez éventuellement sélectionner une autre base de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="52f1d-139">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="52f1d-140">Vérifiez que le mode de récupération est **FULL** ou **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-140">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="52f1d-141">Dans la zone de liste **Type de sauvegarde** , sélectionnez **Journal des transactions**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-141">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="52f1d-142">Vous pouvez si vous le souhaitez sélectionner **Sauvegarde de copie uniquement** pour créer une sauvegarde de copie uniquement.</span><span class="sxs-lookup"><span data-stu-id="52f1d-142">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="52f1d-143">Une *sauvegarde de copie uniquement* est une sauvegarde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indépendante du mécanisme des sauvegardes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conventionnelles.</span><span class="sxs-lookup"><span data-stu-id="52f1d-143">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="52f1d-144">Pour plus d’informations, consultez [Sauvegardes de copie uniquement &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52f1d-144">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="52f1d-145">Lorsque l'option **Différentielle** est sélectionnée, vous ne pouvez pas créer de sauvegarde de copie uniquement.</span><span class="sxs-lookup"><span data-stu-id="52f1d-145">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="52f1d-146">Acceptez le nom du jeu de sauvegarde par défaut proposé dans la zone de texte **Nom** , ou attribuez-lui un autre nom.</span><span class="sxs-lookup"><span data-stu-id="52f1d-146">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="52f1d-147">Dans la zone de texte **Description** , vous avez la possibilité de saisir une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52f1d-147">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
10. <span data-ttu-id="52f1d-148">Indiquez quand le jeu de sauvegarde arrivera à expiration :</span><span class="sxs-lookup"><span data-stu-id="52f1d-148">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="52f1d-149">Pour que le jeu de sauvegarde expire au bout d’un nombre de jours spécifique, cliquez sur **Après** (option par défaut) et entrez le nombre de jours souhaité pour l’expiration du jeu après sa création.</span><span class="sxs-lookup"><span data-stu-id="52f1d-149">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="52f1d-150">Cette valeur doit être comprise entre 0 et 99999 jours ; une valeur de 0 jour signifie que le jeu de sauvegarde n'expirera jamais.</span><span class="sxs-lookup"><span data-stu-id="52f1d-150">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="52f1d-151">La valeur par défaut est définie dans l’option **Délai de rétention par défaut du support de sauvegarde (jours)** de la boîte de dialogue **Propriétés du serveur** (page**Paramètres de base de données** ).</span><span class="sxs-lookup"><span data-stu-id="52f1d-151">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="52f1d-152">Pour accéder à cette base de données, cliquez avec le bouton droit sur le nom du serveur dans l’Explorateur d’objets et sélectionnez Propriétés. Ensuite, sélectionnez la page **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="52f1d-152">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="52f1d-153">Pour que le jeu de sauvegarde expire à une date spécifique, cliquez sur **Le**et entrez la date d'expiration souhaitée.</span><span class="sxs-lookup"><span data-stu-id="52f1d-153">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="52f1d-154">Choisissez le type de destination de la sauvegarde en cliquant sur **Disque**, **URL** ou **Bande**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-154">Choose the type of backup destination by clicking **Disk**, **URL** or **Tape**.</span></span> <span data-ttu-id="52f1d-155">Pour sélectionner les chemins d'accès à 64 lecteurs de bande ou de disque au maximum contenant un seul support de sauvegarde, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-155">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="52f1d-156">Les chemins d'accès sélectionnés apparaissent dans la zone de liste **Sauvegarde sur** .</span><span class="sxs-lookup"><span data-stu-id="52f1d-156">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="52f1d-157">Pour supprimer une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-157">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="52f1d-158">Pour afficher le contenu d'une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Sommaire**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-158">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="52f1d-159">Pour afficher ou sélectionner les options avancées, cliquez sur **Options** dans le volet **Sélectionner une page** .</span><span class="sxs-lookup"><span data-stu-id="52f1d-159">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="52f1d-160">Sélectionnez une option **Remplacer le support** en cliquant sur un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="52f1d-160">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="52f1d-161">**Sauvegarder sur le support de sauvegarde existant**</span><span class="sxs-lookup"><span data-stu-id="52f1d-161">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="52f1d-162">Pour cette option, cliquez sur **Ajouter au jeu de sauvegarde existant** ou sur **Remplacer tous les jeux de sauvegarde existants**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-162">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="52f1d-163">Pour plus d’informations, consultez [Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52f1d-163">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="52f1d-164">Vous pouvez aussi activer la case à cocher **Vérifier le nom du support de sauvegarde et la date d'expiration du jeu de sauvegarde** pour forcer l'opération de sauvegarde à vérifier la date et l'heure de l'expiration du jeu de supports ou du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="52f1d-164">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="52f1d-165">Vous pouvez éventuellement entrer un nom dans la zone de texte **Nom du support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="52f1d-165">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="52f1d-166">Si aucun nom n'est spécifié, un support de sauvegarde avec un nom vide est créé.</span><span class="sxs-lookup"><span data-stu-id="52f1d-166">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="52f1d-167">Si vous spécifiez un nom pour le support de sauvegarde, ce support (bande ou disque) est vérifié pour voir si le nom réel correspond bien au nom que vous entrez ici.</span><span class="sxs-lookup"><span data-stu-id="52f1d-167">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="52f1d-168">Si vous n'entrez pas de nom et que vous activez la case à cocher pour demander la vérification par rapport au support, le nom du support sera également vide sur le support.</span><span class="sxs-lookup"><span data-stu-id="52f1d-168">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="52f1d-169">**Sauvegarder sur un nouveau support de sauvegarde et effacer tous les jeux de sauvegarde existants**</span><span class="sxs-lookup"><span data-stu-id="52f1d-169">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="52f1d-170">Pour cette option, entrez un nom dans la zone de texte **Nouveau nom du support de sauvegarde** et décrivez éventuellement le jeu de supports dans la zone de texte **Description du nouveau support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="52f1d-170">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span> <span data-ttu-id="52f1d-171">Pour plus d’informations, consultez [Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52f1d-171">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
14. <span data-ttu-id="52f1d-172">Dans la section **Fiabilité** , vous pouvez éventuellement activer les cases à cocher :</span><span class="sxs-lookup"><span data-stu-id="52f1d-172">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="52f1d-173">**Vérifier la sauvegarde en fin d'opération**;</span><span class="sxs-lookup"><span data-stu-id="52f1d-173">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="52f1d-174">**Effectuer une somme de contrôle avant d'écrire sur le support**et éventuellement **Continuer lors d'erreurs de somme de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-174">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="52f1d-175">Pour plus d’informations sur les sommes de contrôle, consultez [Erreurs de support possibles pendant les opérations de sauvegarde et de restauration &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52f1d-175">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="52f1d-176">Dans la section **Journal des transactions** :</span><span class="sxs-lookup"><span data-stu-id="52f1d-176">In the **Transaction log** section:</span></span>  
  
    -   <span data-ttu-id="52f1d-177">Pour les sauvegardes normales du journal, conservez la sélection par défaut, **Tronquer le journal des transactions en supprimant les entrées inactives**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-177">For routine log backups, keep the default selection, **Truncate the transaction log by removing inactive entries**.</span></span>  
  
    -   <span data-ttu-id="52f1d-178">Pour sauvegarder la fin du journal (autrement dit le journal actif), cochez la case **Sauvegarder la fin du journal et laisser la base de données dans l’état de restauration**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-178">To back up the tail of the log (that is, the active log), check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
         <span data-ttu-id="52f1d-179">Une sauvegarde de la fin du journal est effectuée après une défaillance pour éviter de perdre des données.</span><span class="sxs-lookup"><span data-stu-id="52f1d-179">A tail-log backup is taken after a failure to back up the tail of the log in order to prevent work loss.</span></span> <span data-ttu-id="52f1d-180">Sauvegardez le journal actif (sauvegarde de la fin du journal) après une défaillance, avant de commencer la restauration de la base de données ou en cas de basculement sur une base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="52f1d-180">Back up the active log (a tail-log backup) both after a failure, before beginning to restore the database, or when failing over to a secondary database.</span></span> <span data-ttu-id="52f1d-181">Sélectionner cette option équivaut à spécifier l'option NORECOVERY dans l'instruction BACKUP LOG de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="52f1d-181">Selecting this option is equivalent to specifying the NORECOVERY option in the BACKUP LOG statement of Transact-SQL.</span></span> <span data-ttu-id="52f1d-182">Pour plus d’informations sur les sauvegardes de la fin du journal, consultez [Sauvegardes de la fin du journal &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52f1d-182">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
16. <span data-ttu-id="52f1d-183">Si vous effectuez la sauvegarde sur un lecteur de bande (spécifié dans la section **Destination** de la page **Général** ), l’option **Décharger la bande après la sauvegarde** est active.</span><span class="sxs-lookup"><span data-stu-id="52f1d-183">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="52f1d-184">Vous pouvez cliquer sur cette option pour activer l'option **Rembobiner la bande avant de décharger** .</span><span class="sxs-lookup"><span data-stu-id="52f1d-184">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
17. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="52f1d-185">et versions ultérieures prennent en charge la [compression de la sauvegarde](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52f1d-185">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="52f1d-186">Par défaut, la compression d’une sauvegarde dépend de la valeur de l’option de configuration de serveur **Compression par défaut des sauvegardes** .</span><span class="sxs-lookup"><span data-stu-id="52f1d-186">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="52f1d-187">Toutefois, quelle que soit la valeur par défaut actuelle au niveau du serveur, vous pouvez compresser une sauvegarde en activant **Compresser la sauvegarde**, et vous pouvez empêcher la compression en activant **Ne pas compresser la sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="52f1d-187">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="52f1d-188">**Pour consulter la valeur par défaut de compression de la sauvegarde actuelle**</span><span class="sxs-lookup"><span data-stu-id="52f1d-188">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="52f1d-189">Afficher ou configurer la compression par défaut des sauvegardes (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="52f1d-189">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
 <span data-ttu-id="52f1d-190">**Chiffrement**</span><span class="sxs-lookup"><span data-stu-id="52f1d-190">**Encryption**</span></span>  
  
 <span data-ttu-id="52f1d-191">Pour chiffrer le fichier de sauvegarde, activez la case à cocher **Chiffrer le fichier de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="52f1d-191">To encrypt the backup file check the **Encrypt backup** check box.</span></span> <span data-ttu-id="52f1d-192">Sélectionnez l'algorithme de chiffrement à utiliser pour chiffrer le fichier de sauvegarde et fournissez un certificat ou une clé asymétrique.</span><span class="sxs-lookup"><span data-stu-id="52f1d-192">Select an encryption algorithm to use for encrypting the backup file and provide a Certificate or Asymmetric key.</span></span> <span data-ttu-id="52f1d-193">Les algorithmes disponibles pour le chiffrement sont :</span><span class="sxs-lookup"><span data-stu-id="52f1d-193">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="52f1d-194">AES 128</span><span class="sxs-lookup"><span data-stu-id="52f1d-194">AES 128</span></span>  
  
-   <span data-ttu-id="52f1d-195">AES 192</span><span class="sxs-lookup"><span data-stu-id="52f1d-195">AES 192</span></span>  
  
-   <span data-ttu-id="52f1d-196">AES 256</span><span class="sxs-lookup"><span data-stu-id="52f1d-196">AES 256</span></span>  
  
-   <span data-ttu-id="52f1d-197">Triple DES</span><span class="sxs-lookup"><span data-stu-id="52f1d-197">Triple DES</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="52f1d-198">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="52f1d-198">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="52f1d-199">Pour sauvegarder un journal des transactions</span><span class="sxs-lookup"><span data-stu-id="52f1d-199">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="52f1d-200">Exécutez l'instruction BACKUP LOG pour sauvegarder le journal des transactions, en spécifiant :</span><span class="sxs-lookup"><span data-stu-id="52f1d-200">Execute the BACKUP LOG statement to back up the transaction log, specifying the following:</span></span>  
  
    -   <span data-ttu-id="52f1d-201">Le nom de la base de données à laquelle appartient le journal des transactions à sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="52f1d-201">The name of the database to which the transaction log that you want to back up belongs.</span></span>  
  
    -   <span data-ttu-id="52f1d-202">l'unité de sauvegarde où sera écrite la sauvegarde du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="52f1d-202">The backup device where the transaction log backup is written.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="52f1d-203">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="52f1d-203">Example (Transact-SQL)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="52f1d-204">Cet exemple utilise la base de données [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , qui fait appel au mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="52f1d-204">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, which uses the simple recovery model.</span></span> <span data-ttu-id="52f1d-205">Pour autoriser les sauvegardes de fichier journal, avant d'effectuer une sauvegarde complète de base de données, la base de données a été configurée pour utiliser le mode de récupération complète.</span><span class="sxs-lookup"><span data-stu-id="52f1d-205">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="52f1d-206">Pour plus d’informations, consultez [Afficher ou modifier le mode de récupération d’une base de données &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52f1d-206">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="52f1d-207">L'exemple suivant crée une sauvegarde du journal des transactions pour la base de données [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sur l'unité de sauvegarde nommée qui a été précédemment créée, `MyAdvWorks_FullRM_log1`.</span><span class="sxs-lookup"><span data-stu-id="52f1d-207">This example creates a transaction log backup for the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to the previously created named backup device, `MyAdvWorks_FullRM_log1`.</span></span>  
  
```sql  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1;  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="52f1d-208">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="52f1d-208">Using PowerShell</span></span>  
  
<span data-ttu-id="52f1d-209">Utilisez l'applet de commande `Backup-SqlDatabase` et spécifiez `Log` comme valeur du paramètre `-BackupAction`.</span><span class="sxs-lookup"><span data-stu-id="52f1d-209">Use the `Backup-SqlDatabase` cmdlet and specify `Log` for the value of the `-BackupAction` parameter.</span></span>  
  
<span data-ttu-id="52f1d-210">L'exemple suivant crée une sauvegarde de fichier journal de la base de données `MyDB` à l'emplacement de sauvegarde par défaut de l'instance de serveur `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="52f1d-210">The following example creates a log backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Log  
    ```  
  
<span data-ttu-id="52f1d-211">Pour configurer et utiliser le fournisseur de SQL Server PowerShell, consultez [SQL Server PowerShell Provider](../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="52f1d-211">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../powershell/sql-server-powershell-provider.md).</span></span>
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="52f1d-212">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="52f1d-212">Related Tasks</span></span>  
  
-   [<span data-ttu-id="52f1d-213">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="52f1d-213">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="52f1d-214">Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="52f1d-214">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="52f1d-215">Résoudre les problèmes liés à un journal des transactions saturé &#40;erreur SQL Server 9002&#41;</span><span class="sxs-lookup"><span data-stu-id="52f1d-215">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
## <a name="see-also"></a><span data-ttu-id="52f1d-216"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52f1d-216">See Also</span></span>  
 <span data-ttu-id="52f1d-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="52f1d-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="52f1d-218">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52f1d-218">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="52f1d-219">[Plans de maintenance](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="52f1d-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="52f1d-220">Sauvegardes de fichiers complètes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="52f1d-220">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
