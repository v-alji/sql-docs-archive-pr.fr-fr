---
title: Obtenir des informations concernant les notifications d’événements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], metadata
- status information [SQL Server], event notifications
- metadata [SQL Server], event notifications
ms.assetid: 8bc10867-66d6-4f57-ac32-a6c29f3327cd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8d8271b6279910321058d01c7b2f96b1df62bd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700913"
---
# <a name="get-information-about-event-notifications"></a><span data-ttu-id="a1ae4-102">Obtenir des informations concernant les notifications d'événements</span><span class="sxs-lookup"><span data-stu-id="a1ae4-102">Get Information About Event Notifications</span></span>
  <span data-ttu-id="a1ae4-103">Les affichages catalogue suivants vous permettent d'interroger les métadonnées concernant les notifications d'événements.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-103">The following catalog views are available to query metadata about event notifications.</span></span>  
  
 <span data-ttu-id="a1ae4-104">**Pour obtenir des informations sur les notifications d'événements qui ne se produisent pas au niveau du serveur**</span><span class="sxs-lookup"><span data-stu-id="a1ae4-104">**To get information about nonserver-level event notifications**</span></span>  
  
-   [<span data-ttu-id="a1ae4-105">sys.event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a1ae4-105">sys.event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="a1ae4-106">Pour afficher les métadonnées sur une notification d’événement dans l’affichage catalogue **sys.event_notifications** créée au niveau de la base de données, vous devez au moins disposer de l’autorisation CONTROL, ALTER, TAKE OWNERSHIP ou VIEW DEFINITION sur la base de données, être propriétaire de la notification d’événement ou disposer de l’autorisation ALTER ANY DATABASE EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-106">To view metadata about any event notification in **sys.event_notifications** created at the database level, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the database, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span> <span data-ttu-id="a1ae4-107">Pour les notifications d'événements créées sur une file d'attente spécifique, vous devez au moins disposer de l'autorisation CONTROL, ALTER, TAKE OWNERSHIP ou VIEW DEFINITION sur l'objet, être propriétaire de la notification d'événement ou disposer de l'autorisation ALTER ANY DATABASE EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-107">For event notifications created on a specific queue, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the object, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span>  
  
 <span data-ttu-id="a1ae4-108">**Pour obtenir des informations sur les notifications d'événements qui se produisent au niveau du serveur**</span><span class="sxs-lookup"><span data-stu-id="a1ae4-108">**To get information about server-level event notifications**</span></span>  
  
-   [<span data-ttu-id="a1ae4-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a1ae4-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="a1ae4-110">Vous devez au moins disposer de l’autorisation CONTROL ou VIEW ANY DEFINITION sur le serveur, être la connexion ou le propriétaire de la notification d’événement ou disposer de l’autorisation ALTER ANY EVENT NOTIFICATION pour afficher les métadonnées concernant toute notification d’événement dans **sys.server_event_notifications**.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-110">At the minimum, you must have the following: CONTROL or VIEW ANY DEFINITION permission on the server, be the logon or owner of the event notification, or have ALTER ANY EVENT NOTIFICATION permission to view metadata about any event notification in **sys.server_event_notifications**.</span></span>  
  
 <span data-ttu-id="a1ae4-111">**Pour obtenir des informations sur tous les événements pouvant déclencher des notifications**</span><span class="sxs-lookup"><span data-stu-id="a1ae4-111">**To get information about all events that can fire event notifications**</span></span>  
  
-   [<span data-ttu-id="a1ae4-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a1ae4-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notification-event-types-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="a1ae4-113">Cette vue de catalogue ne retourne pas de groupes d'événements.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-113">This catalog view does not return event groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ae4-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1ae4-114">See Also</span></span>  
 [<span data-ttu-id="a1ae4-115">Notifications d'événements</span><span class="sxs-lookup"><span data-stu-id="a1ae4-115">Event Notifications</span></span>](event-notifications.md)  
  
  
