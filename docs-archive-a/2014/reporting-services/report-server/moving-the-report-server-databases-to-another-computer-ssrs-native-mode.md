---
title: Déplacement des bases de données du serveur de rapports vers un autre ordinateur (en mode natif SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 44a9854d-e333-44f6-bdc7-8837b9f34416
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49fd35f57cf783b262b3c690e3047e5f479ab193
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695275"
---
# <a name="moving-the-report-server-databases-to-another-computer-ssrs-native-mode"></a><span data-ttu-id="a7a33-102">Déplacement des bases de données du serveur de rapports vers un autre ordinateur (en mode natif SSRS)</span><span class="sxs-lookup"><span data-stu-id="a7a33-102">Moving the Report Server Databases to Another Computer (SSRS Native Mode)</span></span>
  <span data-ttu-id="a7a33-103">Vous pouvez déplacer les bases de données du serveur de rapports qui sont utilisées dans une installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] vers une instance qui se trouve sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a7a33-103">You can move the report server databases that are used in an installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] to an instance that is on a different computer.</span></span> <span data-ttu-id="a7a33-104">Les bases de données reportserver et reportservertempdb doivent être déplacées ou copiées ensemble.</span><span class="sxs-lookup"><span data-stu-id="a7a33-104">Both the reportserver and reportservertempdb databases must be moved or copied together.</span></span> <span data-ttu-id="a7a33-105">Ces deux bases de données sont requises dans une installation [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ; la base de données reportservertempdb doit être liée par nom à la base de données reportserver primaire que vous déplacez.</span><span class="sxs-lookup"><span data-stu-id="a7a33-105">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires both databases; the reportservertempdb database must be related by name to the primary reportserver database you are moving.</span></span>  
  
 <span data-ttu-id="a7a33-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode natif.</span><span class="sxs-lookup"><span data-stu-id="a7a33-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="a7a33-107">Le déplacement d'une base de données n'a aucune incidence sur les opérations planifiées qui sont actuellement définies pour les éléments du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-107">Moving a database does not effect scheduled operations that are currently defined for report server items.</span></span>  
  
-   <span data-ttu-id="a7a33-108">Les planifications sont recréées la première fois que vous redémarrerez le service Report Server.</span><span class="sxs-lookup"><span data-stu-id="a7a33-108">Schedules will be recreated the first time that you restart the Report Server service.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a7a33-109">Les travaux de l’Agent, qui sont utilisés pour déclencher une planification, sont recréés dans la nouvelle instance de base de données.</span><span class="sxs-lookup"><span data-stu-id="a7a33-109">Agent jobs that are used to trigger a schedule will be recreated on the new database instance.</span></span> <span data-ttu-id="a7a33-110">Vous n'avez pas à déplacer les travaux vers le nouvel ordinateur ; toutefois, vous pouvez supprimer des travaux sur l'ordinateur qui ne sera plus utilisé.</span><span class="sxs-lookup"><span data-stu-id="a7a33-110">You do not have to move the jobs to the new computer, but you might want to delete jobs on the computer that will no longer be used.</span></span>  
  
-   <span data-ttu-id="a7a33-111">Les abonnements, les instantanés et les rapports mis en cache sont préservés dans la base de données déplacée.</span><span class="sxs-lookup"><span data-stu-id="a7a33-111">Subscriptions, cached reports, and snapshots are preserved in the moved database.</span></span> <span data-ttu-id="a7a33-112">Si un instantané ne collecte pas des données actualisées après le déplacement de la base de données, désactivez les options d’instantané dans le Gestionnaire de rapports, cliquez sur **Appliquer** pour enregistrer les modifications apportées, recréez la planification, puis cliquez à nouveau sur **Appliquer** pour enregistrer les modifications apportées.</span><span class="sxs-lookup"><span data-stu-id="a7a33-112">If a snapshot is not picking up refreshed data after the database is moved, clear the snapshot options in Report Manager, click **Apply** to save your changes, re-create the schedule, and click **Apply** again to save your changes.</span></span>  
  
-   <span data-ttu-id="a7a33-113">Les données temporaires de session utilisateur et de rapport qui sont stockées dans reportservertempdb sont conservées lorsque vous déplacez la base de données.</span><span class="sxs-lookup"><span data-stu-id="a7a33-113">Temporary report and user session data that is stored in reportservertempdb are persisted when you move that database.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a7a33-114">propose plusieurs approches pour déplacer les bases de données, notamment la sauvegarde et la restauration, l’attachement et le détachement, ainsi que la copie.</span><span class="sxs-lookup"><span data-stu-id="a7a33-114">provides several approaches for moving databases, including backup and restore, attach and detach, and copy.</span></span> <span data-ttu-id="a7a33-115">Les approches ne sont pas toutes appropriées lorsqu'il s'agit de déplacer une base de données vers une nouvelle instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="a7a33-115">Not all approaches are appropriate for relocating an existing database to a new server instance.</span></span> <span data-ttu-id="a7a33-116">L'approche à utiliser pour déplacer la base de données du serveur de rapports varie selon les impératifs de disponibilité de votre système.</span><span class="sxs-lookup"><span data-stu-id="a7a33-116">The approach that you should use to move the report server database will vary depending on your system availability requirements.</span></span> <span data-ttu-id="a7a33-117">Pour déplacer les bases de données du serveur de rapports, la méthode la plus simple consiste à les attacher et à les détacher.</span><span class="sxs-lookup"><span data-stu-id="a7a33-117">The easiest way to move the report server databases is to attach and detach them.</span></span> <span data-ttu-id="a7a33-118">Cependant, cette approche exige une mise hors connexion du serveur de rapports durant le détachement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="a7a33-118">However, this approach requires that you take the report server offline while you detach the database.</span></span> <span data-ttu-id="a7a33-119">La méthode de sauvegarde et de restauration est un choix plus judicieux si vous voulez minimiser les perturbations de service, mais vous devez exécuter des commandes [!INCLUDE[tsql](../../includes/tsql-md.md)] pour effectuer les opérations.</span><span class="sxs-lookup"><span data-stu-id="a7a33-119">Backup and restore is a better choice if you want to minimize service disruptions, but you must run [!INCLUDE[tsql](../../includes/tsql-md.md)] commands to perform the operations.</span></span> <span data-ttu-id="a7a33-120">La copie de la base de données n'est pas recommandée (surtout à l'aide de l'Assistant Copie de base de données), car elle ne conserve pas les paramètres d'autorisation dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a7a33-120">Copying the database is not recommended (specifically, by using the Copy Database Wizard); it does not preserve permission settings in the database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a7a33-121">Les procédures décrites dans cette rubrique sont recommandées lorsque le déplacement de la base de données du serveur de rapports est la seule modification que vous apportez à l'installation existante.</span><span class="sxs-lookup"><span data-stu-id="a7a33-121">The steps provided in this topic are recommended when relocating the report server database is the only change you are making to the existing installation.</span></span> <span data-ttu-id="a7a33-122">Procéder à la migration de toute une installation [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (c’est-à-dire déplacer la base de données et modifier l’identité du service Windows Report Server utilisant la base de données) nécessite la reconfiguration de la connexion et la réinitialisation de la clé de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="a7a33-122">Migrating an entire [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation (that is, moving the database and changing the identity of the Report Server Windows service that uses the database) requires connection reconfiguration and an encryption key reset.</span></span>  
  
## <a name="detaching-and-attaching-the-report-server-databases"></a><span data-ttu-id="a7a33-123">Détachement et attachement des bases de données du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="a7a33-123">Detaching and Attaching the Report Server Databases</span></span>  
 <span data-ttu-id="a7a33-124">Si vous pouvez procéder à une mise hors connexion du serveur de rapports, vous pouvez détacher les bases de données pour les déplacer vers l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="a7a33-124">If you can take the report server offline, you can detach the databases to move them to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="a7a33-125">Cette approche permet de conserver les autorisations définies dans les bases de données.</span><span class="sxs-lookup"><span data-stu-id="a7a33-125">This approach preserves permissions in the databases.</span></span> <span data-ttu-id="a7a33-126">Si vous utilisez une base de données [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , vous devez la déplacer vers une autre instance de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a33-126">If you are using a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] database, you must move it to another [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance.</span></span> <span data-ttu-id="a7a33-127">Une fois que vous avez déplacé les bases de données, vous devez reconfigurer la connexion du serveur de rapports à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-127">After you move the databases, you must reconfigure the report server connection to the report server database.</span></span> <span data-ttu-id="a7a33-128">Si vous exécutez un déploiement avec montée en puissance parallèle, vous devez reconfigurer la connexion à la base de données du serveur de rapports pour chaque serveur de rapports appartenant au déploiement.</span><span class="sxs-lookup"><span data-stu-id="a7a33-128">If you are running a scale-out deployment, you must reconfigure the report server database connection for each report server in the deployment.</span></span>  
  
 <span data-ttu-id="a7a33-129">Suivez la procédure ci-dessous pour déplacer les bases de données :</span><span class="sxs-lookup"><span data-stu-id="a7a33-129">Use the following steps to move the databases:</span></span>  
  
1.  <span data-ttu-id="a7a33-130">Sauvegardez les clés de chiffrement de la base de données du serveur de rapports que vous souhaitez déplacer.</span><span class="sxs-lookup"><span data-stu-id="a7a33-130">Backup the encryption keys for the report server database you want to move.</span></span> <span data-ttu-id="a7a33-131">Vous pouvez utiliser l’outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] pour sauvegarder les clés.</span><span class="sxs-lookup"><span data-stu-id="a7a33-131">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool backup the keys.</span></span>  
  
2.  <span data-ttu-id="a7a33-132">Arrêtez le service Report Server.</span><span class="sxs-lookup"><span data-stu-id="a7a33-132">Stop the Report Server service.</span></span> <span data-ttu-id="a7a33-133">Vous pouvez utiliser l'outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] pour arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="a7a33-133">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to stop the service.</span></span>  
  
3.  <span data-ttu-id="a7a33-134">Démarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et ouvrez une connexion à l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance qui héberge les bases de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-134">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and open a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the report server databases.</span></span>  
  
4.  <span data-ttu-id="a7a33-135">Cliquez avec le bouton droit sur la base de données du serveur de rapports, puis cliquez sur **Détacher**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-135">Right-click the report server database, point to Tasks, and click **Detach**.</span></span> <span data-ttu-id="a7a33-136">Répétez cette étape pour chaque base de données temporaire du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-136">Repeat this step for the report server temporary database.</span></span>  
  
5.  <span data-ttu-id="a7a33-137">Copiez ou déplacez les fichiers .mdf et .ldf vers le dossier Data de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="a7a33-137">Copy or move the .mdf and .ldf files to the Data folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="a7a33-138">Étant donné que vous déplacez deux bases de données, vérifiez que vous déplacez ou copiez les quatre fichiers.</span><span class="sxs-lookup"><span data-stu-id="a7a33-138">Because you are moving two databases, make sure that you move or copy all four files.</span></span>  
  
6.  <span data-ttu-id="a7a33-139">Dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], établissez une connexion à la nouvelle instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui hébergera les bases de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-139">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a connection to the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that will host the report server databases.</span></span>  
  
7.  <span data-ttu-id="a7a33-140">Cliquez avec le bouton droit sur le nœud Bases de données, puis cliquez sur **Détacher**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-140">Right-click the Databases node, and then click **Attach**.</span></span>  
  
8.  <span data-ttu-id="a7a33-141">Cliquez sur **Ajouter** pour sélectionner les fichiers .mdf et .ldf de base de données du serveur de rapports que vous voulez attacher.</span><span class="sxs-lookup"><span data-stu-id="a7a33-141">Click **Add** to select the report server database .mdf and .ldf files that you want to attach.</span></span> <span data-ttu-id="a7a33-142">Répétez cette étape pour chaque base de données temporaire du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-142">Repeat this step for the report server temporary database.</span></span>  
  
9. <span data-ttu-id="a7a33-143">Une fois les bases de données attachées, vérifiez que `RSExecRole` est un rôle de base de données dans la base de données du serveur de rapports et la base de données temporaire.</span><span class="sxs-lookup"><span data-stu-id="a7a33-143">After the databases are attached, verify that the `RSExecRole` is a database role in the report server database and temporary database.</span></span> <span data-ttu-id="a7a33-144">`RSExecRole`doit avoir des autorisations SELECT, Insert, Update, DELETE et Reference sur les tables de base de données du serveur de rapports, et des autorisations Execute sur les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="a7a33-144">`RSExecRole` must have select, insert, update, delete, and reference permissions on the report server database tables, and execute permissions on the stored procedures.</span></span> <span data-ttu-id="a7a33-145">Pour plus d’informations, consultez [Créer le rôle RSExecRole](../security/create-the-rsexecrole.md).</span><span class="sxs-lookup"><span data-stu-id="a7a33-145">For more information, see [Create the RSExecRole](../security/create-the-rsexecrole.md).</span></span>  
  
10. <span data-ttu-id="a7a33-146">Démarrez l’outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , puis établissez une connexion au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-146">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and open a connection to the report server.</span></span>  
  
11. <span data-ttu-id="a7a33-147">Dans la page Installation de la base de données, sélectionnez la nouvelle instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-147">On the Database page, select the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then click **Connect**.</span></span>  
  
12. <span data-ttu-id="a7a33-148">Sélectionnez la base de données de serveur de rapports que vous venez de déplacer, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-148">Select the report server database that you just moved, and then click **Apply**.</span></span>  
  
13. <span data-ttu-id="a7a33-149">Dans la page Clés de chiffrement, cliquez sur Restaurer.</span><span class="sxs-lookup"><span data-stu-id="a7a33-149">On the Encryption Keys page, click Restore.</span></span> <span data-ttu-id="a7a33-150">Spécifiez le fichier qui contient la copie de sauvegarde des clés, ainsi que le mot de passe qui déverrouille le fichier.</span><span class="sxs-lookup"><span data-stu-id="a7a33-150">Specify the file that contains the backup copy of the keys and the password to unlock the file.</span></span>  
  
14. <span data-ttu-id="a7a33-151">Redémarrez le service Report Server.</span><span class="sxs-lookup"><span data-stu-id="a7a33-151">Restart the Report Server service.</span></span>  
  
## <a name="backing-up-and-restoring-the-report-server-databases"></a><span data-ttu-id="a7a33-152">Sauvegarde et restauration des bases de données du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="a7a33-152">Backing Up and Restoring the Report Server Databases</span></span>  
 <span data-ttu-id="a7a33-153">Si vous ne pouvez pas procéder à la mise hors connexion du serveur de rapports, vous pouvez utiliser la sauvegarde et la restauration pour déplacer les bases de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-153">If you cannot take the report server offline, you can use backup and restore to relocate the report server databases.</span></span> <span data-ttu-id="a7a33-154">Vous devez utiliser des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] pour les opérations de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="a7a33-154">You must use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to do the backup and restore.</span></span> <span data-ttu-id="a7a33-155">Une fois les bases de données restaurées, vous devez configurer le serveur de rapports pour qu'il utilise la base de données sur la nouvelle instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="a7a33-155">After you restore the databases, you must configure the report server to use the database on the new server instance.</span></span> <span data-ttu-id="a7a33-156">Pour plus d'informations, consultez les instructions figurant à la fin de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="a7a33-156">For more information, see the instructions at the end of this topic.</span></span>  
  
### <a name="using-backup-and-copy_only-to-backup-the-report-server-databases"></a><span data-ttu-id="a7a33-157">Utilisation de BACKUP et COPY_ONLY pour sauvegarder les bases de données du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="a7a33-157">Using BACKUP and COPY_ONLY to Backup the Report Server Databases</span></span>  
 <span data-ttu-id="a7a33-158">Lorsque vous sauvegardez les bases de données, définissez l'argument COPY_ONLY.</span><span class="sxs-lookup"><span data-stu-id="a7a33-158">When backing up the databases, set the COPY_ONLY argument.</span></span> <span data-ttu-id="a7a33-159">Veillez à sauvegarder les fichiers de base de données et les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="a7a33-159">Be sure to back up both of the databases and log files.</span></span>  
  
```  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServer  
   SET RECOVERY FULL  
  
-- If the ReportServerData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerData',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerData.bak'  
  
-- Create a logical backup device, ReportServerLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerLog.bak'  
  
-- Back up the full ReportServer database.  
BACKUP DATABASE ReportServer  
   TO ReportServerData  
   WITH COPY_ONLY  
  
-- Back up the ReportServer log.  
BACKUP LOG ReportServer  
   TO ReportServerLog  
   WITH COPY_ONLY  
  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServerTempdb  
   SET RECOVERY FULL  
  
-- If the ReportServerTempDBData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBData',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBData.bak'  
  
-- Create a logical backup device, ReportServerTempDBLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBLog.bak'  
  
-- Back up the full ReportServerTempDB database.  
BACKUP DATABASE ReportServerTempDB  
   TO ReportServerTempDBData  
   WITH COPY_ONLY  
  
-- Back up the ReportServerTempDB log.  
BACKUP LOG ReportServerTempDB  
   TO ReportServerTempDBLog  
   WITH COPY_ONLY  
```  
  
### <a name="using-restore-and-move-to-relocate-the-report-server-databases"></a><span data-ttu-id="a7a33-160">Utilisation de RESTORE et de MOVE pour déplacer les bases de données du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="a7a33-160">Using RESTORE and MOVE to Relocate the Report Server Databases</span></span>  
 <span data-ttu-id="a7a33-161">Lorsque vous restaurez les bases de données, veillez à inclure l'argument MOVE pour pouvoir spécifier un chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="a7a33-161">When restoring the databases, be sure to include the MOVE argument so that you can specify a path.</span></span> <span data-ttu-id="a7a33-162">Utilisez l'argument NORECOVERY pour effectuer la restauration initiale ; la base de données reste ainsi dans l'état de restauration, ce qui vous laisse le temps de vérifier les sauvegardes des journaux pour déterminer ceux qui doivent être restaurés.</span><span class="sxs-lookup"><span data-stu-id="a7a33-162">Use the NORECOVERY argument to perform the initial restore; this keeps the database in a RESTORING state, giving you time to review log backups to determine which one to restore.</span></span> <span data-ttu-id="a7a33-163">L'étape finale répète l'opération RESTORE avec l'argument RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="a7a33-163">The final step repeats the RESTORE operation with the RECOVERY argument.</span></span>  
  
 <span data-ttu-id="a7a33-164">L'argument MOVE utilise le nom logique du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="a7a33-164">The MOVE argument uses the logical name of the data file.</span></span> <span data-ttu-id="a7a33-165">Pour trouver le nom logique, exécutez l'instruction suivante : `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="a7a33-165">To find the logical name, execute the following statement: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="a7a33-166">Les exemples suivants incluent l'argument FILE pour que vous puissiez spécifier la position de fichier du fichier journal à restaurer.</span><span class="sxs-lookup"><span data-stu-id="a7a33-166">The following examples include the FILE argument so that you can specify the file position of the log file to restore.</span></span> <span data-ttu-id="a7a33-167">Pour trouver la position de fichier, exécutez l'instruction suivante : `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="a7a33-167">To find the file position, execute the following statement: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="a7a33-168">Lorsque vous restaurez les fichiers de base de données et les fichiers journaux, vous devez exécuter chaque opération RESTORE séparément.</span><span class="sxs-lookup"><span data-stu-id="a7a33-168">When restoring the database and log files, you should run each RESTORE operation separately.</span></span>  
  
```  
-- Restore the report server database and move to new instance folder   
RESTORE DATABASE ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore the report server log file to new instance folder   
RESTORE LOG ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore and move the report server temporary database  
RESTORE DATABASE ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Restore the temporary database log file to new instance folder   
RESTORE LOG ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServer  
   WITH RECOVERY  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServerTempDB  
   WITH RECOVERY  
GO  
```  
  
### <a name="how-to-configure-the-report-server-database-connection"></a><span data-ttu-id="a7a33-169">Procédure à suivre pour configurer la connexion à la base de données du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="a7a33-169">How to Configure the Report Server Database Connection</span></span>  
  
1.  <span data-ttu-id="a7a33-170">Démarrez le Gestionnaire de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , puis établissez une connexion au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-170">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and open a connection to the report server.</span></span>  
  
2.  <span data-ttu-id="a7a33-171">Dans la page Base de données, cliquez sur **Modifier la base de données**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-171">On the Database page, click **Change Database**.</span></span> <span data-ttu-id="a7a33-172">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-172">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="a7a33-173">Cliquez sur **Choisir une base de données de serveur de rapports existante**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-173">Click **Choose an existing report server database**.</span></span> <span data-ttu-id="a7a33-174">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-174">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="a7a33-175">Sélectionnez le serveur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui héberge désormais la base de données du serveur de rapports, puis cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-175">Select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that now hosts the report server database and click **Test Connection**.</span></span> <span data-ttu-id="a7a33-176">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-176">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="a7a33-177">Dans Nom de la base de données, sélectionnez la base de données du serveur de rapports que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="a7a33-177">In Database Name, select the report server database that you want to use.</span></span> <span data-ttu-id="a7a33-178">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-178">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="a7a33-179">Dans Informations d'identification, spécifiez les informations d'identification que le serveur de rapports doit utiliser pour se connecter à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a7a33-179">In Credentials, specify the credentials that the report server will use to connect to the report server database.</span></span> <span data-ttu-id="a7a33-180">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-180">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="a7a33-181">Cliquez sur **Suivant** , puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a7a33-181">Click **Next** and then **Finish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7a33-182">Une installation [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] requiert que l’instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] comporte le rôle `RSExecRole`.</span><span class="sxs-lookup"><span data-stu-id="a7a33-182">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance include the `RSExecRole` role.</span></span> <span data-ttu-id="a7a33-183">La création de rôles, l’inscription d’une connexion et les attributions de rôles ont lieu quand vous définissez la connexion à la base de données du serveur de rapports par le biais de l’outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a33-183">Role creation, login registration, and role assignments occur when you set the report server database connection through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="a7a33-184">Si vous utilisez d'autres approches (surtout si vous recourez à l'utilitaire d'invite de commandes rsconfig.exe) pour configurer la connexion, le serveur de rapports ne sera pas en état de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="a7a33-184">If you use alternate approaches (specifically, if you use the rsconfig.exe command prompt utility) to configure the connection, the report server will not be in a working state.</span></span> <span data-ttu-id="a7a33-185">Vous devrez peut-être écrire du code WMI pour rendre le serveur de rapports disponible.</span><span class="sxs-lookup"><span data-stu-id="a7a33-185">You might have to write WMI code to make the report server available.</span></span> <span data-ttu-id="a7a33-186">Pour plus d’informations, consultez [Accéder au fournisseur WMI de Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="a7a33-186">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a33-187">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7a33-187">See Also</span></span>  
 <span data-ttu-id="a7a33-188">[Créer le RSExecRole](../security/create-the-rsexecrole.md) </span><span class="sxs-lookup"><span data-stu-id="a7a33-188">[Create the RSExecRole](../security/create-the-rsexecrole.md) </span></span>  
 <span data-ttu-id="a7a33-189">[Démarrer et arrêter le service Report Server](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="a7a33-189">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 <span data-ttu-id="a7a33-190">[Configurer une connexion à la base de données du serveur de rapports &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a7a33-190">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="a7a33-191">[Configurer le compte d’exécution sans assistance &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a7a33-191">[Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="a7a33-192">[Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a7a33-192">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="a7a33-193">[Utilitaire rsconfig &#40;&#41;SSRS](../tools/rsconfig-utility-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a7a33-193">[rsconfig Utility &#40;SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span></span>  
 <span data-ttu-id="a7a33-194">[Configurer et gérer des clés de chiffrement &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span><span class="sxs-lookup"><span data-stu-id="a7a33-194">[Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span></span>  
 [<span data-ttu-id="a7a33-195">Base de données du serveur de rapports &#40;SSRS en mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="a7a33-195">Report Server Database &#40;SSRS Native Mode&#41;</span></span>](report-server-database-ssrs-native-mode.md)  
  
  
