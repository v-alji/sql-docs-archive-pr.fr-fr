---
title: Migration vers OLTP en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 405cdac5-a0d4-47a4-9180-82876b773b82
author: rothja
ms.author: jroth
ms.openlocfilehash: ed764ce52d41d76667213b846cec51b26f634a27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709452"
---
# <a name="migrating-to-in-memory-oltp"></a><span data-ttu-id="8adae-102">Migration vers OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="8adae-102">Migrating to In-Memory OLTP</span></span>
  <span data-ttu-id="8adae-103">Cette section explique comment migrer des objets de base de données pour utiliser l'OLTP en mémoire.</span><span class="sxs-lookup"><span data-stu-id="8adae-103">This section discusses how to migrate database objects to use In-Memory OLTP.</span></span>  
  
-   [<span data-ttu-id="8adae-104">Déterminer si un tableau ou une procédure stockée doit être déplacée vers l’OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="8adae-104">Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP</span></span>](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)  
  
-   [<span data-ttu-id="8adae-105">Conseil d’optimisation par mémoire</span><span class="sxs-lookup"><span data-stu-id="8adae-105">Memory Optimization Advisor</span></span>](memory-optimization-advisor.md)  
  
-   [<span data-ttu-id="8adae-106">Conseiller de compilation native</span><span class="sxs-lookup"><span data-stu-id="8adae-106">Native Compilation Advisor</span></span>](native-compilation-advisor.md)  
  
-   [<span data-ttu-id="8adae-107">Constructions Transact-SQL non prises en charge par In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="8adae-107">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
-   [<span data-ttu-id="8adae-108">Implémentation de colonnes LOB dans une table mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="8adae-108">Implementing LOB Columns in a Memory-Optimized Table</span></span>](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="8adae-109">Implémentation de SQL_VARIANT dans un tableau mémoire optimisé</span><span class="sxs-lookup"><span data-stu-id="8adae-109">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="8adae-110">Problèmes de migration pour les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="8adae-110">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="8adae-111">Migration de colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="8adae-111">Migrating Computed Columns</span></span>](migrating-computed-columns.md)  
  
-   [<span data-ttu-id="8adae-112">Migration de déclencheurs</span><span class="sxs-lookup"><span data-stu-id="8adae-112">Migrating Triggers</span></span>](migrating-triggers.md)  
  
-   [<span data-ttu-id="8adae-113">Requêtes de bases de données croisées</span><span class="sxs-lookup"><span data-stu-id="8adae-113">Cross-Database Queries</span></span>](cross-database-queries.md)  
  
-   [<span data-ttu-id="8adae-114">Migration des contraintes de validation et de clé étrangère</span><span class="sxs-lookup"><span data-stu-id="8adae-114">Migrating Check and Foreign Key Constraints</span></span>](../../database-engine/migrating-check-and-foreign-key-constraints.md)  
  
-   [<span data-ttu-id="8adae-115">Implémentation d'IDENTITY dans une table optimisée en mémoire</span><span class="sxs-lookup"><span data-stu-id="8adae-115">Implementing IDENTITY in a Memory-Optimized Table</span></span>](implementing-identity-in-a-memory-optimized-table.md)  
  
 <span data-ttu-id="8adae-116">Pour plus d’informations sur les méthodologies de migration, consultez [OLTP en mémoire - Modèles de charge de travail courants et considérations relatives à la migration](https://msdn.microsoft.com/library/dn673538.aspx).</span><span class="sxs-lookup"><span data-stu-id="8adae-116">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8adae-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8adae-117">See Also</span></span>  
 <span data-ttu-id="8adae-118">[OLTP en mémoire &#40;optimisation en mémoire&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="8adae-118">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 [<span data-ttu-id="8adae-119">Estimer les besoins en mémoire des tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="8adae-119">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
