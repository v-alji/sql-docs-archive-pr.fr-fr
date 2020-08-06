---
title: Certains réplicas de disponibilité ne synchronisent pas de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp4synchronizing.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 3db6a569-e942-4321-a0dd-c4ab002087c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 762b7da1f7b8a07257c2a900307eb1bb10408653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605733"
---
# <a name="some-availability-replicas-are-not-synchronizing-data"></a><span data-ttu-id="0a9fe-102">Certains réplicas de disponibilité ne synchronisent pas de données</span><span class="sxs-lookup"><span data-stu-id="0a9fe-102">Some availability replicas are not synchronizing data</span></span>
    
## <a name="introduction"></a><span data-ttu-id="0a9fe-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="0a9fe-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a9fe-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="0a9fe-104">**Policy Name**</span></span>|<span data-ttu-id="0a9fe-105">État de synchronisation des données des réplicas de disponibilité</span><span class="sxs-lookup"><span data-stu-id="0a9fe-105">Availability Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="0a9fe-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="0a9fe-106">**Issue**</span></span>|<span data-ttu-id="0a9fe-107">Certains réplicas de disponibilité ne synchronisent pas de données.</span><span class="sxs-lookup"><span data-stu-id="0a9fe-107">Some availability replicas are not synchronizing data.</span></span>|  
|<span data-ttu-id="0a9fe-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="0a9fe-108">**Category**</span></span>|<span data-ttu-id="0a9fe-109">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="0a9fe-109">**Warning**</span></span>|  
|<span data-ttu-id="0a9fe-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="0a9fe-110">**Facet**</span></span>|<span data-ttu-id="0a9fe-111">Groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="0a9fe-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0a9fe-112">Description</span><span class="sxs-lookup"><span data-stu-id="0a9fe-112">Description</span></span>  
 <span data-ttu-id="0a9fe-113">Cette stratégie détermine l'état de synchronisation des données de tous les réplicas de disponibilité du groupe de disponibilité et vérifie si la synchronisation d'un réplica de disponibilité n'est pas opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="0a9fe-113">This policy rolls up the data synchronization state of all availability replicas in the availability group and checks if the synchronization of any availability replica is not operational.</span></span> <span data-ttu-id="0a9fe-114">La stratégie se trouve dans un état non sain si l'un des états de synchronisation des données du réplica de disponibilité est NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="0a9fe-114">The policy is in an unhealthy state if any of the data synchronization states of the availability replica is NOT SYNCRONIZING.</span></span>  
  
 <span data-ttu-id="0a9fe-115">Cette stratégie se trouve dans un état sain si aucun des états de synchronisation des données du réplica de disponibilité n'est NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="0a9fe-115">This policy is in a healthy state if none of the data synchronization states of the availability replica is NOT SYNCHRONIZING.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a9fe-116">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Certains réplicas de disponibilité ne synchronisent pas de données](https://go.microsoft.com/fwlink/p/?LinkId=220852) sur TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="0a9fe-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are not synchronizing data](https://go.microsoft.com/fwlink/p/?LinkId=220852) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="0a9fe-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="0a9fe-117">Possible Causes</span></span>  
 <span data-ttu-id="0a9fe-118">Dans ce groupe de disponibilité, au moins un réplica secondaire affiche l'état de synchronisation NOT SYNCHRONIZING et n'accepte pas les données du réplica principal.</span><span class="sxs-lookup"><span data-stu-id="0a9fe-118">In this availability group, at least one secondary replica has a NOT SYNCHRONIZING synchronization state and is not receiving data from the primary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="0a9fe-119">Solution possible</span><span class="sxs-lookup"><span data-stu-id="0a9fe-119">Possible Solution</span></span>  
 <span data-ttu-id="0a9fe-120">Utilisez l'état de la stratégie du réplica de disponibilité pour rechercher le réplica de disponibilité dont l'état est NOT SYNCHRONIZING, puis résolvez le problème affectant le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="0a9fe-120">Use the availability replica policy state to find the availability replica with a NOT SYNCHROINIZING state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9fe-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a9fe-121">See Also</span></span>  
 <span data-ttu-id="0a9fe-122">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a9fe-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="0a9fe-123">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0a9fe-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
