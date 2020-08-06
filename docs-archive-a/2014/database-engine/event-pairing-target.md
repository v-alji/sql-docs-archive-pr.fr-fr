---
title: Cible d’appariement des événements | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- pairing target [SQL Server extended events]
- event pairing target
- targets [SQL Server extended events], pairing target
ms.assetid: 3c87dcfb-543a-4bd8-a73d-1390bdf4ffa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a1a6beb1c6996e6e12f16c4555fd9dfcab97617d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701603"
---
# <a name="event-pairing-target"></a><span data-ttu-id="3be17-102">Cible d'appariement d'événements</span><span class="sxs-lookup"><span data-stu-id="3be17-102">Event Pairing Target</span></span>
  <span data-ttu-id="3be17-103">La cible d'appariement d'événements correspond à deux événements qui utilisent une ou plusieurs colonnes de données qui sont présentes dans chaque événement.</span><span class="sxs-lookup"><span data-stu-id="3be17-103">The event pairing target matches two events using one or more columns of data that are present in each event.</span></span> <span data-ttu-id="3be17-104">De nombreux événements se présentent sous forme de paires, tels que les acquisitions et les libérations de verrous.</span><span class="sxs-lookup"><span data-stu-id="3be17-104">Many events come in pairs, for example, lock acquires and lock releases.</span></span> <span data-ttu-id="3be17-105">Une fois qu'une séquence d'événement a été couplée, les deux événements sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="3be17-105">After an event sequence is paired, both events are discarded.</span></span> <span data-ttu-id="3be17-106">Ignorer des jeux correspondants permet de détecter facilement les acquisitions de verrous qui n'ont pas été libérées.</span><span class="sxs-lookup"><span data-stu-id="3be17-106">Discarding matched sets allows for easy detection of lock acquisitions that have not been released.</span></span>  
  
 <span data-ttu-id="3be17-107">Grâce aux filtres au niveau des événements, la cible d'appariement peut être utilisée pour capturer uniquement les événements qui ne correspondent pas aux critères prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="3be17-107">By using event-level filters, the pairing target can be used to only capture events that do not match pre-set criteria.</span></span>  
  
 <span data-ttu-id="3be17-108">Lorsque vous utilisez la cible d'appariement d'événements, vous pouvez choisir deux événements à associer, ainsi qu'une séquence de colonnes sur lesquelles s'effectuera la correspondance.</span><span class="sxs-lookup"><span data-stu-id="3be17-108">When you use the event pairing target, you can choose two events that will be matched, together with a sequence of columns to perform the matching on.</span></span> <span data-ttu-id="3be17-109">Toutes les colonnes dans cette séquence doivent être du même type.</span><span class="sxs-lookup"><span data-stu-id="3be17-109">All the columns in this sequence must be of the same type.</span></span>  
  
 <span data-ttu-id="3be17-110">Le tableau suivant décrit les options disponibles pour configurer l'appariement d'événements.</span><span class="sxs-lookup"><span data-stu-id="3be17-110">The following table describes the available options for configuring event pairing.</span></span>  
  
|<span data-ttu-id="3be17-111">Option</span><span class="sxs-lookup"><span data-stu-id="3be17-111">Option</span></span>|<span data-ttu-id="3be17-112">Valeurs autorisées</span><span class="sxs-lookup"><span data-stu-id="3be17-112">Allowed values</span></span>|<span data-ttu-id="3be17-113">Description</span><span class="sxs-lookup"><span data-stu-id="3be17-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="3be17-114">begin_event</span><span class="sxs-lookup"><span data-stu-id="3be17-114">begin_event</span></span>|<span data-ttu-id="3be17-115">Tout nom d'événement qui est présent dans la session active.</span><span class="sxs-lookup"><span data-stu-id="3be17-115">Any event name that is present in the current session.</span></span>|<span data-ttu-id="3be17-116">Le nom d'événement qui spécifie l'événement de début dans une séquence couplée.</span><span class="sxs-lookup"><span data-stu-id="3be17-116">The event name specifying the beginning event in a paired sequence.</span></span>|  
|<span data-ttu-id="3be17-117">end_event</span><span class="sxs-lookup"><span data-stu-id="3be17-117">end_event</span></span>|<span data-ttu-id="3be17-118">Tout nom d'événement qui est présent dans la session active.</span><span class="sxs-lookup"><span data-stu-id="3be17-118">Any event name that is present in the current session.</span></span>|<span data-ttu-id="3be17-119">Le nom d'événement qui spécifie l'événement de fin dans une séquence couplée.</span><span class="sxs-lookup"><span data-stu-id="3be17-119">The event name specifying the ending event in a paired sequence.</span></span>|  
|<span data-ttu-id="3be17-120">begin_matching_columns</span><span class="sxs-lookup"><span data-stu-id="3be17-120">begin_matching_columns</span></span>|<span data-ttu-id="3be17-121">Une liste ordonnée de noms de colonnes séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="3be17-121">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="3be17-122">Les colonnes sur lesquelles effectuer la correspondance.</span><span class="sxs-lookup"><span data-stu-id="3be17-122">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="3be17-123">end_matching_columns</span><span class="sxs-lookup"><span data-stu-id="3be17-123">end_matching_columns</span></span>|<span data-ttu-id="3be17-124">Une liste ordonnée de noms de colonnes séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="3be17-124">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="3be17-125">Les colonnes sur lesquelles effectuer la correspondance.</span><span class="sxs-lookup"><span data-stu-id="3be17-125">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="3be17-126">begin_matching_actions</span><span class="sxs-lookup"><span data-stu-id="3be17-126">begin_matching_actions</span></span>|<span data-ttu-id="3be17-127">Liste ordonnée d'actions séparées par des virgules.</span><span class="sxs-lookup"><span data-stu-id="3be17-127">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="3be17-128">Actions sur lesquelles effectuer la correspondance.</span><span class="sxs-lookup"><span data-stu-id="3be17-128">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="3be17-129">end_matching_actions</span><span class="sxs-lookup"><span data-stu-id="3be17-129">end_matching_actions</span></span>|<span data-ttu-id="3be17-130">Liste ordonnée d'actions séparées par des virgules.</span><span class="sxs-lookup"><span data-stu-id="3be17-130">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="3be17-131">Actions sur lesquelles effectuer la correspondance.</span><span class="sxs-lookup"><span data-stu-id="3be17-131">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="3be17-132">respond_to_memory_pressure</span><span class="sxs-lookup"><span data-stu-id="3be17-132">respond_to_memory_pressure</span></span>|<span data-ttu-id="3be17-133">Une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3be17-133">One of the following values:</span></span><br /><br /> <span data-ttu-id="3be17-134">0 = ne pas répondre.</span><span class="sxs-lookup"><span data-stu-id="3be17-134">0 = Do not respond.</span></span><br /><br /> <span data-ttu-id="3be17-135">1 = arrêter d'ajouter de nouveaux orphelins à la liste en cas de sollicitation de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="3be17-135">1 = Stop adding new orphans to the list when there is memory pressure.</span></span>|<span data-ttu-id="3be17-136">La réponse cible aux événements de mémoire.</span><span class="sxs-lookup"><span data-stu-id="3be17-136">The target response to memory events.</span></span> <span data-ttu-id="3be17-137">Si la valeur spécifiée est 1 et que la mémoire du serveur est insuffisante, les informations non couplées qui sont conservées sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="3be17-137">If set to 1 and the server is low on memory, unpaired information that is being maintained is removed.</span></span>|  
|<span data-ttu-id="3be17-138">max_orphans</span><span class="sxs-lookup"><span data-stu-id="3be17-138">max_orphans</span></span>||<span data-ttu-id="3be17-139">Spécifie le nombre total d'événements non couplés qui seront collectés dans la cible.</span><span class="sxs-lookup"><span data-stu-id="3be17-139">Specifies the total number of unpaired events that will be collected in the target.</span></span> <span data-ttu-id="3be17-140">Une fois la limite atteinte, les événements non couplés sont supprimés selon le principe FIFO (premier entré/premier sorti).</span><span class="sxs-lookup"><span data-stu-id="3be17-140">Once the limit is reached, unpaired events are removed on a first-in, first-out (FIFO) basis.</span></span> <span data-ttu-id="3be17-141">Par défaut = 10,000.</span><span class="sxs-lookup"><span data-stu-id="3be17-141">Default = 10,000.</span></span>|  
  
 <span data-ttu-id="3be17-142">Toutes les données associées à un événement sont capturées et stockées pour un appariement futur.</span><span class="sxs-lookup"><span data-stu-id="3be17-142">All the data associated with an event is captured and stored for future pairing.</span></span> <span data-ttu-id="3be17-143">De plus, les données ajoutées par les actions sont également collectées.</span><span class="sxs-lookup"><span data-stu-id="3be17-143">In addition, data added by actions is also collected.</span></span> <span data-ttu-id="3be17-144">Les données d'événement collectées sont stockées en mémoire et ont donc une limite finie.</span><span class="sxs-lookup"><span data-stu-id="3be17-144">The collected event data is stored in memory, and therefore has a finite limit.</span></span> <span data-ttu-id="3be17-145">Cette limite est basée sur la capacité et l'activité du système.</span><span class="sxs-lookup"><span data-stu-id="3be17-145">This limit is based on system capacity and activity.</span></span> <span data-ttu-id="3be17-146">Plutôt que prendre la quantité maximale de mémoire à utiliser comme paramètre, la quantité de mémoire utilisée sera basée sur les ressources système disponibles.</span><span class="sxs-lookup"><span data-stu-id="3be17-146">Instead of taking the maximum amount of memory to be used as a parameter, the amount of memory used will be based on available system resources.</span></span> <span data-ttu-id="3be17-147">Lorsque celles-ci ne sont pas disponibles, les événements non couplés qui ont été conservés seront supprimés.</span><span class="sxs-lookup"><span data-stu-id="3be17-147">When these are not available, unpaired events that have been retained will be dropped.</span></span> <span data-ttu-id="3be17-148">Si un événement n'a pas été couplé et est supprimé, l'événement correspondant apparaîtra comme un événement non couplé.</span><span class="sxs-lookup"><span data-stu-id="3be17-148">If an event has not been paired and is dropped, the matching event will appear as an unpaired event.</span></span>  
  
 <span data-ttu-id="3be17-149">La cible d'appariement applique en série des événements non couplés à un format XML.</span><span class="sxs-lookup"><span data-stu-id="3be17-149">The pairing target serializes unpaired events to an XML format.</span></span> <span data-ttu-id="3be17-150">Ce format n'est conforme à aucun schéma.</span><span class="sxs-lookup"><span data-stu-id="3be17-150">This format does not conform to any schema.</span></span> <span data-ttu-id="3be17-151">Le format contient uniquement deux types d'éléments.</span><span class="sxs-lookup"><span data-stu-id="3be17-151">The format only contains two element types.</span></span> <span data-ttu-id="3be17-152">L' **\<unpaired>** élément est la racine, suivi de un.</span><span class="sxs-lookup"><span data-stu-id="3be17-152">The **\<unpaired>** element is the root, followed by one.</span></span> <span data-ttu-id="3be17-153">**\<event>** élément pour chaque événement non couplé qui fait actuellement l’objet d’un suivi.</span><span class="sxs-lookup"><span data-stu-id="3be17-153">**\<event>** element for each unpaired event that is currently being tracked.</span></span> <span data-ttu-id="3be17-154">L' **\<event>** élément contient un attribut qui contient le nom de l’événement non couplé.</span><span class="sxs-lookup"><span data-stu-id="3be17-154">The **\<event>** element contains one attribute that contains the name of the unpaired event.</span></span>  
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="3be17-155">Ajout de la cible à une session</span><span class="sxs-lookup"><span data-stu-id="3be17-155">Adding the Target to a Session</span></span>  
 <span data-ttu-id="3be17-156">Pour ajouter la paire cible correspondante à une session Événements étendus lorsque vous créez ou modifiez une session d'événements, vous devez inclure l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="3be17-156">To add the pair matching target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```  
ADD TARGET package0.pair_matching   
```  
  
 <span data-ttu-id="3be17-157">Vous la ferez suivre d'une instruction SET pour définir les événements de début et de fin, ainsi que les actions ou les colonnes correspondantes.</span><span class="sxs-lookup"><span data-stu-id="3be17-157">You would follow this with a SET statement, to define the beginning and ending events, and which actions or columns to match.</span></span> <span data-ttu-id="3be17-158">Voici un exemple de syntaxe pour l’appariement des événements sqlserver.lock_acquired et sqlserver.lock_released.</span><span class="sxs-lookup"><span data-stu-id="3be17-158">The following example shows sample syntax for pair matching the sqlserver.lock_acquired and sqlserver.lock_released events.</span></span>  
  
```  
   ( SET begin_event = 'sqlserver.lock_acquired',  
      begin_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
      end_event = 'sqlserver.lock_released',  
      end_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
   respond_to_memory_pressure = 1)  
```  
  
 <span data-ttu-id="3be17-159">Pour plus d’informations, consultez [Déterminer quelles requêtes détiennent des verrous](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span><span class="sxs-lookup"><span data-stu-id="3be17-159">For more information, see [Determine Which Queries Are Holding Locks](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span></span>  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="3be17-160">Vérification de la sortie cible</span><span class="sxs-lookup"><span data-stu-id="3be17-160">Reviewing the Target Output</span></span>  
 <span data-ttu-id="3be17-161">Pour vérifier la sortie de la cible d’appariement, vous pouvez utiliser la requête suivante, en remplaçant *nom_session* par le nom de la session d’événements.</span><span class="sxs-lookup"><span data-stu-id="3be17-161">To review the output for the pair matching target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```  
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="3be17-162">L'exemple suivant montre le format de sortie de la cible d'appariement.</span><span class="sxs-lookup"><span data-stu-id="3be17-162">The following example shows the pairing target output format.</span></span>  
  
```  
<unpaired truncated = "0" matchedCount = "[matched count]" memoryPressureDroppedCount = " [lost count]">  
    <event name  = "[event name]" package = "[package]" id= "[event ID value]" version = "[event version]">  
    <data name = "[column name]">   
    <type name = "[column type]" package = "[type package]" />   
    <value>[column value]</value>  
    <text value>[text value]</text>>  
        </data>  
    </event>  
</unpaired>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3be17-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3be17-163">See Also</span></span>  
 <span data-ttu-id="3be17-164">[Cibles des Événements étendus SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="3be17-164">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="3be17-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3be17-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span></span>  
 <span data-ttu-id="3be17-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3be17-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="3be17-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3be17-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-event-session-transact-sql)  
  
  
