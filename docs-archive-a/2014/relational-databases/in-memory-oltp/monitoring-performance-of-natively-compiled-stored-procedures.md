---
title: Surveillance des performances des procédures stockées compilées en mode natif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 55548cb2-77a8-4953-8b5a-f2778a4f13cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d14d27cdc20c0f090c7a030efe05cfce4842f437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709428"
---
# <a name="monitoring-performance-of-natively-compiled-stored-procedures"></a><span data-ttu-id="12946-102">Surveillance des performances des procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="12946-102">Monitoring Performance of Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="12946-103">Cette rubrique explique comment surveiller les performances des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="12946-103">This topic discusses how you can monitor the performance of natively compiled stored procedures</span></span>  
  
## <a name="using-extended-events"></a><span data-ttu-id="12946-104">Utilisation des événements étendus</span><span class="sxs-lookup"><span data-stu-id="12946-104">Using Extended Events</span></span>  
 <span data-ttu-id="12946-105">Utilisez l'événement étendu `sp_statement_completed` pour tracer l'exécution d'une requête.</span><span class="sxs-lookup"><span data-stu-id="12946-105">Use the `sp_statement_completed` extended event to trace execution of a query.</span></span> <span data-ttu-id="12946-106">Créez une session d'événements étendus avec cet événement, éventuellement avec un filtre sur object_id pour une procédure stockée compilée en mode natif. L'événement étendu est déclenché après l'exécution de chaque requête.</span><span class="sxs-lookup"><span data-stu-id="12946-106">Create an extended event session with this event, optionally with a filter on object_id for a particular natively compiled stored procedure, The extended event is raised after the execution of each query.</span></span> <span data-ttu-id="12946-107">Le temps processeur et la durée signalés par l'événement étendu indiquent l'UC utilisée par la requête et le temps d'exécution.</span><span class="sxs-lookup"><span data-stu-id="12946-107">The CPU time and duration reported by the extended event indicate how much CPU the query used and the execution time.</span></span> <span data-ttu-id="12946-108">Une procédure stockée compilée en mode natif qui utilise beaucoup de temps processeur peut rencontrer des problèmes de performances.</span><span class="sxs-lookup"><span data-stu-id="12946-108">A natively compiled stored procedure that uses a lot of CPU time may have performance problems.</span></span>  
  
 <span data-ttu-id="12946-109">`line_number` et `object_id` dans l'événement étendu peuvent être utilisés pour analyser la requête.</span><span class="sxs-lookup"><span data-stu-id="12946-109">`line_number`, along with the `object_id` in the extended event can be used to investigate the query.</span></span> <span data-ttu-id="12946-110">La requête suivante peut être utilisée pour extraire la définition de procédure.</span><span class="sxs-lookup"><span data-stu-id="12946-110">The following query can be used to retrieve the procedure definition.</span></span> <span data-ttu-id="12946-111">Le numéro de ligne peut être utilisé pour identifier la requête dans la définition :</span><span class="sxs-lookup"><span data-stu-id="12946-111">The line number can be used to identify the query within the definition:</span></span>  
  
```sql  
select [definition] from sys.sql_modules where object_id=object_id  
```  
  
 <span data-ttu-id="12946-112">Pour plus d’informations sur l' `sp_statement_completed` événement étendu, consultez [Comment récupérer l’instruction qui a provoqué un événement](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span><span class="sxs-lookup"><span data-stu-id="12946-112">For more information about the `sp_statement_completed` extended event, see [How to retrieve the statement that caused an event](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span></span>  
  
## <a name="using-data-management-views"></a><span data-ttu-id="12946-113">Utilisation des vues de gestion des données</span><span class="sxs-lookup"><span data-stu-id="12946-113">Using Data Management Views</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="12946-114">prend en charge la collecte de statistiques d'exécution des procédures stockées compilées en mode natif, au niveau de la procédure et au niveau de la requête.</span><span class="sxs-lookup"><span data-stu-id="12946-114">supports collecting execution statistics for natively compiled stored procedures, both on the procedure level and the query level.</span></span> <span data-ttu-id="12946-115">Le collecte des statistiques d'exécution n'est pas activée par défaut en raison de l'impact sur les performances.</span><span class="sxs-lookup"><span data-stu-id="12946-115">Collecting execution statistics is not enabled by default due to performance impact.</span></span>  
  
 <span data-ttu-id="12946-116">Vous pouvez activer et désactiver la collecte de statistiques sur les procédures stockées compilées en mode natif par le biais de [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12946-116">You can enable and disable statistics collection on natively compiled stored procedures using [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="12946-117">Quand la collecte de statistiques est activée avec [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), vous pouvez utiliser [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) pour surveiller les performances d’une procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="12946-117">When statistics collection is enabled with [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), you can use [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="12946-118">Quand la collecte de statistiques est activée avec [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), vous pouvez utiliser [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) pour surveiller les performances d’une procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="12946-118">When statistics collection is enabled with [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), you can use [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="12946-119">Au démarrage de la collection, activez la collection de statistiques.</span><span class="sxs-lookup"><span data-stu-id="12946-119">At the start of collection, enable statistics collection.</span></span> <span data-ttu-id="12946-120">Ensuite, exécutez la procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="12946-120">Then, execute the natively compiled stored procedure.</span></span> <span data-ttu-id="12946-121">À l'issue de la collection, désactivez la collection de statistiques.</span><span class="sxs-lookup"><span data-stu-id="12946-121">At the end of collection, disable statistics collection.</span></span> <span data-ttu-id="12946-122">Ensuite, analysez les statistiques d'exécution retournées par les vues de gestion dynamique.</span><span class="sxs-lookup"><span data-stu-id="12946-122">Then, analyze the execution statistics returned by the DMVs.</span></span>  
  
 <span data-ttu-id="12946-123">Une fois recueillies, les statistiques d’exécution des procédures stockées compilées en mode natif peuvent être interrogées pour une procédure à l’aide de [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) et pour les requêtes à l’aide de [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12946-123">After you collect statistics, the execution statistics for natively compiled stored procedures can be queried for a procedure with [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql), and for queries with [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12946-124">Pour les procédures stockées compilées en mode natif avec collection de statistiques activée, le temps de travail est collecté en millisecondes.</span><span class="sxs-lookup"><span data-stu-id="12946-124">For natively compiled stored procedures when statistics collection is enabled, worker time is collected in milliseconds.</span></span> <span data-ttu-id="12946-125">Si la requête s'exécute en moins d'une milliseconde, la valeur est 0.</span><span class="sxs-lookup"><span data-stu-id="12946-125">If the query executes in less than a millisecond, the value will be 0.</span></span> <span data-ttu-id="12946-126">Pour les procédures stockées compilées en mode natif, **total_worker_time** peut être inexact si plusieurs exécutions sont réalisées en moins d’une milliseconde.</span><span class="sxs-lookup"><span data-stu-id="12946-126">For natively compiled stored procedures, **total_worker_time** may not be accurate if many executions take less than 1 millisecond.</span></span>  
  
 <span data-ttu-id="12946-127">La requête suivante retourne les noms de procédure et les statistiques d'exécution des procédures stockées compilées en mode natif dans la base de données active, après collection de statistiques :</span><span class="sxs-lookup"><span data-stu-id="12946-127">The following query returns the procedure names and execution statistics for natively compiled stored procedures in the current database, after statistics collection:</span></span>  
  
```sql  
select object_id,  
       object_name(object_id) as 'object name',  
       cached_time,  
       last_execution_time,  
       execution_count,  
       total_worker_time,  
       last_worker_time,  
       min_worker_time,  
       max_worker_time,  
       total_elapsed_time,  
       last_elapsed_time,  
       min_elapsed_time,  
       max_elapsed_time   
from sys.dm_exec_procedure_stats  
where database_id=db_id() and object_id in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by total_worker_time desc  
```  
  
 <span data-ttu-id="12946-128">La requête suivante retourne le texte des requêtes ainsi que les statistiques d'exécution de toutes les requêtes dans les procédures stockées compilées en mode natif dans la base de données active pour laquelle les statistiques ont été collectées, triées par temps total de travail, dans l'ordre décroissant :</span><span class="sxs-lookup"><span data-stu-id="12946-128">The following query returns the query text as well as execution statistics for all queries in natively compiled stored procedures in the current database for which statistics have been collected, ordered by total worker time, in descending order:</span></span>  
  
```sql  
select st.objectid,   
       object_name(st.objectid) as 'object name',   
       SUBSTRING(st.text, (qs.statement_start_offset/2) + 1, ((qs.statement_end_offset-qs.statement_start_offset)/2) + 1) as 'query text',   
       qs.creation_time,  
       qs.last_execution_time,  
       qs.execution_count,  
       qs.total_worker_time,  
       qs.last_worker_time,  
       qs.min_worker_time,  
       qs.max_worker_time,  
       qs.total_elapsed_time,  
       qs.last_elapsed_time,  
       qs.min_elapsed_time,  
       qs.max_elapsed_time  
from sys.dm_exec_query_stats qs cross apply sys.dm_exec_sql_text(sql_handle) st  
where  st.dbid=db_id() and st.objectid in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by qs.total_worker_time desc  
```  
  
 <span data-ttu-id="12946-129">Les procédures stockées compilées en mode natif prennent en charge SHOWPLAN_XML (plan d'exécution de requêtes).</span><span class="sxs-lookup"><span data-stu-id="12946-129">Natively compiled stored procedures support SHOWPLAN_XML (estimated execution plan).</span></span> <span data-ttu-id="12946-130">Le plan d'exécution estimé permet d'inspecter le plan de requête, afin de trouver des problèmes de plan erroné.</span><span class="sxs-lookup"><span data-stu-id="12946-130">The estimated execution plan can be used to inspect the query plan, to find any bad plan issues.</span></span> <span data-ttu-id="12946-131">Causes courantes de plans incorrects :</span><span class="sxs-lookup"><span data-stu-id="12946-131">Common reasons for bad plans are:</span></span>  
  
-   <span data-ttu-id="12946-132">Les statistiques n'ont pas été mises à jour avant de créer la procédure.</span><span class="sxs-lookup"><span data-stu-id="12946-132">Stats were not updated before the procedure was created.</span></span>  
  
-   <span data-ttu-id="12946-133">Index manquants</span><span class="sxs-lookup"><span data-stu-id="12946-133">Missing indexes</span></span>  
  
 <span data-ttu-id="12946-134">Le XML du plan d'exécution de requêtes est obtenu en exécutant l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)]suivante :</span><span class="sxs-lookup"><span data-stu-id="12946-134">Showplan XML is obtained by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```sql  
SET SHOWPLAN_XML ON  
GO  
EXEC my_proc   
GO  
SET SHOWPLAN_XML OFF  
GO  
```  
  
 <span data-ttu-id="12946-135">Ou, dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], sélectionnez le nom de la procédure et cliquez sur **Afficher le plan d'exécution estimé**.</span><span class="sxs-lookup"><span data-stu-id="12946-135">Alternatively, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the procedure name and click **Display Estimated Execution Plan**.</span></span>  
  
 <span data-ttu-id="12946-136">Le plan d'exécution estimé pour les procédures stockées compilées en mode natif affiche les opérateurs de requête et les expressions des requêtes dans la procédure.</span><span class="sxs-lookup"><span data-stu-id="12946-136">The estimated execution plan for natively compiled stored procedures shows the query operators and expressions for the queries in the procedure.</span></span> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="12946-137">ne prend pas en charge tous les attributs SHOWPLAN_XML des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="12946-137">does not support all SHOWPLAN_XML attributes for natively compiled stored procedures.</span></span> <span data-ttu-id="12946-138">Par exemple, les attributs liés au coût de l'optimiseur de requête ne font pas partie de SHOWPLAN_XML pour la procédure.</span><span class="sxs-lookup"><span data-stu-id="12946-138">For example, attributes related to query optimizer costing are not part of the SHOWPLAN_XML for the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12946-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12946-139">See Also</span></span>  
 [<span data-ttu-id="12946-140">Procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="12946-140">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
