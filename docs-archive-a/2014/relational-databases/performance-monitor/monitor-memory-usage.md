---
title: Surveiller l’utilisation de la mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- tuning databases [SQL Server], memory
- monitoring server performance [SQL Server], memory usage
- isolating memory [SQL Server]
- paging rate [SQL Server]
- memory [SQL Server], monitoring usage
- monitoring [SQL Server], memory usage
- low-memory conditions
- database monitoring [SQL Server], memory usage
- available memory [SQL Server]
- page faults [SQL Server]
- monitoring performance [SQL Server], memory usage
- server performance [SQL Server], memory
ms.assetid: 1aee3933-a11c-4b87-91b7-32f5ea38c87f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1986d9576f9b067cad18f27d4febbf097ed52703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707403"
---
# <a name="monitor-memory-usage"></a><span data-ttu-id="6d4e9-102">Surveiller l'utilisation de la mémoire</span><span class="sxs-lookup"><span data-stu-id="6d4e9-102">Monitor Memory Usage</span></span>
  <span data-ttu-id="6d4e9-103">Surveillez périodiquement une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vous assurer que l'utilisation de la mémoire reste dans des limites normales.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-103">Monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to confirm that memory usage is within typical ranges.</span></span>  
  
 <span data-ttu-id="6d4e9-104">Pour surveiller l'état de la mémoire basse, utilisez les compteurs des objets suivants :</span><span class="sxs-lookup"><span data-stu-id="6d4e9-104">To monitor for a low-memory condition, use the following object counters:</span></span>  
  
-   <span data-ttu-id="6d4e9-105">**Mémoire : Octets disponibles**</span><span class="sxs-lookup"><span data-stu-id="6d4e9-105">**Memory: Available Bytes**</span></span>  
  
-   <span data-ttu-id="6d4e9-106">**Mémoire : Pages/sec**</span><span class="sxs-lookup"><span data-stu-id="6d4e9-106">**Memory: Pages/sec**</span></span>  
  
 <span data-ttu-id="6d4e9-107">Le compteur **Octets disponibles** indique combien d'octets de mémoire sont actuellement disponibles pour les processus.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-107">The **Available Bytes** counter indicates how many bytes of memory are currently available for use by processes.</span></span> <span data-ttu-id="6d4e9-108">Le compteur **Pages/s** indique le nombre de pages qui ont été extraites du disque en raison de défauts de page ou écrites sur le disque pour libérer de l’espace dans la plage de travail en raison de défauts de page.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-108">The **Pages/sec** counter indicates the number of pages that either were retrieved from disk due to hard page faults or written to disk to free space in the working set due to page faults.</span></span>  
  
 <span data-ttu-id="6d4e9-109">Des valeurs faibles du compteur **Octets disponibles** peuvent indiquer un manque global de mémoire sur l'ordinateur ou bien qu'un programme ne libère pas la mémoire.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-109">Low values for the **Available Bytes** counter can indicate that there is an overall shortage of memory on the computer or that an application is not releasing memory.</span></span> <span data-ttu-id="6d4e9-110">Une valeur élevée du compteur **Pages/s** peut indiquer une pagination excessive.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-110">A high rate for the **Pages/sec** counter could indicate excessive paging.</span></span> <span data-ttu-id="6d4e9-111">Surveillez le compteur **Mémoire : Défauts de page/s** pour vérifier que l’activité du disque n’est pas due à la pagination.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-111">Monitor the **Memory: Page Faults/sec** counter to make sure that the disk activity is not caused by paging.</span></span>  
  
 <span data-ttu-id="6d4e9-112">Un faible taux de pagination (et donc des défauts de page) est typique, même si l'ordinateur dispose de beaucoup de mémoire disponible.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-112">A low rate of paging (and hence page faults) is typical, even if the computer has plenty of available memory.</span></span> <span data-ttu-id="6d4e9-113">Le gestionnaire de mémoire virtuelle de Microsoft Windows soustrait des pages à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et à d'autres processus quand il réduit la taille des parties actives de ces processus.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-113">The Microsoft Windows Virtual Memory Manager (VMM) takes pages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and other processes as it trims the working-set sizes of those processes.</span></span> <span data-ttu-id="6d4e9-114">Son activité a tendance à provoquer des défauts de page.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-114">This VMM activity tends to cause page faults.</span></span> <span data-ttu-id="6d4e9-115">Pour déterminer si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou un autre processus est la cause d’une pagination excessive, surveillez le compteur **Processus : Défauts de page/s** pour l’instance de processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d4e9-115">To determine whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or another process is the cause of excessive paging, monitor the **Process: Page Faults/sec** counter for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process instance.</span></span>  
  
 <span data-ttu-id="6d4e9-116">Pour plus d'informations sur la résolution d'une pagination excessive, consultez la documentation du système d'exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-116">For more information about resolving excessive paging, see the Windows operating system documentation.</span></span>  
  
## <a name="isolating-memory-used-by-sql-server"></a><span data-ttu-id="6d4e9-117">Isolement de la mémoire utilisée par SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d4e9-117">Isolating Memory Used by SQL Server</span></span>  
 <span data-ttu-id="6d4e9-118">Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] modifie dynamiquement ses besoins en mémoire en fonction des ressources système disponibles.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-118">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] changes its memory requirements dynamically, on the basis of available system resources.</span></span> <span data-ttu-id="6d4e9-119">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a besoin de plus de mémoire, il demande au système d'exploitation de déterminer si de la mémoire physique libre est disponible. Dans l'affirmative, il l'utilise.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-119">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] needs more memory, it queries the operating system to determine whether free physical memory is available and uses the available memory.</span></span> <span data-ttu-id="6d4e9-120">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'a pas besoin de la mémoire qui lui est actuellement allouée, il la libère pour le système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-120">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not need the memory currently allocated to it, it releases the memory to the operating system.</span></span> <span data-ttu-id="6d4e9-121">Vous pouvez cependant ignorer cette option pour utiliser dynamiquement de la mémoire au moyen des options de configuration du serveur **minservermemory**et **maxservermemory**</span><span class="sxs-lookup"><span data-stu-id="6d4e9-121">However, you can override the option to dynamically use memory by using the **minservermemory**, and **maxservermemory** server configuration options.</span></span> <span data-ttu-id="6d4e9-122">Pour plus d'informations, consultez [Options de mémoire du serveur](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="6d4e9-122">For more information, see [Server Memory Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span></span>  
  
 <span data-ttu-id="6d4e9-123">Pour surveiller la mémoire utilisée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , examinez les compteurs de performances suivants :</span><span class="sxs-lookup"><span data-stu-id="6d4e9-123">To monitor the amount of memory that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses, examine the following performance counters:</span></span>  
  
-   <span data-ttu-id="6d4e9-124">**Processus : Plage de travail**</span><span class="sxs-lookup"><span data-stu-id="6d4e9-124">**Process: Working Set**</span></span>  
  
-   <span data-ttu-id="6d4e9-125">**SQL Server : Buffer Manager : Taux d’accès au cache**</span><span class="sxs-lookup"><span data-stu-id="6d4e9-125">**SQL Server: Buffer Manager: Buffer Cache Hit Ratio**</span></span>  
  
-   <span data-ttu-id="6d4e9-126">**SQL Server : Buffer Manager : Pages de base de données**</span><span class="sxs-lookup"><span data-stu-id="6d4e9-126">**SQL Server: Buffer Manager: Database Pages**</span></span>  
  
-   <span data-ttu-id="6d4e9-127">**SQL Server : Memory Manager : Mémoire totale du serveur (Ko)**</span><span class="sxs-lookup"><span data-stu-id="6d4e9-127">**SQL Server: Memory Manager: Total Server Memory (KB)**</span></span>  
  
 <span data-ttu-id="6d4e9-128">Le compteur **WorkingSet** indique la quantité de mémoire utilisée par un processus.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-128">The **WorkingSet** counter shows the amount of memory that is used by a process.</span></span> <span data-ttu-id="6d4e9-129">Si ce nombre est régulièrement inférieur à la quantité de mémoire définie par les options du serveur **min server memory** et **max server memory** , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configuré pour utiliser trop de mémoire.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-129">If this number is consistently below the amount of memory that is set by the **min server memory** and **max server memory** server options, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use too much memory.</span></span>  
  
 <span data-ttu-id="6d4e9-130">Le compteur **Buffer Cache Hit Ratio** est propre à une application.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-130">The **Buffer Cache Hit Ratio** counter is specific to an application.</span></span> <span data-ttu-id="6d4e9-131">Cependant, une valeur supérieure ou égale à 90 % est souhaitable.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-131">However, a rate of 90 percent or higher is desirable.</span></span> <span data-ttu-id="6d4e9-132">Ajoutez de la mémoire jusqu'à ce que cette valeur soit régulièrement supérieure à 90 %.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-132">Add more memory until the value is consistently greater than 90 percent.</span></span> <span data-ttu-id="6d4e9-133">Une valeur supérieure à 90 pour cent indique que plus de 90 % de toutes les requêtes ont été satisfaites à partir de la mémoire cache.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-133">A value greater than 90 percent indicates that more than 90 percent of all requests for data were satisfied from the data cache.</span></span>  
  
 <span data-ttu-id="6d4e9-134">Si la valeur du compteur **TotalServerMemory (KB)** est régulièrement élevée par rapport à la quantité de mémoire physique de l’ordinateur, cela peut indiquer que davantage de mémoire est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-134">If the **TotalServerMemory (KB)** counter is consistently high compared to the amount of physical memory in the computer, it may indicate that more memory is required.</span></span>  
  
## <a name="determining-current-memory-allocation"></a><span data-ttu-id="6d4e9-135">Détermination de l'allocation de mémoire actuelle</span><span class="sxs-lookup"><span data-stu-id="6d4e9-135">Determining Current Memory Allocation</span></span>  
 <span data-ttu-id="6d4e9-136">La requête suivante retourne des informations sur la mémoire allouée actuellement.</span><span class="sxs-lookup"><span data-stu-id="6d4e9-136">The following query returns information about currently allocated memory.</span></span>  
  
```  
SELECT  
(physical_memory_in_use_kb/1024) AS Memory_usedby_Sqlserver_MB,  
(locked_page_allocations_kb/1024) AS Locked_pages_used_Sqlserver_MB,  
(total_virtual_address_space_kb/1024) AS Total_VAS_in_MB,  
process_physical_memory_low,  
process_virtual_memory_low  
FROM sys.dm_os_process_memory;  
```  
  
  
