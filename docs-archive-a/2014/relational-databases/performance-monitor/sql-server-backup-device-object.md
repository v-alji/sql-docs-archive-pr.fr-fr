---
title: SQL Server, objet Backup Device | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Backup Device
- Backup Device object
ms.assetid: 52e7febf-d5e0-4674-945b-aacc40a9ad6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e3126310ad31dcc153fc79508dbfaccf86f5da78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603952"
---
# <a name="sql-server-backup-device-object"></a><span data-ttu-id="5c65d-102">SQL Server, objet Unité de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="5c65d-102">SQL Server, Backup Device Object</span></span>
  <span data-ttu-id="5c65d-103">L’objet **Unité de sauvegarde** fournit des compteurs permettant de surveiller les unités de sauvegarde de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisées pour les opérations de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="5c65d-103">The **Backup Device** object provides counters to monitor Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices used for backup and restore operations.</span></span> <span data-ttu-id="5c65d-104">Surveillez les unités de sauvegarde lorsque vous voulez déterminer le débit ou la progression et les performances de vos opérations de sauvegarde et de restauration par unité.</span><span class="sxs-lookup"><span data-stu-id="5c65d-104">Monitor backup devices when you want to determine the throughput or the progress and performance of your backup and restore operations on a per device basis.</span></span> <span data-ttu-id="5c65d-105">Pour surveiller le débit de l’opération de sauvegarde ou de restauration de l’ensemble de la base de données, utilisez le compteur **Débit de sauvegarde/restauration/s** de l’objet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="5c65d-105">To monitor the throughput of the entire database backup or restore operation, use the **Backup/Restore Throughput/sec** counter of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Databases** object.</span></span> <span data-ttu-id="5c65d-106">Pour plus d’informations, voir [SQL Server, Databases Object](sql-server-databases-object.md).</span><span class="sxs-lookup"><span data-stu-id="5c65d-106">For more information, see [SQL Server, Databases Object](sql-server-databases-object.md).</span></span>  
  
 <span data-ttu-id="5c65d-107">Ce tableau décrit le compteur **Unité de sauvegarde** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c65d-107">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Backup Device** counter.</span></span>  
  
|<span data-ttu-id="5c65d-108">Compteurs Unité de sauvegarde de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c65d-108">SQL Server Backup Device counters</span></span>|<span data-ttu-id="5c65d-109">Description</span><span class="sxs-lookup"><span data-stu-id="5c65d-109">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="5c65d-110">**Débit d'unité en octets/s**</span><span class="sxs-lookup"><span data-stu-id="5c65d-110">**Device Throughput Bytes/sec**</span></span>|<span data-ttu-id="5c65d-111">Débit des opérations de lecture et d'écriture (en octets par seconde) pour une unité de sauvegarde utilisée pour la sauvegarde ou la restauration de bases de données.</span><span class="sxs-lookup"><span data-stu-id="5c65d-111">Throughput of read and write operations (in bytes per second) for a backup device used when backing up or restoring databases.</span></span> <span data-ttu-id="5c65d-112">Ce compteur n'existe que lorsque les opérations de sauvegarde ou de restauration sont en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5c65d-112">This counter exists only while the backup or restore operation is executing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c65d-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c65d-113">See Also</span></span>  
 <span data-ttu-id="5c65d-114">[Unités de sauvegarde &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5c65d-114">[Backup Devices &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="5c65d-115">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="5c65d-115">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
