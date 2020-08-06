---
title: Le réplica de disponibilité est déconnecté | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp2connected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 1a2162d3-54fb-4356-b349-effbdc15a5a4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1db92b8e73b6daaee7edf5042b1d73cfeb471d1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701921"
---
# <a name="availability-replica-is-disconnected"></a><span data-ttu-id="17413-102">Le réplica de disponibilité est déconnecté</span><span class="sxs-lookup"><span data-stu-id="17413-102">Availability replica is disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="17413-103">Introduction</span><span class="sxs-lookup"><span data-stu-id="17413-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17413-104">**Nom de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="17413-104">**Policy Name**</span></span>|<span data-ttu-id="17413-105">État de la connexion du réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="17413-105">Availability Replica Connection State</span></span>|  
|<span data-ttu-id="17413-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="17413-106">**Issue**</span></span>|<span data-ttu-id="17413-107">Le réplica de disponibilité est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="17413-107">Availability replica is disconnected.</span></span>|  
|<span data-ttu-id="17413-108">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="17413-108">**Category**</span></span>|<span data-ttu-id="17413-109">**Critical**</span><span class="sxs-lookup"><span data-stu-id="17413-109">**Critical**</span></span>|  
|<span data-ttu-id="17413-110">**Facette**</span><span class="sxs-lookup"><span data-stu-id="17413-110">**Facet**</span></span>|<span data-ttu-id="17413-111">Réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="17413-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="17413-112">Description</span><span class="sxs-lookup"><span data-stu-id="17413-112">Description</span></span>  
 <span data-ttu-id="17413-113">Cette stratégie vérifie l'état de la connexion entre les réplicas de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="17413-113">This policy checks the connection state between availability replicas.</span></span> <span data-ttu-id="17413-114">La stratégie se trouve dans un état non sain lorsque l'état de la connexion du réplica de disponibilité est DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="17413-114">The policy is in an unhealthy state when the connection state of the availability replica is DISCONNECTED.</span></span> <span data-ttu-id="17413-115">Autrement, l'état de la stratégie est sain.</span><span class="sxs-lookup"><span data-stu-id="17413-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17413-116"> Pour cette version de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], les informations sur les causes et les solutions possibles sont situées sous [Le réplica de disponibilité est déconnecté](https://go.microsoft.com/fwlink/p/?LinkId=220857) sur TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="17413-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220857) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="17413-117">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="17413-117">Possible Causes</span></span>  
 <span data-ttu-id="17413-118">Le réplica secondaire n'est pas connecté au réplica principal.</span><span class="sxs-lookup"><span data-stu-id="17413-118">The secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="17413-119">L'état de la connexion est DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="17413-119">The connected state is DISCONNECTED.</span></span> <span data-ttu-id="17413-120">Ce problème peut avoir les causes suivantes :</span><span class="sxs-lookup"><span data-stu-id="17413-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="17413-121">Le port de connexion est peut-être en conflit avec une autre application.</span><span class="sxs-lookup"><span data-stu-id="17413-121">The connection port might be in conflict with another application.</span></span>  
  
-   <span data-ttu-id="17413-122">Le type ou l'algorithme de chiffrement est incompatible.</span><span class="sxs-lookup"><span data-stu-id="17413-122">The encryption type or algorithm is mismatched.</span></span>  
  
-   <span data-ttu-id="17413-123">Le point de terminaison de connexion a été supprimé ou n'a pas été démarré.</span><span class="sxs-lookup"><span data-stu-id="17413-123">The connection endpoint has been deleted or has not been started.</span></span>  
  
-   <span data-ttu-id="17413-124">Le transport est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="17413-124">The transport is disconnected.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="17413-125">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="17413-125">Possible Solutions</span></span>  
 <span data-ttu-id="17413-126">Voici les solutions possibles à ce problème :</span><span class="sxs-lookup"><span data-stu-id="17413-126">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="17413-127">Vérifiez la configuration du point de terminaison de mise en miroir de bases de données pour les instances du réplica principal et secondaire et mettez à jour la configuration incompatible.</span><span class="sxs-lookup"><span data-stu-id="17413-127">Check the database mirroring endpoint configuration for the instances of the primary and secondary replica and update the mismatched configuration.</span></span>  
  
-   <span data-ttu-id="17413-128">Vérifiez si le port est en conflit et, le cas échéant, modifiez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="17413-128">Check if the port is conflicting, and if so, change the port number.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17413-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17413-129">See Also</span></span>  
 <span data-ttu-id="17413-130">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="17413-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="17413-131">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="17413-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
