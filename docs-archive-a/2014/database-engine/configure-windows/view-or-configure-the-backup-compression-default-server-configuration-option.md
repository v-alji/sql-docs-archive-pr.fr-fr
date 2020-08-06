---
title: Afficher ou configurer l’option de configuration de serveur backup compression default | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], backup compression default option
- backup compression [SQL Server], backup compression default Option
ms.assetid: 23029395-3e93-4c29-b7d6-e5a47a3526ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02458c069d7c155b199e24feb7ef028ae0f258a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614829"
---
# <a name="view-or-configure-the-backup-compression-default-server-configuration-option"></a><span data-ttu-id="51be5-102">Afficher ou configurer l'option de configuration de serveur backup compression default</span><span class="sxs-lookup"><span data-stu-id="51be5-102">View or Configure the backup compression default Server Configuration Option</span></span>
  <span data-ttu-id="51be5-103">Cette rubrique explique comment afficher ou configurer l’option de configuration de serveur **backup compression default** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51be5-103">This topic describes how to view or configure the **backup compression default** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="51be5-104">L’option **valeur par défaut de compression de la sauvegarde** détermine si l’instance de serveur crée des sauvegardes compressées par défaut.</span><span class="sxs-lookup"><span data-stu-id="51be5-104">The **backup compression default** option determines whether the server instance creates compressed backups by default.</span></span> <span data-ttu-id="51be5-105">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est installé, l’option **valeur par défaut de compression de la sauvegarde** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="51be5-105">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed, the **backup compression default** option is off.</span></span>  
  
 <span data-ttu-id="51be5-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="51be5-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="51be5-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="51be5-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="51be5-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="51be5-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="51be5-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="51be5-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="51be5-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="51be5-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="51be5-111">**Pour afficher ou configurer l'option valeur par défaut de compression de la sauvegarde, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="51be5-111">**To view or configure the backup compression default option, using:**</span></span>  
  
     [<span data-ttu-id="51be5-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="51be5-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="51be5-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="51be5-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="51be5-114">**Suivi :**  [Après avoir configuré l’option Compression par défaut des sauvegardes](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="51be5-114">**Follow Up:**  [After you configure the backup compression default option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="51be5-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="51be5-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="51be5-116">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="51be5-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="51be5-117">La compression de la sauvegarde n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51be5-117">Backup compression is not available in all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="51be5-118">Pour plus d’informations, consultez [fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="51be5-118">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="51be5-119">Par défaut, la compression augmente considérablement l'utilisation de l'UC et l'UC supplémentaire consommée par le processus de compression peut avoir un impact néfaste sur les opérations simultanées.</span><span class="sxs-lookup"><span data-stu-id="51be5-119">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="51be5-120">Par conséquent, il peut être préférable de créer une sauvegarde compressée de priorité basse dans une session où l’utilisation de l’UC est limitée par [Resource Governor](../../relational-databases/resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="51be5-120">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../../relational-databases/resource-governor/resource-governor.md).</span></span> <span data-ttu-id="51be5-121">Pour plus d'informations, consultez [Utiliser Resource Governor pour limiter l’utilisation de l’UC par compression de la sauvegarde &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="51be5-121">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="51be5-122">Recommandations</span><span class="sxs-lookup"><span data-stu-id="51be5-122">Recommendations</span></span>  
  
-   <span data-ttu-id="51be5-123">Lors de la création d'une sauvegarde individuelle, de la configuration de la copie des journaux de transaction ou de la création d'un plan de maintenance, vous pouvez remplacer la valeur par défaut au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="51be5-123">When you are creating an individual backup, configuring a log shipping configuration, or creating a maintenance plan, you can override the server-level default.</span></span>  
  
-   <span data-ttu-id="51be5-124">La compression de la sauvegarde est prise en charge pour les unités de sauvegarde sur disque et les périphériques de sauvegarde sur bande.</span><span class="sxs-lookup"><span data-stu-id="51be5-124">Backup compression is supported for both disk backup devices and tape backup devices.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="51be5-125">Sécurité</span><span class="sxs-lookup"><span data-stu-id="51be5-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="51be5-126">Autorisations</span><span class="sxs-lookup"><span data-stu-id="51be5-126">Permissions</span></span>  
 <span data-ttu-id="51be5-127">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="51be5-127">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="51be5-128">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="51be5-128">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="51be5-129">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="51be5-129">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="51be5-130">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="51be5-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-the-backup-compression-default-option"></a><span data-ttu-id="51be5-131">Pour afficher ou configurer l'option backup compression default</span><span class="sxs-lookup"><span data-stu-id="51be5-131">To view or configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="51be5-132">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="51be5-132">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="51be5-133">Cliquez sur le nœud **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="51be5-133">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="51be5-134">Sous **Sauvegarde et restauration**, **Compresser la sauvegarde** affiche le paramètre actuel de l’option **valeur par défaut de compression de la sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="51be5-134">Under **Backup and restore**, **Compress backup** shows the current setting of the **backup compression default** option.</span></span> <span data-ttu-id="51be5-135">Ce paramètre détermine la valeur par défaut au niveau du serveur pour la compression des sauvegardes, comme suit :</span><span class="sxs-lookup"><span data-stu-id="51be5-135">This setting determines the server-level default for compressing backups, as follows:</span></span>  
  
    -   <span data-ttu-id="51be5-136">Si la case à cocher **Compresser la sauvegarde** est désactivée, les nouvelles sauvegardes ne sont pas compressées par défaut.</span><span class="sxs-lookup"><span data-stu-id="51be5-136">If the **Compress backup** box is blank, new backups are uncompressed by default.</span></span>  
  
    -   <span data-ttu-id="51be5-137">Si la case à cocher **Compresser la sauvegarde** est activée, les nouvelles sauvegardes sont compressées par défaut.</span><span class="sxs-lookup"><span data-stu-id="51be5-137">If the **Compress backup** box is checked, new backups are compressed by default.</span></span>  
  
     <span data-ttu-id="51be5-138">Si vous êtes membre du rôle serveur fixe **sysadmin** ou **serveradmin** , vous pouvez également modifier le paramètre par défaut en activant la case à cocher **Compresser la sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="51be5-138">If you are a member of the **sysadmin** or **serveradmin** fixed server role, you can also change the default setting by clicking the **Compress backup** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="51be5-139">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="51be5-139">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-backup-compression-default-option"></a><span data-ttu-id="51be5-140">Pour afficher l'option backup compression default</span><span class="sxs-lookup"><span data-stu-id="51be5-140">To view the backup compression default option</span></span>  
  
1.  <span data-ttu-id="51be5-141">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51be5-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="51be5-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="51be5-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="51be5-143">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="51be5-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="51be5-144">L'exemple suivant interroge la vue de catalogue [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) pour déterminer la valeur de `backup compression default`.</span><span class="sxs-lookup"><span data-stu-id="51be5-144">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to determine the value for `backup compression default`.</span></span> <span data-ttu-id="51be5-145">La valeur 0 indique que la compression de la sauvegarde est désactivée, et la valeur 1 indique que la compression de la sauvegarde est activée.</span><span class="sxs-lookup"><span data-stu-id="51be5-145">A value of 0 means that backup compression is off, and a value of 1 means that backup compression is enabled.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
SELECT value   
FROM sys.configurations   
WHERE name = 'backup compression default' ;  
GO  
  
```  
  
#### <a name="to-configure-the-backup-compression-default-option"></a><span data-ttu-id="51be5-146">Pour configurer l'option backup compression default</span><span class="sxs-lookup"><span data-stu-id="51be5-146">To configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="51be5-147">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51be5-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="51be5-148">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="51be5-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="51be5-149">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="51be5-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="51be5-150">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour configurer l’instance de serveur afin de créer des sauvegardes compressées par défaut.</span><span class="sxs-lookup"><span data-stu-id="51be5-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the server instance to create compressed backups by default.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_configure 'backup compression default', 1 ;  
RECONFIGURE WITH OVERRIDE ;  
GO  
  
```  
  
 <span data-ttu-id="51be5-151">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="51be5-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-backup-compression-default-option"></a><a name="FollowUp"></a> <span data-ttu-id="51be5-152">Suivi : Après avoir configuré l’option Compression par défaut des sauvegardes</span><span class="sxs-lookup"><span data-stu-id="51be5-152">Follow Up: After you configure the backup compression default option</span></span>  
 <span data-ttu-id="51be5-153">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="51be5-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51be5-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51be5-154">See Also</span></span>  
 <span data-ttu-id="51be5-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="51be5-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="51be5-156">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="51be5-156">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="51be5-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="51be5-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="51be5-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="51be5-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="51be5-159">Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="51be5-159">Backup Overview &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/backup-overview-sql-server.md)  
  
  
