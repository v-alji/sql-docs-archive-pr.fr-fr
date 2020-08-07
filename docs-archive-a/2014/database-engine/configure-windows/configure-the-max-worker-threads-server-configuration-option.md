---
title: Configurer l’option de configuration de serveur max worker threads | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- worker threads [SQL Server]
- max worker threads option
ms.assetid: abeadfa4-a14d-469a-bacf-75812e48fac1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4881cefee350d34d93b539c56be6f43866d3ddfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611298"
---
# <a name="configure-the-max-worker-threads-server-configuration-option"></a><span data-ttu-id="f82f7-102">Configurer l'option de configuration de serveur max worker threads</span><span class="sxs-lookup"><span data-stu-id="f82f7-102">Configure the max worker threads Server Configuration Option</span></span>
  <span data-ttu-id="f82f7-103">Cette rubrique explique comment configurer l'option de configuration de serveur **max worker threads** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f82f7-103">This topic describes how to configure the **max worker threads** server configuration option in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f82f7-104">L'option **max worker threads** configure le nombre de threads de travail disponibles pour les processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f82f7-104">The **max worker threads** option configures the number of worker threads that are available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f82f7-105">utilise les services de thread natifs des systèmes d'exploitation pour qu'un ou plusieurs threads prennent en charge chaque réseau que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prend en charge simultanément, qu'un autre thread prenne en charge les points de contrôle de base de données et qu'un pool de threads gère tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f82f7-105">uses the native thread services of the operating systems so that one or more threads support each network that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports simultaneously, another thread handles database checkpoints, and a pool of threads handles all users.</span></span> <span data-ttu-id="f82f7-106">La valeur par défaut de **Nombre maximum de threads de travail** est 0.</span><span class="sxs-lookup"><span data-stu-id="f82f7-106">The default value for **max worker threads** is 0.</span></span> <span data-ttu-id="f82f7-107">Cela permet à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de configurer automatiquement le nombre de threads de travail au démarrage.</span><span class="sxs-lookup"><span data-stu-id="f82f7-107">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically configure the number of worker threads at startup.</span></span> <span data-ttu-id="f82f7-108">Ce paramètre par défaut convient à la plupart des systèmes.</span><span class="sxs-lookup"><span data-stu-id="f82f7-108">The default setting is best for most systems.</span></span> <span data-ttu-id="f82f7-109">Cependant, selon votre configuration système, l'attribution d'une valeur spécifique à l'option **Nombre maximum de threads de travail** permet parfois d'accroître les performances.</span><span class="sxs-lookup"><span data-stu-id="f82f7-109">However, depending on your system configuration, setting **max worker threads** to a specific value sometimes improves performance.</span></span>  
  
 <span data-ttu-id="f82f7-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f82f7-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f82f7-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f82f7-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f82f7-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f82f7-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f82f7-113">Recommandations</span><span class="sxs-lookup"><span data-stu-id="f82f7-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f82f7-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f82f7-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f82f7-115">**Pour configurer l'option max worker threads, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="f82f7-115">**To configure the max worker threads option, using:**</span></span>  
  
     [<span data-ttu-id="f82f7-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f82f7-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f82f7-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f82f7-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="f82f7-118">**Suivi :**  [Après avoir configuré l'option Nombre maximum de threads de travail](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f82f7-118">**Follow Up:**  [After you configure the max worker threads option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f82f7-119">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f82f7-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f82f7-120">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f82f7-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f82f7-121">Lorsque le nombre de demandes de requêtes est inférieur au nombre défini dans l'option **Nombre maximum de threads de travail**, un thread traite chaque demande de requête.</span><span class="sxs-lookup"><span data-stu-id="f82f7-121">When the actual number of query requests is less than the amount set in **max worker threads**, one thread handles each query request.</span></span> <span data-ttu-id="f82f7-122">Toutefois, si le nombre réel de demandes de requête dépasse la valeur définie dans nombre **maximal de threads de travail**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] regroupe les threads de travail afin que le prochain thread de travail disponible puisse traiter la demande.</span><span class="sxs-lookup"><span data-stu-id="f82f7-122">However, if the actual number of query request exceeds the amount set in **max worker threads**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pools the worker threads so that the next available worker thread can handle the request.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f82f7-123">Recommandations</span><span class="sxs-lookup"><span data-stu-id="f82f7-123">Recommendations</span></span>  
  
-   <span data-ttu-id="f82f7-124">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f82f7-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="f82f7-125">Le regroupement de threads permet d'optimiser les performances lorsque de nombreux clients sont connectés au serveur.</span><span class="sxs-lookup"><span data-stu-id="f82f7-125">Thread pooling helps optimize performance when large numbers of clients are connected to the server.</span></span> <span data-ttu-id="f82f7-126">Habituellement, un thread de système d'exploitation séparé est créé pour chaque demande de requête.</span><span class="sxs-lookup"><span data-stu-id="f82f7-126">Usually, a separate operating system thread is created for each query request.</span></span> <span data-ttu-id="f82f7-127">Cependant, s'il existe des centaines de connexions au serveur, l'utilisation d'un thread par demande de requête peut consommer de grandes quantités de ressources système.</span><span class="sxs-lookup"><span data-stu-id="f82f7-127">However, with hundreds of connections to the server, using one thread per query request can consume large amounts of system resources.</span></span> <span data-ttu-id="f82f7-128">L'option **Nombre maximum de threads de travail** permet à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de créer un pool de threads de travail afin de servir un grand nombre de demandes de requête, ce qui améliore les performances.</span><span class="sxs-lookup"><span data-stu-id="f82f7-128">The **max worker threads** option enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to create a pool of worker threads to service a larger number of query requests, which improves performance.</span></span>  
  
-   <span data-ttu-id="f82f7-129">Le tableau ci-dessous montre le nombre maximal de threads de travail automatiquement configuré pour différentes combinaisons d'UC et de versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f82f7-129">The following table shows the automatically configured number of max worker threads for various combinations of CPUs and versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    |<span data-ttu-id="f82f7-130">Nombre d'unités centrales</span><span class="sxs-lookup"><span data-stu-id="f82f7-130">Number of CPUs</span></span>|<span data-ttu-id="f82f7-131">ordinateur 32 bits</span><span class="sxs-lookup"><span data-stu-id="f82f7-131">32-bit computer</span></span>|<span data-ttu-id="f82f7-132">Ordinateur 64 bits</span><span class="sxs-lookup"><span data-stu-id="f82f7-132">64-bit computer</span></span>|  
    |--------------------|----------------------|----------------------|  
    |<span data-ttu-id="f82f7-133">\<= 4 processeurs</span><span class="sxs-lookup"><span data-stu-id="f82f7-133">\<= 4 processors</span></span>|<span data-ttu-id="f82f7-134">256</span><span class="sxs-lookup"><span data-stu-id="f82f7-134">256</span></span>|<span data-ttu-id="f82f7-135">512</span><span class="sxs-lookup"><span data-stu-id="f82f7-135">512</span></span>|  
    |<span data-ttu-id="f82f7-136">8 processeurs</span><span class="sxs-lookup"><span data-stu-id="f82f7-136">8 processors</span></span>|<span data-ttu-id="f82f7-137">288</span><span class="sxs-lookup"><span data-stu-id="f82f7-137">288</span></span>|<span data-ttu-id="f82f7-138">576</span><span class="sxs-lookup"><span data-stu-id="f82f7-138">576</span></span>|  
    |<span data-ttu-id="f82f7-139">16 processeurs</span><span class="sxs-lookup"><span data-stu-id="f82f7-139">16 processors</span></span>|<span data-ttu-id="f82f7-140">352</span><span class="sxs-lookup"><span data-stu-id="f82f7-140">352</span></span>|<span data-ttu-id="f82f7-141">704</span><span class="sxs-lookup"><span data-stu-id="f82f7-141">704</span></span>|  
    |<span data-ttu-id="f82f7-142">32 processeurs</span><span class="sxs-lookup"><span data-stu-id="f82f7-142">32 processors</span></span>|<span data-ttu-id="f82f7-143">480</span><span class="sxs-lookup"><span data-stu-id="f82f7-143">480</span></span>|<span data-ttu-id="f82f7-144">960</span><span class="sxs-lookup"><span data-stu-id="f82f7-144">960</span></span>|  
    |<span data-ttu-id="f82f7-145">64 processeurs</span><span class="sxs-lookup"><span data-stu-id="f82f7-145">64 processors</span></span>|<span data-ttu-id="f82f7-146">736</span><span class="sxs-lookup"><span data-stu-id="f82f7-146">736</span></span>|<span data-ttu-id="f82f7-147">1472</span><span class="sxs-lookup"><span data-stu-id="f82f7-147">1472</span></span>|  
    |<span data-ttu-id="f82f7-148">128 processeurs</span><span class="sxs-lookup"><span data-stu-id="f82f7-148">128 processors</span></span>|<span data-ttu-id="f82f7-149">4224</span><span class="sxs-lookup"><span data-stu-id="f82f7-149">4224</span></span>|<span data-ttu-id="f82f7-150">4480</span><span class="sxs-lookup"><span data-stu-id="f82f7-150">4480</span></span>|  
    |<span data-ttu-id="f82f7-151">256 processeurs</span><span class="sxs-lookup"><span data-stu-id="f82f7-151">256 processors</span></span>|<span data-ttu-id="f82f7-152">8320</span><span class="sxs-lookup"><span data-stu-id="f82f7-152">8320</span></span>|<span data-ttu-id="f82f7-153">8576</span><span class="sxs-lookup"><span data-stu-id="f82f7-153">8576</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="f82f7-154">Pour obtenir des recommandations concernant l’utilisation de plus de 64 unités centrales, consultez [Recommandations pour l’exécution de SQL Server sur des ordinateurs comportant plus de 64 unités centrales](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="f82f7-154">For recommendations on using more than 64 CPUs, refer to [Best Practices for Running SQL Server on Computers That Have More Than 64 CPUs](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="f82f7-155">Nous vous recommandons d'utiliser 1 024 comme nombre maximal de threads de travail pour une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exécutée sur un ordinateur 32 bits.</span><span class="sxs-lookup"><span data-stu-id="f82f7-155">We recommend 1024 as the maximum number of worker threads for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on a 32-bit computer.</span></span>  
  
-   <span data-ttu-id="f82f7-156">Lorsque tous les threads de travail traitent de longues requêtes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut sembler ne plus répondre jusqu'à ce qu'un thread de travail soit terminé et devienne disponible.</span><span class="sxs-lookup"><span data-stu-id="f82f7-156">When all worker threads are active with long running queries, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might appear unresponsive until a worker thread completes and becomes available.</span></span> <span data-ttu-id="f82f7-157">Même s'il ne s'agit pas d'une défaillance, ce comportement peut parfois être indésirable.</span><span class="sxs-lookup"><span data-stu-id="f82f7-157">Although this is not a defect, it can sometimes be undesirable.</span></span> <span data-ttu-id="f82f7-158">Si un processus semble ne pas répondre et si aucune nouvelle requête n'est traitée, connectez-vous à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de la connexion administrateur dédiée (DAC) et terminez le processus.</span><span class="sxs-lookup"><span data-stu-id="f82f7-158">If a process appears to be unresponsive and no new queries can be processed, then connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the dedicated administrator connection (DAC), and kill the process.</span></span> <span data-ttu-id="f82f7-159">Pour éviter cette situation, augmentez la valeur de l'option max worker threads.</span><span class="sxs-lookup"><span data-stu-id="f82f7-159">To prevent this, increase the number of max worker threads.</span></span>  
  
 <span data-ttu-id="f82f7-160">L'option de configuration du serveur **max worker threads** (nombre maximal de threads de travail) ne prend pas en compte les threads requis pour toutes les tâches système, telles que les groupes de disponibilité, Service Broker, le gestionnaire de verrous et autres.</span><span class="sxs-lookup"><span data-stu-id="f82f7-160">The **max worker threads** server configuration option does not take into account threads that are required for all the system tasks such as Availibility Groups, Service Broker, Lock Manager, and others.</span></span>  <span data-ttu-id="f82f7-161">Si le nombre de threads configurés est dépassé, la requête suivante fournit des informations sur les tâches système qui ont engendré les threads supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f82f7-161">If the number of threads configured are being exceeded, the following query will provide information about the system tasks that have spawned the additional threads.</span></span>  
  
```  
SELECT  
s.session_id,  
r.command,  
r.status,  
r.wait_type,  
r.scheduler_id,  
w.worker_address,  
w.is_preemptive,  
w.state,  
t.task_state,  
t.session_id,  
t.exec_context_id,  
t.request_id  
FROM sys.dm_exec_sessions AS s  
INNERJOIN sys.dm_exec_requests AS r  
    ON s.session_id = r.session_id  
INNER JOIN sys.dm_os_tasks AS t  
    ON r.task_address = t.task_address  
INNER JOIN sys.dm_os_workers AS w  
    ON t.worker_address = w.worker_address  
WHERE s.is_user_process = 0;  
  
```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f82f7-162">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f82f7-162">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f82f7-163">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f82f7-163">Permissions</span></span>  
 <span data-ttu-id="f82f7-164">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f82f7-164">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="f82f7-165">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="f82f7-165">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="f82f7-166">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="f82f7-166">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f82f7-167">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f82f7-167">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="f82f7-168">Pour configurer l'option max worker threads</span><span class="sxs-lookup"><span data-stu-id="f82f7-168">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="f82f7-169">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f82f7-169">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f82f7-170">Cliquez sur le nœud **Processeurs** .</span><span class="sxs-lookup"><span data-stu-id="f82f7-170">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="f82f7-171">Dans la zone **nombre maximal de threads de travail** , tapez ou sélectionnez une valeur comprise entre 128 et 32767.</span><span class="sxs-lookup"><span data-stu-id="f82f7-171">In the **Max worker threads** box, type or select a value from 128 through 32767.</span></span>  
  
     <span data-ttu-id="f82f7-172">Utilisez l'option de définition du **nombre maximal de threads de travail** pour définir le nombre de threads de travail disponibles pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f82f7-172">Use the **max worker threads** option to configure the number of worker threads available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> <span data-ttu-id="f82f7-173">Le paramètre par défaut de **max worker threads** est adapté à la plupart des systèmes.</span><span class="sxs-lookup"><span data-stu-id="f82f7-173">The default setting for **max worker threads** is best for most systems.</span></span> <span data-ttu-id="f82f7-174">Cependant, selon votre configuration système, l'attribution d'une valeur plus faible à l'option **max worker threads** (Nombre maximum de threads de travail) permet parfois d'accroître les performances.</span><span class="sxs-lookup"><span data-stu-id="f82f7-174">However, depending on your system configuration, setting **max worker threads** to a smaller value sometimes improves performance.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f82f7-175">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f82f7-175">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="f82f7-176">Pour configurer l'option max worker threads</span><span class="sxs-lookup"><span data-stu-id="f82f7-176">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="f82f7-177">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f82f7-177">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f82f7-178">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f82f7-178">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f82f7-179">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f82f7-179">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f82f7-180">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `max worker threads` la valeur `900`.</span><span class="sxs-lookup"><span data-stu-id="f82f7-180">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max worker threads` option to `900`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'max worker threads', 900 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="f82f7-181">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f82f7-181">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-worker-threads-option"></a><a name="FollowUp"></a> <span data-ttu-id="f82f7-182">Suivi : Après avoir configuré l'option Nombre maximum de threads de travail</span><span class="sxs-lookup"><span data-stu-id="f82f7-182">Follow Up: After you configure the max worker threads option</span></span>  
 <span data-ttu-id="f82f7-183">La modification prendra effet immédiatement, sans nécessiter le redémarrage du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f82f7-183">The change will take effect immediately without requiring the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82f7-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f82f7-184">See Also</span></span>  
 <span data-ttu-id="f82f7-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f82f7-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="f82f7-186">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f82f7-186">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="f82f7-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f82f7-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="f82f7-188">Connexion de diagnostic pour les administrateurs de base de données</span><span class="sxs-lookup"><span data-stu-id="f82f7-188">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
