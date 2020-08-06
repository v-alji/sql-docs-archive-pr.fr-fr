---
title: Certains réplicas synchrones ne sont pas synchronisés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp5synchronized.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: e58ed56e-4c30-42e6-a9fc-a8c401620e02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecef2d16e80e128834a71e1f1f112096f8ccc9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605727"
---
# <a name="some-synchronous-replicas-are-not-synchronized"></a><span data-ttu-id="6b5ea-102">Certains réplicas synchrones ne sont pas synchronisés</span><span class="sxs-lookup"><span data-stu-id="6b5ea-102">Some synchronous replicas are not synchronized</span></span>
    
## <a name="introduction"></a><span data-ttu-id="6b5ea-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="6b5ea-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6b5ea-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="6b5ea-104">**Policy Name**</span></span>|<span data-ttu-id="6b5ea-105">État de synchronisation des données de réplicas synchrones</span><span class="sxs-lookup"><span data-stu-id="6b5ea-105">Synchronous Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="6b5ea-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="6b5ea-106">**Issue**</span></span>|<span data-ttu-id="6b5ea-107">Certains réplicas synchrones ne sont pas synchronisés.</span><span class="sxs-lookup"><span data-stu-id="6b5ea-107">Some synchronous replicas are not synchronized.</span></span>|  
|<span data-ttu-id="6b5ea-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="6b5ea-108">**Category**</span></span>|<span data-ttu-id="6b5ea-109">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="6b5ea-109">**Warning**</span></span>|  
|<span data-ttu-id="6b5ea-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="6b5ea-110">**Facet**</span></span>|<span data-ttu-id="6b5ea-111">Groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="6b5ea-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6b5ea-112">Description</span><span class="sxs-lookup"><span data-stu-id="6b5ea-112">Description</span></span>  
 <span data-ttu-id="6b5ea-113">Cette stratégie détermine l'état de synchronisation des données de tous les réplicas de disponibilité et recherche les réplicas de disponibilité qui ne sont pas dans l'état de synchronisation escompté.</span><span class="sxs-lookup"><span data-stu-id="6b5ea-113">This policy rolls up the data synchronization state of all availability replicas and checks for any availability replicas that are not in the expected synchronization state.</span></span> <span data-ttu-id="6b5ea-114">La stratégie se trouve dans un état non sain lorsqu'aucun réplica asynchrone n'est dans un état SYNCHRONIZING et qu'un réplica synchrone n'est dans un état SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="6b5ea-114">The policy is in an unhealthy state when any asynchronous replica is not in a SYNCHRONIZING state and any synchronous replica is not in a SYNCHRONIZED state.</span></span> <span data-ttu-id="6b5ea-115">Sinon, l'état de la stratégie est sain.</span><span class="sxs-lookup"><span data-stu-id="6b5ea-115">The policy state is otherwise healthy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b5ea-116">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Certains réplicas synchrones ne sont pas synchronisés](https://go.microsoft.com/fwlink/p/?LinkId=220853) sur Wiki TechNet.</span><span class="sxs-lookup"><span data-stu-id="6b5ea-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some synchronous replicas are not synchronized](https://go.microsoft.com/fwlink/p/?LinkId=220853) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="6b5ea-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="6b5ea-117">Possible Causes</span></span>  
 <span data-ttu-id="6b5ea-118">Dans ce groupe de disponibilité, au moins un réplica synchrone n'est pas synchronisé actuellement.</span><span class="sxs-lookup"><span data-stu-id="6b5ea-118">In this availability group, at least one synchronous replica is not currently synchronized.</span></span> <span data-ttu-id="6b5ea-119">L'état de synchronisation du réplica peut être SYNCHRONIZING ou NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="6b5ea-119">The replica synchronization state could be either SYNCHONIZING or NOT SYNCHRONIZING.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="6b5ea-120">Solution possible</span><span class="sxs-lookup"><span data-stu-id="6b5ea-120">Possible Solution</span></span>  
 <span data-ttu-id="6b5ea-121">Utilisez l'état de la stratégie de réplica de disponibilité pour rechercher le réplica de disponibilité dont l'état de synchronisation est incorrect, puis résolvez le problème qui affecte le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6b5ea-121">Use the availability replica policy state to find the availability replica with the incorrect synchronization state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5ea-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b5ea-122">See Also</span></span>  
 <span data-ttu-id="6b5ea-123">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6b5ea-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="6b5ea-124">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6b5ea-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
