---
title: Surveiller SQL Server sauvegarde gérée sur Azure | Microsoft Docs
description: Cet article décrit les outils que vous pouvez utiliser pour déterminer l’intégrité globale des sauvegardes à l’aide d’SQL Server sauvegarde gérée sur Azure et identifier les erreurs.
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: cfb9e431-7d4c-457c-b090-6f2528b2f315
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: baec99e63c70befde0cfce76e42dd6202ebc0bad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613624"
---
# <a name="monitor-sql-server-managed-backup-to-azure"></a><span data-ttu-id="f900c-103">Surveiller la sauvegarde managée de SQL Server vers Azure</span><span class="sxs-lookup"><span data-stu-id="f900c-103">Monitor SQL Server Managed Backup to Azure</span></span>
  <span data-ttu-id="f900c-104">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] possède des mesures intégrées permettant d'identifier les problèmes et les erreurs pendant les processus de sauvegarde et les corrige lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="f900c-104">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] has built-in measures to identify problems and errors during backup processes and remedy with corrective action when possible.</span></span>  <span data-ttu-id="f900c-105">Toutefois, dans certaines situations, l'intervention de l'utilisateur est requise.</span><span class="sxs-lookup"><span data-stu-id="f900c-105">However there are certain situations where user intervention is required.</span></span> <span data-ttu-id="f900c-106">Cette rubrique décrit les outils que vous pouvez utiliser pour déterminer l'état d'intégrité général des sauvegardes, et identifier les erreurs qui doivent être corrigées.</span><span class="sxs-lookup"><span data-stu-id="f900c-106">This topic describes the tools that you can use to determine the overall health status of backups, and identify any errors that need to be addressed.</span></span>  
  
## <a name="overview-of-ss_smartbackup-built-in-debugging"></a><span data-ttu-id="f900c-107">Présentation du débogage intégré de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f900c-107">Overview of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Built-in Debugging</span></span>  
 <span data-ttu-id="f900c-108">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] vérifie périodiquement les sauvegardes planifiées et tente de replanifier toute sauvegarde ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="f900c-108">The [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] periodically reviews scheduled backups and attempts to reschedule any failed backups.</span></span> <span data-ttu-id="f900c-109">Elle interroge régulièrement le compte de stockage pour identifier une rupture des séquences de journaux de transactions affectant la récupérabilité de la base de données et planifie de nouvelles sauvegardes en conséquence.</span><span class="sxs-lookup"><span data-stu-id="f900c-109">It polls the storage account periodically to identify breaks in log chains affecting recoverability of the database, and schedules new backups accordingly.</span></span> <span data-ttu-id="f900c-110">Il prend également en compte les stratégies de limitation Azure et met en place des mécanismes pour gérer plusieurs sauvegardes de base de données.</span><span class="sxs-lookup"><span data-stu-id="f900c-110">It also takes into account Azure throttling policies, and has mechanisms in place to manage multiple database backups.</span></span> <span data-ttu-id="f900c-111">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enregistre et utilise des événements étendus pour suivre toutes les activités.</span><span class="sxs-lookup"><span data-stu-id="f900c-111">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] uses extended events to track all activity.</span></span> <span data-ttu-id="f900c-112">Les canaux d'événements étendus utilisés par l'agent de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] comprennent les canaux d'administration, opérationnel, analytique et de débogage.</span><span class="sxs-lookup"><span data-stu-id="f900c-112">The Extended Event channels used by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent include, Admin, Operational, Analytical, and Debug.</span></span> <span data-ttu-id="f900c-113">Les événements tombant sous la catégorie d'administration sont généralement liés aux erreurs, nécessitent l'intervention de l'utilisateur et sont activés par défaut.</span><span class="sxs-lookup"><span data-stu-id="f900c-113">Events that fall under the Admin category usually are related to errors and require user intervention and are enabled by default.</span></span> <span data-ttu-id="f900c-114">Les événements analytiques sont également activés par défaut, mais ne sont généralement pas liés à des erreurs nécessitant l'intervention de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f900c-114">Analytical events are also turned on by default, but usually are not related to errors that require user intervention.</span></span> <span data-ttu-id="f900c-115">Les événements opérationnels sont généralement informatifs.</span><span class="sxs-lookup"><span data-stu-id="f900c-115">Operation events are typically informational.</span></span> <span data-ttu-id="f900c-116">Par exemple, les événements opérationnels incluent la planification d’une sauvegarde, l’aboutissement d’une sauvegarde, etc. Le débogage est le plus détaillé et est utilisé en interne par [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour déterminer les problèmes et les corriger si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f900c-116">For example, operational events include scheduling a backup, a successful completion of backup, etc. The Debug is the most verbose and is used internally by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] to determine issues and correct them if required.</span></span>  
  
### <a name="configure-monitoring-parameters-for-ss_smartbackup"></a><span data-ttu-id="f900c-117">Configurer les paramètres de surveillance de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f900c-117">Configure Monitoring Parameters for [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span></span>  
 <span data-ttu-id="f900c-118">La procédure stockée système **smart_admin. sp_set_parameter** vous permet de spécifier des paramètres d’analyse.</span><span class="sxs-lookup"><span data-stu-id="f900c-118">The **smart_admin.sp_set_parameter** system stored procedure allows you to specify monitoring settings.</span></span> <span data-ttu-id="f900c-119">Les sections suivantes expliquent pas à pas la procédure d'activation des événements étendus et l'activation de la notification par courrier électronique des erreurs et des avertissements.</span><span class="sxs-lookup"><span data-stu-id="f900c-119">The following sections walks through the process of enabling Extended Events,  and enabling email notification for errors and warnings.</span></span>  
  
 <span data-ttu-id="f900c-120">La fonction **smart_admin. fn_get_parameter** peut être utilisée pour obtenir la valeur actuelle d’un paramètre spécifique ou de tous les paramètres configurés.</span><span class="sxs-lookup"><span data-stu-id="f900c-120">The **smart_admin.fn_get_parameter** function can be used to get the current setting for a specific parameter or all configured parameters.</span></span> <span data-ttu-id="f900c-121">Si les paramètres n'ont jamais été configurés, la fonction ne retourne aucune valeur.</span><span class="sxs-lookup"><span data-stu-id="f900c-121">If the parameters have never been configured, the function does not return any values.</span></span>  
  
1.  <span data-ttu-id="f900c-122">Connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f900c-122">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f900c-123">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f900c-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f900c-124">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f900c-124">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="f900c-125">La configuration actuelle des événements étendus et des notifications par courrier électronique est retournée.</span><span class="sxs-lookup"><span data-stu-id="f900c-125">This will return the current configuration for Extended Events, and e-mail notifications.</span></span>  
  
```sql
Use msdb  
Go  
SELECT * FROM smart_admin.fn_get_parameter (NULL)  
GO  
```  
  
 <span data-ttu-id="f900c-126">Pour plus d’informations, consultez [smart_admin. fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="f900c-126">For more information, see [smart_admin.fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span></span>  
  
### <a name="extended-events-for-monitoring"></a><span data-ttu-id="f900c-127">Événements étendus pour la surveillance</span><span class="sxs-lookup"><span data-stu-id="f900c-127">Extended Events for Monitoring</span></span>  
 <span data-ttu-id="f900c-128">Les événements d'administration, opérationnels et analytiques sont activés par défaut.</span><span class="sxs-lookup"><span data-stu-id="f900c-128">By default, Admin, Operational and Analytical events are turned on.</span></span> <span data-ttu-id="f900c-129">Les événements d'administration sont les plus importants et utiles pour détecter les erreurs qui nécessitent une intervention manuelle.</span><span class="sxs-lookup"><span data-stu-id="f900c-129">Admin events are most critical, useful when identifying errors that require manual intervention to solve the problem.</span></span> <span data-ttu-id="f900c-130">Vous pouvez activer les événements opérationnels et de débogage, mais tenez compte du fait qu'ils sont commentés, et demandent à être filtrés.</span><span class="sxs-lookup"><span data-stu-id="f900c-130">You may want to turn on the operational and debug events but consider that these events are verbose and may require some filtering.</span></span> <span data-ttu-id="f900c-131">Les procédures ci-dessous montrent comment surveiller les événements enregistrés via les événements étendus.</span><span class="sxs-lookup"><span data-stu-id="f900c-131">The following procedures describe how to monitor events logged through Extended Events.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f900c-132">Contrairement aux événements étendus du moteur SQL, la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] ne prend pas en charge les principes de session d'événements étendus.</span><span class="sxs-lookup"><span data-stu-id="f900c-132">Unlike Extended Events for SQL Engine, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] does not support Extended Event session concepts.</span></span> <span data-ttu-id="f900c-133">Les procédures stockées système et les fonctions sont les outils utilisés pour interagir avec les événements étendus.</span><span class="sxs-lookup"><span data-stu-id="f900c-133">System stored procedures and functions are the tools used to interact with extended events.</span></span> <span data-ttu-id="f900c-134">Vous pouvez également consulter le journal des événements étendus dans le répertoire des journaux.</span><span class="sxs-lookup"><span data-stu-id="f900c-134">You can also view the extended event log from the log directory.</span></span>  
  
##### <a name="to-configure-and-view-extended-events"></a><span data-ttu-id="f900c-135">Pour configurer et afficher les événements étendus</span><span class="sxs-lookup"><span data-stu-id="f900c-135">To Configure and View Extended Events</span></span>  
  
1.  <span data-ttu-id="f900c-136">Consultez les canaux d'événements étendus disponibles et leur état en exécutant la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="f900c-136">To view available Extended Event channels and their current status by running the following query:</span></span>  
  
    ```sql
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="f900c-137">La sortie de cette requête affiche l'event_name, qu'il soit configurable ou non, et l'état activé ou désactivé actuel.</span><span class="sxs-lookup"><span data-stu-id="f900c-137">The output from this query will display the event_name, whether it is configurable or not, and whether it is currently enabled.</span></span>  <span data-ttu-id="f900c-138">Pour plus d’informations, consultez [smart_admin. fn_get_current_xevent_settings &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f900c-138">For more information, see [smart_admin.fn_get_current_xevent_settings &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span></span>  
  
2.  <span data-ttu-id="f900c-139">Pour activer les événements de débogage, exécutez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="f900c-139">To enable debug events, run the following query:</span></span>  
  
    ```sql
    --  to enable debug events  
    Use msdb;  
    GO 
    EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
    ```  
  
     <span data-ttu-id="f900c-140">Pour plus d’informations sur la procédure stockée, consultez [smart_admin. sp_set_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f900c-140">For more information about the stored procedure, see [smart_admin.sp_set_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span></span>  
  
3.  <span data-ttu-id="f900c-141">Pour consulter les événements enregistrés, exécutez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="f900c-141">To view the logged events run the following query:</span></span>  
  
    ```sql
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;
    ```  
  
    ```sql
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'
    ```  
  
### <a name="aggregated-error-countshealth-status"></a><span data-ttu-id="f900c-142">Nombre agrégé d'erreurs/état d'intégrité</span><span class="sxs-lookup"><span data-stu-id="f900c-142">Aggregated Error Counts/Health Status</span></span>  
 <span data-ttu-id="f900c-143">La fonction **smart_admin. fn_get_health_status** retourne une table de nombres d’erreurs agrégés pour chaque catégorie qui peut être utilisée pour surveiller l’état d’intégrité de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f900c-143">The **smart_admin.fn_get_health_status** function returns a table of aggregated error counts for each category that can be used to monitor the health status of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="f900c-144">Cette même fonction est également utilisée par le mécanisme de notification par courrier électronique configuré au niveau du système, décrit plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f900c-144">This same function is also used by the system configured e-mail notification mechanism described later in this topic.</span></span>   
<span data-ttu-id="f900c-145">Ces nombres agrégés peuvent servir à surveiller l'intégrité du système.</span><span class="sxs-lookup"><span data-stu-id="f900c-145">These aggregated counts can be used to monitor system health.</span></span> <span data-ttu-id="f900c-146">Par exemple, si la colonne number_ of_retention_loops indique 0 pour 30 minutes, il est possible que la gestion de la rétention soit trop longue, ou que l'événement ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="f900c-146">For example, if the number_ of_retention_loops column is 0 in 30 minutes, it is possible that retention management is taking long time or even not working correctly.</span></span> <span data-ttu-id="f900c-147">Les colonnes contenant des erreurs peuvent indiquer des problèmes et les journaux des événements étendus doivent être consultés pour en découvrir la cause.</span><span class="sxs-lookup"><span data-stu-id="f900c-147">Non-zero error columns may indicate problems and Extended Events logs should be checked to discover the problem.</span></span> <span data-ttu-id="f900c-148">Vous pouvez également appeler la procédure stockée **smart_admin. sp_get_backup_diagnostics** pour rechercher les détails de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="f900c-148">Alternatively, call **smart_admin.sp_get_backup_diagnostics** stored procedure to find the details of the error.</span></span>  
  
### <a name="using-agent-notification-for-assessing-backup-status-and-health"></a><span data-ttu-id="f900c-149">Utiliser la notification de l'agent pour déterminer l'état de sauvegarde et d'intégrité</span><span class="sxs-lookup"><span data-stu-id="f900c-149">Using Agent Notification for Assessing Backup Status and Health</span></span>  
 <span data-ttu-id="f900c-150">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] comprend un mécanisme de notification utilisant les stratégies de gestion basées sur la stratégie SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f900c-150">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] includes a notification mechanism that is based on SQL Server policy based management policies.</span></span>  
  
 <span data-ttu-id="f900c-151">**Configuration requise :**</span><span class="sxs-lookup"><span data-stu-id="f900c-151">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="f900c-152">Une messagerie de base de données est requise pour utiliser cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="f900c-152">Database Mail is required to use this functionality.</span></span> <span data-ttu-id="f900c-153">Pour plus d’informations sur l’activation de la messagerie de base de données pour l’instance de SQL Server, consultez [configurer des Database mail](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="f900c-153">For more information, about how to enable DB Mail for the instance of SQL Server, see [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
-   <span data-ttu-id="f900c-154">Les propriétés du système d'alerte de SQL Server Agent doivent être configurées pour utiliser la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="f900c-154">SQL Server Agent Alert System properties should be set to use Database Mail.</span></span>  
  
 <span data-ttu-id="f900c-155">**Architecture de notification :**</span><span class="sxs-lookup"><span data-stu-id="f900c-155">**Notification Architecture:**</span></span>  
  
-   <span data-ttu-id="f900c-156">**Gestion basée sur des stratégies :** Deux stratégies sont définies pour surveiller l’intégrité de la sauvegarde : la **stratégie d’intégrité du système Smart admin**et la stratégie d’intégrité des actions de l' **utilisateur Smart admin**.</span><span class="sxs-lookup"><span data-stu-id="f900c-156">**Policy Based Management:** Two policies are set to monitor backup health: **Smart Admin System Health Policy**, and the **Smart Admin User Action Health Policy**.</span></span> <span data-ttu-id="f900c-157">La stratégie d'intégrité du système Smart Admin évalue les erreurs critiques, comme des informations d'identification SQL manquantes ou non valides, les erreurs de connectivité, et signale l'intégrité du système.</span><span class="sxs-lookup"><span data-stu-id="f900c-157">The Smart Admin System Health Policy evaluates critical errors like lack of or invalid SQL Credentials, connectivity errors and reports the health of the system.</span></span> <span data-ttu-id="f900c-158">Elle nécessite généralement une action manuelle pour corriger le problème sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="f900c-158">These typically require a manual action to correct the underlying issue.</span></span> <span data-ttu-id="f900c-159">La stratégie d'intégrité des actions de l'utilisateur Smart Admin évalue les avertissements concernant, par exemple, les sauvegardes corrompues, ou d'autres événements similaires.</span><span class="sxs-lookup"><span data-stu-id="f900c-159">The Smart Admin User Action Health Policy evaluates warnings such as corrupted backups, and such.</span></span>  <span data-ttu-id="f900c-160">Elle ne nécessite généralement aucune action, et signale simplement un événement.</span><span class="sxs-lookup"><span data-stu-id="f900c-160">These may not require any action but just a warning of an event.</span></span> <span data-ttu-id="f900c-161">Ces problèmes sont automatiquement résolus par l'agent de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f900c-161">It is expected that such issues will be automatically taken care of by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent.</span></span>  
  
-   <span data-ttu-id="f900c-162">**SQL Server Agent** Travail : la notification est effectuée à l’aide d’un travail de SQL Server Agent qui comporte trois étapes.</span><span class="sxs-lookup"><span data-stu-id="f900c-162">**SQL Server Agent** Job: The notification is performed using a SQL Server Agent job that has three job steps.</span></span> <span data-ttu-id="f900c-163">Dans la première étape, l'agent détecte si la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] est configurée pour une base de données ou pour l'instance.</span><span class="sxs-lookup"><span data-stu-id="f900c-163">In the first job step it detects to see whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured for a database or instance.</span></span> <span data-ttu-id="f900c-164">S'il trouve la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] activée et configurée, il exécute la seconde étape à l'aide d'une applet de commande PowerShell qui évalue l'état d'intégrité selon les stratégies de gestion basée sur les stratégies SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f900c-164">If it finds [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled and configured, it executes the second step: executes a PowerShell cmdlet that assess the health status by evaluating the SQL Server policy based management policies.</span></span> <span data-ttu-id="f900c-165">S'il détecte une erreur ou un avertissement, il échoue, ce qui déclenche la troisième étape : la troisième étape envoie une notification par courrier électronique avec le rapport d'erreur/avertissement.</span><span class="sxs-lookup"><span data-stu-id="f900c-165">If it finds either an error or warning, it fails which then triggers the third step: The third step sends out an e-mail notification with the error/warning report.</span></span>  <span data-ttu-id="f900c-166">Notez toutefois que ce travail SQL Server Agent n'est pas activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="f900c-166">However this SQL Server Agent job is not enabled by default.</span></span> <span data-ttu-id="f900c-167">Pour activer le travail de notification par courrier électronique, utilisez la procédure stockée système **smart_admin. sp_set_backup_parameter** .</span><span class="sxs-lookup"><span data-stu-id="f900c-167">To enable the e-mail notification job, use the **smart_admin.sp_set_backup_parameter** system stored procedure.</span></span>  <span data-ttu-id="f900c-168">La procédure suivante décrit ces étapes de façon détaillée :</span><span class="sxs-lookup"><span data-stu-id="f900c-168">The following procedure describes the steps in more detail:</span></span>  
  
##### <a name="enabling-email-notification"></a><span data-ttu-id="f900c-169">Activation de la notification par courrier électronique</span><span class="sxs-lookup"><span data-stu-id="f900c-169">Enabling Email Notification</span></span>  
  
1.  <span data-ttu-id="f900c-170">Si Database Mail n’est pas déjà configuré, suivez les étapes décrites dans [configurer Database mail](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="f900c-170">If Database Mail is not already configured, use the steps described in [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
2.  <span data-ttu-id="f900c-171">Définir la base de données comme système de messagerie pour SQL Server système d’alerte : cliquez avec le bouton droit sur **SQL Server Agent**, sélectionnez **système d’alerte**, cochez la case Activer le **profil de messagerie** , sélectionnez **Database mail** comme **système de messagerie**, puis sélectionnez un profil de messagerie créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="f900c-171">Set database as the Mail System for SQL Server Alert System: Right Click on **SQL Server Agent**, select **Alert System**, check the **Enable mail profile** box, Select **Database Mail** as the **Mail System**, and select a previously created Mail profile.</span></span>  
  
3.  <span data-ttu-id="f900c-172">Exécutez la requête suivante dans une fenêtre de requête et indiquez l'adresse de messagerie qui recevra les notifications :</span><span class="sxs-lookup"><span data-stu-id="f900c-172">Run the following query in a query window and provide the e-mail address where you want the notification to be sent to:</span></span>  
  
    ```sql
    Use msdb  
    Go  
    EXEC smart_admin.sp_set_parameter @parameter_name = 'SSMBackup2WANotificationEmailIds', @parameter_value = '<email address>'
    ```  
  
     <span data-ttu-id="f900c-173">Un travail SQL Server Agent est créé pour collecter l'état d'intégrité et envoyer des notifications en cas d'erreur ou de problème au niveau des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="f900c-173">This creates a SQL Server Agent job that is used to gather health status and send notifications when there is an error or an issue with backups.</span></span>  
  
 <span data-ttu-id="f900c-174">Voici un exemple de script pour activer la messagerie de base de données et configurer la notification par courrier électronique au moyen d'un travail SQL Server Agent :</span><span class="sxs-lookup"><span data-stu-id="f900c-174">Following is a sample script  to enable DB Mail and set up the e-mail notification through SQL Server Agent Job</span></span>  
  
```sql
-- Prereq: Make sure that SQL Server service runs in a service account that has  
--  access to SMTP Server   
-- set SQL Server service account as domain account   
  
EXEC sp_configure 'show advanced', 1  
RECONFIGURE  
GO  
  
-- Enable DBMail  
EXEC sp_configure 'Database Mail XPs',1  
GO  
RECONFIGURE  
GO  
  
-- Configure DBMail  
DECLARE @emailid NVARCHAR(255)  
-- Note: change this email to your own email id  
SET @emailid = N'emailalias@mycompany.com'  
  
DECLARE @smtpserver NVARCHAR(255)  
SET @smtpserver = N'smtphost.domainname.com'  
  
DECLARE @mailprofile NVARCHAR(255)  
SET @mailprofile = N'my_profile'  
  
EXEC msdb.dbo.sysmail_add_account_sp @account_name=N'myaccount',  
                @email_address = @emailid,  
                @replyto_address = @emailid,  
                @mailserver_name = @smtpserver,  
                @use_default_credentials = 1  
  
EXEC msdb.dbo.sysmail_add_profile_sp @profile_name=@mailprofile  
EXEC msdb.dbo.sysmail_add_profileaccount_sp @profile_name=@mailprofile, @account_name=N'myaccount', @sequence_number=1  
  
-- Set SQL Agent to use DBMail profile  
EXEC msdb.dbo.sp_set_sqlagent_properties @databasemail_profile = @mailprofile  
  
-- Configure Notifications   
EXEC msdb.smart_admin.sp_set_parameter  
@parameter_name = 'SSMBackup2WANotificationEmailIds',  
@parameter_value = @emailid  
  
-- To test is you are receiving notifications  
-- delete few backup files from your storage container, Wait for 15 minutes & see if you get any email notification
```  
  
### <a name="using-powershell-to-setup-custom-health-monitoring"></a><span data-ttu-id="f900c-175">Utiliser PowerShell pour configurer une surveillance de l'intégrité personnalisée</span><span class="sxs-lookup"><span data-stu-id="f900c-175">Using PowerShell to Setup Custom Health Monitoring</span></span>  
 <span data-ttu-id="f900c-176">L’applet de commande **test-SqlSmartAdmin** peut être utilisée pour créer une analyse de l’intégrité personnalisée.</span><span class="sxs-lookup"><span data-stu-id="f900c-176">The **Test-SqlSmartAdmin** cmdlet can be used to create custom health monitoring.</span></span> <span data-ttu-id="f900c-177">Par exemple, l'option de notification décrite dans la section précédente peut être configurée au niveau de l'instance.</span><span class="sxs-lookup"><span data-stu-id="f900c-177">For example, the notification option described in the previous section can be configured at the instance level.</span></span>  <span data-ttu-id="f900c-178">Si plusieurs instances de SQL Server utilisent la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], l'applet de commande PowerShell peut être utilisée pour créer des scripts qui collectent l'état et l'intégrité des sauvegardes de toutes les instances.</span><span class="sxs-lookup"><span data-stu-id="f900c-178">If you have several instances of SQL Server configured to use [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], the PowerShell cmdlet can be used to create scripts in gather the status and health of backups for all the instances.</span></span>  
  
 <span data-ttu-id="f900c-179">L’applet de commande **test-SqlSmartAdmin** évalue les erreurs et les avertissements retournés par les stratégies de gestion basée sur des stratégies SQL Server et signale un État reporté.</span><span class="sxs-lookup"><span data-stu-id="f900c-179">The **Test-SqlSmartAdmin** cmdlet assesses the errors and warnings returned by the SQL Server Policy Based Management policies and reports out a rolled up status.</span></span>  <span data-ttu-id="f900c-180">Par défaut, cette applet de commande utilise les stratégies système.</span><span class="sxs-lookup"><span data-stu-id="f900c-180">By default this cmdlet uses the system policies.</span></span> <span data-ttu-id="f900c-181">Pour inclure une stratégie personnalisée, utilisez le paramètre `-AllowUserPolicies`.</span><span class="sxs-lookup"><span data-stu-id="f900c-181">To include any custom policy use the `-AllowUserPolicies` parameter.</span></span>  
  
 <span data-ttu-id="f900c-182">Voici un exemple de script PowerShell qui retourne un rapport d'erreurs et avertissements en fonction des stratégies système et des stratégies utilisateur créées :</span><span class="sxs-lookup"><span data-stu-id="f900c-182">Following is a sample PowerShell script that returns a report of errors and warnings based on the system policies and any user policies created:</span></span>  
  
```powershell
$policyResults = Get-SqlSmartAdmin | Test-SqlSmartAdmin -AllowUserPolicies  
$policyResults.PolicyEvaluationDetails | Select Name, Category, Expression, Result, Exception | fl
```  
  
 <span data-ttu-id="f900c-183">Le script suivant retourne un rapport détaillé des erreurs et des avertissements pour l’instance par défaut ( `\SQL\COMPUTER\DEFAULT` ) :</span><span class="sxs-lookup"><span data-stu-id="f900c-183">The following script returns a detailed report of the errors and warnings for the default instance (`\SQL\COMPUTER\DEFAULT`):</span></span>  
  
```powershell
(Get-SqlSmartAdmin ).EnumHealthStatus()  
```  
  
### <a name="objects-in-msdb-database"></a><span data-ttu-id="f900c-184">Objets dans une base de données MSDB</span><span class="sxs-lookup"><span data-stu-id="f900c-184">Objects in MSDB database</span></span>  
 <span data-ttu-id="f900c-185">Des objets sont installés pour implémenter cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="f900c-185">There are objects that are installed to implement the functionality.</span></span> <span data-ttu-id="f900c-186">Ces objets sont réservés à une utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="f900c-186">These objects are reserved for internal use.</span></span> <span data-ttu-id="f900c-187">Cependant, il existe une table système qui peut être utile pour surveiller l'état de sauvegarde : smart_backup_files.</span><span class="sxs-lookup"><span data-stu-id="f900c-187">However, there is one system table that can be useful in monitoring the backup status: smart_backup_files.</span></span> <span data-ttu-id="f900c-188">La plupart des informations stockées dans ce tableau sont pertinentes pour la surveillance, comme le type de sauvegarde, le nom de la base de données, le premier et le dernier LSN, les dates d’expiration des sauvegardes sont exposées via la fonction système [smart_admin. fn_available_backups &#40;le&#41;Transact-SQL ](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f900c-188">Most of the Information   stored in this table relevant to monitoring like the type of backup, database name, first and last lsn, backup expiry dates are exposed through the system function [smart_admin.fn_available_backups &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span></span> <span data-ttu-id="f900c-189">Cependant, la colonne d'état dans la table smart_backup_files qui indique l'état du fichier de sauvegarde n'est pas disponible via la fonction.</span><span class="sxs-lookup"><span data-stu-id="f900c-189">However the status column in the smart_backup_files table which indicates the status of the backup file is not available using the function.</span></span> <span data-ttu-id="f900c-190">Voici un exemple de requête que vous pouvez utiliser pour récupérer certaines informations, dont l'état, à partir de la table système :</span><span class="sxs-lookup"><span data-stu-id="f900c-190">Following is a sample query you can use to retrieve the some information including the status from the system table:</span></span>  
  
```sql
USE msdb  
GO  
SELECT  
 database_name AS [Database Name] ,backup_path AS [Backup Destination and File]  
,[Backup Type] =  
CASE backup_type  
WHEN 1 THEN 'FULL'  
WHEN 2 THEN 'LOG'  
END  
,[Backup Status] =  
CASE [status]  
WHEN 'A' THEN 'Available'  
WHEN 'B' THEN 'Copy In Progress'  
WHEN 'C' THEN 'Corrupted'  
WHEN 'D' THEN 'Deleted'  
WHEN 'F' THEN 'Copy Failed'  
WHEN 'U' THEN 'Unknown'  
END  
,first_lsn AS [First LSN]  
,last_lsn AS [Last LSN]  
,backup_start_date AS [Backup Start Time]  
,backup_finish_date AS [Backup Completion Time]  
,expiration_date AS [Backup Expiry Date/Time]  
FROM  
smart_backup_files;
```  
  
 <span data-ttu-id="f900c-191">Voici une explication détaillée des différents états retournés :</span><span class="sxs-lookup"><span data-stu-id="f900c-191">Following is a detailed explanation of the different status returned:</span></span>  
  
-   <span data-ttu-id="f900c-192">**Disponible-A :** Il s’agit d’un fichier de sauvegarde normal.</span><span class="sxs-lookup"><span data-stu-id="f900c-192">**Available - A:** This is a normal backup file.</span></span> <span data-ttu-id="f900c-193">La sauvegarde est terminée et a également vérifié qu’elle est disponible dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="f900c-193">The backup has been completed, and also verified that it is available in the Azure storage.</span></span>  
  
-   <span data-ttu-id="f900c-194">**Copie en cours-B :** Cet État est spécifique pour les bases de données de groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f900c-194">**Copy in Progress -B:** This status is specifically for Availability Group databases.</span></span> <span data-ttu-id="f900c-195">Si la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] détecte une interruption de la séquence des journaux de sauvegarde, elle tentera d'abord identifient la sauvegarde qui a peut-être provoqué une interruption dans la séquence.</span><span class="sxs-lookup"><span data-stu-id="f900c-195">If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] detects a break in the backup log chain, it will first attempt identify the  backup that might have caused the break in backup chain.</span></span> <span data-ttu-id="f900c-196">Lors de la recherche du fichier de sauvegarde, il tente de copier le fichier dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="f900c-196">On finding the backup file it attempts to copy the file to Azure storage.</span></span> <span data-ttu-id="f900c-197">Lorsque le processus de copie est en cours, elle affiche l'état.</span><span class="sxs-lookup"><span data-stu-id="f900c-197">When the copying process is in progress it will display this status.</span></span>  
  
-   <span data-ttu-id="f900c-198">**Échec de la copie-F :** Comme pour la copie en cours, il s’agit de bases de données du groupe de disponibilité t spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f900c-198">**Copy Failed - F:** Similar to Copy In Progress, this is specific t Availability Group databases.</span></span> <span data-ttu-id="f900c-199">Si le processus de copie échoue, l'état est marqué comme F.</span><span class="sxs-lookup"><span data-stu-id="f900c-199">If the copy process fails, the status is marked as F.</span></span>  
  
-   <span data-ttu-id="f900c-200">**Endommagé-C :** Si [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] le n’est pas en mesure de vérifier le fichier de sauvegarde dans le stockage en exécutant une commande RESTORE HEADER_ONLY même après plusieurs tentatives, il marque ce fichier comme endommagé.</span><span class="sxs-lookup"><span data-stu-id="f900c-200">**Corrupted - C:** If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is unable to verify the backup file in the storage by performing a RESTORE HEADER_ONLY command even after multiple attempts, it marks this file as corrupted.</span></span> <span data-ttu-id="f900c-201">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] planifiera une sauvegarde pour s'assurer que le fichier endommagé n'entraîne pas une interruption de la séquence de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f900c-201">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] will schedule a backup to ensure that the corrupted file does not result in a break of the backup chain.</span></span>  
  
-   <span data-ttu-id="f900c-202">**Supprimé-D :** Le fichier correspondant est introuvable dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="f900c-202">**Deleted - D:** The corresponding file cannot be found in the Azure storage.</span></span> <span data-ttu-id="f900c-203">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] planifiera une sauvegarde si le fichier supprimé entraîne une interruption dans la séquence de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f900c-203">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] will schedule a backup if the deleted file results in a break in the backup chain.</span></span>  
  
-   <span data-ttu-id="f900c-204">**Inconnu-U :** Cet état indique que [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] n’a pas encore pu vérifier l’existence du fichier et ses propriétés dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="f900c-204">**Unknown - U:** This status indicated that [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] has not yet been able to verify file existence and its properties in the Azure storage.</span></span> <span data-ttu-id="f900c-205">À la prochaine exécution du processus, soit approximativement toutes les 15 minutes, cet état sera mis à jour.</span><span class="sxs-lookup"><span data-stu-id="f900c-205">The next time the process runs, which is approximately every 15 minutes, this status will be updated.</span></span>  
