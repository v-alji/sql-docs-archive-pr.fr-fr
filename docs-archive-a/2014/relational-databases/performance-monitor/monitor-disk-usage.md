---
title: Surveiller l’utilisation du disque | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database monitoring [SQL Server], disk usage
- disks [SQL Server]
- monitoring performance [SQL Server], disk usage
- server performance [SQL Server], disk usage
- monitoring [SQL Server], disk activity
- excess paging [SQL Server]
- tuning databases [SQL Server], disk usage
- I/O [SQL Server], monitoring
- disks [SQL Server], monitoring activity
- isolating disk activity [SQL Server]
- database performance [SQL Server], disk usage
- monitoring server performance [SQL Server], disk usage
ms.assetid: 1525449c-ea7d-4222-b294-1ba1fe99c9ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 51479b024864322d34dc3b0208e29e93d7454184
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707404"
---
# <a name="monitor-disk-usage"></a><span data-ttu-id="43270-102">Surveiller l'utilisation du disque</span><span class="sxs-lookup"><span data-stu-id="43270-102">Monitor Disk Usage</span></span>
  <span data-ttu-id="43270-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise les appels d'entrées/sorties (E/S) du système d'exploitation Microsoft Windows pour effectuer des opérations de lecture et d'écriture sur le disque.</span><span class="sxs-lookup"><span data-stu-id="43270-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses Microsoft Windows operating system input/output (I/O) calls to perform read and write operations on your disk.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="43270-104">gère quand et comment les E/S disque sont effectuées, mais le système d’exploitation Windows effectue les opérations d’E/S sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="43270-104">manages when and how disk I/O is performed, but the Windows operating system performs the underlying I/O operations.</span></span> <span data-ttu-id="43270-105">Le sous-système d'E/S comporte le bus système, les cartes contrôleurs de disque, les disques, les unités de sauvegarde sur bande, les unités de CD-Rom et de nombreux autres périphériques d'E/S.</span><span class="sxs-lookup"><span data-stu-id="43270-105">The I/O subsystem includes the system bus, disk controller cards, disks, tape drives, CD-ROM drive, and many other I/O devices.</span></span> <span data-ttu-id="43270-106">Les E/S sur le disque sont souvent responsables des problèmes de goulot d’étranglement d’un système.</span><span class="sxs-lookup"><span data-stu-id="43270-106">Disk I/O is frequently the cause of bottlenecks in a system.</span></span>  
  
 <span data-ttu-id="43270-107">La surveillance de l'activité du disque est double :</span><span class="sxs-lookup"><span data-stu-id="43270-107">Monitoring disk activity involves two areas of focus:</span></span>  
  
-   <span data-ttu-id="43270-108">Surveillance des E/S du disque et détection des excès de pagination</span><span class="sxs-lookup"><span data-stu-id="43270-108">Monitoring Disk I/O and Detecting Excess Paging</span></span>  
  
-   <span data-ttu-id="43270-109">Isolement de l'activité de disque créée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43270-109">Isolating Disk Activity That [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Creates</span></span>  
  
 <span data-ttu-id="43270-110">Pour plus d’informations, consultez [surveillance de l’utilisation du disque](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)</span><span class="sxs-lookup"><span data-stu-id="43270-110">For more information see, [Monitoring Disk Usage](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)</span></span>  
  
  
