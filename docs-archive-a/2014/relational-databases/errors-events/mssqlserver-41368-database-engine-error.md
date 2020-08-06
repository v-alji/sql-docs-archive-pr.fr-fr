---
title: MSSQLSERVER_41368 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41368 (Database Engine error)
ms.assetid: abc71559-4c4d-4cce-a08f-3299dd167842
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 10e187223a3f35b4b21ede6965e3c9efea2e30c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699630"
---
# <a name="mssqlserver_41368"></a><span data-ttu-id="817c1-102">MSSQLSERVER_41368</span><span class="sxs-lookup"><span data-stu-id="817c1-102">MSSQLSERVER_41368</span></span>
    
## <a name="details"></a><span data-ttu-id="817c1-103">Détails</span><span class="sxs-lookup"><span data-stu-id="817c1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="817c1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="817c1-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="817c1-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="817c1-105">Event ID</span></span>|<span data-ttu-id="817c1-106">41368</span><span class="sxs-lookup"><span data-stu-id="817c1-106">41368</span></span>|  
|<span data-ttu-id="817c1-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="817c1-107">Event Source</span></span>|<span data-ttu-id="817c1-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="817c1-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="817c1-109">Composant</span><span class="sxs-lookup"><span data-stu-id="817c1-109">Component</span></span>|<span data-ttu-id="817c1-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="817c1-110">SQLEngine</span></span>|  
|<span data-ttu-id="817c1-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="817c1-111">Symbolic Name</span></span>|<span data-ttu-id="817c1-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="817c1-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="817c1-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="817c1-113">Message Text</span></span>|<span data-ttu-id="817c1-114">L'accès aux tables optimisées en mémoire selon le niveau d'isolement READ COMMITTED est pris en charge uniquement pour les transactions validées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="817c1-114">Accessing memory optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="817c1-115">Cela n'est pas pris en charge pour les transactions explicites ou implicites.</span><span class="sxs-lookup"><span data-stu-id="817c1-115">It is not supported for explicit or implicit transactions.</span></span> <span data-ttu-id="817c1-116">Spécifiez un niveau d'isolement pris en charge pour la table optimisée en mémoire à l'aide d'un indicateur de table, comme WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="817c1-116">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="817c1-117">Explication</span><span class="sxs-lookup"><span data-stu-id="817c1-117">Explanation</span></span>  
 <span data-ttu-id="817c1-118">L'accès aux tables optimisées en mémoire selon le niveau d'isolement READ COMMITTED est pris en charge uniquement pour les transactions validées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="817c1-118">Accessing memory-optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="817c1-119">Pour plus d’informations, consultez [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="817c1-119">For more information, see [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span></span>  
  
 <span data-ttu-id="817c1-120">Lors de l'accès à une table optimisée en mémoire à partir d'une transaction explicite démarrée par BEGIN TRANSACTION, ou à partir d'une transaction implicite, si IMPLICIT_TRANSACTIONS a la valeur ON, le niveau d'isolement READ COMMITTED n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="817c1-120">When accessing a memory-optimized table from an explicit transaction that was started with BEGIN TRANSACTION, or from an implicit transaction, if IMPLICIT_TRANSACTIONS is set to ON, the READ COMMITTED isolation level is not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="817c1-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="817c1-121">User Action</span></span>  
 <span data-ttu-id="817c1-122">Lors de l'accès à une table optimisée en mémoire à partir d'une transaction READ COMMITTED implicite ou explicite, utilisez SNAPSHOT pour accéder à la table.</span><span class="sxs-lookup"><span data-stu-id="817c1-122">When accessing a memory-optimized table from an explicit or implicit READ COMMITTED transaction, use SNAPSHOT to access the table.</span></span> <span data-ttu-id="817c1-123">Pour ce faire, vous pouvez utiliser l’indicateur de table WITH (SNAPSHOT) (pour plus d’informations, consultez [instructions pour les niveaux d’isolation des transactions avec des tables optimisées en mémoire](../in-memory-oltp/memory-optimized-tables.md)) ou définir l’option de base de données MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT sur on (pour plus d’informations, consultez [options ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span><span class="sxs-lookup"><span data-stu-id="817c1-123">This can be achieved by using the table hint WITH (SNAPSHOT) (for more information, see [Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md)) or by setting the database option MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT to ON (for more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="817c1-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="817c1-124">See Also</span></span>  
 [<span data-ttu-id="817c1-125">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="817c1-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
