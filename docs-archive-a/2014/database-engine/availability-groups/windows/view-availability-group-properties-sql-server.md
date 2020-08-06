---
title: Afficher les propriétés d’un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server]
ms.assetid: 61243c87-bd62-4510-863f-2a8f347caf1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b7d1f57a9bd29b6c65160ec9a163bc77dfca48b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603631"
---
# <a name="view-availability-group-properties-sql-server"></a><span data-ttu-id="9cbff-102">Afficher les propriétés d'un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9cbff-102">View Availability Group Properties (SQL Server)</span></span>
  <span data-ttu-id="9cbff-103">Cette rubrique explique comment afficher les propriétés d'un groupe de disponibilité pour un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)] dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cbff-103">This topic describes how to view the properties of an availability group for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  

  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9cbff-104">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9cbff-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9cbff-105">**Pour afficher et modifier les propriétés d'un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9cbff-105">**To view and change the properties an availability group**</span></span>  
  
1.  <span data-ttu-id="9cbff-106">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="9cbff-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9cbff-107">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="9cbff-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="9cbff-108">Cliquez avec le bouton droit sur le groupe de disponibilité dont vous souhaitez afficher les propriétés, puis sélectionnez la commande **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="9cbff-108">Right-click the availability group whose properties you want to view, and select the **Properties** command.</span></span>  
  
4.  <span data-ttu-id="9cbff-109">Dans la boîte de dialogue **Propriétés du groupe de disponibilité**, utilisez les pages **Général** et **Préférences de sauvegarde** pour afficher et, dans certains cas, pour modifier les propriétés du groupe de disponibilité sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9cbff-109">In the **Availability Group Properties** dialog box, use the **General** and **Backup Preferences** pages to view and, in some cases, change properties of the selected availability group.</span></span> <span data-ttu-id="9cbff-110">Pour plus d’informations, consultez [Propriétés du groupe de disponibilité et Nouveau groupe de disponibilité &#40;page Général&#41;](availability-group-properties-new-availability-group-general-page.md) et [Propriétés d’un groupe de disponibilité : nouveau groupe de disponibilité &#40;page Préférences de sauvegarde&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span><span class="sxs-lookup"><span data-stu-id="9cbff-110">For more information, see [Availability Group Properties and New Availability Group &#40;General Page&#41;](availability-group-properties-new-availability-group-general-page.md) and [Availability Group Properties: New Availability Group &#40;Backup Preferences Page&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span></span>  
  
     <span data-ttu-id="9cbff-111">Utilisez la page **Autorisations** pour afficher les connexions, les rôles et les autorisations explicites actuellement associés au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9cbff-111">Use the **Permissions** page to view the current logins, roles, and explicit permissions associated with the availability group.</span></span> <span data-ttu-id="9cbff-112">Pour plus d’informations, consultez la page [Autorisations ou Éléments sécurisables](../../../relational-databases/security/permissions-or-securables-page.md).</span><span class="sxs-lookup"><span data-stu-id="9cbff-112">For more information, see [Permissions or Securables Page](../../../relational-databases/security/permissions-or-securables-page.md).</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9cbff-113">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9cbff-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="9cbff-114">**Pour afficher les propriétés et l'état d'un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9cbff-114">**To view the properties and state of an availability group**</span></span>  
  
 <span data-ttu-id="9cbff-115">Pour interroger les propriétés et les états des groupes de disponibilité pour lesquels l'instance de serveur héberge un réplica de disponibilité, utilisez les vues suivantes :</span><span class="sxs-lookup"><span data-stu-id="9cbff-115">To query the properties and states of the availability groups for which the server instance hosts an availability replica, use the following views:</span></span>  
  
 [<span data-ttu-id="9cbff-116">sys.availability_groups</span><span class="sxs-lookup"><span data-stu-id="9cbff-116">sys.availability_groups</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-transact-sql)  
 <span data-ttu-id="9cbff-117">Retourne une ligne pour chaque groupe de disponibilité pour lequel l'instance locale d' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] héberge un réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9cbff-117">Returns a row for each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span> <span data-ttu-id="9cbff-118">Chaque ligne contient une copie mise en cache des métadonnées du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9cbff-118">Each row contains a cached copy of the availability group metadata.</span></span>  
  
 <span data-ttu-id="9cbff-119">**Noms de colonne :** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="9cbff-119">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="9cbff-120">sys.availability_groups_cluster</span><span class="sxs-lookup"><span data-stu-id="9cbff-120">sys.availability_groups_cluster</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-cluster-transact-sql)  
 <span data-ttu-id="9cbff-121">Retourne une ligne pour chaque groupe de disponibilité du cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="9cbff-121">Returns a row for each availability group in the WSFC cluster.</span></span> <span data-ttu-id="9cbff-122">Chaque ligne contient les métadonnées du groupe de disponibilité du cluster de clustering de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="9cbff-122">Each row contains the availability group metadata from the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="9cbff-123">**Noms de colonne :** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="9cbff-123">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="9cbff-124">sys.dm_hadr_availability_group_states</span><span class="sxs-lookup"><span data-stu-id="9cbff-124">sys.dm_hadr_availability_group_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-group-states-transact-sql)  
 <span data-ttu-id="9cbff-125">Retourne une ligne pour chaque groupe de disponibilité qui possède un réplica de disponibilité sur l'instance locale de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cbff-125">Returns a row for each availability group that possesses an availability replica on the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9cbff-126">Chaque ligne affiche les états qui définissent l'intégrité d'un groupe de disponibilité donné.</span><span class="sxs-lookup"><span data-stu-id="9cbff-126">Each row displays the states that define the health of a given availability group.</span></span>  
  
 <span data-ttu-id="9cbff-127">**Noms de colonne :** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span><span class="sxs-lookup"><span data-stu-id="9cbff-127">**Column names:** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9cbff-128">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9cbff-128">Related Tasks</span></span>  
 <span data-ttu-id="9cbff-129">**Pour afficher des informations sur les groupes de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9cbff-129">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="9cbff-130">Afficher les propriétés d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-130">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="9cbff-131">Afficher les propriétés d’écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-131">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="9cbff-132">Stratégies AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-132">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="9cbff-133">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-133">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="9cbff-134">Surveiller des groupes de disponibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-134">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="9cbff-135">**Pour configurer un groupe de disponibilité existant**</span><span class="sxs-lookup"><span data-stu-id="9cbff-135">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="9cbff-136">Ajouter un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-136">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="9cbff-137">Supprimer un réplica secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-137">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="9cbff-138">Ajouter une base de données à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-138">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="9cbff-139">Supprimer une base de données secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-139">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="9cbff-140">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-140">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="9cbff-141">Supprimer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-141">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="9cbff-142">Supprimer une base de données primaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-142">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="9cbff-143">Supprimer un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-143">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="9cbff-144">**Pour basculer manuellement un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9cbff-144">**To manually fail over an availability group**</span></span>  
  
-   [<span data-ttu-id="9cbff-145">Effectuer un basculement manuel planifié d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-145">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="9cbff-146">Effectuer un basculement manuel forcé d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="9cbff-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9cbff-147">See Also</span></span>  
 <span data-ttu-id="9cbff-148">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [surveiller les groupes de disponibilité &#40;les stratégies Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn](always-on-policies-for-operational-issues-always-on-availability.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbff-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md)</span></span> 
  
  
