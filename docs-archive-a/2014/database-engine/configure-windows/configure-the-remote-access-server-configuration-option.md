---
title: Configurer l’option de configuration du serveur remote access | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], stored procedure execution
ms.assetid: f5de748d-1c55-4714-9661-38fe62e5095f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eef18ec48ede59544b13545e49dc105909cfac16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601683"
---
# <a name="configure-the-remote-access-server-configuration-option"></a><span data-ttu-id="b51de-102">Configurer l'option de configuration du serveur remote access</span><span class="sxs-lookup"><span data-stu-id="b51de-102">Configure the remote access Server Configuration Option</span></span>
  <span data-ttu-id="b51de-103">Cette rubrique explique comment configurer l'option de configuration de serveur **remote access** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b51de-103">This topic describes how to configure the **remote access** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b51de-104">L'option **remote access** contrôle l'exécution des procédures stockées depuis les serveurs locaux ou distants sur lesquels des instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="b51de-104">The **remote access** option controls the execution of stored procedures from local or remote servers on which instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are running.</span></span> <span data-ttu-id="b51de-105">La valeur par défaut de cette option est 1.</span><span class="sxs-lookup"><span data-stu-id="b51de-105">This default value for this option is 1.</span></span> <span data-ttu-id="b51de-106">Cette valeur autorise l'exécution des procédures stockées locales depuis des serveurs distants, ou des procédures stockées distantes depuis le serveur local.</span><span class="sxs-lookup"><span data-stu-id="b51de-106">This grants permission to run local stored procedures from remote servers or remote stored procedures from the local server.</span></span> <span data-ttu-id="b51de-107">Pour empêcher l'exécution des procédures stockées locales depuis un serveur distant ou des procédures stockées distantes depuis le serveur local, attribuez la valeur 0 à cette option.</span><span class="sxs-lookup"><span data-stu-id="b51de-107">To prevent local stored procedures from being run from a remote server or remote stored procedures from being run on the local server, set the option to 0.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="b51de-108">Utilisez de préférence [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b51de-108">Use [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) instead.</span></span>  
  
 <span data-ttu-id="b51de-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b51de-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b51de-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b51de-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b51de-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b51de-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b51de-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b51de-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b51de-113">**Pour configurer l'option remote access, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b51de-113">**To configure the remote access option, using:**</span></span>  
  
     [<span data-ttu-id="b51de-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b51de-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b51de-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b51de-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="b51de-116">**Suivi :**  [Après avoir configuré l’option remote access](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="b51de-116">**Follow Up:**  [After you configure the remote access option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b51de-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b51de-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b51de-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b51de-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b51de-119">L’option **remote access** ne s’applique qu’aux serveurs ajoutés au moyen de [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql)et n’est incluse que pour des raisons de compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="b51de-119">The **remote access** option only applies to servers that are added by using [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), and is included for backward compatibility.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b51de-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b51de-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b51de-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b51de-121">Permissions</span></span>  
 <span data-ttu-id="b51de-122">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b51de-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="b51de-123">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="b51de-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="b51de-124">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="b51de-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b51de-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b51de-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="b51de-126">Pour configurer l'option remote access</span><span class="sxs-lookup"><span data-stu-id="b51de-126">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="b51de-127">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b51de-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b51de-128">Cliquez sur le nœud **Connexions** .</span><span class="sxs-lookup"><span data-stu-id="b51de-128">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="b51de-129">Sous **Connexions au serveur distant**, activez ou désactivez la case à cocher **Autoriser les accès distants à ce serveur** .</span><span class="sxs-lookup"><span data-stu-id="b51de-129">Under **Remote server connections**, select or clear the **Allow remote connections to this server** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b51de-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b51de-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="b51de-131">Pour configurer l'option remote access</span><span class="sxs-lookup"><span data-stu-id="b51de-131">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="b51de-132">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b51de-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b51de-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b51de-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b51de-134">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b51de-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b51de-135">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `remote access` la valeur `0`.</span><span class="sxs-lookup"><span data-stu-id="b51de-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote access` option to `0`.</span></span>  
  
```sql  
EXEC sp_configure 'remote access', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="b51de-136">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b51de-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-access-option"></a><a name="FollowUp"></a> <span data-ttu-id="b51de-137">Suivi : Après avoir configuré l’option remote access</span><span class="sxs-lookup"><span data-stu-id="b51de-137">Follow Up: After you configure the remote access option</span></span>  
 <span data-ttu-id="b51de-138">SQL Server doit être redémarré pour que ce paramètre prenne effet.</span><span class="sxs-lookup"><span data-stu-id="b51de-138">This setting does not take effect until you restart SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51de-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b51de-139">See Also</span></span>  
 <span data-ttu-id="b51de-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b51de-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="b51de-141">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b51de-141">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="b51de-142">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b51de-142">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
