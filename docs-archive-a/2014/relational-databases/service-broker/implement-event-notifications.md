---
title: Implémenter des notifications d’événements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], target service
- target service [SQL Server]
- event notifications [SQL Server], creating
ms.assetid: 29ac8f68-a28a-4a77-b67b-a8663001308c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a89c66ca5c3b420fff14c087bd604b16c641369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610561"
---
# <a name="implement-event-notifications"></a><span data-ttu-id="766a2-102">Implémenter des notifications d'événements</span><span class="sxs-lookup"><span data-stu-id="766a2-102">Implement Event Notifications</span></span>
  <span data-ttu-id="766a2-103">Pour implémenter une notification d'événement, vous devez créer un service cible destiné à recevoir les notifications d'événements avant de créer la notification d'événement.</span><span class="sxs-lookup"><span data-stu-id="766a2-103">To implement an event notification, you must first create a target service to receive event notifications, and then create the event notification.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="766a2-104">doit être configurée pour les notifications d'événements qui envoient des messages à un Service Broker résidant sur un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="766a2-104">dialog security should be configured for event notifications that send messages to a service broker on a remote server.</span></span> <span data-ttu-id="766a2-105">La sécurité du dialogue doit être configurée manuellement conformément au modèle de sécurité totale.</span><span class="sxs-lookup"><span data-stu-id="766a2-105">Dialog security must be configured manually according to the full security model.</span></span>  
  
## <a name="creating-the-target-service"></a><span data-ttu-id="766a2-106">Création du service cible</span><span class="sxs-lookup"><span data-stu-id="766a2-106">Creating the Target Service</span></span>  
 <span data-ttu-id="766a2-107">Il n'est pas nécessaire que vous créiez un service d'initialisation de [!INCLUDE[ssSB](../../includes/sssb-md.md)], car [!INCLUDE[ssSB](../../includes/sssb-md.md)] inclut le type de message et le contrat de notifications d'événements suivants :</span><span class="sxs-lookup"><span data-stu-id="766a2-107">You do not have to create a [!INCLUDE[ssSB](../../includes/sssb-md.md)]-initiating service because [!INCLUDE[ssSB](../../includes/sssb-md.md)] includes the following specific message type and contract for event notifications:</span></span>  
  
```  
https://schemas.microsoft.com/SQL/Notifications/PostEventNotification  
```  
  
 <span data-ttu-id="766a2-108">Le service cible qui reçoit les notifications d'événements doit respecter ce contrat préexistant.</span><span class="sxs-lookup"><span data-stu-id="766a2-108">The target service that receives event notifications must honor this preexisting contract.</span></span>  
  
 <span data-ttu-id="766a2-109">**Pour créer un service cible**:</span><span class="sxs-lookup"><span data-stu-id="766a2-109">**To create a target service**:</span></span>  
  
1.  <span data-ttu-id="766a2-110">Créez une file d'attente pour recevoir les messages.</span><span class="sxs-lookup"><span data-stu-id="766a2-110">Create a queue to receive messages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="766a2-111">Cette file d'attente reçoit le type de message suivant : `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span><span class="sxs-lookup"><span data-stu-id="766a2-111">The queue receives the following message type: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span></span>  
  
2.  <span data-ttu-id="766a2-112">Créez un service dans la file d'attente qui fasse référence au contrat de notification d'événement.</span><span class="sxs-lookup"><span data-stu-id="766a2-112">Create a service on the queue that references the event notifications contract.</span></span>  
  
3.  <span data-ttu-id="766a2-113">Créez un itinéraire au niveau du service pour indiquer l'adresse à laquelle [!INCLUDE[ssSB](../../includes/sssb-md.md)] doit expédier les messages pour le service.</span><span class="sxs-lookup"><span data-stu-id="766a2-113">Create a route on the service to define the address to which [!INCLUDE[ssSB](../../includes/sssb-md.md)] sends messages for the service.</span></span> <span data-ttu-id="766a2-114">Si la notification d'événement a pour cible un service de la même base de données, spécifiez `ADDRESS = 'LOCAL'`.</span><span class="sxs-lookup"><span data-stu-id="766a2-114">For event notifications that target a service in the same database, specify `ADDRESS = 'LOCAL'`.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="766a2-115">L’acheminement désigne le service appelé à recevoir les messages de notification.</span><span class="sxs-lookup"><span data-stu-id="766a2-115">routing determines the service that receives the notification messages.</span></span> <span data-ttu-id="766a2-116">Si votre notification d'événement a pour cible un service de serveur distant, il convient de définir des itinéraires à la fois sur le serveur source et sur le serveur cible pour éviter des erreurs de communication bidirectionnelle.</span><span class="sxs-lookup"><span data-stu-id="766a2-116">If the event notification targets a service on a remote server, both the source server and the target server must have routes defined on them to make sure that two-way communication occurs.</span></span>  
  
 <span data-ttu-id="766a2-117">L'exemple suivant illustre la création d'une file d'attente, d'un service au niveau de cette file d'attente, et d'un itinéraire au niveau du service en vue de gérer les messages relevant du contrat de notification d'événement.</span><span class="sxs-lookup"><span data-stu-id="766a2-117">The following example creates a queue, a service on the queue, and a route on the service to handle messages from the event notification contract.</span></span>  
  
```  
CREATE QUEUE NotifyQueue ;  
GO  
CREATE SERVICE NotifyService  
ON QUEUE NotifyQueue  
(  
[https://schemas.microsoft.com/SQL/Notifications/PostEventNotification]  
);  
GO  
CREATE ROUTE NotifyRoute  
WITH SERVICE_NAME = 'NotifyService',  
ADDRESS = 'LOCAL';  
GO  
```  
  
## <a name="creating-the-event-notification"></a><span data-ttu-id="766a2-118">Création de la notification d'événement</span><span class="sxs-lookup"><span data-stu-id="766a2-118">Creating the Event Notification</span></span>  
 <span data-ttu-id="766a2-119">Les notifications d'événements sont créées à l'aide de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION et supprimées à l'aide de l'instruction DROP EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="766a2-119">Event notifications are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION statement, and are dropped by using the DROP EVENT NOTIFICATION STATEMENT.</span></span> <span data-ttu-id="766a2-120">Pour modifier une notification d'événement, vous devez la supprimer et la recréer.</span><span class="sxs-lookup"><span data-stu-id="766a2-120">To modify an event notification, you must drop and re-create the event notification.</span></span>  
  
 <span data-ttu-id="766a2-121">L'exemple suivant crée la notification d'événement `CreateDatabaseNotification`.</span><span class="sxs-lookup"><span data-stu-id="766a2-121">The following example creates the event notification `CreateDatabaseNotification`.</span></span> <span data-ttu-id="766a2-122">Cette notification envoie un message à propos de tout événement `CREATE_DATABASE` qui se produit sur le serveur au service `NotifyService` précédemment créé.</span><span class="sxs-lookup"><span data-stu-id="766a2-122">This notification sends a message about any `CREATE_DATABASE` event that occurs on the server to the `NotifyService` service that was previously created.</span></span>  
  
```  
CREATE EVENT NOTIFICATION CreateDatabaseNotification  
ON SERVER  
FOR CREATE_DATABASE  
TO SERVICE 'NotifyService', '8140a771-3c4b-4479-8ac0-81008ab17984' ;  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="766a2-123">Les notifications d'événements reconnaissent les événements CREATE_SCHEMA et les définitions <schema_element> des instructions CREATE SCHEMA comme événements distincts.</span><span class="sxs-lookup"><span data-stu-id="766a2-123">Event notifications recognize CREATE_SCHEMA events and the <schema_element> definitions of CREATE SCHEMA statements as separate events.</span></span> <span data-ttu-id="766a2-124">Par exemple, une notification d'événement est créée sur les deux événements CREATE_SCHEMA et CREATE_TABLE, et vous exécutez le traitement suivant.</span><span class="sxs-lookup"><span data-stu-id="766a2-124">For example, an event notification is created on both the CREATE_SCHEMA and CREATE_TABLE events, and you run the following batch.</span></span>  
>   
>  `CREATE SCHEMA s`  
>   
>  `CREATE TABLE t1 (col1 int)`  
>   
>  <span data-ttu-id="766a2-125">Dans ce cas, la notification d'événement est déclenchée deux fois : une première fois quand se produit l'événement CREATE_SCHEMA, et une deuxième fois quand se produit l'événement CREATE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="766a2-125">In this case, the event notification is raised two times: Onne time when the CREATE_SCHEMA event occurs, and again when the CREATE_TABLE event occurs.</span></span> <span data-ttu-id="766a2-126">Nous recommandons d'éviter de créer des notifications d'événements sur les événements CREATE_SCHEMA et les textes <schema_element> des définitions CREATE SCHEMA correspondantes, ou de créer une logique dans votre application destinée à éviter la capture des données d'événement non souhaitées.</span><span class="sxs-lookup"><span data-stu-id="766a2-126">We recommend that you either avoid creating event notifications on both the CREATE_SCHEMA events and the <schema_element> texts of any corresponding CREATE SCHEMA definitions, or build logic into your application to avoid capturing unwanted event data.</span></span>  
  
 <span data-ttu-id="766a2-127">**Pour créer une notification d'événement**</span><span class="sxs-lookup"><span data-stu-id="766a2-127">**To create an event notification**</span></span>  
  
-   [<span data-ttu-id="766a2-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="766a2-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-notification-transact-sql)  
  
 <span data-ttu-id="766a2-129">**Pour supprimer une notification d'événement**</span><span class="sxs-lookup"><span data-stu-id="766a2-129">**To drop an event notification**</span></span>  
  
-   [<span data-ttu-id="766a2-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="766a2-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-event-notification-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="766a2-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="766a2-131">See Also</span></span>  
 <span data-ttu-id="766a2-132">[Obtenir des informations concernant les notifications d'événements](event-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="766a2-132">[Get Information About Event Notifications](event-notifications.md) </span></span>  
 [<span data-ttu-id="766a2-133">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="766a2-133">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
