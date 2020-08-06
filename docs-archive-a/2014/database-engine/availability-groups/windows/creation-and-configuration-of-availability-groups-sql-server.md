---
title: Création et configuration des groupes de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], creating
ms.assetid: 7f89fab8-6ee2-4273-9de0-e594bfb9407f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc33da393527c19985f5e7b214ba4bc02dc2f3af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710804"
---
# <a name="creation-and-configuration-of-availability-groups-sql-server"></a><span data-ttu-id="a4a17-102">Création et configuration des groupes de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4a17-102">Creation and Configuration of Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="a4a17-103">Les rubriques de cette section expliquent comment déployer une implémentation [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] sur les instances de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] qui résident sur des nœuds de clustering de basculement Windows Server différents dans un seul cluster de basculement WSFC.</span><span class="sxs-lookup"><span data-stu-id="a4a17-103">The topics in this section explain how to deploy a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] implementation on instances of [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] that reside on different Windows Server Failover Clustering (WSFC) nodes within a single WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="a4a17-104">Avant de créer votre premier groupe de disponibilité, il est fortement recommandé de vous familiariser avec les informations présentées dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4a17-104">Before you create your first availability group, we strongly recommend that you familiarize yourself with the information in the following topics:</span></span>  
  
 [<span data-ttu-id="a4a17-105">Conditions préalables requises, restrictions et recommandations pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-105">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
 <span data-ttu-id="a4a17-106">Cette rubrique décrit les conditions préalables requises, restrictions et recommandations applicables aux ordinateurs, les nœuds WSFC, les instances de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], les groupes de disponibilité, les réplicas et les bases de données.</span><span class="sxs-lookup"><span data-stu-id="a4a17-106">This topic describes the prerequisites, restrictions, and recommendations for computers; WSFC nodes; instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; availability groups, replicas, and databases.</span></span> <span data-ttu-id="a4a17-107">Cette rubrique contient également des informations sur les questions de sécurité.</span><span class="sxs-lookup"><span data-stu-id="a4a17-107">This topic also contains information about security considerations.</span></span>  
  
 [<span data-ttu-id="a4a17-108">Prise en main groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-108">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="a4a17-109">Contient des informations sur les étapes de configuration d'une instance de serveur, de création d'un groupe de disponibilité, de configuration du groupe de disponibilité pour les connexions clientes, de gestion des groupes de disponibilité et de surveillance des groupes de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a4a17-109">Contains information about the steps for configuring a server instance, creating an availability group, configuring the availability group for client connections, managing availability groups, and monitoring availability groups.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a4a17-110">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a4a17-110">Related Tasks</span></span>  
 <span data-ttu-id="a4a17-111">**Pour configurer une instance de serveur pour [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="a4a17-111">**To configure a server instance for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span></span>  
  
-   [<span data-ttu-id="a4a17-112">Activer et désactiver les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-112">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-113">Créer un point de terminaison de mise en miroir de bases de données pour groupes de disponibilité AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-113">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="a4a17-114">Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-114">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="a4a17-115">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-115">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
 <span data-ttu-id="a4a17-116">**Pour commencer à configurer des groupes de disponibilité AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="a4a17-116">**To get started with configuring AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="a4a17-117">Prise en main groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-117">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="a4a17-118">**Pour créer et configurer un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="a4a17-118">**To create and configure a new availability group**</span></span>  
  
-   [<span data-ttu-id="a4a17-119">Utiliser l’Assistant Groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-119">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a4a17-120">Créer un groupe de disponibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-120">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="a4a17-121">Créer un groupe de disponibilité &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-121">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="a4a17-122">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-122">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a4a17-123">Spécifier l’URL de point de terminaison lors de l’ajout ou lors de la modification d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-123">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="a4a17-124">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-124">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-125">Configurer la stratégie de basculement flexible pour contrôler les conditions du basculement automatique (groupes de disponibilité AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="a4a17-125">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="a4a17-126">Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-127">Configurer l’accès en lecture seule sur un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-127">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-128">Configurer le routage en lecture seule pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-128">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-129">Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-129">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-130">Démarrer le déplacement des données sur une base de données secondaire AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-130">Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;</span></span>](start-data-movement-on-an-always-on-secondary-database-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-131">Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-131">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-132">Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-132">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-133">Gestion des connexions et des travaux pour les bases de données d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-133">Management of Logins and Jobs for the Databases of an Availability Group &#40;SQL Server&#41;</span></span>](../../logins-and-jobs-for-availability-group-databases.md)  
  
 <span data-ttu-id="a4a17-134">**Pour résoudre les problèmes**</span><span class="sxs-lookup"><span data-stu-id="a4a17-134">**To troubleshoot**</span></span>  
  
-   [<span data-ttu-id="a4a17-135">Résoudre les problèmes de configuration de groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4a17-135">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="a4a17-136">Résoudre les problèmes liés à l’échec d’une opération d’ajout de fichier &#40;groupes de disponibilité AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="a4a17-136">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="a4a17-137">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="a4a17-137">Related Content</span></span>  
  
-   <span data-ttu-id="a4a17-138">**Blogs :**</span><span class="sxs-lookup"><span data-stu-id="a4a17-138">**Blogs:**</span></span>  
  
     [<span data-ttu-id="a4a17-139">AlwaysON - HADRON Learning Series : Worker Pool Usage for HADRON Enabled Databases (en anglais)</span><span class="sxs-lookup"><span data-stu-id="a4a17-139">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="a4a17-140">Blogs de l'équipe de SQL Server AlwaysOn : Blog officiel de l'équipe de SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="a4a17-140">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="a4a17-141">Blogs des ingénieurs du Service clientèle et du Support technique de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a4a17-141">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="a4a17-142">**Vidéos :**</span><span class="sxs-lookup"><span data-stu-id="a4a17-142">**Videos:**</span></span>  
  
     [<span data-ttu-id="a4a17-143">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 1 : Présentation de la solution haute disponibilité de la prochaine génération</span><span class="sxs-lookup"><span data-stu-id="a4a17-143">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="a4a17-144">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 2 : Génération d'une solution haute disponibilité critique à l'aide d'AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="a4a17-144">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="a4a17-145">**Livres blancs :**</span><span class="sxs-lookup"><span data-stu-id="a4a17-145">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="a4a17-146">Guide de solutions Microsoft SQL Server AlwaysOn pour la haute disponibilité et la récupération d'urgence</span><span class="sxs-lookup"><span data-stu-id="a4a17-146">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="a4a17-147">Livres blancs de Microsoft pour SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="a4a17-147">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="a4a17-148">Livres blancs de l'équipe de consultants clients de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a4a17-148">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="a4a17-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4a17-149">See Also</span></span>  
 <span data-ttu-id="a4a17-150">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a4a17-150">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="a4a17-151">[Administration d’un groupe de disponibilité &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a4a17-151">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="a4a17-152">[Stratégies AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="a4a17-152">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="a4a17-153">[Surveillance des groupes de disponibilité &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a4a17-153">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="a4a17-154">Groupes de disponibilité AlwaysOn : interopérabilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4a17-154">AlwaysOn Availability Groups: Interoperability (SQL Server)</span></span>](always-on-availability-groups-interoperability-sql-server.md)  
  
