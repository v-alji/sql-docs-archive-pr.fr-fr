---
title: MSSQLSERVER_9692 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9692 (Database Engine error)
ms.assetid: 02399d6e-ab5e-4f30-8a3e-2bb1e8c135b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6ba95771aafffa5a322ffa1b7443419936addd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604484"
---
# <a name="mssqlserver_9692"></a><span data-ttu-id="52ce0-102">MSSQLSERVER_9692</span><span class="sxs-lookup"><span data-stu-id="52ce0-102">MSSQLSERVER_9692</span></span>
    
## <a name="details"></a><span data-ttu-id="52ce0-103">Détails</span><span class="sxs-lookup"><span data-stu-id="52ce0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52ce0-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="52ce0-104">Product Name</span></span>|<span data-ttu-id="52ce0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="52ce0-105">SQL Server</span></span>|  
|<span data-ttu-id="52ce0-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="52ce0-106">Event ID</span></span>|<span data-ttu-id="52ce0-107">9692</span><span class="sxs-lookup"><span data-stu-id="52ce0-107">9692</span></span>|  
|<span data-ttu-id="52ce0-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="52ce0-108">Event Source</span></span>|<span data-ttu-id="52ce0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="52ce0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="52ce0-110">Composant</span><span class="sxs-lookup"><span data-stu-id="52ce0-110">Component</span></span>|<span data-ttu-id="52ce0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="52ce0-111">SQLEngine</span></span>|  
|<span data-ttu-id="52ce0-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="52ce0-112">Symbolic Name</span></span>|<span data-ttu-id="52ce0-113">SB2_CANT_LISTEN_PORT_IN_USE</span><span class="sxs-lookup"><span data-stu-id="52ce0-113">SB2_CANT_LISTEN_PORT_IN_USE</span></span>|  
|<span data-ttu-id="52ce0-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="52ce0-114">Message Text</span></span>|<span data-ttu-id="52ce0-115">Le transport de protocole %S_MSG ne peut pas écouter le port %d, car il est utilisé par un autre processus.</span><span class="sxs-lookup"><span data-stu-id="52ce0-115">The %S_MSG protocol transport cannot listen on port %d because it is in use by another process.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="52ce0-116">Explication</span><span class="sxs-lookup"><span data-stu-id="52ce0-116">Explanation</span></span>  
 <span data-ttu-id="52ce0-117">Un autre programme exécuté sur l'ordinateur utilise actuellement le port TCP indiqué.</span><span class="sxs-lookup"><span data-stu-id="52ce0-117">Another program on the computer is using the TCP port indicated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="52ce0-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="52ce0-118">User Action</span></span>  
 <span data-ttu-id="52ce0-119">Exécutez `netstat -aon` pour déterminer le programme qui utilise le port.</span><span class="sxs-lookup"><span data-stu-id="52ce0-119">Run `netstat -aon` to determine what program is using the port.</span></span> <span data-ttu-id="52ce0-120">Désactivez cette application ou spécifiez un port différent pour Service Broker.</span><span class="sxs-lookup"><span data-stu-id="52ce0-120">Disable that application or specify a different port for Service Broker.</span></span>  
  
  
