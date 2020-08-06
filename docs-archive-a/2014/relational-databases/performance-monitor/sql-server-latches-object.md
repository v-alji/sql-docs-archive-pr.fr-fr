---
title: SQL Server, objet Latches | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Latches object
- SQLServer:Latches
ms.assetid: 2393ea1c-2bf3-41c3-9f37-b9761144eeca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f49ac00114065e971c0893f9217ab883eb2d7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602082"
---
# <a name="sql-server-latches-object"></a><span data-ttu-id="0ca1c-102">SQL Server - Objet Latches</span><span class="sxs-lookup"><span data-stu-id="0ca1c-102">SQL Server, Latches Object</span></span>
  <span data-ttu-id="0ca1c-103">L'objet **SQLServer:Latches** de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournit des compteurs qui permettent de surveiller les verrous des ressources internes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ca1c-103">The **SQLServer:Latches** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor internal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource locks called latches.</span></span> <span data-ttu-id="0ca1c-104">La surveillance des verrous internes, afin de déterminer l'activité de l'utilisateur et son exploitation des ressources, peut permettre d'identifier les goulots d'étranglement des performances.</span><span class="sxs-lookup"><span data-stu-id="0ca1c-104">Monitoring the latches to determine user activity and resource usage can help you to identify performance bottlenecks.</span></span>  
  
 <span data-ttu-id="0ca1c-105">Ce tableau décrit les compteurs **Verrous internes** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ca1c-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Latches** counters.</span></span>  
  
|<span data-ttu-id="0ca1c-106">Compteurs des verrous internes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ca1c-106">SQL Server Latches counters</span></span>|<span data-ttu-id="0ca1c-107">Description</span><span class="sxs-lookup"><span data-stu-id="0ca1c-107">Description</span></span>|  
|---------------------------------|-----------------|  
|<span data-ttu-id="0ca1c-108">**Temps d'attente moyen d'un verrou interne (ms)**</span><span class="sxs-lookup"><span data-stu-id="0ca1c-108">**Average Latch Wait Time (ms)**</span></span>|<span data-ttu-id="0ca1c-109">Temps d'attente moyen d'un verrou interne (en millisecondes) pour les requêtes en attente.</span><span class="sxs-lookup"><span data-stu-id="0ca1c-109">Average latch wait time (in milliseconds) for latch requests that had to wait.</span></span>|  
|<span data-ttu-id="0ca1c-110">**Attentes de verrous internes/s**</span><span class="sxs-lookup"><span data-stu-id="0ca1c-110">**Latch Waits/sec**</span></span>|<span data-ttu-id="0ca1c-111">Nombre de requêtes de verrous internes n'ayant pas pu être accordés immédiatement.</span><span class="sxs-lookup"><span data-stu-id="0ca1c-111">Number of latch requests that could not be granted immediately.</span></span>|  
|<span data-ttu-id="0ca1c-112">**Nombre de SuperLatch**</span><span class="sxs-lookup"><span data-stu-id="0ca1c-112">**Number of SuperLatches**</span></span>|<span data-ttu-id="0ca1c-113">Nombre de verrous internes qui sont actuellement des SuperLatch.</span><span class="sxs-lookup"><span data-stu-id="0ca1c-113">Number of latches that are currently SuperLatches.</span></span>|  
|<span data-ttu-id="0ca1c-114">**Rétrogradations SuperLatch/sec**</span><span class="sxs-lookup"><span data-stu-id="0ca1c-114">**SuperLatch Demotions/sec**</span></span>|<span data-ttu-id="0ca1c-115">Nombre de SuperLatch ayant été rétrogradés au rang de verrous internes réguliers au cours de la dernière seconde.</span><span class="sxs-lookup"><span data-stu-id="0ca1c-115">Number of SuperLatches that have been demoted to regular latches in the last second.</span></span>|  
|<span data-ttu-id="0ca1c-116">**Promotions SuperLatch/s**</span><span class="sxs-lookup"><span data-stu-id="0ca1c-116">**SuperLatch Promotions/sec**</span></span>|<span data-ttu-id="0ca1c-117">Nombre de SuperLatch ayant été promus au rang de SuperLatch au cours de la dernière seconde.</span><span class="sxs-lookup"><span data-stu-id="0ca1c-117">Number of latches that have been promoted to SuperLatches in the last second.</span></span>|  
|<span data-ttu-id="0ca1c-118">**Temps d'attente total des verrous internes (ms)**</span><span class="sxs-lookup"><span data-stu-id="0ca1c-118">**Total Latch Wait Time (ms)**</span></span>|<span data-ttu-id="0ca1c-119">Temps d'attente total (en millisecondes) pour les verrous lors de la dernière seconde.</span><span class="sxs-lookup"><span data-stu-id="0ca1c-119">Total latch wait time (in milliseconds) for latch requests in the last second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ca1c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ca1c-120">See Also</span></span>  
 [<span data-ttu-id="0ca1c-121">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="0ca1c-121">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
