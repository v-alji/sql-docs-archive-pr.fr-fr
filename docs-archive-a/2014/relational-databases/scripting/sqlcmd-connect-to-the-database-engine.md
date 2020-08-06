---
title: Se connecter au moteur de base de données avec sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sqlcmd utility, Database Engine connections
- Named Pipes [SQL Server], sqlcmd utility
- TCP/IP [SQL Server], client protocols
- network protocols [SQL Server], sqlcmd utility
- protocols [SQL Server], sqlcmd utility
- VIA
- client protocols [SQL Server]
ms.assetid: 74b0fb71-7f8e-4171-9431-d07528532524
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b409683b651e3e6508baced5eb3bc9fcc631e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602040"
---
# <a name="connect-to-the-database-engine-with-sqlcmd"></a><span data-ttu-id="d1150-102">Se connecter au moteur de base de données avec sqlcmd</span><span class="sxs-lookup"><span data-stu-id="d1150-102">Connect to the Database Engine With sqlcmd</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d1150-103">prend en charge la communication cliente par le biais du protocole réseau TCP/IP (protocole par défaut) et du protocole des canaux nommés.</span><span class="sxs-lookup"><span data-stu-id="d1150-103">supports client communication with the TCP/IP network protocol (the default), and the named pipes protocol.</span></span> <span data-ttu-id="d1150-104">Le protocole de mémoire partagée est également disponible si le client se connecte à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d1150-104">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="d1150-105">Il existe trois méthodes courantes de sélection du protocole.</span><span class="sxs-lookup"><span data-stu-id="d1150-105">There are three common methods of selecting the protocol.</span></span> <span data-ttu-id="d1150-106">Le protocole utilisé par l’utilitaire **sqlcmd** est déterminé dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="d1150-106">The protocol used by the **sqlcmd** utility is determined in the following order:</span></span>  
  
-   <span data-ttu-id="d1150-107">**sqlcmd** utilise le protocole spécifié dans la chaîne de connexion comme décrit ci-après.</span><span class="sxs-lookup"><span data-stu-id="d1150-107">**sqlcmd** uses the protocol specified as part of the connection string as described below.</span></span>  
  
-   <span data-ttu-id="d1150-108">Si aucun protocole n’est spécifié dans la chaîne de connexion, **sqlcmd** utilise le protocole défini dans l’alias auquel il se connecte.</span><span class="sxs-lookup"><span data-stu-id="d1150-108">If no protocol is specified as part the connection string, **sqlcmd** will use the protocol defined as part of the alias that it is connecting to.</span></span> <span data-ttu-id="d1150-109">Pour configurer **sqlcmd** pour utiliser un protocole réseau spécifique en créant un alias, consultez [Créer ou modifier un alias de serveur devant être utilisé par un client &#40;Gestionnaire de configuration SQL Server&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="d1150-109">To configure **sqlcmd** to use a specific network protocol by creating an alias, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="d1150-110">Sinon, **sqlcmd** utilise le protocole réseau déterminé par l’ordre des protocoles dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1150-110">If the protocol is not specified in some other way, **sqlcmd** will use the network protocol determined by the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
 <span data-ttu-id="d1150-111">Les exemples suivants montrent différentes manières de se connecter à l'instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)] sur le port 1433 et aux instances nommées du [!INCLUDE[ssDE](../../includes/ssde-md.md)] supposées être à l'écoute sur le port 1691.</span><span class="sxs-lookup"><span data-stu-id="d1150-111">The following examples show various ways of connecting to the default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] on port 1433, and named instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] presumed to be listening on port 1691.</span></span> <span data-ttu-id="d1150-112">Certains de ces exemples utilisent l'adresse IP de la carte de bouclage (127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="d1150-112">Some of these examples use the IP address of the loopback adapter (127.0.0.1).</span></span> <span data-ttu-id="d1150-113">Effectuez un test sur l'adresse IP de la carte réseau de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d1150-113">Test using the IP address of your computer network interface card.</span></span>  
  
 <span data-ttu-id="d1150-114">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)] en spécifiant le nom de l'instance :</span><span class="sxs-lookup"><span data-stu-id="d1150-114">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the instance name:</span></span>  
  
```  
sqlcmd -S ComputerA  
sqlcmd -S ComputerA\instanceB  
```  
  
 <span data-ttu-id="d1150-115">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)] en spécifiant l'adresse IP :</span><span class="sxs-lookup"><span data-stu-id="d1150-115">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the IP address:</span></span>  
  
```  
sqlcmd -S 127.0.0.1  
sqlcmd -S 127.0.0.1\instanceB  
```  
  
 <span data-ttu-id="d1150-116">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)] en spécifiant le numéro de port TCP\IP :</span><span class="sxs-lookup"><span data-stu-id="d1150-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the TCP\IP port number:</span></span>  
  
```  
sqlcmd -S ComputerA,1433  
sqlcmd -S ComputerA,1691  
sqlcmd -S 127.0.0.1,1433  
sqlcmd -S 127.0.0.1,1691  
```  
  
### <a name="to-connect-using-tcpip"></a><span data-ttu-id="d1150-117">Pour établir la connexion à l'aide du protocole TCP/IP</span><span class="sxs-lookup"><span data-stu-id="d1150-117">To connect using TCP/IP</span></span>  
  
-   <span data-ttu-id="d1150-118">Connectez-vous à l'aide de la syntaxe générale suivante :</span><span class="sxs-lookup"><span data-stu-id="d1150-118">Connect using the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S tcp:<computer name>,<port number>  
    ```  
  
-   <span data-ttu-id="d1150-119">Connectez-vous à l'instance par défaut :</span><span class="sxs-lookup"><span data-stu-id="d1150-119">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1433  
    sqlcmd -S tcp:127.0.0.1,1433  
    ```  
  
-   <span data-ttu-id="d1150-120">Connectez-vous à une instance nommée :</span><span class="sxs-lookup"><span data-stu-id="d1150-120">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1691  
    sqlcmd -S tcp:127.0.0.1,1691  
    ```  
  
### <a name="to-connect-using-named-pipes"></a><span data-ttu-id="d1150-121">Pour établir la connexion à l'aide de canaux nommés</span><span class="sxs-lookup"><span data-stu-id="d1150-121">To connect using named pipes</span></span>  
  
-   <span data-ttu-id="d1150-122">Connectez-vous à l'aide de l'une des syntaxes générales suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1150-122">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S np:\\<computer name>\<pipe name>  
    ```  
  
-   <span data-ttu-id="d1150-123">Connectez-vous à l'instance par défaut :</span><span class="sxs-lookup"><span data-stu-id="d1150-123">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\sql\query  
    ```  
  
-   <span data-ttu-id="d1150-124">Connectez-vous à une instance nommée :</span><span class="sxs-lookup"><span data-stu-id="d1150-124">Connect to a named instance instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\MSSQL$<instancename>\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\MSSQL$<instancename>\sql\query  
    ```  
  
### <a name="to-connect-using-shared-memory-a-local-procedure-call-from-a-client-on-the-server"></a><span data-ttu-id="d1150-125">Pour établir la connexion à l'aide de la mémoire partagée (appel de procédure local) depuis un client sur le serveur</span><span class="sxs-lookup"><span data-stu-id="d1150-125">To connect using shared memory (a local procedure call) from a client on the server</span></span>  
  
-   <span data-ttu-id="d1150-126">Connectez-vous à l'aide de l'une des syntaxes générales suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1150-126">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S lpc:<computer name>  
    ```  
  
-   <span data-ttu-id="d1150-127">Connectez-vous à l'instance par défaut :</span><span class="sxs-lookup"><span data-stu-id="d1150-127">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA  
    ```  
  
-   <span data-ttu-id="d1150-128">Connectez-vous à une instance nommée :</span><span class="sxs-lookup"><span data-stu-id="d1150-128">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA\<instancename>  
    ```  
  
  
