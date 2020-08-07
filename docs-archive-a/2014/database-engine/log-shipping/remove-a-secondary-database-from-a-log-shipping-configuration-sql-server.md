---
title: Supprimer une base de données secondaire dans une configuration de la copie des journaux de transaction (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- deleting secondary databases
- secondary databases [SQL Server], in log shipping
- removing secondary databases
- secondary data files [SQL Server], removing
- log shipping [SQL Server], secondary databases
ms.assetid: ebe368a4-ca1c-45d0-9a71-3ddbd5b26a8e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 119f2762d41d0787b6b3279507e9671e89fddfca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611271"
---
# <a name="remove-a-secondary-database-from-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="9f78c-102">Supprimer une base de données secondaire dans une configuration de copie des journaux de transaction (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9f78c-102">Remove a Secondary Database from a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="9f78c-103">Cette rubrique explique comment supprimer la base de données secondaire de copie des journaux de transaction dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f78c-103">This topic describes how to remove a log shipping secondary database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9f78c-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="9f78c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9f78c-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="9f78c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9f78c-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9f78c-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9f78c-107">**Pour supprimer une base de données secondaire de copie des journaux de transaction, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="9f78c-107">**To remove a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="9f78c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9f78c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9f78c-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9f78c-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="9f78c-110">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9f78c-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9f78c-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="9f78c-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9f78c-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9f78c-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9f78c-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="9f78c-113">Permissions</span></span>  
 <span data-ttu-id="9f78c-114">Les procédures stockées de copie des journaux de transaction nécessitent l’appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="9f78c-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9f78c-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9f78c-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-a-log-shipping-secondary-database"></a><span data-ttu-id="9f78c-116">Pour supprimer une base de données secondaire pour la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="9f78c-116">To remove a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="9f78c-117">Connectez-vous à l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est actuellement le serveur principal de copie des journaux de transaction et développez-la.</span><span class="sxs-lookup"><span data-stu-id="9f78c-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="9f78c-118">Développez **Bases de données**, cliquez avec le bouton droit sur la base de données primaire de copie des journaux de transaction, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9f78c-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9f78c-119">Sous **Sélectionner une page**, cliquez sur **Envoi de journaux de transaction**.</span><span class="sxs-lookup"><span data-stu-id="9f78c-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="9f78c-120">Sous **Instances de serveurs et bases de données secondaires**, cliquez sur la base de données à supprimer.</span><span class="sxs-lookup"><span data-stu-id="9f78c-120">Under **Secondary server instances and databases**, click the database you want to remove.</span></span>  
  
5.  <span data-ttu-id="9f78c-121">Cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="9f78c-121">Click **Remove**.</span></span>  
  
6.  <span data-ttu-id="9f78c-122">Cliquez sur **OK** pour mettre à jour la configuration.</span><span class="sxs-lookup"><span data-stu-id="9f78c-122">Click **OK** to update the configuration.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9f78c-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9f78c-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-secondary-database"></a><span data-ttu-id="9f78c-124">Pour supprimer une base de données secondaire</span><span class="sxs-lookup"><span data-stu-id="9f78c-124">To Remove a Secondary Database</span></span>  
  
1.  <span data-ttu-id="9f78c-125">Sur le serveur principal, exécutez [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) pour supprimer du serveur principal les informations relatives à la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="9f78c-125">On the primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="9f78c-126">Sur le serveur secondaire, exécutez [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) pour supprimer la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="9f78c-126">On the secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9f78c-127">Si aucune autre base de données secondaire portant le même ID secondaire n’existe, **sp_delete_log_shipping_secondary_primary** est appelé par **sp_delete_log_shipping_secondary_database** et supprime l’entrée de l’ID secondaire, ainsi que les travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="9f78c-127">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="9f78c-128">Sur le serveur secondaire, désactivez les travaux de copie et de restauration.</span><span class="sxs-lookup"><span data-stu-id="9f78c-128">On the secondary server, disable the copy and restore jobs.</span></span> <span data-ttu-id="9f78c-129">Pour plus d’informations, consultez [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="9f78c-129">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9f78c-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9f78c-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9f78c-131">Mise à niveau de la copie des journaux de transaction vers SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9f78c-131">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="9f78c-132">Configurer la copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9f78c-132">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="9f78c-133">Ajouter une base de données secondaire dans une configuration de copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9f78c-133">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="9f78c-134">Supprimer la copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9f78c-134">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="9f78c-135">Afficher le rapport de la copie des journaux de transaction &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9f78c-135">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="9f78c-136">Surveiller la copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9f78c-136">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="9f78c-137">Basculer vers un serveur secondaire d’envoi de journaux &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9f78c-137">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f78c-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f78c-138">See Also</span></span>  
 <span data-ttu-id="9f78c-139">[À propos de la copie des journaux des transactions &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f78c-139">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="9f78c-140">Tables et procédures stockées liées à la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="9f78c-140">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
