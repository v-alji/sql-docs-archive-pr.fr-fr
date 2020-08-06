---
title: MSSQLSERVER_17083 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17083 (Database Engine error)
ms.assetid: 6c83737d-0531-4fd9-88f6-2da5a150532d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 598cf9b0182178aa13a6d8b965ac10bedaaf5d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612890"
---
# <a name="mssqlserver_17083"></a><span data-ttu-id="dce2b-102">MSSQLSERVER_17083</span><span class="sxs-lookup"><span data-stu-id="dce2b-102">MSSQLSERVER_17083</span></span>
    
## <a name="details"></a><span data-ttu-id="dce2b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="dce2b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dce2b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="dce2b-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="dce2b-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="dce2b-105">Event ID</span></span>|<span data-ttu-id="dce2b-106">17083</span><span class="sxs-lookup"><span data-stu-id="dce2b-106">17083</span></span>|  
|<span data-ttu-id="dce2b-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="dce2b-107">Event Source</span></span>|<span data-ttu-id="dce2b-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dce2b-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dce2b-109">Composant</span><span class="sxs-lookup"><span data-stu-id="dce2b-109">Component</span></span>|<span data-ttu-id="dce2b-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dce2b-110">SQLEngine</span></span>|  
|<span data-ttu-id="dce2b-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="dce2b-111">Symbolic Name</span></span>|<span data-ttu-id="dce2b-112">P3_HEKATON_NOT_ATOMIC</span><span class="sxs-lookup"><span data-stu-id="dce2b-112">P3_HEKATON_NOT_ATOMIC</span></span>|  
|<span data-ttu-id="dce2b-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="dce2b-113">Message Text</span></span>|<span data-ttu-id="dce2b-114">Le corps d'une procédure stockée compilée en mode natif doit être un bloc ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="dce2b-114">The body of a natively compiled stored procedure must be an ATOMIC block.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dce2b-115">Explication</span><span class="sxs-lookup"><span data-stu-id="dce2b-115">Explanation</span></span>  
 <span data-ttu-id="dce2b-116">Le corps d'une procédure stockée compilée en mode natif n'avait pas un bloc ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="dce2b-116">The body of a natively compiled stored procedure did not have an ATOMIC block.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dce2b-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="dce2b-117">User Action</span></span>  
 <span data-ttu-id="dce2b-118">Une procédure stockée compilée en mode natif doit contenir un bloc ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="dce2b-118">A natively compiled stored procedure must contain an ATOMIC block.</span></span> <span data-ttu-id="dce2b-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="dce2b-119">For example:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="dce2b-120">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="dce2b-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce2b-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dce2b-121">See Also</span></span>  
 [<span data-ttu-id="dce2b-122">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="dce2b-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
