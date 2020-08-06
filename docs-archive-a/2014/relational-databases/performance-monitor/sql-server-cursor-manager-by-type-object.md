---
title: Objet SQLServer:Cursor Manager by Type | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Cursor Manager by Type object
- SQLServer:Cursor Manager by Type
ms.assetid: d67fbd8a-7554-4a16-96f1-d9ee857a95e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7bee15aa2917f7b8890e6c1d3f26cc0e210208a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602095"
---
# <a name="sql-server-cursor-manager-by-type-object"></a><span data-ttu-id="c3ee4-102">Objet SQLServer:Cursor Manager by Type</span><span class="sxs-lookup"><span data-stu-id="c3ee4-102">SQL Server, Cursor Manager by Type Object</span></span>
  <span data-ttu-id="c3ee4-103">L'objet **SQLServer:Cursor Manager by Type** fournit des compteurs pour surveiller les curseurs, groupés par type.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-103">The **SQLServer:Cursor Manager by Type** object provides counters to monitor cursors, grouped by type.</span></span>  
  
 <span data-ttu-id="c3ee4-104">Le tableau ci-dessous décrit les compteurs **Cursor Manager by Type** de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-104">This table describes the SQL Server **Cursor Manager by Type** counters.</span></span>  
  
|<span data-ttu-id="c3ee4-105">Compteurs Cursor Manager by Type</span><span class="sxs-lookup"><span data-stu-id="c3ee4-105">Cursor Manager by Type counters</span></span>|<span data-ttu-id="c3ee4-106">Description</span><span class="sxs-lookup"><span data-stu-id="c3ee4-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="c3ee4-107">**Curseurs actifs**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-107">**Active cursors**</span></span>|<span data-ttu-id="c3ee4-108">Nombre de curseurs actifs.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-108">Number of active cursors.</span></span>|  
|<span data-ttu-id="c3ee4-109">**Taux d'accès au cache**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-109">**Cache Hit Ratio**</span></span>|<span data-ttu-id="c3ee4-110">Rapport entre les présences dans le cache et les recherches.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-110">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="c3ee4-111">**Nombres de curseurs mis en cache**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-111">**Cached Cursor Counts**</span></span>|<span data-ttu-id="c3ee4-112">Nombre de curseurs d'un type donné dans le cache.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-112">Number of cursors of a given type in the cache.</span></span>|  
|<span data-ttu-id="c3ee4-113">**Nombre d'utilisations du cache de curseurs/s**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-113">**Cursor Cache Use Count/sec**</span></span>|<span data-ttu-id="c3ee4-114">Nombre d'utilisations de chaque type de curseur en cache.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-114">Times each type of cached cursor has been used.</span></span>|  
|<span data-ttu-id="c3ee4-115">**Mémoire utilisée par les curseurs**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-115">**Cursor memory usage**</span></span>|<span data-ttu-id="c3ee4-116">Quantité de mémoire consommée par les curseurs en kilo-octets (Ko).</span><span class="sxs-lookup"><span data-stu-id="c3ee4-116">Amount of memory consumed by cursors in kilobytes (KB).</span></span>|  
|<span data-ttu-id="c3ee4-117">**Requêtes de curseurs/s**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-117">**Cursor Requests/sec**</span></span>|<span data-ttu-id="c3ee4-118">Nombre de requêtes de curseurs SQL reçues par le serveur.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-118">Number of SQL cursor requests received by server.</span></span>|  
|<span data-ttu-id="c3ee4-119">**Tables de travail utilisées par les curseurs**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-119">**Cursor worktable usage**</span></span>|<span data-ttu-id="c3ee4-120">Nombre de tables de travail utilisées par les curseurs.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-120">Number of worktables used by cursors.</span></span>|  
|<span data-ttu-id="c3ee4-121">**Nombre de plans de curseurs actifs**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-121">**Number of active cursor plans**</span></span>|<span data-ttu-id="c3ee4-122">Nombre de plans de curseurs.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-122">Number of cursor plans.</span></span>|  
  
 <span data-ttu-id="c3ee4-123">Chaque compteur de l'objet contient les instances suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3ee4-123">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="c3ee4-124">Instance Cursor Manager</span><span class="sxs-lookup"><span data-stu-id="c3ee4-124">Cursor Manager instance</span></span>|<span data-ttu-id="c3ee4-125">Description</span><span class="sxs-lookup"><span data-stu-id="c3ee4-125">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="c3ee4-126">**_Total**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-126">**_Total**</span></span>|<span data-ttu-id="c3ee4-127">Informations pour tous les curseurs.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-127">Information for all cursors.</span></span>|  
|<span data-ttu-id="c3ee4-128">**API Cursor**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-128">**API Cursor**</span></span>|<span data-ttu-id="c3ee4-129">Informations sur le curseur API uniquement.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-129">Only the API cursor information.</span></span>|  
|<span data-ttu-id="c3ee4-130">**TSQL Global Cursor**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-130">**TSQL Global Cursor**</span></span>|<span data-ttu-id="c3ee4-131">Informations sur le curseur global [!INCLUDE[tsql](../../includes/tsql-md.md)] uniquement.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-131">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] global cursor information.</span></span>|  
|<span data-ttu-id="c3ee4-132">**TSQL Local Cursor**</span><span class="sxs-lookup"><span data-stu-id="c3ee4-132">**TSQL Local Cursor**</span></span>|<span data-ttu-id="c3ee4-133">Informations sur le curseur local [!INCLUDE[tsql](../../includes/tsql-md.md)] uniquement.</span><span class="sxs-lookup"><span data-stu-id="c3ee4-133">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] local cursor information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3ee4-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3ee4-134">See Also</span></span>  
 [<span data-ttu-id="c3ee4-135">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ee4-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
