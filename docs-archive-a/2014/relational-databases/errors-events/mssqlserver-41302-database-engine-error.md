---
title: MSSQLSERVER_41302 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41302 (Database Engine error)
ms.assetid: 01e75618-afec-4232-ba68-93ab7bc31003
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 751dac91378c002a7e6c6c619ddaf12be8173400
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604024"
---
# <a name="mssqlserver_41302"></a><span data-ttu-id="0ee13-102">MSSQLSERVER_41302</span><span class="sxs-lookup"><span data-stu-id="0ee13-102">MSSQLSERVER_41302</span></span>
    
## <a name="details"></a><span data-ttu-id="0ee13-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0ee13-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ee13-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0ee13-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0ee13-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0ee13-105">Event ID</span></span>|<span data-ttu-id="0ee13-106">41302</span><span class="sxs-lookup"><span data-stu-id="0ee13-106">41302</span></span>|  
|<span data-ttu-id="0ee13-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0ee13-107">Event Source</span></span>|<span data-ttu-id="0ee13-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0ee13-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0ee13-109">Composant</span><span class="sxs-lookup"><span data-stu-id="0ee13-109">Component</span></span>|<span data-ttu-id="0ee13-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0ee13-110">SQLEngine</span></span>|  
|<span data-ttu-id="0ee13-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0ee13-111">Symbolic Name</span></span>|<span data-ttu-id="0ee13-112">WRITE_WRITE_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="0ee13-112">WRITE_WRITE_CONFLICT</span></span>|  
|<span data-ttu-id="0ee13-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0ee13-113">Message Text</span></span>|<span data-ttu-id="0ee13-114">La transaction en cours a tenté de mettre à jour un enregistrement qui a été mis à jour depuis le début de cette transaction.</span><span class="sxs-lookup"><span data-stu-id="0ee13-114">The current transaction attempted to update a record that has been updated since this transaction started.</span></span> <span data-ttu-id="0ee13-115">La transaction a été abandonnée.</span><span class="sxs-lookup"><span data-stu-id="0ee13-115">The transaction was aborted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ee13-116">Explication</span><span class="sxs-lookup"><span data-stu-id="0ee13-116">Explanation</span></span>  
 <span data-ttu-id="0ee13-117">La transaction a rencontré un conflit d'écriture/écriture et l'instruction s'est arrêtée.</span><span class="sxs-lookup"><span data-stu-id="0ee13-117">The transaction encountered a write/write conflict and the statement terminated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ee13-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0ee13-118">User Action</span></span>  
 <span data-ttu-id="0ee13-119">Recommencez l'opération ultérieurement dans une autre transaction.</span><span class="sxs-lookup"><span data-stu-id="0ee13-119">Retry the operation later in a different transaction.</span></span> <span data-ttu-id="0ee13-120">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="0ee13-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee13-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ee13-121">See Also</span></span>  
 [<span data-ttu-id="0ee13-122">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="0ee13-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
