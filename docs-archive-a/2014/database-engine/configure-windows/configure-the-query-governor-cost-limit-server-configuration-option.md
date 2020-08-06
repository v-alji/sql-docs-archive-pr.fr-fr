---
title: Configurer l’option de configuration de serveur query governor cost limit | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], time to execute
- query governor cost limit option [SQL Server]
- time [SQL Server], query run time
ms.assetid: e7b8f084-1052-4133-959b-cebf4add790f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4f8420bf8ed8c08d3626c797968c041a40f7c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601688"
---
# <a name="configure-the-query-governor-cost-limit-server-configuration-option"></a><span data-ttu-id="2822f-102">Configurer l'option de configuration de serveur query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="2822f-102">Configure the query governor cost limit Server Configuration Option</span></span>
  <span data-ttu-id="2822f-103">Cette rubrique explique comment configurer l' `query governor cost limit` option de configuration de serveur dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2822f-103">This topic describes how to configure the `query governor cost limit` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2822f-104">L’option query governor cost limit spécifie une limite supérieure de durée d’exécution d’une requête.</span><span class="sxs-lookup"><span data-stu-id="2822f-104">The query governor cost limit option specifies an upper limit on the time period in which a query can run.</span></span> <span data-ttu-id="2822f-105">Le coût d'une requête correspond à la durée (en secondes) estimée nécessaire à l'exécution complète d'une requête dans une configuration matérielle donnée.</span><span class="sxs-lookup"><span data-stu-id="2822f-105">Query cost refers to the estimated elapsed time, in seconds, that is required to complete a query on a specific hardware configuration.</span></span> <span data-ttu-id="2822f-106">La valeur par défaut de cette option est 0, laquelle désactive l'Administrateur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="2822f-106">The default value for this option is 0, which sets the query governor to off.</span></span> <span data-ttu-id="2822f-107">Cela permet l'exécution de toutes les requêtes sans limitation de temps.</span><span class="sxs-lookup"><span data-stu-id="2822f-107">This allows all queries to run without any time limitation.</span></span> <span data-ttu-id="2822f-108">Si vous spécifiez une valeur positive et différente de zéro, l'Administrateur de requêtes n'autorise pas l'exécution de requêtes dont le coût estimé excède cette valeur.</span><span class="sxs-lookup"><span data-stu-id="2822f-108">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost that exceeds that value.</span></span>  
  
 <span data-ttu-id="2822f-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2822f-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2822f-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2822f-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2822f-111">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2822f-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="2822f-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2822f-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2822f-113">**Pour configurer l'option query governor cost limit, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="2822f-113">**To configure the query governor cost limit option, using:**</span></span>  
  
     [<span data-ttu-id="2822f-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2822f-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2822f-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2822f-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="2822f-116">**Suivi :**  [Après avoir configuré l’option query governor cost limit](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="2822f-116">**Follow Up:**  [After you configure the query governor cost limit option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2822f-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2822f-117">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2822f-118">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2822f-118">Recommendations</span></span>  
  
-   <span data-ttu-id="2822f-119">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2822f-119">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="2822f-120">Pour modifier la valeur de l’option Limite de coût de l’Administrateur de requêtes pour chaque connexion, utilisez l’instruction [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2822f-120">To change the value query governor cost limit on a per-connection basis, use the [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2822f-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2822f-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2822f-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2822f-122">Permissions</span></span>  
 <span data-ttu-id="2822f-123">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2822f-123">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="2822f-124">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="2822f-124">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="2822f-125">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="2822f-125">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2822f-126">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2822f-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="2822f-127">Pour configurer l'option query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="2822f-127">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="2822f-128">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2822f-128">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2822f-129">Cliquez sur la page **Connexions** .</span><span class="sxs-lookup"><span data-stu-id="2822f-129">Click the **Connections** page.</span></span>  
  
3.  <span data-ttu-id="2822f-130">Cochez ou décochez la case **Utiliser l’Administrateur de requêtes pour empêcher les requêtes longues** .</span><span class="sxs-lookup"><span data-stu-id="2822f-130">Select or clear the **Use query governor to prevent long-running queries** check box.</span></span>  
  
     <span data-ttu-id="2822f-131">Si vous activez cette case à cocher, spécifiez dans la zone située en-dessous une valeur positive, que l'Administrateur de requêtes utilise pour interdire l'exécution de toutes les requêtes dont la durée d'exécution dépasse cette valeur.</span><span class="sxs-lookup"><span data-stu-id="2822f-131">If you select this check box, in the box below, enter a positive value, which the query governor uses to disallow execution of any query with a running length exceeding that value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2822f-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2822f-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="2822f-133">Pour configurer l'option query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="2822f-133">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="2822f-134">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2822f-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2822f-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2822f-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2822f-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2822f-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2822f-137">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `query governor cost limit` la valeur `120` secondes.</span><span class="sxs-lookup"><span data-stu-id="2822f-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query governor cost limit` option to `120` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query governor cost limit', 120 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="2822f-138">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2822f-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-governor-cost-limit-option"></a><a name="FollowUp"></a> <span data-ttu-id="2822f-139">Suivi : Après avoir configuré l’option query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="2822f-139">Follow Up: After you configure the query governor cost limit option</span></span>  
 <span data-ttu-id="2822f-140">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="2822f-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2822f-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2822f-141">See Also</span></span>  
 <span data-ttu-id="2822f-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2822f-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="2822f-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2822f-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span></span>  
 <span data-ttu-id="2822f-144">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2822f-144">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="2822f-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2822f-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
