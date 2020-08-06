---
title: MSSQLSERVER_41396 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41396 (Database Engine error)
ms.assetid: 4ff04042-8367-46f3-8a16-c94682d6eedb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2386c805b61631c9b843753d74ba6616e7344223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699618"
---
# <a name="mssqlserver_41396"></a><span data-ttu-id="0ca05-102">MSSQLSERVER_41396</span><span class="sxs-lookup"><span data-stu-id="0ca05-102">MSSQLSERVER_41396</span></span>
    
## <a name="details"></a><span data-ttu-id="0ca05-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0ca05-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ca05-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0ca05-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0ca05-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0ca05-105">Event ID</span></span>|<span data-ttu-id="0ca05-106">41396</span><span class="sxs-lookup"><span data-stu-id="0ca05-106">41396</span></span>|  
|<span data-ttu-id="0ca05-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0ca05-107">Event Source</span></span>|<span data-ttu-id="0ca05-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0ca05-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0ca05-109">Composant</span><span class="sxs-lookup"><span data-stu-id="0ca05-109">Component</span></span>|<span data-ttu-id="0ca05-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0ca05-110">SQLEngine</span></span>|  
|<span data-ttu-id="0ca05-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0ca05-111">Symbolic Name</span></span>|<span data-ttu-id="0ca05-112">MAX_SORT_ROWS_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="0ca05-112">MAX_SORT_ROWS_EXCEEDED</span></span>|  
|<span data-ttu-id="0ca05-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0ca05-113">Message Text</span></span>|<span data-ttu-id="0ca05-114">L'opération de tri a dépassé la limite de la mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="0ca05-114">The sort operation exceeded the buffer limit.</span></span> <span data-ttu-id="0ca05-115">L'exécution de la procédure stockée a été abandonnée.</span><span class="sxs-lookup"><span data-stu-id="0ca05-115">The stored procedure execution was aborted.</span></span> <span data-ttu-id="0ca05-116">Consultez la documentation en ligne de SQL Server pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="0ca05-116">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ca05-117">Explication</span><span class="sxs-lookup"><span data-stu-id="0ca05-117">Explanation</span></span>  
 <span data-ttu-id="0ca05-118">Les procédures stockées compilées en mode natif effectuent des opérations de tri en mémoire.</span><span class="sxs-lookup"><span data-stu-id="0ca05-118">Natively compiled stored procedures perform sort operations in memory.</span></span> <span data-ttu-id="0ca05-119">Il existe une limite sur la taille du tampon de tri.</span><span class="sxs-lookup"><span data-stu-id="0ca05-119">There is a limit on the size of the sort buffer.</span></span> <span data-ttu-id="0ca05-120">Cette erreur indique que la taille du tampon de tri dépasse cette limite.</span><span class="sxs-lookup"><span data-stu-id="0ca05-120">This error means that the size of the sort buffer exceeds this limit.</span></span> <span data-ttu-id="0ca05-121">L'opération de tri et l'exécution de la procédure stockée ont été abandonnées.</span><span class="sxs-lookup"><span data-stu-id="0ca05-121">The sort operation and the stored procedure execution aborted.</span></span>  
  
 <span data-ttu-id="0ca05-122">La taille de chaque ligne ou entrée dans le tampon de tri est déterminée par le nombre de lignes triées ainsi que par le nombre de jointures et le nombre et le type de fonctions d'agrégation dans la requête.</span><span class="sxs-lookup"><span data-stu-id="0ca05-122">The size of each row or entry in the sort buffer is determined by the number of rows sorted as well as the number of joins and the number and type of aggregate functions in the query.</span></span> <span data-ttu-id="0ca05-123">En simplifiant la requête, vous pouvez réduire la taille de chaque ligne, afin de pouvoir faire tenir plus de lignes dans le tampon de tri.</span><span class="sxs-lookup"><span data-stu-id="0ca05-123">By simplifying the query, you can reduce the size of each row thereby fitting more rows in the sort buffer.</span></span> <span data-ttu-id="0ca05-124">La taille des lignes dans les tables de base n'affecte pas la taille de chaque ligne ou entrée dans le tampon de tri.</span><span class="sxs-lookup"><span data-stu-id="0ca05-124">The size of the rows in the base tables does not affect the size of each row or entry in the sort buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ca05-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0ca05-125">User Action</span></span>  
 <span data-ttu-id="0ca05-126">Sélectionnez moins de lignes ou diminuez la complexité de la requête en supprimant des jointures ou des fonctions d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="0ca05-126">Select fewer rows or decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca05-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ca05-127">See Also</span></span>  
 [<span data-ttu-id="0ca05-128">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="0ca05-128">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
