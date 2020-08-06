---
title: Création d’une chaîne de connexion valide avec le protocole de mémoire partagée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], shared memory
- aliases [SQL Server], shared memory
ms.assetid: 5fff42e8-377f-4b40-b0c8-b02393f8a1af
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca97332a09a33fcfc15a3dbb2599af27dbe0e1db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695056"
---
# <a name="creating-a-valid-connection-string-using-shared-memory-protocol"></a><span data-ttu-id="9f57e-102">Création d'une chaîne de connexion valide à l'aide du protocole de mémoire partagée</span><span class="sxs-lookup"><span data-stu-id="9f57e-102">Creating a Valid Connection String Using Shared Memory Protocol</span></span>
  <span data-ttu-id="9f57e-103">Les connexions à [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d'un client exécuté sur le même ordinateur utilisent le protocole de mémoire partagée.</span><span class="sxs-lookup"><span data-stu-id="9f57e-103">Connections to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client running on the same computer use the shared memory protocol.</span></span> <span data-ttu-id="9f57e-104">La mémoire partagée ne possède aucune propriété configurable.</span><span class="sxs-lookup"><span data-stu-id="9f57e-104">Shared memory has no configurable properties.</span></span> <span data-ttu-id="9f57e-105">La mémoire partagée est toujours sollicitée en premier et ne peut pas être déplacée depuis sa position initiale dans la liste des **Protocoles activés** dans la boite de dialogue de **Propriétés de protocoles clients** .</span><span class="sxs-lookup"><span data-stu-id="9f57e-105">Shared memory is always tried first, and cannot be moved from the top position of the **Enabled Protocols** list in the **Client Protocols Properties** list.</span></span> <span data-ttu-id="9f57e-106">Le protocole de mémoire partagée peut être désactivé, ce qui est utile lors du dépannage de l'un des autres protocoles.</span><span class="sxs-lookup"><span data-stu-id="9f57e-106">The Shared Memory protocol can be disabled, which is useful when troubleshooting one of the other protocols.</span></span>  
  
 <span data-ttu-id="9f57e-107">Vous ne pouvez pas créer un alias utilisant le protocole de mémoire partagée mais, si la mémoire partagée est activée, la connexion au [!INCLUDE[ssDE](../../includes/ssde-md.md)] à partir du nom crée une connexion de mémoire partagée.</span><span class="sxs-lookup"><span data-stu-id="9f57e-107">You cannot create an alias using the shared memory protocol, but if shared memory is enabled, then connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by name, creates a shared memory connection.</span></span> <span data-ttu-id="9f57e-108">Une chaîne de connexion de mémoire partagée utilise le format `lpc:<servername>[\instancename]`.</span><span class="sxs-lookup"><span data-stu-id="9f57e-108">A shared memory connection string uses the format `lpc:<servername>[\instancename]`.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="9f57e-109">Connexion au serveur local</span><span class="sxs-lookup"><span data-stu-id="9f57e-109">Connecting to the Local Server</span></span>  
 <span data-ttu-id="9f57e-110">Quand vous vous connectez à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alors que celui-ci s’exécute sur le même ordinateur que l’ordinateur client, vous pouvez utiliser **(local)** comme nom de serveur.</span><span class="sxs-lookup"><span data-stu-id="9f57e-110">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use **(local)** as the server name.</span></span> <span data-ttu-id="9f57e-111">Cette option n'est pas conseillée dans la mesure où elle est source d'ambiguïté ; toutefois, elle peut s'avérer utile lorsqu'il est certain que le client s'exécute sur l'ordinateur visé.</span><span class="sxs-lookup"><span data-stu-id="9f57e-111">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="9f57e-112">Par exemple, quand vous créez une application pour des utilisateurs itinérants déconnectés, tels que des commerciaux, où [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s’exécute sur des ordinateurs portables et stocke les données de projet, un client qui se connecte à **(local)** se connecte toujours à l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s’exécutant sur l’ordinateur portable.</span><span class="sxs-lookup"><span data-stu-id="9f57e-112">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to **(local)** would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="9f57e-113">Vous pouvez utiliser le mot **localhost** ou un point ( **.** ) à la place de **(local)** .</span><span class="sxs-lookup"><span data-stu-id="9f57e-113">The word **localhost** or a period (**.**) can be used in place of **(local)**.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="9f57e-114">Vérification du protocole de connexion</span><span class="sxs-lookup"><span data-stu-id="9f57e-114">Verifying your Connection Protocol</span></span>  
 <span data-ttu-id="9f57e-115">La requête suivante retournera le protocole utilisé pour la connexion active.</span><span class="sxs-lookup"><span data-stu-id="9f57e-115">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="9f57e-116">Exemples :</span><span class="sxs-lookup"><span data-stu-id="9f57e-116">Examples:</span></span>  
 <span data-ttu-id="9f57e-117">Les noms suivants permettent d'établir une connexion à l'ordinateur local avec le protocole de mémoire partagée si celui-ci est activé :</span><span class="sxs-lookup"><span data-stu-id="9f57e-117">The following names will connect to the local computer with the shared memory protocol if it is enabled:</span></span>  
  
 `<servername>`  
  
 `<servername>\<instancename>`  
  
 `(local)`  
  
 `localhost`  
  
 <span data-ttu-id="9f57e-118">Vous ne pouvez pas créer un alias pour une connexion de mémoire partagée.</span><span class="sxs-lookup"><span data-stu-id="9f57e-118">You cannot create an alias for a shared memory connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f57e-119">La spécification d’une adresse IP dans la zone **Serveur** génère une connexion TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="9f57e-119">Specifying an IP Address in the **Server** box will result in a TCP/IP connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f57e-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f57e-120">See Also</span></span>  
 <span data-ttu-id="9f57e-121">[Création d’une chaîne de connexion valide avec TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="9f57e-121">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 <span data-ttu-id="9f57e-122">[Création d’une chaîne de connexion valide avec des canaux nommés](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="9f57e-122">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="9f57e-123">Choix d’un protocole réseau</span><span class="sxs-lookup"><span data-stu-id="9f57e-123">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
