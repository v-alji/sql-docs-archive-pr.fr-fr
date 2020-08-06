---
title: SQL Server:Buffer Node | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Buffer Node
- Buffer Node object
ms.assetid: fd3f9f0f-7c38-4cfd-a0c5-ee93dd52d9a5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14659e4c1191e2260bccdbcd612f510770913629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612770"
---
# <a name="sql-serverbuffer-node"></a><span data-ttu-id="040dd-102">SQL Server:Buffer Node</span><span class="sxs-lookup"><span data-stu-id="040dd-102">SQL Server:Buffer Node</span></span>
  <span data-ttu-id="040dd-103">L'objet **Nœud de tampon** fournit des compteurs qui complètent les compteurs de l'objet **Gestionnaire de tampons** .</span><span class="sxs-lookup"><span data-stu-id="040dd-103">The **Buffer Node** object provides counters that complement counters provided by the **Buffer Manager** object.</span></span> <span data-ttu-id="040dd-104">Il vous permet de contrôler la distribution des pages du pool de mémoires tampons [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour chaque nœud NUMA (Non-Uniform Memory Access).</span><span class="sxs-lookup"><span data-stu-id="040dd-104">It allows you to monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] buffer pool page distribution for each non-uniform memory access (NUMA) node.</span></span> <span data-ttu-id="040dd-105">Il existe une instance de l'objet **Nœud de tampon** pour chaque nœud NUMA employé.</span><span class="sxs-lookup"><span data-stu-id="040dd-105">There is an instance of the **Buffer Node** object for each NUMA node in use.</span></span> <span data-ttu-id="040dd-106">Dans une architecture non-NUMA, une seule instance de l’objet **Nœud de tampon** est présente.</span><span class="sxs-lookup"><span data-stu-id="040dd-106">On non-NUMA architecture, there will be a single instance of the **Buffer Node** object.</span></span>  
  
## <a name="buffer-node-performance-objects"></a><span data-ttu-id="040dd-107">Objets de performances du Nœud de tampon</span><span class="sxs-lookup"><span data-stu-id="040dd-107">Buffer Node Performance Objects</span></span>  
 <span data-ttu-id="040dd-108">Ce tableau décrit les objets de performance **Nœud de tampon** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="040dd-108">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Buffer Node** performance objects.</span></span>  
  
|<span data-ttu-id="040dd-109">Compteurs de l'objet Nœud de tampon de SQL Server</span><span class="sxs-lookup"><span data-stu-id="040dd-109">SQL Server Buffer Node counters</span></span>|<span data-ttu-id="040dd-110">Description</span><span class="sxs-lookup"><span data-stu-id="040dd-110">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="040dd-111">**Pages de base de données**</span><span class="sxs-lookup"><span data-stu-id="040dd-111">**Database pages**</span></span>|<span data-ttu-id="040dd-112">Indique le nombre de pages dans le pool de mémoires tampons de ce nœud avec le contenu de la base de données.</span><span class="sxs-lookup"><span data-stu-id="040dd-112">Indicates the number of pages in the buffer pool on this node with database content.</span></span>|  
|<span data-ttu-id="040dd-113">**Espérance de vie d'une page**</span><span class="sxs-lookup"><span data-stu-id="040dd-113">**Page life expectancy**</span></span>|<span data-ttu-id="040dd-114">Indique le nombre minimal de secondes pendant lesquelles une page est conservée dans le pool de mémoires tampons sur ce nœud sans références.</span><span class="sxs-lookup"><span data-stu-id="040dd-114">Indicates the minimum number of seconds a page will stay in the buffer pool on this node without references.</span></span>|  
|<span data-ttu-id="040dd-115">**Recherches de pages de nœud local/s**</span><span class="sxs-lookup"><span data-stu-id="040dd-115">**Local Node page lookups/sec**</span></span>|<span data-ttu-id="040dd-116">Indique le nombre de demandes de recherches à partir de ce nœud qui ont été satisfaites par ce nœud.</span><span class="sxs-lookup"><span data-stu-id="040dd-116">Indicates the number of lookup requests from this node which were satisfied from this node.</span></span>|  
|<span data-ttu-id="040dd-117">**Recherches de pages de nœud distant/s**</span><span class="sxs-lookup"><span data-stu-id="040dd-117">**Remote Note page lookups/sec**</span></span>|<span data-ttu-id="040dd-118">Indique le nombre de demandes de recherches à partir de ce nœud qui ont été satisfaites par d'autres nœuds.</span><span class="sxs-lookup"><span data-stu-id="040dd-118">Indicates the number of lookup requests from this node which were satisfied from other nodes.</span></span>|  
  
 <span data-ttu-id="040dd-119">Si vous exécutez SQL Server sur du matériel non-NUMA, les compteurs des objets **Nœud de tampon** et **Gestionnaire de tampons** doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="040dd-119">If SQL Server is running on non-NUMA hardware, the counters of **Buffer Node** and **Buffer Manager** objects should match.</span></span>  
  
 <span data-ttu-id="040dd-120">Sur du matériel NUMA, les sommes des compteurs respectifs de tous les objets **Nœud de tampon** doivent correspondre aux sommes de leurs objets **Gestionnaire de tampons**équivalents.</span><span class="sxs-lookup"><span data-stu-id="040dd-120">On NUMA hardware, sums of respective counters of all **Buffer Nodes** should match their counterparts of **Buffer Manager**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="040dd-121">Il est possible que les valeurs et les sommes des compteurs ne correspondent pas exactement en raison de la nature dynamique des compteurs et de la précision d'échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="040dd-121">The counter values and sums may not match precisely due to the dynamic nature of the counters and the sampling accuracy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="040dd-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="040dd-122">See Also</span></span>  
 <span data-ttu-id="040dd-123">[SQL Server, objet Gestionnaire de tampons](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="040dd-123">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 <span data-ttu-id="040dd-124">[Mémoire du serveur (option de configuration de serveur)](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="040dd-124">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="040dd-125">[Analyser l’utilisation des ressources &#40;Moniteur système&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="040dd-125">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 [<span data-ttu-id="040dd-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="040dd-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
