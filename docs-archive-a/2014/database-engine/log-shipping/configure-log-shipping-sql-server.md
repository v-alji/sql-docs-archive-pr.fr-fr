---
title: Configurer la copie des journaux de transaction (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], enabling
- log shipping [SQL Server], configuring
ms.assetid: c42aa04a-4945-4417-b4c7-50589d727e9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269b0ae2980435e507128cc87606f7eb702c2b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697107"
---
# <a name="configure-log-shipping-sql-server"></a><span data-ttu-id="012c3-102">Configurer la copie des journaux de transaction (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="012c3-102">Configure Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="012c3-103">Cette rubrique explique comment configurer une copie des journaux de transaction dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="012c3-103">This topic describes how to configure log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="012c3-104">et ses versions ultérieures prennent en charge la compression de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="012c3-104">and later versions support backup compression.</span></span> <span data-ttu-id="012c3-105">Lorsque vous créez une configuration de copie des journaux de transaction, vous pouvez contrôler le comportement de compression des sauvegardes de fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="012c3-105">When creating a log shipping configuration, you can control the backup compression behavior of log backups.</span></span> <span data-ttu-id="012c3-106">Pour plus d’informations, consultez [Compression de sauvegardes &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="012c3-106">For more information, see [Backup Compression &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="012c3-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="012c3-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="012c3-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="012c3-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="012c3-109">Composants requis</span><span class="sxs-lookup"><span data-stu-id="012c3-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="012c3-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="012c3-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="012c3-111">**Pour configurer la copie des journaux de transaction, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="012c3-111">**To configure log shipping, using:**</span></span>  
  
     [<span data-ttu-id="012c3-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="012c3-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="012c3-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="012c3-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="012c3-114">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="012c3-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="012c3-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="012c3-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="012c3-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="012c3-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="012c3-117">La base de données primaire doit utiliser le mode de récupération complète ou de récupération utilisant les journaux de transactions ; le basculement de la base de données vers une récupération simple empêcherait toute copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="012c3-117">The primary database must use the full or bulk-logged recovery model; switching the database to simple recovery will cause log shipping to stop functioning.</span></span>  
  
-   <span data-ttu-id="012c3-118">Avant de configurer la copie des journaux de transaction, vous devez créer un partage afin de rendre les sauvegardes de journaux de transactions disponibles pour le serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="012c3-118">Before you configure log shipping, you must create a share to make the transaction log backups available to the secondary server.</span></span> <span data-ttu-id="012c3-119">Il s'agit d'un partage du répertoire vers lequel les sauvegardes des journaux de transactions seront générées.</span><span class="sxs-lookup"><span data-stu-id="012c3-119">This is a share of the directory where the transaction log backups will be generated.</span></span> <span data-ttu-id="012c3-120">Par exemple, si vous sauvegardez vos journaux de transactions dans le répertoire c:\data\tlogs\\, vous pouvez créer le partage \\\\*primaryserver*\tlogs de ce répertoire.</span><span class="sxs-lookup"><span data-stu-id="012c3-120">For example, if you back up your transaction logs to the directory c:\data\tlogs\\, you could create the \\\\*primaryserver*\tlogs share of that directory.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="012c3-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="012c3-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="012c3-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="012c3-122">Permissions</span></span>  
 <span data-ttu-id="012c3-123">Les procédures stockées de copie des journaux de transaction nécessitent l’appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="012c3-123">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="012c3-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="012c3-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="012c3-125">Pour configurer la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="012c3-125">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="012c3-126">Cliquez avec le bouton droit sur la base de données que vous voulez utiliser en tant que base de données primaire dans une configuration de copie des journaux de transaction, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="012c3-126">Right click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="012c3-127">Sous **Sélectionner une page**, cliquez sur **Envoi de journaux de transaction**.</span><span class="sxs-lookup"><span data-stu-id="012c3-127">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="012c3-128">Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions** .</span><span class="sxs-lookup"><span data-stu-id="012c3-128">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
4.  <span data-ttu-id="012c3-129">Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="012c3-129">Under **Transaction log backups**, click **Backup Settings**.</span></span>  
  
5.  <span data-ttu-id="012c3-130">Dans la zone **Chemin d'accès réseau au dossier de sauvegarde** , tapez le chemin d'accès réseau vers le partage que vous avez créé pour le dossier de sauvegarde des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="012c3-130">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>  
  
6.  <span data-ttu-id="012c3-131">Si le dossier de sauvegarde est situé sur le serveur principal, tapez le chemin d'accès local vers le dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d'accès local au dossier** .</span><span class="sxs-lookup"><span data-stu-id="012c3-131">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="012c3-132">Si le dossier de sauvegarde n'est pas situé sur le serveur principal, vous pouvez laisser cette zone vide.</span><span class="sxs-lookup"><span data-stu-id="012c3-132">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="012c3-133">Si le compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur votre serveur principal est exécuté sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin d'accès local vers ce dossier.</span><span class="sxs-lookup"><span data-stu-id="012c3-133">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>  
  
7.  <span data-ttu-id="012c3-134">Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit dans l'espace de** .</span><span class="sxs-lookup"><span data-stu-id="012c3-134">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>  
  
8.  <span data-ttu-id="012c3-135">Notez la planification de la sauvegarde figurant dans la zone **Planification** sous **Travail de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="012c3-135">Note the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="012c3-136">Si vous souhaitez personnaliser la planification pour votre installation, cliquez ensuite sur **Planification** et ajustez la planification de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="012c3-136">If you want to customize the schedule for your installation, then click **Schedule** and adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span>  
  
9. [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="012c3-137">prend en charge la [compression de la sauvegarde](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="012c3-137">supports [backup compression](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span> <span data-ttu-id="012c3-138">Lorsque vous créez une configuration de copie des journaux de transaction, vous pouvez contrôler le comportement de compression des sauvegardes de fichiers journaux grâce à l’une des options suivantes : **Utiliser le paramètre de serveur par défaut**, **Compresser la sauvegarde**, ou **Ne pas compresser la sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="012c3-138">When creating a log shipping configuration, you can control the backup compression behavior of log backups by choosing one of the following options: **Use the default server setting**, **Compress backup**, or **Do not compress backup**.</span></span> <span data-ttu-id="012c3-139">Pour plus d’informations, consultez [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span><span class="sxs-lookup"><span data-stu-id="012c3-139">For more information, see [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span></span>  
  
10. <span data-ttu-id="012c3-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="012c3-140">Click **OK**.</span></span>  
  
11. <span data-ttu-id="012c3-141">Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="012c3-141">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
12. <span data-ttu-id="012c3-142">Cliquez sur **Se connecter** et connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser comme serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="012c3-142">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
13. <span data-ttu-id="012c3-143">Dans la zone **Base de données secondaire** , choisissez une base de données dans la liste ou tapez le nom de la base de données que vous voulez créer.</span><span class="sxs-lookup"><span data-stu-id="012c3-143">In the **Secondary Database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
14. <span data-ttu-id="012c3-144">Dans l'onglet **Initialiser la base de données secondaire** , choisissez l'option à utiliser pour initialiser la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="012c3-144">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="012c3-145">Si vous choisissez l’option suivant laquelle [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] initialise la base de données secondaire à partir d’une sauvegarde de la base de données, les fichiers de données et les fichiers journaux de la base de données secondaire sont placés au même emplacement que les fichiers de données et les fichiers journaux de la base de données **MASTER** .</span><span class="sxs-lookup"><span data-stu-id="012c3-145">If you choose to have [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] initialize the secondary database from a database backup, the data and log files of the secondary database are placed in the same location as the data and log files of the **master** database.</span></span> <span data-ttu-id="012c3-146">Il est probable que cet emplacement soit différent de celui des fichiers de données et des fichiers journaux de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="012c3-146">This location is likely to be different than the location of the data and log files of the primary database.</span></span>  
  
15. <span data-ttu-id="012c3-147">Sous l'onglet **Copier les fichiers** , dans la zone **Dossier de destination des fichiers copiés** , tapez le chemin d'accès du dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées.</span><span class="sxs-lookup"><span data-stu-id="012c3-147">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="012c3-148">Ce dossier se situe généralement sur le serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="012c3-148">This folder is often located on the secondary server.</span></span>  
  
16. <span data-ttu-id="012c3-149">Notez la planification de la copie figurant dans la zone **Planification** sous **Copier le travail**.</span><span class="sxs-lookup"><span data-stu-id="012c3-149">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="012c3-150">Si vous souhaitez personnaliser la planification de votre installation, cliquez sur **Planification** et ajustez ensuite la planification de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="012c3-150">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="012c3-151">Cette planification doit être proche de la planification de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="012c3-151">This schedule should approximate the backup schedule.</span></span>  
  
17. <span data-ttu-id="012c3-152">Dans l’onglet **Restaurer** , sous **État de la base de données lors de la restauration des sauvegardes**, choisissez l’option **Aucun mode de récupération** ou **Mode veille** .</span><span class="sxs-lookup"><span data-stu-id="012c3-152">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
18. <span data-ttu-id="012c3-153">Si vous choisissez l'option **Mode veille** , déterminez si vous voulez déconnecter des utilisateurs de la base de données secondaire pendant que l'opération de restauration est en cours.</span><span class="sxs-lookup"><span data-stu-id="012c3-153">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
19. <span data-ttu-id="012c3-154">Si vous voulez retarder le processus de restauration sur le serveur secondaire, choisissez un délai sous **Retarder la restauration des sauvegardes d'au moins**.</span><span class="sxs-lookup"><span data-stu-id="012c3-154">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
20. <span data-ttu-id="012c3-155">Choisissez un seuil d'alerte sous **Envoyer une alerte si aucune restauration ne se produit dans l'espace de**.</span><span class="sxs-lookup"><span data-stu-id="012c3-155">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
21. <span data-ttu-id="012c3-156">Notez la planification de la restauration figurant dans la zone **Planification** sous **Restaurer le travail**.</span><span class="sxs-lookup"><span data-stu-id="012c3-156">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="012c3-157">Si vous souhaitez personnaliser la planification de votre installation, cliquez sur **Planification** et ajustez ensuite la planification de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="012c3-157">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="012c3-158">Cette planification doit être proche de la planification de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="012c3-158">This schedule should approximate the backup schedule.</span></span>  
  
22. <span data-ttu-id="012c3-159">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="012c3-159">Click **OK**.</span></span>  
  
23. <span data-ttu-id="012c3-160">Sous **Instance du serveur moniteur**, activez la case à cocher **Utiliser une instance du serveur moniteur** , puis cliquez sur **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="012c3-160">Under **Monitor server instance**, select the **Use a monitor server instance** check box, and then click **Settings**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="012c3-161">Pour analyser cette configuration d'envoi de journaux, vous devez ajouter maintenant le serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="012c3-161">To monitor this log shipping configuration, you must add the monitor server now.</span></span> <span data-ttu-id="012c3-162">Pour ajouter le serveur moniteur ultérieurement, vous devrez supprimer cette configuration d'envoi de journaux, puis la remplacer par une nouvelle configuration qui inclut un serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="012c3-162">To add the monitor server later, you would need to remove this log shipping configuration and then replace it with a new configuration that includes a monitor server.</span></span>  
  
24. <span data-ttu-id="012c3-163">Cliquez sur **Connecter** et connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous souhaitez utiliser en tant que serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="012c3-163">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your monitor server.</span></span>  
  
25. <span data-ttu-id="012c3-164">Sous **Connexions du moniteur**, choisissez la méthode de connexion que devront utiliser les travaux de sauvegarde, copie et restauration pour se connecter au serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="012c3-164">Under **Monitor connections**, choose the connection method to be used by the backup, copy, and restore jobs to connect to the monitor server.</span></span>  
  
26. <span data-ttu-id="012c3-165">Sous **Rétention de l'historique**, choisissez la durée pendant laquelle vous voulez conserver un enregistrement de l'historique de copie des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="012c3-165">Under **History retention**, choose the length of time you want to retain a record of your log shipping history.</span></span>  
  
27. <span data-ttu-id="012c3-166">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="012c3-166">Click **OK**.</span></span>  
  
28. <span data-ttu-id="012c3-167">Dans la boîte de dialogue **Propriétés de la base de données** , cliquez sur **OK** pour démarrer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="012c3-167">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="012c3-168">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="012c3-168">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="012c3-169">Pour configurer la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="012c3-169">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="012c3-170">Initialisez la base de données secondaire en restaurant une sauvegarde complète de la base de données primaire sur le serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="012c3-170">Initialize the secondary database by restoring a full backup of the primary database on the secondary server.</span></span>  
  
2.  <span data-ttu-id="012c3-171">Sur le serveur principal, exécutez [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) pour ajouter une base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="012c3-171">On the primary server, execute [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) to add a primary database.</span></span> <span data-ttu-id="012c3-172">La procédure stockée renvoie l'ID du travail de sauvegarde et l'ID primaire.</span><span class="sxs-lookup"><span data-stu-id="012c3-172">The stored procedure returns the backup job ID and primary ID.</span></span>  
  
3.  <span data-ttu-id="012c3-173">Sur le serveur principal, exécutez [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) pour ajouter une planification pour le travail de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="012c3-173">On the primary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to add a schedule for the backup job.</span></span>  
  
4.  <span data-ttu-id="012c3-174">Sur le serveur moniteur, exécutez [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) pour ajouter le travail d’alerte.</span><span class="sxs-lookup"><span data-stu-id="012c3-174">On the monitor server, execute [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) to add the alert job.</span></span>  
  
5.  <span data-ttu-id="012c3-175">Sur le serveur principal, activez le travail de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="012c3-175">On the primary server, enable the backup job.</span></span>  
  
6.  <span data-ttu-id="012c3-176">Sur le serveur secondaire, exécutez [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) en fournissant les informations sur le serveur et la base de données principaux.</span><span class="sxs-lookup"><span data-stu-id="012c3-176">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="012c3-177">Cette procédure stockée retourne l'ID secondaire et les ID des travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="012c3-177">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
7.  <span data-ttu-id="012c3-178">Sur le serveur secondaire, exécutez [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) pour définir la planification des travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="012c3-178">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
8.  <span data-ttu-id="012c3-179">Sur le serveur secondaire, exécutez [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) pour ajouter une base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="012c3-179">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
9. <span data-ttu-id="012c3-180">Sur le serveur principal, exécutez [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) pour ajouter les informations requises sur la nouvelle base de données secondaire au serveur principal.</span><span class="sxs-lookup"><span data-stu-id="012c3-180">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
10. <span data-ttu-id="012c3-181">Sur le serveur secondaire, activez les travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="012c3-181">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="012c3-182">Pour plus d’informations, consultez [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="012c3-182">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="012c3-183">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="012c3-183">Related Tasks</span></span>  
  
-   [<span data-ttu-id="012c3-184">Mise à niveau de la copie des journaux de transaction vers SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="012c3-184">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="012c3-185">Ajouter une base de données secondaire dans une configuration de copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="012c3-185">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="012c3-186">Supprimer une base de données secondaire dans une configuration de copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="012c3-186">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="012c3-187">Supprimer la copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="012c3-187">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="012c3-188">Afficher le rapport de la copie des journaux de transaction &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="012c3-188">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="012c3-189">Surveiller la copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="012c3-189">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="012c3-190">Basculer vers un serveur secondaire d’envoi de journaux &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="012c3-190">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="012c3-191">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="012c3-191">See Also</span></span>  
 <span data-ttu-id="012c3-192">[À propos de la copie des journaux des transactions &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="012c3-192">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="012c3-193">Tables et procédures stockées liées à la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="012c3-193">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
