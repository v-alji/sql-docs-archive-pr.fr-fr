---
title: La base de données secondaire n’est pas attachée | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp2joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 10817e5e-75fa-42dd-baa2-359bea3ad051
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81275e85fd865924778f6d6f985e170a5bda9f9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707891"
---
# <a name="secondary-database-is-not-joined"></a><span data-ttu-id="fe1ea-102">La base de données secondaire n'est pas attachée</span><span class="sxs-lookup"><span data-stu-id="fe1ea-102">Secondary database is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="fe1ea-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="fe1ea-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe1ea-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="fe1ea-104">**Policy Name**</span></span>|<span data-ttu-id="fe1ea-105">État de la jointure de la base de données de disponibilité</span><span class="sxs-lookup"><span data-stu-id="fe1ea-105">Availability Database Join State</span></span>|  
|<span data-ttu-id="fe1ea-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="fe1ea-106">**Issue**</span></span>|<span data-ttu-id="fe1ea-107">La base de données secondaire n'est pas jointe.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-107">Secondary database is not joined.</span></span>|  
|<span data-ttu-id="fe1ea-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="fe1ea-108">**Category**</span></span>|<span data-ttu-id="fe1ea-109">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="fe1ea-109">**Warning**</span></span>|  
|<span data-ttu-id="fe1ea-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="fe1ea-110">**Facet**</span></span>|<span data-ttu-id="fe1ea-111">Base de données de disponibilité</span><span class="sxs-lookup"><span data-stu-id="fe1ea-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe1ea-112">Description</span><span class="sxs-lookup"><span data-stu-id="fe1ea-112">Description</span></span>  
 <span data-ttu-id="fe1ea-113">Cette stratégie vérifie l'état de jointure de la base de données secondaire (également appelée « réplica de base de données secondaire »).</span><span class="sxs-lookup"><span data-stu-id="fe1ea-113">This policy checks the join state of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="fe1ea-114">La stratégie se trouve dans un état non sain lorsque le réplica de dataset n'est pas joint.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-114">The policy is in an unhealthy state when the dataset replica is not joined.</span></span> <span data-ttu-id="fe1ea-115">Autrement, l'état de la stratégie est sain.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe1ea-116">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [La base de données secondaire n’est pas jointe](https://go.microsoft.com/fwlink/p/?LinkId=220862) sur le Wiki TechNet.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Secondary database is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220862) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="fe1ea-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="fe1ea-117">Possible Causes</span></span>  
 <span data-ttu-id="fe1ea-118">Cette base de données secondaire n'est pas jointe au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-118">This secondary database is not joined to the availability group.</span></span> <span data-ttu-id="fe1ea-119">La configuration de cette base de données secondaire est incomplète.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-119">The configuration of this secondary database is incomplete.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="fe1ea-120">Solution possible</span><span class="sxs-lookup"><span data-stu-id="fe1ea-120">Possible Solution</span></span>  
 <span data-ttu-id="fe1ea-121">Utilisez Transact-SQL, PowerShell ou SQL Server Management Studio pour joindre le réplica secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="fe1ea-122">Pour plus d’informations sur la jointure des réplicas secondaires aux groupes de disponibilité, consultez [Jointure d’un réplica secondaire à un groupe de disponibilité (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="fe1ea-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe1ea-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe1ea-123">See Also</span></span>  
 <span data-ttu-id="fe1ea-124">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe1ea-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="fe1ea-125">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="fe1ea-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
