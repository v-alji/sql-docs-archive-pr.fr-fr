---
title: Broker, catégorie d’événement | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Broker event category
- Broker event category [SQL Server]
- event classes [SQL Server], Broker event category
ms.assetid: 470dc93c-0dda-4d89-829b-937738d59b31
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23f839416e3404bfdf0a7e61d1b1e8dbbb90ec95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601516"
---
# <a name="broker-event-category"></a><span data-ttu-id="b25f4-102">Catégorie d'événement Broker</span><span class="sxs-lookup"><span data-stu-id="b25f4-102">Broker Event Category</span></span>
  <span data-ttu-id="b25f4-103">La catégorie d’événement **Broker** contient des événements généraux de Service Broker.</span><span class="sxs-lookup"><span data-stu-id="b25f4-103">The **Broker** event category contains general Service Broker events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b25f4-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b25f4-104">In This Section</span></span>  
  
|<span data-ttu-id="b25f4-105">Rubrique</span><span class="sxs-lookup"><span data-stu-id="b25f4-105">Topic</span></span>|<span data-ttu-id="b25f4-106">Description</span><span class="sxs-lookup"><span data-stu-id="b25f4-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b25f4-107">Broker:Activation, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="b25f4-107">Broker:Activation Event Class</span></span>](broker-activation-event-class.md)|<span data-ttu-id="b25f4-108">Événement généré lorsqu'un moniteur de file d'attente démarre une procédure stockée d'activation.</span><span class="sxs-lookup"><span data-stu-id="b25f4-108">An event generated when a queue monitor starts an activation stored procedure.</span></span>|  
|[<span data-ttu-id="b25f4-109">Broker:Connection, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="b25f4-109">Broker:Connection Event Class</span></span>](broker-connection-event-class.md)|<span data-ttu-id="b25f4-110">Événement généré pour signaler l'état d'une connexion de transport gérée par Service Broker.</span><span class="sxs-lookup"><span data-stu-id="b25f4-110">An event generated to report the status of a transport connection managed by Service Broker.</span></span>|  
|[<span data-ttu-id="b25f4-111">Broker:Conversation, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="b25f4-111">Broker:Conversation Event Class</span></span>](broker-conversation-event-class.md)|<span data-ttu-id="b25f4-112">Événement généré pour rapporter les progrès d'une conversation.</span><span class="sxs-lookup"><span data-stu-id="b25f4-112">An event generated to report the progress of a conversation.</span></span>|  
|[<span data-ttu-id="b25f4-113">Broker:Conversation Group, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="b25f4-113">Broker:Conversation Group Event Class</span></span>](broker-conversation-group-event-class.md)|<span data-ttu-id="b25f4-114">Événement généré lorsque la base de données crée ou supprime un groupe de conversations.</span><span class="sxs-lookup"><span data-stu-id="b25f4-114">An event generated when the database creates or drops a conversation group.</span></span>|  
|[<span data-ttu-id="b25f4-115">Broker:Corrupted Message, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="b25f4-115">Broker:Corrupted Message Event Class</span></span>](broker-corrupted-message-event-class.md)|<span data-ttu-id="b25f4-116">Événement généré pour indiquer que la base de données a reçu un message endommagé.</span><span class="sxs-lookup"><span data-stu-id="b25f4-116">An event generated to report that the database has received a corrupt message.</span></span>|  
|[<span data-ttu-id="b25f4-117">Broker:Forwarded Message Dropped, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="b25f4-117">Broker:Forwarded Message Dropped Event Class</span></span>](broker-forwarded-message-dropped-event-class.md)|<span data-ttu-id="b25f4-118">Événement généré lorsque SQL Server supprime un message Service Broker qui aurait dû être transféré.</span><span class="sxs-lookup"><span data-stu-id="b25f4-118">An event generated when SQL Server drops a Service Broker message that was to have been forwarded.</span></span>|  
|[<span data-ttu-id="b25f4-119">Broker:Forwarded Message Sent, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="b25f4-119">Broker:Forwarded Message Sent Event Class</span></span>](broker-forwarded-message-sent-event-class.md)|<span data-ttu-id="b25f4-120">Événement généré lorsque SQL Server transfère un message Service Broker.</span><span class="sxs-lookup"><span data-stu-id="b25f4-120">An event generated when SQL Server forwards a Service Broker message.</span></span>|  
|[<span data-ttu-id="b25f4-121">Classe d'événements Broker:Message Classify</span><span class="sxs-lookup"><span data-stu-id="b25f4-121">Broker:Message Classify Event Class</span></span>](broker-message-classify-event-class.md)|<span data-ttu-id="b25f4-122">Événement généré lorsque Service Broker détermine le routage d'un message.</span><span class="sxs-lookup"><span data-stu-id="b25f4-122">An event generated when Service Broker determines the routing for a message.</span></span>|  
|[<span data-ttu-id="b25f4-123">Classe d'événements Broker:Message Drop</span><span class="sxs-lookup"><span data-stu-id="b25f4-123">Broker:Message Drop Event Class</span></span>](broker-message-drop-event-class.md)|<span data-ttu-id="b25f4-124">Événement généré lorsque Service Broker ne peut pas conserver un message reçu qui aurait dû être remis à un service dans cette instance.</span><span class="sxs-lookup"><span data-stu-id="b25f4-124">An event generated when Service Broker is unable to retain a received message that should have been delivered to a service in this instance</span></span>|  
|[<span data-ttu-id="b25f4-125">Classe d'événements Broker:Remote Message Ack</span><span class="sxs-lookup"><span data-stu-id="b25f4-125">Broker:Remote Message Ack Event Class</span></span>](broker-remote-message-ack-event-class.md)|<span data-ttu-id="b25f4-126">Événement généré lorsque Service Broker envoie ou reçoit un accusé de réception du message.</span><span class="sxs-lookup"><span data-stu-id="b25f4-126">An event generated when Service Broker sends or receives a message acknowledgement.</span></span>|  
  
 <span data-ttu-id="b25f4-127">Deux événements d'audit de sécurité sont également fournis pour Service Broker.</span><span class="sxs-lookup"><span data-stu-id="b25f4-127">Two security audit events are also provided for Service Broker.</span></span> <span data-ttu-id="b25f4-128">Pour plus d’informations sur ces événements, consultez [Classe d’événements Audit Broker Login](audit-broker-login-event-class.md) et [Classe d’événement Audit Broker Conversation](audit-broker-conversation-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="b25f4-128">For more information on those events, see [Audit Broker Login Event Class](audit-broker-login-event-class.md) and [Audit Broker Conversation Event Class](audit-broker-conversation-event-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b25f4-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b25f4-129">See Also</span></span>  
 [<span data-ttu-id="b25f4-130">Catégorie d'événement Audit de sécurité</span><span class="sxs-lookup"><span data-stu-id="b25f4-130">Security Audit Event Category</span></span>](https://docs.microsoft.com/bi-reference/trace-events/security-audit-event-category)  
  
  
