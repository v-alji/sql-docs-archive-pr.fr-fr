---
title: Configurer l’option de configuration de serveur user connections | Microsoft Docs
ms.custom: ''
ms.date: 12/02/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- simultaneous connections [SQL Server]
- user connections option [SQL Server]
- users [SQL Server], simultaneous connections
- maximum number of simultaneous user connections
- connections [SQL Server], simultaneous
ms.assetid: 53beee6e-59fe-4276-9abb-8f1cec2a3508
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fbb4a17de131c128b5b1bb7cfb35a33b9d0037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601089"
---
# <a name="configure-the-user-connections-server-configuration-option"></a><span data-ttu-id="0f77a-102">Configurer l'option de configuration de serveur user connections</span><span class="sxs-lookup"><span data-stu-id="0f77a-102">Configure the user connections Server Configuration Option</span></span>
  <span data-ttu-id="0f77a-103">Cette rubrique explique comment définir l'option de configuration de serveur **user connections** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f77a-103">This topic describes how to set the **user connections** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0f77a-104">L'option **user connections** spécifie le nombre maximal de connexions utilisateur simultanées autorisées sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f77a-104">The **user connections** option specifies the maximum number of simultaneous user connections that are allowed on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0f77a-105">Le nombre réel de connexions utilisateur autorisées dépend également de la version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisée, ainsi que des limites de vos applications et de votre matériel.</span><span class="sxs-lookup"><span data-stu-id="0f77a-105">The actual number of user connections allowed also depends on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using, and also the limits of your application or applications and hardware.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0f77a-106">autorise un maximum de 32 767 connexions utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f77a-106">allows a maximum of 32,767 user connections.</span></span> <span data-ttu-id="0f77a-107">L’option **user connections** est dynamique (auto-configurable). Ainsi, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applique automatiquement le nombre maximal de connexions utilisateur en fonction des besoins, jusqu’à la valeur maximale autorisée.</span><span class="sxs-lookup"><span data-stu-id="0f77a-107">Because **user connections** is a dynamic (self-configuring) option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adjusts the maximum number of user connections automatically as needed, up to the maximum value allowable.</span></span> <span data-ttu-id="0f77a-108">Par exemple, si seuls 10 utilisateurs sont connectés, 10 objets connexion utilisateur sont alloués.</span><span class="sxs-lookup"><span data-stu-id="0f77a-108">For example, if only 10 users are logged in, 10 user connection objects are allocated.</span></span> <span data-ttu-id="0f77a-109">Dans la plupart des cas, il est inutile de modifier la valeur de cette option.</span><span class="sxs-lookup"><span data-stu-id="0f77a-109">In most cases, you do not have to change the value for this option.</span></span> <span data-ttu-id="0f77a-110">La valeur par défaut est zéro, ce qui signifie que le nombre maximal (32 767) de connexions utilisateur est autorisé.</span><span class="sxs-lookup"><span data-stu-id="0f77a-110">The default is 0, which means that the maximum (32,767) user connections are allowed.</span></span>  
  
 <span data-ttu-id="0f77a-111">Pour déterminer le nombre maximal de connexions utilisateur autorisé par votre système, vous pouvez exécuter [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) ou interroger l’affichage catalogue [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="0f77a-111">To determine the maximum number of user connections that your system allows, you can execute [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) or query the [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="0f77a-112">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="0f77a-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0f77a-113">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="0f77a-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0f77a-114">Recommandations</span><span class="sxs-lookup"><span data-stu-id="0f77a-114">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="0f77a-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0f77a-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0f77a-116">**Pour configurer l'option user connections, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="0f77a-116">**To configure the user connections option, using:**</span></span>  
  
     [<span data-ttu-id="0f77a-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0f77a-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0f77a-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0f77a-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="0f77a-119">**Suivi :**  [Après avoir configuré l’option user connections](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="0f77a-119">**Follow Up:**  [After you configure the user connections option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0f77a-120">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="0f77a-120">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="0f77a-121">Recommandations</span><span class="sxs-lookup"><span data-stu-id="0f77a-121">Recommendations</span></span>  
  
-   <span data-ttu-id="0f77a-122">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0f77a-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="0f77a-123">L'option **user connections** vous aide à éviter de surcharger le serveur avec de trop nombreuses connexions simultanées.</span><span class="sxs-lookup"><span data-stu-id="0f77a-123">Using the **user connections** option helps avoid overloading the server with too many concurrent connections.</span></span> <span data-ttu-id="0f77a-124">Pour estimer le nombre de connexions à définir, prenez comme base la configuration de votre système et les besoins des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0f77a-124">You can estimate the number of connections based on system and user requirements.</span></span> <span data-ttu-id="0f77a-125">Par exemple, pour un système comptant de nombreux utilisateurs, chaque utilisateur n'a pas obligatoirement besoin d'une connexion unique.</span><span class="sxs-lookup"><span data-stu-id="0f77a-125">For example, on a system with many users, each user would not usually require a unique connection.</span></span> <span data-ttu-id="0f77a-126">Les connexions peuvent être partagées par plusieurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0f77a-126">Connections can be shared among users.</span></span> <span data-ttu-id="0f77a-127">Les utilisateurs qui exécutent des applications OLE DB ont besoin d’une connexion pour chaque objet de connexion ouvert. Les utilisateurs qui exécutent des applications ODBC (Open Database Connectivity) ont besoin d’une connexion pour chaque descripteur de connexion actif dans l’application. Les utilisateurs qui exécutent des applications de type bibliothèque de base de données (DB-Library) ont besoin d’une connexion pour chaque processus démarré qui appelle la fonction **dbopen** de la bibliothèque de base de données.</span><span class="sxs-lookup"><span data-stu-id="0f77a-127">Users running OLE DB applications need a connection for each open connection object, users running Open Database Connectivity (ODBC) applications need a connection for each active connection handle in the application, and users running DB-Library applications need one connection for each process started that calls the DB-Library **dbopen** function.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0f77a-128">Si vous devez utiliser cette option, n'attribuez pas une valeur trop élevée, car chaque connexion possède un espace réservé, qu'elle soit utilisée ou non.</span><span class="sxs-lookup"><span data-stu-id="0f77a-128">If you must use this option, do not set the value too high, because each connection has overhead regardless of whether the connection is being used.</span></span> <span data-ttu-id="0f77a-129">Si vous dépassez le nombre maximal de connexions utilisateur, un message d'erreur s'affiche et vous devez attendre qu'une autre connexion soit disponible pour pouvoir vous connecter.</span><span class="sxs-lookup"><span data-stu-id="0f77a-129">If you exceed the maximum number of user connections, you receive an error message and are not able to connect until another connection becomes available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0f77a-130">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0f77a-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0f77a-131">Autorisations</span><span class="sxs-lookup"><span data-stu-id="0f77a-131">Permissions</span></span>  
 <span data-ttu-id="0f77a-132">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0f77a-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="0f77a-133">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="0f77a-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="0f77a-134">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="0f77a-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0f77a-135">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0f77a-135">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="0f77a-136">Pour configurer l'option user connections</span><span class="sxs-lookup"><span data-stu-id="0f77a-136">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="0f77a-137">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-137">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0f77a-138">Cliquez sur le nœud **Connexions** .</span><span class="sxs-lookup"><span data-stu-id="0f77a-138">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="0f77a-139">Sous **Connexions**, dans la zone **Nombre maximal de connexions simultanées** , tapez ou sélectionnez une valeur comprise entre 0 et 32 767 pour définir le nombre maximal d'utilisateurs autorisés à se connecter simultanément à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f77a-139">Under **Connections**, in the **Max number of concurrent connections** box, type or select a value from 0 through 32767 to set the maximum number of users that are allowed to connect simultaneously to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="0f77a-140">Redémarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f77a-140">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0f77a-141">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0f77a-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="0f77a-142">Pour configurer l'option user connections</span><span class="sxs-lookup"><span data-stu-id="0f77a-142">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="0f77a-143">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f77a-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0f77a-144">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0f77a-145">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0f77a-146">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `user connections` la valeur `325` utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0f77a-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the value of the `user connections` option to `325` users.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'user connections', 325 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="0f77a-147">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0f77a-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-user-connections-option"></a><a name="FollowUp"></a> <span data-ttu-id="0f77a-148">Suivi : Après avoir configuré l’option user connections</span><span class="sxs-lookup"><span data-stu-id="0f77a-148">Follow Up: After you configure the user connections option</span></span>  
 <span data-ttu-id="0f77a-149">Le serveur doit être redémarré pour que le paramètre puisse être effet.</span><span class="sxs-lookup"><span data-stu-id="0f77a-149">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f77a-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f77a-150">See Also</span></span>  
 <span data-ttu-id="0f77a-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0f77a-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="0f77a-152">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0f77a-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="0f77a-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f77a-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
