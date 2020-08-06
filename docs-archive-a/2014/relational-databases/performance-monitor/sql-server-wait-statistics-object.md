---
title: SQL Server, objet Wait Statistics | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Wait Statistics object
- SQLServer:Wait Statistics
ms.assetid: cb7f917d-4291-4115-9b78-ee7692ebbb2d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfd2f1309cb118896ff7951b7f82feb38de60e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696748"
---
# <a name="sql-server-wait-statistics-object"></a><span data-ttu-id="886ed-102">SQL Server, objet Wait Statistics</span><span class="sxs-lookup"><span data-stu-id="886ed-102">SQL Server, Wait Statistics Object</span></span>
  <span data-ttu-id="886ed-103">L'objet de performance **SQLServer:Wait Statistics** contient des compteurs de performances qui créent des rapports d'information sur l'état d'attente.</span><span class="sxs-lookup"><span data-stu-id="886ed-103">The **SQLServer:Wait Statistics** performance object contains performance counters that report information about wait status.</span></span>  
  
 <span data-ttu-id="886ed-104">Le tableau ci-dessous répertorie les compteurs contenus dans l'objet Wait Statistics.</span><span class="sxs-lookup"><span data-stu-id="886ed-104">The table below lists the counters that the Wait Statistics object contains.</span></span>  
  
|<span data-ttu-id="886ed-105">Compteurs Statistiques d'attente de SQL Server</span><span class="sxs-lookup"><span data-stu-id="886ed-105">SQL Server Wait Statistics counters</span></span>|<span data-ttu-id="886ed-106">Description</span><span class="sxs-lookup"><span data-stu-id="886ed-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="886ed-107">**Attente de verrouillage**</span><span class="sxs-lookup"><span data-stu-id="886ed-107">**Lock waits**</span></span>|<span data-ttu-id="886ed-108">Statistiques des processus attendant un verrou.</span><span class="sxs-lookup"><span data-stu-id="886ed-108">Statistics for processes waiting on a lock.</span></span>|  
|<span data-ttu-id="886ed-109">**Attente accès tampon journal**</span><span class="sxs-lookup"><span data-stu-id="886ed-109">**Log buffer waits**</span></span>|<span data-ttu-id="886ed-110">Statistiques des processus attendant qu'un tampon journal soit disponible.</span><span class="sxs-lookup"><span data-stu-id="886ed-110">Statistics for processes waiting for log buffer to be available.</span></span>|  
|<span data-ttu-id="886ed-111">**Attente d'écriture du journal**</span><span class="sxs-lookup"><span data-stu-id="886ed-111">**Log write waits**</span></span>|<span data-ttu-id="886ed-112">Statistiques des processus attendant qu'un tampon journal soit écrit.</span><span class="sxs-lookup"><span data-stu-id="886ed-112">Statistics for processes waiting for log buffer to be written.</span></span>|  
|<span data-ttu-id="886ed-113">**Attente d'allocation de mémoire**</span><span class="sxs-lookup"><span data-stu-id="886ed-113">**Memory grant queue waits**</span></span>|<span data-ttu-id="886ed-114">Statistiques des processus attendant qu'une allocation de mémoire devienne disponible.</span><span class="sxs-lookup"><span data-stu-id="886ed-114">Statistics for processes waiting for memory grant to become available.</span></span>|  
|<span data-ttu-id="886ed-115">**Attente d'E/S réseau**</span><span class="sxs-lookup"><span data-stu-id="886ed-115">**Network IO waits**</span></span>|<span data-ttu-id="886ed-116">Statistiques concernant l'attente sur l'E/S réseau.</span><span class="sxs-lookup"><span data-stu-id="886ed-116">Statistics relevant to wait on network I/O.</span></span>|  
|<span data-ttu-id="886ed-117">**Attente verrous non spécifiques des pages**</span><span class="sxs-lookup"><span data-stu-id="886ed-117">**Non-Page latch waits**</span></span>|<span data-ttu-id="886ed-118">Statistiques concernant les verrous non spécifiques des pages.</span><span class="sxs-lookup"><span data-stu-id="886ed-118">Statistics relevant to non-page latches.</span></span>|  
|<span data-ttu-id="886ed-119">**Attente de verrous d'E/S de pages**</span><span class="sxs-lookup"><span data-stu-id="886ed-119">**Page IO latch waits**</span></span>|<span data-ttu-id="886ed-120">Statistiques concernant les verrous d'E/S de pages.</span><span class="sxs-lookup"><span data-stu-id="886ed-120">Statistics relevant to page I/O latches.</span></span>|  
|<span data-ttu-id="886ed-121">**Attente de verrous de pages**</span><span class="sxs-lookup"><span data-stu-id="886ed-121">**Page latch waits**</span></span>|<span data-ttu-id="886ed-122">Statistiques concernant les verrous de pages, qui n'incluent pas les verrous d'E/S.</span><span class="sxs-lookup"><span data-stu-id="886ed-122">Statistics relevant to page latches, not including I/O latches.</span></span>|  
|<span data-ttu-id="886ed-123">**Attente d'objets mémoire thread-safe**</span><span class="sxs-lookup"><span data-stu-id="886ed-123">**Thread-safe memory objects waits**</span></span>|<span data-ttu-id="886ed-124">Statistiques relatives aux processus en attente d'allocateurs de mémoire thread-safe.</span><span class="sxs-lookup"><span data-stu-id="886ed-124">Statistics for processes waiting on thread-safe memory allocators.</span></span>|  
|<span data-ttu-id="886ed-125">**Attente de propriété de transaction**</span><span class="sxs-lookup"><span data-stu-id="886ed-125">**Transaction ownership waits**</span></span>|<span data-ttu-id="886ed-126">Statistiques relatives aux processus de synchronisation d'accès à une transaction.</span><span class="sxs-lookup"><span data-stu-id="886ed-126">Statistics relevant to processes synchronizing access to transaction.</span></span>|  
|<span data-ttu-id="886ed-127">**Attente du thread de travail**</span><span class="sxs-lookup"><span data-stu-id="886ed-127">**Wait for the worker**</span></span>|<span data-ttu-id="886ed-128">Statistiques relatives aux processus en attente d'accès à un thread de travail.</span><span class="sxs-lookup"><span data-stu-id="886ed-128">Statistics relevant to processes waiting for worker to become available.</span></span>|  
|<span data-ttu-id="886ed-129">**Attente de synchronisation d'espace de travail**</span><span class="sxs-lookup"><span data-stu-id="886ed-129">**Workspace synchronization waits**</span></span>|<span data-ttu-id="886ed-130">Statistiques relatives aux processus de synchronisation d'accès à un espace de travail.</span><span class="sxs-lookup"><span data-stu-id="886ed-130">Statistics relevant to processes synchronizing access to workspace.</span></span>|  
  
 <span data-ttu-id="886ed-131">Chaque compteur de l'objet contient les instances suivantes :</span><span class="sxs-lookup"><span data-stu-id="886ed-131">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="886ed-132">Élément</span><span class="sxs-lookup"><span data-stu-id="886ed-132">Item</span></span>|<span data-ttu-id="886ed-133">Description</span><span class="sxs-lookup"><span data-stu-id="886ed-133">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="886ed-134">**Temps d'attente moyen (ms)**</span><span class="sxs-lookup"><span data-stu-id="886ed-134">**Average wait time (ms)**</span></span>|<span data-ttu-id="886ed-135">Temps moyen pour le type d'attente sélectionné.</span><span class="sxs-lookup"><span data-stu-id="886ed-135">Average time for the selected type of wait.</span></span>|  
|<span data-ttu-id="886ed-136">**Temps d'attente cumulé (ms) par seconde**</span><span class="sxs-lookup"><span data-stu-id="886ed-136">**Cumulative wait time (ms) per second**</span></span>|<span data-ttu-id="886ed-137">Temps d'attente agrégé par seconde, pour le type d'attente sélectionné.</span><span class="sxs-lookup"><span data-stu-id="886ed-137">Aggregated wait time per second, for the selected type of wait.</span></span>|  
|<span data-ttu-id="886ed-138">**Attentes en cours**</span><span class="sxs-lookup"><span data-stu-id="886ed-138">**Waits in progress**</span></span>|<span data-ttu-id="886ed-139">Nombre de processus en cours d'attente du type suivant.</span><span class="sxs-lookup"><span data-stu-id="886ed-139">Number of processes currently waiting on the following type.</span></span>|  
|<span data-ttu-id="886ed-140">**Attentes démarrées par seconde**</span><span class="sxs-lookup"><span data-stu-id="886ed-140">**Waits started per second**</span></span>|<span data-ttu-id="886ed-141">Nombre d'attentes démarrées par seconde pour le type d'attente sélectionné.</span><span class="sxs-lookup"><span data-stu-id="886ed-141">Number of waits started per second of the selected type of wait.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="886ed-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="886ed-142">See Also</span></span>  
 [<span data-ttu-id="886ed-143">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="886ed-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
