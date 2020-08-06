---
title: Configurer le moteur de base de données de manière à écouter sur plusieurs ports TCP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- ports [SQL Server], multiple
- TDS
- listen on multiple ports
- endpoints [SQL Server], TDS
- adding ports
- tabular data stream
- multiple ports
ms.assetid: 8e955033-06ef-403f-b813-3d8241b62f1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab803bcaa5ab6b6187c1a994abef02f81ae105c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601690"
---
# <a name="configure-the-database-engine-to-listen-on-multiple-tcp-ports"></a><span data-ttu-id="fcede-102">Configurer le moteur de base de données de manière à écouter sur plusieurs ports TCP</span><span class="sxs-lookup"><span data-stu-id="fcede-102">Configure the Database Engine to Listen on Multiple TCP Ports</span></span>
  <span data-ttu-id="fcede-103">Cette rubrique explique comment configurer le [!INCLUDE[ssDE](../../includes/ssde-md.md)] pour écouter sur plusieurs ports TCP dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide du Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fcede-103">This topic describes how to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on multiple TCP ports in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="fcede-104">Lorsque TCP/IP est activé pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le [!INCLUDE[ssDE](../../includes/ssde-md.md)] écoute les connexions entrantes sur un point de connexion composé d'une adresse IP et d'un numéro de port TCP. Les procédures suivantes créent un point de terminaison TDS (Tabular Data Stream, flux de données tabulaires), afin que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] écoute sur un port TCP supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="fcede-104">When TCP/IP is enabled for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will listen for incoming connections on a connection point consisting of an IP address and TCP port number.The following procedures create a tabular data stream (TDS) endpoint, so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will listen on an additional TCP port.</span></span>  
  
 <span data-ttu-id="fcede-105">Les raisons pouvant conduire à créer un second point de terminaison TDS sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fcede-105">Possible reasons to create a second TDS endpoint include:</span></span>  
  
-   <span data-ttu-id="fcede-106">Renforcement de la sécurité en configurant le pare-feu de manière à restreindre l'accès au point de terminaison par défaut aux ordinateurs clients locaux appartenant à un sous-réseau spécifique.</span><span class="sxs-lookup"><span data-stu-id="fcede-106">Increase security by configuring the firewall to restrict access to the default endpoint to local client computers on a specific subnet.</span></span> <span data-ttu-id="fcede-107">Conservez l'accès Internet à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour l'équipe de support technique en créant un nouveau point de terminaison que le pare-feu expose à Internet et en limitant les droits de connexion à ce point de terminaison à l'équipe de support technique.</span><span class="sxs-lookup"><span data-stu-id="fcede-107">Maintain Internet access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for your support team by creating a new endpoint that the firewall exposes to the Internet, and restricting connection rights to this endpoint to your server support team.</span></span>  
  
-   <span data-ttu-id="fcede-108">Affinage des connexions sur des processeurs spécifiques lors de l'utilisation d'un accès NUMA (Non-Uniform Memory Access).</span><span class="sxs-lookup"><span data-stu-id="fcede-108">Affinitizing connections to specific processors when using Non-Uniform Memory Access (NUMA).</span></span>  
  
 <span data-ttu-id="fcede-109">La configuration d'un point de terminaison TDS comprend les étapes suivantes, que vous pouvez réaliser dans l'ordre de votre choix :</span><span class="sxs-lookup"><span data-stu-id="fcede-109">Configuring a TDS endpoint consists of the following steps, which can be done in any order:</span></span>  
  
-   <span data-ttu-id="fcede-110">Créer le point de terminaison TDS du port TCP et, le cas échéant, restaurer l'accès au point de terminaison par défaut.</span><span class="sxs-lookup"><span data-stu-id="fcede-110">Create the TDS endpoint for the TCP port, and restore access to the default endpoint if appropriate.</span></span>  
  
-   <span data-ttu-id="fcede-111">Accorder l'accès au point de terminaison aux principaux de serveur souhaités.</span><span class="sxs-lookup"><span data-stu-id="fcede-111">Grant access to the endpoint to the desired server principals.</span></span>  
  
-   <span data-ttu-id="fcede-112">Spécifier le numéro de port TCP de l'adresse IP sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fcede-112">Specify the TCP port number for the selected IP address.</span></span>  
  
 <span data-ttu-id="fcede-113">Pour plus d’informations sur les paramètres par défaut du Pare-feu Windows et pour obtenir une description des ports TCP qui affectent le moteur de base de données, Analysis Services, Reporting Services et Integration Services, consultez [Configurer le Pare-feu Windows pour autoriser l’accès à SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="fcede-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-create-a-tds-endpoint"></a><span data-ttu-id="fcede-114">Pour créer un point de terminaison TDS</span><span class="sxs-lookup"><span data-stu-id="fcede-114">To create a TDS endpoint</span></span>  
  
-   <span data-ttu-id="fcede-115">Émettez l'instruction suivante afin de créer un point de terminaison nommé **CustomConnection** pour le port 1500 pour toutes les adresses TCP disponibles sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="fcede-115">Issue the following statement to create an endpoint named **CustomConnection** for port 1500 for all available TCP addresses on the server.</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE ENDPOINT [CustomConnection]  
    STATE = STARTED  
    AS TCP  
       (LISTENER_PORT = 1500, LISTENER_IP =ALL)  
    FOR TSQL() ;  
    GO  
    ```  
  
 <span data-ttu-id="fcede-116">Lorsque vous créez un nouveau point de terminaison [!INCLUDE[tsql](../../includes/tsql-md.md)] , les autorisations de connexion de **public** sont révoquées pour le point de terminaison TDS par défaut.</span><span class="sxs-lookup"><span data-stu-id="fcede-116">When you create a new [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoint, connect permissions for **public** are revoked for the default TDS endpoint.</span></span> <span data-ttu-id="fcede-117">Si l'accès au groupe **public** est nécessaire pour le point de terminaison par défaut, réappliquez cette autorisation à l'aide de l'instruction `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` .</span><span class="sxs-lookup"><span data-stu-id="fcede-117">If access to the **public** group is needed for the default endpoint, reapply this permission by using the `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` statement.</span></span>  
  
#### <a name="to-grant-access-to-the-endpoint"></a><span data-ttu-id="fcede-118">Pour accorder l'accès au point de terminaison</span><span class="sxs-lookup"><span data-stu-id="fcede-118">To grant access to the endpoint</span></span>  
  
-   <span data-ttu-id="fcede-119">Émettez l'instruction suivante afin d'accorder l'accès au point de terminaison **CustomConnection** au groupe SQLSupport du domaine corp.</span><span class="sxs-lookup"><span data-stu-id="fcede-119">Issue the following statement to grant access to the **CustomConnection** endpoint to the SQLSupport group in the corp domain.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[CustomConnection] to [corp\SQLSupport] ;  
    GO  
    ```  
  
#### <a name="to-configure-the-sql-server-database-engine-to-listen-on-an-additional-tcp-port"></a><span data-ttu-id="fcede-120">Pour configurer le moteur de base de données SQL Server de manière à écouter sur un port TCP supplémentaire</span><span class="sxs-lookup"><span data-stu-id="fcede-120">To configure the SQL Server Database Engine to listen on an additional TCP port</span></span>  
  
1.  <span data-ttu-id="fcede-121">Dans le Gestionnaire de configuration SQL Server, développez **Configuration du réseau SQL Server**, puis cliquez sur **Protocoles pour** _<nom_instance>_ .</span><span class="sxs-lookup"><span data-stu-id="fcede-121">In SQL Server Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for**_<instance_name>_.</span></span>  
  
2.  <span data-ttu-id="fcede-122">Développez **Protocoles pour** _<nom_instance>_ , puis cliquez sur **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="fcede-122">Expand **Protocols for**_<instance_name>_, and then click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="fcede-123">Dans le volet droit, cliquez avec le bouton droit sur chaque adresse IP désactivée à activer, puis cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="fcede-123">In the right pane, right-click each disabled IP address that you want to enable, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="fcede-124">Cliquez avec le bouton droit sur **IPAll**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="fcede-124">Right-click **IPAll**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="fcede-125">Dans la zone **Port TCP** , tapez les ports sur lesquels le [!INCLUDE[ssDE](../../includes/ssde-md.md)] doit écouter, en les séparant par des virgules.</span><span class="sxs-lookup"><span data-stu-id="fcede-125">In the **TCP Port** box, type the ports that you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, separated by commas.</span></span> <span data-ttu-id="fcede-126">Dans notre exemple, si le port par défaut 1433 est listé, tapez `,1500` afin que la zone soit lue `1433,1500` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcede-126">In our example, if the default port 1433 is listed, type `,1500` so the box reads `1433,1500`, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcede-127">Si vous n'activez pas le port sur toutes les adresses IP, configurez le port supplémentaire dans la zone des propriétés pour uniquement l'adresse de votre choix.</span><span class="sxs-lookup"><span data-stu-id="fcede-127">If you are not enabling the port on all IP addresses, configure the additional port in the property box for only for the desired address.</span></span> <span data-ttu-id="fcede-128">Ensuite, dans le volet de la console, cliquez avec le bouton droit sur **TCP/IP**, cliquez sur **Propriétés**puis, dans la zone **Écouter tout** , sélectionnez **Non**.</span><span class="sxs-lookup"><span data-stu-id="fcede-128">Then, in the console pane, right-click **TCP/IP**, click **Properties**, and in the **Listen All** box, select **No**.</span></span>  
  
6.  <span data-ttu-id="fcede-129">Dans le volet gauche, cliquez sur **Services SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="fcede-129">In the left pane, click **SQL Server Services**.</span></span>  
  
7.  <span data-ttu-id="fcede-130">Dans le volet droit, cliquez avec le bouton droit sur **<nom_instance>** _SQL Server_, puis cliquez sur **Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="fcede-130">In the right pane, right-click **SQL Server**_<instance_name>_, and then click **Restart**.</span></span>  
  
     <span data-ttu-id="fcede-131">Lorsque le [!INCLUDE[ssDE](../../includes/ssde-md.md)] redémarre, le journal des erreurs répertorie les ports sur lesquels [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est à l'écoute.</span><span class="sxs-lookup"><span data-stu-id="fcede-131">When the [!INCLUDE[ssDE](../../includes/ssde-md.md)] restarts, the Error log will list the ports on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening.</span></span>  
  
#### <a name="to-connect-to-the-new-endpoint"></a><span data-ttu-id="fcede-132">Pour établir la connexion au nouveau point de terminaison</span><span class="sxs-lookup"><span data-stu-id="fcede-132">To connect to the new endpoint</span></span>  
  
-   <span data-ttu-id="fcede-133">Émettez l’instruction suivante pour vous connecter au point de terminaison **CustomConnection** de l’instance par défaut de SQL Server sur le serveur nommé ACCT, à l’aide d’une connexion approuvée et en supposant que l’utilisateur est membre du groupe [corp\SQLSupport].</span><span class="sxs-lookup"><span data-stu-id="fcede-133">Issue the following statement to connect to the **CustomConnection** endpoint of the default instance of SQL Server on the server named ACCT, using a trusted connection, and assuming the user is a member of the [corp\SQLSupport] group.</span></span>  
  
    ```  
    sqlcmd -SACCT,1500  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fcede-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcede-134">See Also</span></span>  
 <span data-ttu-id="fcede-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcede-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="fcede-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcede-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="fcede-137">[Autorisations GRANT sur point de terminaison &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcede-137">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="fcede-138">Mapper les ports TCP/IP aux nœuds NUMA &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fcede-138">Map TCP IP Ports to NUMA Nodes &#40;SQL Server&#41;</span></span>](map-tcp-ip-ports-to-numa-nodes-sql-server.md)  
  
  
