---
title: Ajouter une base de données secondaire dans une configuration de copie des journaux de transaction (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- adding secondary databases
- secondary databases [SQL Server], in log shipping
- secondary data files [SQL Server], adding
- log shipping [SQL Server], secondary databases
ms.assetid: b02eba13-f8e6-4684-b7e4-75ea038ea473
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 062df1b53ed74321ba0c75c9df763de79a4802bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605698"
---
# <a name="add-a-secondary-database-to-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="4eed5-102">Ajouter une base de données secondaire dans une configuration de copie des journaux de transaction (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4eed5-102">Add a Secondary Database to a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="4eed5-103">Cette rubrique explique comment ajouter une base de données secondaire à une configuration de copie des journaux de transaction dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eed5-103">This topic describes how to add a secondary database to an existing log shipping configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4eed5-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4eed5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4eed5-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="4eed5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4eed5-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4eed5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4eed5-107">**Pour ajouter une base de données secondaire pour la copie des journaux de transaction, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="4eed5-107">**To add a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="4eed5-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4eed5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4eed5-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4eed5-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="4eed5-110">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="4eed5-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4eed5-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4eed5-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4eed5-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4eed5-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4eed5-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4eed5-113">Permissions</span></span>  
 <span data-ttu-id="4eed5-114">Les procédures stockées de copie des journaux de transaction nécessitent l’appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4eed5-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4eed5-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4eed5-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="4eed5-116">Pour ajouter une base de données secondaire pour la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="4eed5-116">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="4eed5-117">Cliquez avec le bouton droit sur la base de données à utiliser en tant que base de données primaire dans la configuration de copie des journaux de transaction, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4eed5-117">Right-click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="4eed5-118">Sous **Sélectionner une page**, cliquez sur **Envoi de journaux de transaction**.</span><span class="sxs-lookup"><span data-stu-id="4eed5-118">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="4eed5-119">Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4eed5-119">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="4eed5-120">Cliquez sur **Se connecter** et connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser comme serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="4eed5-120">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
5.  <span data-ttu-id="4eed5-121">Dans la zone **Base de données secondaire** , choisissez une base de données dans la liste ou tapez le nom de la base de données que vous voulez créer.</span><span class="sxs-lookup"><span data-stu-id="4eed5-121">In the **Secondary database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
6.  <span data-ttu-id="4eed5-122">Dans l'onglet **Initialiser la base de données secondaire** , choisissez l'option à utiliser pour initialiser la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="4eed5-122">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
7.  <span data-ttu-id="4eed5-123">Dans l' **onglet Copier les fichiers**, dans la zone **Dossier de destination des fichiers copiés** , entrez le chemin du dossier vers lequel vous voulez copier les sauvegardes des journaux des transactions.</span><span class="sxs-lookup"><span data-stu-id="4eed5-123">On the **Copy Files tab**, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="4eed5-124">Ce dossier se situe généralement sur le serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="4eed5-124">This folder is often located on the secondary server.</span></span>  
  
8.  <span data-ttu-id="4eed5-125">Notez la planification de la copie figurant dans la zone **Planification** sous **Copier le travail**.</span><span class="sxs-lookup"><span data-stu-id="4eed5-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="4eed5-126">Si vous souhaitez personnaliser la planification de votre installation, cliquez sur **Planification** et ajustez ensuite la planification de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="4eed5-126">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="4eed5-127">Cette planification doit être proche de la planification de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="4eed5-127">This schedule should approximate the backup schedule.</span></span>  
  
9. <span data-ttu-id="4eed5-128">Dans l’onglet **Restaurer** , sous **État de la base de données lors de la restauration des sauvegardes**, choisissez l’option **Aucun mode de récupération** ou **Mode veille** .</span><span class="sxs-lookup"><span data-stu-id="4eed5-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
10. <span data-ttu-id="4eed5-129">Si vous choisissez l'option **Mode veille** , déterminez si vous voulez déconnecter des utilisateurs de la base de données secondaire pendant que l'opération de restauration est en cours.</span><span class="sxs-lookup"><span data-stu-id="4eed5-129">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
11. <span data-ttu-id="4eed5-130">Si vous voulez retarder le processus de restauration sur le serveur secondaire, choisissez un délai sous **Retarder la restauration des sauvegardes d'au moins**.</span><span class="sxs-lookup"><span data-stu-id="4eed5-130">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
12. <span data-ttu-id="4eed5-131">Choisissez un seuil d'alerte sous **Envoyer une alerte si aucune restauration ne se produit dans l'espace de**.</span><span class="sxs-lookup"><span data-stu-id="4eed5-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
13. <span data-ttu-id="4eed5-132">Notez la planification de la restauration figurant dans la zone **Planification** sous **Restaurer le travail**.</span><span class="sxs-lookup"><span data-stu-id="4eed5-132">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="4eed5-133">Si vous souhaitez personnaliser la planification de votre installation, cliquez sur **Planification** et ajustez ensuite la planification de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="4eed5-133">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="4eed5-134">Cette planification doit être proche de la planification de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="4eed5-134">This schedule should approximate the backup schedule.</span></span>  
  
14. <span data-ttu-id="4eed5-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4eed5-135">Click **OK**.</span></span>  
  
15. <span data-ttu-id="4eed5-136">Cliquez sur **OK** dans la boîte de dialogue Propriétés de la base de données pour démarrer la procédure de configuration.</span><span class="sxs-lookup"><span data-stu-id="4eed5-136">Click **OK** on the Database Properties dialog box to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4eed5-137">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4eed5-137">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="4eed5-138">Pour ajouter une base de données secondaire pour la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="4eed5-138">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="4eed5-139">Sur le serveur secondaire, exécutez [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) en fournissant les informations sur le serveur et la base de données principaux.</span><span class="sxs-lookup"><span data-stu-id="4eed5-139">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="4eed5-140">Cette procédure stockée retourne l'ID secondaire et les ID des travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="4eed5-140">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
2.  <span data-ttu-id="4eed5-141">Sur le serveur secondaire, exécutez [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) pour définir la planification des travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="4eed5-141">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="4eed5-142">Sur le serveur secondaire, exécutez [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) pour ajouter une base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="4eed5-142">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
4.  <span data-ttu-id="4eed5-143">Sur le serveur principal, exécutez [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) pour ajouter les informations requises sur la nouvelle base de données secondaire au serveur principal.</span><span class="sxs-lookup"><span data-stu-id="4eed5-143">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
5.  <span data-ttu-id="4eed5-144">Sur le serveur secondaire, activez les travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="4eed5-144">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="4eed5-145">Pour plus d’informations, consultez [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="4eed5-145">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4eed5-146">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="4eed5-146">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4eed5-147">Mise à niveau de la copie des journaux de transaction vers SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4eed5-147">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="4eed5-148">Configurer la copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4eed5-148">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="4eed5-149">Supprimer une base de données secondaire dans une configuration de copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4eed5-149">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="4eed5-150">Supprimer la copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4eed5-150">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="4eed5-151">Afficher le rapport de la copie des journaux de transaction &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4eed5-151">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="4eed5-152">Surveiller la copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4eed5-152">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="4eed5-153">Basculer vers un serveur secondaire d’envoi de journaux &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4eed5-153">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4eed5-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4eed5-154">See Also</span></span>  
 <span data-ttu-id="4eed5-155">[À propos de la copie des journaux des transactions &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4eed5-155">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="4eed5-156">Tables et procédures stockées liées à la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="4eed5-156">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
