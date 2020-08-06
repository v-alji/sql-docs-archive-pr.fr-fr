---
title: Administration d’un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], managing
ms.assetid: 0b7542fa-235e-413d-81bf-3eff9ee07480
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2cac9a34fe71c11f71ec47bbb6d690199869fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601705"
---
# <a name="administration-of-an-availability-group-sql-server"></a><span data-ttu-id="0cf7d-102">Administration d'un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0cf7d-102">Administration of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="0cf7d-103">La gestion d'un groupe de disponibilité AlwaysOn existant dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] implique une ou plusieurs des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0cf7d-103">Managing an existing AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] involves one or more of the following tasks:</span></span>  
  
-   <span data-ttu-id="0cf7d-104">Modification des propriétés d'un réplica de disponibilité existant, par exemple pour modifier l'accès de connexion du client (pour configurer les réplicas secondaires lisibles), modification de son mode de basculement, mode de disponibilité ou paramètre de délai d'expiration de session.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-104">Altering the properties of an existing availability replica, for example to change client connection access (for configuring readable secondary replicas), changing its failover mode, availability mode, or session timeout setting.</span></span>  
  
-   <span data-ttu-id="0cf7d-105">Ajout ou suppression de réplicas secondaires.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-105">Adding or removing secondary replicas.</span></span>  
  
-   <span data-ttu-id="0cf7d-106">Ajout ou suppression d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-106">Adding or removing a database.</span></span>  
  
-   <span data-ttu-id="0cf7d-107">Interruption ou reprise d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-107">Suspending or resuming a database.</span></span>  
  
-   <span data-ttu-id="0cf7d-108">Exécution d’un basculement manuel planifié ( *basculement manuel*) ou d’un basculement manuel forcé ( *basculement forcé*).</span><span class="sxs-lookup"><span data-stu-id="0cf7d-108">Performing a planned manual failover (a *manual failover*) or a forced manual failover (a *forced failover*).</span></span>  
  
-   <span data-ttu-id="0cf7d-109">Création ou configuration d'un écouteur de groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-109">Creating or configuring an availability group listener.</span></span>  
  
-   <span data-ttu-id="0cf7d-110">Gestion des [réplicas secondaires lisibles](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) pour un groupe de disponibilité donné.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-110">Managing [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="0cf7d-111">Cela implique la configuration d'un ou plusieurs réplicas pour l'accès en lecture seule en cas d'exécution sous le rôle secondaire, et la configuration du routage en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-111">This involves configuring one or more replicas to read-only access when running under the secondary role, and configuring read-only routing.</span></span>  
  
-   <span data-ttu-id="0cf7d-112">Gestion des [sauvegardes sur des réplicas secondaires](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) pour un groupe de disponibilité donné.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-112">Managing [backups on secondary replicas](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="0cf7d-113">Cela implique la configuration de l'emplacement d'exécution des travaux de sauvegarde, puis la création d'un script pour les travaux de sauvegarde pour implémenter vos préférences de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-113">This involves configuring where you prefer that backup jobs run and then scripting backup jobs to implement your backup preference.</span></span> <span data-ttu-id="0cf7d-114">Vous devez créer un script de travaux de sauvegarde pour chaque base de données dans le groupe de disponibilité sur chaque instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge un réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-114">you need to script backup jobs for every database in the availability group on every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica.</span></span>  
  
-   <span data-ttu-id="0cf7d-115">Suppression d'un groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-115">Deleting an availability group.</span></span>  
  
-   <span data-ttu-id="0cf7d-116">Migration entre clusters de groupes de disponibilité AlwaysOn pour la mise à niveau du système d'exploitation</span><span class="sxs-lookup"><span data-stu-id="0cf7d-116">Cross-cluster migration of AlwaysOn Availability Groups for OS upgrade</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0cf7d-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="0cf7d-117">Related Tasks</span></span>  
 <span data-ttu-id="0cf7d-118">**Pour configurer un groupe de disponibilité existant**</span><span class="sxs-lookup"><span data-stu-id="0cf7d-118">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="0cf7d-119">Ajouter un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-119">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-120">Supprimer un réplica secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-120">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-121">Ajouter une base de données à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-121">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="0cf7d-122">Supprimer une base de données secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-122">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-123">Supprimer une base de données primaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-123">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-124">Configurez la stratégie de basculement flexible pour contrôler les conditions du basculement automatique &#40;groupes de disponibilité AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-124">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover &#40;AlwaysOn Availability Groups&#41;</span></span>](configure-flexible-automatic-failover-policy.md)  
  
 <span data-ttu-id="0cf7d-125">**Pour gérer un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="0cf7d-125">**To manage an availability group**</span></span>  
  
-   [<span data-ttu-id="0cf7d-126">Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-127">Effectuer un basculement manuel planifié d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-127">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-128">Effectuer un basculement manuel forcé d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-128">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-129">Supprimer un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-129">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="0cf7d-130">**Pour gérer un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="0cf7d-130">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="0cf7d-131">Ajouter un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-131">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-132">Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-132">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-133">Supprimer un réplica secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-133">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-134">Modifier le mode de disponibilité d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-134">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-135">Modifier le mode de basculement d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-135">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-136">Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-136">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-137">Configurer l’accès en lecture seule sur un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-137">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-138">Configurer le routage en lecture seule pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-138">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-139">Modifier le délai d’expiration de session pour un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-139">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="0cf7d-140">**Pour gérer une base de données de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="0cf7d-140">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="0cf7d-141">Ajouter une base de données à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-141">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="0cf7d-142">Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-142">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-143">Supprimer une base de données primaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-143">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-144">Supprimer une base de données secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-144">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-145">Interrompre une base de données de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-145">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-146">Reprendre une base de données de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-146">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
 <span data-ttu-id="0cf7d-147">**Pour surveiller un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="0cf7d-147">**To monitor an availability group**</span></span>  
  
-   [<span data-ttu-id="0cf7d-148">Outils pour superviser les groupes de disponibilité Always On</span><span class="sxs-lookup"><span data-stu-id="0cf7d-148">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
 <span data-ttu-id="0cf7d-149">**Pour prendre en charge la migration des groupes de disponibilité vers un nouveau cluster WSFC (migration entre clusters)**</span><span class="sxs-lookup"><span data-stu-id="0cf7d-149">**To support migrating availability groups to a new WSFC cluster (cross-cluster migration)**</span></span>  
  
-   [<span data-ttu-id="0cf7d-150">Changer le contexte de cluster HADR de l’instance de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-150">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
-   [<span data-ttu-id="0cf7d-151">Placer un groupe de disponibilité hors connexion &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-151">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="0cf7d-152">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="0cf7d-152">Related Content</span></span>  
  
-   <span data-ttu-id="0cf7d-153">**Blogs :**</span><span class="sxs-lookup"><span data-stu-id="0cf7d-153">**Blogs:**</span></span>  
  
     [<span data-ttu-id="0cf7d-154">Blogs de l'équipe de SQL Server AlwaysOn : Blog officiel de l'équipe de SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="0cf7d-154">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="0cf7d-155">Blogs des ingénieurs du Service clientèle et du Support technique de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0cf7d-155">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="0cf7d-156">**Vidéos :**</span><span class="sxs-lookup"><span data-stu-id="0cf7d-156">**Videos:**</span></span>  
  
     [<span data-ttu-id="0cf7d-157">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 1 : Présentation de la solution haute disponibilité de la prochaine génération</span><span class="sxs-lookup"><span data-stu-id="0cf7d-157">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="0cf7d-158">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 2 : Génération d'une solution haute disponibilité critique à l'aide d'AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="0cf7d-158">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="0cf7d-159">**Livres blancs :**</span><span class="sxs-lookup"><span data-stu-id="0cf7d-159">**White papers:**</span></span>  
  
     [<span data-ttu-id="0cf7d-160">Livres blancs de Microsoft pour SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="0cf7d-160">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="0cf7d-161">Livres blancs de l'équipe de consultants clients de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0cf7d-161">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
  
## <a name="see-also"></a><span data-ttu-id="0cf7d-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0cf7d-162">See Also</span></span>  
 <span data-ttu-id="0cf7d-163">[Groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0cf7d-163">[AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="0cf7d-164">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0cf7d-164">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="0cf7d-165">Configuration d’une instance de serveur pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-165">Configuration of a Server Instance for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](configuration-of-a-server-instance-for-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="0cf7d-166">[Création et configuration des groupes de disponibilité &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0cf7d-166">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="0cf7d-167">[Secondaires actifs : réplicas secondaires accessibles en lecture &#40;groupes de disponibilité AlwaysOn&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="0cf7d-167">[Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="0cf7d-168">Secondaires actifs : sauvegarde sur les réplicas secondaires &#40;groupes de disponibilité AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-168">Active Secondaries: Backup on Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md)  
 <span data-ttu-id="0cf7d-169">[Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="0cf7d-169">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 <span data-ttu-id="0cf7d-170">[Stratégies AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="0cf7d-170">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="0cf7d-171">[Surveillance des groupes de disponibilité &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0cf7d-171">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="0cf7d-172">[Groupes de disponibilité AlwaysOn : interopérabilité &#40;SQL Server&#41;](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0cf7d-172">[AlwaysOn Availability Groups: Interoperability &#40;SQL Server&#41;](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="0cf7d-173">[Vue d’ensemble des instructions Transact-SQL pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="0cf7d-173">[Overview of Transact-SQL Statements for AlwaysOn Availability Groups &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="0cf7d-174">Vue d’ensemble des applets de commande PowerShell pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf7d-174">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
