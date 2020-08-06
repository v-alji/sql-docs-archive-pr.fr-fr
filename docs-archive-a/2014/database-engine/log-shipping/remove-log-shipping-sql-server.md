---
title: Supprimer la copie des journaux de transaction (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], removing
- removing log shipping
- deleting log shipping
ms.assetid: 859373db-c744-4a4b-8479-45163f61e8cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 14fdc36c66073e89dcc2014aed4319a2ce78a98f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605697"
---
# <a name="remove-log-shipping-sql-server"></a><span data-ttu-id="2d473-102">Supprimer la copie des journaux de transaction (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2d473-102">Remove Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="2d473-103">Cette rubrique explique comment supprimer la copie des journaux de transaction dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d473-103">This topic describes how to remove log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2d473-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2d473-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2d473-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2d473-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2d473-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2d473-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2d473-107">**Pour supprimer la copie des journaux de transaction, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="2d473-107">**To remove log shipping, using:**</span></span>  
  
     [<span data-ttu-id="2d473-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d473-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2d473-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d473-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="2d473-110">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="2d473-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d473-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2d473-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d473-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2d473-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d473-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2d473-113">Permissions</span></span>  
 <span data-ttu-id="2d473-114">Les procédures stockées de copie des journaux de transaction nécessitent l’appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="2d473-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2d473-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d473-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="2d473-116">Pour supprimer l'envoi de journaux</span><span class="sxs-lookup"><span data-stu-id="2d473-116">To remove log shipping</span></span>  
  
1.  <span data-ttu-id="2d473-117">Connectez-vous à l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est actuellement le serveur principal de copie des journaux de transaction et développez-la.</span><span class="sxs-lookup"><span data-stu-id="2d473-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="2d473-118">Développez **Bases de données**, cliquez avec le bouton droit sur la base de données primaire de copie des journaux de transaction, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2d473-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2d473-119">Sous **Sélectionner une page**, cliquez sur **Envoi de journaux de transaction**.</span><span class="sxs-lookup"><span data-stu-id="2d473-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="2d473-120">Désactivez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions** .</span><span class="sxs-lookup"><span data-stu-id="2d473-120">Clear the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
5.  <span data-ttu-id="2d473-121">Cliquez sur **OK** pour supprimer l'envoi de journaux depuis cette base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="2d473-121">Click **OK** to remove log shipping from this primary database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2d473-122">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d473-122">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="2d473-123">Pour supprimer l'envoi de journaux</span><span class="sxs-lookup"><span data-stu-id="2d473-123">To Remove Log Shipping</span></span>  
  
1.  <span data-ttu-id="2d473-124">Sur le serveur principal de copie des journaux de transaction, exécutez [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) pour supprimer du serveur principal les informations relatives à la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="2d473-124">On the log shipping primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="2d473-125">Sur le serveur secondaire de copie des journaux de transaction, exécutez [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) pour supprimer la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="2d473-125">On the log shipping secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d473-126">Si aucune autre base de données secondaire portant le même ID secondaire n’existe, **sp_delete_log_shipping_secondary_primary** est appelé par **sp_delete_log_shipping_secondary_database** et supprime l’entrée de l’ID secondaire, ainsi que les travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="2d473-126">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="2d473-127">Sur le serveur principal de copie des journaux de transaction, exécutez **sp_delete_log_shipping_primary_database** pour supprimer du serveur principal les informations relatives à la configuration d’envoi de journaux.</span><span class="sxs-lookup"><span data-stu-id="2d473-127">On the log shipping primary server, execute **sp_delete_log_shipping_primary_database** to delete information about the log shipping configuration from the primary server.</span></span> <span data-ttu-id="2d473-128">Le travail de sauvegarde est également supprimé.</span><span class="sxs-lookup"><span data-stu-id="2d473-128">This also deletes the backup job.</span></span>  
  
4.  <span data-ttu-id="2d473-129">Sur le serveur principal de copie des journaux de transaction, désactivez le travail de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="2d473-129">On the log shipping primary server, disable the backup job.</span></span> <span data-ttu-id="2d473-130">Pour plus d’informations, consultez [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="2d473-130">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
5.  <span data-ttu-id="2d473-131">Sur le serveur secondaire de copie des journaux de transaction, désactivez les travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="2d473-131">On the log shipping secondary server, disable the copy and restore jobs.</span></span>  
  
6.  <span data-ttu-id="2d473-132">Éventuellement, si vous n'utilisez plus la base de données secondaire de copie des journaux de transaction, vous pouvez la supprimer du serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="2d473-132">Optionally, if you are no longer using the log shipping secondary database, you can delete it from the secondary server.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2d473-133">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="2d473-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2d473-134">Mise à niveau de la copie des journaux de transaction vers SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2d473-134">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="2d473-135">Configurer la copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2d473-135">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="2d473-136">Ajouter une base de données secondaire dans une configuration de copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2d473-136">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="2d473-137">Supprimer une base de données secondaire dans une configuration de copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2d473-137">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="2d473-138">Surveiller la copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2d473-138">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="2d473-139">Basculer vers un serveur secondaire d’envoi de journaux &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2d473-139">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="2d473-140">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="2d473-140">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
## <a name="see-also"></a><span data-ttu-id="2d473-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d473-141">See Also</span></span>  
 <span data-ttu-id="2d473-142">[À propos de la copie des journaux des transactions &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2d473-142">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="2d473-143">Tables et procédures stockées liées à la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="2d473-143">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
