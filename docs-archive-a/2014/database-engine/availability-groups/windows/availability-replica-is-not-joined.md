---
title: Le réplica de disponibilité n’est pas joint | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp4joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 9c0d10b1-9e12-430c-83b9-ca2bd0a3afc4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7c4f76e98d373e50124f5ca2b135a9fad8f34226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701916"
---
# <a name="availability-replica-is-not-joined"></a><span data-ttu-id="f877a-102">Le réplica de disponibilité n'est pas joint</span><span class="sxs-lookup"><span data-stu-id="f877a-102">Availability replica is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="f877a-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="f877a-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f877a-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="f877a-104">**Policy Name**</span></span>|<span data-ttu-id="f877a-105">État de jointure du réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f877a-105">Availability Replica Join State</span></span>|  
|<span data-ttu-id="f877a-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="f877a-106">**Issue**</span></span>|<span data-ttu-id="f877a-107">Le réplica de disponibilité n'est pas joint.</span><span class="sxs-lookup"><span data-stu-id="f877a-107">Availability Replica is not joined.</span></span>|  
|<span data-ttu-id="f877a-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="f877a-108">**Category**</span></span>|<span data-ttu-id="f877a-109">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="f877a-109">**Warning**</span></span>|  
|<span data-ttu-id="f877a-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="f877a-110">**Facet**</span></span>|<span data-ttu-id="f877a-111">Réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f877a-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f877a-112">Description</span><span class="sxs-lookup"><span data-stu-id="f877a-112">Description</span></span>  
 <span data-ttu-id="f877a-113">Cette stratégie vérifie l'état de jointure du réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f877a-113">This policy checks the join state of the availability replica.</span></span> <span data-ttu-id="f877a-114">La stratégie se trouve dans un état défectueux lorsque le réplica de disponibilité est ajouté au groupe de disponibilité, mais n'est pas joint correctement.</span><span class="sxs-lookup"><span data-stu-id="f877a-114">The policy is in an unhealthy state when the availability replica is added to the availability group, but is not joined properly.</span></span> <span data-ttu-id="f877a-115">Autrement, l'état de la stratégie est sain.</span><span class="sxs-lookup"><span data-stu-id="f877a-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f877a-116">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Le réplica de disponibilité n’est pas joint](https://go.microsoft.com/fwlink/p/?LinkId=220859) sur TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="f877a-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220859) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="f877a-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="f877a-117">Possible Causes</span></span>  
 <span data-ttu-id="f877a-118">Le réplica secondaire n'est pas joint au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f877a-118">The secondary replica is not joined to the availability group.</span></span> <span data-ttu-id="f877a-119">Pour qu'un réplica de disponibilité soit correctement joint au groupe de disponibilité, l'état de jointure doit être une instance autonome jointe (1) ou un cluster de basculement joint (2).</span><span class="sxs-lookup"><span data-stu-id="f877a-119">For an availability replica to be successfully joined to the availability group, the join state must be Joined Standalone Instance (1) or Joined Failover Cluster (2).</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="f877a-120">Solution possible</span><span class="sxs-lookup"><span data-stu-id="f877a-120">Possible Solution</span></span>  
 <span data-ttu-id="f877a-121">Utilisez Transact-SQL, PowerShell ou SQL Server Management Studio pour joindre le réplica secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f877a-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="f877a-122">Pour plus d’informations sur la jointure des réplicas secondaires aux groupes de disponibilité, consultez [Jointure d’un réplica secondaire à un groupe de disponibilité (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="f877a-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f877a-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f877a-123">See Also</span></span>  
 <span data-ttu-id="f877a-124">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f877a-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f877a-125">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f877a-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
