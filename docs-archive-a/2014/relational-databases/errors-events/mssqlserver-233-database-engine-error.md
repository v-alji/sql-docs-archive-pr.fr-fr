---
title: MSSQLSERVER_233 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "233"
helpviewer_keywords:
- 233 (Database Engine error)
ms.assetid: 201665dc-7ac8-4c19-90d3-33354c5caa72
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c51fac7c0af16c520d7cf5538e512912e62cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698255"
---
# <a name="mssqlserver_233"></a><span data-ttu-id="5f1fa-102">MSSQLSERVER_233</span><span class="sxs-lookup"><span data-stu-id="5f1fa-102">MSSQLSERVER_233</span></span>
    
## <a name="details"></a><span data-ttu-id="5f1fa-103">Détails</span><span class="sxs-lookup"><span data-stu-id="5f1fa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f1fa-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="5f1fa-104">Product Name</span></span>|<span data-ttu-id="5f1fa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5f1fa-105">SQL Server</span></span>|  
|<span data-ttu-id="5f1fa-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="5f1fa-106">Event ID</span></span>|<span data-ttu-id="5f1fa-107">233</span><span class="sxs-lookup"><span data-stu-id="5f1fa-107">233</span></span>|  
|<span data-ttu-id="5f1fa-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="5f1fa-108">Event Source</span></span>|<span data-ttu-id="5f1fa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5f1fa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5f1fa-110">Composant</span><span class="sxs-lookup"><span data-stu-id="5f1fa-110">Component</span></span>|<span data-ttu-id="5f1fa-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5f1fa-111">SQLEngine</span></span>|  
|<span data-ttu-id="5f1fa-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="5f1fa-112">Symbolic Name</span></span>||  
|<span data-ttu-id="5f1fa-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5f1fa-113">Message Text</span></span>|<span data-ttu-id="5f1fa-114">Une connexion a été établie avec le serveur, mais une erreur s’est ensuite produite pendant le processus de connexion.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-114">A connection was successfully established with the server, but then an error occurred during the login process.</span></span> <span data-ttu-id="5f1fa-115">(fournisseur : Fournisseur de mémoire partagée, erreur : 0 - Il n’y a pas de processus à l’autre extrémité du canal.) (Microsoft SQL Server, erreur : 233)</span><span class="sxs-lookup"><span data-stu-id="5f1fa-115">(provider: Shared Memory Provider, error: 0 - No process is on the other end of the pipe.) (Microsoft SQL Server, Error: 233)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5f1fa-116">Explication</span><span class="sxs-lookup"><span data-stu-id="5f1fa-116">Explanation</span></span>  
 <span data-ttu-id="5f1fa-117">Le client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="5f1fa-118">Cette erreur s'est peut-être produite parce que le serveur n'est pas configuré pour accepter des connexions distantes.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-118">This error could occur because the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5f1fa-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5f1fa-119">User Action</span></span>  
 <span data-ttu-id="5f1fa-120">Utilisez l'outil Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour permettre à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'accepter des connexions distantes.</span><span class="sxs-lookup"><span data-stu-id="5f1fa-120">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f1fa-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f1fa-121">See Also</span></span>  
 <span data-ttu-id="5f1fa-122">[Protocoles réseau et bibliothèques réseau](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="5f1fa-122">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="5f1fa-123">[Configuration du réseau client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5f1fa-123">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="5f1fa-124">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="5f1fa-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="5f1fa-125">Activer ou désactiver un protocole réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="5f1fa-125">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
