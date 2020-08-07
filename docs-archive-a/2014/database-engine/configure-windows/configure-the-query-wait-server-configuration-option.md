---
title: Configurer l’option de configuration de serveur query wait | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], timing out
- time [SQL Server], query wait time
- query wait option [SQL Server]
ms.assetid: 0fc4aa01-65a3-4a33-9ef4-caca41add238
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 638afff2aa05a9fc4e61bc71e8610dba1dda8cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611289"
---
# <a name="configure-the-query-wait-server-configuration-option"></a><span data-ttu-id="2004a-102">Configurer l'option de configuration de serveur query wait</span><span class="sxs-lookup"><span data-stu-id="2004a-102">Configure the query wait Server Configuration Option</span></span>
  <span data-ttu-id="2004a-103">Cette rubrique explique comment configurer l'option de configuration de serveur **query wait** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2004a-103">This topic describes how to configure the **query wait** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2004a-104">Les requêtes utilisant beaucoup de mémoire (par exemple les requêtes incluant des opérations de tri et de hachage) sont mises en attente si la quantité de mémoire est insuffisante pour leur exécution.</span><span class="sxs-lookup"><span data-stu-id="2004a-104">Memory-intensive queries (such as those involving sorting and hashing) are queued when there is not enough memory available to run the query.</span></span> <span data-ttu-id="2004a-105">L’option **query wait** spécifie le délai (exprimé en secondes, de 0 à 2147483647) pendant lequel une requête peut attendre des ressources avant d’expirer. La valeur par défaut de cette option est -1.</span><span class="sxs-lookup"><span data-stu-id="2004a-105">The **query wait** option specifies the time, in seconds (from 0 through 2147483647), that a query waits for resources before it times out. The default value for this option is -1.</span></span> <span data-ttu-id="2004a-106">Cela signifie que le délai d'attente est calculé comme étant 25 fois le coût estimé de la requête.</span><span class="sxs-lookup"><span data-stu-id="2004a-106">This means the time-out is calculated as 25 times the estimated query cost.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2004a-107">Une transaction contenant la requête en attente peut contenir des verrous en attendant une quantité supplémentaire de mémoire.</span><span class="sxs-lookup"><span data-stu-id="2004a-107">A transaction that contains the waiting query might hold locks while the query waits for memory.</span></span> <span data-ttu-id="2004a-108">Dans de rares situations, il est possible qu'un blocage indétectable se produise.</span><span class="sxs-lookup"><span data-stu-id="2004a-108">In rare situations, it is possible for an undetectable deadlock to occur.</span></span> <span data-ttu-id="2004a-109">En réduisant la durée d’attente de la requête, vous réduisez également la probabilité de déclenchement de ces verrous.</span><span class="sxs-lookup"><span data-stu-id="2004a-109">Decreasing the query wait time lowers the probability of such deadlocks.</span></span> <span data-ttu-id="2004a-110">À la fin de celle-ci, une requête en attente est arrêtée et les verrous de la transaction sont libérés.</span><span class="sxs-lookup"><span data-stu-id="2004a-110">Eventually, a waiting query will be terminated and the transaction locks released.</span></span> <span data-ttu-id="2004a-111">Cependant, l'augmentation de la durée d'attente maximale risque d'augmenter la durée nécessaire pour l'achèvement de la requête.</span><span class="sxs-lookup"><span data-stu-id="2004a-111">However, increasing the maximum wait time may increase the amount of time for the query to be terminated.</span></span> <span data-ttu-id="2004a-112">Il est déconseillé de modifier cette option.</span><span class="sxs-lookup"><span data-stu-id="2004a-112">Changes to this option are not recommended.</span></span>  
  
 <span data-ttu-id="2004a-113">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2004a-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2004a-114">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2004a-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2004a-115">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2004a-115">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="2004a-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2004a-116">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2004a-117">**Pour configurer l'option query wait, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="2004a-117">**To configure the query wait option, using:**</span></span>  
  
     [<span data-ttu-id="2004a-118">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2004a-118">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2004a-119">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2004a-119">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="2004a-120">**Suivi :**  [Après avoir configuré l’option query wait](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="2004a-120">**Follow Up:**  [After you configure the query wait option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2004a-121">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2004a-121">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2004a-122">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2004a-122">Recommendations</span></span>  
  
-   <span data-ttu-id="2004a-123">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2004a-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2004a-124">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2004a-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2004a-125">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2004a-125">Permissions</span></span>  
 <span data-ttu-id="2004a-126">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2004a-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="2004a-127">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="2004a-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="2004a-128">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="2004a-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2004a-129">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2004a-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="2004a-130">Pour configurer l'option query wait</span><span class="sxs-lookup"><span data-stu-id="2004a-130">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="2004a-131">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2004a-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2004a-132">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="2004a-132">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="2004a-133">Sous **Parallélisme**, tapez la valeur de votre choix pour l'option **query wait** .</span><span class="sxs-lookup"><span data-stu-id="2004a-133">Under **Parallelism**, type the desired value for the **query wait** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2004a-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2004a-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="2004a-135">Pour configurer l'option query wait</span><span class="sxs-lookup"><span data-stu-id="2004a-135">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="2004a-136">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2004a-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2004a-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2004a-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2004a-138">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2004a-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2004a-139">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `query wait` la valeur `7500` secondes.</span><span class="sxs-lookup"><span data-stu-id="2004a-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query wait` option to `7500` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query wait', 7500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="2004a-140">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2004a-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-wait-option"></a><a name="FollowUp"></a> <span data-ttu-id="2004a-141">Suivi : Après avoir configuré l’option query wait</span><span class="sxs-lookup"><span data-stu-id="2004a-141">Follow Up: After you configure the query wait option</span></span>  
 <span data-ttu-id="2004a-142">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="2004a-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2004a-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2004a-143">See Also</span></span>  
 <span data-ttu-id="2004a-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2004a-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="2004a-145">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2004a-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="2004a-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2004a-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
