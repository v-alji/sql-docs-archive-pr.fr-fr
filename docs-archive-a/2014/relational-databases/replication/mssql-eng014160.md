---
title: MSSQL_ENG014160 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014160 error
ms.assetid: d0f3855e-d095-4a81-a5bd-9d7ad51f2c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3351567a31a0a0384ab8957073ab0457ef0ea7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600805"
---
# <a name="mssql_eng014160"></a><span data-ttu-id="c383e-102">MSSQL_ENG014160</span><span class="sxs-lookup"><span data-stu-id="c383e-102">MSSQL_ENG014160</span></span>
    
## <a name="message-details"></a><span data-ttu-id="c383e-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="c383e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c383e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="c383e-104">Product Name</span></span>|<span data-ttu-id="c383e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c383e-105">SQL Server</span></span>|  
|<span data-ttu-id="c383e-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="c383e-106">Event ID</span></span>|<span data-ttu-id="c383e-107">14160</span><span class="sxs-lookup"><span data-stu-id="c383e-107">14160</span></span>|  
|<span data-ttu-id="c383e-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="c383e-108">Event Source</span></span>|<span data-ttu-id="c383e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c383e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c383e-110">Composant</span><span class="sxs-lookup"><span data-stu-id="c383e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="c383e-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="c383e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="c383e-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="c383e-112">Message Text</span></span>|<span data-ttu-id="c383e-113">Le seuil [%s:%s] de la publication [%s] a été défini.</span><span class="sxs-lookup"><span data-stu-id="c383e-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="c383e-114">Un ou plusieurs abonnements à cette publication ont expiré.</span><span class="sxs-lookup"><span data-stu-id="c383e-114">One or more subscriptions to this publication have expired.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c383e-115">Explication</span><span class="sxs-lookup"><span data-stu-id="c383e-115">Explanation</span></span>  
 <span data-ttu-id="c383e-116">La réplication vous permet d'activer des avertissements pour plusieurs situations.</span><span class="sxs-lookup"><span data-stu-id="c383e-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="c383e-117">Vous pouvez, entre autres, signaler l'expiration imminente d'un abonnement.</span><span class="sxs-lookup"><span data-stu-id="c383e-117">This includes imminent subscription expiration.</span></span> <span data-ttu-id="c383e-118">Les abonnements peuvent expirer s'ils ne sont pas synchronisés durant une certaine *période de rétention*.</span><span class="sxs-lookup"><span data-stu-id="c383e-118">Subscriptions can expire if they are not synchronized within a specified *retention period*.</span></span> <span data-ttu-id="c383e-119">Pour plus d’informations, voir [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="c383e-119">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="c383e-120">Lorsque vous activez un avertissement à l'aide du moniteur de réplication ou de la procédure stockée [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), vous spécifiez un seuil qui détermine à quel moment l'avertissement sera déclenché.</span><span class="sxs-lookup"><span data-stu-id="c383e-120">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="c383e-121">Quand ce seuil est atteint ou dépassé, un avertissement s'affiche dans le moniteur de réplication et un événement est enregistré dans le journal des événements Windows.</span><span class="sxs-lookup"><span data-stu-id="c383e-121">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="c383e-122">Le franchissement d'un seuil peut également déclencher une alerte de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c383e-122">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="c383e-123">Pour plus d’informations, consultez [Définir des seuils et des avertissements dans le moniteur de réplication](monitor/set-thresholds-and-warnings-in-replication-monitor.md) et [Surveiller la réplication par programme](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="c383e-123">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c383e-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c383e-124">User Action</span></span>  
 <span data-ttu-id="c383e-125">La résolution de ce problème dépend de la raison pour laquelle l'avertissement s'est déclenché :</span><span class="sxs-lookup"><span data-stu-id="c383e-125">The resolution for this issue depends on the reason the warning was raised:</span></span>  
  
-   <span data-ttu-id="c383e-126">Si le seuil a été dépassé mais que l'abonnement n'a pas encore expiré, synchronisez l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="c383e-126">If the threshold has been exceeded, but the subscription has not yet expired, synchronize the subscription.</span></span> <span data-ttu-id="c383e-127">Pour plus d’informations, consultez [Synchroniser les données](synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="c383e-127">For more information, see [Synchronize Data](synchronize-data.md).</span></span>  
  
-   <span data-ttu-id="c383e-128">Si l'agent s'exécute mais qu'il ne réplique pas correctement les modifications, l'abonnement peut expirer.</span><span class="sxs-lookup"><span data-stu-id="c383e-128">If the agent has been running, but has not been replicating changes properly, this can cause the subscription to expire.</span></span> <span data-ttu-id="c383e-129">Pour la réplication transactionnelle, assurez-vous que l'Agent de distribution et l'Agent de lecture du journal sont en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c383e-129">For transactional replication, make sure that the Distribution Agent and Log Reader Agent are running.</span></span> <span data-ttu-id="c383e-130">Pour la réplication de fusion, assurez-vous que l'Agent de fusion est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c383e-130">For merge replication, make sure the Merge Agent is running.</span></span> <span data-ttu-id="c383e-131">Pour plus d’informations sur le démarrage de ces agents, consultez [Démarrer et arrêter un agent de réplication&#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) ou [Concepts des exécutables de l’agent de réplication](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="c383e-131">For information about how to start these agents, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="c383e-132">Si l'abonnement a expiré, il doit soit être réinitialisé, soit être supprimé et recréé, suivant le type de l'abonnement et le moment où il a expiré.</span><span class="sxs-lookup"><span data-stu-id="c383e-132">If the subscription has expired, it must either be reinitialized or dropped and re-created, depending on the type of subscription and how long it has been expired.</span></span> <span data-ttu-id="c383e-133">Pour plus d’informations, voir [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="c383e-133">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c383e-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c383e-134">See Also</span></span>  
 [<span data-ttu-id="c383e-135">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="c383e-135">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
