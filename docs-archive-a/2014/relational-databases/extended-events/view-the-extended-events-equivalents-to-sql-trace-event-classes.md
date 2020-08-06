---
title: Consulter les événements étendus équivalents aux classes d’événements Trace SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, extended events equivalents
- extended events [SQL Server], SQL Trace equivalents
- extended events [SQL Server], user configurable events
ms.assetid: 7f24104c-201d-4361-9759-f78a27936011
author: rothja
ms.author: jroth
ms.openlocfilehash: 37459359f9f6cb7e3951b705c4007477ec43e36a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695603"
---
# <a name="view-the-extended-events-equivalents-to-sql-trace-event-classes"></a><span data-ttu-id="a0193-102">Consulter les Événements étendus équivalents aux classes d’événements Trace SQL</span><span class="sxs-lookup"><span data-stu-id="a0193-102">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>
  <span data-ttu-id="a0193-103">Si vous souhaitez utiliser Événements étendus pour recueillir des données d'événement qui sont équivalentes aux classes et colonnes d'événements Trace SQL, il est utile de comprendre comment les événements Trace SQL sont mappés aux événements et actions Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="a0193-103">If you want to use Extended Events to collect event data that is equivalent to SQL Trace event classes and columns, it is useful to understand how the SQL Trace events map to Extended Events events and actions.</span></span>  
  
 <span data-ttu-id="a0193-104">Vous pouvez utiliser la procédure suivante pour consulter les événements et actions Événements étendus équivalents à chaque événement Trace SQL et à ses colonnes associées.</span><span class="sxs-lookup"><span data-stu-id="a0193-104">You can use the following procedure to view the Extended Events events and actions that are equivalent to each SQL Trace event and its associated columns.</span></span>  
  
## <a name="to-view-the-extended-events-equivalents-to-sql-trace-events-using-query-editor"></a><span data-ttu-id="a0193-105">Pour afficher les événements étendus équivalents aux événements Trace SQL à l'aide de l'éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="a0193-105">To view the Extended Events equivalents to SQL Trace events using Query Editor</span></span>  
  
-   <span data-ttu-id="a0193-106">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], exécutez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="a0193-106">From Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], run the following query:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    SELECT DISTINCT  
       tb.trace_event_id,  
       te.name AS 'Event Class',  
       em.package_name AS 'Package',  
       em.xe_event_name AS 'XEvent Name',  
       tb.trace_column_id,  
       tc.name AS 'SQL Trace Column',  
       am.xe_action_name as 'Extended Events action'  
    FROM (sys.trace_events te LEFT OUTER JOIN sys.trace_xe_event_map em  
       ON te.trace_event_id = em.trace_event_id) LEFT OUTER JOIN sys.trace_event_bindings tb  
       ON em.trace_event_id = tb.trace_event_id LEFT OUTER JOIN sys.trace_columns tc  
       ON tb.trace_column_id = tc.trace_column_id LEFT OUTER JOIN sys.trace_xe_action_map am  
       ON tc.trace_column_id = am.trace_column_id  
    ORDER BY te.name, tc.name  
    ```  
  
 <span data-ttu-id="a0193-107">Lorsque vous affichez les résultats, gardez présentes à l'esprit les considérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a0193-107">When you view the results, note the following:</span></span>  
  
-   <span data-ttu-id="a0193-108">Si toutes les colonnes retournent NULL à l’exception de la colonne Event Class, cela indique que la classe d’événements n’a pas été migrée à partir de Trace SQL.</span><span class="sxs-lookup"><span data-stu-id="a0193-108">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="a0193-109">Si seule la valeur de la colonne Extended Events est NULL, cela indique que l’une des conditions suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="a0193-109">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="a0193-110">La colonne Trace SQL mappe à l'un des champs de données associé à l'événement Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="a0193-110">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a0193-111">Chaque événement Événements étendus a un jeu par défaut des champs de données inclus automatiquement dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="a0193-111">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="a0193-112">La colonne d'action n'a pas d'équivalent Événements étendus explicite.</span><span class="sxs-lookup"><span data-stu-id="a0193-112">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="a0193-113">Citons par exemple la colonne EventClass dans Trace SQL.</span><span class="sxs-lookup"><span data-stu-id="a0193-113">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="a0193-114">Cette colonne n'est pas nécessaire dans Événements étendus, car le nom d'événement est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a0193-114">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="a0193-115">Pour les classes d’événements Trace SQL utilisateur configurables (UserConfigurable:1 via UserConfigurable:9), les événements étendus utilisent un événement unique pour les remplacer.</span><span class="sxs-lookup"><span data-stu-id="a0193-115">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="a0193-116">L’événement se nomme user_event.</span><span class="sxs-lookup"><span data-stu-id="a0193-116">The event is named user_event.</span></span> <span data-ttu-id="a0193-117">Cet événement est déclenché à l’aide de sp_trace_generateevent, qui est la même procédure stockée que celle utilisée par Trace SQL.</span><span class="sxs-lookup"><span data-stu-id="a0193-117">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="a0193-118">L’événement user_event est retourné indépendamment de l’ID d’événement passé à la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a0193-118">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="a0193-119">Toutefois, un champ event_id est retourné dans les données d’événement.</span><span class="sxs-lookup"><span data-stu-id="a0193-119">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="a0193-120">Cela vous permet de générer un prédicat basé sur l'ID d'événement.</span><span class="sxs-lookup"><span data-stu-id="a0193-120">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="a0193-121">Par exemple, si vous utilisez UserConfigurable:0 (ID d’événement : 82) dans le code, vous pouvez ajouter l’événement user_event à la session et spécifier un prédicat 'event_id = 82'.</span><span class="sxs-lookup"><span data-stu-id="a0193-121">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="a0193-122">Par conséquent, vous n’avez pas à modifier le code parce que la procédure stockée sp_trace_generateevent génère l’événement user_event des événements étendus, et la classe d’événements Trace SQL équivalente.</span><span class="sxs-lookup"><span data-stu-id="a0193-122">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
-   <span data-ttu-id="a0193-123">Si toutes les colonnes retournent NULL à l’exception de la colonne Event Class, cela indique que la classe d’événements n’a pas été migrée à partir de Trace SQL.</span><span class="sxs-lookup"><span data-stu-id="a0193-123">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="a0193-124">Si seule la valeur de la colonne Extended Events est NULL, cela indique que l’une des conditions suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="a0193-124">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="a0193-125">La colonne Trace SQL mappe à l'un des champs de données associé à l'événement Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="a0193-125">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a0193-126">Chaque événement Événements étendus a un jeu par défaut des champs de données inclus automatiquement dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="a0193-126">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="a0193-127">La colonne d'action n'a pas d'équivalent Événements étendus explicite.</span><span class="sxs-lookup"><span data-stu-id="a0193-127">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="a0193-128">Citons par exemple la colonne EventClass dans Trace SQL.</span><span class="sxs-lookup"><span data-stu-id="a0193-128">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="a0193-129">Cette colonne n'est pas nécessaire dans Événements étendus, car le nom d'événement est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a0193-129">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="a0193-130">Pour les classes d’événements Trace SQL utilisateur configurables (UserConfigurable:1 via UserConfigurable:9), les événements étendus utilisent un événement unique pour les remplacer.</span><span class="sxs-lookup"><span data-stu-id="a0193-130">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="a0193-131">L’événement se nomme user_event.</span><span class="sxs-lookup"><span data-stu-id="a0193-131">The event is named user_event.</span></span> <span data-ttu-id="a0193-132">Cet événement est déclenché à l’aide de sp_trace_generateevent, qui est la même procédure stockée que celle utilisée par Trace SQL.</span><span class="sxs-lookup"><span data-stu-id="a0193-132">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="a0193-133">L’événement user_event est retourné indépendamment de l’ID d’événement passé à la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a0193-133">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="a0193-134">Toutefois, un champ event_id est retourné dans les données d’événement.</span><span class="sxs-lookup"><span data-stu-id="a0193-134">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="a0193-135">Cela vous permet de générer un prédicat basé sur l'ID d'événement.</span><span class="sxs-lookup"><span data-stu-id="a0193-135">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="a0193-136">Par exemple, si vous utilisez UserConfigurable:0 (ID d’événement : 82) dans le code, vous pouvez ajouter l’événement user_event à la session et spécifier un prédicat 'event_id = 82'.</span><span class="sxs-lookup"><span data-stu-id="a0193-136">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="a0193-137">Par conséquent, vous n’avez pas à modifier le code parce que la procédure stockée sp_trace_generateevent génère l’événement user_event des événements étendus, et la classe d’événements Trace SQL équivalente.</span><span class="sxs-lookup"><span data-stu-id="a0193-137">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0193-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0193-138">See Also</span></span>  
 [<span data-ttu-id="a0193-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a0193-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)  
  
  
