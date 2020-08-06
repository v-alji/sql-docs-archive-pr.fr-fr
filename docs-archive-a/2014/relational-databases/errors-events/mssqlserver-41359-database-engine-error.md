---
title: MSSQLSERVER_41359 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41359 (Database Engine error)
ms.assetid: 02b717c7-9170-4676-b0f6-4dec9eb5b5d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cf45a117dcda0827672c6072c603a1fc0866a33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613462"
---
# <a name="mssqlserver_41359"></a><span data-ttu-id="b8701-102">MSSQLSERVER_41359</span><span class="sxs-lookup"><span data-stu-id="b8701-102">MSSQLSERVER_41359</span></span>
    
## <a name="details"></a><span data-ttu-id="b8701-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b8701-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8701-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b8701-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="b8701-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b8701-105">Event ID</span></span>|<span data-ttu-id="b8701-106">41359</span><span class="sxs-lookup"><span data-stu-id="b8701-106">41359</span></span>|  
|<span data-ttu-id="b8701-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b8701-107">Event Source</span></span>|<span data-ttu-id="b8701-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b8701-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b8701-109">Composant</span><span class="sxs-lookup"><span data-stu-id="b8701-109">Component</span></span>|<span data-ttu-id="b8701-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b8701-110">SQLEngine</span></span>|  
|<span data-ttu-id="b8701-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b8701-111">Symbolic Name</span></span>|<span data-ttu-id="b8701-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="b8701-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="b8701-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b8701-113">Message Text</span></span>|<span data-ttu-id="b8701-114">Une requête qui accède à des tables optimisées en mémoire selon le niveau d'isolement READ COMMITTED ne peut pas accéder aux tables sur disque lorsque l'option READ_COMMITTED_SNAPSHOT de la base de données a la valeur ON.</span><span class="sxs-lookup"><span data-stu-id="b8701-114">A query that accesses memory optimized tables using the READ COMMITTED isolation level, cannot access disk based tables when the database option READ_COMMITTED_SNAPSHOT is set to ON.</span></span> <span data-ttu-id="b8701-115">Spécifiez un niveau d'isolement pris en charge pour la table optimisée en mémoire à l'aide d'un indicateur de table, comme WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="b8701-115">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b8701-116">Explication</span><span class="sxs-lookup"><span data-stu-id="b8701-116">Explanation</span></span>  
 <span data-ttu-id="b8701-117">La base de données avec READ_COMMITTED_SNAPSHOT=ON ne prend pas en charge les transactions qui accèdent aux tables optimisées en mémoire et aux tables sur disque.</span><span class="sxs-lookup"><span data-stu-id="b8701-117">The database with READ_COMMITTED_SNAPSHOT=ON does not support the transactions that access both memory-optimized tables and disk based tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b8701-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b8701-118">User Action</span></span>  
 <span data-ttu-id="b8701-119">Définissez READ_COMMITTED_SNAPSHOT sur OFF, ou fournissez un niveau d’isolement pris en charge pour la table optimisée en mémoire à l’aide d’un indicateur au niveau de la table, comme WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="b8701-119">Set READ_COMMITTED_SNAPSHOT to OFF or supply a supported isolation level for the memory-optimized table using a table-level hint, such as WITH (SNAPSHOT).</span></span> <span data-ttu-id="b8701-120">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="b8701-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8701-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8701-121">See Also</span></span>  
 [<span data-ttu-id="b8701-122">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="b8701-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
