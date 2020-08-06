---
title: Certains réplicas de disponibilité sont déconnectés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp7allconnected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: aea808be-6f0f-40c2-9aa2-a2a435ec6443
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1bb6535b513770b9b4718a0e8372c0a5bc3cba84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605736"
---
# <a name="some-availability-replicas-are-disconnected"></a><span data-ttu-id="62d6c-102">Certains réplicas de disponibilité sont déconnectés</span><span class="sxs-lookup"><span data-stu-id="62d6c-102">Some availability replicas are disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="62d6c-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="62d6c-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62d6c-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="62d6c-104">**Policy Name**</span></span>|<span data-ttu-id="62d6c-105">État de la connexion des réplicas de disponibilité</span><span class="sxs-lookup"><span data-stu-id="62d6c-105">Availability Replicas Connection State</span></span>|  
|<span data-ttu-id="62d6c-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="62d6c-106">**Issue**</span></span>|<span data-ttu-id="62d6c-107">Certains réplicas de disponibilité sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="62d6c-107">Some availability replicas are disconnected.</span></span>|  
|<span data-ttu-id="62d6c-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="62d6c-108">**Category**</span></span>|<span data-ttu-id="62d6c-109">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="62d6c-109">**Warning**</span></span>|  
|<span data-ttu-id="62d6c-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="62d6c-110">**Facet**</span></span>|<span data-ttu-id="62d6c-111">Groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="62d6c-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="62d6c-112">Description</span><span class="sxs-lookup"><span data-stu-id="62d6c-112">Description</span></span>  
 <span data-ttu-id="62d6c-113">Cette stratégie détermine l'état de la connexion de tous les réplicas de disponibilité et recherche les réplicas de disponibilité dont l'état est DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="62d6c-113">This policy rolls up the connection state of all availability replicas and checks for any availability replicas that are DISCONENCTED.</span></span> <span data-ttu-id="62d6c-114">La stratégie se trouve dans un état non sain lorsque l'état d'un réplica de disponibilité est DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="62d6c-114">The policy is in an unhealthy state when any availability replica is DISCONNECTED.</span></span> <span data-ttu-id="62d6c-115">Autrement, l'état de la stratégie est sain.</span><span class="sxs-lookup"><span data-stu-id="62d6c-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62d6c-116"> Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Certains réplicas de disponibilité sont déconnectés](https://go.microsoft.com/fwlink/p/?LinkId=220855) sur TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="62d6c-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220855) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="62d6c-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="62d6c-117">Possible Causes</span></span>  
 <span data-ttu-id="62d6c-118">Dans ce groupe de disponibilité, au moins un réplica secondaire n'est pas connecté au réplica principal.</span><span class="sxs-lookup"><span data-stu-id="62d6c-118">In this availability group, at least one secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="62d6c-119">L'état de la connexion est DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="62d6c-119">The connected state is DISCONNECTED.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="62d6c-120">Solution possible</span><span class="sxs-lookup"><span data-stu-id="62d6c-120">Possible Solution</span></span>  
 <span data-ttu-id="62d6c-121">Utilisez l'état de la stratégie de réplica de disponibilité pour rechercher le réplica de disponibilité dont l'état est DISCONNECTED, puis résolvez le problème qui affecte le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="62d6c-121">Use the availability replica policy state to find the availability replica that is DISCONNECTED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d6c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62d6c-122">See Also</span></span>  
 <span data-ttu-id="62d6c-123">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="62d6c-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="62d6c-124">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="62d6c-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
