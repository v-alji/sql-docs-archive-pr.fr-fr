---
title: Afficher ou modifier des propriétés de serveur (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- viewing server properties
- server properties [SQL Server]
- displaying server properties
- servers [SQL Server], viewing
ms.assetid: 55f3ac04-5626-4ad2-96bd-a1f1b079659d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 415d4e2d1aaa3166ae4df2dea53b34e064544e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697151"
---
# <a name="view-or-change-server-properties-sql-server"></a><span data-ttu-id="ee3a0-102">Afficher ou modifier des propriétés de serveur (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ee3a0-102">View or Change Server Properties (SQL Server)</span></span>
  <span data-ttu-id="ee3a0-103">Cette rubrique explique comment afficher ou modifier les propriétés d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]ou SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-103">This topic describes how to view or change the properties of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Configuration Manager.</span></span>  
  
 <span data-ttu-id="ee3a0-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ee3a0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ee3a0-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ee3a0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ee3a0-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ee3a0-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ee3a0-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ee3a0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ee3a0-108">**Pour afficher ou modifier des propriétés de serveur à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="ee3a0-108">**To view or change server properties, using:**</span></span>  
  
     [<span data-ttu-id="ee3a0-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee3a0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ee3a0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee3a0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="ee3a0-111">Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="ee3a0-111">SQL Server Configuration Manager</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="ee3a0-112">**Suivi :**  [après avoir modifié les propriétés du serveur](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="ee3a0-112">**Follow Up:**  [After you change server properties](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ee3a0-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ee3a0-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ee3a0-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ee3a0-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ee3a0-115">Lorsque vous utilisez sp_configure, vous devez exécuter RECONFIGURE ou RECONFIGURE WITH OVERRIDE après la définition d'une option de configuration.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-115">When using sp_configure, you must run either RECONFIGURE or RECONFIGURE WITH OVERRIDE after setting a configuration option.</span></span> <span data-ttu-id="ee3a0-116">L'instruction RECONFIGURE WITH OVERRIDE est généralement réservée aux options de configuration qui doivent être utilisées avec une extrême prudence.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-116">The RECONFIGURE WITH OVERRIDE statement is usually reserved for configuration options that should be used with extreme caution.</span></span> <span data-ttu-id="ee3a0-117">Cependant, RECONFIGURE WITH OVERRIDE fonctionne avec toutes les options de configuration, et vous pouvez l'utiliser pour remplacer RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-117">However, RECONFIGURE WITH OVERRIDE works for all configuration options, and you can use it in place of RECONFIGURE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee3a0-118">RECONFIGURE s'exécute au sein d'une transaction.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-118">RECONFIGURE executes within a transaction.</span></span> <span data-ttu-id="ee3a0-119">Si l'une des opérations de reconfiguration échoue, aucune de ces opérations ne prend effet.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-119">If any of the reconfigure operations fail, none of the reconfigure operations will take effect.</span></span>  
  
-   <span data-ttu-id="ee3a0-120">Certaines pages de propriétés présentent des informations fournies par l'intermédiaire de WMI (Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="ee3a0-120">Some property pages present information obtained via Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="ee3a0-121">Pour afficher ces pages, WMI doit être installé sur l'ordinateur qui exécute [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee3a0-121">To display those pages, WMI must be installed on the computer running [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ee3a0-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ee3a0-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ee3a0-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ee3a0-123">Permissions</span></span>  
 <span data-ttu-id="ee3a0-124">Pour plus d’informations, consultez [Rôles de niveau serveur](../../relational-databases/security/authentication-access/server-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ee3a0-124">For more information, see [Server-Level Roles](../../relational-databases/security/authentication-access/server-level-roles.md).</span></span>  
  
 <span data-ttu-id="ee3a0-125">Les autorisations d’exécution sur sans paramètre `sp_configure` ou avec uniquement le premier paramètre sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-125">Execute permissions on `sp_configure` with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="ee3a0-126">Pour exécuter `sp_configure` avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction REconfigure, un utilisateur doit disposer de l’autorisation ALTER Settings au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-126">To execute `sp_configure` with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="ee3a0-127">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="ee3a0-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ee3a0-128">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee3a0-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="ee3a0-129">Pour afficher ou modifier des propriétés de serveur</span><span class="sxs-lookup"><span data-stu-id="ee3a0-129">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="ee3a0-130">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-130">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ee3a0-131">Dans la boîte de dialogue **Propriétés du serveur** , cliquez sur une page pour afficher ou modifier les informations du serveur relatives à cette page.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-131">In the **Server Properties** dialog box, click a page to view or change server information about that page.</span></span> <span data-ttu-id="ee3a0-132">Certaines propriétés sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-132">Some properties are read-only.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ee3a0-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee3a0-133">Using Transact-SQL</span></span>  
  
#### <a name="to-view-server-properties-by-using-the-serverproperty-built-in-function"></a><span data-ttu-id="ee3a0-134">Pour afficher les propriétés du serveur à l'aide de la fonction intégrée SERVERPROPERTY</span><span class="sxs-lookup"><span data-stu-id="ee3a0-134">To view server properties by using the SERVERPROPERTY built-in function</span></span>  
  
1.  <span data-ttu-id="ee3a0-135">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee3a0-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ee3a0-136">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ee3a0-137">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ee3a0-138">Cet exemple utilise la fonction intégrée [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) dans une instruction `SELECT` pour retourner des informations sur le serveur actif.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-138">This example uses the [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) built-in function in a `SELECT` statement to return information about the current server.</span></span> <span data-ttu-id="ee3a0-139">Ce scénario est utile lorsque plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont installées sur un serveur basé sur Windows et que le client doit ouvrir une autre connexion vers l'instance utilisée par la connexion actuelle.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-139">This scenario is useful when there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on a Windows-based server, and the client must open another connection to the same instance that is used by the current connection.</span></span>  
  
    ```sql  
    SELECT CONVERT( sysname, SERVERPROPERTY('servername'));  
    GO  
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysservers-catalog-view"></a><span data-ttu-id="ee3a0-140">Pour afficher les propriétés du serveur à l'aide de la vue de catalogue sys.servers</span><span class="sxs-lookup"><span data-stu-id="ee3a0-140">To view server properties by using the sys.servers catalog view</span></span>  
  
1.  <span data-ttu-id="ee3a0-141">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee3a0-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ee3a0-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ee3a0-143">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ee3a0-144">L’exemple suivant interroge l’affichage catalogue [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) pour retourner le nom (`name`) et l’ID (`server_id`) du serveur actuel, ainsi que le nom du fournisseur OLE DB (`provider`) pour vous connecter à un serveur lié.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-144">This example queries the [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) catalog view to return the name (`name`) and ID (`server_id`) of the current server, and the name of the OLE DB provider (`provider`) for connecting to a linked server.</span></span>  
  
    ```sql  
    USE AdventureWorks2012;   
    GO  
    SELECT name, server_id, provider  
    FROM sys.servers ;   
    GO
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysconfigurations-catalog-view"></a><span data-ttu-id="ee3a0-145">Pour afficher les propriétés du serveur à l'aide de la vue de catalogue sys.configurations</span><span class="sxs-lookup"><span data-stu-id="ee3a0-145">To view server properties by using the sys.configurations catalog view</span></span>  
  
1.  <span data-ttu-id="ee3a0-146">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee3a0-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ee3a0-147">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ee3a0-148">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-148">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ee3a0-149">L'exemple suivant interroge la vue de catalogue [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) pour retourner des informations sur chaque option de configuration du serveur sur le serveur actuel.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-149">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to return information about each server configuration option on the current server.</span></span> <span data-ttu-id="ee3a0-150">L'exemple retourne le nom (`name`) et la description (`description`) de l'option et indique si l'option est une option avancée (`is_advanced`).</span><span class="sxs-lookup"><span data-stu-id="ee3a0-150">The example returns the name (`name`) and description (`description`) of the option and whether the option is an advanced option (`is_advanced`).</span></span>  
  
    ```sql
    USE AdventureWorks2012;
    GO  
    SELECT name, description, is_advanced  
    FROM sys.configurations ;
    GO
    ```  
  
#### <a name="to-change-a-server-property-by-using-sp_configure"></a><span data-ttu-id="ee3a0-151">Pour modifier une propriété de serveur à l'aide de sp_configure</span><span class="sxs-lookup"><span data-stu-id="ee3a0-151">To change a server property by using sp_configure</span></span>  
  
1.  <span data-ttu-id="ee3a0-152">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee3a0-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ee3a0-153">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ee3a0-154">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ee3a0-155">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour modifier une propriété de serveur.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-155">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to change a server property.</span></span> <span data-ttu-id="ee3a0-156">L'exemple modifie la valeur de l'option `fill factor` sur `100`.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-156">The example changes the value of the `fill factor` option to `100`.</span></span> <span data-ttu-id="ee3a0-157">Le serveur doit être redémarré pour appliquer le changement.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-157">The server must be restarted before the change can take effect.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="ee3a0-158">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ee3a0-158">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="ee3a0-159">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="ee3a0-159">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="ee3a0-160">Certaines propriétés du serveur peuvent être affichées ou modifiées à l'aide du gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-160">Some server properties can be viewed or changed by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="ee3a0-161">Par exemple, vous pouvez afficher la version et l'édition de l'instance de SQL Server, ou modifier l'emplacement où les fichiers des journaux d'erreurs sont stockés.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-161">For example, you can view the version and edition of the instance of SQL Server, or change the location where error log files are stored.</span></span> <span data-ttu-id="ee3a0-162">Vous pouvez aussi afficher ces propriétés en interrogeant les [fonctions et vues de gestion dynamique relatives au serveur](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ee3a0-162">These properties can also be viewed by querying the [Server-Related Dynamic Management Views and Functions](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="ee3a0-163">Pour afficher ou modifier des propriétés de serveur</span><span class="sxs-lookup"><span data-stu-id="ee3a0-163">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="ee3a0-164">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-164">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="ee3a0-165">Dans le **Gestionnaire de configuration SQL Server**, cliquez sur **Services SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-165">In **SQL Server Configuration Manager**, click **SQL Server Services**.</span></span>  
  
3.  <span data-ttu-id="ee3a0-166">Dans le volet d’informations, cliquez avec le bouton droit sur **SQL Server (\<***instancename***>)** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-166">In the details pane, right-click **SQL Server (\<***instancename***>)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ee3a0-167">Dans la boîte de dialogue **Propriétés de SQL Server (\<***instancename***>)** , modifiez les propriétés du serveur sous l’onglet **Service** ou **Avancé**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-167">In the **SQL Server (\<***instancename***>) Properties** dialog box, change the server properties on the **Service** tab or the **Advanced** tab, and then click **OK**.</span></span>  
  
##  <a name="follow-up-after-you-change-server-properties"></a><a name="FollowUp"></a><span data-ttu-id="ee3a0-168">Suivi : après avoir modifié les propriétés du serveur</span><span class="sxs-lookup"><span data-stu-id="ee3a0-168">Follow Up: After you change server properties</span></span>  
 <span data-ttu-id="ee3a0-169">Pour certaines propriétés, le serveur doit être redémarré afin d'appliquer les modification.</span><span class="sxs-lookup"><span data-stu-id="ee3a0-169">For some properties, the server might have to be restarted before the change can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee3a0-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee3a0-170">See Also</span></span>  
 <span data-ttu-id="ee3a0-171">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ee3a0-171">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="ee3a0-172">[Instructions SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ee3a0-172">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 <span data-ttu-id="ee3a0-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ee3a0-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="ee3a0-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ee3a0-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="ee3a0-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ee3a0-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="ee3a0-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ee3a0-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="ee3a0-177">[Configurer WMI pour afficher l’état du serveur dans les outils SQL Server](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ee3a0-177">[Configure WMI to Show Server Status in SQL Server Tools](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span></span>  
 <span data-ttu-id="ee3a0-178">[Gestionnaire de configuration SQL Server](../../relational-databases/sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ee3a0-178">[SQL Server Configuration Manager](../../relational-databases/sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="ee3a0-179">[Fonctions de configuration &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ee3a0-179">[Configuration Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span></span>  
 [<span data-ttu-id="ee3a0-180">Fonctions et vues de gestion dynamique relatives au serveur &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ee3a0-180">Server-Related Dynamic Management Views and Functions &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql)  
