---
title: Afficher les propriétés d’un écouteur de groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistenerproperties.general.f1
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
ms.assetid: aca0d016-3228-40b8-bdc3-285ed6d9b280
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7fe316394a030350ceb12a0d1b8e2d48ee1d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601105"
---
# <a name="view-availability-group-listener-properties-sql-server"></a><span data-ttu-id="ce1a8-102">Afficher les propriétés d’un écouteur de groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ce1a8-102">View Availability Group Listener Properties (SQL Server)</span></span>
  <span data-ttu-id="ce1a8-103">Cette rubrique explique comment afficher les propriétés d'un *écouteur de groupe de disponibilité* AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)] dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce1a8-103">This topic describes how to view the properties of an AlwaysOn *availability group listener* by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="ce1a8-104">**Pour afficher les propriétés d'un écouteur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="ce1a8-104">**To view listener properties, using:**</span></span>  
  
     [<span data-ttu-id="ce1a8-105">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce1a8-105">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ce1a8-106">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce1a8-106">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ce1a8-107">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce1a8-107">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ce1a8-108">**Pour afficher les propriétés d'un écouteur, procédez comme suit :**</span><span class="sxs-lookup"><span data-stu-id="ce1a8-108">**To view listener properties**</span></span>  
  
1.  <span data-ttu-id="ce1a8-109">Dans l'Explorateur d'objets, connectez-vous à une instance de serveur qui héberge un réplica de disponibilité du groupe de disponibilité dont vous souhaitez afficher l'écouteur.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-109">In Object Explorer, connect to a server instance that hosts any availability replica of the availability group whose listener you want to view.</span></span> <span data-ttu-id="ce1a8-110">Cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-110">Click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ce1a8-111">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="ce1a8-111">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="ce1a8-112">Développez le nœud du groupe de disponibilité, puis développez le nœud **Écouteurs de groupe de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="ce1a8-112">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="ce1a8-113">Cliquez avec le bouton droit sur l’écouteur que vous voulez afficher, puis sélectionnez la commande **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="ce1a8-113">Right-click the listener that you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="ce1a8-114">Cela ouvre la boîte de dialogue **Propriétés de l'écouteur du groupe disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="ce1a8-114">This opens the **Availability Group Listener Properties** dialog box.</span></span> <span data-ttu-id="ce1a8-115">Pour plus d’informations, consultez [Propriétés de l’écouteur du groupe disponibilité (boîte de dialogue)](#AgListenerPropertiesDialog), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-115">For more information, see [Availability Group Listener Properties (Dialog Box)](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="availability-group-listener-properties-dialog-box"></a><a name="AgListenerPropertiesDialog"></a> <span data-ttu-id="ce1a8-116">Propriétés de l’écouteur du groupe disponibilité (boîte de dialogue)</span><span class="sxs-lookup"><span data-stu-id="ce1a8-116">Availability Group Listener Properties (Dialog Box)</span></span>  
 <span data-ttu-id="ce1a8-117">**Nom DNS de l'écouteur**</span><span class="sxs-lookup"><span data-stu-id="ce1a8-117">**Listener DNS Name**</span></span>  
 <span data-ttu-id="ce1a8-118">Nom réseau de l'écouteur du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-118">The network name of the availability group listener.</span></span>  
  
 <span data-ttu-id="ce1a8-119">**Port**</span><span class="sxs-lookup"><span data-stu-id="ce1a8-119">**Port**</span></span>  
 <span data-ttu-id="ce1a8-120">Port TCP utilisé par cet écouteur.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-120">The TCP port used by this listener.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce1a8-121">Si vous êtes connecté au réplica principal, vous pouvez utiliser ce champ pour modifier le numéro de port de l'écouteur.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-121">If you are connected the primary replica, you can use this field to modify the port number of the listener.</span></span> <span data-ttu-id="ce1a8-122">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-122">This requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
 <span data-ttu-id="ce1a8-123">**Mode réseau**</span><span class="sxs-lookup"><span data-stu-id="ce1a8-123">**Network Mode**</span></span>  
 <span data-ttu-id="ce1a8-124">Indique le protocole TCP utilisé par l'écouteur, à savoir :</span><span class="sxs-lookup"><span data-stu-id="ce1a8-124">Indicates the TCP protocol used by the listener, one of:</span></span>  
  
 <span data-ttu-id="ce1a8-125">**DHCP**</span><span class="sxs-lookup"><span data-stu-id="ce1a8-125">**DHCP**</span></span>  
 <span data-ttu-id="ce1a8-126">L'écouteur utilise une adresse IP dynamique affectée par un serveur exécutant le protocole DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="ce1a8-126">The listener uses an dynamic IP address that is assigned by a server running the Dynamic Host Configuration Protocol (DHCP).</span></span>  
  
 <span data-ttu-id="ce1a8-127">**Adresse IP statique**</span><span class="sxs-lookup"><span data-stu-id="ce1a8-127">**Static IP**</span></span>  
 <span data-ttu-id="ce1a8-128">L'écouteur utilise une ou plusieurs adresses IP statiques.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-128">The listener uses one or more Static IP addresses.</span></span> <span data-ttu-id="ce1a8-129">Pour accéder aux différents sous-réseaux, un écouteur de groupe de disponibilité doit utiliser des adresses IP statiques.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-129">To access the different subnets, an availability group listener must use static IP addresses.</span></span>  
  
 <span data-ttu-id="ce1a8-130">La grille affiche chacun des sous-réseaux sur lesquels l'écouteur écoute, ainsi que l'adresse IP associée à chaque sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-130">The grid displays each of the subnets on which the listener listens and the IP address associated with that subnet.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ce1a8-131">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce1a8-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="ce1a8-132">**Pour afficher les propriétés d'un écouteur, procédez comme suit :**</span><span class="sxs-lookup"><span data-stu-id="ce1a8-132">**To view listener properties**</span></span>  
  
 <span data-ttu-id="ce1a8-133">Pour surveiller les écouteurs de groupe de disponibilité, utilisez les vues suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce1a8-133">To monitor the availability group listeners, use the following views:</span></span>  
  
 [<span data-ttu-id="ce1a8-134">sys.availability_group_listener_ip_addresses</span><span class="sxs-lookup"><span data-stu-id="ce1a8-134">sys.availability_group_listener_ip_addresses</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listener-ip-addresses-transact-sql)  
 <span data-ttu-id="ce1a8-135">Retourne une ligne pour chaque adresse IP virtuelle conforme actuellement en ligne pour un écouteur de groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-135">Returns a row for every conformant virtual IP address that is currently online for an availability group listener.</span></span>  
  
 <span data-ttu-id="ce1a8-136">**Noms de colonne** : listener_id, ip_address, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span><span class="sxs-lookup"><span data-stu-id="ce1a8-136">**Column names:** listener_id, ip_address, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span></span>  
  
 [<span data-ttu-id="ce1a8-137">sys.availability_group_listeners</span><span class="sxs-lookup"><span data-stu-id="ce1a8-137">sys.availability_group_listeners</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listeners-transact-sql)  
 <span data-ttu-id="ce1a8-138">Pour un groupe de disponibilité donné, retourne soit zéro ligne pour indiquer qu'aucun nom réseau n'est associé au groupe de disponibilité, soit une ligne pour chaque configuration d'écouteur de groupe de disponibilité dans le cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-138">For a given availability group, returns either zero rows indicating that no network name is associated with the availability group, or returns a row for each availability-group listener configuration in the WSFC cluster.</span></span>  
  
 <span data-ttu-id="ce1a8-139">**Noms de colonne** : group_id, listener_id, dns_name, port, is_conformant, ip_configuration_string_from_cluster</span><span class="sxs-lookup"><span data-stu-id="ce1a8-139">**Column names:** group_id, listener_id, dns_name, port, is_conformant, ip_configuration_string_from_cluster</span></span>  
  
 [<span data-ttu-id="ce1a8-140">sys.dm_tcp_listener_states</span><span class="sxs-lookup"><span data-stu-id="ce1a8-140">sys.dm_tcp_listener_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tcp-listener-states-transact-sql)  
 <span data-ttu-id="ce1a8-141">Retourne une ligne contenant les informations dynamiques d'état pour chaque écouteur TCP.</span><span class="sxs-lookup"><span data-stu-id="ce1a8-141">Returns a row containing dynamic-state information for each TCP listener.</span></span>  
  
 <span data-ttu-id="ce1a8-142">**Noms de colonne** : listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span><span class="sxs-lookup"><span data-stu-id="ce1a8-142">**Column names:** listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce1a8-143">Pour plus d’informations sur l’utilisation de [!INCLUDE[tsql](../../../includes/tsql-md.md)] pour surveiller votre environnement [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , consultez [Surveiller des groupes de disponibilité &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ce1a8-143">For more information about using [!INCLUDE[tsql](../../../includes/tsql-md.md)] to monitor your [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] environment, see [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ce1a8-144">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ce1a8-144">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ce1a8-145">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ce1a8-145">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="ce1a8-146">Supprimer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ce1a8-146">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ce1a8-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce1a8-147">See Also</span></span>  
 <span data-ttu-id="ce1a8-148">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ce1a8-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="ce1a8-149">[Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="ce1a8-149">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="ce1a8-150">Surveiller des groupes de disponibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce1a8-150">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
