---
title: MSSQL_ENG014150 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014150 error
ms.assetid: c3dd3109-abf3-4b38-a4e9-ef48d0235656
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c926d05be9613ff559f119484fa5e238d71d861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600812"
---
# <a name="mssql_eng014150"></a><span data-ttu-id="076af-102">MSSQL_ENG014150</span><span class="sxs-lookup"><span data-stu-id="076af-102">MSSQL_ENG014150</span></span>
    
## <a name="message-details"></a><span data-ttu-id="076af-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="076af-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="076af-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="076af-104">Product Name</span></span>|<span data-ttu-id="076af-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="076af-105">SQL Server</span></span>|  
|<span data-ttu-id="076af-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="076af-106">Event ID</span></span>|<span data-ttu-id="076af-107">14150</span><span class="sxs-lookup"><span data-stu-id="076af-107">14150</span></span>|  
|<span data-ttu-id="076af-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="076af-108">Event Source</span></span>|<span data-ttu-id="076af-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="076af-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="076af-110">Composant</span><span class="sxs-lookup"><span data-stu-id="076af-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="076af-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="076af-111">Symbolic Name</span></span>||  
|<span data-ttu-id="076af-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="076af-112">Message Text</span></span>|<span data-ttu-id="076af-113">Réplication-%s : réussite de l'agent %s.</span><span class="sxs-lookup"><span data-stu-id="076af-113">Replication-%s: agent %s succeeded.</span></span> <span data-ttu-id="076af-114">%s</span><span class="sxs-lookup"><span data-stu-id="076af-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="076af-115">Explication</span><span class="sxs-lookup"><span data-stu-id="076af-115">Explanation</span></span>  
 <span data-ttu-id="076af-116">Ce message indique qu'un agent de réplication s'est correctement exécuté.</span><span class="sxs-lookup"><span data-stu-id="076af-116">This message indicates that a replication agent has successfully finished running.</span></span> <span data-ttu-id="076af-117">La réplication utilise les agents suivants :</span><span class="sxs-lookup"><span data-stu-id="076af-117">Replication uses the following agents:</span></span>  
  
-   <span data-ttu-id="076af-118">L'Agent d'instantané.</span><span class="sxs-lookup"><span data-stu-id="076af-118">The Snapshot Agent.</span></span> <span data-ttu-id="076af-119">Cet agent est utilisé par toutes les publications.</span><span class="sxs-lookup"><span data-stu-id="076af-119">This agent is used by all publications.</span></span>  
  
-   <span data-ttu-id="076af-120">L'Agent de lecture du journal.</span><span class="sxs-lookup"><span data-stu-id="076af-120">The Log Reader Agent.</span></span> <span data-ttu-id="076af-121">Cet agent est utilisé par toutes les publications transactionnelles.</span><span class="sxs-lookup"><span data-stu-id="076af-121">This agent is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="076af-122">L'Agent de lecture de la file d'attente.</span><span class="sxs-lookup"><span data-stu-id="076af-122">The Queue Reader Agent.</span></span> <span data-ttu-id="076af-123">Cet agent est utilisé par les publications transactionnelles pour lesquelles les abonnements mis à jour en file d'attente sont activés.</span><span class="sxs-lookup"><span data-stu-id="076af-123">This agent is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="076af-124">L'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="076af-124">The Distribution Agent.</span></span> <span data-ttu-id="076af-125">Cet agent synchronise les abonnements aux publications transactionnelles et aux publications d'instantané.</span><span class="sxs-lookup"><span data-stu-id="076af-125">This agent synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="076af-126">L'Agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="076af-126">The Merge Agent.</span></span> <span data-ttu-id="076af-127">Cet agent synchronise les abonnements aux publications de fusion.</span><span class="sxs-lookup"><span data-stu-id="076af-127">This agent synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="076af-128">Travaux de maintenance de la réplication</span><span class="sxs-lookup"><span data-stu-id="076af-128">Replication maintenance jobs.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="076af-129">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="076af-129">User Action</span></span>  
 <span data-ttu-id="076af-130">L'Agent de lecture du journal, l'Agent de lecture de la file d'attente et l'Agent de distribution s'exécutent généralement en continu, tandis que les autres agents s'exécutent généralement à la demande ou selon un calendrier.</span><span class="sxs-lookup"><span data-stu-id="076af-130">The Log Reader Agent, Queue Reader Agent, and Distribution Agent typically run continuously, whereas the other agents typically run on demand or on a schedule.</span></span> <span data-ttu-id="076af-131">Si vous ne pensez pas qu'un agent doit avoir terminé son exécution, vérifiez son état.</span><span class="sxs-lookup"><span data-stu-id="076af-131">If you do not expect an agent to have completed a run, check the status of the agent.</span></span> <span data-ttu-id="076af-132">Pour plus d’informations, voir [Monitor Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="076af-132">For more information, see [Monitor Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="076af-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="076af-133">See Also</span></span>  
 <span data-ttu-id="076af-134">[Administration de l’Agent de réplication](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="076af-134">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="076af-135">[Guide de référence des erreurs et des événements &#40;réplication&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="076af-135">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="076af-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="076af-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="076af-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="076af-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="076af-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="076af-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="076af-139">[Agent de lecture de la file d'attente de réplication](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="076af-139">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="076af-140">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="076af-140">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
