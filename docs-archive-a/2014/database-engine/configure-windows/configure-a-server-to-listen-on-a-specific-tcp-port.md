---
title: Configurer un serveur pour l’écoute sur un port TCP spécifique (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fixed port
- static ports
- ports [SQL Server], assigning numbers
- assigning port numbers
- dynamic ports [SQL Server]
- TCP/IP [SQL Server], port numbers
ms.assetid: 2276a5ed-ae3f-4855-96d8-f5bf01890640
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb740910c65580e8ea3170d03481e6cb628860
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601101"
---
# <a name="configure-a-server-to-listen-on-a-specific-tcp-port-sql-server-configuration-manager"></a><span data-ttu-id="f22bd-102">Configurer un serveur pour écouter un port TCP spécifique (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f22bd-102">Configure a Server to Listen on a Specific TCP Port (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="f22bd-103">Cette rubrique explique comment configurer une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] pour l'écoute sur un port fixe spécifique à l'aide du Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f22bd-103">This topic describes how to configure an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] to listen on a specific fixed port by using the SQL Server Configuration Manager.</span></span> <span data-ttu-id="f22bd-104">Si elle est activée, l’instance par défaut du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] écoute le port TCP 1433.</span><span class="sxs-lookup"><span data-stu-id="f22bd-104">If enabled, the default instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on TCP port 1433.</span></span> <span data-ttu-id="f22bd-105">Les instances nommées du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et de [!INCLUDE[ssEW](../../includes/ssew-md.md)] sont configurées pour des ports dynamiques.</span><span class="sxs-lookup"><span data-stu-id="f22bd-105">Named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] are configured for dynamic ports.</span></span> <span data-ttu-id="f22bd-106">Cela signifie qu'elles sélectionnent un port disponible lorsque le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est démarré.</span><span class="sxs-lookup"><span data-stu-id="f22bd-106">This means they select an available port when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service is started.</span></span> <span data-ttu-id="f22bd-107">Lorsque vous vous connectez à une instance nommée par l'intermédiaire d'un pare-feu, configurez le [!INCLUDE[ssDE](../../includes/ssde-md.md)] pour écouter un port spécifique, de façon à pouvoir ouvrir le port approprié dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="f22bd-107">When you are connecting to a named instance through a firewall, configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on a specific port, so that the appropriate port can be opened in the firewall.</span></span>  
  
 <span data-ttu-id="f22bd-108">Pour plus d’informations sur les paramètres par défaut du Pare-feu Windows et pour obtenir une description des ports TCP qui affectent le moteur de base de données, Analysis Services, Reporting Services et Integration Services, consultez [Configurer le Pare-feu Windows pour autoriser l’accès à SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="f22bd-108">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="f22bd-109">Lors de la sélection du numéro de port, consultez [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) pour obtenir la liste des numéros de ports attribués aux applications spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f22bd-109">When selecting a port number, consult [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) for a list of port numbers that are assigned to specific applications.</span></span> <span data-ttu-id="f22bd-110">sélectionnez un numéro de port non assigné.</span><span class="sxs-lookup"><span data-stu-id="f22bd-110">Select an unassigned port number.</span></span> <span data-ttu-id="f22bd-111">Pour plus d’informations, consultez [La plage de port dynamique par défaut pour le protocole TCP/IP a changé dans Windows Vista et dans Windows Server 2008](https://support.microsoft.com/kb/929851).</span><span class="sxs-lookup"><span data-stu-id="f22bd-111">For more information, see [The default dynamic port range for TCP/IP has changed in Windows Vista and in Windows Server 2008](https://support.microsoft.com/kb/929851).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="f22bd-112">Le moteur de base de données commence l'écoute sur un nouveau port une fois redémarré.</span><span class="sxs-lookup"><span data-stu-id="f22bd-112">The Database Engine begins listening on a new port when restarted.</span></span> <span data-ttu-id="f22bd-113">Toutefois le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser surveille le Registre et signale le nouveau numéro de port dès que la configuration est modifiée, même si le moteur de base de données ne l'utilise pas.</span><span class="sxs-lookup"><span data-stu-id="f22bd-113">However the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service monitors the registry and reports the new port number as soon as the configuration is changed, even though the Database Engine might not be using it.</span></span> <span data-ttu-id="f22bd-114">Redémarrez le moteur de base de données pour assurer la cohérence et éviter les échecs de connexion.</span><span class="sxs-lookup"><span data-stu-id="f22bd-114">Restart the Database Engine to ensure consistency and avoid connection failures.</span></span>  
  
 <span data-ttu-id="f22bd-115">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f22bd-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f22bd-116">**Pour configurer un serveur pour l'écoute sur un port TCP spécifique, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="f22bd-116">**To configure a server to listen on a specific TCP port, using:**</span></span>  
  
     [<span data-ttu-id="f22bd-117">Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="f22bd-117">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f22bd-118">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="f22bd-118">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-assign-a-tcpip-port-number-to-the-sql-server-database-engine"></a><span data-ttu-id="f22bd-119">Pour affecter un numéro de port TCP/IP au moteur de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="f22bd-119">To assign a TCP/IP port number to the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="f22bd-120">Dans le Gestionnaire de configuration SQL Server, dans le volet de la console, développez **Configuration du réseau SQL Server**, **Protocoles pour \<instance name>** , puis double-cliquez sur **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="f22bd-120">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, expand **Protocols for \<instance name>**, and then double-click **TCP/IP**.</span></span>  
  
2.  <span data-ttu-id="f22bd-121">Dans la boîte de dialogue **Propriétés TCP/IP** , sous l’onglet **Adresses IP** , plusieurs adresses IP apparaissent au format **IP1**, **IP2**, jusqu’à **IPAll**.</span><span class="sxs-lookup"><span data-stu-id="f22bd-121">In the **TCP/IP Properties** dialog box, on the **IP Addresses** tab, several IP addresses appear in the format **IP1**, **IP2**, up to **IPAll**.</span></span> <span data-ttu-id="f22bd-122">Une de ces adresses correspond à l'adresse IP de la carte de bouclage, 127.0.0.1.</span><span class="sxs-lookup"><span data-stu-id="f22bd-122">One of these is for the IP address of the loopback adapter, 127.0.0.1.</span></span> <span data-ttu-id="f22bd-123">D'autres adresses sont affichées pour chaque adresse IP sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f22bd-123">Additional IP addresses appear for each IP Address on the computer.</span></span> <span data-ttu-id="f22bd-124">Cliquez avec le bouton droit sur chaque adresse, puis cliquez sur **Propriétés** pour identifier l’adresse IP que vous voulez configurer.</span><span class="sxs-lookup"><span data-stu-id="f22bd-124">Right-click each address, and then click **Properties** to identify the IP address that you want to configure.</span></span>  
  
3.  <span data-ttu-id="f22bd-125">Si la boîte de dialogue **Ports TCP dynamiques** contient **0**pour indiquer que [!INCLUDE[ssDE](../../includes/ssde-md.md)] écoute les ports dynamiques, supprimez le 0.</span><span class="sxs-lookup"><span data-stu-id="f22bd-125">If the **TCP Dynamic Ports** dialog box contains **0**, indicating the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is listening on dynamic ports, delete the 0.</span></span>  
  
4.  <span data-ttu-id="f22bd-126">Dans **Propriétés** _IP_**n**, dans la zone **Port TCP**, tapez le numéro du port sur lequel vous voulez que cette adresse IP écoute, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f22bd-126">In the **IP**_n_ **Properties** area box, in the **TCP Port** box, type the port number you want this IP address to listen on, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="f22bd-127">Dans le volet de la console, cliquez sur **Services SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f22bd-127">In the console pane, click **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="f22bd-128">Dans le volet d’informations, cliquez avec le bouton droit sur **SQL Server (** \<instance name> **)** , puis cliquez sur **Redémarrer** pour arrêter et redémarrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f22bd-128">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f22bd-129">Après avoir configuré [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour écouter un port spécifique, il existe trois manières de vous connecter à un port spécifique avec une application cliente :</span><span class="sxs-lookup"><span data-stu-id="f22bd-129">After you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on a specific port, there are three ways to connect to a specific port with a client application:</span></span>  
  
-   <span data-ttu-id="f22bd-130">Exécutez le service Explorateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur le serveur à connecter à l'instance [!INCLUDE[ssDE](../../includes/ssde-md.md)] par le nom.</span><span class="sxs-lookup"><span data-stu-id="f22bd-130">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance by name.</span></span>  
  
-   <span data-ttu-id="f22bd-131">Créez un alias sur le client, en spécifiant le numéro du port.</span><span class="sxs-lookup"><span data-stu-id="f22bd-131">Create an alias on the client, specifying the port number.</span></span>  
  
-   <span data-ttu-id="f22bd-132">Programmer le client pour une connexion à l'aide d'une chaîne de connexion personnalisée.</span><span class="sxs-lookup"><span data-stu-id="f22bd-132">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22bd-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f22bd-133">See Also</span></span>  
 [<span data-ttu-id="f22bd-134">Créer ou supprimer un alias de serveur devant être utilisé par un client &#40;Gestionnaire de configuration SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f22bd-134">Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;</span></span>](create-or-delete-a-server-alias-for-use-by-a-client.md)  
  
  
