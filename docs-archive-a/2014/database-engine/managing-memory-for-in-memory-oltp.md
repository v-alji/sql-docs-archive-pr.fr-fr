---
title: Gestion de la mémoire pour l’OLTP en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: d82f21fa-6be1-4723-a72e-f2526fafd1b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90f9b638697d59a0a573a9a31c0a5faade23e870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706700"
---
# <a name="managing-memory-for-in-memory-oltp"></a><span data-ttu-id="cbb8d-102">Gestion de la mémoire pour l'OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="cbb8d-102">Managing Memory for In-Memory OLTP</span></span>
  <span data-ttu-id="cbb8d-103">Les tables mémoire optimisées nécessitent suffisamment de mémoire pour conserver tous les index et les lignes en mémoire.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-103">Memory-optimized tables require that sufficient memory exist to keep all of the rows and indexes in memory.</span></span> <span data-ttu-id="cbb8d-104">Dans la mesure où la mémoire est une ressource limitée, il est important de comprendre et de gérer l'utilisation de la mémoire sur votre système.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-104">Because memory is a finite resource, it is important that you understand and manage memory usage on your system.</span></span> <span data-ttu-id="cbb8d-105">Les rubriques de cette section traitent de scénarios courants d'utilisation et de gestion de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-105">The topics in this section cover common memory use and management scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cbb8d-106">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="cbb8d-106">In this section</span></span>  
  
|<span data-ttu-id="cbb8d-107">Section</span><span class="sxs-lookup"><span data-stu-id="cbb8d-107">Section</span></span>|<span data-ttu-id="cbb8d-108">Description</span><span class="sxs-lookup"><span data-stu-id="cbb8d-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbb8d-109">Estimer les besoins en mémoire des tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="cbb8d-109">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)|<span data-ttu-id="cbb8d-110">Estimez les besoins en mémoire d’une table.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-110">Estimate a table's memory needs.</span></span>|  
|[<span data-ttu-id="cbb8d-111">Lier une base de données avec des tables mémoire optimisées à un pool de ressources</span><span class="sxs-lookup"><span data-stu-id="cbb8d-111">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md)|<span data-ttu-id="cbb8d-112">Procédure pas à pas pour lier une base de données à un pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-112">Step by step walkthrough to bind a database with a resource pool.</span></span>|  
|[<span data-ttu-id="cbb8d-113">Surveiller l’utilisation de la mémoire et résoudre les problèmes connexes</span><span class="sxs-lookup"><span data-stu-id="cbb8d-113">Monitor and Troubleshoot Memory Usage</span></span>](../relational-databases/in-memory-oltp/monitor-and-troubleshoot-memory-usage.md)|<span data-ttu-id="cbb8d-114">Outils que vous pouvez utiliser pour surveiller l'utilisation de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-114">Tools you can use to monitor your memory usage.</span></span> <span data-ttu-id="cbb8d-115">Couvre également le dépannage si l'utilisation de la mémoire est trop intensive.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-115">Also covers troubleshooting if memory usage gets too high.</span></span>|  
|[<span data-ttu-id="cbb8d-116">Résoudre les problèmes de mémoire insuffisante</span><span class="sxs-lookup"><span data-stu-id="cbb8d-116">Resolve Out Of Memory Issues</span></span>](../relational-databases/in-memory-oltp/resolve-out-of-memory-issues.md)|<span data-ttu-id="cbb8d-117">Étapes pour récupérer d'une situation d'insuffisance de mémoire.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-117">Steps to recover from an OOM (Out of Memory) situation.</span></span>|  
|[<span data-ttu-id="cbb8d-118">Restaurer une base de données et la lier à un pool de ressources</span><span class="sxs-lookup"><span data-stu-id="cbb8d-118">Restore a Database and Bind it to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md)|<span data-ttu-id="cbb8d-119">Étapes pour restaurer une base de données [!INCLUDE[hek_2](../includes/hek-2-md.md)] et la lier à un pool de ressources nommé.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-119">Steps to restore an [!INCLUDE[hek_2](../includes/hek-2-md.md)] database and bind it to a named resource pool.</span></span>|  
|[<span data-ttu-id="cbb8d-120">Garbage collection de l'OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="cbb8d-120">In-Memory OLTP Garbage Collection</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-garbage-collection.md)|<span data-ttu-id="cbb8d-121">Comprendre comment le garbage collection fonctionne sur les lignes supprimées.</span><span class="sxs-lookup"><span data-stu-id="cbb8d-121">Understand how garbage collection operates on deleted rows.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbb8d-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbb8d-122">See Also</span></span>  
 [<span data-ttu-id="cbb8d-123">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="cbb8d-123">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
