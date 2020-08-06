---
title: Modifier les connexions qui utilisent les protocoles réseau Banyan VINEs Séquencéd paquet Protocol (SPP), Multiprotocol, AppleTalk ou NWLink IPX SPX | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], modifying connections
- SPP [SQL Server]
- NWLink IPX/SPX [SQL Server]
- connections [SQL Server]
- AppleTalk [SQL Server]
- Sequenced Packet Protocol [SQL Server]
- Multiprotocol Net-Library [SQL Server]
- Banyan VINES Sequenced Package Protocol [SQL Server]
- IPX/SPX [SQL Server]
- protocols [SQL Server], modifying connections
- RPC [SQL Server]
ms.assetid: 5c5ae453-cc5b-4898-95c7-ad34157b1f60
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 750b9c0b76ab6c3b43908ecb8454f31ac1a25b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708055"
---
# <a name="modify-connections-that-use-banyan-vines-sequenced-packet-protocol-spp-multiprotocol-appletalk-or-nwlink-ipx-spx-network-protocols"></a><span data-ttu-id="b62cc-102">Modifier les connexions utilisant les protocoles réseau Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk ou NWLink IPX/SPX</span><span class="sxs-lookup"><span data-stu-id="b62cc-102">Modify connections that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX SPX network protocols</span></span>
  <span data-ttu-id="b62cc-103">Le Conseiller de mise à niveau a détecté des protocoles de connexion serveur client qui ne sont pas pris en charge dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b62cc-103">The Upgrade Advisor has detected client server connectivity protocols that are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b62cc-104">Les applications clientes qui utilisent les protocoles réseau Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol (RPC), AppleTalk ou NWLink IPX/SPX doivent se connecter à l'aide d'un protocole pris en charge.</span><span class="sxs-lookup"><span data-stu-id="b62cc-104">Client applications that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol (RPC), AppleTalk, or NWLink IPX/SPX network protocols must connect using a supported protocol.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b62cc-105">Composant</span><span class="sxs-lookup"><span data-stu-id="b62cc-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b62cc-106">Description</span><span class="sxs-lookup"><span data-stu-id="b62cc-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="b62cc-107">ne prend pas en charge les protocoles réseau Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk ou NWLink IPX/SPX.</span><span class="sxs-lookup"><span data-stu-id="b62cc-107">does not support the Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX/SPX network protocols.</span></span> <span data-ttu-id="b62cc-108">Les clients précédemment connectés au moyen de ces protocoles doivent sélectionner un autre protocole.</span><span class="sxs-lookup"><span data-stu-id="b62cc-108">Clients previously connecting with these protocols must select a different protocol.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b62cc-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="b62cc-109">Corrective Action</span></span>  
 <span data-ttu-id="b62cc-110">Modifiez les applications clientes pour qu'elles utilisent un protocole pris en charge lorsqu'elles se connectent au serveur.</span><span class="sxs-lookup"><span data-stu-id="b62cc-110">Change the client applications to use a supported protocol when connecting to the server.</span></span> <span data-ttu-id="b62cc-111">Si un alias est défini, qui utilise l'un des protocoles non pris en charge, cet alias doit alors être modifié pour utiliser un protocole pris en charge.</span><span class="sxs-lookup"><span data-stu-id="b62cc-111">If you have an alias setup that uses one of the unsupported protocols then the alias must be modified to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="b62cc-112">Si la chaîne de connexion de votre application utilise ou charge spécifiquement l’un de ces protocoles, soit en spécifiant NETWORK = DBMSRPCN pour RPC, NETWORK = DBMSADSN pour AppleTalk ou NETWORK = DBMSVINN pour la propriété Banyan VINEs, ou en utilisant un préfixe explicite tel que « SPX :*server\instance*» pour SPX, « BV :*serveur*» pour Banyan VINES, « ADSP :*serveur*» pour AppleTalk ou « RPC :*serveur*» pour le multiprotocole, vous devez modifier votre application pour utiliser l’un des protocoles pris en charge.</span><span class="sxs-lookup"><span data-stu-id="b62cc-112">If your application connection string specifically uses or loads one of these protocols, by either specifying NETWORK=DBMSRPCN for RPC, NETWORK=DBMSADSN for Appletalk, or NETWORK=DBMSVINN for Banyan VINES property, or by using an explicit prefix such as "spx:*server\instance*" for SPX, "bv:*server*" for Banyan VINES, "adsp:*server*" for AppleTalk, or "rpc:*server*" for multiprotocol, then you must modify your application to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="b62cc-113">Pour plus d'informations, consultez « Choix d'un protocole réseau » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b62cc-113">For more information, see "Choosing a Network Protocol" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b62cc-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b62cc-114">See Also</span></span>  
 <span data-ttu-id="b62cc-115">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b62cc-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b62cc-116">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="b62cc-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
