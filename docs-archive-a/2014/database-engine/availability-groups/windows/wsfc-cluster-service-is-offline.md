---
title: Le service de cluster WSFC est hors connexion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp1WSFCquorum.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: d502548d-ece6-4a42-9ded-2157d33e3d21
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6e7b48f96eb09638291b1d0655d385d606b1666
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701904"
---
# <a name="wsfc-cluster-service-is-offline"></a><span data-ttu-id="5eb79-102">Le service de cluster WSFC est hors connexion</span><span class="sxs-lookup"><span data-stu-id="5eb79-102">WSFC cluster service is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="5eb79-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="5eb79-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5eb79-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="5eb79-104">**Policy Name**</span></span>|<span data-ttu-id="5eb79-105">État du cluster WSFC</span><span class="sxs-lookup"><span data-stu-id="5eb79-105">WSFC Cluster State</span></span>|  
|<span data-ttu-id="5eb79-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="5eb79-106">**Issue**</span></span>|<span data-ttu-id="5eb79-107">Le service de cluster WSFC est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="5eb79-107">WSFC cluster service is offline.</span></span>|  
|<span data-ttu-id="5eb79-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="5eb79-108">**Category**</span></span>|<span data-ttu-id="5eb79-109">**Critical**</span><span class="sxs-lookup"><span data-stu-id="5eb79-109">**Critical**</span></span>|  
|<span data-ttu-id="5eb79-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="5eb79-110">**Facet**</span></span>|<span data-ttu-id="5eb79-111">Instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5eb79-111">Instance of SQL Server</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5eb79-112">Description</span><span class="sxs-lookup"><span data-stu-id="5eb79-112">Description</span></span>  
 <span data-ttu-id="5eb79-113">Cette stratégie vérifie l'état du cluster de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="5eb79-113">This policy checks the state of the Windows Server Failover Cluster (WSFC).</span></span> <span data-ttu-id="5eb79-114">La stratégie se trouve dans un état non sain et une alerte est déclenchée lorsque le cluster WSFC est hors connexion ou que son état est Quorum forcé.</span><span class="sxs-lookup"><span data-stu-id="5eb79-114">The policy is in an unhealthy state and an alert is raised when the WSFC cluster is offline or in the forced quorum state.</span></span> <span data-ttu-id="5eb79-115">Tous les groupes de disponibilité hébergés dans ce cluster sont hors connexion ou une action de récupération d'urgence est requise.</span><span class="sxs-lookup"><span data-stu-id="5eb79-115">All availability groups hosted within this cluster are offline or a disaster recovery action is required.</span></span>  
  
 <span data-ttu-id="5eb79-116">L'état de la stratégie est sain lorsque l'état du cluster est Quorum normal.</span><span class="sxs-lookup"><span data-stu-id="5eb79-116">The policy state is healthy when the cluster state is in the normal quorum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5eb79-117">Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Le service de cluster WSFC est hors connexion](https://go.microsoft.com/fwlink/p/?LinkId=220849) sur TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="5eb79-117">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [WSFC cluster service is offline](https://go.microsoft.com/fwlink/p/?LinkId=220849) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="5eb79-118">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="5eb79-118">Possible Causes</span></span>  
 <span data-ttu-id="5eb79-119">Ce problème peut être dû à un problème de service de cluster ou à la perte du quorum dans le cluster.</span><span class="sxs-lookup"><span data-stu-id="5eb79-119">This issue can be caused by a cluster service issue or by the loss of the quorum in the cluster.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="5eb79-120">Solution possible</span><span class="sxs-lookup"><span data-stu-id="5eb79-120">Possible Solution</span></span>  
 <span data-ttu-id="5eb79-121">Utilisez l'outil Administrateur de cluster pour exécuter le quorum forcé ou le flux de travail de récupération d'urgence.</span><span class="sxs-lookup"><span data-stu-id="5eb79-121">Use the Cluster Administrator tool to perform the forced quorum or disaster recovery workflow.</span></span> <span data-ttu-id="5eb79-122">Si vous ne pouvez pas résoudre le problème en exécutant le quorum forcé ou la récupération d'urgence, contactez votre administrateur de cluster pour résoudre ce problème.</span><span class="sxs-lookup"><span data-stu-id="5eb79-122">If you cannot resolve the issue by performing the forced quorum or disaster recovery, contact your cluster administrator to help resolve this issue.</span></span> <span data-ttu-id="5eb79-123">Pour plus d’informations, consultez [Forcer un cluster WSFC à démarrer sans quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5eb79-123">For more information, see [Force a WSFC Cluster to Start Without a Quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb79-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5eb79-124">See Also</span></span>  
 <span data-ttu-id="5eb79-125">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5eb79-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="5eb79-126">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5eb79-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
