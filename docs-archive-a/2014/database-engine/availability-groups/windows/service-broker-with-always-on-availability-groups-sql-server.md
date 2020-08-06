---
title: Service Broker avec groupes de disponibilité AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 881c20e5-1c99-44eb-b393-09fc5ea0f122
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da179219363422c4ec242d29be61f35dd1609823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605734"
---
# <a name="service-broker-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="6bc58-102">Service Broker avec les groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6bc58-102">Service Broker with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="6bc58-103">Cette rubrique contient des informations sur la configuration de Service Broker afin d'utiliser [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bc58-103">This topic contains information about configuring Service Broker to work with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="6bc58-104">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="6bc58-104">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="6bc58-105">Conditions requises pour qu’un service d’un groupe de disponibilité reçoive des messages distants</span><span class="sxs-lookup"><span data-stu-id="6bc58-105">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>](#ReceiveRemoteMessages)  
  
-   [<span data-ttu-id="6bc58-106">Conditions requises pour l’envoi de messages à un service distant dans un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="6bc58-106">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>](#SendRemoteMessages)  
  
##  <a name="requirements-for-a-service-in-an-availability-group-to-receive-remote-messages"></a><a name="ReceiveRemoteMessages"></a> <span data-ttu-id="6bc58-107">Spécifications pour qu'un service dans un groupe de disponibilité reçoive les messages distants</span><span class="sxs-lookup"><span data-stu-id="6bc58-107">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>  
  
1.  <span data-ttu-id="6bc58-108">**Assurez-vous que le groupe de disponibilité possède un écouteur.**</span><span class="sxs-lookup"><span data-stu-id="6bc58-108">**Ensure that the availability group possesses a listener.**</span></span>  
  
     <span data-ttu-id="6bc58-109">Pour plus d'informations, consultez [Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6bc58-109">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="6bc58-110">**Vérifiez que le point de terminaison Service Broker existe et est configuré correctement.**</span><span class="sxs-lookup"><span data-stu-id="6bc58-110">**Ensure that the Service Broker endpoint exists and is correctly configured.**</span></span>  
  
     <span data-ttu-id="6bc58-111">Sur chaque instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge un réplica de disponibilité pour le groupe de disponibilité, configurez le point de terminaison Service Broker, comme suit :</span><span class="sxs-lookup"><span data-stu-id="6bc58-111">On every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica for the availability group, configure the Service Broker endpoint, as follows:</span></span>  
  
    -   <span data-ttu-id="6bc58-112">Définissez LISTENER_IP sur « ALL ».</span><span class="sxs-lookup"><span data-stu-id="6bc58-112">Set LISTENER_IP to 'ALL'.</span></span> <span data-ttu-id="6bc58-113">Ce paramètre permet les connexions à une adresse IP valide liée à l'écouteur du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6bc58-113">This setting enables connections on any valid IP address that is bound to the availability group listener.</span></span>  
  
    -   <span data-ttu-id="6bc58-114">Définissez le PORT de Service Broker sur le même numéro de port pour toutes les instances de serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="6bc58-114">Set the Service Broker PORT to the same port number on all the host server instances.</span></span>  
  
        > [!TIP]  
        >  <span data-ttu-id="6bc58-115">Pour afficher le numéro de port du point de terminaison Service Broker sur une instance de serveur donnée, interrogez la colonne **port** de l’affichage catalogue [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) , où **type_desc** = 'SERVICE_BROKER'.</span><span class="sxs-lookup"><span data-stu-id="6bc58-115">To view the port number of the Service Broker endpoint on a given server instance, query the **port** column of the [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) catalog view, where **type_desc** = 'SERVICE_BROKER'.</span></span>  
  
     <span data-ttu-id="6bc58-116">L'exemple suivant crée un point de terminaison Service Broker authentifié par Windows qui utilise le port par défaut de Service Broker (4022) et écoute toutes les adresses IP valides.</span><span class="sxs-lookup"><span data-stu-id="6bc58-116">The following example creates a Windows authenticated Service Broker endpoint that uses the default Service Broker port (4022) and listens to all valid IP addresses.</span></span>  
  
    ```  
    CREATE ENDPOINT [SSBEndpoint]  
        STATE = STARTED  
        AS TCP  (LISTENER_PORT = 4022, LISTENER_IP = ALL )  
        FOR SERVICE_BROKER (AUTHENTICATION = WINDOWS)  
    ```  
  
     <span data-ttu-id="6bc58-117">Pour plus d’informations, consultez [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6bc58-117">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
3.  <span data-ttu-id="6bc58-118">**Accordez l'autorisation CONNECT sur le point de terminaison.**</span><span class="sxs-lookup"><span data-stu-id="6bc58-118">**Grant CONNECT permission on the endpoint.**</span></span>  
  
     <span data-ttu-id="6bc58-119">Accordez l'autorisation CONNECT sur le point de terminaison Service Broker sur PUBLIC ou sur une connexion.</span><span class="sxs-lookup"><span data-stu-id="6bc58-119">Grant CONNECT permission on the Service Broker endpoint either to PUBLIC or to a login.</span></span>  
  
     <span data-ttu-id="6bc58-120">L'exemple suivant accorde la connexion sur un point de terminaison Service Broker nommé `broker_endpoint` sur PUBLIC.</span><span class="sxs-lookup"><span data-stu-id="6bc58-120">The following example grants the connection on a Service Broker endpoint named `broker_endpoint` to PUBLIC.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[broker_endpoint] TO [PUBLIC]  
    ```  
  
     <span data-ttu-id="6bc58-121">Pour plus d’informations, consultez [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6bc58-121">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span>  
  
4.  <span data-ttu-id="6bc58-122">**Vérifiez que msdb contient un itinéraire AutoCreatedLocal ou un itinéraire vers le service spécifique.**</span><span class="sxs-lookup"><span data-stu-id="6bc58-122">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6bc58-123">Chaque base de données utilisateur qui englobe **msdb**contient par défaut l'itinéraire **AutoCreatedLocal**.</span><span class="sxs-lookup"><span data-stu-id="6bc58-123">By default, each user database, including **msdb**, contains the route **AutoCreatedLocal**.</span></span> <span data-ttu-id="6bc58-124">Cet itinéraire, qui correspond à tous les noms de services et instances de broker, spécifie que le message doit être remis dans l'instance active.</span><span class="sxs-lookup"><span data-stu-id="6bc58-124">This route matches any service name and broker instance and specifies that the message should be delivered within the current instance.</span></span> <span data-ttu-id="6bc58-125">**AutoCreatedLocal** a une priorité plus faible que les itinéraires qui spécifient explicitement un service spécifique qui communique avec une instance distante.</span><span class="sxs-lookup"><span data-stu-id="6bc58-125">**AutoCreatedLocal** has lower priority than routes that explicitly specify a specific service that communicates with a remote instance.</span></span>  
  
     <span data-ttu-id="6bc58-126">Pour plus d’informations sur la création des itinéraires, consultez [Exemples de routage Service Broker](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (dans la version [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] de la documentation en ligne) et [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6bc58-126">For information about creating routes, see [Service Broker Routing Examples](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (in the [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] version of Books Online) and [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
##  <a name="requirements-for-sending-messages-to-a-remote-service-in-an-availability-group"></a><a name="SendRemoteMessages"></a> <span data-ttu-id="6bc58-127">Spécifications pour l'envoi de messages à un service distant dans un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="6bc58-127">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>  
  
1.  <span data-ttu-id="6bc58-128">**Créez un itinéraire vers le service cible.**</span><span class="sxs-lookup"><span data-stu-id="6bc58-128">**Create a route to the target service.**</span></span>  
  
     <span data-ttu-id="6bc58-129">Configurez l'itinéraire comme suit :</span><span class="sxs-lookup"><span data-stu-id="6bc58-129">Configure the route as follows:</span></span>  
  
    -   <span data-ttu-id="6bc58-130">Définissez ADDRESS sur l'adresse IP de l'écouteur du groupe de disponibilité qui héberge la base de données de service.</span><span class="sxs-lookup"><span data-stu-id="6bc58-130">Set ADDRESS to the listener IP address of availability group that hosts the service database.</span></span>  
  
    -   <span data-ttu-id="6bc58-131">Définissez PORT sur le port que vous avez spécifié dans le point de terminaison Service Broker de chacune des instances distantes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6bc58-131">Set PORT to the port that you specified in the Service Broker endpoint of each of the remote SQL Server instances.</span></span>  
  
     <span data-ttu-id="6bc58-132">L'exemple suivant crée un itinéraire nommé `RouteToTargetService` pour le service `ISBNLookupRequestService` .</span><span class="sxs-lookup"><span data-stu-id="6bc58-132">The following example creates a route named `RouteToTargetService` for the `ISBNLookupRequestService` service.</span></span> <span data-ttu-id="6bc58-133">L'itinéraire cible l'écouteur du groupe de disponibilité, `MyAgListener`, qui utilise le port 4022.</span><span class="sxs-lookup"><span data-stu-id="6bc58-133">The route targets the availability group listener, `MyAgListener`, which uses port 4022.</span></span>  
  
    ```  
    CREATE ROUTE [RouteToTargetService] WITH   
    SERVICE_NAME = 'ISBNLookupRequestService',   
    ADDRESS = 'TCP://MyAgListener:4022';  
  
    ```  
  
     <span data-ttu-id="6bc58-134">Pour plus d’informations, consultez [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6bc58-134">For more information, see [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
2.  <span data-ttu-id="6bc58-135">**Vérifiez que msdb contient un itinéraire AutoCreatedLocal ou un itinéraire vers le service spécifique.**</span><span class="sxs-lookup"><span data-stu-id="6bc58-135">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span> <span data-ttu-id="6bc58-136">(Pour plus d’informations, consultez [Spécifications pour qu’un service dans un groupe de disponibilité reçoive les messages distants](#ReceiveRemoteMessages), plus haut dans cette rubrique.)</span><span class="sxs-lookup"><span data-stu-id="6bc58-136">(For more information, see [Requirements for a Service in an Availability Group to Receive Remote Messages](#ReceiveRemoteMessages), earlier in this topic.)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6bc58-137">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="6bc58-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6bc58-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6bc58-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
  
-   [<span data-ttu-id="6bc58-139">CREATE ROUTE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6bc58-139">CREATE ROUTE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-route-transact-sql)  
  
-   [<span data-ttu-id="6bc58-140">GRANT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6bc58-140">GRANT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-transact-sql)  
  
-   <span data-ttu-id="6bc58-141">[Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6bc58-141">[Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="6bc58-142">Création et configuration des groupes de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6bc58-142">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="6bc58-143">Configurer des comptes de connexion pour la mise en miroir de bases de données ou groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6bc58-143">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
## <a name="see-also"></a><span data-ttu-id="6bc58-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6bc58-144">See Also</span></span>  
 <span data-ttu-id="6bc58-145">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6bc58-145">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="6bc58-146">[Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="6bc58-146">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="6bc58-147">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="6bc58-147">SQL Server Service Broker</span></span>](../../configure-windows/sql-server-service-broker.md)  
  
  
