---
title: MSSQLSERVER_41325 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41325 (Database Engine error)
ms.assetid: 97c6a8bb-139a-44f3-9ed5-f46d047e8ed3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a512d7db6529876259d889d04aabf3d07747cafe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701226"
---
# <a name="mssqlserver_41325"></a><span data-ttu-id="0b311-102">MSSQLSERVER_41325</span><span class="sxs-lookup"><span data-stu-id="0b311-102">MSSQLSERVER_41325</span></span>
    
## <a name="details"></a><span data-ttu-id="0b311-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0b311-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b311-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0b311-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0b311-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0b311-105">Event ID</span></span>|<span data-ttu-id="0b311-106">41325</span><span class="sxs-lookup"><span data-stu-id="0b311-106">41325</span></span>|  
|<span data-ttu-id="0b311-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0b311-107">Event Source</span></span>|<span data-ttu-id="0b311-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0b311-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0b311-109">Composant</span><span class="sxs-lookup"><span data-stu-id="0b311-109">Component</span></span>|<span data-ttu-id="0b311-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0b311-110">SQLEngine</span></span>|  
|<span data-ttu-id="0b311-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0b311-111">Symbolic Name</span></span>|<span data-ttu-id="0b311-112">HK_TX_COMMIT_SR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="0b311-112">HK_TX_COMMIT_SR_VALIDATION</span></span>|  
|<span data-ttu-id="0b311-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0b311-113">Message Text</span></span>|<span data-ttu-id="0b311-114">La transaction en cours n'a pas été validée en raison d'un échec de validation SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="0b311-114">The current transaction failed to commit due to a serializable validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0b311-115">Explication</span><span class="sxs-lookup"><span data-stu-id="0b311-115">Explanation</span></span>  
 <span data-ttu-id="0b311-116">La transaction a rencontré une erreur de validation, et est maintenant vouée à l'échec.</span><span class="sxs-lookup"><span data-stu-id="0b311-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b311-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0b311-117">User Action</span></span>  
 <span data-ttu-id="0b311-118">Réexécutez la transaction en échec.</span><span class="sxs-lookup"><span data-stu-id="0b311-118">Retry the failed transaction.</span></span> <span data-ttu-id="0b311-119">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="0b311-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b311-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b311-120">See Also</span></span>  
 [<span data-ttu-id="0b311-121">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="0b311-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
