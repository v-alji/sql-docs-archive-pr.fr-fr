---
title: Fonctionnement des transactions sur les tables optimisées en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 06075248-705e-4563-9371-b64cd609793c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0671bba8b7a0bda27ea27cf059cb9e3b1bb87b2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701525"
---
# <a name="understanding-transactions-on-memory-optimized-tables"></a><span data-ttu-id="b3e6f-102">Comprendre les transactions sur les tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="b3e6f-102">Understanding Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="b3e6f-103">Les transactions accèdent aux tables mémoire optimisées à l'aide d'un type de contrôle d'accès concurrentiel optimiste et multiversion.</span><span class="sxs-lookup"><span data-stu-id="b3e6f-103">Transactions access memory-optimized tables using a form of optimistic, multi-version concurrency control.</span></span> <span data-ttu-id="b3e6f-104">Cela signifie qu'il existe différentes versions de données.</span><span class="sxs-lookup"><span data-stu-id="b3e6f-104">This means that there are different versions of the data.</span></span> <span data-ttu-id="b3e6f-105">Chaque transaction opère sur sa propre version de base de données cohérente d'un point de vue transactionnel, indépendamment des autres transactions exécutées simultanément.</span><span class="sxs-lookup"><span data-stu-id="b3e6f-105">Each transaction operates on its own transactionally consistent version of the database, independent from other concurrently running transactions.</span></span> <span data-ttu-id="b3e6f-106">De plus, les transactions opèrent dans l'hypothèse optimiste qu'il n'y a aucun conflit avec d'autres transactions simultanées.</span><span class="sxs-lookup"><span data-stu-id="b3e6f-106">In addition, transactions operate under the optimistic assumption that there will be no conflicts with other, concurrent, transactions.</span></span> <span data-ttu-id="b3e6f-107">Cela évite d'utiliser des verrous, mais nécessite que le système détecte les conflits et mette fin à l'une des transactions impliquées.</span><span class="sxs-lookup"><span data-stu-id="b3e6f-107">This avoids the need to use locks, but does require the system to detect conflicts and terminate one of the conflicting transactions.</span></span> <span data-ttu-id="b3e6f-108">Des conflits peuvent se produire uniquement pour les transactions d'écriture-écriture et les transactions de lecture-écriture.</span><span class="sxs-lookup"><span data-stu-id="b3e6f-108">Conflicts can occur only for write-write transactions and for read-write transactions.</span></span> <span data-ttu-id="b3e6f-109">S'il existe un conflit d'écriture-écriture, une transaction d'écriture est terminée.</span><span class="sxs-lookup"><span data-stu-id="b3e6f-109">If there is a write-write conflict, one write transaction is terminated.</span></span>  
  
 <span data-ttu-id="b3e6f-110">Il existe des similitudes entre le contrôle d'accès concurrentiel des tables mémoire optimisées et le contrôle d'accès concurrentiel des tables sur disque pour les niveaux d'isolation des transactions READ_COMMITTED_SNAPSHOT et SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="b3e6f-110">There are similarities between the concurrency control for memory-optimized tables and the concurrency control for disk-based tables for the READ_COMMITTED_SNAPSHOT and SNAPSHOT transaction isolation levels.</span></span> <span data-ttu-id="b3e6f-111">(Pour plus d’informations sur les tables sur disque, consultez [niveaux d’isolement basés sur le contrôle de version de ligne dans la moteur de base de données](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span><span class="sxs-lookup"><span data-stu-id="b3e6f-111">(For more information about disk-based tables, see [Row Versioning-based Isolation Levels in the Database Engine](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span></span>  
  
## <a name="topics-in-this-section"></a><span data-ttu-id="b3e6f-112">Rubriques de cette section</span><span class="sxs-lookup"><span data-stu-id="b3e6f-112">Topics in This Section</span></span>  
 <span data-ttu-id="b3e6f-113">Cette section sur les transactions dans les tables mémoire optimisées contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3e6f-113">This section on transactions in memory-optimized tables includes the following topics:</span></span>  
  
-   [<span data-ttu-id="b3e6f-114">Instructions pour les niveaux d'isolement des transactions sur les tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="b3e6f-114">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
-   [<span data-ttu-id="b3e6f-115">Instructions pour la logique de nouvelle tentative des transactions sur des tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="b3e6f-115">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="b3e6f-116">Transactions dans les tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="b3e6f-116">Transactions in Memory-Optimized Tables</span></span>](transactions-in-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="b3e6f-117">Niveaux d'isolement des transactions</span><span class="sxs-lookup"><span data-stu-id="b3e6f-117">Transaction Isolation Levels</span></span>](transaction-isolation-levels.md)  
  
-   [<span data-ttu-id="b3e6f-118">Transactions entre conteneurs</span><span class="sxs-lookup"><span data-stu-id="b3e6f-118">Cross-Container Transactions</span></span>](cross-container-transactions.md)  
  
 <span data-ttu-id="b3e6f-119">Pour plus d’informations, consultez [Contrôler la durabilité d’une transaction](../relational-databases/logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="b3e6f-119">For more information, see [Control Transaction Durability](../relational-databases/logs/control-transaction-durability.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e6f-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b3e6f-120">See Also</span></span>  
 [<span data-ttu-id="b3e6f-121">Tables à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="b3e6f-121">Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
