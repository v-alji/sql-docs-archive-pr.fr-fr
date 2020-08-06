---
title: Configurer l’option de configuration de serveur locks | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- locks option [SQL Server]
ms.assetid: b0cf0f86-7652-4574-a9fb-908e10d03973
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e45f4cc539be585966eb0beb30d4938b504c3419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708608"
---
# <a name="configure-the-locks-server-configuration-option"></a><span data-ttu-id="21d6a-102">Configurer l'option de configuration de serveur locks</span><span class="sxs-lookup"><span data-stu-id="21d6a-102">Configure the locks Server Configuration Option</span></span>
  <span data-ttu-id="21d6a-103">Cette rubrique explique comment configurer l'option de configuration de serveur **locks** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21d6a-103">This topic describes how to configure the **locks** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="21d6a-104">L'option **locks** définit le nombre maximum de verrous disponibles, limitant ainsi la quantité de mémoire utilisée pour eux par le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21d6a-104">The **locks** option sets the maximum number of available locks, thereby limiting the amount of memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for them.</span></span> <span data-ttu-id="21d6a-105">La valeur par défaut est 0 ; elle permet au [!INCLUDE[ssDE](../../includes/ssde-md.md)] d'allouer et de libérer des structures de verrous de manière dynamique en fonction des modifications de la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="21d6a-105">The default setting is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically, based on changing system requirements.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="21d6a-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="21d6a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="21d6a-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="21d6a-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="21d6a-108">Recommandations</span><span class="sxs-lookup"><span data-stu-id="21d6a-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="21d6a-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="21d6a-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="21d6a-110">**Pour définir l'option locks, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="21d6a-110">**To configure the locks option, using:**</span></span>  
  
     [<span data-ttu-id="21d6a-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="21d6a-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="21d6a-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="21d6a-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="21d6a-113">**Suivi :**  [Après avoir configuré l’option locks](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="21d6a-113">**Follow Up:**  [After you configure the locks option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="21d6a-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="21d6a-114">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="21d6a-115">Recommandations</span><span class="sxs-lookup"><span data-stu-id="21d6a-115">Recommendations</span></span>  
  
-   <span data-ttu-id="21d6a-116">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21d6a-116">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="21d6a-117">Lorsque le serveur est démarré alors que la valeur 0 est attribuée à l'option **Verrous** , le gestionnaire de verrous acquiert suffisamment de mémoire auprès du [!INCLUDE[ssDE](../../includes/ssde-md.md)] pour un pool initial de 2 500 structures de verrous.</span><span class="sxs-lookup"><span data-stu-id="21d6a-117">When the server is started with **locks** set to 0, the lock manager acquires sufficient memory from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for an initial pool of 2,500 lock structures.</span></span> <span data-ttu-id="21d6a-118">Lorsque ce pool est épuisé, le gestionnaire de verrous redemande de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="21d6a-118">As the lock pool is exhausted, additional memory is acquired for the pool.</span></span>  
  
     <span data-ttu-id="21d6a-119">En règle générale, si une quantité de mémoire supérieure à celle du pool de mémoires du [!INCLUDE[ssDE](../../includes/ssde-md.md)] est requise pour le pool de verrous, et s’il reste de la mémoire sur l’ordinateur (c’est-à-dire si le seuil de l’option **Mémoire maximum du serveur** n’a pas été atteint), le [!INCLUDE[ssDE](../../includes/ssde-md.md)] alloue dynamiquement de la mémoire afin de satisfaire la demande de verrous.</span><span class="sxs-lookup"><span data-stu-id="21d6a-119">Generally, if more memory is required for the lock pool than is available in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool, and more computer memory is available (the **max server memory** threshold has not been reached), the [!INCLUDE[ssDE](../../includes/ssde-md.md)] allocates memory dynamically to satisfy the request for locks.</span></span> <span data-ttu-id="21d6a-120">Cependant, si l'allocation de mémoire entraîne une pagination au niveau du système d'exploitation (par exemple, si une autre application est exécutée sur le même ordinateur en tant qu'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et utilise cette mémoire), aucun espace supplémentaire n'est alloué pour les verrous.</span><span class="sxs-lookup"><span data-stu-id="21d6a-120">However, if allocating that memory would cause paging at the operating system level (for example, if another application is running on the same computer as an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and using that memory), more lock space is not allocated.</span></span> <span data-ttu-id="21d6a-121">Le pool de verrous dynamiques n’acquiert pas plus de 60 pour cent de la mémoire allouée au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21d6a-121">The dynamic lock pool does not acquire more than 60 percent of the memory allocated to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="21d6a-122">Une fois que le pool de verrous a atteint 60 pour cent de la mémoire acquise par une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)], ou s’il ne reste plus de mémoire disponible sur l’ordinateur, les autres demandes de verrous génèrent une erreur.</span><span class="sxs-lookup"><span data-stu-id="21d6a-122">After the lock pool has reached 60 percent of the memory acquired by an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or no more memory is available on the computer, further requests for locks generate an error.</span></span>  
  
     <span data-ttu-id="21d6a-123">La configuration recommandée est l'autorisation de l'utilisation dynamique des verrous par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21d6a-123">Allowing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use locks dynamically is the recommended configuration.</span></span> <span data-ttu-id="21d6a-124">Cependant, vous pouvez définir l'option **locks** et empêcher [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'allouer des ressources de verrous de façon dynamique.</span><span class="sxs-lookup"><span data-stu-id="21d6a-124">However, you can set **locks** and override the ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to allocate lock resources dynamically.</span></span> <span data-ttu-id="21d6a-125">Quand l’option **locks** a une valeur différente de 0, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] ne peut pas allouer plus de verrous que ce **nombre**.</span><span class="sxs-lookup"><span data-stu-id="21d6a-125">When **locks** is set to a value other than 0, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] cannot allocate more locks than the value specified in **locks**.</span></span> <span data-ttu-id="21d6a-126">Augmentez cette valeur si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affiche un message vous informant que vous avez dépassé le nombre de verrous disponibles.</span><span class="sxs-lookup"><span data-stu-id="21d6a-126">Increase this value if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a message that you have exceeded the number of available locks.</span></span> <span data-ttu-id="21d6a-127">Puisque chaque verrou consomme de la mémoire (96 octets par verrou), il est possible que l’augmentation de cette valeur vous oblige à augmenter la mémoire destinée au serveur.</span><span class="sxs-lookup"><span data-stu-id="21d6a-127">Because each lock consumes memory (96 bytes per lock), increasing this value can require increasing the amount of memory dedicated to the server.</span></span>  
  
-   <span data-ttu-id="21d6a-128">L'option **locks** influence également le moment où a lieu l'escalade de verrous.</span><span class="sxs-lookup"><span data-stu-id="21d6a-128">The **locks** option also affects when lock escalation occurs.</span></span> <span data-ttu-id="21d6a-129">Quand l’option **locks** a la valeur 0, l’escalade de verrous se produit quand la mémoire utilisée par les structures de verrous actuelles atteint 40 pour cent du pool de mémoire du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21d6a-129">When **locks** is set to 0, lock escalation occurs when the memory used by the current lock structures reaches 40 percent of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool.</span></span> <span data-ttu-id="21d6a-130">Lorsque l'option **locks** a une valeur différente de 0, l'escalade de verrous intervient quand le nombre de verrous atteint 40 pour cent de la valeur spécifiée pour **Verrous**.</span><span class="sxs-lookup"><span data-stu-id="21d6a-130">When **locks** is not set to 0, lock escalation occurs when the number of locks reaches 40 percent of the value specified for **locks**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="21d6a-131">Sécurité</span><span class="sxs-lookup"><span data-stu-id="21d6a-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="21d6a-132">Autorisations</span><span class="sxs-lookup"><span data-stu-id="21d6a-132">Permissions</span></span>  
 <span data-ttu-id="21d6a-133">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="21d6a-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="21d6a-134">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="21d6a-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="21d6a-135">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="21d6a-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="21d6a-136">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="21d6a-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="21d6a-137">Pour définir l'option locks</span><span class="sxs-lookup"><span data-stu-id="21d6a-137">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="21d6a-138">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="21d6a-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="21d6a-139">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="21d6a-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="21d6a-140">Sous **Parallelism**, entrez la valeur appropriée de l'option **locks** .</span><span class="sxs-lookup"><span data-stu-id="21d6a-140">Under **Parallelism**, type the desired value for the **locks** option.</span></span>  
  
     <span data-ttu-id="21d6a-141">Utilisez l'option **locks** pour définir le nombre maximal de verrous disponibles et limiter ainsi la quantité de mémoire qu'utilise [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec les verrous.</span><span class="sxs-lookup"><span data-stu-id="21d6a-141">Use the **locks** option to set the maximum number of available locks, thereby limiting the amount of memory [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses for them.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="21d6a-142">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="21d6a-142">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="21d6a-143">Pour définir l'option locks</span><span class="sxs-lookup"><span data-stu-id="21d6a-143">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="21d6a-144">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21d6a-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="21d6a-145">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="21d6a-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="21d6a-146">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="21d6a-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="21d6a-147">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `locks` de définition du nombre de verrous disponibles pour tous les utilisateurs la valeur `20000`.</span><span class="sxs-lookup"><span data-stu-id="21d6a-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `locks` option to set the number of locks available for all users to `20000`.</span></span>  
  
```sql  
Use AdventureWorks2012 ;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'locks', 20000;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="21d6a-148">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="21d6a-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-locks-option"></a><a name="FollowUp"></a> <span data-ttu-id="21d6a-149">Suivi : Après avoir configuré l’option locks</span><span class="sxs-lookup"><span data-stu-id="21d6a-149">Follow Up: After you configure the locks option</span></span>  
 <span data-ttu-id="21d6a-150">Le serveur doit être redémarré pour que le paramètre puisse être effet.</span><span class="sxs-lookup"><span data-stu-id="21d6a-150">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d6a-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21d6a-151">See Also</span></span>  
 <span data-ttu-id="21d6a-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="21d6a-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="21d6a-153">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="21d6a-153">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="21d6a-154">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="21d6a-154">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
