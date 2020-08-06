---
title: Tables optimisées en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 14dddf81-b502-49dc-a6b6-d18b1ae32d2b
author: rothja
ms.author: jroth
ms.openlocfilehash: 73430505e55230daf31c492d882eadeb6d35d29f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708359"
---
# <a name="memory-optimized-tables"></a><span data-ttu-id="95430-102">Tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="95430-102">Memory-Optimized Tables</span></span>
  <span data-ttu-id="95430-103">L'OLTP en mémoire[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contribue à améliorer les performances des applications OLTP grâce à un accès rapide aux données optimisées en mémoire, à la compilation en mode natif de la logique métier et aux algorithmes de verrous (internes et externes) gratuits.</span><span class="sxs-lookup"><span data-stu-id="95430-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] In-Memory OLTP helps improve performance of OLTP applications through efficient, memory-optimized data access, native compilation of business logic, and lock- and latch free algorithms.</span></span> <span data-ttu-id="95430-104">La fonctionnalité OLTP en mémoire comprend les tables optimisées en mémoire et les types de tables, ainsi que la compilation en mode natif des procédures stockées [!INCLUDE[tsql](../../includes/tsql-md.md)] pour permettre un accès efficace à ces tables.</span><span class="sxs-lookup"><span data-stu-id="95430-104">The In-Memory OLTP feature includes memory-optimized tables and table types, as well as native compilation of [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures for efficient access to these tables.</span></span>  
  
 <span data-ttu-id="95430-105">Pour plus d'informations sur les tables optimisées en mémoire, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="95430-105">For more information about memory-optimized tables, see:</span></span>  
  
-   [<span data-ttu-id="95430-106">Introduction aux tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="95430-106">Introduction to Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
     <span data-ttu-id="95430-107">Explique de façon détaillée ce que sont les tables optimisées en mémoire et fournit des informations sur la durabilité des données et l'accès aux données dans des tables optimisées en mémoire, ainsi que sur la performance et l'évolutivité.</span><span class="sxs-lookup"><span data-stu-id="95430-107">Details what memory-optimized tables are and provides information about data durability, accessing data in memory-optimized tables, and performance and scalability.</span></span>  
  
-   [<span data-ttu-id="95430-108">Compilation en mode natif de tables et de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="95430-108">Native Compilation of Tables and Stored Procedures</span></span>](../in-memory-oltp/natively-compiled-stored-procedures.md)  
  
     <span data-ttu-id="95430-109">Explique de façon détaillée comment les tables optimisées en mémoire et les procédures stockées compilées en mode natif sont compilées en DLL, et contient des considérations relatives à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="95430-109">Details how memory-optimized tables and natively compiled stored procedures are compiled into DLLs, and provides related security considerations.</span></span>  
  
-   [<span data-ttu-id="95430-110">Modification des tables à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="95430-110">Altering Memory-Optimized Tables</span></span>](altering-memory-optimized-tables.md)  
  
     <span data-ttu-id="95430-111">Directives pour la mise à jour des tables optimisées en mémoire (y compris la modification des colonnes des tables, des index et de bucket_count).</span><span class="sxs-lookup"><span data-stu-id="95430-111">Guidelines for updating memory-optimized tables (including changing table columns, indexes, and bucket_count).</span></span>  
  
-   [<span data-ttu-id="95430-112">Comprendre les transactions sur les tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="95430-112">Understanding Transactions on Memory-Optimized Tables</span></span>](../../database-engine/understanding-transactions-on-memory-optimized-tables.md)  
  
     <span data-ttu-id="95430-113">Cette section contient plusieurs rubriques relatives à la réalisation de transactions sur les tables optimisées en mémoire, y compris les niveaux d'isolement des transactions et les transactions multiconteneurs.</span><span class="sxs-lookup"><span data-stu-id="95430-113">This section provides several topics related to performing transactions on memory-optimized tables including transaction isolation levels, and cross-container transactions.</span></span>  
  
-   [<span data-ttu-id="95430-114">Modèle d’application pour partitionner des tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="95430-114">Application Pattern for Partitioning Memory-Optimized Tables</span></span>](application-pattern-for-partitioning-memory-optimized-tables.md)  
  
     <span data-ttu-id="95430-115">Exemple de code détaillé montrant comment émuler des tables partitionnées lors de l'utilisation de tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="95430-115">Detailed code sample that shows how to emulate partitioned tables when using memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="95430-116">Statistiques pour les tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="95430-116">Statistics for Memory-Optimized Tables</span></span>](statistics-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="95430-117">Explique de façon détaillée comment les statistiques sont compilées pour les tables optimisées en mémoire, et comment gérer et mettre à jour manuellement ces statistiques.</span><span class="sxs-lookup"><span data-stu-id="95430-117">Details how statistics are compiled for memory-optimized tables and how to maintain and manually update statistics for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="95430-118">Classements et pages de codes</span><span class="sxs-lookup"><span data-stu-id="95430-118">Collations and Code Pages</span></span>](../../database-engine/collations-and-code-pages.md)  
  
     <span data-ttu-id="95430-119">Explique de façon détaillée les restrictions sur les classements et les pages de codes pris en charge pour les tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="95430-119">Details the restrictions on supported collations and code pages for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="95430-120">Taille de la table et des lignes dans les tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="95430-120">Table and Row Size in Memory-Optimized Tables</span></span>](table-and-row-size-in-memory-optimized-tables.md)  
  
     <span data-ttu-id="95430-121">Explique de façon détaillée la limite de 8 060 octets sur les lignes des tables optimisées en mémoire et donne un exemple de calcul de la taille d'une table et des lignes.</span><span class="sxs-lookup"><span data-stu-id="95430-121">Details the 8060 byte limit on memory-optimized table rows, and provides an example for calculating table and row sizes.</span></span>  
  
-   [<span data-ttu-id="95430-122">Guide du traitement des requêtes pour les tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="95430-122">A Guide to Query Processing for Memory-Optimized Tables</span></span>](a-guide-to-query-processing-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="95430-123">Fournit une vue d'ensemble du traitement des requêtes pour les tables optimisées en mémoire et les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="95430-123">Provides an overview of query processing for both memory-optimized tables, and natively compiled stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95430-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95430-124">See Also</span></span>  
 [<span data-ttu-id="95430-125">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="95430-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
