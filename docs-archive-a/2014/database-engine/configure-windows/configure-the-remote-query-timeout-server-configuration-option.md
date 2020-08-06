---
title: Configurer l’option de configuration de serveur remote query timeout | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- time limit for remote queries [SQL Server]
- remote query timeout option
ms.assetid: 888c8448-933b-41e3-8aa1-c206bc0cdb78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 74f82d621d7f0375a6a3ca604abba00f83fc6024
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707863"
---
# <a name="configure-the-remote-query-timeout-server-configuration-option"></a><span data-ttu-id="a7efc-102">Configurer l'option de configuration de serveur remote query timeout</span><span class="sxs-lookup"><span data-stu-id="a7efc-102">Configure the remote query timeout Server Configuration Option</span></span>
  <span data-ttu-id="a7efc-103">Cette rubrique explique comment configurer l'option de configuration de serveur **remote query timeout** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7efc-103">This topic describes how to configure the **remote query timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a7efc-104">L'option **remote query timeout** spécifie la durée, en secondes, d'une opération distante au terme de laquelle le délai d'attente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expire. La valeur par défaut de cette option est 600, qui correspond à une attente de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="a7efc-104">The **remote query timeout** option specifies how long, in seconds, a remote operation can take before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] times out. The default value for this option is 600, which allows a 10-minute wait.</span></span> <span data-ttu-id="a7efc-105">Cette valeur s'applique à une connexion sortante émise par le [!INCLUDE[ssDE](../../includes/ssde-md.md)] comme requête distante.</span><span class="sxs-lookup"><span data-stu-id="a7efc-105">This value applies to an outgoing connection initiated by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] as a remote query.</span></span> <span data-ttu-id="a7efc-106">Elle n'a aucun effet sur les requêtes reçues par le [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7efc-106">This value has no effect on queries received by the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="a7efc-107">Pour désactiver le délai d'attente, affectez-lui la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="a7efc-107">To disable the time-out, set the value to 0.</span></span> <span data-ttu-id="a7efc-108">Une requête attend jusqu’à ce qu’elle se termine.</span><span class="sxs-lookup"><span data-stu-id="a7efc-108">A query will wait until it completes.</span></span>  
  
 <span data-ttu-id="a7efc-109">Pour les requêtes hétérogènes, l’option **remote query timeout** spécifie le nombre de secondes (initialisé dans l’objet commande à l’aide de la propriété d’ensemble de lignes DBPROP_COMMANDTIMEOUT) pendant lesquelles un fournisseur distant peut attendre les résultats avant l’expiration de la requête. Cette valeur est également utilisée pour définir DBPROP_GENERALTIMEOUT si elle est prise en charge par le fournisseur distant.</span><span class="sxs-lookup"><span data-stu-id="a7efc-109">For heterogeneous queries, **remote query timeout** specifies the number of seconds (initialized in the command object using the DBPROP_COMMANDTIMEOUT rowset property) that a remote provider should wait for result sets before the query times out. This value is also used to set DBPROP_GENERALTIMEOUT if supported by the remote provider.</span></span> <span data-ttu-id="a7efc-110">Cela entraînera l'expiration du délai de toutes les autres opérations après le nombre de secondes spécifié.</span><span class="sxs-lookup"><span data-stu-id="a7efc-110">This will cause any other operations to time out after the specified number of seconds.</span></span>  
  
 <span data-ttu-id="a7efc-111">Pour les procédures stockées distantes, l'option **remote query timeout** spécifie le nombre de secondes devant s'écouler après l'envoi d'une instruction distante `EXEC` avant que le délai d'attente ne soit atteint.</span><span class="sxs-lookup"><span data-stu-id="a7efc-111">For remote stored procedures, **remote query timeout** specifies the number of seconds that must elapse after sending a remote `EXEC` statement before the remote stored procedure times out.</span></span>  
  
 <span data-ttu-id="a7efc-112">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="a7efc-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a7efc-113">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a7efc-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a7efc-114">Composants requis</span><span class="sxs-lookup"><span data-stu-id="a7efc-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="a7efc-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a7efc-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a7efc-116">**Pour configurer l'option remote query timeout, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="a7efc-116">**To configure the remote query timeout option, using:**</span></span>  
  
     [<span data-ttu-id="a7efc-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a7efc-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a7efc-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a7efc-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="a7efc-119">**Suivi :**  [Après avoir configuré l’option remote query timeout](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a7efc-119">**Follow Up:**  [After you configure the remote query timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a7efc-120">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a7efc-120">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a7efc-121">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="a7efc-121">Prerequisites</span></span>  
  
-   <span data-ttu-id="a7efc-122">Les connexions au serveur distant doivent être autorisées avant que cette valeur puisse être définie.</span><span class="sxs-lookup"><span data-stu-id="a7efc-122">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a7efc-123">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a7efc-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a7efc-124">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a7efc-124">Permissions</span></span>  
 <span data-ttu-id="a7efc-125">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a7efc-125">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="a7efc-126">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="a7efc-126">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="a7efc-127">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="a7efc-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a7efc-128">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a7efc-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="a7efc-129">Pour configurer l'option Délai d'attente de la requête distante</span><span class="sxs-lookup"><span data-stu-id="a7efc-129">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="a7efc-130">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a7efc-130">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="a7efc-131">Cliquez sur le nœud **Connexions** .</span><span class="sxs-lookup"><span data-stu-id="a7efc-131">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="a7efc-132">Sous **Connexions au serveur distant**, dans la zone **Délai d'attente de la requête distante** , tapez ou sélectionnez une valeur comprise entre 0 et 2 147 483 647 pour définir le nombre maximal de secondes de l'attente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant expiration.</span><span class="sxs-lookup"><span data-stu-id="a7efc-132">Under **Remote server connections**, in the **Remote query timeout** box, type or select a value from 0 through 2,147,483,647 to set the maximum number seconds for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to wait before timing out.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a7efc-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a7efc-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="a7efc-134">Pour configurer l'option Délai d'attente de la requête distante</span><span class="sxs-lookup"><span data-stu-id="a7efc-134">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="a7efc-135">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7efc-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a7efc-136">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a7efc-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a7efc-137">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a7efc-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a7efc-138">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `remote query timeout` la valeur `0` afin de désactiver le délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="a7efc-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote query timeout` option to `0` to disable the time-out.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote query timeout', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="a7efc-139">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a7efc-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-query-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="a7efc-140">Suivi : Après avoir configuré l’option remote query timeout</span><span class="sxs-lookup"><span data-stu-id="a7efc-140">Follow Up: After you configure the remote query timeout option</span></span>  
 <span data-ttu-id="a7efc-141">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="a7efc-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7efc-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7efc-142">See Also</span></span>  
 <span data-ttu-id="a7efc-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a7efc-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="a7efc-144">[Propriétés et comportements de l’ensemble de lignes](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="a7efc-144">[Rowset Properties and Behaviors](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 <span data-ttu-id="a7efc-145">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a7efc-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="a7efc-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a7efc-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
