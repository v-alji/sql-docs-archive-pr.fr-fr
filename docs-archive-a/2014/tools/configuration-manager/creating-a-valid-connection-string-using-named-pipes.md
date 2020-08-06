---
title: Création d’une chaîne de connexion valide à l’aide de canaux nommés | Microsoft Docs
description: Découvrez comment créer une chaîne de connexion valide lors de l’utilisation du protocole canaux nommés pour vous connecter à une instance de SQL Server. Affichez des exemples de noms de canaux valides.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], named pipes
- pipes [SQL Server]
- pipes [SQL Server], connecting to
- aliases [SQL Server], named pipes
- Named Pipes [SQL Server], connection strings
ms.assetid: 90930ff2-143b-4651-8ae3-297103600e4f
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f3e1d01e9e5b7b1d1c0d1bb822bf233ceee636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604793"
---
# <a name="creating-a-valid-connection-string-using-named-pipes"></a><span data-ttu-id="10ca4-104">Création d'une chaîne de connexion valide à l'aide de canaux nommés</span><span class="sxs-lookup"><span data-stu-id="10ca4-104">Creating a Valid Connection String Using Named Pipes</span></span>
  <span data-ttu-id="10ca4-105">Sauf modification par l’utilisateur, lorsque l’instance par défaut de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] écoute le protocole des canaux nommés, elle utilise `\\.\pipe\sql\query` comme nom de canal.</span><span class="sxs-lookup"><span data-stu-id="10ca4-105">Unless changed by the user, when the default instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on the named pipes protocol, it uses `\\.\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="10ca4-106">Le point indique que l’ordinateur est l’ordinateur local, `pipe` indique que la connexion est un canal nommé et `sql\query` est le nom du canal.</span><span class="sxs-lookup"><span data-stu-id="10ca4-106">The period indicates that the computer is the local computer, `pipe` indicates that the connection is a named pipe, and `sql\query` is the name of the pipe.</span></span> <span data-ttu-id="10ca4-107">Pour se connecter au canal par défaut, l'alias doit avoir `\\<computer_name>\pipe\sql\query` comme nom de canal.</span><span class="sxs-lookup"><span data-stu-id="10ca4-107">To connect to the default pipe, the alias must have `\\<computer_name>\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="10ca4-108">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été configuré de manière à être à l'écoute sur un autre canal, le nom de canal doit correspondre à ce canal.</span><span class="sxs-lookup"><span data-stu-id="10ca4-108">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been configured to listen on a different pipe, the pipe name must use that pipe.</span></span> <span data-ttu-id="10ca4-109">Par exemple, si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise `\\.\pipe\unit\app` comme canal, l'alias doit utiliser `\\<computer_name>\pipe\unit\app` comme nom de canal.</span><span class="sxs-lookup"><span data-stu-id="10ca4-109">For instance, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using `\\.\pipe\unit\app` as the pipe, the alias must use `\\<computer_name>\pipe\unit\app` as the pipe name.</span></span>  
  
 <span data-ttu-id="10ca4-110">Pour créer un nom de canal valide, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="10ca4-110">To create a valid pipe name, you must:</span></span>  
  
-   <span data-ttu-id="10ca4-111">Spécifiez un **nom de l'alias**.</span><span class="sxs-lookup"><span data-stu-id="10ca4-111">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="10ca4-112">Sélectionnez **canaux nommés** comme **protocole**.</span><span class="sxs-lookup"><span data-stu-id="10ca4-112">Select **Named Pipes** as the **Protocol**.</span></span>  
  
-   <span data-ttu-id="10ca4-113">Entrez le **nom du canal**.</span><span class="sxs-lookup"><span data-stu-id="10ca4-113">Enter the **Pipe Name**.</span></span> <span data-ttu-id="10ca4-114">Vous pouvez également laisser le **nom du canal** vide et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager terminera le nom du canal approprié une fois que vous aurez spécifié le **protocole** et le **serveur**</span><span class="sxs-lookup"><span data-stu-id="10ca4-114">Alternatively, you can leave **Pipe Name** blank and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager will complete the appropriate pipe name after you specify the **Protocol** and **Server**</span></span>  
  
-   <span data-ttu-id="10ca4-115">Spécifiez un **serveur**.</span><span class="sxs-lookup"><span data-stu-id="10ca4-115">Specify a **Server**.</span></span> <span data-ttu-id="10ca4-116">Pour une instance nommée, vous pouvez indiquer un nom de serveur et un nom d'instance.</span><span class="sxs-lookup"><span data-stu-id="10ca4-116">For a named instance you can provide a server name and instance name.</span></span>  
  
 <span data-ttu-id="10ca4-117">Au moment de la connexion, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] composant Native Client lit dans le registre les valeurs de serveur, protocole et nom de canal pour le nom d’alias spécifié et crée un nom de canal au format `np:\\<computer_name>\pipe\<pipename>` ou `np:\\<IPAddress>\pipe\<pipename>` . Pour une instance nommée, le nom du canal par défaut est `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query` .</span><span class="sxs-lookup"><span data-stu-id="10ca4-117">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and pipe name values from the registry for the specified alias name, and creates a pipe name in the format `np:\\<computer_name>\pipe\<pipename>` or `np:\\<IPAddress>\pipe\<pipename>`.For a named instance, the default pipe name is `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10ca4-118">Le Pare-feu [!INCLUDE[msCoName](../../includes/msconame-md.md)] ferme le port 445 par défaut.</span><span class="sxs-lookup"><span data-stu-id="10ca4-118">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 445 by default.</span></span> <span data-ttu-id="10ca4-119">Comme [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communique par le biais du port 445, vous devez ouvrir de nouveau le port si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configuré pour être à l'écoute des connexions clientes entrantes utilisant des canaux nommés.</span><span class="sxs-lookup"><span data-stu-id="10ca4-119">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 445, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using named pipes.</span></span> <span data-ttu-id="10ca4-120">Pour plus d'informations sur la configuration d'un pare-feu, consultez « Procédure : configurer un pare-feu pour accéder à SQL Server » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou passez en revue la documentation de votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="10ca4-120">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="10ca4-121">Connexion au serveur local</span><span class="sxs-lookup"><span data-stu-id="10ca4-121">Connecting to the Local Server</span></span>  
 <span data-ttu-id="10ca4-122">Lorsque vous vous connectez à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alors que celui-ci est exécuté sur le même ordinateur que l'ordinateur client, vous pouvez utiliser `(local)` comme nom de serveur.</span><span class="sxs-lookup"><span data-stu-id="10ca4-122">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)`as the server name.</span></span> <span data-ttu-id="10ca4-123">L'utilisation de `(local)` n'est pas conseillée dans la mesure où elle est source d'ambiguïté ; toutefois, elle peut s'avérer utile lorsqu'il est certain que le client s'exécute sur l'ordinateur prévu.</span><span class="sxs-lookup"><span data-stu-id="10ca4-123">Using `(local)` is not encouraged because it leads to ambiguity; however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="10ca4-124">Par exemple, lorsque vous créez une application destinée à des utilisateurs itinérants déconnectés, tels que des vendeurs, pour lesquels [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute sur des ordinateurs portables et stocke les données de projet, un client établissant une connexion à (local) se connecte toujours à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cours d'exécution sur l'ordinateur portable.</span><span class="sxs-lookup"><span data-stu-id="10ca4-124">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to (local) would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="10ca4-125">Vous pouvez utiliser le mot `localhost` ou un point (.) à la place de `(local)`.</span><span class="sxs-lookup"><span data-stu-id="10ca4-125">The word `localhost` or a period (.) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="10ca4-126">Vérification de votre protocole de connexion</span><span class="sxs-lookup"><span data-stu-id="10ca4-126">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="10ca4-127">La requête suivante retournera le protocole utilisé pour la connexion active.</span><span class="sxs-lookup"><span data-stu-id="10ca4-127">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="10ca4-128">Exemples</span><span class="sxs-lookup"><span data-stu-id="10ca4-128">Examples</span></span>  
 <span data-ttu-id="10ca4-129">Connexion au canal par défaut à partir du nom de serveur :</span><span class="sxs-lookup"><span data-stu-id="10ca4-129">Connecting by server name to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="10ca4-130">Connexion au canal par défaut à partir de l'adresse IP :</span><span class="sxs-lookup"><span data-stu-id="10ca4-130">Connecting by IP Address to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <leave blank>  
Protocol           Named Pipes  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="10ca4-131">Connexion à partir du nom de serveur à un canal autre que celui utilisé par défaut :</span><span class="sxs-lookup"><span data-stu-id="10ca4-131">Connecting by server name to a non-default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\unit\app  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="10ca4-132">Connexion à une instance nommée à partir du nom de serveur :</span><span class="sxs-lookup"><span data-stu-id="10ca4-132">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\MSSQL$<instancename>\SQL\query  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="10ca4-133">Connexion à l'ordinateur local à l'aide du paramètre `localhost`:</span><span class="sxs-lookup"><span data-stu-id="10ca4-133">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             localhost  
  
```  
  
 <span data-ttu-id="10ca4-134">Connexion à l'ordinateur local à l'aide d'un point :</span><span class="sxs-lookup"><span data-stu-id="10ca4-134">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <left blank>  
Protocol           Named Pipes  
Server             .  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="10ca4-135">Pour spécifier le protocole réseau en tant que paramètre **sqlcmd** , consultez « Procédure : se connecter au moteur de base de données à l’aide de sqlcmd.exe » dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation en ligne de.</span><span class="sxs-lookup"><span data-stu-id="10ca4-135">To specify the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ca4-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10ca4-136">See Also</span></span>  
 <span data-ttu-id="10ca4-137">[Création d’une chaîne de connexion valide à l’aide du protocole de mémoire partagée](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="10ca4-137">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="10ca4-138">[Création d’une chaîne de connexion valide à l’aide de l’adresse IP TCP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="10ca4-138">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 [<span data-ttu-id="10ca4-139">Choix d'un protocole réseau</span><span class="sxs-lookup"><span data-stu-id="10ca4-139">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
