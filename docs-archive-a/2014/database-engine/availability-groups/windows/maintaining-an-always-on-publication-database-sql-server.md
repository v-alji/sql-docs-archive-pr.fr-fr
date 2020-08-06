---
title: Maintenance d’une base de données de publication AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 55b345fe-2eb9-4b04-a900-63d858eec360
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8f36d29049140b6e5bbdfc1a4e716d41a766a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604714"
---
# <a name="maintaining-an-alwayson-publication-database-sql-server"></a><span data-ttu-id="303ae-102">Gestion d'une base de données de publication AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="303ae-102">Maintaining an AlwaysOn Publication Database (SQL Server)</span></span>
  <span data-ttu-id="303ae-103">Cette rubrique comporte des remarques spécifiques sur la gestion d'une base de données de publication lors de l'utilisation de groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="303ae-103">This topic discusses special considerations for maintaining a publication database when you use AlwaysOn availability groups.</span></span>  
  
 
  
##  <a name="maintaining-a-published-database-in-an-availability-group"></a><a name="MaintainPublDb"></a><span data-ttu-id="303ae-104">Maintenance d’une base de données publiée dans un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="303ae-104">Maintaining a Published Database in an Availability Group</span></span>  
 <span data-ttu-id="303ae-105">La gestion d'une base de données de publication AlwaysOn est quasiment identique à la gestion d'une base de données de publication standard. Il convient toutefois de prendre quelques précautions :</span><span class="sxs-lookup"><span data-stu-id="303ae-105">Maintaining an AlwaysOn publication database is basically the same as maintaining a standard publication database, with the following considerations:</span></span>  
  
-   <span data-ttu-id="303ae-106">L'administration doit être effectuée au niveau de l'hôte de réplica principal.</span><span class="sxs-lookup"><span data-stu-id="303ae-106">Administration must occur at the primary replica host.</span></span> <span data-ttu-id="303ae-107">Dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], les publications apparaissent dans le dossier **Publications locales** pour l'hôte de réplica principal et également pour les réplicas secondaires lisibles.</span><span class="sxs-lookup"><span data-stu-id="303ae-107">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], publications appear under the **Local Publications** folder for the primary replica host and also for readable secondary replicas.</span></span> <span data-ttu-id="303ae-108">Après un basculement, il est possible que vous soyez contraint d'actualiser manuellement [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] pour que la modification soit prise en compte si le serveur secondaire qui est devenu le principal n'était pas lisible.</span><span class="sxs-lookup"><span data-stu-id="303ae-108">After failover, you might have to manually refresh [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] for the change to be reflected if the secondary that was promoted to primary was not readable.</span></span>  
  
-   <span data-ttu-id="303ae-109">Le moniteur de réplication affiche toujours les informations de publication sous le serveur de publication d'origine.</span><span class="sxs-lookup"><span data-stu-id="303ae-109">Replication Monitor always displays publication information under the original publisher.</span></span> <span data-ttu-id="303ae-110">Toutefois, ces informations peuvent être consultées dans le moniteur de réplication à partir de tout réplica en ajoutant le serveur de publication d'origine comme serveur.</span><span class="sxs-lookup"><span data-stu-id="303ae-110">However, this information can be viewed in Replication Monitor from any replica by adding the original publisher as a server.</span></span>  
  
-   <span data-ttu-id="303ae-111">Si vous faites appel aux procédures stockées ou aux Replication Management Objects pour gérer la réplication sur le principal actuel, vous devez spécifier comme serveur de publication le nom de l'instance où la base de données est activée pour la réplication (le serveur de publication d'origine).</span><span class="sxs-lookup"><span data-stu-id="303ae-111">When using stored procedures or Replication Management Objects (RMO) to administer replication at the current primary, for cases in which you specify the Publisher name, you must specify the name of the instance on which the database was enabled for replication (the original publisher).</span></span> <span data-ttu-id="303ae-112">Pour déterminer le nom approprié, utilisez la fonction `PUBLISHINGSERVERNAME`.</span><span class="sxs-lookup"><span data-stu-id="303ae-112">To determine the appropriate name, use the `PUBLISHINGSERVERNAME` function.</span></span> <span data-ttu-id="303ae-113">Lorsqu'une base de données de publication joint un groupe de disponibilité, les métadonnées de réplication stockées dans les réplicas de bases de données secondaires sont identiques à celles du principal.</span><span class="sxs-lookup"><span data-stu-id="303ae-113">When a publishing database joins an availability group, the replication metadata stored in the secondary database replicas is identical to that at the primary.</span></span> <span data-ttu-id="303ae-114">Par conséquent, en cas de bases de données de publication activées pour la réplication sur le principal, le nom d'instance du serveur de publication stocké dans les tables système du serveur secondaire est celui du serveur principal, et non du serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="303ae-114">Consequently, for publication databases enabled for replication at the primary, the publisher instance name stored in system tables at the secondary is the name of the primary, not the secondary.</span></span> <span data-ttu-id="303ae-115">Cela affecte la configuration et l'administration de la réplication si la base de données de publication bascule sur un serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="303ae-115">This affects replication configuration and maintenance if the publication database fails over to a secondary.</span></span> <span data-ttu-id="303ae-116">Par exemple, si vous configurez la réplication avec des procédures stockées sur un serveur secondaire après le basculement et que vous souhaitez un abonnement par extraction à une base de données de publication qui a été activée sur un autre réplica, vous devez spécifier le nom du serveur de publication d’origine au lieu du serveur de publication actuel comme *@publisher* paramètre de `sp_addpullsubscription` ou `sp_addmergepulllsubscription` .</span><span class="sxs-lookup"><span data-stu-id="303ae-116">For example, if you are configuring replication with stored procedures at a secondary after failover, and you want a pull subscription to a publication database that was enabled at a different replica, you must specify the name of the original publisher instead of the current publisher as the *@publisher* parameter of `sp_addpullsubscription` or `sp_addmergepulllsubscription`.</span></span> <span data-ttu-id="303ae-117">Toutefois, si vous activez une base de données de publication après un basculement, le nom de l'instance du serveur de publication stocké dans les tables système est le nom de l'hôte principal actuel.</span><span class="sxs-lookup"><span data-stu-id="303ae-117">However, if you enable a publication database after failover, the publisher instance name stored in the system tables is the name of the current primary host.</span></span> <span data-ttu-id="303ae-118">Dans ce cas, vous devez utiliser le nom d’hôte du réplica principal actuel pour le *@publisher* paramètre.</span><span class="sxs-lookup"><span data-stu-id="303ae-118">In this case, you would use the host name of the current primary replica for the *@publisher* parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="303ae-119">Pour certaines procédures, telles que `sp_addpublication` , le *@publisher* paramètre est pris en charge uniquement pour les serveurs de publication qui ne sont pas des instances de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ; dans ce cas, il n’est pas pertinent pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="303ae-119">For some procedures, such as `sp_addpublication`, the *@publisher* parameter is supported only for publishers that are not instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; in these cases, it is not relevant for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span></span>  
  
-   <span data-ttu-id="303ae-120">Pour synchroniser un abonnement dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] après un basculement, synchronisez les abonnements par extraction à partir de l'abonné, puis synchronisez les abonnements par émission de données à partir du serveur de publication actif.</span><span class="sxs-lookup"><span data-stu-id="303ae-120">To synchronize a subscription in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] after a failover, synchronize pull subscriptions from the subscriber and synchronize push subscriptions from the active publisher.</span></span>  
  
##  <a name="removing-a-published-database-from-an-availability-group"></a><a name="RemovePublDb"></a> <span data-ttu-id="303ae-121">Suppression d'une base de données publiée d'un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="303ae-121">Removing a Published Database from an Availability Group</span></span>  
 <span data-ttu-id="303ae-122">Considérez les points suivants lorsqu'une base de données publiée est supprimée d'un groupe de disponibilité, ou lorsqu'un groupe de disponibilité avec une base de données membre publiée est supprimé.</span><span class="sxs-lookup"><span data-stu-id="303ae-122">Consider the following issues if a published database is removed from an availability group, or if an availability group that has a published member database is dropped.</span></span>  
  
-   <span data-ttu-id="303ae-123">Si la base de données de publication sur le serveur de publication d’origine est supprimée d’un réplica principal de groupe de disponibilité, vous devez exécuter `sp_redirect_publisher` sans spécifier de valeur pour le *@redirected_publisher* paramètre pour supprimer la redirection pour la paire serveur de publication/base de données.</span><span class="sxs-lookup"><span data-stu-id="303ae-123">If the publication database at the original publisher is removed from an availability group primary replica, you must run `sp_redirect_publisher` without specifying a value for the *@redirected_publisher* parameter in order to remove the redirection for the publisher/database pair.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB';  
    ```  
  
     <span data-ttu-id="303ae-124">La base de données restera à l'état de récupération dans le principal et devra être restaurée.</span><span class="sxs-lookup"><span data-stu-id="303ae-124">The database will be left in the recovering state at the primary and must be restored.</span></span> <span data-ttu-id="303ae-125">Après cela, la réplication doit s'exécuter sans modification sur le serveur de publication d'origine.</span><span class="sxs-lookup"><span data-stu-id="303ae-125">Once you do this, replication should work unchanged against the original Publisher.</span></span>  
  
-   <span data-ttu-id="303ae-126">Si la base de données de publication bascule du serveur de publication d'origine vers un réplica et elle est supprimée du réplica principal de groupe de disponibilité, utilisez la procédure stockée `sp_redirect_publisher` pour rediriger explicitement le serveur de publication d'origine vers nouveau serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="303ae-126">If the publication database fails over from the original publisher to a replica and the database is removed from the availability group primary replica, use the stored procedure `sp_redirect_publisher` to explicitly redirect the original publisher to the new publisher.</span></span> <span data-ttu-id="303ae-127">La base de données restera à l'état de récupération et devra être restaurée.</span><span class="sxs-lookup"><span data-stu-id="303ae-127">The database will be left in the recovering state and must be restored.</span></span> <span data-ttu-id="303ae-128">Après cela, la réplication doit continuer à fonctionner de la même manière qu'avec le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="303ae-128">Once you do this, replication should continue to work as it did under the availability group.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB',  
        @redirected_publisher = 'MyNewPublisher';  
    ```  
  
     <span data-ttu-id="303ae-129">Ne supprimez pas le serveur distant du serveur de publication d'origine du serveur de distribution, même si le serveur n'est plus accessible.</span><span class="sxs-lookup"><span data-stu-id="303ae-129">Do not remove the remote server for the original publisher from the distributor, even if the server can no longer be accessed.</span></span> <span data-ttu-id="303ae-130">Les métadonnées du serveur du serveur de publication d'origine sont requises sur le serveur de distribution pour satisfaire les requêtes de métadonnées de publication.</span><span class="sxs-lookup"><span data-stu-id="303ae-130">The server metadata for the original publisher is needed at the distributor to satisfy publication metadata queries.</span></span>  
  
-   <span data-ttu-id="303ae-131">Si un groupe de disponibilité complet est supprimé, le comportement d'une base de données membre répliquée est le même que lorsqu'une base de données publiée est supprimée d'un groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="303ae-131">If a complete availability group is removed, the behavior with regard to a member replicated database is the same as when a published database is removed from an availability group.</span></span> <span data-ttu-id="303ae-132">La réplication peut être reprise à partir du dernier principal dès que la base de données a été restaurée et la redirection a été modifiée.</span><span class="sxs-lookup"><span data-stu-id="303ae-132">Replication can be resumed from the last primary as soon as the database has been restored and the redirection has been modified.</span></span> <span data-ttu-id="303ae-133">Si la base de données est restaurée sur son serveur de publication d'origine, la redirection doit être supprimée.</span><span class="sxs-lookup"><span data-stu-id="303ae-133">If the database is restored at its original publisher, redirection should be removed.</span></span> <span data-ttu-id="303ae-134">Si la base de données est restaurée sur un hôte différent, la redirection doit être explicitement dirigée vers le nouvel hôte.</span><span class="sxs-lookup"><span data-stu-id="303ae-134">If the database is restored at a different host, redirection should be explicitly directed to the new host.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="303ae-135">Lorsqu'un groupe de disponibilité comportant des bases de données membres publiées est supprimé, ou lorsqu'une base de données publiée est est supprimée d'un groupe de disponibilité, toutes les copies des bases de données publiées sont laissées à l'état de récupération.</span><span class="sxs-lookup"><span data-stu-id="303ae-135">When an availability group is removed that has published member databases, or a published database is removed from an availability group, all copies of the published databases will be left in the recovering state.</span></span> <span data-ttu-id="303ae-136">Si elles sont restaurées, chacune apparaîtra comme une base de données publiée.</span><span class="sxs-lookup"><span data-stu-id="303ae-136">If restored, each will appear as a published database.</span></span> <span data-ttu-id="303ae-137">Une seule copie doit être conservée avec les métadonnées de publication.</span><span class="sxs-lookup"><span data-stu-id="303ae-137">Only one copy should be retained with publication metadata.</span></span> <span data-ttu-id="303ae-138">Pour désactiver la réplication d'une copie de base de données publiée, commencez par supprimer tous les abonnements et toutes les publications de la base de données.</span><span class="sxs-lookup"><span data-stu-id="303ae-138">To disable replication for a published database copy, first remove all subscriptions and publications from the database.</span></span>  
  
     <span data-ttu-id="303ae-139">Exécutez `sp_dropsubscription` pour supprimer les abonnements de publication.</span><span class="sxs-lookup"><span data-stu-id="303ae-139">Run `sp_dropsubscription` to remove publication subscriptions.</span></span> <span data-ttu-id="303ae-140">Veillez à définir le paramètre *@ignore_distributributor* sur 1 pour conserver les métadonnées de la base de données de publication active sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="303ae-140">Make sure to set the parameter *@ignore_distributributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    USE MyDBName;  
    GO  
  
    EXEC sys.sp_dropsubscription   
        @subscriber = 'MySubscriber',  
        @publication = 'MyPublication',  
        @article = 'all',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="303ae-141">Exécutez `sp_droppublication` pour supprimer toutes les publications.</span><span class="sxs-lookup"><span data-stu-id="303ae-141">Run `sp_droppublication` to remove all publications.</span></span> <span data-ttu-id="303ae-142">Là encore, affectez la valeur 1 au paramètre *@ignore_distributor* pour conserver les métadonnées de la base de données de publication active sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="303ae-142">Again, set the parameter *@ignore_distributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    EXEC sys.sp_droppublication   
        @publication = 'MyPublication',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="303ae-143">Exécutez `sp_replicationdboption` pour désactiver la réplication pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="303ae-143">Run `sp_replicationdboption` to disable replication for the database.</span></span>  
  
    ```  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'false';  
    ```  
  
     <span data-ttu-id="303ae-144">À ce stade, la copie de la base de données publiée peut être conservée ou supprimée.</span><span class="sxs-lookup"><span data-stu-id="303ae-144">At this point, the copy of the published database can be retained or dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="303ae-145">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="303ae-145">Related Tasks</span></span>  
  
-   [<span data-ttu-id="303ae-146">Configurer la réplication pour les groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="303ae-146">Configure Replication for AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="303ae-147">Réplication, Change Tracking, capture de données modifiées et groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="303ae-147">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="303ae-148">FAQ sur l’administration de la réplication</span><span class="sxs-lookup"><span data-stu-id="303ae-148">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
-   [<span data-ttu-id="303ae-149">Abonnés de réplication et groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="303ae-149">Replication Subscribers and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replication-subscribers-and-always-on-availability-groups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="303ae-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="303ae-150">See Also</span></span>  
 <span data-ttu-id="303ae-151">[Conditions préalables requises, restrictions et recommandations pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="303ae-151">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="303ae-152">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="303ae-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="303ae-153">[Groupes de disponibilité AlwaysOn : interopérabilité (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="303ae-153">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="303ae-154">Réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="303ae-154">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
  
  
