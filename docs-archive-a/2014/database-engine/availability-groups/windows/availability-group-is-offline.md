---
title: Le groupe de disponibilité est hors connexion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp2online.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 093c5208-bf7a-49f4-a546-72b48197cadf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b25e5b22a09783c8dfcad862500b5c0dfcb2c319
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601120"
---
# <a name="availability-group-is-offline"></a><span data-ttu-id="d87f7-102">Le groupe de disponibilité est hors connexion</span><span class="sxs-lookup"><span data-stu-id="d87f7-102">Availability group is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="d87f7-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="d87f7-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d87f7-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="d87f7-104">**Policy Name**</span></span>|<span data-ttu-id="d87f7-105">État en ligne du groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="d87f7-105">Availability Group Online State</span></span>|  
|<span data-ttu-id="d87f7-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="d87f7-106">**Issue**</span></span>|<span data-ttu-id="d87f7-107">Le groupe de disponibilité est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="d87f7-107">Availability group is offline.</span></span>|  
|<span data-ttu-id="d87f7-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="d87f7-108">**Category**</span></span>|<span data-ttu-id="d87f7-109">**Critical**</span><span class="sxs-lookup"><span data-stu-id="d87f7-109">**Critical**</span></span>|  
|<span data-ttu-id="d87f7-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="d87f7-110">**Facet**</span></span>|<span data-ttu-id="d87f7-111">Groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="d87f7-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d87f7-112">Description</span><span class="sxs-lookup"><span data-stu-id="d87f7-112">Description</span></span>  
 <span data-ttu-id="d87f7-113">Cette stratégie vérifie l'état (en ligne ou hors connexion) du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="d87f7-113">This policy checks the online or offline state of the availability group.</span></span> <span data-ttu-id="d87f7-114">La stratégie se trouve dans un état non sain et une alerte est générée lorsque la ressource de cluster du groupe de disponibilité est hors connexion ou que le groupe de disponibilité n'a pas de réplica principal.</span><span class="sxs-lookup"><span data-stu-id="d87f7-114">The policy is in an unhealthy state and an alert is raised when the cluster resource of the availability group is offline or the availability group does not have a primary replica.</span></span>  
  
 <span data-ttu-id="d87f7-115">L'état de la stratégie est sain lorsque la ressource de cluster du groupe de disponibilité est en ligne et que le groupe de disponibilité a un réplica principal.</span><span class="sxs-lookup"><span data-stu-id="d87f7-115">The policy state is healthy when the cluster resource of the availability group is online and the availability group has a primary replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d87f7-116"> Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Le groupe de disponibilité est hors connexion](https://go.microsoft.com/fwlink/p/?LinkId=220850) sur TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="d87f7-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is offline](https://go.microsoft.com/fwlink/p/?LinkId=220850) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="d87f7-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="d87f7-117">Possible Causes</span></span>  
 <span data-ttu-id="d87f7-118">Ce problème peut être dû à un échec de l'instance de serveur qui héberge le réplica principal ou à la mise hors connexion de la ressource de groupe de disponibilité du cluster de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="d87f7-118">This issue can be caused by a failure in the server instance that hosts the primary replica or by the Windows Server Failover Cluster (WSFC) availability group resource going offline.</span></span> <span data-ttu-id="d87f7-119">Voici les causes possibles de mise hors connexion du groupe de disponibilité :</span><span class="sxs-lookup"><span data-stu-id="d87f7-119">Following are possible causes for the availability group to be offline:</span></span>  
  
-   <span data-ttu-id="d87f7-120">Le groupe de disponibilité n'est pas configuré avec le mode de basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="d87f7-120">The availability group is not configured with automatic failover mode.</span></span> <span data-ttu-id="d87f7-121">Le réplica principal va bientôt être indisponible et le rôle de tous les réplicas du groupe de disponibilité est RESOLVING.</span><span class="sxs-lookup"><span data-stu-id="d87f7-121">The primary replica becomes unavailable and the role of all replicas in the availability group become RESOLVING.</span></span>  
  
    -   <span data-ttu-id="d87f7-122">Le service de l'instance du réplica principal est arrêté ou ne répond pas.</span><span class="sxs-lookup"><span data-stu-id="d87f7-122">The primary replica instance service is down or unresponsive.</span></span>  
  
    -   <span data-ttu-id="d87f7-123">Le groupe de disponibilité rencontre un problème de connectivité avec le cluster.</span><span class="sxs-lookup"><span data-stu-id="d87f7-123">The availability group has a connectivity issue with the cluster.</span></span>  
  
-   <span data-ttu-id="d87f7-124">Le groupe de disponibilité est configuré avec le mode de basculement automatique et ne se termine pas correctement.</span><span class="sxs-lookup"><span data-stu-id="d87f7-124">The availability group is configured with automatic failover mode and does not complete successfully.</span></span>  
  
    -   <span data-ttu-id="d87f7-125">Pendant le basculement automatique, le contrôle de disponibilité du réplica principal sur le réplica cible échoue, et aucun réplica n'est disponible pour devenir le nouveau réplica principal.</span><span class="sxs-lookup"><span data-stu-id="d87f7-125">During the automatic failover, the primary readiness check on the target replica fails, and there is no replica available to become the new primary.</span></span>  
  
-   <span data-ttu-id="d87f7-126">La ressource du groupe de disponibilité dans le cluster est en train de passer hors connexion.</span><span class="sxs-lookup"><span data-stu-id="d87f7-126">The availability group resource in the cluster becomes offline.</span></span>  
  
    -   <span data-ttu-id="d87f7-127">Une ressource de cluster dépendante rencontre un problème critique et est en train de passer hors connexion.</span><span class="sxs-lookup"><span data-stu-id="d87f7-127">Any dependent cluster resource encounters a critical issue and becomes offline.</span></span> <span data-ttu-id="d87f7-128">La ressource du groupe de disponibilité reste également hors connexion jusqu'à ce que la ressource dépendante soit en ligne.</span><span class="sxs-lookup"><span data-stu-id="d87f7-128">The availability group resource is also offline until the dependent resource becomes online.</span></span>  
  
    -   <span data-ttu-id="d87f7-129">Un problème critique au niveau du cluster désactive la ressource du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="d87f7-129">A critical issue in the cluster turns off the availability group resource.</span></span>  
  
-   <span data-ttu-id="d87f7-130">Un basculement automatique, manuel ou forcé est en cours pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="d87f7-130">There is an automatic, manual, or forced failover in progress for the availability group.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="d87f7-131">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="d87f7-131">Possible Solutions</span></span>  
 <span data-ttu-id="d87f7-132">Voici les solutions possibles à ce problème :</span><span class="sxs-lookup"><span data-stu-id="d87f7-132">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="d87f7-133">Si l'instance SQL Server du réplica principal est arrêtée, redémarrez le serveur, puis vérifiez que le groupe de disponibilité repasse à un état sain.</span><span class="sxs-lookup"><span data-stu-id="d87f7-133">If the SQL Server instance of the primary replica is down, restart the server and then verify that the availability group recovers to a healthy state.</span></span>  
  
-   <span data-ttu-id="d87f7-134">Si le basculement automatique a échoué, vérifiez que les bases de données du réplica sont synchronisées avec le réplica principal précédemment connu, puis basculez vers le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="d87f7-134">If the automatic failover appears to have failed, verify that the databases on the replica are synchronized with the previously known primary replica, and then failover to the primary replica.</span></span> <span data-ttu-id="d87f7-135">Si les bases de données ne sont pas synchronisées, sélectionnez un réplica avec une perte minimale de données, puis repassez en mode de basculement.</span><span class="sxs-lookup"><span data-stu-id="d87f7-135">If the databases are not synchronized, select a replica with a minimum loss of data, and then recover to failover mode.</span></span>  
  
-   <span data-ttu-id="d87f7-136">Si la ressource du cluster est hors connexion alors que les instances SQL Server semblent être saines, utilisez le Gestionnaire du cluster de basculement pour vérifier l'intégrité de cluster ou détecter d'autres problèmes de cluster sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="d87f7-136">If the resource in the cluster is offline while the instances of SQL Server appear to be healthy, use Failover Cluster Manager to check the cluster health or other cluster issues on the server.</span></span> <span data-ttu-id="d87f7-137">Vous pouvez également utiliser le Gestionnaire du cluster de basculement pour tenter de remettre en ligne la ressource du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="d87f7-137">You can also use the Failover Cluster Manager to attempt to turn the availability group resource online.</span></span>  
  
-   <span data-ttu-id="d87f7-138">Si un basculement est en cours, attendez qu'il soit achevé.</span><span class="sxs-lookup"><span data-stu-id="d87f7-138">If there is a failover in progress, wait for the failover to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d87f7-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d87f7-139">See Also</span></span>  
 <span data-ttu-id="d87f7-140">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d87f7-140">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="d87f7-141">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d87f7-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
