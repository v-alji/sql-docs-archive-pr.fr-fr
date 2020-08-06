---
title: Cible de compteur d’événements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- synchronous event counter target [SQL Server extended events]
- targets [SQL Server extended events], synchronous event counter target
ms.assetid: 342e08d1-dcca-4a71-ae64-cb61b55b85bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f540f39176ec638cdc9236b315e306ecebfdcb1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701615"
---
# <a name="event-counter-target"></a><span data-ttu-id="28644-102">Cible de compteur d'événements</span><span class="sxs-lookup"><span data-stu-id="28644-102">Event Counter Target</span></span>
  <span data-ttu-id="28644-103">La cible de compteur d'événements compte tous les événements qui surviennent au cours d'une session Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="28644-103">The event counter target counts all events that occur during an Extended Events session.</span></span> <span data-ttu-id="28644-104">Elle vous permet d'obtenir des informations sur les caractéristiques de charge de travail sans ajouter la surcharge de la collecte d'événements complète.</span><span class="sxs-lookup"><span data-stu-id="28644-104">By using the event counter target, you can obtain information about workload characteristics without adding the overhead of full event collection.</span></span> <span data-ttu-id="28644-105">Cette cible n'a pas de paramètres personnalisables.</span><span class="sxs-lookup"><span data-stu-id="28644-105">This target has no customizable parameters.</span></span>  
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="28644-106">Ajout de la cible à une session</span><span class="sxs-lookup"><span data-stu-id="28644-106">Adding the Target to a Session</span></span>  
 <span data-ttu-id="28644-107">Pour ajouter la cible de compteur d'événements à une session Événements étendus, vous devez inclure l'instruction suivante lorsque vous créez ou modifiez une session d'événements :</span><span class="sxs-lookup"><span data-stu-id="28644-107">To add the event counter target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```  
ADD TARGET package0.event_counter  
```  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="28644-108">Vérification de la sortie cible</span><span class="sxs-lookup"><span data-stu-id="28644-108">Reviewing the Target Output</span></span>  
 <span data-ttu-id="28644-109">Pour vérifier la sortie de la cible de compteur d’événements, vous pouvez utiliser la requête suivante, en remplaçant *session_name* par le nom de la session d’événements :</span><span class="sxs-lookup"><span data-stu-id="28644-109">To review the output from the event counter target, you can use the following query, replacing *session_name* with the name of the event session:</span></span>  
  
```  
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="28644-110">L'exemple suivant montre le format de sortie de la cible de compteur d'événements.</span><span class="sxs-lookup"><span data-stu-id="28644-110">The following example shows the event counter target output format.</span></span>  
  
```  
<CounterTarget truncated = "0">  
  <Packages>  
    <Package name = "[package name]">  
      <Event name = "[event name]" count = "[number]" />  
    </Package>  
  </Packages>  
</CounterTarget>  
```  
  
## <a name="see-also"></a><span data-ttu-id="28644-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28644-111">See Also</span></span>  
 <span data-ttu-id="28644-112">[Cibles des Événements étendus SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="28644-112">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="28644-113">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28644-113">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span></span>  
 <span data-ttu-id="28644-114">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28644-114">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="28644-115">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="28644-115">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-event-session-transact-sql)  
  
  
