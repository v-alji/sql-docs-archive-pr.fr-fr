---
title: Création et gestion du stockage des objets mémoire optimisés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 622aabe6-95c7-42cc-8768-ac2e679c5089
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 118e5e582a284023dd8e5cc71629d635e79fb989
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604015"
---
# <a name="creating-and-managing-storage-for-memory-optimized-objects"></a><span data-ttu-id="ecacb-102">Création et gestion du stockage des objets mémoire optimisés</span><span class="sxs-lookup"><span data-stu-id="ecacb-102">Creating and Managing Storage for Memory-Optimized Objects</span></span>
  <span data-ttu-id="ecacb-103">Le moteur [!INCLUDE[hek_2](../../includes/hek-2-md.md)] est intégré dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ce qui vous permet d’avoir des tables optimisées en mémoire et des tables sur disque (traditionnelles) dans la même base de données.</span><span class="sxs-lookup"><span data-stu-id="ecacb-103">The [!INCLUDE[hek_2](../../includes/hek-2-md.md)] engine is integrated into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which lets you have both memory-optimized tables and (traditional) disk-based tables in the same database.</span></span> <span data-ttu-id="ecacb-104">Toutefois, la structure de stockage des tables optimisées en mémoire est différente de celle des tables sur disque.</span><span class="sxs-lookup"><span data-stu-id="ecacb-104">However, the storage structure for memory-optimized tables is different from disk-based tables.</span></span>  
  
 <span data-ttu-id="ecacb-105">Les principales caractéristiques du stockage des tables sur disque sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ecacb-105">Storage for disk-based table has following key attributes:</span></span>  
  
-   <span data-ttu-id="ecacb-106">Elles sont mappées à groupe de fichiers contenant un ou plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="ecacb-106">Mapped to a filegroup and the filegroup contains one or more files.</span></span>  
  
-   <span data-ttu-id="ecacb-107">Chaque fichier est divisé en étendues de 8 pages de 8 Ko chacune.</span><span class="sxs-lookup"><span data-stu-id="ecacb-107">Each file is divided into extents of 8 pages and each page is of size 8K bytes.</span></span>  
  
-   <span data-ttu-id="ecacb-108">Une étendue peut être partagée entre plusieurs tables, mais il existe une correspondance univoque entre une page allouée et la table ou l’index.</span><span class="sxs-lookup"><span data-stu-id="ecacb-108">An extent can be shared across multiple tables, but a there is 1-to-1 mapping between an allocated page and the table or index.</span></span> <span data-ttu-id="ecacb-109">En d’autres termes, une page ne peut pas contenir de lignes issues de plusieurs tables ou index.</span><span class="sxs-lookup"><span data-stu-id="ecacb-109">In other words, a page can't have rows from two or more tables or index.</span></span>  
  
-   <span data-ttu-id="ecacb-110">Les données sont placées dans la mémoire (le pool de mémoires tampons) en fonction des besoins et les pages modifiées ou créées sont écrites de façon asynchrone sur le disque, générant essentiellement des E/S aléatoires.</span><span class="sxs-lookup"><span data-stu-id="ecacb-110">The data is moved into memory (the buffer pool) as needed and the modified or newly created pages are asynchronously written to the disk generating mostly random IO.</span></span>  
  
 <span data-ttu-id="ecacb-111">Les principales caractéristiques du stockage des tables optimisées en mémoire sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ecacb-111">Storage for memory-optimized tables has following key attributes:</span></span>  
  
-   <span data-ttu-id="ecacb-112">Toutes les tables mémoire optimisées sont mappées à un groupe de fichiers mémoire optimisé.</span><span class="sxs-lookup"><span data-stu-id="ecacb-112">All memory-optimized tables are mapped to a memory-optimized filegroup.</span></span> <span data-ttu-id="ecacb-113">Ce groupe de fichiers est créé à l'aide du groupe de fichiers de flux de fichier.</span><span class="sxs-lookup"><span data-stu-id="ecacb-113">This filegroup is built using the filestream filegroup.</span></span>  
  
-   <span data-ttu-id="ecacb-114">Il n’y a aucune page et les données sont conservées sur une ligne.</span><span class="sxs-lookup"><span data-stu-id="ecacb-114">There are no pages and the data is persisted as a row.</span></span>  
  
-   <span data-ttu-id="ecacb-115">Toutes les modifications apportées aux tables optimisées en mémoire sont stockées à la fin des fichiers actifs.</span><span class="sxs-lookup"><span data-stu-id="ecacb-115">All changes to memory-optimized tables are stored by appending to active files.</span></span> <span data-ttu-id="ecacb-116">La lecture et l’écriture des fichiers sont séquentielles.</span><span class="sxs-lookup"><span data-stu-id="ecacb-116">Both reading and writing to files is sequential.</span></span>  
  
-   <span data-ttu-id="ecacb-117">Une mise à jour correspond à une suppression suivie d’une insertion.</span><span class="sxs-lookup"><span data-stu-id="ecacb-117">An update is implemented as a delete followed by an insert.</span></span> <span data-ttu-id="ecacb-118">Les lignes supprimées ne sont pas immédiatement supprimées du stockage.</span><span class="sxs-lookup"><span data-stu-id="ecacb-118">The deleted rows are not immediately removed from the storage.</span></span> <span data-ttu-id="ecacb-119">Les lignes supprimées le sont par un processus d’arrière-plan, appelé MERGE, basé sur une stratégie et décrit dans [Durabilité pour les tables optimisées en mémoire](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ecacb-119">The deleted rows are removed by a background process, called MERGE, based on a policy as described in [Durability for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
-   <span data-ttu-id="ecacb-120">Contrairement aux tables sur disque, le stockage des tables optimisées en mémoire n’est pas compressé.</span><span class="sxs-lookup"><span data-stu-id="ecacb-120">Unlike disk-based tables, storage for memory-optimized tables is not compressed.</span></span> <span data-ttu-id="ecacb-121">Lors de la migration d’une table sur disque (ligne ou page) compressée vers une table optimisée en mémoire, vous devez prendre en compte la modification de taille.</span><span class="sxs-lookup"><span data-stu-id="ecacb-121">When migrating a compressed (ROW or PAGE) disk-based table to memory-optimized table, you will need to account for the change in size.</span></span>  
  
-   <span data-ttu-id="ecacb-122">Une table optimisée en mémoire peut être durable ou non durable.</span><span class="sxs-lookup"><span data-stu-id="ecacb-122">A memory-optimized table can be durable or can be non-durable.</span></span> <span data-ttu-id="ecacb-123">Vous devez simplement configurer le stockage des tables mémoire optimisées durables.</span><span class="sxs-lookup"><span data-stu-id="ecacb-123">You only need to configure storage for durable memory-optimize tables.</span></span>  
  
 <span data-ttu-id="ecacb-124">Cette section décrit les paires de fichiers de point de contrôle d'autres aspects du stockage des données dans des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="ecacb-124">This section describes checkpoint file pairs and other aspects of how data in memory-optimized tables is stored.</span></span>  
  
 <span data-ttu-id="ecacb-125">Rubriques de cette section :</span><span class="sxs-lookup"><span data-stu-id="ecacb-125">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="ecacb-126">Configuration du stockage des tables à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="ecacb-126">Configuring Storage for Memory-Optimized Tables</span></span>](configuring-storage-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="ecacb-127">Groupe de fichiers mémoire optimisé</span><span class="sxs-lookup"><span data-stu-id="ecacb-127">The Memory Optimized Filegroup</span></span>](the-memory-optimized-filegroup.md)  
  
-   [<span data-ttu-id="ecacb-128">Durabilité pour les tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="ecacb-128">Durability for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
-   [<span data-ttu-id="ecacb-129">Opération de point de contrôle pour les tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="ecacb-129">Checkpoint Operation for Memory-Optimized Tables</span></span>](checkpoint-operation-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="ecacb-130">Définition de la durabilité des objets mémoire optimisés</span><span class="sxs-lookup"><span data-stu-id="ecacb-130">Defining Durability for Memory-Optimized Objects</span></span>](defining-durability-for-memory-optimized-objects.md)  
  
-   [<span data-ttu-id="ecacb-131">Comparaison du stockage des tables sur disque et du stockage des tables à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="ecacb-131">Comparing Disk-Based Table Storage to Memory-Optimized Table Storage</span></span>](comparing-disk-based-table-storage-to-memory-optimized-table-storage.md)  
  
-   [<span data-ttu-id="ecacb-132">Surveiller et dépanner la fusion de paires de fichiers de données et de fichiers delta</span><span class="sxs-lookup"><span data-stu-id="ecacb-132">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>](../../database-engine/monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs.md)  
  
## <a name="see-also"></a><span data-ttu-id="ecacb-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ecacb-133">See Also</span></span>  
 [<span data-ttu-id="ecacb-134">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="ecacb-134">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
