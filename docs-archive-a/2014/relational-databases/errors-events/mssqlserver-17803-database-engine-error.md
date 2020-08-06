---
title: MSSQLSERVER_17803 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17803 (Database Engine error)
ms.assetid: 28591a19-258d-4891-b78a-4686789bb2d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be63b3d05bff2ebf90122f66af4297d77376fce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612884"
---
# <a name="mssqlserver_17803"></a><span data-ttu-id="5efe7-102">MSSQLSERVER_17803</span><span class="sxs-lookup"><span data-stu-id="5efe7-102">MSSQLSERVER_17803</span></span>
    
## <a name="details"></a><span data-ttu-id="5efe7-103">Détails</span><span class="sxs-lookup"><span data-stu-id="5efe7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5efe7-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="5efe7-104">Product Name</span></span>|<span data-ttu-id="5efe7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5efe7-105">SQL Server</span></span>|  
|<span data-ttu-id="5efe7-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="5efe7-106">Event ID</span></span>|<span data-ttu-id="5efe7-107">17803</span><span class="sxs-lookup"><span data-stu-id="5efe7-107">17803</span></span>|  
|<span data-ttu-id="5efe7-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="5efe7-108">Event Source</span></span>|<span data-ttu-id="5efe7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5efe7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5efe7-110">Composant</span><span class="sxs-lookup"><span data-stu-id="5efe7-110">Component</span></span>|<span data-ttu-id="5efe7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5efe7-111">SQLEngine</span></span>|  
|<span data-ttu-id="5efe7-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="5efe7-112">Symbolic Name</span></span>|<span data-ttu-id="5efe7-113">SRV_NOMEMORY</span><span class="sxs-lookup"><span data-stu-id="5efe7-113">SRV_NOMEMORY</span></span>|  
|<span data-ttu-id="5efe7-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5efe7-114">Message Text</span></span>|<span data-ttu-id="5efe7-115">Une erreur d'allocation de mémoire s'est produite au cours de l'établissement de la connexion.</span><span class="sxs-lookup"><span data-stu-id="5efe7-115">There was a memory allocation failure during connection establishment.</span></span> <span data-ttu-id="5efe7-116">Réduisez la charge de mémoire qui n'est pas essentielle ou augmentez la quantité de mémoire système.</span><span class="sxs-lookup"><span data-stu-id="5efe7-116">Reduce nonessential memory load, or increase system memory.</span></span> <span data-ttu-id="5efe7-117">La connexion a été fermée.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="5efe7-117">The connection has been closed.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5efe7-118">Explication</span><span class="sxs-lookup"><span data-stu-id="5efe7-118">Explanation</span></span>  
 <span data-ttu-id="5efe7-119">Le serveur manque de mémoire.</span><span class="sxs-lookup"><span data-stu-id="5efe7-119">Server is running out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5efe7-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5efe7-120">User Action</span></span>  
 <span data-ttu-id="5efe7-121">Déterminez la cause de la mémoire insuffisante au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="5efe7-121">Determine the cause for server running out of memory.</span></span> <span data-ttu-id="5efe7-122">Les étapes de résolution des problèmes de mémoire génériques peuvent être utiles</span><span class="sxs-lookup"><span data-stu-id="5efe7-122">Generic memory troubleshooting steps may be useful</span></span>  
  
  
