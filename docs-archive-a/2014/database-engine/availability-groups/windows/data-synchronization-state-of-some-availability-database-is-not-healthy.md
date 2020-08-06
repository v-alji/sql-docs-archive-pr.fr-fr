---
title: L’état de synchronisation des données d’une base de données de disponibilité n’est pas sain | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 89f95d15-33c6-4768-bccd-9dbf8c4f49a9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 221f25a1ee7e4a8719acc133372c742ca4a79303
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710796"
---
# <a name="data-synchronization-state-of-some-availability-database-is-not-healthy"></a><span data-ttu-id="84df5-102">L'état de synchronisation des données d'une base de données de disponibilité n'est pas sain</span><span class="sxs-lookup"><span data-stu-id="84df5-102">Data synchronization state of some availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="84df5-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="84df5-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84df5-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="84df5-104">**Policy Name**</span></span>|<span data-ttu-id="84df5-105">État de synchronisation des données du réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="84df5-105">Availability Replica Data Synchronization State</span></span>|  
|<span data-ttu-id="84df5-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="84df5-106">**Issue**</span></span>|<span data-ttu-id="84df5-107">L'état de synchronisation des données d'une base de données de disponibilité n'est pas sain.</span><span class="sxs-lookup"><span data-stu-id="84df5-107">Data synchronization state of some availability database is not healthy.</span></span>|  
|<span data-ttu-id="84df5-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="84df5-108">**Category**</span></span>|<span data-ttu-id="84df5-109">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="84df5-109">**Warning**</span></span>|  
|<span data-ttu-id="84df5-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="84df5-110">**Facet**</span></span>|<span data-ttu-id="84df5-111">Réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="84df5-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="84df5-112">Description</span><span class="sxs-lookup"><span data-stu-id="84df5-112">Description</span></span>  
 <span data-ttu-id="84df5-113">Cette stratégie vérifie l'état de synchronisation des données de la base de données de disponibilité (également appelée « réplica de base de données »).</span><span class="sxs-lookup"><span data-stu-id="84df5-113">This policy checks the data synchronization state of the availability database (also known as a "database replica").</span></span> <span data-ttu-id="84df5-114">La stratégie se trouve dans un état non sain lorsque l'état de synchronisation de données est NOT SYNCHRONIZING ou que l'état du réplica de base de données à validation synchrone n'est pas SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="84df5-114">The policy is in an unhealthy state when the data synchronization state is NOT SYNCHRONIZING or the state is not SYNCHRONIZED for the synchronous-commit database replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84df5-115">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], vous trouverez des informations sur les causes et les solutions possibles dans la page [L’état de synchronisation des données d’une base de données de disponibilité n’est pas sain](https://go.microsoft.com/fwlink/p/?LinkId=220863) sur le wiki TechNet.</span><span class="sxs-lookup"><span data-stu-id="84df5-115">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220863) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="84df5-116">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="84df5-116">Possible Causes</span></span>  
 <span data-ttu-id="84df5-117">Au moins une base de données de disponibilité sur le réplica a un état de synchronisation des données non sain.</span><span class="sxs-lookup"><span data-stu-id="84df5-117">At least one availability database on the replica has an unhealthy data synchronization state.</span></span> <span data-ttu-id="84df5-118">S'il s'agit d'un réplica de disponibilité en validation asynchrone, toutes les bases de données de disponibilité doivent être dans l'état SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="84df5-118">If this is an asynchronous-commit availability replica, all availability databases should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="84df5-119">S'il s'agit d'un réplica de disponibilité à validation synchrone, toutes les bases de données de disponibilité doivent être dans l'état SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="84df5-119">If this is a synchronous-commit availability replica, all availability databases should be in the SYNCHRONIZED state.</span></span> <span data-ttu-id="84df5-120">Ce problème peut avoir les causes suivantes :</span><span class="sxs-lookup"><span data-stu-id="84df5-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="84df5-121">Le réplica de disponibilité est peut-être déconnecté.</span><span class="sxs-lookup"><span data-stu-id="84df5-121">The availability replica might be disconnected.</span></span>  
  
-   <span data-ttu-id="84df5-122">Le déplacement des données est peut-être suspendu.</span><span class="sxs-lookup"><span data-stu-id="84df5-122">The data movement might be suspended.</span></span>  
  
-   <span data-ttu-id="84df5-123">La base de données n'est peut-être pas accessible.</span><span class="sxs-lookup"><span data-stu-id="84df5-123">The database might not be accessible.</span></span>  
  
-   <span data-ttu-id="84df5-124">Il peut exister un problème de délai temporaire en raison de la latence réseau ou de la charge sur le réplica principal ou secondaire.</span><span class="sxs-lookup"><span data-stu-id="84df5-124">There might be a temporary delay issue due to network latency or the load on the primary or secondary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="84df5-125">Solution possible</span><span class="sxs-lookup"><span data-stu-id="84df5-125">Possible Solution</span></span>  
 <span data-ttu-id="84df5-126">Résolvez tout problème de connexion ou de suspension du déplacement des données.</span><span class="sxs-lookup"><span data-stu-id="84df5-126">Resolve any connection or data movement suspend issues.</span></span> <span data-ttu-id="84df5-127">Vérifiez les événements liés à ce problème à l'aide de SQL Server Management Studio et recherchez l'erreur de base de données.</span><span class="sxs-lookup"><span data-stu-id="84df5-127">Check the events for this issue using SQL Server Management Studio, and find the database error.</span></span> <span data-ttu-id="84df5-128">Suivez les étapes de résolution spécifiques à cette erreur.</span><span class="sxs-lookup"><span data-stu-id="84df5-128">Follow the troubleshooting steps for the specific error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84df5-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84df5-129">See Also</span></span>  
 <span data-ttu-id="84df5-130">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84df5-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="84df5-131">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="84df5-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
