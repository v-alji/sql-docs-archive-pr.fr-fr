---
title: MSSQLSERVER_17887 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17887 (Database Engine error)
ms.assetid: ad0806e6-3296-4c32-b103-fccf0f8a8d3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 006e616d80ef7e8d083f60675b02b4e6a4e8dc24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600986"
---
# <a name="mssqlserver_17887"></a><span data-ttu-id="54b19-102">MSSQLSERVER_17887</span><span class="sxs-lookup"><span data-stu-id="54b19-102">MSSQLSERVER_17887</span></span>
    
## <a name="details"></a><span data-ttu-id="54b19-103">Détails</span><span class="sxs-lookup"><span data-stu-id="54b19-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54b19-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="54b19-104">Product Name</span></span>|<span data-ttu-id="54b19-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="54b19-105">SQL Server</span></span>|  
|<span data-ttu-id="54b19-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="54b19-106">Event ID</span></span>|<span data-ttu-id="54b19-107">17887</span><span class="sxs-lookup"><span data-stu-id="54b19-107">17887</span></span>|  
|<span data-ttu-id="54b19-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="54b19-108">Event Source</span></span>|<span data-ttu-id="54b19-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="54b19-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="54b19-110">Composant</span><span class="sxs-lookup"><span data-stu-id="54b19-110">Component</span></span>|<span data-ttu-id="54b19-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="54b19-111">SQLEngine</span></span>|  
|<span data-ttu-id="54b19-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="54b19-112">Symbolic Name</span></span>|<span data-ttu-id="54b19-113">SRV_IO_COMP_LISTENER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="54b19-113">SRV_IO_COMP_LISTENER_NONYIELDING</span></span>|  
|<span data-ttu-id="54b19-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="54b19-114">Message Text</span></span>|<span data-ttu-id="54b19-115">L’écoute d’achèvement d’E/S (0x%lx) travail 0x%p semble être improductive sur le nœud %ld.</span><span class="sxs-lookup"><span data-stu-id="54b19-115">IO Completion Listener (0x%lx) Worker 0x%p appears to be non-yielding on Node %ld.</span></span> <span data-ttu-id="54b19-116">Utilisation approximative de l'UC : noyau %I64d ms, utilisateur %I64d ms, intervalle : %I64d.</span><span class="sxs-lookup"><span data-stu-id="54b19-116">Approx CPU Used: kernel %I64d ms, user %I64d ms, Interval: %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="54b19-117">Explication</span><span class="sxs-lookup"><span data-stu-id="54b19-117">Explanation</span></span>  
 <span data-ttu-id="54b19-118">Indique qu'il existe un éventuel problème avec l'écouteur du port d'exécution d'E/S sur le nœud spécifié lors de l'exécution de la routine d'exécution d'E/S pour un événement de lecture/écriture sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="54b19-118">Indicates that there is a possible problem with the I/O Completion Port Listener on the specified node when executing the I/O Completion routine for a network read/write event.</span></span> <span data-ttu-id="54b19-119">Cette erreur disparaîtra lorsque l'écouteur du port d'exécution d'E/S sortira de la routine d'exécution d'E/S.</span><span class="sxs-lookup"><span data-stu-id="54b19-119">This error will go away when the I/O Completion Port Listener returns from executing the I/O Completion routine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54b19-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="54b19-120">User Action</span></span>  
 <span data-ttu-id="54b19-121">Contactez les services d'assistance Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54b19-121">Contact Microsoft Customer Support Services (CSS).</span></span>  
  
  
