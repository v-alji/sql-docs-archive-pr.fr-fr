---
title: Configurer le routage en lecture seule pour un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- read-only routing
- Availability Groups [SQL Server], readable secondary replicas
- Availability Groups [SQL Server], read-only routing
- readable secondary replicas
- Availability Groups [SQL Server], client connectivity
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 7bd89ddd-0403-4930-a5eb-3c78718533d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d51d1db75caa29814a01fc1f49bfdd49b403c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611954"
---
# <a name="configure-read-only-routing-for-an-availability-group-sql-server"></a><span data-ttu-id="30774-102">Configurer le routage en lecture seule pour un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="30774-102">Configure Read-Only Routing for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="30774-103">Pour configurer un groupe de disponibilité AlwaysOn et prendre en charge le routage en lecture seule dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], vous pouvez utiliser [!INCLUDE[tsql](../../../includes/tsql-md.md)] ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30774-103">To configure an AlwaysOn availability group to support read-only routing in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can use either [!INCLUDE[tsql](../../../includes/tsql-md.md)] or PowerShell.</span></span> <span data-ttu-id="30774-104">Le*routage en lecture seule* fait référence à la capacité de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] d'acheminer les demandes de connexion en lecture seule applicables à un [réplica secondaire lisible](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) AlwaysOn disponible (autrement dit, un réplica configuré pour autoriser des charges de travail en lecture seule lorsqu'il s'exécute sous le rôle secondaire).</span><span class="sxs-lookup"><span data-stu-id="30774-104">*Read-only routing* refers to the ability of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to route qualifying read-only connection requests to an available AlwaysOn [readable secondary replica](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) (that is, a replica that is configured to allow read-only workloads when running under the secondary role).</span></span> <span data-ttu-id="30774-105">Pour prendre en charge le routage en lecture seule, le groupe de disponibilité doit posséder un [écouteur de groupe de disponibilité](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="30774-105">To support read-only routing, the availability group must possess an [availability group listener](../../listeners-client-connectivity-application-failover.md).</span></span> <span data-ttu-id="30774-106">Les clients en lecture seule doivent diriger leurs demandes de connexion à cet écouteur, et les chaînes de connexion du client doivent spécifier l'intention d'application « en lecture seule ».</span><span class="sxs-lookup"><span data-stu-id="30774-106">Read-only clients must direct their connection requests to this listener, and the client's connection strings must specify the application intent as "read-only."</span></span> <span data-ttu-id="30774-107">Autrement dit, il doit s’agir de *demandes de connexion d’intention de lecture*.</span><span class="sxs-lookup"><span data-stu-id="30774-107">That is, they must be *read-intent connection requests*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30774-108">Pour plus d’informations sur la configuration d’un réplica secondaire lisible, consultez [Configurer l’accès en lecture seule sur un réplica de disponibilité &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30774-108">For information about how to configure a readable secondary replica, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="30774-109">La configuration du routage en lecture seule n'est pas prise en charge par [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30774-109">Configuring read-only routing is not supported by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="30774-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="30774-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="30774-111">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="30774-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="30774-112">Le groupe de disponibilité doit posséder un écouteur.</span><span class="sxs-lookup"><span data-stu-id="30774-112">The availability group must possess an availability group listener.</span></span> <span data-ttu-id="30774-113">Pour plus d'informations, consultez [Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30774-113">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   <span data-ttu-id="30774-114">Un ou plusieurs réplicas de disponibilité doivent être configurés pour accepter les accès en lecture seule dans le rôle secondaire (autrement dit, pour être des [réplicas secondaires lisibles](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn% 20Availability% 20Groups \) . MD)).</span><span class="sxs-lookup"><span data-stu-id="30774-114">One or more availability replicas must be configured to accept read-only in the secondary role (that is, to be [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn%20Availability%20Groups\).md)).</span></span> <span data-ttu-id="30774-115">Pour plus d’informations, consultez [Configurer l’accès en lecture seule sur un réplica de disponibilité &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30774-115">For more information, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>  
  
-   <span data-ttu-id="30774-116">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal actuel.</span><span class="sxs-lookup"><span data-stu-id="30774-116">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
###  <a name="what-replica-properties-do-you-need-to-configure-to-support-read-only-routing"></a><a name="RORReplicaProperties"></a><span data-ttu-id="30774-117">Quelles sont les propriétés de réplica que vous devez configurer pour prendre en charge le routage en lecture seule ?</span><span class="sxs-lookup"><span data-stu-id="30774-117">What Replica Properties Do you Need to Configure to Support Read-Only Routing?</span></span>  
  
-   <span data-ttu-id="30774-118">Pour chaque réplica secondaire lisible qui doit prendre en charge le routage en lecture seule, vous devez spécifier une *URL de routage en lecture seule*.</span><span class="sxs-lookup"><span data-stu-id="30774-118">For each readable secondary replica that is to support read-only routing, you need to specify a *read-only routing URL*.</span></span> <span data-ttu-id="30774-119">Cette URL est effective uniquement lorsque le réplica local s'exécute sous le rôle secondaire.</span><span class="sxs-lookup"><span data-stu-id="30774-119">This URL takes effect only when the local replica is running under the secondary role.</span></span> <span data-ttu-id="30774-120">L'URL de routage en lecture seule doit être spécifiée par réplica, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="30774-120">The read-only routing URL must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="30774-121">Chaque URL de routage en lecture seule est utilisée pour acheminer les demandes de connexion d'intention de lecture vers un réplica secondaire lisible spécifique.</span><span class="sxs-lookup"><span data-stu-id="30774-121">Each read-only routing URL is used for routing read-intent connection requests to a specific readable secondary replica.</span></span> <span data-ttu-id="30774-122">En général, à chaque réplica secondaire lisible est affecté une URL de routage en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="30774-122">Typically, every readable secondary replica is assigned a read-only routing URL.</span></span>  
  
     <span data-ttu-id="30774-123">Pour plus d'informations sur le calcul de l'URL de routage en lecture seule pour un réplica de disponibilité, consultez [Calcul de l'URL de routage en lecture seule pour AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="30774-123">For information about calculating the read-only routing URL for an availability replica, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
-   <span data-ttu-id="30774-124">Pour chaque réplica de disponibilité qui doit prendre en charge le routage en lecture seule lorsqu’il est le réplica principal, vous devez spécifier une *liste de routage en lecture seule*.</span><span class="sxs-lookup"><span data-stu-id="30774-124">For each availability replica that you want to support read-only routing when it is the primary replica, you need to specify a *read-only routing list*.</span></span> <span data-ttu-id="30774-125">Une liste de routage en lecture seule donnée est effective uniquement lorsque le réplica local s'exécute sous le rôle principal.</span><span class="sxs-lookup"><span data-stu-id="30774-125">A given read-only routing list takes effect only when the local replica is running under the primary role.</span></span> <span data-ttu-id="30774-126">Cette liste doit être spécifiée par réplica, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="30774-126">This list must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="30774-127">En général, chaque liste de routage en lecture seule contient toutes les URL de routage en lecture seule, avec l'URL du réplica local à la fin de la liste.</span><span class="sxs-lookup"><span data-stu-id="30774-127">Typically, each read-only routing list would contain every read-only routing URL, with the URL of the local replica at the end of the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30774-128">Les demandes de connexion d'intention de lecture sont acheminées vers le premier secondaire lisible disponible dans la liste de routage en lecture seule du réplica principal actuel.</span><span class="sxs-lookup"><span data-stu-id="30774-128">Read-intent connection requests are routed to the first available readable secondary on the read-only routing list of the current primary replica.</span></span> <span data-ttu-id="30774-129">Il n'existe aucun équilibrage de charge.</span><span class="sxs-lookup"><span data-stu-id="30774-129">There is no load balancing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30774-130">Pour plus d’informations sur les écouteurs de groupe de disponibilité et sur le routage en lecture seule, consultez [Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="30774-130">For information about availability group listeners and more information about read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="30774-131">Sécurité</span><span class="sxs-lookup"><span data-stu-id="30774-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="30774-132">Autorisations</span><span class="sxs-lookup"><span data-stu-id="30774-132">Permissions</span></span>  
  
|<span data-ttu-id="30774-133">Tâche</span><span class="sxs-lookup"><span data-stu-id="30774-133">Task</span></span>|<span data-ttu-id="30774-134">Autorisations</span><span class="sxs-lookup"><span data-stu-id="30774-134">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="30774-135">Pour configurer des réplicas lors de la création d'un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="30774-135">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="30774-136">Requiert l’appartenance au rôle serveur fixe **sysadmin** et l’autorisation de serveur CREATE AVAILABILITY GROUP, l’autorisation ALTER ANY AVAILABILITY GROUP ou l’autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="30774-136">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="30774-137">Pour modifier un réplica de disponibilité :</span><span class="sxs-lookup"><span data-stu-id="30774-137">To modify an availability replica</span></span>|<span data-ttu-id="30774-138">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="30774-138">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="30774-139">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30774-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="30774-140">**Pour configurer le routage en lecture seule**</span><span class="sxs-lookup"><span data-stu-id="30774-140">**To Configure read-only routing**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30774-141">Pour obtenir un exemple de code, consultez [Exemple (Transact-SQL)](#TsqlExample), plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="30774-141">For a code example, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="30774-142">Connectez-vous à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="30774-142">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="30774-143">Si vous spécifiez un réplica pour un nouveau groupe de disponibilité, utilisez l'instruction [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30774-143">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="30774-144">Si vous ajoutez ou modifiez un réplica pour un groupe de disponibilité existant, utilisez l’instruction [ALTER Availability Group](/sql/t-sql/statements/alter-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30774-144">If you are adding or modifying a replica for an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="30774-145">Pour configurer le routage en lecture seule pour le rôle secondaire, dans la clause ADD REPLICA ou MODIFY REPLICA WITH, spécifiez l'option SECONDARY_ROLE, comme suit :</span><span class="sxs-lookup"><span data-stu-id="30774-145">To configure read-only routing for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="30774-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **= '** TCP **:// *`system-address`* : *`port`* ')**</span><span class="sxs-lookup"><span data-stu-id="30774-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **='** TCP **://*`system-address`*:*`port`*')**</span></span>  
  
         <span data-ttu-id="30774-147">Les paramètres de l'URL de routage en lecture sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="30774-147">The parameters of the read-only routing URL are as follows:</span></span>  
  
         <span data-ttu-id="30774-148">*system-address*</span><span class="sxs-lookup"><span data-stu-id="30774-148">*system-address*</span></span>  
         <span data-ttu-id="30774-149">Chaîne, telle qu'un nom de système, un nom de domaine complet ou une adresse IP, qui identifie de manière unique l'ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="30774-149">Is a string, such as a system name, a fully qualified domain name, or an IP address, that unambiguously identifies the destination computer system.</span></span>  
  
         <span data-ttu-id="30774-150">*port*</span><span class="sxs-lookup"><span data-stu-id="30774-150">*port*</span></span>  
         <span data-ttu-id="30774-151">Numéro de port utilisé par le moteur de base de données de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30774-151">Is a port number that is used by the Database Engine of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="30774-152">Par exemple :   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span><span class="sxs-lookup"><span data-stu-id="30774-152">For example:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span></span>  
  
         <span data-ttu-id="30774-153">Dans une clause MODIFY REPLICA, ALLOW_CONNECTIONS est facultatif si le réplica est déjà configuré pour autoriser les connexions en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="30774-153">In a MODIFY REPLICA clause the ALLOW_CONNECTIONS is optional if the replica is already configured to allow read-only connections.</span></span>  
  
         <span data-ttu-id="30774-154">Pour plus d'informations, consultez [Calcul de l'URL de routage en lecture seule pour AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="30774-154">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="30774-155">Pour configurer le routage en lecture seule pour le rôle principal, dans la clause ADD REPLICA ou MODIFY REPLICA WITH, spécifiez l'option PRIMARY_ROLE, comme suit :</span><span class="sxs-lookup"><span data-stu-id="30774-155">To configure read-only routing for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="30774-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **= (' *`server`* '** [ **,**... *n* ] **))**</span><span class="sxs-lookup"><span data-stu-id="30774-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **=('*`server`*'** [ **,**...*n* ] **))**</span></span>  
  
         <span data-ttu-id="30774-157">où *server* indique une instance de serveur qui héberge un réplica secondaire en lecture seule dans le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="30774-157">where, *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span>  
  
         <span data-ttu-id="30774-158">Par exemple :   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span><span class="sxs-lookup"><span data-stu-id="30774-158">For example:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="30774-159">Vous devez définir le routage en lecture seule avant de configurer la liste de routage en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="30774-159">You must set the read-only routing URL before configuring the read-only routing list.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="30774-160">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="30774-160">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="30774-161">L'exemple suivant modifie deux réplicas de disponibilité d'un groupe de disponibilité existant, `AG1` pour prendre en charge le routage en lecture seule si un de ces réplicas détient actuellement le rôle principal.</span><span class="sxs-lookup"><span data-stu-id="30774-161">The following example modifies two availability replicas of an existing availability group, `AG1` to support read-only routing if one of these replicas currently owns the primary role.</span></span> <span data-ttu-id="30774-162">Pour identifier les instances de serveur qui hébergent le réplica de disponibilité, cet exemple spécifie les noms d’instance `COMPUTER01` et `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="30774-162">To identify the server instances that host the availability replica, this example specifies the instance names-`COMPUTER01` and `COMPUTER02`.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER02.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER02','COMPUTER01')));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER01','COMPUTER02')));  
GO
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="30774-163">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="30774-163">Using PowerShell</span></span>  

### <a name="to-configure-read-only-routing"></a><span data-ttu-id="30774-164">Pour configurer le routage en lecture seule</span><span class="sxs-lookup"><span data-stu-id="30774-164">To Configure read-only routing</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="30774-165">Pour obtenir un exemple de code, consultez [Exemple (PowerShell)](#PSExample), plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="30774-165">For a code example, see [Example (PowerShell)](#PSExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="30774-166">Définissez la valeur par défaut (`cd`) sur l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="30774-166">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="30774-167">Lorsque vous ajoutez un réplica de disponibilité à un groupe de disponibilité, utilisez l'applet de commande `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="30774-167">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="30774-168">Lorsque vous modifiez un réplica de disponibilité existant, utilisez l'applet de commande `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="30774-168">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="30774-169">Les paramètres pertinents sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="30774-169">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="30774-170">Pour configurer le routage en lecture seule pour le rôle secondaire, spécifiez le paramètre **paramètre readonlyroutingconnectionurl « *`url`* »** .</span><span class="sxs-lookup"><span data-stu-id="30774-170">To configure read-only routing for the secondary role, specify the **ReadonlyRoutingConnectionUrl"*`url`*"** parameter.</span></span>  
  
         <span data-ttu-id="30774-171">où *url* est le nom de domaine complet (FQDN) de la connectivité et le port à utiliser lors de l’acheminement vers le réplica pour les connexions en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="30774-171">where, *url* is the connectivity fully-qualified domain name (FQDN) and port to use when routing to the replica for read-only connections.</span></span> <span data-ttu-id="30774-172">Par exemple : `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span><span class="sxs-lookup"><span data-stu-id="30774-172">For example:  `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span></span>  
  
         <span data-ttu-id="30774-173">Pour plus d'informations, consultez [Calcul de l'URL de routage en lecture seule pour AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="30774-173">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="30774-174">Pour configurer l’accès à la connexion pour le rôle principal, spécifiez **ReadonlyRoutingList " *`server`* "** [ **,**... *n* ], où le *serveur* identifie une instance de serveur qui héberge un réplica secondaire en lecture seule dans le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="30774-174">To configure connection access for the primary role, specify **ReadonlyRoutingList"*`server`*"** [ **,**...*n* ], where *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span> <span data-ttu-id="30774-175">Par exemple : `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span><span class="sxs-lookup"><span data-stu-id="30774-175">For example:  `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="30774-176">Vous devez définir l'URL de routage en lecture seule d'un réplica avant de configurer sa liste de routage en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="30774-176">You must set the read-only routing URL of a replica before configuring its read-only routing list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30774-177">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30774-177">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="30774-178">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="30774-178">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="30774-179">Pour configurer et utiliser le fournisseur de SQL Server PowerShell, consultez [SQL Server PowerShell fournisseur](../../../powershell/sql-server-powershell-provider.md) et [obtenir de l’aide SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="30774-179">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md) and [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>
  
###  <a name="example-powershell"></a><a name="PSExample"></a> <span data-ttu-id="30774-180">Exemple (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="30774-180">Example (PowerShell)</span></span>  
 <span data-ttu-id="30774-181">L'exemple suivant configure le réplica principal et un réplica secondaire dans un groupe de disponibilité pour le routage en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="30774-181">The following example configures the primary replica and one secondary replica in an availability group for read-only routing.</span></span> <span data-ttu-id="30774-182">D'abord, l'exemple affecte une URL de routage en lecture seule à chaque réplica.</span><span class="sxs-lookup"><span data-stu-id="30774-182">First, the example assigns a read-only routing URL to each replica.</span></span> <span data-ttu-id="30774-183">Il définit ensuite la liste de routage en lecture seule sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="30774-183">Then it sets the read-only routing list on the primary replica.</span></span> <span data-ttu-id="30774-184">Les connexions avec la propriété « ReadOnly » définie dans la chaîne de connexion sont redirigées vers le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="30774-184">Connections with the "ReadOnly" property set in the connection string will be redirected to the secondary replica.</span></span> <span data-ttu-id="30774-185">Si ce réplica secondaire n'est pas accessible en lecture (comme déterminé par le paramètre `ConnectionModeInSecondaryRole`), la connexion sera renvoyée vers le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="30774-185">If this secondary replica is not readable (as determined by the `ConnectionModeInSecondaryRole` setting), the connection will be directed back to the primary replica.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  
$secondaryReplica = Get-Item "AvailabilityReplicas\SecondaryServer"  
  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://PrimaryServer.domain.com:1433" -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://SecondaryServer.domain.com:1433" -InputObject $secondaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingList "SecondaryServer","PrimaryServer" -InputObject $primaryReplica  
```  
  
##  <a name="follow-up-after-configuring-read-only-routing"></a><a name="FollowUp"></a> <span data-ttu-id="30774-186">Suivi : après la configuration du routage en lecture seule</span><span class="sxs-lookup"><span data-stu-id="30774-186">Follow Up: After Configuring Read-Only Routing</span></span>  
 <span data-ttu-id="30774-187">Une fois le réplica principal actuel et les réplicas secondaires lisibles configurés pour prendre en charge le routage en lecture seule dans les deux rôles, les réplicas secondaires lisibles peuvent recevoir des demandes de connexion d'intention de lecture des clients qui se connectent via l'écouteur du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="30774-187">Once the current primary replica and the readable secondary replicas are configured to support read-only routing in both roles, the readable secondary replicas can receive read read-intent connection requests from clients that connect via the availability group listener.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="30774-188">Lorsque vous utilisez l' [utilitaire bcp](../../../tools/bcp-utility.md) ou l' [utilitaire sqlcmd](../../../tools/sqlcmd-utility.md), vous pouvez spécifier l’accès en lecture seule à n’importe quel réplica secondaire qui est activé pour l’accès en lecture seule en spécifiant le `-K ReadOnly` commutateur.</span><span class="sxs-lookup"><span data-stu-id="30774-188">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
###  <a name="requirements-and-recommendations-for-client-connection-strings"></a><a name="ConnStringReqsRecs"></a> <span data-ttu-id="30774-189">Exigences et recommandations pour les chaînes de connexion clientes</span><span class="sxs-lookup"><span data-stu-id="30774-189">Requirements and Recommendations for Client Connection-Strings</span></span>  
 <span data-ttu-id="30774-190">Pour qu'une application cliente utilise le routage en lecture seule, sa chaîne de connexion doit respecter les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="30774-190">For a client application to use read-only routing, its connection string must satisfy the following requirements:</span></span>  
  
-   <span data-ttu-id="30774-191">Utiliser le protocole TCP.</span><span class="sxs-lookup"><span data-stu-id="30774-191">Use the TCP protocol.</span></span>  
  
-   <span data-ttu-id="30774-192">Définir l'attribut/propriété d'intention de l'application en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="30774-192">Set the application intent attribute/property to readonly.</span></span>  
  
-   <span data-ttu-id="30774-193">Référencer l'écouteur d'un groupe de disponibilité qui est configuré pour prendre en charge le routage en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="30774-193">Reference the listener of an availability group that is configured to support read-only routing.</span></span>  
  
-   <span data-ttu-id="30774-194">Référencer une base de données dans ce groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="30774-194">Reference a database in that availability group.</span></span>  
  
 <span data-ttu-id="30774-195">En outre, nous recommandons que les chaînes de connexion autorisent le basculement de sous-réseaux multiples, ce qui permet de prendre en charge un thread client parallèle pour chaque réplica sur chaque sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="30774-195">In addition, we recommend that connection strings enable multi-subnet failover, which supports a parallel client thread for each replica on each subnet.</span></span> <span data-ttu-id="30774-196">Cela réduit le temps de reconnexion du client après un basculement.</span><span class="sxs-lookup"><span data-stu-id="30774-196">This minimizes client reconnection time after a failover.</span></span>  
  
 <span data-ttu-id="30774-197">La syntaxe d'une chaîne de connexion dépend du fournisseur SQL Server utilisé par l'application.</span><span class="sxs-lookup"><span data-stu-id="30774-197">The syntax for a connection string depends on the SQL Server provider an application is using.</span></span> <span data-ttu-id="30774-198">L'exemple de chaîne de connexion suivant pour le fournisseur de données .NET Framework Data Provider 4.0.2 pour SQL Server illustre les parties d'une chaîne de connexion requises et recommandées pour utiliser le routage en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="30774-198">The following example connection string for the .NET Framework Data Provider 4.0.2 for SQL Server illustrates the parts of a connection string that are required and recommended to work for read-only routing.</span></span>  
  
```  
Server=tcp:MyAgListener,1433;Database=Db1;IntegratedSecurity=SSPI;ApplicationIntent=ReadOnly;MultiSubnetFailover=True  
```  
  
 <span data-ttu-id="30774-199">Pour plus d’informations sur l’intention de l’application en lecture seule et le routage en lecture seule, consultez [Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="30774-199">For more information about read-only application intent and read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
### <a name="if-read-only-routing-is-not-working-correctly"></a><span data-ttu-id="30774-200">Si le routage en lecture seule ne fonctionne pas correctement</span><span class="sxs-lookup"><span data-stu-id="30774-200">If Read-Only Routing is Not Working Correctly</span></span>  
 <span data-ttu-id="30774-201">Pour plus d’informations sur la résolution des problèmes liés à la configuration du routage en lecture seule, consultez [Le routage en lecture seule ne fonctionne pas correctement](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30774-201">For information about troubleshooting a read-only routing configuration, see [Read-Only Routing is Not Working Correctly](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="30774-202">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="30774-202">Related Tasks</span></span>  

### <a name="to-view-read-only-routing-configurations"></a><span data-ttu-id="30774-203">Pour consulter les configurations de routage en lecture seule</span><span class="sxs-lookup"><span data-stu-id="30774-203">To view read-only routing configurations</span></span>
  
-   [<span data-ttu-id="30774-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="30774-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
  
-   <span data-ttu-id="30774-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (colonne **read_only_routing_url**)</span><span class="sxs-lookup"><span data-stu-id="30774-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (**read_only_routing_url** column)</span></span>  
  
### <a name="to-configure-client-connection-access"></a><span data-ttu-id="30774-206">Pour configurer l'accès à la connexion du client</span><span class="sxs-lookup"><span data-stu-id="30774-206">To configure client connection access</span></span>
  
-   [<span data-ttu-id="30774-207">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="30774-207">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="30774-208">Configurer l’accès en lecture seule sur un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="30774-208">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
### <a name="to-use-connection-strings-in-applications"></a><span data-ttu-id="30774-209">Pour utiliser les chaînes de connexion dans des applications</span><span class="sxs-lookup"><span data-stu-id="30774-209">To use connection strings in applications</span></span>
  
-   [<span data-ttu-id="30774-210">Prise en charge des fonctionnalités de récupération d'urgence, haute disponibilité par SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="30774-210">SQL Server Native Client Support for High Availability, Disaster Recovery</span></span>](../../../relational-databases/native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md)  
  
-   [<span data-ttu-id="30774-211">Utilisation de mots clés de chaîne de connexion avec SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="30774-211">Using Connection String Keywords with SQL Server Native Client</span></span>](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="30774-212">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="30774-212">Related Content</span></span>  
  
-   <span data-ttu-id="30774-213">**Blogs :**</span><span class="sxs-lookup"><span data-stu-id="30774-213">**Blogs:**</span></span>  
  
     [<span data-ttu-id="30774-214">Calcul de l'URL de routage en lecture seule pour AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="30774-214">Calculating read_only_routing_url for AlwaysOn</span></span>](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson)  
  
     [<span data-ttu-id="30774-215">Blogs de l'équipe de SQL Server AlwaysOn : Blog officiel de l'équipe de SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="30774-215">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="30774-216">Blogs des ingénieurs du Service clientèle et du Support technique de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30774-216">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="30774-217">**Livres blancs :**</span><span class="sxs-lookup"><span data-stu-id="30774-217">**White papers:**</span></span>  
  
     [<span data-ttu-id="30774-218">Livres blancs de Microsoft pour SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="30774-218">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="30774-219">Livres blancs de l'équipe de consultants clients de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30774-219">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="30774-220">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="30774-220">See Also</span></span>  
 <span data-ttu-id="30774-221">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30774-221">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="30774-222">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30774-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="30774-223">[Secondaires actifs : réplicas secondaires accessibles en lecture (groupes de disponibilité AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="30774-223">[Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 <span data-ttu-id="30774-224">[À propos de l’accès de la connexion client aux réplicas de disponibilité &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="30774-224">[About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span></span>  
 [<span data-ttu-id="30774-225">Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="30774-225">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
