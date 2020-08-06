---
title: Démarrer le déplacement des données sur une base de données secondaire AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], databases
ms.assetid: 498eb3fb-6a43-434d-ad95-68a754232c45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ce4f80b456244cd6e024377383abe75e002057a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708651"
---
# <a name="start-data-movement-on-an-alwayson-secondary-database-sql-server"></a><span data-ttu-id="af6a5-102">Démarrer un mouvement de données sur une base de données secondaire AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="af6a5-102">Start Data Movement on an AlwaysOn Secondary Database (SQL Server)</span></span>
  <span data-ttu-id="af6a5-103">Cette rubrique contient des informations sur le démarrage de la synchronisation des données après avoir ajouté une base de données à un groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="af6a5-103">This topic contains information about how to start data synchronization after you add a database to an AlwaysOn availability group.</span></span> <span data-ttu-id="af6a5-104">Pour chaque nouveau réplica principal, les bases de données secondaires doivent être préparées sur les instances de serveur qui hébergent les réplicas secondaires.</span><span class="sxs-lookup"><span data-stu-id="af6a5-104">For each new primary replica, secondary databases must be prepared on the server instances that host the secondary replicas.</span></span> <span data-ttu-id="af6a5-105">Puis, chacune de ces bases de données secondaires doit être attachée manuellement au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="af6a5-105">Then each of these secondary databases must be manually joined to the availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af6a5-106">Si les chemins d’accès aux fichiers sont identiques sur chaque instance de serveur qui héberge un réplica de disponibilité pour un groupe de disponibilité, [l’Assistant Nouveau groupe de disponibilité](use-the-availability-group-wizard-sql-server-management-studio.md), [l’Assistant Ajouter un réplica au groupe de disponibilité](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)ou [l’Assistant Ajouter une base de données au groupe de disponibilité](availability-group-add-database-to-group-wizard.md) peut être en mesure de démarrer automatiquement la synchronisation des données.</span><span class="sxs-lookup"><span data-stu-id="af6a5-106">If the file paths are identical on every server instance that hosts an availability replica for an availability group, the [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md) might be able to automatically start data synchronization for you.</span></span>  
  
 <span data-ttu-id="af6a5-107">Pour démarrer la synchronisation des données manuellement, vous devez vous connecter, tour à tour, à chaque instance de serveur qui héberge un réplica secondaire pour le groupe de disponibilité et procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="af6a5-107">To start data synchronization manually, you need to connect, in turn, to each server instance that is hosting a secondary replica for the availability group and complete the following steps:</span></span>  
  
1.  <span data-ttu-id="af6a5-108">Restaurez les sauvegardes actuelles de chaque base de données primaire et de son journal des transactions (à l'aide de RESTORE WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="af6a5-108">Restore current backups of each primary database and its transaction log (using RESTORE WITH NORECOVERY).</span></span> <span data-ttu-id="af6a5-109">Vous pouvez utiliser l'une des autres approches suivantes :</span><span class="sxs-lookup"><span data-stu-id="af6a5-109">You can use either of the following alternative approaches:</span></span>  
  
    -   <span data-ttu-id="af6a5-110">Restaurez manuellement une sauvegarde récente de la base de données primaire à l'aide de RESTORE WITH NORECOVERY, puis restaurez chaque sauvegarde de journal suivante à l'aide de RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="af6a5-110">Manually restore a recent database backup of the primary database using RESTORE WITH NORECOVERY, and then restore each subsequent log backup using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="af6a5-111">Effectuez cette séquence de restauration sur chaque instance de serveur qui héberge un réplica secondaire pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="af6a5-111">Perform this restore sequence on every server instance that hosts a secondary replica for the availability group.</span></span>  
  
         <span data-ttu-id="af6a5-112">**Pour plus d’informations :**</span><span class="sxs-lookup"><span data-stu-id="af6a5-112">**For more information:**</span></span>  
  
         [<span data-ttu-id="af6a5-113">Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="af6a5-113">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
    -   <span data-ttu-id="af6a5-114">Si vous ajoutez une ou plusieurs bases de données principales pour la copie des journaux de transaction à un groupe de disponibilité, vous pourrez peut-être effectuer une migration d'une ou de plusieurs des bases de données secondaires correspondantes depuis la copie des journaux de transaction vers des groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="af6a5-114">If you are adding one or more log shipping primary databases to an availability group, you might be able to migrate one or more of the corresponding secondary databases from log shipping to AlwaysOn Availability Groups.</span></span> <span data-ttu-id="af6a5-115">La migration d'une base de données secondaire pour la copie des journaux de transaction nécessite l'utilisation du même nom de base de données que la base de données principale et sa présence sur une instance de serveur qui héberge un réplica secondaire pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="af6a5-115">Migrating a log shipping secondary database requires that it use the same database name as the primary database and that it reside on a server instance that is hosting a secondary replica for the availability group.</span></span> <span data-ttu-id="af6a5-116">Par ailleurs, le groupe de disponibilité doit être configuré de sorte que le réplica principal corresponde à la préférence pour les sauvegardes et qu'il soit candidat à l'exécution de sauvegardes (autrement dit, que sa priorité de sauvegarde soit >0).</span><span class="sxs-lookup"><span data-stu-id="af6a5-116">Furthermore, the availability group must be configured so that the primary replica is preferred for backups and is a candidate for performing backups (that is, that has a backup priority that is >0).</span></span> <span data-ttu-id="af6a5-117">Une fois que le travail de sauvegarde a été exécuté sur la base de données principale, vous devez le désactiver. De même, une fois que le travail de restauration a été exécuté sur une base de données secondaire donnée, vous devez le désactiver.</span><span class="sxs-lookup"><span data-stu-id="af6a5-117">Once the backup job has run on the primary database, you will need to disable the backup job, and once the restore job has run on a given secondary database, you will need to disable the restore job.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="af6a5-118">Après avoir créé toutes les bases de données secondaires pour le groupe de disponibilité, si vous souhaitez effectuer des sauvegardes sur des réplicas secondaires, vous devez reconfigurer la préférence de sauvegarde automatisée du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="af6a5-118">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you will need to re-configure the automated backup preference of the availability group.</span></span>  
  
         <span data-ttu-id="af6a5-119">**Pour plus d’informations :**</span><span class="sxs-lookup"><span data-stu-id="af6a5-119">**For more information:**</span></span>  
  
         [<span data-ttu-id="af6a5-120">Conditions préalables à la migration de la copie des journaux de session vers groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="af6a5-120">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
         [<span data-ttu-id="af6a5-121">Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="af6a5-121">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
2.  <span data-ttu-id="af6a5-122">Dès que possible, attachez chaque base de données secondaire récemment préparée au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="af6a5-122">As soon as possible, join each newly prepared secondary database to the availability group.</span></span>  
  
     <span data-ttu-id="af6a5-123">**Pour plus d’informations :**</span><span class="sxs-lookup"><span data-stu-id="af6a5-123">**For more information:**</span></span>  
  
     [<span data-ttu-id="af6a5-124">Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="af6a5-124">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="LaunchWiz"></a> <span data-ttu-id="af6a5-125">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="af6a5-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="af6a5-126">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="af6a5-126">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="af6a5-127">Utiliser l’Assistant Ajouter un réplica au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="af6a5-127">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="af6a5-128">Utiliser l’Assistant Ajouter une base de données au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="af6a5-128">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="af6a5-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af6a5-129">See Also</span></span>  
 [<span data-ttu-id="af6a5-130">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="af6a5-130">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
