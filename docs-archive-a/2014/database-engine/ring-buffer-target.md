---
title: Cible de mémoire tampon en anneau | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events], ring buffer target
- ring buffer target [SQL Server extended events]
ms.assetid: 54494e11-b56b-43b7-aa5e-c8724e56b251
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 186e847bb9f9b621543119c25510dc5d6107e274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613110"
---
# <a name="ring-buffer-target"></a><span data-ttu-id="c3f25-102">Cible de mémoire tampon en anneau</span><span class="sxs-lookup"><span data-stu-id="c3f25-102">Ring Buffer Target</span></span>
  <span data-ttu-id="c3f25-103">La cible de mémoire tampon en anneau maintient brièvement les données d'événements en mémoire.</span><span class="sxs-lookup"><span data-stu-id="c3f25-103">The ring buffer target briefly holds event data in memory.</span></span> <span data-ttu-id="c3f25-104">Cette cible peut gérer des événements dans deux modes différents.</span><span class="sxs-lookup"><span data-stu-id="c3f25-104">This target can manage events in one of two modes.</span></span>  
  
-   <span data-ttu-id="c3f25-105">Le premier mode est le mode FIFO strict (premier entré, premier sorti), où l'événement le plus ancien est supprimé lorsque toute la mémoire allouée à la cible est utilisée.</span><span class="sxs-lookup"><span data-stu-id="c3f25-105">The first mode is strict first-in first-out (FIFO), where the oldest event is discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="c3f25-106">Dans ce mode (par défaut), l'option occurrence_number a la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="c3f25-106">In this mode (the default), the occurrence_number option is set to 0.</span></span>  
  
-   <span data-ttu-id="c3f25-107">Le deuxième mode est le mode FIFO par événement, où un nombre spécifié d'événements de chaque type est conservé.</span><span class="sxs-lookup"><span data-stu-id="c3f25-107">The second mode is per-event FIFO, where a specified number of events of each type is kept.</span></span> <span data-ttu-id="c3f25-108">Dans ce mode, les événements les plus anciens de chaque type sont ignorés lorsque toute la mémoire allouée à la cible est utilisée.</span><span class="sxs-lookup"><span data-stu-id="c3f25-108">In this mode, the oldest events of each type are discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="c3f25-109">Vous pouvez configurer l'option occurrence_number pour spécifier le nombre d'événements de chaque type à conserver.</span><span class="sxs-lookup"><span data-stu-id="c3f25-109">You can configure the occurrence_number option to specify the number of events of each type to keep.</span></span>  
  
 <span data-ttu-id="c3f25-110">Le tableau suivant décrit les options disponibles pour configurer la cible de mémoire tampon en anneau.</span><span class="sxs-lookup"><span data-stu-id="c3f25-110">The following table describes the available options for configuring the ring buffer target.</span></span>  
  
|<span data-ttu-id="c3f25-111">Option</span><span class="sxs-lookup"><span data-stu-id="c3f25-111">Option</span></span>|<span data-ttu-id="c3f25-112">Valeurs autorisées</span><span class="sxs-lookup"><span data-stu-id="c3f25-112">Allowed values</span></span>|<span data-ttu-id="c3f25-113">Description</span><span class="sxs-lookup"><span data-stu-id="c3f25-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="c3f25-114">max_memory</span><span class="sxs-lookup"><span data-stu-id="c3f25-114">max_memory</span></span>|<span data-ttu-id="c3f25-115">Tout entier 32 bits.</span><span class="sxs-lookup"><span data-stu-id="c3f25-115">Any 32-bit integer.</span></span> <span data-ttu-id="c3f25-116">Cette valeur est facultative.</span><span class="sxs-lookup"><span data-stu-id="c3f25-116">This value is optional.</span></span>|<span data-ttu-id="c3f25-117">Quantité de mémoire maximale, en kilo-octet (Ko), à utiliser.</span><span class="sxs-lookup"><span data-stu-id="c3f25-117">The maximum amount of memory in kilobytes (KB) to use.</span></span> <span data-ttu-id="c3f25-118">Des événements existants sont supprimés en fonction de la limite qui est atteinte en premier : max_event_limit ou max_memory.</span><span class="sxs-lookup"><span data-stu-id="c3f25-118">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="c3f25-119">La valeur maximale est de 4194303 Ko.</span><span class="sxs-lookup"><span data-stu-id="c3f25-119">The maximum value is 4194303 KB.</span></span> <span data-ttu-id="c3f25-120">Avant de définir la taille de la mémoire tampon en anneau sur les limites de la plage Go, il convient de tenir compte de la taille de la mémoire tampon en mémoire, car cela peut avoir un impact sur les autres SQL Server consommateurs</span><span class="sxs-lookup"><span data-stu-id="c3f25-120">A careful consideration should be made before setting the ring buffer size to limits in the GB range as it may impact other memory consumers in SQL Server</span></span>|  
|<span data-ttu-id="c3f25-121">max_event_limit</span><span class="sxs-lookup"><span data-stu-id="c3f25-121">max_event_limit</span></span>|<span data-ttu-id="c3f25-122">Tout entier 32 bits.</span><span class="sxs-lookup"><span data-stu-id="c3f25-122">Any 32-bit integer.</span></span> <span data-ttu-id="c3f25-123">Cette valeur est facultative.</span><span class="sxs-lookup"><span data-stu-id="c3f25-123">This value is optional.</span></span>|<span data-ttu-id="c3f25-124">Nombre maximal d'événements conservés dans le tampon ring_buffer.</span><span class="sxs-lookup"><span data-stu-id="c3f25-124">The maximum number of events kept in the ring_buffer.</span></span> <span data-ttu-id="c3f25-125">Des événements existants sont supprimés en fonction de la limite qui est atteinte en premier : max_event_limit ou max_memory.</span><span class="sxs-lookup"><span data-stu-id="c3f25-125">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="c3f25-126">Par défaut = 1000.</span><span class="sxs-lookup"><span data-stu-id="c3f25-126">Default = 1000.</span></span>|  
|<span data-ttu-id="c3f25-127">occurrence_number</span><span class="sxs-lookup"><span data-stu-id="c3f25-127">occurrence_number</span></span>|<span data-ttu-id="c3f25-128">Une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3f25-128">One of the following values:</span></span><br /><br /> <span data-ttu-id="c3f25-129">0 (par défaut) = l'événement le plus ancien est supprimé lorsque toute la mémoire allouée à la cible est utilisée.</span><span class="sxs-lookup"><span data-stu-id="c3f25-129">0 (the default) = Oldest event is discarded when all the memory allocated to the target is used.</span></span><br /><br /> <span data-ttu-id="c3f25-130">Tout entier 32 bits = le nombre d’événements de chaque type à conserver avant d’être éliminés par événement FIFO.</span><span class="sxs-lookup"><span data-stu-id="c3f25-130">Any 32-bit integer = The number of events of each type to keep before being discarded on a per-event FIFO basis.</span></span><br /><br /> <br /><br /> <span data-ttu-id="c3f25-131">Cette valeur est facultative.</span><span class="sxs-lookup"><span data-stu-id="c3f25-131">This value is optional.</span></span>|<span data-ttu-id="c3f25-132">Le mode FIFO à utiliser et, s'il est supérieur à 0, le nombre d'événements préférés de chaque type à conserver dans la mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="c3f25-132">The FIFO mode to use, and, if set to a value greater than 0, the preferred number of events of each type to keep in the buffer.</span></span>|
| &nbsp; | &nbsp; | &nbsp; |
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="c3f25-133">Ajout de la cible à une session</span><span class="sxs-lookup"><span data-stu-id="c3f25-133">Adding the Target to a Session</span></span>  
 <span data-ttu-id="c3f25-134">Pour ajouter la cible de mémoire tampon en anneau à une session Événements étendus lorsque vous créez ou modifiez une session d'événements, vous devez inclure l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="c3f25-134">To add the ring buffer target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```sql
ADD TARGET package0.ring_buffer  
```  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="c3f25-135">Vérification de la sortie cible</span><span class="sxs-lookup"><span data-stu-id="c3f25-135">Reviewing the Target Output</span></span>  
 <span data-ttu-id="c3f25-136">Pour vérifier la sortie de la cible de mémoire tampon en anneau, vous pouvez utiliser la requête suivante, en remplaçant *session_name* par le nom de la session d’événements.</span><span class="sxs-lookup"><span data-stu-id="c3f25-136">To review the output from the ring buffer target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```sql
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="c3f25-137">L'exemple suivant montre le format de sortie de la cible de mémoire tampon en anneau.</span><span class="sxs-lookup"><span data-stu-id="c3f25-137">The following example shows the ring buffer target output format.</span></span>  
  
```  
<RingBufferTarget eventsPerSec="" processingTime="" totalEventsProcessed="" eventCount="" droppedCount="" memoryUsed="">  
 <event name="" package="" id="" version="" timestamp="">  
    <data name="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </data>  
    <action name="" package="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </action>  
  </event>  
</RingBufferTarget>  
```


## <a name="see-also"></a><span data-ttu-id="c3f25-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3f25-138">See Also</span></span>

- [<span data-ttu-id="c3f25-139">Cibles des Événements étendus SQL Server</span><span class="sxs-lookup"><span data-stu-id="c3f25-139">SQL Server Extended Events Targets</span></span>](../../2014/database-engine/sql-server-extended-events-targets.md)
- [<span data-ttu-id="c3f25-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3f25-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="c3f25-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3f25-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-session-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="c3f25-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3f25-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](https://docs.microsoft.com/sql/t-sql/statements/alter-event-session-transact-sql?view=sql-server-2016)

