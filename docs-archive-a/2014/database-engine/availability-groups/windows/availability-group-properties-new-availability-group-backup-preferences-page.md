---
title: 'Propriétés du groupe de disponibilité : nouveau groupe de disponibilité (page préférences de sauvegarde) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.backuppreferences.f1
helpviewer_keywords:
- read-only routing
ms.assetid: 65fff22d-5963-4a8c-8b31-fe9ab247a03e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7914d4b1d7af06bcaf4f3fd05a260138e3edf5fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601114"
---
# <a name="availability-group-properties-new-availability-group-backup-preferences-page"></a><span data-ttu-id="f8320-102">Propriétés d’un groupe de disponibilité : Nouveau groupe de disponibilité (page Préférences de sauvegarde)</span><span class="sxs-lookup"><span data-stu-id="f8320-102">Availability Group Properties: New Availability Group (Backup Preferences Page)</span></span>
  <span data-ttu-id="f8320-103">Utilisez cette boîte de dialogue pour afficher et modifier les préférences de sauvegarde du groupe de disponibilité sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f8320-103">Use this dialog box to view and change the backup preferences of the selected availability group.</span></span>  
  
 <span data-ttu-id="f8320-104">**Pour afficher les propriétés d'un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="f8320-104">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="f8320-105">Afficher les propriétés d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f8320-105">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="f8320-106">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f8320-106">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="where-should-backups-occur"></a><span data-ttu-id="f8320-107">Où les sauvegardes doivent-elles être effectuées ?</span><span class="sxs-lookup"><span data-stu-id="f8320-107">Where should backups occur?</span></span>  
 <span data-ttu-id="f8320-108">**Préférer secondaire**</span><span class="sxs-lookup"><span data-stu-id="f8320-108">**Prefer Secondary**</span></span>  
 <span data-ttu-id="f8320-109">Spécifie que les sauvegardes doivent se produire sur un réplica secondaire sauf lorsque le réplica principal est le seul réplica en ligne.</span><span class="sxs-lookup"><span data-stu-id="f8320-109">Specifies that backups should occur on a secondary replica except when the primary replica is the only replica online.</span></span> <span data-ttu-id="f8320-110">Dans ce cas, la sauvegarde doit se produire sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f8320-110">In that case, the backup should occur on the primary replica.</span></span> <span data-ttu-id="f8320-111">Il s'agit de l'option par défaut.</span><span class="sxs-lookup"><span data-stu-id="f8320-111">This is the default option.</span></span>  
  
 <span data-ttu-id="f8320-112">**Secondaire uniquement**</span><span class="sxs-lookup"><span data-stu-id="f8320-112">**Secondary only**</span></span>  
 <span data-ttu-id="f8320-113">Spécifie que les sauvegardes ne doivent jamais être effectuées sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f8320-113">Specifies that backups should never be performed on the primary replica.</span></span> <span data-ttu-id="f8320-114">Si le réplica principal est le seul réplica en ligne, la sauvegarde ne doit pas avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="f8320-114">If the primary replica is the only replica online, the backup should not occur.</span></span>  
  
 <span data-ttu-id="f8320-115">**Primaire**</span><span class="sxs-lookup"><span data-stu-id="f8320-115">**Primary**</span></span>  
 <span data-ttu-id="f8320-116">Spécifie que les sauvegardes doivent toujours avoir lieu sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f8320-116">Specifies that the backups should always occur on the primary replica.</span></span> <span data-ttu-id="f8320-117">Cette option est utile si vous avez besoin de fonctionnalités de sauvegarde, telles que la création de sauvegardes différentielles, qui ne sont pas prises en charge lorsque la sauvegarde est exécutée sur un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="f8320-117">This option is useful if you need backup features, such as creating differential backups, that are not supported when backup is run on a secondary replica.</span></span>  
  
 <span data-ttu-id="f8320-118">**Tout réplica**</span><span class="sxs-lookup"><span data-stu-id="f8320-118">**Any Replica**</span></span>  
 <span data-ttu-id="f8320-119">Spécifie que vous préférez que les travaux de sauvegarde ignorent le rôle des réplicas de disponibilité lorsque vous choisissez le réplica pour effectuer les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="f8320-119">Specifies that you prefer that backup jobs ignore the role of the availability replicas when choosing the replica to perform backups.</span></span> <span data-ttu-id="f8320-120">Notez que les travaux de sauvegarde peuvent évaluer d'autres facteurs tels que la priorité de sauvegarde de chaque réplica de disponibilité en association avec son état opérationnel et son état connecté.</span><span class="sxs-lookup"><span data-stu-id="f8320-120">Note backup jobs might evaluate other factors such as backup priority of each availability replica in combination with its operational state and connected state.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f8320-121">Il n'y a aucune contrainte du paramètre de préférence de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f8320-121">There is no enforcement of the backup-preference setting.</span></span> <span data-ttu-id="f8320-122">La traduction de cette préférence dépend de la logique, le cas échéant, que vous avez écrite dans les travaux de sauvegarde pour les bases de données dans un groupe de disponibilité donné.</span><span class="sxs-lookup"><span data-stu-id="f8320-122">The interpretation of this preference depends on the logic, if any, that you script into back jobs for the databases in a given availability group.</span></span> <span data-ttu-id="f8320-123">Pour plus d’informations, consultez secondaires [actifs : sauvegarde sur les réplicas secondaires (groupes de disponibilité AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="f8320-123">For more information, see [Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
## <a name="replica-backup-priorities"></a><span data-ttu-id="f8320-124">Priorités de sauvegarde de réplica</span><span class="sxs-lookup"><span data-stu-id="f8320-124">Replica backup priorities</span></span>  
 <span data-ttu-id="f8320-125">Cette grille affiche la priorité de sauvegarde actuelle de chaque instance de serveur qui héberge un réplica pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f8320-125">This grid displays the current backup priority of each server instance that hosts a replica for the availability group.</span></span> <span data-ttu-id="f8320-126">Utilisez cette grille pour modifier la priorité de sauvegarde d'un ou plusieurs réplicas de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f8320-126">Use this grid to change the backup priority of one or more availability replicas.</span></span>  
  
 <span data-ttu-id="f8320-127">**Instance de serveur**</span><span class="sxs-lookup"><span data-stu-id="f8320-127">**Server Instance**</span></span>  
 <span data-ttu-id="f8320-128">Nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f8320-128">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span>  
  
 <span data-ttu-id="f8320-129">**Priorité de sauvegarde (Minimale=1, Maximale=100)**</span><span class="sxs-lookup"><span data-stu-id="f8320-129">**Backup Priority (Lowest=1, Highest=100)**</span></span>  
 <span data-ttu-id="f8320-130">Spécifie la priorité d'exécution des sauvegardes sur ce réplica par rapport aux autres réplicas dans le même groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f8320-130">Specifies your priority for performing backups on this replica relative to the other replicas in the same availability group.</span></span> <span data-ttu-id="f8320-131">La valeur est un entier compris entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="f8320-131">The value is an integer in the range of 0..100.</span></span> <span data-ttu-id="f8320-132">1 indique la priorité la plus faible, 100 la priorité la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="f8320-132">1 indicates the lowest priority, and 100 indicates the highest priority.</span></span> <span data-ttu-id="f8320-133">Si **Priorité de sauvegarde** = 1, le réplica de disponibilité est choisi pour l'exécution des sauvegardes uniquement si aucun réplica de disponibilité ayant une priorité plus élevée n'est actuellement disponible.</span><span class="sxs-lookup"><span data-stu-id="f8320-133">If **Backup Priority** = 1, the availability replica would be chosen for performing backups only if no higher priority availability replicas are currently available.</span></span>  
  
 <span data-ttu-id="f8320-134">**Exclure le réplica**</span><span class="sxs-lookup"><span data-stu-id="f8320-134">**Exclude Replica**</span></span>  
 <span data-ttu-id="f8320-135">Sélectionnez cette option si vous ne souhaitez jamais que ce réplica de disponibilité soit choisi pour effectuer des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="f8320-135">Select if you never want this availability replica to be chosen for performing backups.</span></span> <span data-ttu-id="f8320-136">Cela est utile, par exemple, pour un réplica de disponibilité distant sur lequel vous ne souhaitez jamais basculer de sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="f8320-136">This is useful, for example, for a remote availability replica to which you never want backups to fail over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8320-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8320-137">See Also</span></span>  
 <span data-ttu-id="f8320-138">[Secondaires actifs : sauvegarde sur les réplicas secondaires (groupes de disponibilité AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="f8320-138">[Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="f8320-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f8320-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
