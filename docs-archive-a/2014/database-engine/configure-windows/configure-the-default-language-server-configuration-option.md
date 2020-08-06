---
title: Configurer l’option de configuration de serveur default language | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default language option
ms.assetid: c08c26d8-5a62-487e-a4ee-4c529e4f9287
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b0e62fef112dad2c6c307946bc720adf1f14d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708612"
---
# <a name="configure-the-default-language-server-configuration-option"></a><span data-ttu-id="4f2a8-102">Configurer l'option de configuration de serveur default language</span><span class="sxs-lookup"><span data-stu-id="4f2a8-102">Configure the default language Server Configuration Option</span></span>
  <span data-ttu-id="4f2a8-103">Cette rubrique explique comment configurer l'option de configuration de serveur **default language** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f2a8-103">This topic describes how to configure the **default language** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4f2a8-104">L'option **default language** spécifie la langue par défaut pour toutes les connexions nouvellement créées.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-104">The **default language** option specifies the default language for all newly created logins.</span></span> <span data-ttu-id="4f2a8-105">Pour définir la langue par défaut, spécifiez la valeur **langid** de la langue souhaitée.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-105">To set default language, specify the **langid** value of the language you want.</span></span> <span data-ttu-id="4f2a8-106">La valeur **langid** peut être obtenue en interrogeant la vue de compatibilité **sys.syslanguages** .</span><span class="sxs-lookup"><span data-stu-id="4f2a8-106">The **langid** value can be obtained by querying the **sys.syslanguages** compatibility view.</span></span>  
  
 <span data-ttu-id="4f2a8-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4f2a8-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4f2a8-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="4f2a8-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4f2a8-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="4f2a8-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4f2a8-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4f2a8-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4f2a8-111">**Pour configurer l'option default language, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="4f2a8-111">**To configure the default language option, using:**</span></span>  
  
     [<span data-ttu-id="4f2a8-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f2a8-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4f2a8-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f2a8-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="4f2a8-114">**Suivi :**  [Après avoir configuré l’option default language](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="4f2a8-114">**Follow Up:**  [After you configure the default language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4f2a8-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4f2a8-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4f2a8-116">Recommandations</span><span class="sxs-lookup"><span data-stu-id="4f2a8-116">Recommendations</span></span>  
  
-   <span data-ttu-id="4f2a8-117">La langue par défaut pour une session ouverte peut être remplacée en utilisant CREATE LOGIN ou ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-117">The default language for a login can be overridden by using CREATE LOGIN or ALTER LOGIN.</span></span> <span data-ttu-id="4f2a8-118">Elle correspond à celle définie dès l'ouverture de la session, à moins qu’elle ne soit remplacée à chaque session à l’aide des API ODBC (Open Database Connectivity) ou OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-118">The default language for a session is the language for that session's login, unless overridden on a per-session basis by using the Open Database Connectivity (ODBC) or OLE DB APIs.</span></span> <span data-ttu-id="4f2a8-119">Remarque : Vous ne pouvez définir l’option **default language** que sur un identificateur de langue existant dans [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32).</span><span class="sxs-lookup"><span data-stu-id="4f2a8-119">Note that you can only set the **default language** option to a language ID defined in [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32).</span></span> <span data-ttu-id="4f2a8-120">Lorsque vous utilisez des bases de données autonomes, il est possible de définir une langue par défaut pour une base de données à l'aide de CREATE DATABASE ou de ALTER DATABASE, et pour les utilisateurs de bases de données autonomes, à l'aide de CREATE USER ou de ALTER USER.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-120">When you are using contained databases, a default language can be set for a database by using CREATE DATABASE or ALTER DATABASE, and for contained database users by using CREATE USER or ALTER USER.</span></span> <span data-ttu-id="4f2a8-121">La langue par défaut dans une base de données autonome peut être définie à l'aide de la valeur **langid**, du nom de la langue, ou d'un alias de langue répertorié dans **sys.syslanguages**.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-121">Setting default languages in a contained database accepts **langid** value, the language name, or a language alias as listed in **sys.syslanguages**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4f2a8-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4f2a8-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f2a8-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4f2a8-123">Permissions</span></span>  
 <span data-ttu-id="4f2a8-124">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="4f2a8-125">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="4f2a8-126">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="4f2a8-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4f2a8-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f2a8-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="4f2a8-128">Pour configurer l'option default language</span><span class="sxs-lookup"><span data-stu-id="4f2a8-128">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="4f2a8-129">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="4f2a8-130">Cliquez sur le nœud **Paramètres divers du serveur** .</span><span class="sxs-lookup"><span data-stu-id="4f2a8-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="4f2a8-131">Dans la zone **Langue par défaut pour l'utilisateur** , sélectionnez la langue dans laquelle [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit afficher les messages système.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-131">In the **Default language for users** box, choose the language in which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should display system messages.</span></span>  
  
     <span data-ttu-id="4f2a8-132">La langue par défaut est l'anglais.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-132">The default language is English.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4f2a8-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f2a8-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="4f2a8-134">Pour configurer l'option default language</span><span class="sxs-lookup"><span data-stu-id="4f2a8-134">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="4f2a8-135">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f2a8-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f2a8-136">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f2a8-137">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4f2a8-138">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `default language` la valeur Français (`2`).</span><span class="sxs-lookup"><span data-stu-id="4f2a8-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `default language` option to French (`2`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'default language', 2 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
 <span data-ttu-id="4f2a8-139">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a8-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="4f2a8-140">Suivi : Après avoir configuré l’option default language</span><span class="sxs-lookup"><span data-stu-id="4f2a8-140">Follow Up: After you configure the default language option</span></span>  
 <span data-ttu-id="4f2a8-141">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2a8-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f2a8-142">See Also</span></span>  
 <span data-ttu-id="4f2a8-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f2a8-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="4f2a8-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f2a8-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 <span data-ttu-id="4f2a8-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f2a8-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="4f2a8-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f2a8-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span></span>  
 <span data-ttu-id="4f2a8-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f2a8-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="4f2a8-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f2a8-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="4f2a8-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f2a8-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="4f2a8-150">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4f2a8-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="4f2a8-151">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4f2a8-151">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
