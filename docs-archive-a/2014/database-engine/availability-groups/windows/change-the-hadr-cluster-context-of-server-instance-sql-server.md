---
title: Changer le contexte de cluster HADR de l’instance de serveur (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- Availability replicas [SQL Server], change WSFC cluster context
ms.assetid: ecd99f91-b9a2-4737-994e-507065a12f80
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbc29fa2ebaaf2bbc9e577b5bd303e8a0dd0ec4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708676"
---
# <a name="change-the-hadr-cluster-context-of-server-instance-sql-server"></a><span data-ttu-id="1d225-102">Changer le contexte de cluster HADR de l'instance de serveur (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1d225-102">Change the HADR Cluster Context of Server Instance (SQL Server)</span></span>
  <span data-ttu-id="1d225-103">Cette rubrique explique comment basculer le contexte de cluster HADR d'une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de [!INCLUDE[tsql](../../../includes/tsql-md.md)] dans [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="1d225-103">This topic describes how to switch the HADR cluster context of an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="1d225-104">Le *contexte de cluster HADR* détermine le cluster de clustering de basculement Windows Server (WSFC) qui gère les métadonnées pour les réplicas de disponibilité hébergés par l’instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="1d225-104">The *HADR cluster context* determines which Windows Server Failover Clustering (WSFC) cluster manages the metadata for availability replicas hosted by the server instance.</span></span>  
  
 <span data-ttu-id="1d225-105">Basculez le contexte de cluster HADR uniquement pendant une migration entre clusters de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] vers une instance de [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] sur un nouveau cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="1d225-105">Switch the HADR cluster context only during a cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] to an instance of [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] on a new WSFC cluster.</span></span> <span data-ttu-id="1d225-106">La migration entre clusters de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prend en charge la mise à niveau vers [!INCLUDE[win8](../../../includes/win8-md.md)] ou [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] avec un temps mort minimal des groupes de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="1d225-106">Cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] supports OS upgrade to [!INCLUDE[win8](../../../includes/win8-md.md)] or [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] with minimal downtime of availability groups.</span></span> <span data-ttu-id="1d225-107">Pour plus d'informations, consultez [Migration entre clusters de groupes de disponibilité AlwaysOn pour la mise à niveau du système d'exploitation](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="1d225-107">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1d225-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="1d225-108">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1d225-109">Basculez le contexte de cluster HADR uniquement lors de la migration entre clusters de déploiements [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d225-109">Switch the HADR cluster context only during cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] deployments.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1d225-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="1d225-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1d225-111">Vous pouvez basculer le contexte de cluster HADR uniquement du cluster WSFC local vers un cluster distant, puis de nouveau du cluster distant vers le cluster local.</span><span class="sxs-lookup"><span data-stu-id="1d225-111">You can switch the HADR cluster context only from the local WSFC cluster to a remote cluster and then back from the remote cluster to the local cluster.</span></span> <span data-ttu-id="1d225-112">Vous ne pouvez pas changer de contexte de cluster HADR d'un cluster distant à un autre.</span><span class="sxs-lookup"><span data-stu-id="1d225-112">You cannot switch the HADR cluster context from one remote cluster to another remote cluster.</span></span>  
  
-   <span data-ttu-id="1d225-113">Il est possible de basculer le contexte de cluster HADR vers un cluster distant uniquement lorsque l'instance de SQL Server n'héberge pas un réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="1d225-113">The HADR cluster context can be switched to a remote cluster only when the instance of SQL Server is not hosting any availability replicas.</span></span>  
  
-   <span data-ttu-id="1d225-114">Un environnement de cluster HADR distant peut être basculé vers le cluster local à tout moment.</span><span class="sxs-lookup"><span data-stu-id="1d225-114">A remote HADR cluster context can be switched back to the local cluster at any time.</span></span> <span data-ttu-id="1d225-115">Toutefois, le contexte ne peut pas être rebasculé tant que l'instance de serveur héberge des réplicas de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="1d225-115">However, the context cannot be switched again as long as the server instance is hosting any availability replicas.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1d225-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1d225-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="1d225-117">L'instance de serveur sur laquelle vous modifiez le contexte de cluster HADR doit exécuter [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] ou version ultérieure (édition Entreprise ou ultérieure).</span><span class="sxs-lookup"><span data-stu-id="1d225-117">The server instance on which you change the HADR cluster context must be running [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="1d225-118">L'instance de serveur doit être activée pour AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="1d225-118">The server instance must be enabled for AlwaysOn.</span></span> <span data-ttu-id="1d225-119">Pour plus d’informations, consultez [Activer et désactiver les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1d225-119">For more information, see [Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="1d225-120">Pour pouvoir être basculée du contexte de cluster local vers un cluster à distance, une instance de serveur ne peut pas héberger de réplicas de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="1d225-120">To be eligible to be switched from the local cluster context to a remote cluster cluster, a server instance cannot be hosting any availability replicas.</span></span> <span data-ttu-id="1d225-121">La vue de catalogue [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) ne doit retourner aucune ligne.</span><span class="sxs-lookup"><span data-stu-id="1d225-121">The [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) catalog view should not return any rows.</span></span>  
  
     <span data-ttu-id="1d225-122">S'il existe des réplicas de disponibilité sur l'instance de serveur, avant de modifier le contexte de cluster HADR, vous devez effectuer l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1d225-122">If any availability replicas exist on the server instance, before you can change the HADR cluster context, you must do one of the following:</span></span>  
  
    |<span data-ttu-id="1d225-123">Rôle du réplica</span><span class="sxs-lookup"><span data-stu-id="1d225-123">Replica Role</span></span>|<span data-ttu-id="1d225-124">Action</span><span class="sxs-lookup"><span data-stu-id="1d225-124">Action</span></span>|<span data-ttu-id="1d225-125">Lien</span><span class="sxs-lookup"><span data-stu-id="1d225-125">Link</span></span>|  
    |------------------|------------|----------|  
    |<span data-ttu-id="1d225-126">Principal</span><span class="sxs-lookup"><span data-stu-id="1d225-126">Primary</span></span>|<span data-ttu-id="1d225-127">Place le groupe de disponibilité hors connexion.</span><span class="sxs-lookup"><span data-stu-id="1d225-127">Take the availability group offline.</span></span>|[<span data-ttu-id="1d225-128">Placer un groupe de disponibilité hors connexion &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d225-128">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)|  
    |<span data-ttu-id="1d225-129">Secondary</span><span class="sxs-lookup"><span data-stu-id="1d225-129">Secondary</span></span>|<span data-ttu-id="1d225-130">Supprimer le réplica de son groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="1d225-130">Remove the replica from its availability group</span></span>|[<span data-ttu-id="1d225-131">Supprimer un réplica secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d225-131">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)|  
  
-   <span data-ttu-id="1d225-132">Avant de pouvoir basculer d'un cluster à distance vers un cluster local, tous les réplicas de validation synchrone doivent être dans l'état SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="1d225-132">Before you can switch from a remote cluster to the local cluster, all synchronous-commit replicas must be SYNCHRONIZED.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1d225-133">Recommandations</span><span class="sxs-lookup"><span data-stu-id="1d225-133">Recommendations</span></span>  
  
-   <span data-ttu-id="1d225-134">Nous vous recommandons de spécifier le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="1d225-134">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="1d225-135">Cela est dû au fait que pour rechercher l'adresse IP cible d'un nom court, ALTER SERVER CONFIGURATION utilise la résolution DNS.</span><span class="sxs-lookup"><span data-stu-id="1d225-135">This is because to find the target IP address of a short name, ALTER SERVER CONFIGURATION uses DNS resolution.</span></span> <span data-ttu-id="1d225-136">Dans certaines situations, selon l'ordre de recherche de DNS, l'utilisation d'un nom court peut entraîner quelques confusions.</span><span class="sxs-lookup"><span data-stu-id="1d225-136">Under some situations, depending on the DNS searching order, using a short name could cause confusion.</span></span> <span data-ttu-id="1d225-137">Par exemple, considérez la commande suivante, exécutée sur un nœud dans le domaine `abc` , (`node1.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="1d225-137">For example, consider the following command, which is executed on a node in the `abc` domain, (`node1.abc.com`).</span></span> <span data-ttu-id="1d225-138">Le cluster de destination attendu est le cluster `CLUS01` dans le domaine `xyz` (`clus01.xyz.com`).</span><span class="sxs-lookup"><span data-stu-id="1d225-138">The intended destination cluster is the `CLUS01` cluster in the `xyz` domain (`clus01.xyz.com`).</span></span> <span data-ttu-id="1d225-139">Toutefois, le domaine local héberge aussi un cluster nommé `CLUS01` (`clus01.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="1d225-139">However, the local  domain hosts also hosts a cluster named `CLUS01` (`clus01.abc.com`).</span></span>  
  
     <span data-ttu-id="1d225-140">Si le nom court du cluster cible, `CLUS01`, a été spécifié, la résolution de noms DNS peut retourner l'adresse IP d'un cluster incorrect, `clus01.abc.com`.</span><span class="sxs-lookup"><span data-stu-id="1d225-140">If the short name of the target cluster, `CLUS01`, were specified, DNS name resolution could return the IP address of the wrong cluster, `clus01.abc.com`.</span></span> <span data-ttu-id="1d225-141">Pour éviter une telle confusion, spécifiez le nom complet du cluster cible, comme dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="1d225-141">To avoid such confusion, specify the full name of the target cluster, as in the following example:</span></span>  
  
    ```  
    ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com'  
    ```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1d225-142">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1d225-142">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1d225-143">Autorisations</span><span class="sxs-lookup"><span data-stu-id="1d225-143">Permissions</span></span>  
  
-   <span data-ttu-id="1d225-144">**compte de connexion SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1d225-144">**SQL Server login**</span></span>  
  
     <span data-ttu-id="1d225-145">Requiert l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="1d225-145">Requires CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="1d225-146">**Compte de service SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1d225-146">**SQL Server service account**</span></span>  
  
     <span data-ttu-id="1d225-147">Le compte de service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de l'instance de serveur doit disposer :</span><span class="sxs-lookup"><span data-stu-id="1d225-147">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account of the server instance must have:</span></span>  
  
    -   <span data-ttu-id="1d225-148">des autorisations nécessaires pour ouvrir le cluster WSFC de destination ;</span><span class="sxs-lookup"><span data-stu-id="1d225-148">Permission to open the destination WSFC cluster.</span></span>  
  
    -   <span data-ttu-id="1d225-149">d'un accès en lecture/écriture au cluster WSFC distant.</span><span class="sxs-lookup"><span data-stu-id="1d225-149">Remote WSFC read-write access.</span></span>  
  
 
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1d225-150">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1d225-150">Using Transact-SQL</span></span>  
 <span data-ttu-id="1d225-151">**Pour modifier le contexte de cluster WSFC d'un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="1d225-151">**To change the WSFC cluster context of an availability replica**</span></span>  
  
1.  <span data-ttu-id="1d225-152">Connectez-vous à l'instance de qui héberge soit le réplica principal, soit un réplica secondaire du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="1d225-152">Connect to the server instance that hosts either the primary replica or a secondary replica of the availability group.</span></span>  
  
2.  <span data-ttu-id="1d225-153">Utilisez la clause SET HADR CLUSTER CONTEXT de l’instruction [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="1d225-153">Use the SET HADR CLUSTER CONTEXT clause of the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="1d225-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT **=** { **' *`windows_cluster`* '** | LOCALISÉ</span><span class="sxs-lookup"><span data-stu-id="1d225-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT **=** { **'*`windows_cluster`*'** | LOCAL }</span></span>  
  
     <span data-ttu-id="1d225-155">où :</span><span class="sxs-lookup"><span data-stu-id="1d225-155">where,</span></span>  
  
     <span data-ttu-id="1d225-156">*windows_cluster*</span><span class="sxs-lookup"><span data-stu-id="1d225-156">*windows_cluster*</span></span>  
     <span data-ttu-id="1d225-157">Le nom d'objet cluster (CON) d'un cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="1d225-157">The cluster object name (CON) of a WSFC cluster.</span></span> <span data-ttu-id="1d225-158">Vous pouvez spécifier le nom court ou le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="1d225-158">You can specify either the short name or the full domain name.</span></span> <span data-ttu-id="1d225-159">Nous vous recommandons de spécifier le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="1d225-159">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="1d225-160">Pour plus d’informations, consultez [recommandations](#Recommendations), plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="1d225-160">For more information, see [Recommendations](#Recommendations), earlier in this topic.</span></span>  
  
     <span data-ttu-id="1d225-161">LOCAL</span><span class="sxs-lookup"><span data-stu-id="1d225-161">LOCAL</span></span>  
     <span data-ttu-id="1d225-162">Cluster WSFC local</span><span class="sxs-lookup"><span data-stu-id="1d225-162">The local WSFC cluster.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="1d225-163">Exemples</span><span class="sxs-lookup"><span data-stu-id="1d225-163">Examples</span></span>  
 <span data-ttu-id="1d225-164">L'exemple qui suit remplace le contexte de cluster HADR par un autre cluster.</span><span class="sxs-lookup"><span data-stu-id="1d225-164">The following example changes the HADR cluster context to a different cluster.</span></span> <span data-ttu-id="1d225-165">Pour identifier le cluster WSFC de destination, `clus01`, l'exemple spécifie le nom d'objet cluster complet, `clus01.xyz.com`.</span><span class="sxs-lookup"><span data-stu-id="1d225-165">To identify the destination WSFC cluster, `clus01`, the example specifies the full cluster object name, `clus01.xyz.com`.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com';  
```  
  
 <span data-ttu-id="1d225-166">L'exemple qui suit remplace le contexte de cluster HADR par le cluster WSFC local.</span><span class="sxs-lookup"><span data-stu-id="1d225-166">The following example changes the HADR cluster context to the local WSFC cluster.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = LOCAL;  
```  
  

  
##  <a name="follow-up-after-switching-the-cluster-context-of-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="1d225-167">Suivi : après le basculement du contexte de cluster d'un réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="1d225-167">Follow Up: After Switching the Cluster Context of an Availability Replica</span></span>  
 <span data-ttu-id="1d225-168">Le nouveau contexte de cluster HADR prend effet immédiatement, sans redémarrer l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="1d225-168">The new HADR cluster context takes effect immediately, without restarting the server instance.</span></span> <span data-ttu-id="1d225-169">Le paramètre de contexte de cluster HADR est un paramètre persistant au niveau de l'instance qui demeure inchangé si l'instance de serveur redémarre.</span><span class="sxs-lookup"><span data-stu-id="1d225-169">The HADR cluster context setting is a persistent instance-level setting that remains unchanged if the server instance restarts.</span></span>  
  
 <span data-ttu-id="1d225-170">Confirmez le nouveau contexte de cluster HADR en interrogeant la vue de gestion dynamique [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="1d225-170">Confirm the new HADR cluster context by querying the [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) dynamic management view, as follows:</span></span>  
  
```  
SELECT cluster_name FROM sys.dm_hadr_cluster  
```  
  
 <span data-ttu-id="1d225-171">Cette requête doit retourner le nom du cluster auquel sur lequel vous définissez le contexte de cluster HADR.</span><span class="sxs-lookup"><span data-stu-id="1d225-171">This query should return the name of the cluster to which you set the HADR cluster context.</span></span>  
  
 <span data-ttu-id="1d225-172">Lorsque le contexte de cluster HADR est basculé vers un nouveau cluster :</span><span class="sxs-lookup"><span data-stu-id="1d225-172">When the HADR cluster context is switched to a new cluster:</span></span>  
  
-   <span data-ttu-id="1d225-173">Les métadonnées sont nettoyées pour tous les réplicas de disponibilité qui sont actuellement hébergés par l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d225-173">The metadata is cleaned up for any availability replicas that are currently hosted by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1d225-174">Toutes les bases de données qui ont déjà appartenu à un réplica de disponibilité sont désormais dans un état RESTORING.</span><span class="sxs-lookup"><span data-stu-id="1d225-174">All the databases that previously belonged to an availability replica are now in the RESTORING state.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1d225-175">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="1d225-175">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1d225-176">Supprimer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d225-176">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="1d225-177">Placer un groupe de disponibilité hors connexion &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d225-177">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
-   [<span data-ttu-id="1d225-178">Ajouter un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d225-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="1d225-179">Supprimer un réplica secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d225-179">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="1d225-180">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d225-180">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="1d225-181">Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d225-181">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
 
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="1d225-182">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="1d225-182">Related Content</span></span>  
  
-   <span data-ttu-id="1d225-183">[Articles techniques SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d225-183">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="1d225-184">Blog de l'équipe de SQL Server AlwaysOn : Blog officiel de l'équipe de SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="1d225-184">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="1d225-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d225-185">See Also</span></span>  
 <span data-ttu-id="1d225-186">[Groupes de disponibilité AlwaysOn (SQL Server)](always-on-availability-groups-sql-server.md) [clustering de basculement Windows Server &#40;WSFC&#41; avec SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1d225-186">[AlwaysOn Availability Groups (SQL Server)](always-on-availability-groups-sql-server.md) [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="1d225-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1d225-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-server-configuration-transact-sql)  
  
  
