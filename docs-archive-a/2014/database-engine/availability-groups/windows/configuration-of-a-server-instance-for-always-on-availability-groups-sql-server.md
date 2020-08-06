---
title: Configuration d’une instance de serveur pour les groupes de disponibilité Always On (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], about
ms.assetid: fad8db32-593e-49d5-989c-39eb8399c416
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3392e6189b687516e627d847acceedb165141117
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708675"
---
# <a name="configuration-of-a-server-instance-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="7ddc8-102">Configuration d’une instance de serveur pour les groupes de disponibilité Always On (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7ddc8-102">Configuration of a Server Instance for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="7ddc8-103">Cette rubrique contient des informations sur les conditions requises pour configurer une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour la prise en charge de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ddc8-103">This topic contains information about the requirements for configuring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7ddc8-104">Pour obtenir des informations de base sur la configuration nécessaire pour [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] et les restrictions pour les nœuds de clustering de basculement Windows Server (WSFC) et pour les instances de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], consultez [Conditions préalables requises, restrictions et recommandations pour les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="7ddc8-104">For essential information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites and restrictions for Windows Server Failover Clustering (WSFC) nodes and for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
 
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="7ddc8-105">Termes et définitions</span><span class="sxs-lookup"><span data-stu-id="7ddc8-105">Terms and Definitions</span></span>  
  
 <span data-ttu-id="7ddc8-106">Solution de haute disponibilité et de récupération d'urgence qui fournit une alternative au niveau de l'entreprise à la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-106">A high-availability and disaster-recovery solution that provides an enterprise-level replacement for database mirroring.</span></span> <span data-ttu-id="7ddc8-107">Un *groupe de disponibilité* prend en charge un environnement de basculement pour un ensemble discret de bases de données utilisateur, appelées *bases de données de disponibilité*, qui basculent ensemble.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-107">An *availability group* supports a failover environment for a discrete set of user databases, known as *availability databases*, that fail over together.</span></span>  
  
 <span data-ttu-id="7ddc8-108">réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="7ddc8-108">availability replica</span></span>  
 <span data-ttu-id="7ddc8-109">Instanciation d'un groupe de disponibilité hébergé par une instance spécifique de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et qui conserve une copie locale de chaque base de données de disponibilité appartenant au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-109">An instantiation of an availability group that is hosted by a specific instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and that maintains a local copy of each availability database that belongs to the availability group.</span></span> <span data-ttu-id="7ddc8-110">Il existe deux types de réplicas de disponibilité : un seul *réplica principal* et un à quatre *réplicas secondaires*.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-110">Two types of availability replicas exist: a single *primary replica* and one to four *secondary replicas*.</span></span> <span data-ttu-id="7ddc8-111">Les instances de serveur qui hébergent les réplicas de disponibilité pour un groupe de disponibilité donné doivent résider sur différents nœuds d'un même cluster WSFC (Clustering de basculement Windows Server).</span><span class="sxs-lookup"><span data-stu-id="7ddc8-111">The server instances that host the availability replicas for a given availability group must reside on different nodes of a single Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 [<span data-ttu-id="7ddc8-112">point de terminaison de mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="7ddc8-112">database mirroring endpoint</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
 <span data-ttu-id="7ddc8-113">Un point de terminaison est un objet SQL Server qui permet à SQL Server de communiquer sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-113">An endpoint is a SQL Server object that enables SQL Server to communicate over the network.</span></span> <span data-ttu-id="7ddc8-114">Pour participer à la mise en miroir de bases de données et/ou à [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , une instance de serveur requiert un point de terminaison spécial et dédié.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-114">To participate in database mirroring and/or [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] a server instance requires a special, dedicated endpoint.</span></span> <span data-ttu-id="7ddc8-115">Toutes les connexions de groupe de disponibilité et de mise en miroir sur une instance de serveur utilisent le même point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-115">All mirroring and availability group connections on a server instance use the same database mirroring endpoint.</span></span> <span data-ttu-id="7ddc8-116">Ce point de terminaison a un objectif spécifique et permet exclusivement de recevoir ces connexions provenant d'autres instances de serveur.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-116">This endpoint is a special-purpose endpoint used exclusively to receive these connections from other server instances.</span></span>  
  
##  <a name="to-configure-a-server-instance-to-support-alwayson-availability-groups"></a><a name="ConfigSI"></a><span data-ttu-id="7ddc8-117">Pour configurer une instance de serveur pour prendre en charge groupes de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7ddc8-117">To Configure a Server Instance to Support AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="7ddc8-118">Pour prendre en charge [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], une instance de serveur doit résider sur un nœud dans le cluster de basculement WSFC qui héberge le groupe de disponibilité, être compatible avec [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] et posséder un point de terminaison pour la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-118">To support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], a server instance must reside on a node in the WSFC failover cluster that hosts the availability group, be [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] enabled, and possess a database mirroring endpoint.</span></span>  
  
1.  <span data-ttu-id="7ddc8-119">Activez la fonctionnalité Groupes de disponibilité AlwaysOn sur chaque instance de serveur devant participer à un ou plusieurs groupes de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-119">Enable the AlwaysOn Availability Groups feature on every server instance that is to participate in one or more availability groups.</span></span> <span data-ttu-id="7ddc8-120">Une instance de serveur donnée peut héberger un seul réplica de disponibilité pour un groupe de disponibilité donné.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-120">A given server instance can host only a single availability replica for a given availability group.</span></span>  
  
2.  <span data-ttu-id="7ddc8-121">Veillez à ce que l'instance de serveur possède un point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-121">Ensure that the server instance possesses a database mirroring endpoint.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7ddc8-122">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="7ddc8-122">Related Tasks</span></span>  
 <span data-ttu-id="7ddc8-123">**Pour activer les groupes de disponibilité AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-123">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="7ddc8-124">Activer et désactiver les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ddc8-124">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="7ddc8-125">**Pour déterminer si un point de terminaison de mise en miroir de bases de données existe**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-125">**To determine whether a database mirroring endpoint exists**</span></span>  
  
-   [<span data-ttu-id="7ddc8-126">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7ddc8-126">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="7ddc8-127">**Pour créer un point de terminaison pour la mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-127">**To create a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="7ddc8-128">Créer un point de terminaison de mise en miroir de bases de données pour groupes de disponibilité AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="7ddc8-128">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="7ddc8-129">Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7ddc8-129">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="7ddc8-130">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7ddc8-130">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="7ddc8-131">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="7ddc8-131">Related Content</span></span>  
  
-   <span data-ttu-id="7ddc8-132">**Blogs :**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-132">**Blogs:**</span></span>  
  
     [<span data-ttu-id="7ddc8-133">AlwaysON - HADRON Learning Series : Worker Pool Usage for HADRON Enabled Databases (en anglais)</span><span class="sxs-lookup"><span data-stu-id="7ddc8-133">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="7ddc8-134">Blogs de l'équipe de SQL Server AlwaysOn : Blog officiel de l'équipe de SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7ddc8-134">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="7ddc8-135">Blogs des ingénieurs du Service clientèle et du Support technique de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ddc8-135">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="7ddc8-136">**Vidéos :**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-136">**Videos:**</span></span>  
  
     [<span data-ttu-id="7ddc8-137">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 1 : Présentation de la solution haute disponibilité de la prochaine génération</span><span class="sxs-lookup"><span data-stu-id="7ddc8-137">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="7ddc8-138">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 2 : Génération d'une solution haute disponibilité critique à l'aide d'AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7ddc8-138">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="7ddc8-139">**Livres blancs :**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-139">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="7ddc8-140">Guide de solutions Microsoft SQL Server AlwaysOn pour la haute disponibilité et la récupération d'urgence</span><span class="sxs-lookup"><span data-stu-id="7ddc8-140">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="7ddc8-141">Livres blancs de Microsoft pour SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="7ddc8-141">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="7ddc8-142">Livres blancs de l'équipe de consultants clients de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ddc8-142">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="7ddc8-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7ddc8-143">See Also</span></span>  
 <span data-ttu-id="7ddc8-144">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ddc8-144">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7ddc8-145">[Conditions préalables requises, restrictions et recommandations pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="7ddc8-145">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="7ddc8-146">[Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ddc8-146">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="7ddc8-147">[Groupes de disponibilité AlwaysOn : interopérabilité (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ddc8-147">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="7ddc8-148">[Clustering de basculement et groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ddc8-148">[Failover Clustering and AlwaysOn Availability Groups &#40;SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7ddc8-149">[Clustering de basculement Windows Server &#40;WSFC&#41; avec SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ddc8-149">[Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="7ddc8-150">Instances de cluster de basculement AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7ddc8-150">AlwaysOn Failover Cluster Instances</span></span>](../../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md)  
  
