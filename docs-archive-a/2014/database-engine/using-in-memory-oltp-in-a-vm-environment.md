---
title: Utilisation de l’OLTP en mémoire dans un environnement de machine virtuelle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 27ec7eb3-3a24-41db-aa65-2f206514c6f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83cf785fbcd2df9449d61e328e3bf8e374a6656d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700199"
---
# <a name="using-in-memory-oltp-in-a-vm-environment"></a><span data-ttu-id="af0e9-102">Utilisation de l’OLTP en mémoire dans un environnement de machine virtuelle</span><span class="sxs-lookup"><span data-stu-id="af0e9-102">Using In-Memory OLTP in a VM Environment</span></span>
  <span data-ttu-id="af0e9-103">La virtualisation de serveur vous permet de réduire les coûts d’exploitation et de capital informatique et d’optimiser l’efficacité informatique, grâce à des processus de configuration, de maintenance, de disponibilité, de sauvegarde et de récupération d’applications optimisés.</span><span class="sxs-lookup"><span data-stu-id="af0e9-103">Server virtualization can help you lower IT capital and operational costs and attain greater IT efficiency with improved application provisioning, maintenance, availability, and backup/recovery processes.</span></span> <span data-ttu-id="af0e9-104">Avec les progrès technologiques récents, les charges de travail de base de données complexes peuvent être consolidées plus aisément à l'aide de la virtualisation.</span><span class="sxs-lookup"><span data-stu-id="af0e9-104">With recent technological advances, complex database workloads can be more readily consolidated using virtualization.</span></span> <span data-ttu-id="af0e9-105">Cette rubrique porte sur les meilleures pratiques relatives à l’utilisation de [!INCLUDE[hek_1](../includes/hek-1-md.md)] dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="af0e9-105">This topic covers best practices for using [!INCLUDE[hek_1](../includes/hek-1-md.md)] in a virtualized environment.</span></span>  
  
##  <a name="memory-pre-allocation"></a><a name="bkmk_memoryPreAllocation"></a><span data-ttu-id="af0e9-106">Pré-allocation de mémoire</span><span class="sxs-lookup"><span data-stu-id="af0e9-106">Memory pre-allocation</span></span>  
 <span data-ttu-id="af0e9-107">Pour la mémoire dans un environnement virtualisé, de meilleures performances et une prise en charge améliorée sont essentielles.</span><span class="sxs-lookup"><span data-stu-id="af0e9-107">For memory in a virtualized environment, better performance and enhanced support are essential considerations.</span></span> <span data-ttu-id="af0e9-108">Vous devez pouvoir allouer rapidement de la mémoire aux machines virtuelles en fonction des exigences (charges de pointe et creuses) et garantir que la mémoire n'est pas gaspillée.</span><span class="sxs-lookup"><span data-stu-id="af0e9-108">You must be able to both quickly allocate memory to virtual machines depending on their requirements (peak and off-peak loads) and ensure that the memory is not wasted.</span></span> <span data-ttu-id="af0e9-109">La fonctionnalité de mémoire dynamique d’Hyper-V augmente l’agilité de l’allocation et de la gestion de la mémoire entre les machines virtuelles exécutées sur un hôte.</span><span class="sxs-lookup"><span data-stu-id="af0e9-109">The Hyper-V Dynamic Memory feature increases agility in how the memory is allocated and managed between virtual machines running on a host.</span></span>  
  
 <span data-ttu-id="af0e9-110">Certains meilleures pratiques pour virtualiser et gérer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ont besoin d'être modifiées lors de la virtualisation d'une base de données avec des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="af0e9-110">Some best practices for virtualizing and managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] need to be modified when virtualizing a database with memory-optimized tables.</span></span> <span data-ttu-id="af0e9-111">Sans les tables mémoire optimisées, les deux meilleures pratiques sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="af0e9-111">Without memory-optimized tables, two of the best practices are:</span></span>  
  
-   <span data-ttu-id="af0e9-112">Si vous utilisez le paramètre MIN_SERVER_MEMORY, il vaut mieux allouer uniquement la quantité de mémoire nécessaire, afin qu’une mémoire suffisante reste disponible pour d’autres processus (évitant ainsi la pagination).</span><span class="sxs-lookup"><span data-stu-id="af0e9-112">If you use MIN_SERVER_MEMORY, it is better to assign only the amount of memory that is required so sufficient memory remains for other processes (thereby avoiding paging).</span></span>  
  
-   <span data-ttu-id="af0e9-113">Ne définissez pas la préallocation de mémoire sur une valeur trop élevée.</span><span class="sxs-lookup"><span data-stu-id="af0e9-113">Do not set the memory pre-allocation value too high.</span></span> <span data-ttu-id="af0e9-114">Sinon, les autres processus ne disposeront pas de suffisamment de mémoire au moment où ils en ont besoin, ce qui peut entraîner une pagination de mémoire.</span><span class="sxs-lookup"><span data-stu-id="af0e9-114">Otherwise, other processes may not get sufficient memory at the time when they require it, and this can result in memory paging.</span></span>  
  
 <span data-ttu-id="af0e9-115">Si vous suivez les pratiques ci-dessus pour une base de données avec des tables à mémoire optimisée, une tentative de récupération et de restauration d’une base de données peut entraîner le blocage de la base de données à l’état « Récupération en attente », même si vous avez suffisamment de mémoire disponible pour la récupérer.</span><span class="sxs-lookup"><span data-stu-id="af0e9-115">If you follow the above practices for a database with memory-optimized tables, an attempt to restore and recover a database could result in the database being in a "Recovery Pending" state, even if you have sufficient memory to recover the database.</span></span> <span data-ttu-id="af0e9-116">En effet, au démarrage, [!INCLUDE[hek_2](../includes/hek-2-md.md)] met les données en mémoire plus rapidement que l’allocation de mémoire dynamique n’alloue la mémoire nécessaire à la base de données.</span><span class="sxs-lookup"><span data-stu-id="af0e9-116">The reason for this is that, when starting up, [!INCLUDE[hek_2](../includes/hek-2-md.md)] brings data into memory more aggressively than dynamic memory allocation allocates memory to the database.</span></span>  
  
 <span data-ttu-id="af0e9-117">**Résolution :**</span><span class="sxs-lookup"><span data-stu-id="af0e9-117">**Resolution**</span></span>  
  
 <span data-ttu-id="af0e9-118">Pour atténuer ce problème, préallouez suffisamment de mémoire à la base de données pour la récupération ou le redémarrage ; ne vous contentez pas d'une valeur minimale en comptant sur la mémoire dynamique pour fournir la mémoire supplémentaire lorsque cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="af0e9-118">To mitigate this, pre-allocate sufficient memory to the database to recover or restart the database, not a minimum value relying on dynamic memory to provide the additional memory when needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0e9-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af0e9-119">See Also</span></span>  
 [<span data-ttu-id="af0e9-120">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="af0e9-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
