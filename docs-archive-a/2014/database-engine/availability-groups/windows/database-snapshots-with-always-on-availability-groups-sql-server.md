---
title: Instantanés de base de données avec groupes de disponibilité AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 7432da1c-ce2f-4cd9-af41-54c97744166b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1e4307653b5b8150d71019a373ee073d15123f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705439"
---
# <a name="database-snapshots-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="4f358-102">Instantanés de base de données avec des groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4f358-102">Database Snapshots with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="4f358-103">Vous pouvez créer un instantané de base de données sur une base de données primaire ou secondaire dans un groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="4f358-103">You can create a database snapshot on an primary or secondary database in an availability group.</span></span> <span data-ttu-id="4f358-104">Le rôle de réplica doit être PRIMARY ou SECONDARY, et non dans l'état RESOLVING.</span><span class="sxs-lookup"><span data-stu-id="4f358-104">The replica role must be either PRIMARY or SECONDARY, not in the RESOLVING state.</span></span>  
  
 <span data-ttu-id="4f358-105">Nous vous recommandons que l'état de synchronisation de base de données soit SYNCHRONIZING ou SYNCHRONIZED lorsque vous créez un instantané de base de données.</span><span class="sxs-lookup"><span data-stu-id="4f358-105">We recommend that the database synchronization state be SYNCHRONIZING or SYNCHRONIZED when you create a database snapshot.</span></span> <span data-ttu-id="4f358-106">Toutefois, les instantanés de base de données peuvent être créés lorsque l'état de synchronisation de base de données est NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="4f358-106">However, database snapshots can be created when the database synchronization state is NOT SYNCHRONIZING.</span></span>  
  
 <span data-ttu-id="4f358-107">Un instantané de base de données sur un réplica secondaire doit continuer de fonctionner si le réplica est déconnecté (état DISCONNECTED) du réplica principal.</span><span class="sxs-lookup"><span data-stu-id="4f358-107">A database snapshot on a secondary replica should continue to work if the replica is DISCONNECTED from the primary replica.</span></span>  
  
 <span data-ttu-id="4f358-108">Certaines conditions [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] provoquent le redémarrage de la base de données source et de ses instantanés de base de données, entraînant la déconnexion temporaire des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4f358-108">Some [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] conditions cause both the source database and its database snapshots to be restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="4f358-109">Ces conditions sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="4f358-109">These conditions are as follows:</span></span>  
  
-   <span data-ttu-id="4f358-110">Le réplica principal modifie des rôles, ce qui peut se produire lorsque le réplica principal actuel est mis hors connexion et qu'il revient en ligne sur la même instance de serveur ou en cas de basculement du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="4f358-110">The primary replica changes roles, whether because the current primary replica goes off line and comes back online on the same server instance or because the availability group fails over.</span></span>  
  
-   <span data-ttu-id="4f358-111">La base de données entre dans le rôle secondaire.</span><span class="sxs-lookup"><span data-stu-id="4f358-111">The database enters the secondary role.</span></span>  
  
 <span data-ttu-id="4f358-112">Si le réplica de disponibilité qui héberge les instantanés de base de données fait l'objet d'un basculement, les instantanés de base de données restent sur l'instance de serveur où ils ont été créés.</span><span class="sxs-lookup"><span data-stu-id="4f358-112">If the availability replica that hosts database snapshots is failed over, the database snapshots remain on the server instance where they were created.</span></span> <span data-ttu-id="4f358-113">Les utilisateurs peuvent continuer à utiliser les instantanés après le basculement. Si les performances constituent un problème dans votre environnement, nous vous recommandons de créer des instantanés de base de données uniquement sur les bases de données secondaires qui sont hébergées par un réplica secondaire configuré en mode de basculement manuel.</span><span class="sxs-lookup"><span data-stu-id="4f358-113">Users can continue to use the snapshots after the failover.If performance is a concern in your environment, we recommend that you create database snapshots only on secondary databases that are hosted by a secondary replica that is configured for manual failover mode.</span></span>  <span data-ttu-id="4f358-114">S'il vous arrive de basculer manuellement le groupe de disponibilité vers ce réplica secondaire, vous pouvez créer un nouvel ensemble d'instantanés de base de données sur un autre réplica secondaire, rediriger les clients vers les nouveaux instantanés de base de données, puis supprimer tous les instantanés de base de données des bases de données désormais primaires.</span><span class="sxs-lookup"><span data-stu-id="4f358-114">If you ever manually fail over the availability group to this secondary replica, you can create a new set of database snapshots on another secondary replica, redirect clients to the new database snapshots, and drop all of the database snapshots from the now primary databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f358-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f358-115">See Also</span></span>  
 <span data-ttu-id="4f358-116">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4f358-116">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="4f358-117">Instantanés de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4f358-117">Database Snapshots &#40;SQL Server&#41;</span></span>](../../../relational-databases/databases/database-snapshots-sql-server.md)  
  
  
