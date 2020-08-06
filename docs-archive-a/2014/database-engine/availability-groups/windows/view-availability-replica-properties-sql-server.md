---
title: Afficher les propriétés d’un réplica de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- ', policies'
ms.assetid: 14fed3c4-8ecc-4e1c-931d-a7ec1e9f9e90
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ca7b0508907b4d86c9ee627438a3f18e1b01fdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701910"
---
# <a name="view-availability-replica-properties-sql-server"></a><span data-ttu-id="e82f2-102">Afficher les propriétés d'un réplica de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e82f2-102">View Availability Replica Properties (SQL Server)</span></span>
  <span data-ttu-id="e82f2-103">Cette rubrique explique comment afficher les propriétés d'un réplica de disponibilité pour un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)] dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e82f2-103">This topic describes how to view the properties of an availability replica for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e82f2-104">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e82f2-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="e82f2-105">**Pour afficher et modifier les propriétés d'un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="e82f2-105">**To view and change properties an availability replica**</span></span>  
  
1.  <span data-ttu-id="e82f2-106">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="e82f2-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e82f2-107">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="e82f2-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="e82f2-108">Développez le groupe de disponibilité auquel appartient le réplica de disponibilité, puis développez le nœud **Réplicas de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="e82f2-108">Expand the availability group to which the availability replica belongs, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="e82f2-109">Cliquez avec le bouton droit sur le réplica de disponibilité dont vous souhaitez afficher les propriétés, puis sélectionnez la commande **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="e82f2-109">Right-click the availability replica whose properties you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="e82f2-110">Dans la boîte de dialogue **Propriétés du réplica de disponibilité** , utilisez la page **Général** pour afficher les propriétés de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="e82f2-110">In the **Availability Replica Properties** dialog box, use the **General** page to view the properties of this replica.</span></span> <span data-ttu-id="e82f2-111">Si vous êtes connecté au réplica principal, vous pouvez modifier les propriétés suivantes : mode de disponibilité, mode de basculement, accès à la connexion pour le rôle principal, accès en lecture pour le rôle secondaire (secondaire lisible) et valeur de délai d'expiration de session.</span><span class="sxs-lookup"><span data-stu-id="e82f2-111">If you are connected to the primary replica, you can change the following properties: availability mode, failover mode, connection access for the primary role, read-access for the secondary role (readable-secondary), and the session-timeout value.</span></span> <span data-ttu-id="e82f2-112">Pour plus d’informations, consultez [Propriétés du réplica de disponibilité &#40;page général&#41;](availability-replica-properties-general-page.md).</span><span class="sxs-lookup"><span data-stu-id="e82f2-112">For more information, see  [Availability Replica Properties &#40;General Page&#41;](availability-replica-properties-general-page.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e82f2-113">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e82f2-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="e82f2-114">**Pour afficher les propriétés et les états des réplicas de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="e82f2-114">**To view properties and states of availability replicas**</span></span>  
  
 <span data-ttu-id="e82f2-115">Pour afficher les propriétés et les états des réplicas de disponibilité, utilisez les vues et fonctions système suivantes :</span><span class="sxs-lookup"><span data-stu-id="e82f2-115">To view the properties and states of availability replicas, use the following views and system function:</span></span>  
  
 [<span data-ttu-id="e82f2-116">sys.availability_replicas</span><span class="sxs-lookup"><span data-stu-id="e82f2-116">sys.availability_replicas</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql)  
 <span data-ttu-id="e82f2-117">Retourne une ligne pour chaque réplica de disponibilité dans chaque groupe de disponibilité pour lequel l'instance locale de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] héberge un réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="e82f2-117">Returns a row for every availability replica in each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span>  
  
 <span data-ttu-id="e82f2-118">**Noms de colonne :** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span><span class="sxs-lookup"><span data-stu-id="e82f2-118">**Column names:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span></span>  
  
 [<span data-ttu-id="e82f2-119">sys.availability_read_only_routing_lists</span><span class="sxs-lookup"><span data-stu-id="e82f2-119">sys.availability_read_only_routing_lists</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
 <span data-ttu-id="e82f2-120">Retourne une ligne pour la liste de routage en lecture seule de chaque réplica de disponibilité d'un groupe de disponibilité AlwaysOn dans le cluster de basculement WSFC.</span><span class="sxs-lookup"><span data-stu-id="e82f2-120">Returns a row for the read only routing list of each availability replica in an AlwaysOn availability group in the WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="e82f2-121">**Noms de colonnes :** replica_id, routing_priority, read_only_replica_id</span><span class="sxs-lookup"><span data-stu-id="e82f2-121">**Column names:** replica_id, routing_priority, read_only_replica_id</span></span>  
  
 [<span data-ttu-id="e82f2-122">sys.dm_hadr_availability_replica_cluster_nodes</span><span class="sxs-lookup"><span data-stu-id="e82f2-122">sys.dm_hadr_availability_replica_cluster_nodes</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-nodes-transact-sql)  
 <span data-ttu-id="e82f2-123">Retourne une ligne pour chaque réplica de disponibilité (indépendamment de l'état de jointure) des groupes de disponibilité AlwaysOn dans le cluster de clustering de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="e82f2-123">Returns a row for every availability replica (regardless of join state) of the AlwaysOn availability groups in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="e82f2-124">**Noms de colonnes :** group_name, replica_server_name, node_name</span><span class="sxs-lookup"><span data-stu-id="e82f2-124">**Column names:** group_name, replica_server_name, node_name</span></span>  
  
 [<span data-ttu-id="e82f2-125">sys.dm_hadr_availability_replica_cluster_states</span><span class="sxs-lookup"><span data-stu-id="e82f2-125">sys.dm_hadr_availability_replica_cluster_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-states-transact-sql)  
 <span data-ttu-id="e82f2-126">Retourne une ligne pour chaque réplica (indépendamment de l'état de jointure) de tous les groupes de disponibilité AlwaysOn (indépendamment de l'emplacement du réplica) dans le cluster WSFC (clustering de basculement Windows Server).</span><span class="sxs-lookup"><span data-stu-id="e82f2-126">Returns a row for each replica (regardless of join state) of all AlwaysOn availability groups (regardless of replica location) in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="e82f2-127">**Noms de colonnes :** replica_id, replica_server_name, group_id, join_state, join_state_desc</span><span class="sxs-lookup"><span data-stu-id="e82f2-127">**Column names:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span></span>  
  
 [<span data-ttu-id="e82f2-128">sys.dm_hadr_availability_replica_states</span><span class="sxs-lookup"><span data-stu-id="e82f2-128">sys.dm_hadr_availability_replica_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-states-transact-sql)  
 <span data-ttu-id="e82f2-129">Retourne une ligne montrant l'état de chaque réplica de disponibilité local et une ligne pour chaque réplica de disponibilité distant au sein du même groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="e82f2-129">Returns a row showing the state of each local availability replica and a row for each remote availability replica in the same availability group.</span></span>  
  
 <span data-ttu-id="e82f2-130">**Noms de colonnes :** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description et last_connect_error_timestamp</span><span class="sxs-lookup"><span data-stu-id="e82f2-130">**Column names:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description, and last_connect_error_timestamp</span></span>  
  
 [<span data-ttu-id="e82f2-131">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="e82f2-131">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
 <span data-ttu-id="e82f2-132">Détermine si le réplica actuel est le réplica de sauvegarde par défaut.</span><span class="sxs-lookup"><span data-stu-id="e82f2-132">Determines whether the current replica is the preferred backup replica.</span></span> <span data-ttu-id="e82f2-133">Retourne 1 si la base de données sur l'instance de serveur actuelle est le réplica par défaut.</span><span class="sxs-lookup"><span data-stu-id="e82f2-133">Returns 1 if the database on the current server instance is the preferred replica.</span></span> <span data-ttu-id="e82f2-134">Sinon, retourne 0.</span><span class="sxs-lookup"><span data-stu-id="e82f2-134">Otherwise, it returns 0.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e82f2-135">Pour plus d’informations sur les compteurs de performances pour les réplicas de disponibilité (l’objet de performances **SQLServer:Availability Replica**  ), consultez [SQL Server, réplica de disponibilité](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="e82f2-135">For information about performance counters for availability replicas (the **SQLServer:Availability Replica**  performance object), see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e82f2-136">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="e82f2-136">Related Tasks</span></span>  
 <span data-ttu-id="e82f2-137">**Pour afficher des informations sur les groupes de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="e82f2-137">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="e82f2-138">Afficher les propriétés d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-138">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-139">Afficher les propriétés d’écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-139">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-140">Stratégies AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-140">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="e82f2-141">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="e82f2-142">Surveiller des groupes de disponibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-142">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="e82f2-143">**Pour gérer des réplicas de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="e82f2-143">**To manage availability replicas**</span></span>  
  
-   [<span data-ttu-id="e82f2-144">Ajouter un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-144">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-145">Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-145">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-146">Configurer l’accès en lecture seule sur un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-146">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-147">Modifier le mode de disponibilité d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-147">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-148">Modifier le mode de basculement d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-148">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-149">Modifier le délai d’expiration de session pour un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-149">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-150">Supprimer un réplica secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-150">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="e82f2-151">**Pour gérer une base de données de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="e82f2-151">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="e82f2-152">Ajouter une base de données à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-152">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="e82f2-153">Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-153">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-154">Interrompre une base de données de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-154">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-155">Reprendre une base de données de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-155">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-156">Supprimer une base de données secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-156">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="e82f2-157">Supprimer une base de données primaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-157">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="e82f2-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e82f2-158">See Also</span></span>  
 <span data-ttu-id="e82f2-159">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e82f2-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="e82f2-160">[Surveiller les groupes de disponibilité &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="e82f2-160">[Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) </span></span>  
 <span data-ttu-id="e82f2-161">[Stratégies AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="e82f2-161">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 [<span data-ttu-id="e82f2-162">Administration d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e82f2-162">Administration of an Availability Group &#40;SQL Server&#41;</span></span>](administration-of-an-availability-group-sql-server.md)  
  
  
