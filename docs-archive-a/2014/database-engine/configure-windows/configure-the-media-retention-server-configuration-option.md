---
title: Configurer l’option de configuration de serveur media retention | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- backup retention duration [SQL Server]
- backup sets [SQL Server], retention duration
- media retention option
ms.assetid: 12e9fe6a-20a5-4c6e-9cc9-d500c003b70a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 092e0a2b5cfc30fd2d2362645fc1242bf4a1651e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603626"
---
# <a name="configure-the-media-retention-server-configuration-option"></a><span data-ttu-id="dd260-102">Configurer l'option de configuration de serveur media retention</span><span class="sxs-lookup"><span data-stu-id="dd260-102">Configure the media retention Server Configuration Option</span></span>
  <span data-ttu-id="dd260-103">Cette rubrique explique comment configurer l'option de configuration de serveur **media retention** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd260-103">This topic describes how to configure the **media retention** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="dd260-104">L'option **media retention** spécifie la durée de rétention de chaque jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dd260-104">The **media retention** option specifies the length of time to retain each backup set.</span></span> <span data-ttu-id="dd260-105">Cette option permet d'éviter l'écrasement des sauvegardes pendant le nombre de jours spécifié.</span><span class="sxs-lookup"><span data-stu-id="dd260-105">The option helps protect backups from being overwritten until the specified number of days has elapsed.</span></span> <span data-ttu-id="dd260-106">Après avoir configuré l'option **media retention**, il est inutile de spécifier la durée de rétention des sauvegardes système à chaque sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dd260-106">After you configure **media retention** option, you do not have to specify the length of time to retain system backups each time you perform a backup.</span></span> <span data-ttu-id="dd260-107">La valeur par défaut est de 0 jour et la valeur maximum de 365 jours.</span><span class="sxs-lookup"><span data-stu-id="dd260-107">The default value is 0 days, and the maximum value is 365 days.</span></span>  
  
 <span data-ttu-id="dd260-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="dd260-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dd260-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="dd260-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dd260-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="dd260-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="dd260-111">Recommandations</span><span class="sxs-lookup"><span data-stu-id="dd260-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="dd260-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dd260-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dd260-113">**Pour configurer l'option media retention, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="dd260-113">**To configure the media retention option, using:**</span></span>  
  
     [<span data-ttu-id="dd260-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dd260-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dd260-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dd260-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="dd260-116">**Suivi :**  [Après avoir configuré l’option media retention](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="dd260-116">**Follow Up:**  [After you configure the media retention option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dd260-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="dd260-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="dd260-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="dd260-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="dd260-119">Si vous utilisez le support de sauvegarde avant que le nombre de jours spécifié soit écoulé, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] génère un message d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="dd260-119">If you use the backup medium before the set number of days has passed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] issues a warning message.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dd260-120">ne génère aucun avertissement, sauf si vous modifiez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="dd260-120">does not issue a warning unless you change the default.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="dd260-121">Recommandations</span><span class="sxs-lookup"><span data-stu-id="dd260-121">Recommendations</span></span>  
  
-   <span data-ttu-id="dd260-122">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd260-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="dd260-123">L'option **media retention** peut être annulée par l'utilisation de la clause RETAINDAYS de l'instruction [BACKUP](/sql/t-sql/statements/backup-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="dd260-123">The **media retention** option can be overridden by using the RETAINDAYS clause of the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dd260-124">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dd260-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dd260-125">Autorisations</span><span class="sxs-lookup"><span data-stu-id="dd260-125">Permissions</span></span>  
 <span data-ttu-id="dd260-126">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="dd260-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="dd260-127">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="dd260-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="dd260-128">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="dd260-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dd260-129">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dd260-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="dd260-130">Pour configurer l'option Rétention du support</span><span class="sxs-lookup"><span data-stu-id="dd260-130">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="dd260-131">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="dd260-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="dd260-132">Cliquez sur le nœud **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="dd260-132">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="dd260-133">Sous **Sauvegarde et restauration**, dans la zone **Délai de rétention par défaut du support de sauvegarde (jours)** , entrez ou sélectionnez une valeur comprise entre 0 et 365 pour définir le nombre de jours pendant lesquels le support de sauvegarde sera conservé après une sauvegarde de la base de données ou du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="dd260-133">Under **Backup/Restore**, in the **Default backup media retention** box, type or select a value from 0 through 365 to set the number of days the backup medium will be retained after a database or transaction log backup.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dd260-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dd260-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="dd260-135">Pour configurer l'option Rétention du support</span><span class="sxs-lookup"><span data-stu-id="dd260-135">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="dd260-136">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd260-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dd260-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="dd260-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dd260-138">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="dd260-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="dd260-139">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `media retention` la valeur `60` jours.</span><span class="sxs-lookup"><span data-stu-id="dd260-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `media retention` option to `60` days.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'media retention', 60 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="dd260-140">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd260-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-media-retention-option"></a><a name="FollowUp"></a> <span data-ttu-id="dd260-141">Suivi : Après avoir configuré l’option media retention</span><span class="sxs-lookup"><span data-stu-id="dd260-141">Follow Up: After you configure the media retention option</span></span>  
 <span data-ttu-id="dd260-142">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="dd260-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd260-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd260-143">See Also</span></span>  
 <span data-ttu-id="dd260-144">[Sauvegarde et restauration des bases de données SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="dd260-144">[Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="dd260-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dd260-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="dd260-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dd260-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="dd260-147">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dd260-147">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="dd260-148">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dd260-148">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
