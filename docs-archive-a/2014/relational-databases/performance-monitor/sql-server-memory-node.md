---
title: SQL Server, nœud de mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 55b28ba9-b6d5-4ea9-8103-db8a72f42982
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5bbc3f581ea9ececeb7d55a614ef27c3c72de7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613996"
---
# <a name="sql-server-memory-node"></a><span data-ttu-id="d775b-102">SQL Server, nœud de mémoire</span><span class="sxs-lookup"><span data-stu-id="d775b-102">SQL Server, Memory Node</span></span>
  <span data-ttu-id="d775b-103">L'objet **Nœud de mémoire** de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournit des compteurs permettant de surveiller l'utilisation globale de la mémoire sur des nœuds NUMA.</span><span class="sxs-lookup"><span data-stu-id="d775b-103">The **Memory Node** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor server memory usage on NUMA nodes.</span></span>  
  
## <a name="memory-node-counters"></a><span data-ttu-id="d775b-104">Compteurs de nœuds de mémoire</span><span class="sxs-lookup"><span data-stu-id="d775b-104">Memory Node Counters</span></span>  
 <span data-ttu-id="d775b-105">Ce tableau décrit les compteurs **Nœud de mémoire** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d775b-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Memory Node** counters.</span></span>  
  
|<span data-ttu-id="d775b-106">Compteurs du Gestionnaire de mémoire de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d775b-106">SQL Server Memory Manager counters</span></span>|<span data-ttu-id="d775b-107">Description</span><span class="sxs-lookup"><span data-stu-id="d775b-107">Description</span></span>|  
|----------------------------------------|-----------------|  
|<span data-ttu-id="d775b-108">**Mémoire de nœud de base de données (Ko)**</span><span class="sxs-lookup"><span data-stu-id="d775b-108">**Database Node Memory (KB)**</span></span>|<span data-ttu-id="d775b-109">Spécifie la quantité de mémoire que le serveur utilise actuellement sur ce nœud pour les pages de bases de données.</span><span class="sxs-lookup"><span data-stu-id="d775b-109">Specifies the amount of memory the server is currently using on this node for database pages.</span></span>|  
|<span data-ttu-id="d775b-110">**Mémoire disponible du nœud (Ko)**</span><span class="sxs-lookup"><span data-stu-id="d775b-110">**Free Node Memory (KB)**</span></span>|<span data-ttu-id="d775b-111">Spécifie la quantité de mémoire que le serveur n'utilise pas sur ce nœud.</span><span class="sxs-lookup"><span data-stu-id="d775b-111">Specifies the amount of memory the server is not using on this node.</span></span>|  
|<span data-ttu-id="d775b-112">**Mémoire distante du nœud (Ko)**</span><span class="sxs-lookup"><span data-stu-id="d775b-112">**Foreign Node Memory (KB)**</span></span>|<span data-ttu-id="d775b-113">Spécifie la quantité de mémoire non-NUMA locale sur ce nœud.</span><span class="sxs-lookup"><span data-stu-id="d775b-113">Specifies the amount of non NUMA-local memory on this node.</span></span>|  
|<span data-ttu-id="d775b-114">**Mémoire détournée du nœud (Ko)**</span><span class="sxs-lookup"><span data-stu-id="d775b-114">**Stolen Memory Node (KB)**</span></span>|<span data-ttu-id="d775b-115">Spécifie la quantité de mémoire utilisée par le serveur sur ce nœud à d'autres fins que les pages de bases de données.</span><span class="sxs-lookup"><span data-stu-id="d775b-115">Specifies the amount of memory the server is using on this node for purposes other than database pages.</span></span>|  
|<span data-ttu-id="d775b-116">**Mémoire cible du nœud**</span><span class="sxs-lookup"><span data-stu-id="d775b-116">**Target Node Memory**</span></span>|<span data-ttu-id="d775b-117">Spécifie la quantité de mémoire idéale pour ce nœud.</span><span class="sxs-lookup"><span data-stu-id="d775b-117">Specifies the ideal amount of memory for this node.</span></span>|  
|<span data-ttu-id="d775b-118">**Mémoire totale du nœud**</span><span class="sxs-lookup"><span data-stu-id="d775b-118">**Total Node Memory**</span></span>|<span data-ttu-id="d775b-119">Indique la quantité totale de mémoire validée par le serveur sur ce nœud.</span><span class="sxs-lookup"><span data-stu-id="d775b-119">Indicates the total amount of memory the server has committed on this node.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d775b-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d775b-120">See Also</span></span>  
 <span data-ttu-id="d775b-121">[Analyser l’utilisation des ressources &#40;Moniteur système&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d775b-121">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="d775b-122">[SQL Server, objet Gestionnaire de tampons](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="d775b-122">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="d775b-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d775b-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
