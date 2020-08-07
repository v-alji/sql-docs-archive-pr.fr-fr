---
title: MSSQLSERVER_41332 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41332 (Database Engine error)
ms.assetid: d3403c3e-d178-4006-b6c9-c18609562db5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72a87838673f07f7a40596517ab54533d944e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611830"
---
# <a name="mssqlserver_41332"></a><span data-ttu-id="1ad2a-102">MSSQLSERVER_41332</span><span class="sxs-lookup"><span data-stu-id="1ad2a-102">MSSQLSERVER_41332</span></span>
    
## <a name="details"></a><span data-ttu-id="1ad2a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="1ad2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ad2a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="1ad2a-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="1ad2a-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="1ad2a-105">Event ID</span></span>|<span data-ttu-id="1ad2a-106">41332</span><span class="sxs-lookup"><span data-stu-id="1ad2a-106">41332</span></span>|  
|<span data-ttu-id="1ad2a-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="1ad2a-107">Event Source</span></span>|<span data-ttu-id="1ad2a-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1ad2a-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1ad2a-109">Composant</span><span class="sxs-lookup"><span data-stu-id="1ad2a-109">Component</span></span>|<span data-ttu-id="1ad2a-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1ad2a-110">SQLEngine</span></span>|  
|<span data-ttu-id="1ad2a-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="1ad2a-111">Symbolic Name</span></span>|<span data-ttu-id="1ad2a-112">SQL_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="1ad2a-112">SQL_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="1ad2a-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="1ad2a-113">Message Text</span></span>|<span data-ttu-id="1ad2a-114">Les tables optimisées en mémoire et les procédures stockées compilées en mode natif ne sont pas accessibles ou ne peuvent pas être créées lorsque la session TRANSACTION ISOLATION LEVEL a la valeur SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="1ad2a-114">Memory optimized tables and natively compiled stored procedures cannot be accessed or created when the session TRANSACTION ISOLATION LEVEL is set to SNAPSHOT.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ad2a-115">Explication</span><span class="sxs-lookup"><span data-stu-id="1ad2a-115">Explanation</span></span>  
 <span data-ttu-id="1ad2a-116">La transaction a démarré au niveau d'isolation SNAPSHOT, puis a tenté d'utiliser une fonctionnalité qui n'est pas compatible.</span><span class="sxs-lookup"><span data-stu-id="1ad2a-116">The transaction was started in snapshot isolation level and then attempted to use an incompatible feature.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ad2a-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ad2a-117">User Action</span></span>  
 <span data-ttu-id="1ad2a-118">Démarrer la transaction avec un autre niveau d'isolation.</span><span class="sxs-lookup"><span data-stu-id="1ad2a-118">Start the transaction with a different isolation level.</span></span> <span data-ttu-id="1ad2a-119">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="1ad2a-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad2a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ad2a-120">See Also</span></span>  
 [<span data-ttu-id="1ad2a-121">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="1ad2a-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
