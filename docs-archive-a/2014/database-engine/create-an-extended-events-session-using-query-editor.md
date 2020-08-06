---
title: Créer une session d’événements étendus à l’aide de l’éditeur de requête | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- create extended events session
- extended events [SQL Server], create session
ms.assetid: cba0e02b-b201-4863-bf1b-9164e68e5fa8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 648370ecdd2938b6fb425955dc02da8960f884c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605709"
---
# <a name="create-an-extended-events-session-using-query-editor"></a><span data-ttu-id="4ae93-102">Créer une session d'événements étendus à l'aide de l'éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="4ae93-102">Create an Extended Events Session Using Query Editor</span></span>
  <span data-ttu-id="4ae93-103">Vous pouvez créer une session d'événements étendus à l'aide de l'éditeur de requête, ou vous pouvez créer une session dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="4ae93-103">You can create an Extended Events session by using the Query Editor, or you can create a session in Object Explorer.</span></span> <span data-ttu-id="4ae93-104">Dans l’Explorateur d’objets, les événements étendus fournissent deux interfaces utilisateur que vous pouvez utiliser pour créer, modifier et afficher des données de session d’événements : un assistant qui vous guide tout au long du processus de création de la session d’événements et une interface utilisateur de nouvelle session qui fournit des options de configuration plus avancées.</span><span class="sxs-lookup"><span data-stu-id="4ae93-104">In Object Explorer, Extended Events provides two user interfaces you can use to create, modify, and view event session data - a wizard that guides you through the event session creation process, and a New Session UI that provides more advanced configuration options.</span></span> <span data-ttu-id="4ae93-105">Vous pouvez créer des sessions d'événements étendus pour diagnostiquer le suivi SQL Server, qui vous permet de résoudre des problèmes tels que :</span><span class="sxs-lookup"><span data-stu-id="4ae93-105">You can create Extended Events sessions to diagnose SQL Server tracing, which enables you to resolve issues such as the following:</span></span>  
  
-   <span data-ttu-id="4ae93-106">Rechercher les requêtes les plus onéreuses</span><span class="sxs-lookup"><span data-stu-id="4ae93-106">Find your most expensive queries</span></span>  
  
-   <span data-ttu-id="4ae93-107">Rechercher les causes premières d'une contention de verrouillage</span><span class="sxs-lookup"><span data-stu-id="4ae93-107">Find root causes of latch contention</span></span>  
  
-   <span data-ttu-id="4ae93-108">Rechercher une requête qui bloque d'autres requêtes</span><span class="sxs-lookup"><span data-stu-id="4ae93-108">Find a query that is blocking other queries</span></span>  
  
-   <span data-ttu-id="4ae93-109">Remédier à l'utilisation excessive du processeur due à la recompilation de requêtes</span><span class="sxs-lookup"><span data-stu-id="4ae93-109">Troubleshoot excessive CPU usage caused by query recompilation</span></span>  
  
-   <span data-ttu-id="4ae93-110">Résoudre les problèmes de blocages</span><span class="sxs-lookup"><span data-stu-id="4ae93-110">Troubleshoot deadlocks</span></span>  
  
 <span data-ttu-id="4ae93-111">Pour plus d’informations sur la création d’une session Événements étendus à l’aide de l’Assistant Nouvelle session, consultez [Créer une session d’événements étendus à l’aide de l’Assistant &#40;Explorateur d’objets&#41;](../ssms/object/object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="4ae93-111">For information about how to create an Extended Events session using the New Session Wizard, see [Create an Extended Events Session Using the Wizard &#40;Object Explorer&#41;](../ssms/object/object-explorer.md).</span></span> <span data-ttu-id="4ae93-112">Pour plus d’informations sur la création d’une session d’événements étendus en utilisant l’interface utilisateur de nouvelle session, consultez [Créer une session Événements étendus à l’aide de la boîte de dialogue Nouvelle session](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span><span class="sxs-lookup"><span data-stu-id="4ae93-112">For information about how to create an Extended Events session using the New Session UI, see [Create an Extended Events Session Using the New Session Dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4ae93-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4ae93-113">Permissions</span></span>  
 <span data-ttu-id="4ae93-114">Pour créer une session d'événements étendus, vous devez disposer de l'autorisation ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="4ae93-114">To create an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="creating-an-extended-events-session-using-query-editor"></a><span data-ttu-id="4ae93-115">Création d'une session d'événements étendus à l'aide de l'éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="4ae93-115">Creating an Extended Events session using Query Editor</span></span>  
  
#### <a name="to-create-an-extended-events-session"></a><span data-ttu-id="4ae93-116">Pour créer une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="4ae93-116">To create an Extended Events session</span></span>  
  
1.  <span data-ttu-id="4ae93-117">La procédure suivante indique comment créer une session d'événements étendus en utilisant l'Éditeur de requête dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ae93-117">The following procedure shows how to create an Extended Events session by using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="4ae93-118">Déterminez quels événements vous souhaitez utiliser dans la session.</span><span class="sxs-lookup"><span data-stu-id="4ae93-118">Determine which events that you want to use in the session.</span></span> <span data-ttu-id="4ae93-119">Pour consulter tous les événements qui sont disponibles, avec le mot clé et le canal, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="4ae93-119">To see all the events that are available, together with the keyword and channel, use the following query:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ae93-120">Pour plus d’informations sur les mots clés et les canaux, consultez [Packages d’événements étendus SQL Server](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span><span class="sxs-lookup"><span data-stu-id="4ae93-120">For information about keywords and channels, see [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span></span>  
  
    ```  
    SELECT p.name, c.event, k.keyword, c.channel, c.description FROM  
       (  
       SELECT event_package = o.package_guid, o.description,   
       event=c.object_name, channel = v.map_value  
       FROM sys.dm_xe_objects o  
       LEFT JOIN sys.dm_xe_object_columns c ON o.name = c.object_name  
       INNER JOIN sys.dm_xe_map_values v ON c.type_name = v.name   
       AND c.column_value = cast(v.map_key AS nvarchar)  
       WHERE object_type = 'event' AND (c.name = 'CHANNEL' or c.name IS NULL)  
       ) c LEFT JOIN   
       (  
       SELECT event_package = c.object_package_guid, event = c.object_name,   
       keyword = v.map_value  
       FROM sys.dm_xe_object_columns c INNER JOIN sys.dm_xe_map_values v   
       ON c.type_name = v.name AND c.column_value = v.map_key   
       AND c.type_package_guid = v.object_package_guid  
       INNER JOIN sys.dm_xe_objects o ON o.name = c.object_name   
       AND o.package_guid = c.object_package_guid  
       WHERE object_type = 'event' AND c.name = 'KEYWORD'   
       ) k  
       ON  
       k.event_package = c.event_package AND (k.event=c.event or k.event IS NULL)  
       INNER JOIN sys.dm_xe_packages p ON p.guid = c.event_package  
    ORDER BY keyword desc, channel, event  
    ```  
  
2.  <span data-ttu-id="4ae93-121">Dans une nouvelle fenêtre de requête, ajoutez les instructions suivantes pour créer une session d’événements, en remplaçant *session_name* par le nom de session à utiliser :</span><span class="sxs-lookup"><span data-stu-id="4ae93-121">In a new query window, add the following statements to create an event session, replacing *session_name* with the session name that you want to use:</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4ae93-122">Les étapes 2 à 6 de cette procédure décrivent chaque section de la définition de session d'événements.</span><span class="sxs-lookup"><span data-stu-id="4ae93-122">Steps 2 through 6 of this procedure describe each section of the event session definition.</span></span> <span data-ttu-id="4ae93-123">Vous devez ajouter toutes les instructions dans une seule fenêtre de requête avant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="4ae93-123">You would add all the statements to a single query window before executing.</span></span> <span data-ttu-id="4ae93-124">Pour obtenir un exemple complet, consultez la section Exemple de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4ae93-124">For a full example, see the Example section of this topic.</span></span>  
  
    ```  
    CREATE EVENT SESSION session_name   
    ON SERVER  
    ```  
  
3.  <span data-ttu-id="4ae93-125">Ajoutez les événements à surveiller, au format *package_name*.*event_name*.</span><span class="sxs-lookup"><span data-stu-id="4ae93-125">Add the events that you want to monitor, in the format *package_name*.*event_name*.</span></span> <span data-ttu-id="4ae93-126">Pour chaque événement, ajoutez une ligne semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="4ae93-126">For each event, add a line similar to the following:</span></span>  
  
    ```  
    ADD EVENT package_name.event_name  
    ```  
  
     <span data-ttu-id="4ae93-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4ae93-127">For example:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed,  
    ADD EVENT sqlserver.file_write_completed  
    ```  
  
4.  <span data-ttu-id="4ae93-128">(Facultatif) Après avoir ajouté un événement, vous pouvez ajouter des actions à entreprendre.</span><span class="sxs-lookup"><span data-stu-id="4ae93-128">(Optional) After you add an event, you can add actions to take.</span></span> <span data-ttu-id="4ae93-129">Vous pouvez également ajouter des prédicats.</span><span class="sxs-lookup"><span data-stu-id="4ae93-129">You can also add predicates.</span></span> <span data-ttu-id="4ae93-130">Les prédicats sont utilisés pour établir des critères pour la consommation des informations d'événements par la cible.</span><span class="sxs-lookup"><span data-stu-id="4ae93-130">Predicates are used to establish criteria for when the event information should be consumed by the target.</span></span> <span data-ttu-id="4ae93-131">Les actions sont ajoutées à l'aide d'une clause ACTION, et les prédicats sont ajoutés à l'aide d'une clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="4ae93-131">Actions are added by using an ACTION clause, and predicates are added by using a WHERE clause.</span></span> <span data-ttu-id="4ae93-132">Par exemple, pour ajouter une action et un prédicat là où le texte [!INCLUDE[tsql](../includes/tsql-md.md)] est capturé pour l’événement sqlserver.file_read_completed, où l’ID de fichier correspond à 1, vous devez inclure l’instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="4ae93-132">For example, to add an action and predicate where the [!INCLUDE[tsql](../includes/tsql-md.md)] text is captured for the sqlserver.file_read_completed event, where the file ID equals 1, you would include the following statement:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed  
       (ACTION (sqlserver.sql_text)  
       WHERE file_id = 1),  
    ```  
  
    -   <span data-ttu-id="4ae93-133">Pour afficher les actions disponibles, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="4ae93-133">To view which actions are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS 'package_name', xo.name AS 'action_name', xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'action'  
        AND (xo.capabilities & 1 = 0   
        OR xo.capabilities IS NULL)  
        ORDER BY p.name, xo.name  
        ```  
  
    -   <span data-ttu-id="4ae93-134">Pour afficher les prédicats disponibles pour un événement, utilisez la requête suivante, en remplaçant *event_name* par le nom de l’événement pour lequel vous souhaitez ajouter un prédicat :</span><span class="sxs-lookup"><span data-stu-id="4ae93-134">To view which predicates are available for an event, use the following query, replacing *event_name* with the name of the event for which you want to add a predicate:</span></span>  
  
        ```  
        SELECT *  
        FROM sys.dm_xe_object_columns  
        WHERE object_name = 'event_name'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="4ae93-135">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4ae93-135">For example:</span></span>  
  
        ```  
        SELECT *   
        FROM sys.dm_xe_object_columns   
        WHERE object_name = 'file_read_completed'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="4ae93-136">Sachez que vous pouvez également ajouter des sources de prédicat globales.</span><span class="sxs-lookup"><span data-stu-id="4ae93-136">Be aware that you can also add global predicate sources.</span></span> <span data-ttu-id="4ae93-137">Une source de prédicat globale peut être utilisée dans toute expression de prédicat.</span><span class="sxs-lookup"><span data-stu-id="4ae93-137">A global predicate source can be used in any predicate expression.</span></span> <span data-ttu-id="4ae93-138">Pour afficher les sources de prédicat globales disponibles, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="4ae93-138">To view which global predicate sources are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS package_name, xo.name AS predicate_name  
           , xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'pred_source'  
        ORDER BY p.name, xo.name  
        ```  
  
         <span data-ttu-id="4ae93-139">Par exemple, vous pouvez utiliser l'expression de prédicat suivante pour spécifier que les données doivent uniquement être collectées pour un événement les cinq premières fois qu'un événement se produit.</span><span class="sxs-lookup"><span data-stu-id="4ae93-139">For example, you could use the following predicate expression to specify that data should only be collected for an event the first five times that an event occurs.</span></span>  
  
        ```  
        WHERE package0.counter <= 5  
        ```  
  
5.  <span data-ttu-id="4ae93-140">Ajoutez la cible souhaitée, où les données d'événement seront traitées et consommées.</span><span class="sxs-lookup"><span data-stu-id="4ae93-140">Add the desired target, where the event data will be processed and consumed.</span></span> <span data-ttu-id="4ae93-141">Utilisez le format suivant :</span><span class="sxs-lookup"><span data-stu-id="4ae93-141">Use the following format:</span></span>  
  
    ```  
    ADD TARGET package_name.target_name  
    ```  
  
     <span data-ttu-id="4ae93-142">L'exemple suivant ajoute la cible de fichier asynchrone :</span><span class="sxs-lookup"><span data-stu-id="4ae93-142">The following example adds the asynchronous file target:</span></span>  
  
    ```  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
    ```  
  
     <span data-ttu-id="4ae93-143">Pour consulter la liste de cibles disponibles, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="4ae93-143">To view the list of available targets, use the following query:</span></span>  
  
    ```  
    SELECT p.name AS 'package_name', xo.name AS 'target_name'  
       , xo.description, xo.object_type   
    FROM sys.dm_xe_objects AS xo  
    JOIN sys.dm_xe_packages AS p  
       ON xo.package_guid = p.guid  
    WHERE xo.object_type = 'target'  
    AND (xo.capabilities & 1 = 0  
    OR xo.capabilities IS NULL)  
    ORDER BY p.name, xo.name  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ae93-144">Pour plus d’informations sur les différents types de cible, consultez [Cibles des événements étendus SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="4ae93-144">For information about the different target types, see [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span></span>  
  
6.  <span data-ttu-id="4ae93-145">Examinez et ajoutez toutes options de configuration supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="4ae93-145">Review and add any additional configuration options.</span></span> <span data-ttu-id="4ae93-146">Par exemple, vous pouvez configurer des options telles que le mode de rétention d'événement, le mode de mise en mémoire tampon des longs événements, ou si la session d'événements doit démarrer automatiquement au démarrage de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ae93-146">For example, you can configure options such as the event retention mode, how long events are buffered in memory, or whether the event session should start automatically when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="4ae93-147">Les options sont décrites dans la rubrique [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4ae93-147">The options are described in the topic [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span></span> <span data-ttu-id="4ae93-148">N’oubliez pas que les valeurs par défaut sont affectées si ces options ne sont pas spécifiées.</span><span class="sxs-lookup"><span data-stu-id="4ae93-148">Be aware that default values are assigned if these options are not specified.</span></span>  
  
7.  <span data-ttu-id="4ae93-149">Démarrez la session.</span><span class="sxs-lookup"><span data-stu-id="4ae93-149">Start the session.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ae93-150">Pour plus d’informations sur la consultation des résultats de session, reportez-vous à la rubrique correspondant au type de cible que vous avez utilisé dans le nœud [Cibles des événements étendus SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) de la documentation en ligne.</span><span class="sxs-lookup"><span data-stu-id="4ae93-150">For more information about how to view the session results, see the corresponding topic for the target type that you used in the [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) node of Books Online.</span></span>  
  
 <span data-ttu-id="4ae93-151">L'exemple suivant crée une session d'événements étendus nommée IOActivity qui capture les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4ae93-151">The following example creates an Extended Events session named IOActivity that captures the following information:</span></span>  
  
-   <span data-ttu-id="4ae93-152">des données d'événement pour les lectures de fichier achevées, notamment le texte [!INCLUDE[tsql](../includes/tsql-md.md)] associé pour les lectures de fichier où l'ID de fichier correspond à 1 ;</span><span class="sxs-lookup"><span data-stu-id="4ae93-152">Event data for completed file reads, including the associated [!INCLUDE[tsql](../includes/tsql-md.md)] text for file reads where the file ID is equal to 1.</span></span>  
  
-   <span data-ttu-id="4ae93-153">des données d'événement pour les écritures de fichier achevées ;</span><span class="sxs-lookup"><span data-stu-id="4ae93-153">Event data for completed file writes.</span></span>  
  
-   <span data-ttu-id="4ae93-154">des données d'événement relatives à l'écriture des données du cache du journal dans le fichier journal physique ;</span><span class="sxs-lookup"><span data-stu-id="4ae93-154">Event data for when data is written from the log cache to the physical log file.</span></span>  
  
 <span data-ttu-id="4ae93-155">La session envoie la sortie à une cible de fichier.</span><span class="sxs-lookup"><span data-stu-id="4ae93-155">The session sends the output to a file target.</span></span>  
  
```  
CREATE EVENT SESSION IOActivity  
ON SERVER  
  
ADD EVENT sqlserver.file_read_completed  
   (  
   ACTION (sqlserver.sql_text)  
   WHERE file_id = 1),  
ADD EVENT sqlserver.file_write_completed,  
ADD EVENT sqlserver.databases_log_flush  
  
ADD TARGET package0.asynchronous_file_target   
   (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ae93-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ae93-156">See Also</span></span>  
 <span data-ttu-id="4ae93-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ae93-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="4ae93-158">[Cibles des Événements étendus SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="4ae93-158">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 [<span data-ttu-id="4ae93-159">Packages d’événements étendus SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ae93-159">SQL Server Extended Events Packages</span></span>](../relational-databases/extended-events/sql-server-extended-events-packages.md)  
  
  
