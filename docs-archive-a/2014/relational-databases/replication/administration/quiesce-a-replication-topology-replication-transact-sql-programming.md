---
title: Suspendre une topologie de réplication (programmation Transact-SQL de la réplication) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- administering replication, quiescing
- quiesce [SQL Server replication]
- transactional replication, backup and restore
ms.assetid: 7626d575-9994-47be-b772-5b6f1b7ef7ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12f0fb8ee3a6118e03799d17836573fb5c733df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705075"
---
# <a name="quiesce-a-replication-topology-replication-transact-sql-programming"></a><span data-ttu-id="bed42-102">Suspendre une topologie de réplication (programmation Transact-SQL de la réplication)</span><span class="sxs-lookup"><span data-stu-id="bed42-102">Quiesce a Replication Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="bed42-103">*Suspendre* un système revient à interrompre toute activité des tables publiées dans l’ensemble des nœuds, et à vérifier que chaque nœud a reçu toutes les modifications des autres nœuds.</span><span class="sxs-lookup"><span data-stu-id="bed42-103">*Quiescing* a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="bed42-104">Cette rubrique explique comment suspendre une topologie de réplication, requise pour plusieurs tâches d'administration et comment garantir qu'un nœud a reçu toutes les modifications d'autres nœuds.</span><span class="sxs-lookup"><span data-stu-id="bed42-104">This topic explains how to quiesce a replication topology, which is required for a number of administrative tasks, and how to ensure that a node has received all changes from other nodes.</span></span>  
  
### <a name="to-quiesce-a-transactional-replication-topology-with-read-only-subscriptions"></a><span data-ttu-id="bed42-105">Pour suspendre une topologie de réplication transactionnelle avec les abonnements en lecture seule</span><span class="sxs-lookup"><span data-stu-id="bed42-105">To quiesce a transactional replication topology with read-only subscriptions</span></span>  
  
1.  <span data-ttu-id="bed42-106">Arrêtez l'activité sur toutes les tables publiées sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="bed42-106">Stop activity on all published tables at the Publisher.</span></span>  
  
2.  <span data-ttu-id="bed42-107">Dans la base de données de publication sur le serveur de publication, exécutez [sp_posttracertoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bed42-107">At the Publisher on the publication database, execute [sp_posttracertoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span></span>  
  
3.  <span data-ttu-id="bed42-108">Dans la base de données de publication sur le serveur de publication, exécutez [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bed42-108">At the Publisher on the publication database, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span></span>  
  
4.  <span data-ttu-id="bed42-109">Assurez-vous que chaque Abonné a reçu le jeton de suivi.</span><span class="sxs-lookup"><span data-stu-id="bed42-109">Ensure that each Subscriber has received the tracer token.</span></span>  
  
### <a name="to-quiesce-a-transactional-replication-topology-with-updatable-subscriptions"></a><span data-ttu-id="bed42-110">Pour suspendre une topologie de réplication transactionnelle avec les abonnements pouvant être mis à jour</span><span class="sxs-lookup"><span data-stu-id="bed42-110">To quiesce a transactional replication topology with updatable subscriptions</span></span>  
  
1.  <span data-ttu-id="bed42-111">Arrêtez l'activité sur toutes les tables publiées sur le serveur de publication et sur tous les Abonnés.</span><span class="sxs-lookup"><span data-stu-id="bed42-111">Stop activity on all published tables at the Publisher and all Subscribers.</span></span>  
  
2.  <span data-ttu-id="bed42-112">Si tous les Abonnés utilisent des abonnements de mise à jour en attente :</span><span class="sxs-lookup"><span data-stu-id="bed42-112">If any Subscribers use queued updating subscriptions:</span></span>  
  
    1.  <span data-ttu-id="bed42-113">Si l'Agent de lecture de la file d'attente ne s'exécute pas en mode continu, exécutez l'Agent.</span><span class="sxs-lookup"><span data-stu-id="bed42-113">If the Queue Reader Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="bed42-114">Pour plus d’informations sur l’exécution des agents, consultez [Concepts des exécutables de l’agent de réplication](../concepts/replication-agent-executables-concepts.md) ou [Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="bed42-114">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
    2.  <span data-ttu-id="bed42-115">Pour vérifier que la file d'attente est vide, exécutez [sp_replqueuemonitor](/sql/relational-databases/system-stored-procedures/sp-replqueuemonitor-transact-sql) sur chaque Abonné.</span><span class="sxs-lookup"><span data-stu-id="bed42-115">To verify that the queue is empty, execute [sp_replqueuemonitor](/sql/relational-databases/system-stored-procedures/sp-replqueuemonitor-transact-sql) at each Subscriber.</span></span>  
  
3.  <span data-ttu-id="bed42-116">Dans la base de données de publication sur le serveur de publication, exécutez [sp_posttracertoken](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bed42-116">At the Publisher on the publication database, execute [sp_posttracertoken](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span></span>  
  
4.  <span data-ttu-id="bed42-117">Dans la base de données de publication sur le serveur de publication, exécutez [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bed42-117">At the Publisher on the publication database, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span></span>  
  
5.  <span data-ttu-id="bed42-118">Assurez-vous que chaque Abonné a reçu le jeton de suivi.</span><span class="sxs-lookup"><span data-stu-id="bed42-118">Ensure that each Subscriber has received the tracer token.</span></span>  
  
### <a name="to-quiesce-a-peer-to-peer-transactional-replication-topology"></a><span data-ttu-id="bed42-119">Pour suspendre une topologie de réplication transactionnelle d'égal à égal</span><span class="sxs-lookup"><span data-stu-id="bed42-119">To quiesce a peer-to-peer transactional replication topology</span></span>  
  
1.  <span data-ttu-id="bed42-120">Arrêtez l'activité sur toutes les tables publiées sur tous les nœuds.</span><span class="sxs-lookup"><span data-stu-id="bed42-120">Stop activity on all published tables at all nodes.</span></span>  
  
2.  <span data-ttu-id="bed42-121">Exécutez [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) sur chaque base de données de publication dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="bed42-121">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) on each publication database in the topology.</span></span>  
  
3.  <span data-ttu-id="bed42-122">Si l'Agent de lecture du journal ou l'Agent de distribution ne s'exécute pas en mode continu, exécutez l'Agent.</span><span class="sxs-lookup"><span data-stu-id="bed42-122">If the Log Reader Agent or Distribution Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="bed42-123">L'Agent de lecture du journal doit être démarré avant l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="bed42-123">The Log Reader Agent must be started before the Distribution Agent.</span></span> <span data-ttu-id="bed42-124">Pour plus d’informations sur l’exécution des agents, consultez [Concepts des exécutables de l’agent de réplication](../concepts/replication-agent-executables-concepts.md) ou [Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="bed42-124">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
4.  <span data-ttu-id="bed42-125">Exécutez [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) sur chaque base de données de publication dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="bed42-125">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) on each publication database in the topology.</span></span> <span data-ttu-id="bed42-126">Vérifiez que le jeu de résultats contient des réponses de chacun des autres nœuds.</span><span class="sxs-lookup"><span data-stu-id="bed42-126">Ensure that the result set contains responses from each of the other nodes.</span></span>  
  
### <a name="to-ensure-a-peer-to-peer-node-has-received-all-prior-changes"></a><span data-ttu-id="bed42-127">Pour garantir qu'un nœud d'égal à égal a reçu toutes les modifications antérieures</span><span class="sxs-lookup"><span data-stu-id="bed42-127">To ensure a peer-to-peer node has received all prior changes</span></span>  
  
1.  <span data-ttu-id="bed42-128">Exécutez [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) sur la base de données de publication au nœud que vous contrôlez.</span><span class="sxs-lookup"><span data-stu-id="bed42-128">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) on the publication database at the node you are checking.</span></span>  
  
2.  <span data-ttu-id="bed42-129">Si l'Agent de lecture du journal ou l'Agent de distribution ne s'exécute pas en mode continu, exécutez l'Agent.</span><span class="sxs-lookup"><span data-stu-id="bed42-129">If the Log Reader Agent or Distribution Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="bed42-130">L'Agent de lecture du journal doit être démarré avant l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="bed42-130">The Log Reader Agent must be started before the Distribution Agent.</span></span> <span data-ttu-id="bed42-131">Pour plus d’informations sur l’exécution des agents, consultez [Concepts des exécutables de l’agent de réplication](../concepts/replication-agent-executables-concepts.md) ou [Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="bed42-131">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="bed42-132">Exécutez [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) sur la base de données de publication au nœud que vous contrôlez.</span><span class="sxs-lookup"><span data-stu-id="bed42-132">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) on the publication database at the node you are checking.</span></span> <span data-ttu-id="bed42-133">Vérifiez que le jeu de résultats contient des réponses de chacun des autres nœuds.</span><span class="sxs-lookup"><span data-stu-id="bed42-133">Ensure that the result set contains responses from each of the other nodes.</span></span>  
  
### <a name="to-quiesce-a-merge-replication-topology"></a><span data-ttu-id="bed42-134">Pour suspendre une topologie de réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="bed42-134">To quiesce a merge replication topology</span></span>  
  
1.  <span data-ttu-id="bed42-135">Arrêtez l'activité sur toutes les tables publiées sur le serveur de publication et sur tous les Abonnés.</span><span class="sxs-lookup"><span data-stu-id="bed42-135">Stop activity on all published tables at the Publisher and at all Subscribers.</span></span>  
  
2.  <span data-ttu-id="bed42-136">Exécutez l'Agent de fusion pour chaque abonnement deux fois : synchronisez tous les abonnements une fois, puis synchronisez chaque abonnement une deuxième fois.</span><span class="sxs-lookup"><span data-stu-id="bed42-136">Run the Merge Agent for each subscription two times: synchronize all subscriptions once and then synchronize each subscription a second time.</span></span> <span data-ttu-id="bed42-137">Cela garantit que toutes les modifications sont répliquées sur tous les nœuds.</span><span class="sxs-lookup"><span data-stu-id="bed42-137">This ensures that all changes are replicated to all nodes.</span></span> <span data-ttu-id="bed42-138">Pour plus d’informations sur l’exécution des agents, consultez [Concepts des exécutables de l’agent de réplication](../concepts/replication-agent-executables-concepts.md) ou [Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="bed42-138">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bed42-139">Si les conflits se produisent pendant la synchronisation, il est possible que les modifications requises par la résolution de conflit ne soient pas propagées à tous les nœuds après que l'Agent de fusion a été exécuté deux fois.</span><span class="sxs-lookup"><span data-stu-id="bed42-139">If conflicts occur during synchronization, it is possible that changes required by conflict resolution will not be propagated to all nodes after running the Merge Agent two times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed42-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bed42-140">See Also</span></span>  
 <span data-ttu-id="bed42-141">[Administrer une topologie d’égal à égal &#40;programmation Transact-SQL de la réplication&#41;](administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="bed42-141">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="bed42-142">Mesurer la latence et valider les connexions pour la réplication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="bed42-142">Measure Latency and Validate Connections for Transactional Replication</span></span>](../monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
