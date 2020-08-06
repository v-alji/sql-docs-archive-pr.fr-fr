---
title: Configurer l’option de configuration de serveur cost threshold for parallelism | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cost threshold for parallelism option
ms.assetid: dad21bee-fe28-41f6-9d2f-e6ababfaf9db
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 675055a753e84ace3a4fcb44b41b8c914326c5c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601693"
---
# <a name="configure-the-cost-threshold-for-parallelism-server-configuration-option"></a><span data-ttu-id="15600-102">Configurer l'option de configuration de serveur cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="15600-102">Configure the cost threshold for parallelism Server Configuration Option</span></span>
  <span data-ttu-id="15600-103">Cette rubrique explique comment configurer l'option de configuration de serveur **cost threshold for parallelism** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15600-103">This topic describes how to configure the **cost threshold for parallelism** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="15600-104">L'option **cost threshold for parallelism** spécifie le seuil de création et d'exécution des plans parallèles par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15600-104">The **cost threshold for parallelism** option specifies the threshold at which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates and runs parallel plans for queries.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="15600-105">crée et exécute un plan parallèle pour une requête uniquement lorsque le coût estimé de l'exécution d'un plan en série pour la même requête est supérieur à la valeur définie dans **Seuil de coût pour le parallélisme**.</span><span class="sxs-lookup"><span data-stu-id="15600-105">creates and runs a parallel plan for a query only when the estimated cost to run a serial plan for the same query is higher than the value set in **cost threshold for parallelism**.</span></span> <span data-ttu-id="15600-106">Ce coût fait référence à l'estimation du temps (exprimé en secondes) nécessaire à l'exécution du plan de série pour une configuration matérielle spécifique.</span><span class="sxs-lookup"><span data-stu-id="15600-106">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="15600-107">L'option **cost threshold for parallelism** peut prendre toute valeur comprise entre 0 et 32 767.</span><span class="sxs-lookup"><span data-stu-id="15600-107">The **cost threshold for parallelism** option can be set to any value from 0 through 32767.</span></span> <span data-ttu-id="15600-108">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="15600-108">The default value is 5.</span></span>  
  
 <span data-ttu-id="15600-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="15600-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="15600-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="15600-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="15600-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="15600-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="15600-112">Recommandations</span><span class="sxs-lookup"><span data-stu-id="15600-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="15600-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="15600-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="15600-114">**Pour configurer l'option cost threshold for parallelism, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="15600-114">**To configure the cost threshold for parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="15600-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15600-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="15600-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15600-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="15600-117">**Suivi :**  [Après avoir configuré l’option cost threshold for parallelism](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="15600-117">**Follow Up:**  [After you configure the cost threshold for parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="15600-118">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="15600-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="15600-119">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="15600-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="15600-120">Ce coût fait référence à l'estimation du temps (exprimé en secondes) nécessaire à l'exécution du plan de série pour une configuration matérielle spécifique.</span><span class="sxs-lookup"><span data-stu-id="15600-120">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="15600-121">Spécifiez **cost threshold for parallelism** uniquement sur des multiprocesseurs symétriques.</span><span class="sxs-lookup"><span data-stu-id="15600-121">Only set **cost threshold for parallelism** on symmetric multiprocessors.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="15600-122">ignore la valeur de l'option **cost threshold for parallelism** dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="15600-122">ignores the **cost threshold for parallelism** value under the following conditions:</span></span>  
  
    -   <span data-ttu-id="15600-123">L'ordinateur ne dispose que d'un seul processeur logique.</span><span class="sxs-lookup"><span data-stu-id="15600-123">Your computer has only one logical processor.</span></span>  
  
    -   <span data-ttu-id="15600-124">Un seul processeur logique est disponible pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en raison de l’option de configuration **affinity mask** .</span><span class="sxs-lookup"><span data-stu-id="15600-124">Only a single logical processor is available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because of the **affinity mask** configuration option.</span></span>  
  
    -   <span data-ttu-id="15600-125">L'option de degré maximal de parallélisme **max degree of parallelism** a la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="15600-125">The **max degree of parallelism** option is set to 1.</span></span>  
  
 <span data-ttu-id="15600-126">Un processeur logique correspond à l'unité de base d'un processeur qui permet au système d'exploitation de distribuer une tâche ou d'exécuter un contexte de thread.</span><span class="sxs-lookup"><span data-stu-id="15600-126">A logical processor is the basic unit of processor hardware that allows the operating system to dispatch a task or execute a thread context.</span></span> <span data-ttu-id="15600-127">Chaque processeur logique peut exécuter uniquement un contexte de thread à la fois.</span><span class="sxs-lookup"><span data-stu-id="15600-127">Each logical processor can execute only one thread context at a time.</span></span> <span data-ttu-id="15600-128">Le noyau du processeur désigne le circuit qui permet de décoder et d'exécuter des instructions.</span><span class="sxs-lookup"><span data-stu-id="15600-128">The processor core is the circuitry that provides ability to decode and execute instructions.</span></span> <span data-ttu-id="15600-129">Un noyau de processeur peut contenir un ou plusieurs processeurs logiques.</span><span class="sxs-lookup"><span data-stu-id="15600-129">A processor core may contain one or more logical processors.</span></span> <span data-ttu-id="15600-130">La requête [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante peut être utilisée pour obtenir les informations de l'UC pour le système.</span><span class="sxs-lookup"><span data-stu-id="15600-130">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] query can be used for obtaining CPU information for the system.</span></span>  
  
```  
SELECT (cpu_count / hyperthread_ratio) AS PhysicalCPUs,   
cpu_count AS logicalCPUs   
FROM sys.dm_os_sys_info  
```  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="15600-131">Recommandations</span><span class="sxs-lookup"><span data-stu-id="15600-131">Recommendations</span></span>  
  
-   <span data-ttu-id="15600-132">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15600-132">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="15600-133">Dans certains cas, un plan parallèle peut être choisi, même si le plan de coût de la requête est inférieur à la valeur actuelle de l'option **Seuil de coût pour le parallélisme** .</span><span class="sxs-lookup"><span data-stu-id="15600-133">In certain cases, a parallel plan may be chosen even though the query's cost plan is less than the current **cost threshold for parallelism** value.</span></span> <span data-ttu-id="15600-134">Cela s'explique par le fait que la décision d'utilisation d'un plan parallèle ou d'un plan en série prend comme base une estimation de coût fournie avant que l'optimisation soit terminée.</span><span class="sxs-lookup"><span data-stu-id="15600-134">This can happen because the decision to use a parallel or serial plan is based on a cost estimate provided before the full optimization is complete.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="15600-135">Sécurité</span><span class="sxs-lookup"><span data-stu-id="15600-135">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="15600-136">Autorisations</span><span class="sxs-lookup"><span data-stu-id="15600-136">Permissions</span></span>  
 <span data-ttu-id="15600-137">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="15600-137">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="15600-138">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="15600-138">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="15600-139">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="15600-139">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="15600-140">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15600-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="15600-141">Pour configurer l'option cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="15600-141">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="15600-142">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="15600-142">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="15600-143">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="15600-143">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="15600-144">Sous **Parallélisme**, remplacez l'option **Seuil de coût pour le parallélisme** par la valeur souhaitée.</span><span class="sxs-lookup"><span data-stu-id="15600-144">Under **Parallelism**, change the **CostThresholdForParallelism** option to the value you want.</span></span> <span data-ttu-id="15600-145">Tapez ou sélectionnez une valeur comprise entre 0 et 32 767.</span><span class="sxs-lookup"><span data-stu-id="15600-145">Type or select a value from 0 to 32767.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="15600-146">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15600-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="15600-147">Pour configurer l'option cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="15600-147">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="15600-148">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15600-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="15600-149">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="15600-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="15600-150">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="15600-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="15600-151">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `cost threshold for parallelism` la valeur `10`.</span><span class="sxs-lookup"><span data-stu-id="15600-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `cost threshold for parallelism` option to `10`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cost threshold for parallelism', 10 ;  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="15600-152">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="15600-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cost-threshold-for-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="15600-153">Suivi : Après avoir configuré l’option cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="15600-153">Follow Up: After you configure the cost threshold for parallelism option</span></span>  
 <span data-ttu-id="15600-154">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="15600-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15600-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="15600-155">See Also</span></span>  
 <span data-ttu-id="15600-156">[Configurer des opérations d'index parallèles](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="15600-156">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="15600-157">[Indicateurs de requête &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="15600-157">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 <span data-ttu-id="15600-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15600-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="15600-159">[affinity mask (option de configuration de serveur)](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="15600-159">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="15600-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15600-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="15600-161">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15600-161">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="15600-162">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15600-162">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
