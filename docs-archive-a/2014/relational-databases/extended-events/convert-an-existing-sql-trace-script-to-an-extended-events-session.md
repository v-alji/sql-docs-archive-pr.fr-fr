---
title: Convertir un script Trace SQL existant en session d’événements étendus | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, convert script to extended events
- extended events [SQL Server], convert SQL Trace script
ms.assetid: 4c8f29e6-0a37-490f-88b3-33493871b3f9
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e5b0d0e20fbf4fd55398c130abf6cfff128ebe8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612357"
---
# <a name="convert-an-existing-sql-trace-script-to-an-extended-events-session"></a><span data-ttu-id="34992-102">Convertir un script Trace SQL existant en session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="34992-102">Convert an Existing SQL Trace Script to an Extended Events Session</span></span>
  <span data-ttu-id="34992-103">Si vous disposez d'un script Trace SQL existant que vous souhaitez convertir en session d'événements étendus, vous pouvez utiliser les procédures décrites dans cette rubrique pour créer une session d'événements étendus équivalente.</span><span class="sxs-lookup"><span data-stu-id="34992-103">If you have an existing SQL Trace script that you want to convert to an Extended Events session, you can use the procedures in this topic to create an equivalent Extended Events session.</span></span> <span data-ttu-id="34992-104">En utilisant les informations contenues dans les tables système trace_xe_action_map et trace_xe_event_map, vous pouvez recueillir les informations nécessaires pour effectuer la conversion.</span><span class="sxs-lookup"><span data-stu-id="34992-104">By using the information in the trace_xe_action_map and trace_xe_event_map system tables, you can collect the information that you must have to do the conversion.</span></span>  
  
 <span data-ttu-id="34992-105">Ces étapes sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="34992-105">The steps include the following:</span></span>  
  
1.  <span data-ttu-id="34992-106">Exécutez le script existant pour créer une session Trace SQL, puis obtenez l'ID de la trace.</span><span class="sxs-lookup"><span data-stu-id="34992-106">Execute the existing script to create a SQL Trace session, and then obtain the ID of the trace.</span></span>  
  
2.  <span data-ttu-id="34992-107">Exécutez une requête qui utilise la fonction fn_trace_geteventinfo pour rechercher les événements et actions d’événements étendus équivalents pour chaque classe d’événements Trace SQL et ses colonnes associées.</span><span class="sxs-lookup"><span data-stu-id="34992-107">Run a query that uses the fn_trace_geteventinfo function to find the equivalent Extended Events events and actions for each SQL Trace event class and its associated columns.</span></span>  
  
3.  <span data-ttu-id="34992-108">Utilisez la fonction fn_trace_getfilterinfo pour répertorier les filtres et les actions d’événements étendus équivalentes à utiliser.</span><span class="sxs-lookup"><span data-stu-id="34992-108">Use the fn_trace_getfilterinfo function to list the filters and the equivalent Extended Events actions to use.</span></span>  
  
4.  <span data-ttu-id="34992-109">Créez manuellement une session d'événements étendus, à l'aide des événements, des actions et des prédicats (filtres) d'événements étendus équivalents.</span><span class="sxs-lookup"><span data-stu-id="34992-109">Manually create an Extended Events session, using the equivalent Extended Events events, actions, and predicates (filters).</span></span>  
  
## <a name="to-obtain-the-trace-id"></a><span data-ttu-id="34992-110">Pour obtenir l'ID de trace</span><span class="sxs-lookup"><span data-stu-id="34992-110">To obtain the trace ID</span></span>  
  
1.  <span data-ttu-id="34992-111">Ouvrez le script Trace SQL dans l'Éditeur de requête, puis exécutez le script pour créer la session de trace.</span><span class="sxs-lookup"><span data-stu-id="34992-111">Open the SQL Trace script in Query Editor, and then execute the script to create the trace session.</span></span> <span data-ttu-id="34992-112">Notez qu'il n'est pas nécessaire que la session de trace soit en cours d'exécution pour exécuter cette procédure.</span><span class="sxs-lookup"><span data-stu-id="34992-112">Note that the trace session does not need to be running to complete this procedure.</span></span>  
  
2.  <span data-ttu-id="34992-113">Obtenez l'ID de la trace.</span><span class="sxs-lookup"><span data-stu-id="34992-113">Obtain the ID of the trace.</span></span> <span data-ttu-id="34992-114">Pour cela, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="34992-114">To do this, use the following query:</span></span>  
  
    ```sql
    SELECT * FROM sys.traces;  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="34992-115">L'ID de trace 1 indique en général la trace par défaut.</span><span class="sxs-lookup"><span data-stu-id="34992-115">Trace ID 1 typically indicates the default trace.</span></span>  
  
## <a name="to-determine-the-extended-events-equivalents"></a><span data-ttu-id="34992-116">Pour déterminer les équivalents des événements étendus</span><span class="sxs-lookup"><span data-stu-id="34992-116">To determine the Extended Events equivalents</span></span>  
  
1.  <span data-ttu-id="34992-117">Pour déterminer les événements et actions d’événements étendus équivalents, exécutez la requête suivante, où la valeur de l’ID de trace obtenue au cours de l’étape précédente est affectée à *trace_id* .</span><span class="sxs-lookup"><span data-stu-id="34992-117">To determine the equivalent Extended Events events and actions, run the following query, where *trace_id* is set to the value of the trace ID that you obtained in the previous procedure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34992-118">Dans cet exemple, l'ID de trace pour la trace par défaut (1) est utilisé.</span><span class="sxs-lookup"><span data-stu-id="34992-118">In this example, the trace ID for the default trace (1) is used.</span></span>  
  
    ```sql
    USE MASTER;  
    GO  
    DECLARE @trace_id int;  
    SET @trace_id = 1;  
    SELECT DISTINCT el.eventid, em.package_name, em.xe_event_name AS 'event'  
       , el.columnid, ec.xe_action_name AS 'action'  
    FROM (sys.fn_trace_geteventinfo(@trace_id) AS el  
       LEFT OUTER JOIN sys.trace_xe_event_map AS em  
          ON el.eventid = em.trace_event_id)  
    LEFT OUTER JOIN sys.trace_xe_action_map AS ec  
       ON el.columnid = ec.trace_column_id  
    WHERE em.xe_event_name IS NOT NULL AND ec.xe_action_name IS NOT NULL;  
    ```  
  
     <span data-ttu-id="34992-119">L'ID d'événement, le nom du package, le nom de l'événement, l'ID de colonne et le nom de l'action des événements étendus équivalents sont retournés.</span><span class="sxs-lookup"><span data-stu-id="34992-119">The equivalent Extended Events event ID, package name, event name, column ID and action name are returned.</span></span> <span data-ttu-id="34992-120">Vous utiliserez cette sortie dans la procédure « Pour créer une session d'événements étendus » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="34992-120">You will use this output in the procedure "To create the Extended Events session" later in this topic.</span></span>  
  
     <span data-ttu-id="34992-121">Dans certains cas, la colonne filtrée est mappée à un champ de données d'événement inclus par défaut dans l'événement Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="34992-121">In some cases, the filtered column maps to an event data field that is included by default in the Extended Events event.</span></span> <span data-ttu-id="34992-122">Par conséquent, la colonne « Extended_Events_action_name » sera NULL.</span><span class="sxs-lookup"><span data-stu-id="34992-122">Therefore, the "Extended_Events_action_name" column will be NULL.</span></span> <span data-ttu-id="34992-123">Si cela se produit, vous devez effectuer les opérations suivantes pour déterminer le champ de données qui est équivalent à la colonne filtrée :</span><span class="sxs-lookup"><span data-stu-id="34992-123">If this occurs, you must do the following to determine which data field is equivalent to the filtered column:</span></span>  
  
    1.  <span data-ttu-id="34992-124">Pour les actions qui retournent NULL, identifiez quelles sont les classes d'événements Trace SQL dans le script qui contiennent la colonne filtrée.</span><span class="sxs-lookup"><span data-stu-id="34992-124">For the actions that return NULL, identify which SQL Trace event classes in the script contain the column that is being filtered.</span></span>  
  
         <span data-ttu-id="34992-125">Par exemple, vous avez peut-être utilisé la classe d’événements SP:StmtCompleted et spécifié un filtre sur le nom de colonne de trace Duration (ID 45 de classe d’événements Trace SQL, et ID 13 de colonne Trace SQL).</span><span class="sxs-lookup"><span data-stu-id="34992-125">For example, you may have used the SP:StmtCompleted event class, and specified a filter on the Duration trace column name (SQL Trace event class ID 45, and SQL Trace column ID 13).</span></span> <span data-ttu-id="34992-126">Dans ce cas, le nom de l'action s'affichera comme NULL dans les résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="34992-126">In this case, the action name will appear as NULL in the query results.</span></span>  
  
    2.  <span data-ttu-id="34992-127">Pour chaque classe d'événements Trace SQL que vous avez identifiée à l'étape précédente, recherchez le nom d'événement Événements étendus équivalent.</span><span class="sxs-lookup"><span data-stu-id="34992-127">For each SQL Trace event class that you identified in the previous step, find the equivalent Extended Events event name.</span></span> <span data-ttu-id="34992-128">(Si vous n’êtes pas sûr du nom de l’événement équivalent, utilisez la requête dans la rubrique [Consulter les Événements étendus équivalents aux classes d’événements Trace SQL](view-the-extended-events-equivalents-to-sql-trace-event-classes.md).)</span><span class="sxs-lookup"><span data-stu-id="34992-128">(If you are not sure of the equivalent event name, use the query in the topic [View the Extended Events Equivalents to SQL Trace Event Classes](view-the-extended-events-equivalents-to-sql-trace-event-classes.md).)</span></span>  
  
    3.  <span data-ttu-id="34992-129">Utilisez la requête suivante pour identifier les champs de données corrects à utiliser pour les événements que vous avez identifiés à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="34992-129">Use the following query to identify the correct data fields to use for the events that you identified in the previous step.</span></span> <span data-ttu-id="34992-130">La requête affiche les champs de données d'événements étendus dans la colonne « event_field ».</span><span class="sxs-lookup"><span data-stu-id="34992-130">The query shows the Extended Events data fields in the "event_field" column.</span></span> <span data-ttu-id="34992-131">Dans la requête, remplacez *<event_name>* par le nom d’un événement que vous avez spécifié à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="34992-131">In the query, replace *<event_name>* with the name of an event that you specified in the previous step.</span></span>  
  
        ```sql
        SELECT xp.name package_name, xe.name event_name  
           ,xc.name event_field, xc.description  
        FROM sys.trace_xe_event_map AS em  
        INNER JOIN sys.dm_xe_objects AS xe  
           ON em.xe_event_name = xe.name  
        INNER JOIN sys.dm_xe_packages AS xp  
           ON xe.package_guid = xp.guid AND em.package_name = xp.name  
        INNER JOIN sys.dm_xe_object_columns AS xc  
           ON xe.name = xc.object_name  
        WHERE xe.object_type = 'event' AND xc.column_type <> 'readonly'  
           AND em.xe_event_name = '<event_name>';  
        ```  
  
         <span data-ttu-id="34992-132">Par exemple, la classe d’événements SP:StmtCompleted correspond à l’événement d’événements étendus sp_statement_completed.</span><span class="sxs-lookup"><span data-stu-id="34992-132">For example, the SP:StmtCompleted event class maps to the sp_statement_completed Extended Events event.</span></span> <span data-ttu-id="34992-133">Si vous spécifiez sp_statement_completed comme nom d’événement dans la requête, la colonne « event_field » affiche les champs inclus par défaut avec l’événement.</span><span class="sxs-lookup"><span data-stu-id="34992-133">If you specify sp_statement_completed as the event name in the query, the "event_field" column shows the fields that are included by default with the event.</span></span> <span data-ttu-id="34992-134">Si vous observez les champs, vous pouvez voir qu'il y a un champ de « durée ».</span><span class="sxs-lookup"><span data-stu-id="34992-134">Looking at the fields, you can see that there is a "duration" field.</span></span> <span data-ttu-id="34992-135">Pour créer le filtre dans la session d'événements étendus équivalente, vous devez ajouter un prédicat tel que « WHERE duration > 0 ».</span><span class="sxs-lookup"><span data-stu-id="34992-135">To create the filter in the equivalent Extended Events session, you would add a predicate such as "WHERE duration > 0".</span></span> <span data-ttu-id="34992-136">Pour obtenir un exemple, consultez la procédure « Pour créer la session d'événements étendus » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="34992-136">For an example, see the "To create the Extended Events session" procedure in this topic.</span></span>  
  
## <a name="to-create-the-extended-events-session"></a><span data-ttu-id="34992-137">Pour créer la session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="34992-137">To create the Extended Events session</span></span>  
 <span data-ttu-id="34992-138">Utilisez l'Éditeur de requête pour créer la session d'événements étendus, et écrire la sortie dans une cible de fichier.</span><span class="sxs-lookup"><span data-stu-id="34992-138">Use Query Editor to create the Extended Events session, and to write the output to a file target.</span></span> <span data-ttu-id="34992-139">Les étapes suivantes décrivent une requête unique, avec les explications indiquant comment générer la requête.</span><span class="sxs-lookup"><span data-stu-id="34992-139">The following steps describe a single query, with explanations to show you how to build the query.</span></span> <span data-ttu-id="34992-140">Pour obtenir un exemple de requête complet, consultez la section Exemple de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="34992-140">For the full query example, see the "Example" section of this topic.</span></span>  
  
1.  <span data-ttu-id="34992-141">Ajoutez les instructions pour créer la session d’événements, en remplaçant*session_name* par le nom à utiliser pour la session d’événements étendus.</span><span class="sxs-lookup"><span data-stu-id="34992-141">Add statements to create the event session, replacing s*ession_name* with the name that you want to use for the Extended Events session.</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [Session_Name] ON SERVER;  
    CREATE EVENT SESSION [Session_Name]  
    ON SERVER;  
    ```  
  
2.  <span data-ttu-id="34992-142">Ajoutez les événements d'événements étendus et les actions retournés comme sortie dans la procédure « Déterminer les équivalents d'événements étendus », puis ajoutez les prédicats (filtres) que vous avez identifiés dans la procédure « Pour déterminer les filtres utilisés dans le script ».</span><span class="sxs-lookup"><span data-stu-id="34992-142">Add the Extended Events events and actions that were returned as output in the procedure "Determine the Extended Events equivalents", and add the predicates (filters) that you identified in the procedure "To determine the filters that were used in the script".</span></span>  
  
     <span data-ttu-id="34992-143">L’exemple suivant utilise un script Trace SQL qui inclut les classes d’événements SQL:StmtStarting et SP:StmtCompleted, avec les filtres pour l’ID et la durée de session.</span><span class="sxs-lookup"><span data-stu-id="34992-143">The following example uses a SQL Trace script that includes the SQL:StmtStarting and SP:StmtCompleted event classes, with filters for session ID and duration.</span></span> <span data-ttu-id="34992-144">L'exemple de sortie pour la requête dans la procédure « Déterminer les équivalents d'événements étendus » a retourné le jeu de résultats suivant :</span><span class="sxs-lookup"><span data-stu-id="34992-144">Sample output for the query in the "Determine the Extended Events equivalents" procedure returned the following result set:</span></span>  
  
    ```  
    Eventid  package_name  event                   columnid  action  
    44       sqlserver     sp_statement_starting   6         nt_username  
    44       sqlserver     sp_statement_starting   9         client_pid  
    44       sqlserver     sp_statement_starting   10        client_app_name  
    44       sqlserver     sp_statement_starting   11        server_principal_name  
    44       sqlserver     sp_statement_starting   12        session_id  
    45       sqlserver     sp_statement_completed  6         nt_username  
    45       sqlserver     sp_statement_completed  9         client_pid  
    45       sqlserver     sp_statement_completed  10        client_app_name  
    45       sqlserver     sp_statement_completed  11        server_principal_name  
    45       sqlserver     sp_statement_completed  12        session_id  
    ```  
  
     <span data-ttu-id="34992-145">Pour convertir ceci en équivalents d’événements étendus, les événements sqlserver.sp_statement_starting et sqlserver.sp_statement_completed sont ajoutés, avec une liste d’actions.</span><span class="sxs-lookup"><span data-stu-id="34992-145">To convert this to the Extended Events equivalent, the sqlserver.sp_statement_starting and the sqlserver.sp_statement_completed events are added, with a list of actions.</span></span> <span data-ttu-id="34992-146">Les instructions de prédicat sont incluses comme clauses WHERE.</span><span class="sxs-lookup"><span data-stu-id="34992-146">Predicate statements are included as WHERE clauses.</span></span>  
  
    ```sql
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       )  
    ```  
  
3.  <span data-ttu-id="34992-147">Ajoutez la cible de fichier asynchrone, en remplaçant les chemins d’accès de fichier par l’emplacement où vous souhaitez enregistrer la sortie.</span><span class="sxs-lookup"><span data-stu-id="34992-147">Add the asynchronous file target, replacing the file paths with the location where you want to save the output.</span></span> <span data-ttu-id="34992-148">Lorsque vous spécifiez la cible de fichier, vous devez inclure un fichier journal et un fichier du chemin d'accès du fichier de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="34992-148">When specifying the file target, you must include a log file and metadata file path file.</span></span>  
  
    ```sql
    ADD TARGET package0.asynchronous_file_target(  
       SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="to-view-the-results"></a><span data-ttu-id="34992-149">Pour afficher les résultats</span><span class="sxs-lookup"><span data-stu-id="34992-149">To view the results</span></span>  
  
1.  <span data-ttu-id="34992-150">Vous pouvez utiliser la fonction sys.fn_xe_file_target_read_file pour afficher la sortie.</span><span class="sxs-lookup"><span data-stu-id="34992-150">You can use the sys.fn_xe_file_target_read_file function to view the output.</span></span> <span data-ttu-id="34992-151">Pour cela, exécutez la requête suivante, en remplaçant les chemins d'accès aux fichiers par les chemins d'accès que vous avez spécifiés :</span><span class="sxs-lookup"><span data-stu-id="34992-151">To do this, run the following query, replacing the file paths with the paths that you specified:</span></span>  
  
    ```sql
    SELECT *, CAST(event_data as XML) AS 'event_data_XML'  
    FROM sys.fn_xe_file_target_read_file('c:\temp\ExtendedEventsStoredProcs*.xel', 'c:\temp\ExtendedEventsStoredProcs*.xem', NULL, NULL);  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="34992-152">La conversion des données d'événement en tant que XML est facultative.</span><span class="sxs-lookup"><span data-stu-id="34992-152">Casting the event data as XML is optional.</span></span>  
  
     <span data-ttu-id="34992-153">Pour plus d’informations sur la fonction sys.fn_xe_file_target_read_file, consultez [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="34992-153">For more information about the sys.fn_xe_file_target_read_file function, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [session_name] ON SERVER;  
    CREATE EVENT SESSION [session_name]  
    ON SERVER  
  
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       );  
  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="example"></a><span data-ttu-id="34992-154"> Exemple</span><span class="sxs-lookup"><span data-stu-id="34992-154">Example</span></span>  
  
```sql
IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
   DROP EVENT SESSION [session_name] ON SERVER;  
CREATE EVENT SESSION [session_name]  
ON SERVER  
  
ADD EVENT sqlserver.sp_statement_starting  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59   
   ),  
  
ADD EVENT sqlserver.sp_statement_completed  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59 AND duration > 0  
   )  
  
ADD TARGET package0.asynchronous_file_target  
   (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
```  
  
## <a name="see-also"></a><span data-ttu-id="34992-155"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34992-155">See Also</span></span>  
 [<span data-ttu-id="34992-156">Consulter les événements étendus équivalents aux classes d’événements Trace SQL</span><span class="sxs-lookup"><span data-stu-id="34992-156">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>](view-the-extended-events-equivalents-to-sql-trace-event-classes.md)  
  
  
