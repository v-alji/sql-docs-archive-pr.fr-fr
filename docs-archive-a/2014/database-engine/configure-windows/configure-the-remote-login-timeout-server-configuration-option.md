---
title: Configurer l’option de configuration de serveur remote login timeout | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote login timeout option
ms.assetid: 077adebe-0e3f-42a5-a75e-5e6d04847e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58b3405f9b0e51bd43edcaa31e84c8ebbcc48547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601680"
---
# <a name="configure-the-remote-login-timeout-server-configuration-option"></a><span data-ttu-id="c474d-102">Configurer l'option de configuration de serveur remote login timeout</span><span class="sxs-lookup"><span data-stu-id="c474d-102">Configure the remote login timeout Server Configuration Option</span></span>
  <span data-ttu-id="c474d-103">Cette rubrique explique comment configurer l'option de configuration de serveur **remote login timeout** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c474d-103">This topic describes how to configure the **remote login timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c474d-104">L'option **Délai d'attente de la connexion distante** spécifie le nombre de secondes d'attente avant le renvoi d'une tentative de connexion à un serveur distant qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="c474d-104">The **remote login timeout** option specifies the number of seconds to wait before returning from a failed attempt to log in to a remote server.</span></span> <span data-ttu-id="c474d-105">Par exemple, si vous tentez de vous connecter à un serveur distant et que ce serveur est arrêté, l'option **remote login timeout** vous assure de ne pas attendre indéfiniment que votre ordinateur cesse ses tentatives de connexion.</span><span class="sxs-lookup"><span data-stu-id="c474d-105">For example, if you are trying to log in to a remote server and that server is down, **remote login timeout** helps make sure that you do not have to wait indefinitely before your computer stops trying to log in.</span></span> <span data-ttu-id="c474d-106">La valeur par défaut de cette option est de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="c474d-106">The default value for this option is 10 seconds.</span></span> <span data-ttu-id="c474d-107">Une valeur égale à 0 entraîne une attente infinie.</span><span class="sxs-lookup"><span data-stu-id="c474d-107">A value of 0 allows for an infinite wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c474d-108">La valeur par défaut de cette option est de 20 secondes dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c474d-108">The default value for this option is 20 seconds in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="c474d-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c474d-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c474d-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c474d-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c474d-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c474d-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c474d-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c474d-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c474d-113">**Pour configurer l'option remote login timeout, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="c474d-113">**To configure the remote login timeout option, using:**</span></span>  
  
     [<span data-ttu-id="c474d-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c474d-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c474d-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c474d-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="c474d-116">**Suivi :**  [Après avoir configuré l’option remote login timeout](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c474d-116">**Follow Up:**  [After you configure the remote login timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c474d-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c474d-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c474d-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c474d-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c474d-119">L'option **remote login timeout** concerne les connexions à des fournisseurs OLE DB établies pour des requêtes hétérogènes.</span><span class="sxs-lookup"><span data-stu-id="c474d-119">The **remote login timeout** option affects connections to OLE DB providers made for heterogeneous queries.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c474d-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c474d-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c474d-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c474d-121">Permissions</span></span>  
 <span data-ttu-id="c474d-122">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c474d-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="c474d-123">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="c474d-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="c474d-124">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="c474d-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c474d-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c474d-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="c474d-126">Pour configurer l'option remote login timeout</span><span class="sxs-lookup"><span data-stu-id="c474d-126">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="c474d-127">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c474d-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c474d-128">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="c474d-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="c474d-129">Sous **Réseau**, sélectionnez une valeur pour la zone **Remote Login Timeout** .</span><span class="sxs-lookup"><span data-stu-id="c474d-129">Under **Network**, select a value for the **Remote Login Timeout** box.</span></span>  
  
     <span data-ttu-id="c474d-130">Utilisez l'option **remote login timeout** pour spécifier le nombre de secondes d'attente avant le renvoi d'une tentative de connexion qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="c474d-130">Use the **remote login timeout** option to specify the number of seconds to wait before returning from a failed remote login attempt.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c474d-131">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c474d-131">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="c474d-132">Pour configurer l'option remote login timeout</span><span class="sxs-lookup"><span data-stu-id="c474d-132">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="c474d-133">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c474d-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c474d-134">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c474d-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c474d-135">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c474d-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c474d-136">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `remote login timeout` la valeur `35` secondes.</span><span class="sxs-lookup"><span data-stu-id="c474d-136">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote login timeout` option to `35` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote login timeout', 35 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="c474d-137">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c474d-137">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-login-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="c474d-138">Suivi : Après avoir configuré l’option remote login timeout</span><span class="sxs-lookup"><span data-stu-id="c474d-138">Follow Up: After you configure the remote login timeout option</span></span>  
 <span data-ttu-id="c474d-139">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="c474d-139">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c474d-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c474d-140">See Also</span></span>  
 <span data-ttu-id="c474d-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c474d-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="c474d-142">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c474d-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="c474d-143">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c474d-143">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
