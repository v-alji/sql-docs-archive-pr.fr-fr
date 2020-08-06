---
title: Analyse des performances à l’aide du Magasin des requêtes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: e06344a4-22a5-4c67-b6c6-a7060deb5de6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5d74b9c4def9c0314569a8d0bd87939cdcb11b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613994"
---
# <a name="monitoring-performance-by-using-the-query-store"></a><span data-ttu-id="50a75-102">Analyse des performances à l'aide du magasin de requêtes</span><span class="sxs-lookup"><span data-stu-id="50a75-102">Monitoring Performance By Using the Query Store</span></span>
  <span data-ttu-id="50a75-103">La fonctionnalité de magasin de requêtes fournit aux administrateurs de bases de données des informations sur le choix de plan de requête et les performances.</span><span class="sxs-lookup"><span data-stu-id="50a75-103">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="50a75-104">Elle simplifie la résolution des problèmes de performances en vous permettant de trouver rapidement les différences de performances provoquées par un changement de plan de requête.</span><span class="sxs-lookup"><span data-stu-id="50a75-104">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="50a75-105">La fonctionnalité capture automatiquement l'historique des requêtes, des plans et des statistiques d'exécution et les conserve à des fins de consultation.</span><span class="sxs-lookup"><span data-stu-id="50a75-105">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="50a75-106">Elle sépare les données en périodes, ce qui vous permet de voir les modèles d'utilisation de base de données et de comprendre à quel moment le changement de plan de requête a eu lieu sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="50a75-106">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="50a75-107">Le magasin de requêtes peut être configuré à l'aide de l'option [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="50a75-107">The query store can be configured by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span>

||
|-|
|<span data-ttu-id="50a75-108">**S’applique à**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] (l'[obtient](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span><span class="sxs-lookup"><span data-stu-id="50a75-108">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([Get it](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="50a75-109">Il s'agit actuellement d'une fonctionnalité d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="50a75-109">This is currently a preview feature.</span></span> <span data-ttu-id="50a75-110">Pour utiliser le magasin de requêtes, vous devez reconnaître et accepter que l'implémentation du magasin de requêtes est soumise aux termes de la version d'évaluation dans votre contrat de licence (par exemple, Contrat Entreprise, Contrat Microsoft Azure ou Contrat d'abonnement à Microsoft Online), ainsi qu'à toutes les [Conditions d'Utilisation Supplémentaires relatives aux Évaluations Microsoft Azure](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span><span class="sxs-lookup"><span data-stu-id="50a75-110">To use the Query Store you must acknowledge and agree that implementation of Query Store is subject to the preview terms in your license agreement (e.g. the Enterprise Agreement, Microsoft Azure Agreement, or Microsoft Online Subscription Agreement), as well as any applicable [Supplemental Terms of Use for Microsoft Azure Preview](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span></span>

##  <a name="enabling-the-query-store"></a><a name="Enabling"></a> <span data-ttu-id="50a75-111">Activation du magasin de requêtes</span><span class="sxs-lookup"><span data-stu-id="50a75-111">Enabling the Query Store</span></span>
 <span data-ttu-id="50a75-112">Le magasin de requêtes n'est pas actif par défaut pour les nouvelles bases de données.</span><span class="sxs-lookup"><span data-stu-id="50a75-112">Query Store is not active for new databases by default.</span></span>

#### <a name="by-using-the-query-store-page-in-management-studio"></a><span data-ttu-id="50a75-113">En utilisant la page Magasin de requêtes dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="50a75-113">By Using the Query Store Page in Management Studio</span></span>

1.  <span data-ttu-id="50a75-114">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur une base de données, puis sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="50a75-114">In Object Explorer, right-click a database, and then click **Properties**.</span></span> <span data-ttu-id="50a75-115">(Nécessite la version [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 de [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="50a75-115">(Requires [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 version of [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span></span>

2.  <span data-ttu-id="50a75-116">Dans la boîte de dialogue **Propriétés de la base de données** , sélectionnez la page **Magasin de requêtes** .</span><span class="sxs-lookup"><span data-stu-id="50a75-116">In the **Database Properties** dialog box, select the **Query Store** page.</span></span>

3.  <span data-ttu-id="50a75-117">Dans la case **Activer** , sélectionnez **True**.</span><span class="sxs-lookup"><span data-stu-id="50a75-117">In the **Enable** box, select **True**.</span></span>

#### <a name="by-using-transact-sql-statements"></a><span data-ttu-id="50a75-118">En utilisant des instructions Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50a75-118">By Using Transact-SQL Statements</span></span>

1.  <span data-ttu-id="50a75-119">Utilisez l’instruction `ALTER DATABASE` pour activer le magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-119">Use the `ALTER DATABASE` statement to enable the query store.</span></span> <span data-ttu-id="50a75-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="50a75-120">For example:</span></span>

    ```
    ALTER DATABASE AdventureWorks2012 SET QUERY_STORE = ON;
    ```

     <span data-ttu-id="50a75-121">Pour obtenir d’autres options de syntaxe relatives au magasin de requêtes, consultez [options ALTER DATABASE SET &#40;&#41;Transact-SQL ](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="50a75-121">For more syntax options related to the query store, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>

> [!NOTE]
>  <span data-ttu-id="50a75-122">Vous ne pouvez pas activer le magasin de requêtes pour la base de données MASTER.</span><span class="sxs-lookup"><span data-stu-id="50a75-122">You cannot enable the query store for the master database.</span></span>



##  <a name="information-in-the-query-store"></a><a name="About"></a> <span data-ttu-id="50a75-123">Informations sur le Magasin des requêtes</span><span class="sxs-lookup"><span data-stu-id="50a75-123">Information in the Query Store</span></span>
 <span data-ttu-id="50a75-124">Les plans d’exécution d’une requête spécifique dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] évoluent généralement au fil du temps pour un certain nombre de raisons, telles que les modifications des statistiques, les modifications de schémas, la création/suppression d’index, etc. Le cache de procédures (où sont stockés les plans de requête mis en cache) stocke uniquement le dernier plan d'exécution.</span><span class="sxs-lookup"><span data-stu-id="50a75-124">Execution plans for any specific query in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] typically evolve over time due to a number of different reasons such as statistics changes, schema changes, creation/deletion of indexes, etc. The procedure cache (where cached query plans are stored) only stores the latest execution plan.</span></span> <span data-ttu-id="50a75-125">Les plans sont également supprimés du cache du plan en raison de la sollicitation de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="50a75-125">Plans also get evicted from the plan cache due to memory pressure.</span></span> <span data-ttu-id="50a75-126">Par conséquent, les régressions des performances de requête provoquées par des modifications du plan d'exécution peuvent être significatives et longues à résoudre.</span><span class="sxs-lookup"><span data-stu-id="50a75-126">As a result, query performance regressions caused by execution plan changes can be non-trivial and time consuming to resolve.</span></span>

 <span data-ttu-id="50a75-127">Comme le magasin de requêtes conserve plusieurs plans d'exécution par requête, il peut appliquer des stratégies pour indiquer au processeur de requêtes d'utiliser un plan d'exécution spécifique pour une requête.</span><span class="sxs-lookup"><span data-stu-id="50a75-127">Since the query store retains multiple execution plans per query, it can enforce policies to direct the query processor to use a specific execution plan for a query.</span></span> <span data-ttu-id="50a75-128">On parle alors de forçage de plan.</span><span class="sxs-lookup"><span data-stu-id="50a75-128">This is referred to as plan forcing.</span></span> <span data-ttu-id="50a75-129">Le forçage de plan dans un magasin de requêtes est fourni à l'aide d'un mécanisme semblable à l’indicateur de requête [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) , mais il ne nécessite pas d’apporter des modifications dans les applications utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50a75-129">Plan forcing in Query Store is provided by using a mechanism similar to the [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) query hint, but it does not require any change in user applications.</span></span> <span data-ttu-id="50a75-130">Le forçage de plan peut résoudre une régression des performances de requête provoquée par une modification du plan dans un délai très court.</span><span class="sxs-lookup"><span data-stu-id="50a75-130">Plan forcing can resolve a query performance regression caused by a plan change in a very short period of time.</span></span>

 <span data-ttu-id="50a75-131">Voici des scénarios courants pour l'utilisation de la fonctionnalité de magasin de requêtes :</span><span class="sxs-lookup"><span data-stu-id="50a75-131">Common scenarios for using the Query Store feature are:</span></span>

-   <span data-ttu-id="50a75-132">Recherchez et corrigez rapidement une régression des performances du plan en forçant l’application du plan de requête précédent.</span><span class="sxs-lookup"><span data-stu-id="50a75-132">Quickly find and fix a plan performance regression by forcing the previous query plan.</span></span> <span data-ttu-id="50a75-133">Résolvez les requêtes qui ont récemment rencontré une régression des performances suite à la modification du plan d'exécution.</span><span class="sxs-lookup"><span data-stu-id="50a75-133">Fix queries that have recently regressed in performance due to execution plan changes.</span></span>

-   <span data-ttu-id="50a75-134">Déterminez le nombre de fois où une requête a été exécutée dans une fenêtre de temps donnée, en aidant un administrateur de base de données à résoudre les problèmes liés aux ressources de performances.</span><span class="sxs-lookup"><span data-stu-id="50a75-134">Determine the number of times a query was executed in a given time window, assisting a DBA in troubleshooting performance resource problems.</span></span>

-   <span data-ttu-id="50a75-135">Identifiez les *n* requêtes les plus importantes (en termes de temps d’exécution, de consommation de mémoire, etc.) au cours des *x* dernières heures.</span><span class="sxs-lookup"><span data-stu-id="50a75-135">Identify top *n* queries (by execution time, memory consumption, etc.) in the past *x* hours.</span></span>

-   <span data-ttu-id="50a75-136">Auditez l'historique des plans de requête pour une requête donnée.</span><span class="sxs-lookup"><span data-stu-id="50a75-136">Audit the history of query plans for a given query.</span></span>

-   <span data-ttu-id="50a75-137">Analysez les ressources (UC, E/S et mémoire) des modèles d'utilisation pour une base de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="50a75-137">Analyze the resource (CPU, I/O, and Memory) usage patterns for a particular database.</span></span>

 <span data-ttu-id="50a75-138">Le magasin de requêtes contient deux magasins : un **magasin de plans** pour rendre persistantes les informations du plan d'exécution et un **magasin des statistiques d'exécution** pour rendre persistantes les informations sur les statistiques d'exécution.</span><span class="sxs-lookup"><span data-stu-id="50a75-138">The query store contains two stores; a **plan store** for persisting the execution plan information, and a **runtime stats store** for persisting the execution statistics information.</span></span> <span data-ttu-id="50a75-139">Le nombre de plans uniques pouvant être stockés pour une requête dans le magasin de plans est limité par l'option de configuration `max_plans_per_query`.</span><span class="sxs-lookup"><span data-stu-id="50a75-139">The number of unique plans that can be stored for a query in the plan store is limited by the `max_plans_per_query` configuration option.</span></span> <span data-ttu-id="50a75-140">Pour améliorer les performances, les informations sont écrites dans les deux magasins de façon asynchrone.</span><span class="sxs-lookup"><span data-stu-id="50a75-140">To enhance performance, the information is written to the two stores asynchronously.</span></span> <span data-ttu-id="50a75-141">Pour optimiser l'espace, les statistiques d'exécution du runtime du magasin de statistiques du runtime sont agrégées sur une période fixe.</span><span class="sxs-lookup"><span data-stu-id="50a75-141">To minimize space usage, the runtime execution statistics in the runtime stats store are aggregated over a fixed time window.</span></span> <span data-ttu-id="50a75-142">Les informations contenues dans ces magasins sont visibles en interrogeant les affichages de catalogue du magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-142">The information in these stores is visible by querying the query store catalog views.</span></span>

 <span data-ttu-id="50a75-143">La requête suivante retourne des informations sur les requêtes et plans du magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-143">The following query returns information about queries and plans in the query store.</span></span>

```
SELECT Txt.query_text_id, Txt.query_sql_text, Pl.plan_id, Qry.*
FROM sys.query_store_plan AS Pl
JOIN sys.query_store_query AS Qry
    ON Pl.query_id = Qry.query_id
JOIN sys.query_store_query_text AS Txt
    ON Qry.query_text_id = Txt.query_text_id ;
```



## <a name="using-the-regressed-queries-feature"></a><span data-ttu-id="50a75-144">Utilisation de la fonctionnalité de régression des requêtes</span><span class="sxs-lookup"><span data-stu-id="50a75-144">Using the Regressed Queries Feature</span></span>
 <span data-ttu-id="50a75-145">Après avoir activé le magasin de requêtes, actualisez la partie base de données du volet de l’Explorateur d’objets pour ajouter la section **magasin des requêtes** .</span><span class="sxs-lookup"><span data-stu-id="50a75-145">After enabling the query store, refresh the database portion of the Object Explorer pane to add the **Query Store** section.</span></span>

 <span data-ttu-id="50a75-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span><span class="sxs-lookup"><span data-stu-id="50a75-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span></span>

 <span data-ttu-id="50a75-147">Sélectionnez **Requêtes en régression**pour ouvrir le volet **Requêtes en régression** dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50a75-147">Selecting **Regressed Queries**, opens the **Regressed Queries** pane in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="50a75-148">Le volet Requêtes en régression affiche les requêtes et les plans du magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-148">The Regressed Queries pane shows you the queries, and plans in the query store.</span></span> <span data-ttu-id="50a75-149">Les listes déroulantes situées en haut vous permettent de sélectionner les requêtes selon différents critères.</span><span class="sxs-lookup"><span data-stu-id="50a75-149">Drop down boxes at the top allow you to select queries based on various criteria.</span></span> <span data-ttu-id="50a75-150">Sélectionnez un plan pour afficher le plan de requête sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="50a75-150">Select a plan to see the graphical query plan.</span></span> <span data-ttu-id="50a75-151">Des boutons permettent d'afficher la requête source, de forcer un plan de requête et d’annuler son application forcée, ainsi que d'actualiser l'affichage.</span><span class="sxs-lookup"><span data-stu-id="50a75-151">Buttons are available to view the source query, force, and unforce a query plan, and refresh the display.</span></span>

 <span data-ttu-id="50a75-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span><span class="sxs-lookup"><span data-stu-id="50a75-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span></span>

 <span data-ttu-id="50a75-153">Pour forcer un plan, sélectionnez une requête et un plan, puis cliquez sur **forcer le plan.**</span><span class="sxs-lookup"><span data-stu-id="50a75-153">To force a plan, select a query and plan, and then click **Force Plan.**</span></span> <span data-ttu-id="50a75-154">Vous pouvez uniquement forcer des plans qui ont été enregistrés par la fonctionnalité de plan de requête et sont toujours conservés dans le cache du plan de requête.</span><span class="sxs-lookup"><span data-stu-id="50a75-154">You can only force plans that were saved by the query plan feature and are still retained in the query plan cache.</span></span>



##  <a name="configuration-options"></a><a name="Options"></a> <span data-ttu-id="50a75-155">Options de configuration</span><span class="sxs-lookup"><span data-stu-id="50a75-155">Configuration Options</span></span>
 <span data-ttu-id="50a75-156">OPERATION_MODE peut être READ_WRITE ou READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="50a75-156">OPERATION_MODE Can be READ_WRITE or READ_ONLY.</span></span>

 <span data-ttu-id="50a75-157">CLEANUP_POLICY configurez l’argument STALE_QUERY_THRESHOLD_DAYS pour spécifier le nombre de jours pendant lesquels les données doivent être conservées dans le magasin des requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-157">CLEANUP_POLICY Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>

 <span data-ttu-id="50a75-158">DATA_FLUSH_INTERVAL_SECONDS détermine la fréquence à laquelle les données écrites sur le magasin des requêtes sont conservées sur le disque.</span><span class="sxs-lookup"><span data-stu-id="50a75-158">DATA_FLUSH_INTERVAL_SECONDS Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="50a75-159">Pour optimiser les performances, les données collectées par le magasin de requête sont écrites de façon asynchrone sur le disque.</span><span class="sxs-lookup"><span data-stu-id="50a75-159">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="50a75-160">La fréquence à laquelle ce transfert asynchrone se produit est configurée via DATA_FLUSH_INTERVAL_SECONDS.</span><span class="sxs-lookup"><span data-stu-id="50a75-160">The frequency at which this asynchronous transfer occurs is configured via DATA_FLUSH_INTERVAL_SECONDS.</span></span>

 <span data-ttu-id="50a75-161">MAX_SIZE_MB configure la taille maximale du magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-161">MAX_SIZE_MB Configures the maximum size of the query store.</span></span> <span data-ttu-id="50a75-162">Si la taille des données du magasin de requêtes atteint la limite MAX_SIZE_MB, le magasin de requêtes fait passer automatiquement l'état de Lecture-écriture à Lecture seule et arrête la collecte de nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="50a75-162">If the data in the query store hits the MAX_SIZE_MB limit, the query store automatically changes the state from read-write to read-only and stops collecting new data.</span></span>

 <span data-ttu-id="50a75-163">INTERVAL_LENGTH_MINUTES détermine l’intervalle de temps auquel les données des statistiques d’exécution du runtime sont agrégées dans le magasin des requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-163">INTERVAL_LENGTH_MINUTES Determines the time interval at which runtime execution statistics data is aggregated into the query store.</span></span> <span data-ttu-id="50a75-164">Pour optimiser l'espace, les statistiques d'exécution du runtime du magasin de statistiques du runtime sont agrégées sur une période fixe.</span><span class="sxs-lookup"><span data-stu-id="50a75-164">To optimize for space usage, the runtime execution statistics in the Runtime Stats Store are aggregated over a fixed time window.</span></span> <span data-ttu-id="50a75-165">Cette période fixe est configurée via INTERVAL_LENGTH_MINUTES.</span><span class="sxs-lookup"><span data-stu-id="50a75-165">This fixed time window is configured via INTERVAL_LENGTH_MINUTES.</span></span>

 <span data-ttu-id="50a75-166">Interrogez l'affichage `sys.database_query_store_options` pour déterminer les options actuelles du magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-166">Query the `sys.database_query_store_options` view to determine the current options of the query store.</span></span>

 <span data-ttu-id="50a75-167">Pour plus d'informations sur la définition des options à l'aide d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] , consultez [Gestion des options](#OptionMgmt).</span><span class="sxs-lookup"><span data-stu-id="50a75-167">For more information about setting options by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, see [Option Management](#OptionMgmt).</span></span>

 

##  <a name="related-views-functions-and-procedures"></a><a name="Related"></a> <span data-ttu-id="50a75-168">Vues, fonctions et procédures associées</span><span class="sxs-lookup"><span data-stu-id="50a75-168">Related Views, Functions, and Procedures</span></span>
 <span data-ttu-id="50a75-169">Le magasin de requêtes peut être affiché et géré via [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] ou en utilisant les vues et les procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="50a75-169">The Query Store can be viewed and managed through [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] or by using the following views and procedures.</span></span>

-   [<span data-ttu-id="50a75-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-stmt-sql-handle-from-sql-stmt-transact-sql)

### <a name="query-store-catalog-views"></a><span data-ttu-id="50a75-171">Affichages catalogue de magasin de requête</span><span class="sxs-lookup"><span data-stu-id="50a75-171">Query Store Catalog Views</span></span>
 <span data-ttu-id="50a75-172">Sept affichages catalogue présentent des informations sur le magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-172">Seven catalog views present information about the Query Store.</span></span>

-   [<span data-ttu-id="50a75-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-query-store-options-transact-sql)

-   [<span data-ttu-id="50a75-174">sys.query_context_settings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-174">sys.query_context_settings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-context-settings-transact-sql)

-   [<span data-ttu-id="50a75-175">sys.query_store_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-175">sys.query_store_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-plan-transact-sql)

-   [<span data-ttu-id="50a75-176">sys.query_store_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-176">sys.query_store_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-transact-sql)

-   [<span data-ttu-id="50a75-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-text-transact-sql)

-   [<span data-ttu-id="50a75-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql)

-   [<span data-ttu-id="50a75-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-interval-transact-sql)

### <a name="query-store-stored-procedures"></a><span data-ttu-id="50a75-180">Procédures stockées du magasin de requêtes</span><span class="sxs-lookup"><span data-stu-id="50a75-180">Query Store Stored Procedures</span></span>
 <span data-ttu-id="50a75-181">Six procédures stockées configurent le magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="50a75-181">Six stored procedures configure the Query Store.</span></span>

-   [<span data-ttu-id="50a75-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-flush-db-transact-sql)

-   [<span data-ttu-id="50a75-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql)

-   [<span data-ttu-id="50a75-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql)

-   [<span data-ttu-id="50a75-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql)

-   [<span data-ttu-id="50a75-186">sp_query_store_remove_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-plan-transct-sql)

-   [<span data-ttu-id="50a75-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql)



##  <a name="key-usage-scenarios"></a><a name="Scenarios"></a> <span data-ttu-id="50a75-188">Principaux scénarios d’utilisation</span><span class="sxs-lookup"><span data-stu-id="50a75-188">Key Usage Scenarios</span></span>

###  <a name="option-management"></a><a name="OptionMgmt"></a> <span data-ttu-id="50a75-189">Gestion des options</span><span class="sxs-lookup"><span data-stu-id="50a75-189">Option Management</span></span>
 <span data-ttu-id="50a75-190">Cette section fournit des instructions sur la gestion de la fonctionnalité de magasin de requête proprement dite.</span><span class="sxs-lookup"><span data-stu-id="50a75-190">This section provides some guidelines on managing Query Store feature itself.</span></span>

 <span data-ttu-id="50a75-191">**Le magasin de requêtes est-il actuellement actif ?**</span><span class="sxs-lookup"><span data-stu-id="50a75-191">**Is Query Store currently active?**</span></span>

 <span data-ttu-id="50a75-192">Le magasin de requêtes stocke ses données dans la base de données utilisateur. C’est pourquoi sa taille est limitée (`MAX_STORAGE_SIZE_MB`).</span><span class="sxs-lookup"><span data-stu-id="50a75-192">Query Store stores its data inside the user database and that is why it has size limit (configured  with `MAX_STORAGE_SIZE_MB`).</span></span> <span data-ttu-id="50a75-193">Si les données du magasin de requêtes atteignent cette limite, le magasin de requêtes fait passer automatiquement l'état de Lecture-écriture à Lecture seule et arrête la collecte de nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="50a75-193">If data in Query Store hits that limit Query Store will automatically change state from read-write to read-only and stop collecting new data.</span></span>

 <span data-ttu-id="50a75-194">Exécutez le script suivant pour déterminer si le magasin de requêtes est actuellement actif et s'il collecte actuellement des statistiques d'exécution.</span><span class="sxs-lookup"><span data-stu-id="50a75-194">Execute the following script to determine if Query Store is currently active, and whether it is currently collects runtime stats or not.</span></span>

```
DECLARE @x nvarchar(100) = CAST(newid() AS nvarchar(100));
DECLARE @query nvarchar(max) = 
N'IF EXISTS
(
    SELECT * 
    FROM sys.query_store_query_text 
    WHERE query_sql_text LIKE ''%' + @x + N'%''
)
SELECT ''Query Store is active'' ;
ELSE SELECT ''Query Store is NOT active''' ;
EXEC sp_executesql @query;
```

 <span data-ttu-id="50a75-195">**Accès aux options du magasin de requêtes**</span><span class="sxs-lookup"><span data-stu-id="50a75-195">**Get Query Store options**</span></span>

 <span data-ttu-id="50a75-196">Pour trouver des informations détaillées sur l'état du magasin de requêtes, exécutez ce qui suit dans une base de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50a75-196">To find out detailed information about Query Store status, execute following in a user database.</span></span>

```
SELECT * FROM sys.database_query_store_options;
```

 <span data-ttu-id="50a75-197">**Définition de l’intervalle du magasin de requêtes**</span><span class="sxs-lookup"><span data-stu-id="50a75-197">**Setting Query Store interval**</span></span>

 <span data-ttu-id="50a75-198">Vous pouvez remplacer l'intervalle d'agrégation des statistiques d'exécution de requête (la valeur par défaut est 60 minutes).</span><span class="sxs-lookup"><span data-stu-id="50a75-198">You can override interval for aggregating query runtime statistics (default is 60 minutes).</span></span>

```

      USE master;
GO

ALTER DATABASE <database_name> 
SET QUERY_STORE (INTERVAL_LENGTH_MINUTES = 15);
```

 <span data-ttu-id="50a75-199">Notez que les valeurs arbitraires ne sont pas autorisées. Vous devez utiliser une des valeurs suivantes : 1, 5, 10, 15, 30 et 60.</span><span class="sxs-lookup"><span data-stu-id="50a75-199">Note that arbitrary values are not allowed - you should use one of the following: 1, 5, 10, 15, 30 and 60.</span></span>

 <span data-ttu-id="50a75-200">La nouvelle valeur de l'intervalle est exposée via l'affichage `sys.database_query_store_options`.</span><span class="sxs-lookup"><span data-stu-id="50a75-200">New value for interval is exposed through `sys.database_query_store_options` view.</span></span>

 <span data-ttu-id="50a75-201">Si le stockage du magasin de requêtes est saturé, utilisez l'instruction suivante pour l’étendre.</span><span class="sxs-lookup"><span data-stu-id="50a75-201">If the Query Store storage is full use the following statement to extend the storage.</span></span>

```
ALTER DATABASE <database_name> 
SET QUERY_STORE (MAX_STORAGE_SIZE_MB = <new_size>);
```

 <span data-ttu-id="50a75-202">**Définition de toutes les options du magasin de requêtes**</span><span class="sxs-lookup"><span data-stu-id="50a75-202">**Set all Query Store options**</span></span>

 <span data-ttu-id="50a75-203">Vous pouvez définir simultanément plusieurs options de magasin de requêtes avec l'instruction ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="50a75-203">You can set multiple Query Store options at once with a single ALTER DATABASE statement.</span></span>

```
ALTER DATABASE <database name> 
SET QUERY_STORE (
    OPERATION_MODE = READ_WRITE,
    CLEANUP_POLICY = 
    (STALE_QUERY_THRESHOLD_DAYS = 30),
    DATA_FLUSH_INTERVAL_SECONDS = 3000,
    MAX_STORAGE_SIZE_MB = 500,
    INTERVAL_LENGTH_MINUTES = 15
);
```

 <span data-ttu-id="50a75-204">**Nettoyage de l’espace**</span><span class="sxs-lookup"><span data-stu-id="50a75-204">**Cleaning up the space**</span></span>

 <span data-ttu-id="50a75-205">Les tables internes du magasin de requêtes sont créées dans le groupe de fichiers PRIMARY lors de la création de la base de données. Cette configuration ne peut pas être modifiée ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="50a75-205">Query Store internal tables are created in the PRIMARY filegroup during database creation and that configuration cannot be changed later.</span></span> <span data-ttu-id="50a75-206">Si vous manquez d'espace, vous pouvez effacer les anciennes données du magasin de requêtes à l'aide de l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="50a75-206">If you are running out of space you might want to clear older Query Store data by using the following statement.</span></span>

```
ALTER DATABASE <db_name> SET QUERY_STORE CLEAR;
```

 <span data-ttu-id="50a75-207">Vous pouvez également effacer uniquement les données de requête ad hoc, car elles sont moins pertinentes pour les optimisations de requête et l'analyse du plan, mais utilisent autant d'espace.</span><span class="sxs-lookup"><span data-stu-id="50a75-207">Alternatively, you might want to clear up only ad-hoc query data, since it is less relevant for query optimizations and plan analysis but takes up just as much space.</span></span>

 <span data-ttu-id="50a75-208">**Supprimer des requêtes ad-hoc** Cette opération supprime les requêtes qui ont été exécutées une seule fois et qui datent de plus de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="50a75-208">**Delete ad-hoc queries** This deletes the queries that were only executed only once and that are more than 24 hours old.</span></span>

```
DECLARE @id int
DECLARE adhoc_queries_cursor CURSOR 
FOR 
SELECT q.query_id
FROM sys.query_store_query_text AS qt
JOIN sys.query_store_query AS q 
    ON q.query_text_id = qt.query_text_id
JOIN sys.query_store_plan AS p 
    ON p.query_id = q.query_id
JOIN sys.query_store_runtime_stats AS rs 
    ON rs.plan_id = p.plan_id
GROUP BY q.query_id
HAVING SUM(rs.count_executions) < 2 
AND MAX(rs.last_execution_time) < DATEADD (hour, -24, GETUTCDATE())
ORDER BY q.query_id ;

OPEN adhoc_queries_cursor ;
FETCH NEXT FROM adhoc_queries_cursor INTO @id;
WHILE @@fetch_status = 0
    BEGIN 
        PRINT @id
        EXEC sp_query_store_remove_query @id
        FETCH NEXT FROM adhoc_queries_cursor INTO @id
    END 
CLOSE adhoc_queries_cursor ;
DEALLOCATE adhoc_queries_cursor;
```

 <span data-ttu-id="50a75-209">Vous pouvez définir votre propre procédure avec une logique différente pour effacer les données qui ne sont plus importantes pour vous.</span><span class="sxs-lookup"><span data-stu-id="50a75-209">You can define your own procedure with different logic for clearing up the data that is no longer important for you.</span></span>

 <span data-ttu-id="50a75-210">L'exemple ci-dessus utilise la procédure stockée étendue `sp_query_store_remove_query` pour supprimer les données inutiles.</span><span class="sxs-lookup"><span data-stu-id="50a75-210">The example above uses the `sp_query_store_remove_query` extended stored procedure for removing unnecessary data.</span></span> <span data-ttu-id="50a75-211">Vous pouvez également utiliser deux autres procédures.</span><span class="sxs-lookup"><span data-stu-id="50a75-211">You can also use two other procedures.</span></span>

-   <span data-ttu-id="50a75-212">`sp_query_store_reset_exec_stats`-effacer les statistiques d’exécution pour un plan donné.</span><span class="sxs-lookup"><span data-stu-id="50a75-212">`sp_query_store_reset_exec_stats` - clear runtime statistics for a given plan.</span></span>

-   <span data-ttu-id="50a75-213">`sp_query_store_remove_plan`-supprime un seul plan.</span><span class="sxs-lookup"><span data-stu-id="50a75-213">`sp_query_store_remove_plan` - removes a single plan.</span></span>



###  <a name="performance-auditing-and-troubleshooting"></a><a name="Peformance"></a> <span data-ttu-id="50a75-214">Audit et résolution des problèmes de performances</span><span class="sxs-lookup"><span data-stu-id="50a75-214">Performance Auditing and Troubleshooting</span></span>
 <span data-ttu-id="50a75-215">Étant donné que le magasin de requêtes conserve l'historique de compilation et les mesures d'exécution de l'ensemble des exécutions de requête, il permet de répondre facilement aux nombreuses questions que vous pouvez vous poser concernant votre charge de travail.</span><span class="sxs-lookup"><span data-stu-id="50a75-215">Because Query Store keeps history of compilation and runtime metrics throughout query executions there are many different questions you can easily answer with regards to your workload.</span></span>

 <span data-ttu-id="50a75-216">***N* dernières requêtes exécutées sur la base de données.**</span><span class="sxs-lookup"><span data-stu-id="50a75-216">**Last *n* queries executed on the database.**</span></span>

```
SELECT TOP 10 qt.query_sql_text, q.query_id, 
    qt.query_text_id, p.plan_id, rs.last_execution_time
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
ORDER BY rs.last_execution_time DESC;
```

 <span data-ttu-id="50a75-217">**Nombre d’exécutions pour chaque requête.**</span><span class="sxs-lookup"><span data-stu-id="50a75-217">**Number of executions for each query.**</span></span>

```
SELECT q.query_id, qt.query_text_id, qt.query_sql_text, 
    SUM(rs.count_executions) AS total_execution_count
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
GROUP BY q.query_id, qt.query_text_id, qt.query_sql_text
ORDER BY total_execution_count DESC;
```

 <span data-ttu-id="50a75-218">**Nombre de requêtes avec la durée moyenne d’exécution la plus longue au cours de la dernière heure.**</span><span class="sxs-lookup"><span data-stu-id="50a75-218">**The number of queries with the longest average execution time within last hour.**</span></span>

```
SELECT TOP 10 rs.avg_duration, qt.query_sql_text, q.query_id,
    qt.query_text_id, p.plan_id, GETUTCDATE() AS CurrentUTCTime, 
    rs.last_execution_time 
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
WHERE rs.last_execution_time > DATEADD(hour, -1, GETUTCDATE())
ORDER BY rs.avg_duration DESC;
```

 <span data-ttu-id="50a75-219">**Nombre de requêtes ayant la plus grande moyenne de lectures d’e/s physiques au cours des dernières 24 heures, avec le nombre moyen de lignes et le nombre d’exécutions correspondants.**</span><span class="sxs-lookup"><span data-stu-id="50a75-219">**The number of queries that had the biggest average physical IO reads in last 24 hours, with corresponding average row count and execution count.**</span></span>

```
SELECT TOP 10 rs.avg_physical_io_reads, qt.query_sql_text, 
    q.query_id, qt.query_text_id, p.plan_id, rs.runtime_stats_id, 
    rsi.start_time, rsi.end_time, rs.avg_rowcount, rs.count_executions
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi 
    ON rsi.runtime_stats_interval_id = rs.runtime_stats_interval_id
WHERE rsi.start_time >= DATEADD(hour, -24, GETUTCDATE()) 
ORDER BY rs.avg_physical_io_reads DESC;
```

 <span data-ttu-id="50a75-220">**Requêtes avec plusieurs plans.**</span><span class="sxs-lookup"><span data-stu-id="50a75-220">**Queries with multiple plans.**</span></span> <span data-ttu-id="50a75-221">Ces requêtes sont particulièrement intéressantes, car elles sont adaptées aux régressions dues à un changement de plan.</span><span class="sxs-lookup"><span data-stu-id="50a75-221">These queries are especially interesting because they are candidates for regressions due to plan choice change.</span></span> <span data-ttu-id="50a75-222">La requête suivante identifie ces requêtes, ainsi que tous les plans :</span><span class="sxs-lookup"><span data-stu-id="50a75-222">The following query identifies these queries along with all plans:</span></span>

```
WITH Query_MultPlans
AS
(
    SELECT COUNT(*) AS cnt, q.query_id 
    FROM sys.query_store_query_text AS qt
    JOIN sys.query_store_query AS q
        ON qt.query_text_id = q.query_text_id
    JOIN sys.query_store_plan AS p
        ON p.query_id = q.query_id
    GROUP BY q.query_id
    HAVING COUNT(distinct plan_id) > 1
)

SELECT q.query_id, object_name(object_id) AS ContainingObject, query_sql_text,
plan_id, p.query_plan AS plan_xml,
p.last_compile_start_time, p.last_execution_time
FROM Query_MultPlans AS qm
JOIN sys.query_store_query AS q
    ON qm.query_id = q.query_id
JOIN sys.query_store_plan AS p
    ON q.query_id = p.query_id
JOIN sys.query_store_query_text qt 
    ON qt.query_text_id = q.query_text_id
ORDER BY query_id, plan_id;
```

 <span data-ttu-id="50a75-223">**Requêtes ayant récemment régressé les performances (en comparant un point dans le temps différent).**</span><span class="sxs-lookup"><span data-stu-id="50a75-223">**Queries that recently regressed in performance (comparing different point in time).**</span></span> <span data-ttu-id="50a75-224">L'exemple de requête suivant retourne toutes les requêtes dont le temps d'exécution a doublé au cours des dernières 48 heures suite à un changement de plan.</span><span class="sxs-lookup"><span data-stu-id="50a75-224">The following query example returns all queries for which execution time doubled in last 48 hours due to a plan choice change.</span></span> <span data-ttu-id="50a75-225">La requête compare tous les intervalles de statistiques d'exécution côte à côte.</span><span class="sxs-lookup"><span data-stu-id="50a75-225">Query compares all runtime stat intervals side by side.</span></span>

```
SELECT 
    qt.query_sql_text, 
    q.query_id, 
    qt.query_text_id, 
    rs1.runtime_stats_id AS runtime_stats_id_1,
    rsi1.start_time AS interval_1, 
    p1.plan_id AS plan_1, 
    rs1.avg_duration AS avg_duration_1, 
    rs2.avg_duration AS avg_duration_2,
    p2.plan_id AS plan_2, 
    rsi2.start_time AS interval_2, 
    rs2.runtime_stats_id AS runtime_stats_id_2
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p1 
    ON q.query_id = p1.query_id 
JOIN sys.query_store_runtime_stats AS rs1 
    ON p1.plan_id = rs1.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi1 
    ON rsi1.runtime_stats_interval_id = rs1.runtime_stats_interval_id 
JOIN sys.query_store_plan AS p2 
    ON q.query_id = p2.query_id 
JOIN sys.query_store_runtime_stats AS rs2 
    ON p2.plan_id = rs2.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi2 
    ON rsi2.runtime_stats_interval_id = rs2.runtime_stats_interval_id
WHERE rsi1.start_time > DATEADD(hour, -48, GETUTCDATE()) 
    AND rsi2.start_time > rsi1.start_time 
    AND p1.plan_id <> p2.plan_id
    AND rs2.avg_duration > 2*rs1.avg_duration
ORDER BY q.query_id, rsi1.start_time, rsi2.start_time;
```

 <span data-ttu-id="50a75-226">Si vous souhaitez voir toutes les régressions de performances (pas uniquement celles liées au changement de plan), supprimez simplement la condition `AND p1.plan_id <> p2.plan_id` de la requête précédente.</span><span class="sxs-lookup"><span data-stu-id="50a75-226">If you want to see performance all regressions (not only those related to plan choice change) than just remove condition `AND p1.plan_id <> p2.plan_id` from the previous query.</span></span>

 <span data-ttu-id="50a75-227">**Les requêtes qui ont récemment régressé les performances (en comparant les exécutions récentes et historiques).**</span><span class="sxs-lookup"><span data-stu-id="50a75-227">**Queries that recently regressed in performance (comparing recent vs. history execution).**</span></span> <span data-ttu-id="50a75-228">La requête suivante compare l'exécution des requête en fonction des périodes d'exécution.</span><span class="sxs-lookup"><span data-stu-id="50a75-228">The next query compares query execution based periods of execution.</span></span> <span data-ttu-id="50a75-229">Dans cet exemple particulier, la requête compare l'exécution lors d'une période récente (1 heure) et l'exécution lors d'une période historique (la veille), puis identifie celles qui ont introduit une charge de travail supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="50a75-229">In this particular example the query compares execution in recent period (1 hour) vs. history period (last day) and identifies those that introduced additional_duration_workload.</span></span> <span data-ttu-id="50a75-230">Cette mesure est calculée comme suit : différence entre la moyenne des exécutions récentes et la moyenne des exécutions historiques, multipliée par le nombre d'exécutions récentes.</span><span class="sxs-lookup"><span data-stu-id="50a75-230">This metrics is calculated as a difference between recent average execution and history average execution multiplied by the number of recent executions.</span></span> <span data-ttu-id="50a75-231">Elle représente en fait la durée supplémentaire introduite dans les exécutions récentes en comparaison avec les exécutions historiques :</span><span class="sxs-lookup"><span data-stu-id="50a75-231">It actually represents how much of additional duration recent executions introduced compared to history:</span></span>

```
--- "Recent" workload - last 1 hour
DECLARE @recent_start_time datetimeoffset;
DECLARE @recent_end_time datetimeoffset;
SET @recent_start_time = DATEADD(hour, -1, SYSUTCDATETIME());
SET @recent_end_time = SYSUTCDATETIME();

--- "History" workload
DECLARE @history_start_time datetimeoffset;
DECLARE @history_end_time datetimeoffset;
SET @history_start_time = DATEADD(hour, -24, SYSUTCDATETIME());
SET @history_end_time = SYSUTCDATETIME();

WITH
hist AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
     FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @history_start_time AND rs.last_execution_time < @history_end_time)
        OR (rs.first_execution_time <= @history_start_time AND rs.last_execution_time > @history_start_time)
        OR (rs.first_execution_time <= @history_end_time AND rs.last_execution_time > @history_end_time)
    GROUP BY p.query_id
),
recent AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
    FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @recent_start_time AND rs.last_execution_time < @recent_end_time)
        OR (rs.first_execution_time <= @recent_start_time AND rs.last_execution_time > @recent_start_time)
        OR (rs.first_execution_time <= @recent_end_time AND rs.last_execution_time > @recent_end_time)
    GROUP BY p.query_id
)
SELECT 
    results.query_id query_id,
    results.query_text query_text,
    results.additional_duration_workload additional_duration_workload,
    results.total_duration_recent total_duration_recent,
    results.total_duration_hist total_duration_hist,
    ISNULL(results.count_executions_recent, 0) count_executions_recent,
    ISNULL(results.count_executions_hist, 0) count_executions_hist 
FROM
(
    SELECT
        hist.query_id query_id,
        qt.query_sql_text query_text,
        ROUND(CONVERT(float, recent.total_duration/recent.count_executions-hist.total_duration/hist.count_executions)*(recent.count_executions), 2) AS additional_duration_workload,
        ROUND(recent.total_duration, 2) total_duration_recent, 
        ROUND(hist.total_duration, 2) total_duration_hist,
        recent.count_executions count_executions_recent,
        hist.count_executions count_executions_hist   
    FROM hist 
        JOIN recent 
            ON hist.query_id = recent.query_id 
        JOIN sys.query_store_query AS q 
            ON q.query_id = hist.query_id
        JOIN sys.query_store_query_text AS qt 
            ON q.query_text_id = qt.query_text_id    
) AS results
WHERE additional_duration_workload > 0
ORDER BY additional_duration_workload DESC
OPTION (MERGE JOIN);
```



###  <a name="maintaining-query-performance-stability"></a><a name="Stability"></a><span data-ttu-id="50a75-232">Maintien de la stabilité des performances des requêtes</span><span class="sxs-lookup"><span data-stu-id="50a75-232">Maintaining Query Performance Stability</span></span>
 <span data-ttu-id="50a75-233">Pour les requêtes exécutées plusieurs fois, vous pouvez remarquer que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a utilisé différents plans, ce qui a entraîné une utilisation des ressources et une durée différentes.</span><span class="sxs-lookup"><span data-stu-id="50a75-233">For queries that are executed multiple times you may notice that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] used different plans which resulted in different resource utilization and duration.</span></span> <span data-ttu-id="50a75-234">Le magasin de requêtes permet de facilement détecter le moment où les performances des requêtes ont régressé et de déterminer le plan optimal dans un délai donné.</span><span class="sxs-lookup"><span data-stu-id="50a75-234">With Query Store you can easily detect when the query performance regressed and determine the optimal plan within a period of interest.</span></span> <span data-ttu-id="50a75-235">Ensuite, vous pouvez forcer l'application de ce plan optimal pour l'exécution des requêtes ultérieures.</span><span class="sxs-lookup"><span data-stu-id="50a75-235">Then you can force that optimal plan for future query execution.</span></span>

 <span data-ttu-id="50a75-236">Vous pouvez également identifier les performances de requêtes incohérentes avec des paramètres (définis manuellement ou automatiquement).</span><span class="sxs-lookup"><span data-stu-id="50a75-236">You can also identify inconsistent query performance for a query with parameters (either auto- parameterized or manually parameterized).</span></span> <span data-ttu-id="50a75-237">Parmi les différents plans, vous pouvez identifier le plan qui est suffisamment rapide et optimal pour la totalité ou la plupart des valeurs de paramètre et forcer ce plan, en maintenant ainsi des performances prévisibles pour l'ensemble plus large de scénarios utilisateur.</span><span class="sxs-lookup"><span data-stu-id="50a75-237">Among different plans you can identify plan which is fast and optimal enough for all or most of the parameter values and force that plan; keeping predictable performance for the wider set of user scenarios.</span></span>

 <span data-ttu-id="50a75-238">**Forcer un plan pour une requête (appliquer une stratégie de forçage).**</span><span class="sxs-lookup"><span data-stu-id="50a75-238">**Force or a plan for a query (apply forcing policy).**</span></span> <span data-ttu-id="50a75-239">Lorsqu'un plan est forcé pour une requête donnée, chaque fois qu'une requête est exécutée, elle l'est avec le plan forcé.</span><span class="sxs-lookup"><span data-stu-id="50a75-239">When a plan is forced for a certain query, every time a query comes to execution it will be executed with the plan that is forced.</span></span>

```
EXEC sp_query_store_force_plan @query_id = 48, @plan_id = 49;
```

 <span data-ttu-id="50a75-240">Lorsque vous utilisez `sp_query_store_force_plan`, vous pouvez uniquement forcer des plans qui ont été enregistrés par le magasin de requêtes en tant que plan pour cette requête.</span><span class="sxs-lookup"><span data-stu-id="50a75-240">When using `sp_query_store_force_plan` you can only force plans that were recorded by Query Store as a plan for that query.</span></span> <span data-ttu-id="50a75-241">En d'autres termes, les plans disponibles pour une requête sont uniquement ceux qui ont déjà été utilisés pour exécuter Q1 lorsque le magasin de requêtes était actif.</span><span class="sxs-lookup"><span data-stu-id="50a75-241">In other words, the only plans available for a query are those that were already used to execute Q1 while Query Store was active.</span></span>

 <span data-ttu-id="50a75-242">**Supprimer le forçage de plan pour une requête.**</span><span class="sxs-lookup"><span data-stu-id="50a75-242">**Remove plan forcing for a query.**</span></span> <span data-ttu-id="50a75-243">Pour vous appuyer à nouveau sur l' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] optimiseur de requête pour calculer le plan de requête optimal, utilisez `sp_query_store_unforce_plan` pour annuler l’application du plan sélectionné pour la requête.</span><span class="sxs-lookup"><span data-stu-id="50a75-243">To rely again on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] query optimizer to calculate the optimal query plan, use `sp_query_store_unforce_plan` to unforce the plan that was selected for the query.</span></span>

```
EXEC sp_query_store_unforce_plan @query_id = 48, @plan_id = 49;
```



## <a name="see-also"></a><span data-ttu-id="50a75-244">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50a75-244">See Also</span></span>
 <span data-ttu-id="50a75-245">[Surveiller et régler les performances de performance outils de](../performance/monitor-and-tune-for-performance.md) [surveillance et de paramétrage](../performance/performance-monitoring-and-tuning-tools.md) [ouvrir le moniteur d’activité &#40;SQL Server Management Studio](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) le [moniteur d’activité](../performance-monitor/activity-monitor.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="50a75-245">[Monitor and Tune for Performance](../performance/monitor-and-tune-for-performance.md) [Performance Monitoring and Tuning Tools](../performance/performance-monitoring-and-tuning-tools.md) [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [Activity Monitor](../performance-monitor/activity-monitor.md)</span></span>


