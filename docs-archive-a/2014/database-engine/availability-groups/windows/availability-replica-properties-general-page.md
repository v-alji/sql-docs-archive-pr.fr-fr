---
title: Propriétés du réplica de disponibilité (page Général) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilityreplicaproperties.general.f1
ms.assetid: 8318fefb-e045-4fab-8507-e1951fc7cec6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 313314baf009cdfb6109e63e9b65e369ac314f60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708687"
---
# <a name="availability-replica-properties-general-page"></a><span data-ttu-id="5c319-102">Propriétés du réplica de disponibilité (page Général)</span><span class="sxs-lookup"><span data-stu-id="5c319-102">Availability Replica Properties (General Page)</span></span>
  <span data-ttu-id="5c319-103">Utilisez cette boîte de dialogue pour afficher les propriétés d’un réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="5c319-103">Use this dialog box to viewthe properties of an availability replica.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="5c319-104">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="5c319-104">Task List</span></span>  
 <span data-ttu-id="5c319-105">**Pour afficher les propriétés d'un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="5c319-105">**To view availability replica properties**</span></span>  
  
-   [<span data-ttu-id="5c319-106">Afficher les propriétés d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c319-106">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="5c319-107">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5c319-107">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="5c319-108">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="5c319-108">UI element list</span></span>  
 <span data-ttu-id="5c319-109">**Nom du groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="5c319-109">**Availability group name**</span></span>  
 <span data-ttu-id="5c319-110">Nom du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="5c319-110">Name of the availability group.</span></span> <span data-ttu-id="5c319-111">Il s'agit d'un nom spécifié par l'utilisateur qui doit être unique dans le cluster de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="5c319-111">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
 <span data-ttu-id="5c319-112">**Instance de serveur**</span><span class="sxs-lookup"><span data-stu-id="5c319-112">**Server instance**</span></span>  
 <span data-ttu-id="5c319-113">Nom de serveur de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge ce réplica et, pour une instance non définie par défaut, son nom d'instance.</span><span class="sxs-lookup"><span data-stu-id="5c319-113">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="5c319-114">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="5c319-114">**Role**</span></span>  
 <span data-ttu-id="5c319-115">**Primaire**</span><span class="sxs-lookup"><span data-stu-id="5c319-115">**Primary**</span></span>  
 <span data-ttu-id="5c319-116">Actuellement le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="5c319-116">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="5c319-117">**Secondaire**</span><span class="sxs-lookup"><span data-stu-id="5c319-117">**Secondary**</span></span>  
 <span data-ttu-id="5c319-118">Actuellement un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="5c319-118">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="5c319-119">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="5c319-119">**Resolving**</span></span>  
 <span data-ttu-id="5c319-120">Actuellement le rôle de réplica est en cours d'être résolu en rôle principal ou secondaire.</span><span class="sxs-lookup"><span data-stu-id="5c319-120">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="5c319-121">**Mode de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="5c319-121">**Availability mode**</span></span>  
 <span data-ttu-id="5c319-122">Mode de disponibilité du réplica, parmi :</span><span class="sxs-lookup"><span data-stu-id="5c319-122">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="5c319-123">**Validation asynchrone**</span><span class="sxs-lookup"><span data-stu-id="5c319-123">**Asynchronous commit**</span></span>  
 <span data-ttu-id="5c319-124">Le réplica principal peut valider des transactions sans attendre que le réplica secondaire écrive le journal sur le disque.</span><span class="sxs-lookup"><span data-stu-id="5c319-124">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="5c319-125">**Validation synchrone**</span><span class="sxs-lookup"><span data-stu-id="5c319-125">**Synchronous commit**</span></span>  
 <span data-ttu-id="5c319-126">Le réplica principal attend pour valider une transaction donnée que le réplica secondaire ait écrit la transaction sur le disque.</span><span class="sxs-lookup"><span data-stu-id="5c319-126">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="5c319-127">Pour plus d’informations, consultez [modes de disponibilité (groupes de disponibilité AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5c319-127">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="5c319-128">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="5c319-128">**Failover mode**</span></span>  
 <span data-ttu-id="5c319-129">Mode de basculement du réplica, parmi :</span><span class="sxs-lookup"><span data-stu-id="5c319-129">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="5c319-130">**Automatique**</span><span class="sxs-lookup"><span data-stu-id="5c319-130">**Automatic**</span></span>  
 <span data-ttu-id="5c319-131">Basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="5c319-131">Automatic failover.</span></span> <span data-ttu-id="5c319-132">Le réplica est une cible pour les basculements automatiques.</span><span class="sxs-lookup"><span data-stu-id="5c319-132">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="5c319-133">Pris en charge uniquement si le mode de disponibilité est défini en mode de validation synchrone.</span><span class="sxs-lookup"><span data-stu-id="5c319-133">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="5c319-134">**Manuel**</span><span class="sxs-lookup"><span data-stu-id="5c319-134">**Manual**</span></span>  
 <span data-ttu-id="5c319-135">Basculement manuel.</span><span class="sxs-lookup"><span data-stu-id="5c319-135">Manual failover.</span></span> <span data-ttu-id="5c319-136">Le réplica peut uniquement être basculé manuellement par l'administrateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="5c319-136">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="5c319-137">**Connexions en rôle principal**</span><span class="sxs-lookup"><span data-stu-id="5c319-137">**Connections in primary role**</span></span>  
 <span data-ttu-id="5c319-138">Type de connexions clientes pris en charge lorsque le réplica joue le rôle principal.</span><span class="sxs-lookup"><span data-stu-id="5c319-138">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="5c319-139">**Autoriser toutes les connexions**</span><span class="sxs-lookup"><span data-stu-id="5c319-139">**Allow all connections**</span></span>  
 <span data-ttu-id="5c319-140">Toutes les connexions aux bases de données sont autorisées dans le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="5c319-140">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="5c319-141">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="5c319-141">This is the default setting.</span></span>  
  
 <span data-ttu-id="5c319-142">**Autoriser les connexions en lecture/écriture**</span><span class="sxs-lookup"><span data-stu-id="5c319-142">**Allow read/write connections**</span></span>  
 <span data-ttu-id="5c319-143">Les connexions où la propriété de connexion d’intention de l’application a la valeur **ReadOnly** ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="5c319-143">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="5c319-144">Lorsque la propriété d’intention d’application a la valeur **ReadWrite** ou si la propriété de connexion d’intention d’application n’est pas définie, la connexion est autorisée.</span><span class="sxs-lookup"><span data-stu-id="5c319-144">When the Application Intent property is set to **ReadWrite** or the application intent connection property is not set, the connection is allowed.</span></span>  
  
 <span data-ttu-id="5c319-145">**Lisible secondaire**</span><span class="sxs-lookup"><span data-stu-id="5c319-145">**Readable Secondary**</span></span>  
 <span data-ttu-id="5c319-146">Si un réplica de disponibilité qui revêt le rôle secondaire (autrement dit, un réplica secondaire) peut accepter les connexions des clients, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="5c319-146">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="5c319-147">**Non**</span><span class="sxs-lookup"><span data-stu-id="5c319-147">**No**</span></span>  
 <span data-ttu-id="5c319-148">Aucune connexion directe n'est autorisée aux bases de données secondaires de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="5c319-148">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="5c319-149">Elles ne sont pas disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="5c319-149">They are not available for read access.</span></span> <span data-ttu-id="5c319-150">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="5c319-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="5c319-151">**Tentative de lecture uniquement**</span><span class="sxs-lookup"><span data-stu-id="5c319-151">**Read-intent only**</span></span>  
 <span data-ttu-id="5c319-152">Seules les connexions en lecture seule directes sont autorisées aux bases de données secondaires de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="5c319-152">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="5c319-153">La ou les bases de données secondaires sont toutes disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="5c319-153">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="5c319-154">**Oui**</span><span class="sxs-lookup"><span data-stu-id="5c319-154">**Yes**</span></span>  
 <span data-ttu-id="5c319-155">Toutes les connexions sont autorisées aux bases de données secondaires de ce réplica, mais uniquement pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="5c319-155">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="5c319-156">La ou les bases de données secondaires sont toutes disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="5c319-156">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="5c319-157">Pour plus d’informations, consultez [secondaires actifs : réplicas secondaires accessibles en lecture (groupes de disponibilité AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5c319-157">For more information, see [Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="5c319-158">**Délai d'attente de session (secondes)**</span><span class="sxs-lookup"><span data-stu-id="5c319-158">**Session timeout (seconds)**</span></span>  
 <span data-ttu-id="5c319-159">Délai d'attente en secondes.</span><span class="sxs-lookup"><span data-stu-id="5c319-159">The time-out period, in seconds.</span></span> <span data-ttu-id="5c319-160">Le délai d’expiration est le temps maximum pendant lequel le réplica attend de recevoir un message d’un autre réplica avant de considérer que la connexion entre les réplicas principal et secondaire a échoué.</span><span class="sxs-lookup"><span data-stu-id="5c319-160">The time-out period is the maximum time that the replica waits to receive a message from another replica before considering connection between the primary and secondary replica have failed.</span></span> <span data-ttu-id="5c319-161">Le délai d'expiration de session détecte si les réplicas secondaries sont connectés au réplica primaire.</span><span class="sxs-lookup"><span data-stu-id="5c319-161">Session timeout detects whether secondaries are connected the primary replica.</span></span> <span data-ttu-id="5c319-162">En cas de détection d’un échec de connexion avec un réplica secondaire, le réplica principal considère que le réplica secondaire présente l’état NOT_SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="5c319-162">On detecting a failed connection with a secondary replica, the primary replica considers the secondary replica to be NOT_SYNCHRONIZED.</span></span> <span data-ttu-id="5c319-163">En cas de détection d'un échec de connexion avec le réplica principal, un réplica secondaire tente simplement de se reconnecter.</span><span class="sxs-lookup"><span data-stu-id="5c319-163">On detecting a failed connection with the primary replica, a secondary replica simply attempts to reconnect.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c319-164">Les délais d'expiration de session ne provoquent pas de basculements automatiques.</span><span class="sxs-lookup"><span data-stu-id="5c319-164">Session timeouts do not cause automatic failovers.</span></span>  
  
 <span data-ttu-id="5c319-165">**URL de point de terminaison**</span><span class="sxs-lookup"><span data-stu-id="5c319-165">**Endpoint URL**</span></span>  
 <span data-ttu-id="5c319-166">Représentation de chaîne du point de terminaison de mise en miroir de bases de données spécifié par l'utilisateur, qui est utilisé par les connexions entre les réplicas principal et secondaire pour la synchronisation des données.</span><span class="sxs-lookup"><span data-stu-id="5c319-166">String representation of the user-specified database mirroring endpoint that is used by connections between primary and secondary replicas for data synchronization.</span></span> <span data-ttu-id="5c319-167">Pour plus d’informations sur la syntaxe des URL de point de terminaison, consultez [Spécifier l’URL de point de terminaison lors de l’ajout ou lors de la modification d’un réplica de disponibilité &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="5c319-167">For information about the syntax of endpoint URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c319-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c319-168">See Also</span></span>  
 [<span data-ttu-id="5c319-169">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c319-169">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
