---
title: Le réplica de disponibilité n’a pas un rôle sain | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp1rolehealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: ebb2c9f4-2097-4688-b4fb-8f0571047317
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7be26945903a5e3b602ef4a99c269de6a58b04a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701928"
---
# <a name="availability-replica-does-not-have-a-healthy-role"></a><span data-ttu-id="f89d4-102">Le réplica de disponibilité n'a pas un rôle sain</span><span class="sxs-lookup"><span data-stu-id="f89d4-102">Availability replica does not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="f89d4-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="f89d4-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f89d4-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="f89d4-104">**Policy Name**</span></span>|<span data-ttu-id="f89d4-105">État du rôle du réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f89d4-105">Availability Replica Role State</span></span>|  
|<span data-ttu-id="f89d4-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="f89d4-106">**Issue**</span></span>|<span data-ttu-id="f89d4-107">Le réplica de disponibilité n'a pas un rôle sain.</span><span class="sxs-lookup"><span data-stu-id="f89d4-107">Availability replica does not have a healthy role.</span></span>|  
|<span data-ttu-id="f89d4-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="f89d4-108">**Category**</span></span>|<span data-ttu-id="f89d4-109">**Critical**</span><span class="sxs-lookup"><span data-stu-id="f89d4-109">**Critical**</span></span>|  
|<span data-ttu-id="f89d4-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="f89d4-110">**Facet**</span></span>|<span data-ttu-id="f89d4-111">Réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f89d4-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f89d4-112">Description</span><span class="sxs-lookup"><span data-stu-id="f89d4-112">Description</span></span>  
 <span data-ttu-id="f89d4-113">Cette stratégie vérifie l'état du rôle du réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f89d4-113">This policy checks the state of the role of the availability replica.</span></span> <span data-ttu-id="f89d4-114">La stratégie se trouve dans un état non sain lorsque le rôle du réplica de disponibilité n'est ni principal ni secondaire.</span><span class="sxs-lookup"><span data-stu-id="f89d4-114">The policy is in an unhealthy state when the role of the availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="f89d4-115">Autrement, l'état de la stratégie est sain.</span><span class="sxs-lookup"><span data-stu-id="f89d4-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f89d4-116">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], des informations sur les causes et les solutions possibles se trouvent dans [Le réplica de disponibilité n’a pas un rôle sain](https://go.microsoft.com/fwlink/p/?LinkId=220856) sur Wiki TechNet.</span><span class="sxs-lookup"><span data-stu-id="f89d4-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica does not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220856) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="f89d4-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="f89d4-117">Possible Causes</span></span>  
 <span data-ttu-id="f89d4-118">Le rôle de ce réplica de disponibilité n'est pas sain.</span><span class="sxs-lookup"><span data-stu-id="f89d4-118">The role of this availability replica is unhealthy.</span></span> <span data-ttu-id="f89d4-119">Le réplica n'a pas le rôle principal ou secondaire.</span><span class="sxs-lookup"><span data-stu-id="f89d4-119">The replica does not have either the primary or secondary role.</span></span>  
  
## <a name="possible-solution-information_still_to_come"></a><span data-ttu-id="f89d4-120">Solution possible : Information_à_venir</span><span class="sxs-lookup"><span data-stu-id="f89d4-120">Possible Solution: Information_still_to_come</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89d4-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f89d4-121">See Also</span></span>  
 <span data-ttu-id="f89d4-122">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f89d4-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f89d4-123">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f89d4-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
