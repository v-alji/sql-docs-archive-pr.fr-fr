---
title: MSSQLSERVER_41305 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41305 (Database Engine error)
ms.assetid: a96e5083-ff97-4003-a900-07942454151d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9c00e20ec220d7fcee0da4e99c2ef35817dae67f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611097"
---
# <a name="mssqlserver_41305"></a><span data-ttu-id="0e53e-102">MSSQLSERVER_41305</span><span class="sxs-lookup"><span data-stu-id="0e53e-102">MSSQLSERVER_41305</span></span>
    
## <a name="details"></a><span data-ttu-id="0e53e-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0e53e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e53e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0e53e-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0e53e-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0e53e-105">Event ID</span></span>|<span data-ttu-id="0e53e-106">41305</span><span class="sxs-lookup"><span data-stu-id="0e53e-106">41305</span></span>|  
|<span data-ttu-id="0e53e-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0e53e-107">Event Source</span></span>|<span data-ttu-id="0e53e-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0e53e-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0e53e-109">Composant</span><span class="sxs-lookup"><span data-stu-id="0e53e-109">Component</span></span>|<span data-ttu-id="0e53e-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0e53e-110">SQLEngine</span></span>|  
|<span data-ttu-id="0e53e-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0e53e-111">Symbolic Name</span></span>|<span data-ttu-id="0e53e-112">HK_TX_COMMIT_RR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="0e53e-112">HK_TX_COMMIT_RR_VALIDATION</span></span>|  
|<span data-ttu-id="0e53e-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0e53e-113">Message Text</span></span>|<span data-ttu-id="0e53e-114">La transaction en cours n'a pas été validée en raison d'un échec de validation REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="0e53e-114">The current transaction failed to commit due to a repeatable read validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0e53e-115">Explication</span><span class="sxs-lookup"><span data-stu-id="0e53e-115">Explanation</span></span>  
 <span data-ttu-id="0e53e-116">La transaction a rencontré une erreur de validation, et est maintenant vouée à l'échec.</span><span class="sxs-lookup"><span data-stu-id="0e53e-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
 <span data-ttu-id="0e53e-117">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="0e53e-117">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e53e-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0e53e-118">User Action</span></span>  
 <span data-ttu-id="0e53e-119">Réexécutez la transaction en échec.</span><span class="sxs-lookup"><span data-stu-id="0e53e-119">Retry the failed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e53e-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e53e-120">See Also</span></span>  
 [<span data-ttu-id="0e53e-121">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="0e53e-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
