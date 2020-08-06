---
title: Le groupe de disponibilité n’est pas prêt pour le basculement automatique | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp3autofailover.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 28261014-342c-442a-bd89-6d04b8d4e8b7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2995ddec51cd70d8a3f209229d0ecb9b0132c79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601123"
---
# <a name="availability-group-is-not-ready-for-automatic-failover"></a><span data-ttu-id="414ef-102">Le groupe de disponibilité n'est pas prêt pour le basculement automatique</span><span class="sxs-lookup"><span data-stu-id="414ef-102">Availability group is not ready for automatic failover</span></span>
    
## <a name="introduction"></a><span data-ttu-id="414ef-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="414ef-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="414ef-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="414ef-104">**Policy Name**</span></span>|<span data-ttu-id="414ef-105">Disponibilité du groupe de disponibilité pour le basculement automatique</span><span class="sxs-lookup"><span data-stu-id="414ef-105">Availability Group Automatic Failover Readiness</span></span>|  
|<span data-ttu-id="414ef-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="414ef-106">**Issue**</span></span>|<span data-ttu-id="414ef-107">Le groupe de disponibilité n'est pas prêt pour le basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="414ef-107">Availability group is not ready for automatic failover.</span></span>|  
|<span data-ttu-id="414ef-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="414ef-108">**Category**</span></span>|<span data-ttu-id="414ef-109">**Critical**</span><span class="sxs-lookup"><span data-stu-id="414ef-109">**Critical**</span></span>|  
|<span data-ttu-id="414ef-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="414ef-110">**Facet**</span></span>|<span data-ttu-id="414ef-111">Groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="414ef-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="414ef-112">Description</span><span class="sxs-lookup"><span data-stu-id="414ef-112">Description</span></span>  
 <span data-ttu-id="414ef-113">Cette stratégie vérifie que le groupe de disponibilité a au moins un réplica secondaire prêt pour le basculement.</span><span class="sxs-lookup"><span data-stu-id="414ef-113">This policy checks to verify that the availability group has at least one secondary replica that is failover ready.</span></span> <span data-ttu-id="414ef-114">La stratégie se trouve dans un état non sain et une alerte est déclenchée lorsque le mode de basculement du réplica principal est automatique, mais qu'aucun des réplicas secondaires dans le groupe de disponibilité n'est prêt pour le basculement.</span><span class="sxs-lookup"><span data-stu-id="414ef-114">The policy is in an unhealthy state and an alert is raised when the failover mode of the primary replica is automatic, however none of the secondary replicas in the availability group are failover ready.</span></span>  
  
 <span data-ttu-id="414ef-115">La stratégie se trouve dans un état sain lorsqu'au moins un réplica secondaire est prêt pour le basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="414ef-115">The policy is in a healthy state when at least one secondary replica is automatic failover ready.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="414ef-116"> Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Le groupe de disponibilité n'est pas prêt pour le basculement automatique](https://go.microsoft.com/fwlink/p/?LinkId=220851) sur TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="414ef-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is not ready for automatic failover](https://go.microsoft.com/fwlink/p/?LinkId=220851) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="414ef-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="414ef-117">Possible Causes</span></span>  
 <span data-ttu-id="414ef-118">Le groupe de disponibilité n'est pas prêt pour le basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="414ef-118">The availability group is not ready for automatic failover.</span></span> <span data-ttu-id="414ef-119">Le réplica principal est configuré pour le basculement automatique ; toutefois, le réplica secondaire n'est pas prêt pour le basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="414ef-119">The primary replica is configured for automatic failover; however, the secondary replica is not ready for automatic failover.</span></span> <span data-ttu-id="414ef-120">Le réplica secondaire configuré pour le basculement automatique est peut-être indisponible ou son état de synchronisation des données n'est pas SYNCHRONIZED pour le moment.</span><span class="sxs-lookup"><span data-stu-id="414ef-120">The secondary replica that is configured for automatic failover might be unavailable or its data synchronization state is currently not SYNCHRONIZED.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="414ef-121">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="414ef-121">Possible Solutions</span></span>  
 <span data-ttu-id="414ef-122">Voici les solutions possibles à ce problème :</span><span class="sxs-lookup"><span data-stu-id="414ef-122">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="414ef-123">Vérifiez qu'au moins un réplica secondaire est configuré pour le basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="414ef-123">Verify that at least one secondary replica is configured as automatic failover.</span></span> <span data-ttu-id="414ef-124">Si aucun réplica secondaire n'est configuré pour le basculement automatique, mettez à jour la configuration d'un réplica secondaire de sorte qu'il soit la cible de basculement automatique avec validation synchrone.</span><span class="sxs-lookup"><span data-stu-id="414ef-124">If there is not a secondary replica configured as automatic failover, update the configuration of a secondary replica to be the automatic failover target with synchronous commit.</span></span>  
  
-   <span data-ttu-id="414ef-125">Utilisez la stratégie pour vérifier que les données sont dans un état de synchronisation et que la cible de basculement automatique est à l'état SYNCHRONIZED, puis pour résoudre le problème qui affecte le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="414ef-125">Use the policy to verify that the data is in a synchronization state and the automatic failover target is SYNCHRONIZED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="414ef-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="414ef-126">See Also</span></span>  
 <span data-ttu-id="414ef-127">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="414ef-127">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="414ef-128">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="414ef-128">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
