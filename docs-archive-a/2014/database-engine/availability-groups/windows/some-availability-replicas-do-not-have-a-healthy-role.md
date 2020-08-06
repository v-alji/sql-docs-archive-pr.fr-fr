---
title: Certains réplicas de disponibilité n’ont pas un rôle sain | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp6allroleshealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 7ec5b337-7201-4a66-a541-7560f8b18784
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 801fe20edf6f2dbe09bc800722cf4210988ebc69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605732"
---
# <a name="some-availability-replicas-do-not-have-a-healthy-role"></a><span data-ttu-id="b277e-102">Certains réplicas de disponibilité n'ont pas un rôle sain</span><span class="sxs-lookup"><span data-stu-id="b277e-102">Some availability replicas do not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="b277e-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="b277e-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b277e-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="b277e-104">**Policy Name**</span></span>|<span data-ttu-id="b277e-105">État du rôle des réplicas de disponibilité</span><span class="sxs-lookup"><span data-stu-id="b277e-105">Availability Replicas Role State</span></span>|  
|<span data-ttu-id="b277e-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="b277e-106">**Issue**</span></span>|<span data-ttu-id="b277e-107">Certains réplicas de disponibilité n'ont pas un rôle sain.</span><span class="sxs-lookup"><span data-stu-id="b277e-107">Some availability replicas do not have a healthy role.</span></span>|  
|<span data-ttu-id="b277e-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="b277e-108">**Category**</span></span>|<span data-ttu-id="b277e-109">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="b277e-109">**Warning**</span></span>|  
|<span data-ttu-id="b277e-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="b277e-110">**Facet**</span></span>|<span data-ttu-id="b277e-111">Groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="b277e-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b277e-112">Description</span><span class="sxs-lookup"><span data-stu-id="b277e-112">Description</span></span>  
 <span data-ttu-id="b277e-113">Cette stratégie détermine l'état de connexion de tous les réplicas de disponibilité et vérifie s'il existe des réplicas de disponibilité qui n'ont pas un rôle sain.</span><span class="sxs-lookup"><span data-stu-id="b277e-113">This policy rolls up the connection state of all availability replicas and checks if there are any availability replicas that are not in a healthy role.</span></span> <span data-ttu-id="b277e-114">La stratégie se trouve dans un état non sain lorsqu'un réplica de disponibilité n'est ni principal ni secondaire.</span><span class="sxs-lookup"><span data-stu-id="b277e-114">The policy is in an unhealthy state when any availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="b277e-115">Autrement, l'état de la stratégie est sain.</span><span class="sxs-lookup"><span data-stu-id="b277e-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b277e-116">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Certains réplicas de disponibilité n’ont pas un rôle sain](https://go.microsoft.com/fwlink/p/?LinkId=220854) sur TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="b277e-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas do not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220854) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="b277e-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="b277e-117">Possible Causes</span></span>  
 <span data-ttu-id="b277e-118">Dans ce groupe de disponibilité, au moins un réplica de disponibilité n'a pas de rôle principal ou secondaire pour le moment.</span><span class="sxs-lookup"><span data-stu-id="b277e-118">In this availability group, at least one availability replica does not currently have the primary or secondary role.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="b277e-119">Solution possible</span><span class="sxs-lookup"><span data-stu-id="b277e-119">Possible Solution</span></span>  
 <span data-ttu-id="b277e-120">Utilisez l'état de la stratégie de réplica de disponibilité pour rechercher le réplica de disponibilité dont le rôle n'est ni principal ni secondaire, puis résolvez le problème qui affecte le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="b277e-120">Use the availability replica policy state to find the availability replica whose role is not primary or secondary, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b277e-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b277e-121">See Also</span></span>  
 <span data-ttu-id="b277e-122">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b277e-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="b277e-123">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b277e-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
