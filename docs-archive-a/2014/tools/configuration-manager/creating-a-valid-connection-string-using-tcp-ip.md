---
title: Création d’une chaîne de connexion valide avec TCP/IP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine]
- ports [SQL Server], connecting to
- TCP/IP [SQL Server], connection strings
- connection strings [Database Engine], TCP/IP
- aliases [SQL Server], TCP/IP
ms.assetid: ee5dbc2c-1fc6-42bd-bdf5-efa792557934
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f761fa86ec4ed09c13bf4807489754c10b979ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604791"
---
# <a name="creating-a-valid-connection-string-using-tcp-ip"></a><span data-ttu-id="db565-102">Création d’une chaîne de connexion valide à l’aide du protocole TCP/IP</span><span class="sxs-lookup"><span data-stu-id="db565-102">Creating a Valid Connection String Using TCP IP</span></span>
  <span data-ttu-id="db565-103">Pour créer une chaîne de connexion valide à l'aide du protocole TCP/IP, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="db565-103">To create a valid connection string using TCP/IP, you must:</span></span>  
  
-   <span data-ttu-id="db565-104">Spécifiez un **nom de l'alias**.</span><span class="sxs-lookup"><span data-stu-id="db565-104">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="db565-105">Pour **Serveur**, entrez le nom d’un serveur auquel vous pouvez vous connecter à l’aide de l’utilitaire **PING** , ou une adresse IP à laquelle vous pouvez vous connecter au moyen de l’utilitaire **PING** .</span><span class="sxs-lookup"><span data-stu-id="db565-105">For the **Server**, enter either a server name to which you can connect using the **PING** utility, or an IP address to which you can connect using the **PING** utility.</span></span> <span data-ttu-id="db565-106">Pour une instance nommée, ajoutez le nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="db565-106">For a named instance append the instance name.</span></span>  
  
-   <span data-ttu-id="db565-107">Spécifiez **TCP/IP** comme **Protocole**.</span><span class="sxs-lookup"><span data-stu-id="db565-107">Specify **TCP/IP** for the **Protocol**.</span></span>  
  
-   <span data-ttu-id="db565-108">Vous pouvez éventuellement entrer un numéro de port dans **Numéro de port**.</span><span class="sxs-lookup"><span data-stu-id="db565-108">Optionally, enter a port number for the **Port No**.</span></span> <span data-ttu-id="db565-109">La valeur par défaut est 1433 ; il s'agit du numéro de port de l'instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)] sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="db565-109">The default is 1433, which is the port number of the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a server.</span></span> <span data-ttu-id="db565-110">Pour vous connecter à une instance nommée ou à une instance par défaut qui n'est pas à l'écoute sur le port 1433, vous devez spécifier le numéro de port ou démarrer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="db565-110">To connect to a named instance or a default instance that is not listening on port 1433, you must provide the port number, or start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span> <span data-ttu-id="db565-111">Pour plus d’informations sur la configuration du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser, consultez [Service SQL Server Browser](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="db565-111">For information on configuring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service, see [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="db565-112">Au moment de la connexion, le composant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client lit dans le Registre les valeurs de serveur, protocole et port pour le nom d'alias spécifié, et crée une chaîne de connexion au format `tcp:<servername>[\<instancename>],<port>` ou `tcp:<IPAddress>[\<instancename>],<port>`.</span><span class="sxs-lookup"><span data-stu-id="db565-112">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and port values from the registry for the specified alias name, and creates a connection string in the format `tcp:<servername>[\<instancename>],<port>` or `tcp:<IPAddress>[\<instancename>],<port>`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db565-113">Le pare-feu [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows ferme le port 1433 par défaut.</span><span class="sxs-lookup"><span data-stu-id="db565-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 1433 by default.</span></span> <span data-ttu-id="db565-114">Sachant que [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communique via le port 1433, vous devez rouvrir ce port si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configuré pour être à l’écoute des connexions clientes entrantes utilisant TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="db565-114">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 1433, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using TCP/IP.</span></span> <span data-ttu-id="db565-115">Pour plus d'informations sur la configuration d'un pare-feu, consultez « Procédure : configurer un pare-feu pour accéder à SQL Server » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou passez en revue la documentation de votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="db565-115">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="db565-116">et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prennent intégralement en charge IPv4 (Internet Protocol version 4) et IPv6 (Internet Protocol version 6).</span><span class="sxs-lookup"><span data-stu-id="db565-116">and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fully support both Internet Protocol version 4 (IPv4) and Internet Protocol version 6 (IPv6).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="db565-117">accepte les deux formats IPv4 et IPv6 pour les adresses IP.</span><span class="sxs-lookup"><span data-stu-id="db565-117">Configuration Manager accepts both IPv4 and IPv6 formats for IP addresses.</span></span> <span data-ttu-id="db565-118">Pour plus d'informations sur IPv6, consultez « Connexion avec IPv6 » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db565-118">For information on IPv6, see "Connecting Using IPv6" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="db565-119">Connexion au serveur local</span><span class="sxs-lookup"><span data-stu-id="db565-119">Connecting to the Local Server</span></span>  
 <span data-ttu-id="db565-120">Lorsque vous vous connectez à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alors que celui-ci est exécuté sur le même ordinateur que l'ordinateur client, vous pouvez utiliser `(local)` comme nom de serveur.</span><span class="sxs-lookup"><span data-stu-id="db565-120">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)` as the server name.</span></span> <span data-ttu-id="db565-121">Cette option n'est pas conseillée dans la mesure où elle est source d'ambiguïté ; toutefois, elle peut s'avérer utile lorsqu'il est certain que le client s'exécute sur l'ordinateur visé.</span><span class="sxs-lookup"><span data-stu-id="db565-121">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="db565-122">Par exemple, lorsque vous créez une application destinée à des utilisateurs itinérants déconnectés, tels que des vendeurs, pour lesquels [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute sur des ordinateurs portables et stocke les données de projet, un client établissant une connexion à `(local)` se connecte toujours à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cours d'exécution sur l'ordinateur portable.</span><span class="sxs-lookup"><span data-stu-id="db565-122">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to `(local)` would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="db565-123">Vous pouvez utiliser le mot `localhost` ou un point ( **.** ) à la place de `(local)`.</span><span class="sxs-lookup"><span data-stu-id="db565-123">The word `localhost` or a period (**.**) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="db565-124">Vérification de votre protocole de connexion</span><span class="sxs-lookup"><span data-stu-id="db565-124">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="db565-125">La requête suivante retourne le protocole utilisé pour la connexion active.</span><span class="sxs-lookup"><span data-stu-id="db565-125">The following query returns the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="db565-126">Exemples</span><span class="sxs-lookup"><span data-stu-id="db565-126">Examples</span></span>  
 <span data-ttu-id="db565-127">Connexion à partir du nom de serveur :</span><span class="sxs-lookup"><span data-stu-id="db565-127">Connecting by server name:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="db565-128">Connexion à une instance nommée à partir du nom de serveur :</span><span class="sxs-lookup"><span data-stu-id="db565-128">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>\<instancename>  
  
```  
  
 <span data-ttu-id="db565-129">Connexion à un port spécifié à partir du nom de serveur :</span><span class="sxs-lookup"><span data-stu-id="db565-129">Connecting by server name to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="db565-130">Connexion par l'adresse IP :</span><span class="sxs-lookup"><span data-stu-id="db565-130">Connecting by IP address:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="db565-131">Connexion par l'adresse IP à une instance nommée :</span><span class="sxs-lookup"><span data-stu-id="db565-131">Connecting by IP address to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>\<instancename>  
  
```  
  
 <span data-ttu-id="db565-132">Connexion par l'adresse IP à un port spécifié :</span><span class="sxs-lookup"><span data-stu-id="db565-132">Connecting by IP address to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port number>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="db565-133">Connexion à l'ordinateur local à l'aide du paramètre `(local)`:</span><span class="sxs-lookup"><span data-stu-id="db565-133">Connecting to the local computer using `(local)`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             (local)  
  
```  
  
 <span data-ttu-id="db565-134">Connexion à l'ordinateur local à l'aide du paramètre `localhost`:</span><span class="sxs-lookup"><span data-stu-id="db565-134">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost  
  
```  
  
 <span data-ttu-id="db565-135">Connexion à une instance nommée sur l'ordinateur local `localhost`:</span><span class="sxs-lookup"><span data-stu-id="db565-135">Connecting to a named instance on the local computer `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost\<instancename>  
  
```  
  
 <span data-ttu-id="db565-136">Connexion à l'ordinateur local à l'aide d'un point :</span><span class="sxs-lookup"><span data-stu-id="db565-136">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .  
  
```  
  
 <span data-ttu-id="db565-137">Connexion à une instance nommée sur l'ordinateur local à l'aide d'un point :</span><span class="sxs-lookup"><span data-stu-id="db565-137">Connecting to a named instance on the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .\<instancename>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="db565-138">Pour plus d’informations sur la spécification du protocole réseau en tant que paramètre **sqlcmd** , consultez « Procédure : établir une connexion au moteur de base de données à l’aide de sqlcmd.exe » dans la documentation en ligne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db565-138">For information on specifying the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db565-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db565-139">See Also</span></span>  
 <span data-ttu-id="db565-140">[Création d'une chaîne de connexion valide à l'aide du protocole de mémoire partagée](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="db565-140">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="db565-141">[Création d’une chaîne de connexion valide avec des canaux nommés](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="db565-141">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="db565-142">Choix d’un protocole réseau</span><span class="sxs-lookup"><span data-stu-id="db565-142">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
