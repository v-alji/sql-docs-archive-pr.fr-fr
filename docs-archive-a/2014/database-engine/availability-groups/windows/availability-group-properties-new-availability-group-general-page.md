---
title: Propriétés du groupe de disponibilité et nouveau groupe de disponibilité (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.general.f1
ms.assetid: 9af5379f-91b8-4729-9f75-4a80242a30e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 876b9d0948b7cd0d01c21b0ec1d64c51a55fa157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601109"
---
# <a name="availability-group-properties-and-new-availability-group-general-page"></a><span data-ttu-id="9ad80-102">Propriétés du groupe de disponibilité et Nouveau groupe de disponibilité (page Général)</span><span class="sxs-lookup"><span data-stu-id="9ad80-102">Availability Group Properties and New Availability Group (General Page)</span></span>
  <span data-ttu-id="9ad80-103">Cette rubrique s’applique à l’onglet **Général** de la boîte de dialogue **Nouveau groupe de disponibilité** et de la boîte de dialogue **Propriétés du groupe de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="9ad80-103">This topic applies to the **General** tab of both the **New Availability Group** dialog box and the **Availability Group Properties** dialog box.</span></span>  <span data-ttu-id="9ad80-104">La boîte de dialogue **Nouveau groupe de disponibilité** vous permet de créer un nouveau groupe de disponibilité sans utiliser l’ [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ad80-104">The **New Availability Group** dialog box enables you to create a new availability group without using the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span></span> <span data-ttu-id="9ad80-105">La boîte de dialogue **Propriétés du groupe de disponibilité** vous permet d’afficher et de modifier la configuration d’un groupe de disponibilité existant.</span><span class="sxs-lookup"><span data-stu-id="9ad80-105">The **Availability Group Properties** dialog box enables you to view and alter the configuration of an existing availability group.</span></span>  
  
 <span data-ttu-id="9ad80-106">**Pour afficher les propriétés d'un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9ad80-106">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="9ad80-107">Afficher les propriétés d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ad80-107">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="9ad80-108">Utiliser le tableau de bord Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9ad80-108">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="9ad80-109">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="9ad80-109">UI element list</span></span>  
 <span data-ttu-id="9ad80-110">**Nom du groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9ad80-110">**Availability group name**</span></span>  
 <span data-ttu-id="9ad80-111">Nom du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9ad80-111">Name of the availability group.</span></span> <span data-ttu-id="9ad80-112">Il s'agit d'un nom spécifié par l'utilisateur qui doit être unique dans le cluster de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="9ad80-112">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
## <a name="availability-databases"></a><span data-ttu-id="9ad80-113">Bases de données de disponibilité</span><span class="sxs-lookup"><span data-stu-id="9ad80-113">Availability Databases</span></span>  
 <span data-ttu-id="9ad80-114">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="9ad80-114">**Database Name**</span></span>  
 <span data-ttu-id="9ad80-115">Nom d'une base de données qui a été ajoutée au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9ad80-115">Name of a database that has been added to the availability group.</span></span>  
  
 <span data-ttu-id="9ad80-116">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="9ad80-116">**Add**</span></span>  
 <span data-ttu-id="9ad80-117">Cliquez pour ajouter une base de données au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9ad80-117">Click to add a database to the availability group.</span></span>  
  
 <span data-ttu-id="9ad80-118">**Remove**</span><span class="sxs-lookup"><span data-stu-id="9ad80-118">**Remove**</span></span>  
 <span data-ttu-id="9ad80-119">Cliquez pour supprimer une base de données sélectionnée du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9ad80-119">Click to remove a selected database from the availability group.</span></span>  
  
## <a name="availability-replicas"></a><span data-ttu-id="9ad80-120">Réplicas de disponibilité</span><span class="sxs-lookup"><span data-stu-id="9ad80-120">Availability Replicas</span></span>  
 <span data-ttu-id="9ad80-121">**Instance de serveur**</span><span class="sxs-lookup"><span data-stu-id="9ad80-121">**Server instance**</span></span>  
 <span data-ttu-id="9ad80-122">Nom de serveur de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge ce réplica et, pour une instance non définie par défaut, son nom d'instance.</span><span class="sxs-lookup"><span data-stu-id="9ad80-122">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="9ad80-123">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="9ad80-123">**Role**</span></span>  
 <span data-ttu-id="9ad80-124">**Primaire**</span><span class="sxs-lookup"><span data-stu-id="9ad80-124">**Primary**</span></span>  
 <span data-ttu-id="9ad80-125">Actuellement le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="9ad80-125">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="9ad80-126">**Secondaire**</span><span class="sxs-lookup"><span data-stu-id="9ad80-126">**Secondary**</span></span>  
 <span data-ttu-id="9ad80-127">Actuellement un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="9ad80-127">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="9ad80-128">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="9ad80-128">**Resolving**</span></span>  
 <span data-ttu-id="9ad80-129">Actuellement le rôle de réplica est en cours d'être résolu en rôle principal ou secondaire.</span><span class="sxs-lookup"><span data-stu-id="9ad80-129">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="9ad80-130">**Mode de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9ad80-130">**Availability Mode**</span></span>  
 <span data-ttu-id="9ad80-131">Mode de disponibilité du réplica, parmi :</span><span class="sxs-lookup"><span data-stu-id="9ad80-131">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="9ad80-132">**Validation asynchrone**</span><span class="sxs-lookup"><span data-stu-id="9ad80-132">**Asynchronous commit**</span></span>  
 <span data-ttu-id="9ad80-133">Le réplica principal peut valider des transactions sans attendre que le réplica secondaire écrive le journal sur le disque.</span><span class="sxs-lookup"><span data-stu-id="9ad80-133">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="9ad80-134">**Validation synchrone**</span><span class="sxs-lookup"><span data-stu-id="9ad80-134">**Synchronous commit**</span></span>  
 <span data-ttu-id="9ad80-135">Le réplica principal attend pour valider une transaction donnée que le réplica secondaire ait écrit la transaction sur le disque.</span><span class="sxs-lookup"><span data-stu-id="9ad80-135">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="9ad80-136">Pour plus d’informations, consultez [modes de disponibilité (groupes de disponibilité AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9ad80-136">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="9ad80-137">**Mode de basculement**</span><span class="sxs-lookup"><span data-stu-id="9ad80-137">**Failover Mode**</span></span>  
 <span data-ttu-id="9ad80-138">Mode de basculement du réplica, parmi :</span><span class="sxs-lookup"><span data-stu-id="9ad80-138">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="9ad80-139">**Automatique**</span><span class="sxs-lookup"><span data-stu-id="9ad80-139">**Automatic**</span></span>  
 <span data-ttu-id="9ad80-140">Basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="9ad80-140">Automatic failover.</span></span> <span data-ttu-id="9ad80-141">Le réplica est une cible pour les basculements automatiques.</span><span class="sxs-lookup"><span data-stu-id="9ad80-141">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="9ad80-142">Pris en charge uniquement si le mode de disponibilité est défini en mode de validation synchrone.</span><span class="sxs-lookup"><span data-stu-id="9ad80-142">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="9ad80-143">**Manuel**</span><span class="sxs-lookup"><span data-stu-id="9ad80-143">**Manual**</span></span>  
 <span data-ttu-id="9ad80-144">Basculement manuel.</span><span class="sxs-lookup"><span data-stu-id="9ad80-144">Manual failover.</span></span> <span data-ttu-id="9ad80-145">Le réplica peut uniquement être basculé manuellement par l'administrateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="9ad80-145">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="9ad80-146">**Connexions dans le rôle principal**</span><span class="sxs-lookup"><span data-stu-id="9ad80-146">**Connections in Primary Role**</span></span>  
 <span data-ttu-id="9ad80-147">Type de connexions clientes pris en charge lorsque le réplica joue le rôle principal.</span><span class="sxs-lookup"><span data-stu-id="9ad80-147">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="9ad80-148">**Autoriser toutes les connexions**</span><span class="sxs-lookup"><span data-stu-id="9ad80-148">**Allow all connections**</span></span>  
 <span data-ttu-id="9ad80-149">Toutes les connexions aux bases de données sont autorisées dans le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="9ad80-149">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="9ad80-150">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="9ad80-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="9ad80-151">**Autoriser les connexions en lecture/écriture**</span><span class="sxs-lookup"><span data-stu-id="9ad80-151">**Allow read/write connections**</span></span>  
 <span data-ttu-id="9ad80-152">Les connexions où la propriété de connexion d’intention de l’application a la valeur **ReadOnly** ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="9ad80-152">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="9ad80-153">Lorsque la propriété d'intention de l'application a la valeur **ReadWrite** ou si cette propriété n'est pas définie, la connexion est autorisée.</span><span class="sxs-lookup"><span data-stu-id="9ad80-153">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="9ad80-154">Pour plus d'informations sur la propriété de connexion d'intention de l'application, consultez [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="9ad80-154">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="9ad80-155">**Lisible secondaire**</span><span class="sxs-lookup"><span data-stu-id="9ad80-155">**Readable Secondary**</span></span>  
 <span data-ttu-id="9ad80-156">Si un réplica de disponibilité qui revêt le rôle secondaire (autrement dit, un réplica secondaire) peut accepter les connexions des clients, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="9ad80-156">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="9ad80-157">**Non**</span><span class="sxs-lookup"><span data-stu-id="9ad80-157">**No**</span></span>  
 <span data-ttu-id="9ad80-158">Aucune connexion directe n'est autorisée aux bases de données secondaires de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="9ad80-158">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="9ad80-159">Elles ne sont pas disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="9ad80-159">They are not available for read access.</span></span> <span data-ttu-id="9ad80-160">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="9ad80-160">This is the default setting.</span></span>  
  
 <span data-ttu-id="9ad80-161">**Tentative de lecture uniquement**</span><span class="sxs-lookup"><span data-stu-id="9ad80-161">**Read-intent only**</span></span>  
 <span data-ttu-id="9ad80-162">Seules les connexions en lecture seule directes sont autorisées aux bases de données secondaires de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="9ad80-162">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="9ad80-163">La ou les bases de données secondaires sont toutes disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="9ad80-163">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="9ad80-164">**Oui**</span><span class="sxs-lookup"><span data-stu-id="9ad80-164">**Yes**</span></span>  
 <span data-ttu-id="9ad80-165">Toutes les connexions sont autorisées aux bases de données secondaires de ce réplica, mais uniquement pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="9ad80-165">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="9ad80-166">La ou les bases de données secondaires sont toutes disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="9ad80-166">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="9ad80-167">**Délai d'attente de session (secondes)**</span><span class="sxs-lookup"><span data-stu-id="9ad80-167">**Session Timeout (seconds)**</span></span>  
 <span data-ttu-id="9ad80-168">Nombre de secondes pour la période de délai d'expiration de session sur ce réplica.</span><span class="sxs-lookup"><span data-stu-id="9ad80-168">The number of seconds for the session-timeout period on this replica.</span></span>  
  
 <span data-ttu-id="9ad80-169">**URL de point de terminaison**</span><span class="sxs-lookup"><span data-stu-id="9ad80-169">**Endpoint URL**</span></span>  
 <span data-ttu-id="9ad80-170">URL du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="9ad80-170">The URL of the endpoint.</span></span> <span data-ttu-id="9ad80-171">Pour plus d’informations sur le format de ces URL, consultez [Spécifier l’URL de point de terminaison lors de l’ajout ou lors de la modification d’un réplica de disponibilité &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="9ad80-171">For information the format of these URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
 <span data-ttu-id="9ad80-172">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="9ad80-172">**Add**</span></span>  
 <span data-ttu-id="9ad80-173">Cliquez pour ajouter un réplica secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9ad80-173">Click to add a secondary replica to the availability group.</span></span>  
  
 <span data-ttu-id="9ad80-174">**Remove**</span><span class="sxs-lookup"><span data-stu-id="9ad80-174">**Remove**</span></span>  
 <span data-ttu-id="9ad80-175">Cliquez pour supprimer un réplica secondaire du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9ad80-175">Click to remove a secondary replica from the availability group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad80-176">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ad80-176">See Also</span></span>  
 [<span data-ttu-id="9ad80-177">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ad80-177">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
