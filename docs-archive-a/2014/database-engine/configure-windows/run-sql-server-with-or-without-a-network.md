---
title: Exécuter SQL Server avec ou sans réseau | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- verifying Server service has been started
- net start [SQL Server]
- command prompt [SQL Server], connections
- SQL Server services, networks
- status information [SQL Server], Server service
- running SQL Server
- networking [SQL Server], SQL Server with or without
- services [SQL Server], networks
- starting Server service
- SQL Server, running
ms.assetid: 54eac961-5c7a-4481-982d-f93a64b5c2f4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a80e7e4d42f322bc42d0c67c57e3a1f9bddb87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605717"
---
# <a name="run-sql-server-with-or-without-a-network"></a><span data-ttu-id="93539-102">Exécuter SQL Server avec ou sans réseau</span><span class="sxs-lookup"><span data-stu-id="93539-102">Run SQL Server With or Without a Network</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="93539-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut s’exécuter sur un réseau ou fonctionner sans réseau.</span><span class="sxs-lookup"><span data-stu-id="93539-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can run on a network, or it can function without a network.</span></span>  
  
## <a name="running-sql-server-on-a-network"></a><span data-ttu-id="93539-104">Exécution de SQL Server sur un réseau</span><span class="sxs-lookup"><span data-stu-id="93539-104">Running SQL Server on a Network</span></span>  
 <span data-ttu-id="93539-105">Pour permettre à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de communiquer en réseau, le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit être en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="93539-105">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to communicate over a network, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service must be running.</span></span> <span data-ttu-id="93539-106">Par défaut, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows démarre automatiquement le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intégré.</span><span class="sxs-lookup"><span data-stu-id="93539-106">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows automatically starts the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="93539-107">Pour savoir si le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est lancé, à l'invite de commandes tapez :</span><span class="sxs-lookup"><span data-stu-id="93539-107">To find out whether the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has been started, at the command prompt, type the following:</span></span>  
  
 <span data-ttu-id="93539-108">**net start**</span><span class="sxs-lookup"><span data-stu-id="93539-108">**net start**</span></span>  
  
 <span data-ttu-id="93539-109">Si les services associés à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ont été démarrés, les services suivants s’affichent dans la sortie **net start** :</span><span class="sxs-lookup"><span data-stu-id="93539-109">If the services associated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] have been started, the following services will appear in the **net start** output:</span></span>  
  
-   <span data-ttu-id="93539-110">Analysis Services (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="93539-110">Analysis Services (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="93539-111">SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="93539-111">SQL Server (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="93539-112">Agent SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="93539-112">SQL Server Agent (MSSQLSERVER)</span></span>  
  
## <a name="running-sql-server-without-a-network"></a><span data-ttu-id="93539-113">Exécution de SQL Server sans réseau</span><span class="sxs-lookup"><span data-stu-id="93539-113">Running SQL Server Without a Network</span></span>  
 <span data-ttu-id="93539-114">Lors de l'exécution d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sans réseau, il n'est pas nécessaire de démarrer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intégré.</span><span class="sxs-lookup"><span data-stu-id="93539-114">When running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without a network, you do not need to start the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="93539-115">Étant donné que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], le Gestionnaire de configuration SQL Server et les commandes **net start** et **net stop** sont toujours fonctionnels (même sans réseau), les procédures de démarrage et d’arrêt d’une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont identiques, qu’il s’agisse d’un fonctionnement en réseau ou en mode autonome.</span><span class="sxs-lookup"><span data-stu-id="93539-115">Because [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], SQL Server Configuration Manager, and the **net start** and **net stop** commands are functional even without a network, the procedures for starting and stopping an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are identical for a network or stand-alone operation.</span></span>  
  
 <span data-ttu-id="93539-116">Quand vous vous connectez à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode autonome à partir d’une station cliente locale telle que **sqlcmd**, par exemple, vous ignorez le réseau et vous accédez directement à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide d’un canal de communication local.</span><span class="sxs-lookup"><span data-stu-id="93539-116">When connecting to an instance of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a local client such as **sqlcmd**, you bypass the network and connect directly to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a local pipe.</span></span> <span data-ttu-id="93539-117">La différence entre un canal de communication local et un canal de communication réseau réside dans l'utilisation ou non d'un réseau.</span><span class="sxs-lookup"><span data-stu-id="93539-117">The difference between a local pipe and a network pipe is whether you are using a network.</span></span> <span data-ttu-id="93539-118">Les canaux de communication local et réseau établissent une connexion avec une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide du canal standard (\\\\.\pipe\sql\query), sauf instructions contraires.</span><span class="sxs-lookup"><span data-stu-id="93539-118">Both local and network pipes establish a connection with an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the standard pipe (\\\\.\pipe\sql\query), unless otherwise directed.</span></span>  
  
 <span data-ttu-id="93539-119">Quand vous vous connectez à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] locale sans spécifier le nom d'un serveur, vous utilisez un canal de communication local.</span><span class="sxs-lookup"><span data-stu-id="93539-119">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without specifying a server name, you are using a local pipe.</span></span> <span data-ttu-id="93539-120">Lorsque vous vous connectez à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] locale en spécifiant explicitement le nom d'un serveur, vous utilisez soit un canal réseau, soit un autre mécanisme de réseau IPC, comme IPX/SPX (Internetwork Packet Exchange/Sequenced Packet Exchange) (si vous avez configuré [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour une utilisation multi-réseau).</span><span class="sxs-lookup"><span data-stu-id="93539-120">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and specify a server name explicitly, you are using either a network pipe or another network interprocess communication (IPC) mechanism, such as Internetwork Packet Exchange/Sequenced Packet Exchange (IPX/SPX) (assuming you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use multiple networks).</span></span> <span data-ttu-id="93539-121">Comme une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autonome ne gère pas les canaux de communication réseau, vous devez omettre l’argument **/** _<nom_serveur>_ , devenu inutile, quand vous vous connectez à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d’un client.</span><span class="sxs-lookup"><span data-stu-id="93539-121">Because a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support network pipes, you must omit the unnecessary **/**_<Server_name>_ argument when connecting to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client.</span></span> <span data-ttu-id="93539-122">Par exemple, pour vous connecter à une instance autonome de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir de **osql**, tapez :</span><span class="sxs-lookup"><span data-stu-id="93539-122">For example, to connect to a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from **osql**, type:</span></span>  
  
 <span data-ttu-id="93539-123">**osql /Usa /P** _\<saPassword>_</span><span class="sxs-lookup"><span data-stu-id="93539-123">**osql /Usa /P** _\<saPassword>_</span></span>  
  
  
