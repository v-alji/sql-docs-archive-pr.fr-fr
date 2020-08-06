---
title: Surveiller l’activité système à l’aide d’événements étendus | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- xe
- extended events [SQL Server], monitoring system activity
ms.assetid: d83ad88f-818c-49fe-a9a9-299f704fca53
author: rothja
ms.author: jroth
ms.openlocfilehash: d847d156d8244ede533e684c9e6b753d7d7b5047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600914"
---
# <a name="monitor-system-activity-using-extended-events"></a><span data-ttu-id="6329a-102">Surveiller l'activité système à l’aide d’événements étendus</span><span class="sxs-lookup"><span data-stu-id="6329a-102">Monitor System Activity Using Extended Events</span></span>
  <span data-ttu-id="6329a-103">Cette procédure illustre l’utilisation des événements étendus avec le suivi d'événements pour Windows (ETW) pour surveiller l’activité système.</span><span class="sxs-lookup"><span data-stu-id="6329a-103">This procedure illustrates how Extended Events can be used with Event Tracing for Windows (ETW) to monitor system activity.</span></span> <span data-ttu-id="6329a-104">Elle indique également comment utiliser les instructions CREATE EVENT SESSION, ALTER EVENT SESSION et DROP EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="6329a-104">The procedure also shows how the CREATE EVENT SESSION, ALTER EVENT SESSION, and DROP EVENT SESSION statements are used.</span></span>  
  
 <span data-ttu-id="6329a-105">L’utilisation de l'éditeur de requête de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] est nécessaire pour effectuer la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="6329a-105">Accomplishing these tasks involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span> <span data-ttu-id="6329a-106">Cette dernière nécessite également l'utilisation de l'invite de commandes pour exécuter des commandes ETW.</span><span class="sxs-lookup"><span data-stu-id="6329a-106">The procedure also requires using the command prompt to run ETW commands.</span></span>  
  
### <a name="to-monitor-system-activity-using-extended-events"></a><span data-ttu-id="6329a-107">Pour surveiller l'activité système à l’aide d’événements étendus</span><span class="sxs-lookup"><span data-stu-id="6329a-107">To monitor system activity using Extended Events</span></span>  
  
1.  <span data-ttu-id="6329a-108">Dans l’éditeur de requêtes, émettez les instructions suivantes afin de créer une session d'événement et d’y ajouter deux événements.</span><span class="sxs-lookup"><span data-stu-id="6329a-108">In Query Editor, issue the following statements to create an event session and add two events.</span></span> <span data-ttu-id="6329a-109">Ces événements, checkpoint_begin et checkpoint_end, se déclenchent au début et à la fin d'un point de contrôle de base de données.</span><span class="sxs-lookup"><span data-stu-id="6329a-109">These events, checkpoint_begin and checkpoint_end, fire at the beginning and end of a database checkpoint.</span></span>  
  
    ```  
    CREATE EVENT SESSION test0  
    ON SERVER  
    ADD EVENT sqlserver.checkpoint_begin,  
    ADD EVENT sqlserver.checkpoint_end  
    WITH (MAX_DISPATCH_LATENCY = 1 SECONDS)  
    go  
    ```  
  
2.  <span data-ttu-id="6329a-110">Ajoutez la cible de création de compartiments avec 32 compartiments pour compter le nombre de points de contrôle en fonction de l'ID de base de données.</span><span class="sxs-lookup"><span data-stu-id="6329a-110">Add the bucketing target with 32 buckets to count the number of checkpoints based on the database ID.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.histogram  
    (  
          SET slots = 32, filtering_event_name = 'sqlserver.checkpoint_end', source_type = 0, source = 'database_id'  
    )  
    go  
    ```  
  
3.  <span data-ttu-id="6329a-111">Émettez les instructions suivantes pour ajouter la cible ETW.</span><span class="sxs-lookup"><span data-stu-id="6329a-111">Issue the following statements to add the ETW target.</span></span> <span data-ttu-id="6329a-112">Cela vous permettra de voir les événements de début et de fin et de déterminer ainsi le temps requis par le point de contrôle.</span><span class="sxs-lookup"><span data-stu-id="6329a-112">This will enable you to see the begin and end events, which is used to determine how long the checkpoint takes.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.etw_classic_sync_target  
    go  
    ```  
  
4.  <span data-ttu-id="6329a-113">Émettez les instructions suivantes pour démarrer la session et lancer la collecte d'événements.</span><span class="sxs-lookup"><span data-stu-id="6329a-113">Issue the following statements to start the session and begin event collection.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = start  
    go  
    ```  
  
5.  <span data-ttu-id="6329a-114">Émettez les instructions suivantes pour provoquer le déclenchement de trois événements.</span><span class="sxs-lookup"><span data-stu-id="6329a-114">Issue the following statements to cause three events to fire.</span></span>  
  
    ```  
    USE tempdb  
          checkpoint  
    go  
    USE master  
          checkpoint  
          checkpoint  
    go  
    ```  
  
6.  <span data-ttu-id="6329a-115">Émettez les instructions suivantes pour afficher le nombre d’événements.</span><span class="sxs-lookup"><span data-stu-id="6329a-115">Issue the following statements to view the event counts.</span></span>  
  
    ```  
    SELECT CAST(xest.target_data AS xml) Bucketizer_Target_Data_in_XML  
    FROM sys.dm_xe_session_targets xest  
    JOIN sys.dm_xe_sessions xes ON xes.address = xest.event_session_address  
    JOIN sys.server_event_sessions ses ON xes.name = ses.name  
    WHERE xest.target_name = 'histogram' AND xes.name = 'test0'  
    go  
    ```  
  
7.  <span data-ttu-id="6329a-116">À l'invite de commandes, émettez les commandes suivantes pour afficher les données ETW.</span><span class="sxs-lookup"><span data-stu-id="6329a-116">At the command prompt, issue the following commands to view the ETW data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6329a-117">Pour obtenir de l’aide sur la commande **tracerpt** , entrez `tracerpt /?`à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="6329a-117">To get help for the **tracerpt** command, at the command prompt, enter `tracerpt /?`.</span></span>  
  
    ```  
    logman query -ets --- List the ETW sessions. This is optional.  
    logman update XE_DEFAULT_ETW_SESSION -fd -ets --- Flush the ETW log.  
    tracerpt %temp%\xeetw.etl -o xeetw.txt --- Dump the events so they can be seen.  
    ```  
  
8.  <span data-ttu-id="6329a-118">Émettez les instructions suivantes pour arrêter la session d'événement et la supprimer du serveur.</span><span class="sxs-lookup"><span data-stu-id="6329a-118">Issue the following statements to stop the event session and remove it from the server.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = STOP  
    go  
  
    DROP EVENT SESSION test0  
    ON SERVER  
    go  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6329a-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6329a-119">See Also</span></span>  
 <span data-ttu-id="6329a-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6329a-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="6329a-121">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6329a-121">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 <span data-ttu-id="6329a-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6329a-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="6329a-123">Affichages catalogue des événements étendus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6329a-123">Extended Events Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql)  
 <span data-ttu-id="6329a-124">[Vues de gestion dynamique des événements étendus](../views/views.md) </span><span class="sxs-lookup"><span data-stu-id="6329a-124">[Extended Events Dynamic Management Views](../views/views.md) </span></span>  
 [<span data-ttu-id="6329a-125">Cibles des Événements étendus SQL Server</span><span class="sxs-lookup"><span data-stu-id="6329a-125">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
