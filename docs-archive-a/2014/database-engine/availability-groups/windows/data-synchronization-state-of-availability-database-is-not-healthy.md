---
title: L’état de synchronisation des données de la base de données de disponibilité n’est pas sain | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 4fd003e7-808e-4b0e-b28a-47d9f2616f06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a179008c20b108a2f6aaefd5dd80b22708e94a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710807"
---
# <a name="data-synchronization-state-of-availability-database-is-not-healthy"></a><span data-ttu-id="6ec98-102">L'état de synchronisation des données de la base de données de disponibilité n'est pas sain</span><span class="sxs-lookup"><span data-stu-id="6ec98-102">Data synchronization state of availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="6ec98-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="6ec98-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6ec98-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="6ec98-104">**Policy Name**</span></span>|<span data-ttu-id="6ec98-105">État de synchronisation des données de la base de données de disponibilité</span><span class="sxs-lookup"><span data-stu-id="6ec98-105">Availability Database Data Synchronization State</span></span>|  
|<span data-ttu-id="6ec98-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="6ec98-106">**Issue**</span></span>|<span data-ttu-id="6ec98-107">L'état de synchronisation des données de la base de données de disponibilité n'est pas sain.</span><span class="sxs-lookup"><span data-stu-id="6ec98-107">Data synchronization state of availability database is not healthy.</span></span>|  
|<span data-ttu-id="6ec98-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="6ec98-108">**Category**</span></span>|<span data-ttu-id="6ec98-109">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="6ec98-109">**Warning**</span></span>|  
|<span data-ttu-id="6ec98-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="6ec98-110">**Facet**</span></span>|<span data-ttu-id="6ec98-111">Base de données de disponibilité</span><span class="sxs-lookup"><span data-stu-id="6ec98-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6ec98-112">Description</span><span class="sxs-lookup"><span data-stu-id="6ec98-112">Description</span></span>  
 <span data-ttu-id="6ec98-113">Cette stratégie regroupe l'état de synchronisation des données de toutes les bases de données de disponibilité (également appelées « réplicas de base de données ») dans le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6ec98-113">This policy rolls up the data synchronization state of all availability databases (also known as "database replicas") in the availability replica.</span></span> <span data-ttu-id="6ec98-114">La stratégie se trouve dans un état non sain lorsqu'un réplica de base de données ne se trouve pas dans l'état de synchronisation des données attendu.</span><span class="sxs-lookup"><span data-stu-id="6ec98-114">The policy is in an unhealthy sate when any database replica is not in the expected data synchronization state.</span></span> <span data-ttu-id="6ec98-115">Autrement, l'état de la stratégie est sain.</span><span class="sxs-lookup"><span data-stu-id="6ec98-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ec98-116">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], vous trouverez des informations sur les causes et les solutions possibles dans la page [L’état de synchronisation des données d’une base de données de disponibilité n’est pas sain](https://go.microsoft.com/fwlink/p/?LinkId=220858) sur le wiki TechNet.</span><span class="sxs-lookup"><span data-stu-id="6ec98-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of some availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220858) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="6ec98-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="6ec98-117">Possible Causes</span></span>  
 <span data-ttu-id="6ec98-118">L'état de synchronisation des données de cette base de données de disponibilité n'est pas sain.</span><span class="sxs-lookup"><span data-stu-id="6ec98-118">The data synchronization state of this availability database is unhealthy.</span></span> <span data-ttu-id="6ec98-119">Sur un réplica de disponibilité en validation asynchrone, chaque base de données de disponibilité doit avoir l'état SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="6ec98-119">On an asynchronous-commit availability replica, every availability database should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="6ec98-120">Sur un réplica à validation synchrone, chaque base de données de disponibilité doit être dans l'état SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="6ec98-120">On a synchronous-commit replica, every availability database must be in the SYNCHRONIZED state.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="6ec98-121">Solution possible</span><span class="sxs-lookup"><span data-stu-id="6ec98-121">Possible Solution</span></span>  
 <span data-ttu-id="6ec98-122">Utilisez la stratégie de réplica de base de données pour rechercher le réplica de base de données affichant un état de synchronisation des données non sain, puis résolvez le problème qui affecte le réplica de base de données.</span><span class="sxs-lookup"><span data-stu-id="6ec98-122">Use the database replica policy to find the database replica with an unhealthy data synchronization state, and then resolve the issue at the database replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec98-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ec98-123">See Also</span></span>  
 <span data-ttu-id="6ec98-124">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6ec98-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="6ec98-125">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6ec98-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
