---
title: 'Secondaires actifs : sauvegarde sur les réplicas secondaires (groupes de disponibilité Always On) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- backup priority
- backup on secondary replicas
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], backup on secondary replicas
- active secondary replicas [SQL Server], backup on
- automated backup preference
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 82afe51b-71d1-4d5b-b20a-b57afc002405
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0cf899cdbeb1ae4ede6c9196b8eb93a9d9e54f05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701940"
---
# <a name="active-secondaries-backup-on-secondary-replicas-always-on-availability-groups"></a><span data-ttu-id="3bbf4-102">Secondaires actifs : sauvegarde sur les réplicas secondaires (groupes de disponibilité Always On)</span><span class="sxs-lookup"><span data-stu-id="3bbf4-102">Active Secondaries: Backup on Secondary Replicas (Always On Availability Groups)</span></span>
  <span data-ttu-id="3bbf4-103">Les fonctions secondaires actives [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] incluent la prise en charge des opérations de sauvegarde sur les réplicas secondaires.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-103">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] active secondary capabilities include support for performing backup operations on secondary replicas.</span></span> <span data-ttu-id="3bbf4-104">Les opérations de sauvegarde peuvent solliciter de manière significative les E/S et l'UC (avec la compression de sauvegarde).</span><span class="sxs-lookup"><span data-stu-id="3bbf4-104">Backup operations can put significant strain on I/O and CPU (with backup compression).</span></span> <span data-ttu-id="3bbf4-105">Le déchargement des sauvegardes vers un réplica secondaire synchronisé ou en cours de synchronisation vous permet d'utiliser les ressources sur l'instance de serveur qui héberge le réplica principal pour vos charges de travail de niveau 1.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-105">Offloading backups to a synchronized or synchronizing secondary replica allows you to use the resources on server instance that hosts the primary replica for your tier-1 workloads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3bbf4-106">Les instructions RESTORE ne sont pas autorisées sur les bases de données primaire ou secondaire d'un groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-106">RESTORE statements are not allowed on either the primary or secondary databases of an availability group.</span></span>  
  
  
  
##  <a name="backup-types-supported-on-secondary-replicas"></a><a name="SupportedBuTypes"></a> <span data-ttu-id="3bbf4-107">Types de sauvegardes pris en charge sur les réplicas secondaires</span><span class="sxs-lookup"><span data-stu-id="3bbf4-107">Backup Types Supported on Secondary Replicas</span></span>  
  
-   <span data-ttu-id="3bbf4-108">`BACKUP DATABASE`prend en charge uniquement la copie seule des sauvegardes complètes de la base de données, des fichiers ou des groupes de fichiers lorsqu'elle est exécutée sur les réplicas secondaires.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-108">`BACKUP DATABASE` supports only copy-only full backups of databases, files, or filegroups when it is executed on secondary replicas.</span></span> <span data-ttu-id="3bbf4-109">Notez que les sauvegardes de type copie seule n'affectent pas la séquence de journaux de transactions consécutifs ou n'effacent pas la bitmap différentielle.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-109">Note that copy-only backups do not impact the log chain or clear the differential bitmap.</span></span>  
  
-   <span data-ttu-id="3bbf4-110">Les sauvegardes différentielles ne sont pas prises en charge sur les réplicas secondaires.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-110">Differential backups are not supported on secondary replicas.</span></span>  
  
-   <span data-ttu-id="3bbf4-111">**BACKUP LOG** prend uniquement en charge les sauvegardes de journaux régulières (l’option COPY_ONLY n’est pas prise en charge pour les sauvegardes de fichiers journaux sur des réplicas secondaires).</span><span class="sxs-lookup"><span data-stu-id="3bbf4-111">**BACKUP LOG** supports only regular log backups (the COPY_ONLY option is not supported for log backups on secondary replicas).</span></span>  
  
     <span data-ttu-id="3bbf4-112">Une séquence de journaux de transactions consécutifs cohérente est garantie sur les sauvegardes des journaux effectuées sur les réplicas (principaux ou secondaires), quel que soit leur mode de disponibilité (avec validation synchrone ou validation asynchrone).</span><span class="sxs-lookup"><span data-stu-id="3bbf4-112">A consistent log chain is ensured across log backups taken on any of the replicas (primary or secondary), irrespective of their availability mode (synchronous-commit or asynchronous-commit).</span></span>  
  
-   <span data-ttu-id="3bbf4-113">Pour sauvegarder une base de données secondaire, un réplica secondaire doit pouvoir communiquer avec le réplica principal et doit être `SYNCHRONIZED` ou `SYNCHRONIZING`.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-113">To back up a secondary database, a secondary replica must be able to communicate with the primary replica and must be `SYNCHRONIZED` or `SYNCHRONIZING`.</span></span>  
  
##  <a name="configuring-where-backup-jobs-run"></a><a name="WhereBuJobsRun"></a><span data-ttu-id="3bbf4-114">Configuration de l’emplacement d’exécution des travaux de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="3bbf4-114">Configuring Where Backup Jobs Run</span></span>  
 <span data-ttu-id="3bbf4-115">L'exécution de sauvegardes sur un réplica secondaire pour décharger la charge de travail de sauvegarde du serveur de production principal constitue un énorme avantage.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-115">Performing backups on a secondary replica to offload the backup workload from the primary production server is a great benefit.</span></span> <span data-ttu-id="3bbf4-116">Cependant, les sauvegardes sur des réplicas secondaires compliquent considérablement la détermination de l'emplacement d'exécution des travaux de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-116">However, performing backups on secondary replicas introduce significant complexity to the process of determining where backup jobs should run.</span></span> <span data-ttu-id="3bbf4-117">Pour résoudre ce problème, configurez l'emplacement d'exécution des travaux de sauvegarde comme suit :</span><span class="sxs-lookup"><span data-stu-id="3bbf4-117">To address this, configure where backup jobs run as follows:</span></span>  
  
1.  <span data-ttu-id="3bbf4-118">Configurez le groupe de disponibilité pour spécifier les réplicas de disponibilité de votre choix pour effectuer les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-118">Configure the availability group to specify which availability replicas where you would prefer backups to be performed.</span></span> <span data-ttu-id="3bbf4-119">Pour plus d’informations, consultez les paramètres *AUTOMATED_BACKUP_PREFERENCE* et *BACKUP_PRIORITY* dans [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) ou [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3bbf4-119">For more information, see *AUTOMATED_BACKUP_PREFERENCE* and *BACKUP_PRIORITY* parameters in [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) or [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
2.  <span data-ttu-id="3bbf4-120">Créez les travaux de sauvegarde par script pour chaque base de données de disponibilité sur chaque instance de serveur qui héberge un réplica de disponibilité candidat pour effectuer des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-120">Create scripted backup jobs for every availability database on every server instance that hosts an availability replica that is a candidate for performing backups.</span></span> <span data-ttu-id="3bbf4-121">Pour plus d’informations, consultez la section « Suivi : Après la configuration de la sauvegarde sur les réplicas secondaires » dans [Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3bbf4-121">For more information, see the "Follow Up: After Configuring Backup on Secondary Replicas" section of [Configure Backup on Availability Replicas &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3bbf4-122">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3bbf4-122">Related Tasks</span></span>  
 <span data-ttu-id="3bbf4-123">**Pour configurer la sauvegarde sur les réplicas secondaires**</span><span class="sxs-lookup"><span data-stu-id="3bbf4-123">**To configure backup on secondary replicas**</span></span>  
  
-   [<span data-ttu-id="3bbf4-124">Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3bbf4-124">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
 <span data-ttu-id="3bbf4-125">**Pour déterminer si le réplica actuel est le réplica de sauvegarde par défaut**</span><span class="sxs-lookup"><span data-stu-id="3bbf4-125">**To determine whether the current replica is the preferred backup replica**</span></span>  
  
-   [<span data-ttu-id="3bbf4-126">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="3bbf4-126">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
  
 <span data-ttu-id="3bbf4-127">**Pour créer un travail de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="3bbf4-127">**To create a backup job**</span></span>  
  
-   [<span data-ttu-id="3bbf4-128">Utiliser l'Assistant Plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="3bbf4-128">Use the Maintenance Plan Wizard</span></span>](../../../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
-   [<span data-ttu-id="3bbf4-129">Implémenter des travaux</span><span class="sxs-lookup"><span data-stu-id="3bbf4-129">Implement Jobs</span></span>](../../../ssms/agent/implement-jobs.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="3bbf4-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3bbf4-130">See Also</span></span>  
 <span data-ttu-id="3bbf4-131">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3bbf4-131">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="3bbf4-132">[Sauvegardes de type copie seule &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3bbf4-132">[Copy-Only Backups &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span></span>  
 <span data-ttu-id="3bbf4-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3bbf4-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span></span>  
 [<span data-ttu-id="3bbf4-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3bbf4-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
