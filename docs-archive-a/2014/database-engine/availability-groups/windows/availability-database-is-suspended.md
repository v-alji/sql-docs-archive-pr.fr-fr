---
title: La base de données de disponibilité est suspendue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp1notsuspended.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6baee70f-848c-4e86-b20d-78875c0f82cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07a547f217367f13df739348325461c862d831f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601127"
---
# <a name="availability-database-is-suspended"></a><span data-ttu-id="07882-102">La base de données de disponibilité est suspendue</span><span class="sxs-lookup"><span data-stu-id="07882-102">Availability database is suspended</span></span>
    
## <a name="introduction"></a><span data-ttu-id="07882-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="07882-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07882-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="07882-104">**Policy Name**</span></span>|<span data-ttu-id="07882-105">État de suspension de la base de données de disponibilité</span><span class="sxs-lookup"><span data-stu-id="07882-105">Availability Database Suspension State</span></span>|  
|<span data-ttu-id="07882-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="07882-106">**Issue**</span></span>|<span data-ttu-id="07882-107">La base de données de disponibilité est suspendue.</span><span class="sxs-lookup"><span data-stu-id="07882-107">Availability database is suspended.</span></span>|  
|<span data-ttu-id="07882-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="07882-108">**Category**</span></span>|<span data-ttu-id="07882-109">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="07882-109">**Warning**</span></span>|  
|<span data-ttu-id="07882-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="07882-110">**Facet**</span></span>|<span data-ttu-id="07882-111">Base de données de disponibilité</span><span class="sxs-lookup"><span data-stu-id="07882-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07882-112">Description</span><span class="sxs-lookup"><span data-stu-id="07882-112">Description</span></span>  
 <span data-ttu-id="07882-113">Cette stratégie vérifie l'état du déplacement des données de la base de données secondaire (également appelée « réplica de base de données secondaire »).</span><span class="sxs-lookup"><span data-stu-id="07882-113">This policy checks the state of data movement of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="07882-114">La stratégie se trouve dans un état non sain lorsque le déplacement des données est suspendu.</span><span class="sxs-lookup"><span data-stu-id="07882-114">The policy is in an unhealthy state when the data movement is suspended.</span></span> <span data-ttu-id="07882-115">Autrement, l'état de la stratégie est sain.</span><span class="sxs-lookup"><span data-stu-id="07882-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07882-116">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [La base de données de disponibilité est suspendue](https://go.microsoft.com/fwlink/p/?LinkId=220860) sur TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="07882-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability database is suspended](https://go.microsoft.com/fwlink/p/?LinkId=220860) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="07882-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="07882-117">Possible Causes</span></span>  
 <span data-ttu-id="07882-118">La synchronisation des données sur cette base de données de disponibilité peut avoir été suspendue pour les motifs suivants :</span><span class="sxs-lookup"><span data-stu-id="07882-118">Data synchronization on this availability database might have been suspended because of the following:</span></span>  
  
-   <span data-ttu-id="07882-119">En raison d'une erreur, le système peut avoir suspendu la synchronisation des données.</span><span class="sxs-lookup"><span data-stu-id="07882-119">Due to an error, the system might have suspended data synchronization.</span></span>  
  
-   <span data-ttu-id="07882-120">L'administrateur de base de données peut avoir suspendu la synchronisation des données à des fins de maintenance.</span><span class="sxs-lookup"><span data-stu-id="07882-120">The database administrator might have suspended data synchronization for maintenance purposes.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="07882-121">Solution possible</span><span class="sxs-lookup"><span data-stu-id="07882-121">Possible Solution</span></span>  
 <span data-ttu-id="07882-122">Relancez la synchronisation des données.</span><span class="sxs-lookup"><span data-stu-id="07882-122">Resume data synchronization.</span></span> <span data-ttu-id="07882-123">Si le problème persiste, vérifiez le groupe de disponibilité dans le journal des événements, puis diagnostiquez la raison de la suspension du déplacement des données par le système.</span><span class="sxs-lookup"><span data-stu-id="07882-123">If the issue persists, check the availability group in the Event log, and then diagnose why the system suspended data movement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07882-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07882-124">See Also</span></span>  
 <span data-ttu-id="07882-125">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="07882-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="07882-126">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="07882-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
