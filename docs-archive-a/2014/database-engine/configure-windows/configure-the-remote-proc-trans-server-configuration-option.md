---
title: Configurer l’option de configuration de serveur remote proc trans | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote proc trans option
- distributed transactions [SQL Server], enforcing
ms.assetid: cfbc6158-ab96-44b4-87eb-ea278c1b0c6b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54fcaafa51eef33acb1ae8d1e2f36022840b76a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603618"
---
# <a name="configure-the-remote-proc-trans-server-configuration-option"></a><span data-ttu-id="c395d-102">Configurer l'option de configuration de serveur remote proc trans</span><span class="sxs-lookup"><span data-stu-id="c395d-102">Configure the remote proc trans Server Configuration Option</span></span>
  <span data-ttu-id="c395d-103">Cette rubrique explique comment configurer l'option de configuration de serveur **remote proc trans** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c395d-103">This topic describes how to configure the **remote proc trans** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c395d-104">L’option **remote proc trans** contribue à protéger les actions d’une procédure de serveur à serveur via une transaction MS DTC ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator).</span><span class="sxs-lookup"><span data-stu-id="c395d-104">The **remote proc trans** option helps protect the actions of a server-to-server procedure through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) transaction.</span></span>  
  
 <span data-ttu-id="c395d-105">Attribuez la valeur 1 à l’option **remote proc trans** pour obtenir une transaction distribuée coordonnée par MS DTC qui protège les propriétés ACID (Atomicité, Cohérence, Isolation et Durabilité) des transactions.</span><span class="sxs-lookup"><span data-stu-id="c395d-105">Set the value of **remote proc trans** to 1 to provide an MS DTC-coordinated distributed transaction that protects the ACID (atomic, consistent, isolated, and durable) properties of transactions.</span></span> <span data-ttu-id="c395d-106">Les sessions qui commencent après l'attribution de la valeur 1 à cette option héritent par défaut des options de configuration.</span><span class="sxs-lookup"><span data-stu-id="c395d-106">Sessions begun after setting this option to 1 inherit the configuration setting as their default.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  
 <span data-ttu-id="c395d-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c395d-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c395d-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c395d-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c395d-109">Composants requis</span><span class="sxs-lookup"><span data-stu-id="c395d-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="c395d-110">Recommandations</span><span class="sxs-lookup"><span data-stu-id="c395d-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c395d-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c395d-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c395d-112">**Pour configurer l'option remote proc trans, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="c395d-112">**To configure the remote proc trans option, using:**</span></span>  
  
     [<span data-ttu-id="c395d-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c395d-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c395d-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c395d-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="c395d-115">**Suivi :**  [Après avoir configuré l’option remote proc trans](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c395d-115">**Follow Up:**  [After you configure the remote proc trans option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c395d-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c395d-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c395d-117">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c395d-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="c395d-118">Les connexions au serveur distant doivent être autorisées avant que cette valeur puisse être définie.</span><span class="sxs-lookup"><span data-stu-id="c395d-118">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c395d-119">Recommandations</span><span class="sxs-lookup"><span data-stu-id="c395d-119">Recommendations</span></span>  
  
-   <span data-ttu-id="c395d-120">Cette option garantit la compatibilité avec les versions antérieures de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour les applications qui utilisent des procédures stockées distantes.</span><span class="sxs-lookup"><span data-stu-id="c395d-120">This option is provided for compatibility with earlier versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for applications that use remote stored procedures.</span></span> <span data-ttu-id="c395d-121">Au lieu d’émettre des appels de procédures stockées distantes, utilisez des requêtes distribuées faisant référence à des serveurs liés, qui sont définis à l’aide de [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c395d-121">Instead of issuing remote stored procedure calls, use distributed queries that reference linked servers, which are defined by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c395d-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c395d-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c395d-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c395d-123">Permissions</span></span>  
 <span data-ttu-id="c395d-124">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c395d-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="c395d-125">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="c395d-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="c395d-126">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="c395d-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c395d-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c395d-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="c395d-128">Pour configurer l'option remote proc trans</span><span class="sxs-lookup"><span data-stu-id="c395d-128">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="c395d-129">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c395d-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c395d-130">Cliquez sur le nœud **Connexions** .</span><span class="sxs-lookup"><span data-stu-id="c395d-130">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="c395d-131">Sous **Connexions au serveur distant**, activez la case à cocher **Nécessite des transactions distribuées pour la communication de serveur à serveur** .</span><span class="sxs-lookup"><span data-stu-id="c395d-131">Under **Remote server connections**, select the **Require Distributed Transactions for server to server communication** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c395d-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c395d-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="c395d-133">Pour configurer l'option remote proc trans</span><span class="sxs-lookup"><span data-stu-id="c395d-133">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="c395d-134">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c395d-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c395d-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c395d-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c395d-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c395d-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c395d-137">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `remote proc trans` la valeur `1`.</span><span class="sxs-lookup"><span data-stu-id="c395d-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote proc trans` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote proc trans', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="c395d-138">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c395d-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-proc-trans-option"></a><a name="FollowUp"></a> <span data-ttu-id="c395d-139">Suivi : Après avoir configuré l’option remote proc trans</span><span class="sxs-lookup"><span data-stu-id="c395d-139">Follow Up: After you configure the remote proc trans option</span></span>  
 <span data-ttu-id="c395d-140">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="c395d-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c395d-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c395d-141">See Also</span></span>  
 <span data-ttu-id="c395d-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c395d-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="c395d-143">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c395d-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="c395d-144">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c395d-144">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
