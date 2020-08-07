---
title: Configurer l’option de configuration de serveur max degree of parallelism | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parallel queries [SQL Server]
- processors [SQL Server], parallel queries
- number of processors for parallel queries
- max degree of parallelism option
ms.assetid: 86b65bf1-a6a1-4670-afc0-cdfad1558032
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 824dc837142acc4a0898cb04b4a8687bc5be4043
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611300"
---
# <a name="configure-the-max-degree-of-parallelism-server-configuration-option"></a><span data-ttu-id="a00ea-102">Configurer l'option de configuration de serveur max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="a00ea-102">Configure the max degree of parallelism Server Configuration Option</span></span>
  <span data-ttu-id="a00ea-103">Cette rubrique explique comment configurer l' `max degree of parallelism` option de configuration de serveur dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a00ea-103">This topic describes how to configure the `max degree of parallelism` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a00ea-104">Lorsqu'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute sur un ordinateur doté de plusieurs microprocesseurs ou UC, elle détecte le degré de parallélisme optimal, qui correspond au nombre de processeurs employés pour exécuter une seule instruction, pour chaque exécution d'un plan parallèle.</span><span class="sxs-lookup"><span data-stu-id="a00ea-104">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on a computer that has more than one microprocessor or CPU, it detects the best degree of parallelism, that is, the number of processors employed to run a single statement, for each parallel plan execution.</span></span> <span data-ttu-id="a00ea-105">Vous pouvez utiliser l'option `max degree of parallelism` pour limiter le nombre de processeurs à utiliser dans une exécution de plans parallèles.</span><span class="sxs-lookup"><span data-stu-id="a00ea-105">You can use the `max degree of parallelism` option to limit the number of processors to use in parallel plan execution.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a00ea-106">prend en compte les plans d’exécution parallèle pour les requêtes, les opérations DDL (Data Definition Language) d’index et l’alimentation des curseurs statiques et pilotés par keyset.</span><span class="sxs-lookup"><span data-stu-id="a00ea-106">considers parallel execution plans for queries, index data definition language (DDL) operations, and static and keyset-driven cursor population.</span></span>  
  
 <span data-ttu-id="a00ea-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="a00ea-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a00ea-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a00ea-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a00ea-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a00ea-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a00ea-110">Recommandations</span><span class="sxs-lookup"><span data-stu-id="a00ea-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="a00ea-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a00ea-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a00ea-112">**Pour configurer l'option Degré maximal de parallélisme, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="a00ea-112">**To configure the max degree of parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="a00ea-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a00ea-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a00ea-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a00ea-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="a00ea-115">**Suivi :**  [Après avoir configuré l'option Degré maximal de parallélisme](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a00ea-115">**Follow Up:**  [After you configure the max degree of parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a00ea-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a00ea-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a00ea-117">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a00ea-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a00ea-118">Si l'option affinity mask n'est pas définie sur la valeur par défaut, il est possible qu'elle limite le nombre de processeurs disponibles pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur les systèmes de multitraitement symétrique (SMP, symmetric multiprocessing).</span><span class="sxs-lookup"><span data-stu-id="a00ea-118">If the affinity mask option is not set to the default, it may restrict the number of processors available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on symmetric multiprocessing (SMP) systems.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a00ea-119">Recommandations</span><span class="sxs-lookup"><span data-stu-id="a00ea-119">Recommendations</span></span>  
  
-   <span data-ttu-id="a00ea-120">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a00ea-120">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="a00ea-121">Pour permettre au serveur de déterminer le degré maximal de parallélisme, définissez cette option sur 0, c'est-à-dire la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="a00ea-121">To enable the server to determine the maximum degree of parallelism, set this option to 0, the default value.</span></span> <span data-ttu-id="a00ea-122">Attribuer la valeur 0 à l'option Degré maximal de parallélisme permet à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'utiliser tous les processeurs disponibles, dans la limite de 64.</span><span class="sxs-lookup"><span data-stu-id="a00ea-122">Setting maximum degree of parallelism to 0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use all the available processors up to 64 processors.</span></span> <span data-ttu-id="a00ea-123">Pour supprimer la génération de plans parallèles, attribuez la valeur 1 à l'option `max degree of parallelism`.</span><span class="sxs-lookup"><span data-stu-id="a00ea-123">To suppress parallel plan generation, set `max degree of parallelism` to 1.</span></span> <span data-ttu-id="a00ea-124">Affectez la valeur à un nombre compris entre 1 et 32 767 pour spécifier le nombre maximal de noyaux de processeurs qui peuvent être utilisés par une seule exécution.</span><span class="sxs-lookup"><span data-stu-id="a00ea-124">Set the value to a number from 1 to 32,767 to specify the maximum number of processor cores that can be used by a single query execution.</span></span> <span data-ttu-id="a00ea-125">Si une valeur supérieure au nombre de processeurs disponibles est spécifiée, le nombre réel de processeurs disponibles est utilisé.</span><span class="sxs-lookup"><span data-stu-id="a00ea-125">If a value greater than the number of available processors is specified, the actual number of available processors is used.</span></span> <span data-ttu-id="a00ea-126">Si l'ordinateur est équipé d'un seul processeur, la valeur de l'option `max degree of parallelism` est ignorée.</span><span class="sxs-lookup"><span data-stu-id="a00ea-126">If the computer has only one processor, the `max degree of parallelism` value is ignored.</span></span>  
  
-   <span data-ttu-id="a00ea-127">Vous pouvez remplacer la valeur de l'option max degree of parallelism dans les requêtes en spécifiant l'indicateur de requête MAXDOP dans l'instruction de requête.</span><span class="sxs-lookup"><span data-stu-id="a00ea-127">You can override the max degree of parallelism value in queries by specifying the MAXDOP query hint in the query statement.</span></span> <span data-ttu-id="a00ea-128">Pour plus d’informations, consultez [Indicateurs de requête &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="a00ea-128">For more information, see [Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
-   <span data-ttu-id="a00ea-129">Les opérations d'index destinées à créer ou à recréer un index, voire à supprimer un index cluster, peuvent nécessiter une quantité importante de ressources.</span><span class="sxs-lookup"><span data-stu-id="a00ea-129">Index operations that create or rebuild an index, or that drop a clustered index, can be resource intensive.</span></span> <span data-ttu-id="a00ea-130">Vous pouvez remplacer la valeur de l'option max degree of parallelism pour les opérations d'index en spécifiant l'option d'index MAXDOP dans l'instruction d'index.</span><span class="sxs-lookup"><span data-stu-id="a00ea-130">You can override the max degree of parallelism value for index operations by specifying the MAXDOP index option in the index statement.</span></span> <span data-ttu-id="a00ea-131">La valeur de MAXDOP est appliquée à l'instruction au moment de son exécution et n'est pas stockée dans les métadonnées de l'index.</span><span class="sxs-lookup"><span data-stu-id="a00ea-131">The MAXDOP value is applied to the statement at execution time and is not stored in the index metadata.</span></span> <span data-ttu-id="a00ea-132">Pour plus d’informations, consultez [Configurer des opérations d’index parallèles](../../relational-databases/indexes/configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="a00ea-132">For more information, see [Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md).</span></span>  
  
-   <span data-ttu-id="a00ea-133">En plus des requêtes et des opérations d'index, cette option gère également le parallélisme de DBCC CHECKTABLE, DBCC CHECKDB et DBCC CHECKFILEGROUP.</span><span class="sxs-lookup"><span data-stu-id="a00ea-133">In addition to queries and index operations, this option also controls the parallelism of DBCC CHECKTABLE, DBCC CHECKDB, and DBCC CHECKFILEGROUP.</span></span> <span data-ttu-id="a00ea-134">Vous pouvez désactiver les plans d'exécution parallèle pour ces instructions en utilisant l'indicateur de trace 2528.</span><span class="sxs-lookup"><span data-stu-id="a00ea-134">You can disable parallel execution plans for these statements by using trace flag 2528.</span></span> <span data-ttu-id="a00ea-135">Pour plus d’informations, consultez [Indicateurs de trace &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a00ea-135">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a00ea-136">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a00ea-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a00ea-137">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a00ea-137">Permissions</span></span>  
 <span data-ttu-id="a00ea-138">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a00ea-138">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="a00ea-139">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="a00ea-139">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="a00ea-140">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="a00ea-140">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a00ea-141">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a00ea-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="a00ea-142">Pour configurer l'option max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="a00ea-142">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="a00ea-143">Dans l’ **Explorateur d’objets**, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a00ea-143">In **Object Explorer**, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="a00ea-144">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="a00ea-144">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="a00ea-145">Dans la zone **Degré maximal de parallélisme** , sélectionnez le nombre maximal de processeurs à utiliser au cours de l'exécution d'un plan parallèle.</span><span class="sxs-lookup"><span data-stu-id="a00ea-145">In the **Max Degree of Parallelism** box, select the maximum number of processors to use in parallel plan execution.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a00ea-146">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a00ea-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="a00ea-147">Pour configurer l'option max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="a00ea-147">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="a00ea-148">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a00ea-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a00ea-149">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a00ea-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a00ea-150">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a00ea-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a00ea-151">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `max degree of parallelism` la valeur `8`.</span><span class="sxs-lookup"><span data-stu-id="a00ea-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max degree of parallelism` option to `8`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO   
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
EXEC sp_configure 'max degree of parallelism', 8;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
```  
  
 <span data-ttu-id="a00ea-152">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a00ea-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-degree-of-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="a00ea-153">Suivi : Après avoir configuré l’option max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="a00ea-153">Follow Up: After you configure the max degree of parallelism option</span></span>  
 <span data-ttu-id="a00ea-154">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="a00ea-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00ea-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a00ea-155">See Also</span></span>  
 <span data-ttu-id="a00ea-156">[affinity mask (option de configuration de serveur)](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="a00ea-156">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="a00ea-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a00ea-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="a00ea-158">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a00ea-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="a00ea-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a00ea-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="a00ea-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a00ea-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="a00ea-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a00ea-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="a00ea-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a00ea-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="a00ea-163">[DBCC CHECKTABLE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a00ea-163">[DBCC CHECKTABLE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span></span>  
 <span data-ttu-id="a00ea-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a00ea-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="a00ea-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a00ea-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="a00ea-166">[Configurer des opérations d'index parallèles](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="a00ea-166">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="a00ea-167">[Indicateurs de requête &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="a00ea-167">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="a00ea-168">Définir les options d’index</span><span class="sxs-lookup"><span data-stu-id="a00ea-168">Set Index Options</span></span>](../../relational-databases/indexes/set-index-options.md)  
  
  
