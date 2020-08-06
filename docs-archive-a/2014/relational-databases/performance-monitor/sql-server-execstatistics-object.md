---
title: Objet SQL Server, ExecStatistics | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:ExecStatistics
- ExecStatistics object
ms.assetid: 4f8557a8-345f-4622-a8a5-763a0388ad94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d1a50c97add4708a58b9edc45fd49982b97a51ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602085"
---
# <a name="sql-server-execstatistics-object"></a><span data-ttu-id="5c52d-102">Objet SQL Server, ExecStatistics</span><span class="sxs-lookup"><span data-stu-id="5c52d-102">SQL Server, ExecStatistics Object</span></span>
  <span data-ttu-id="5c52d-103">L'objet **SQLServer:ExecStatistics** de Microsoft SQL Server intègre des compteurs chargés de surveiller les diverses exécutions.</span><span class="sxs-lookup"><span data-stu-id="5c52d-103">The **SQLServer:ExecStatistics** object in Microsoft SQL Server provides counters to monitor various executions.</span></span>  
  
 <span data-ttu-id="5c52d-104">Ce tableau décrit les compteurs **Exec Statistics** de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5c52d-104">This table describes the SQL Server **Exec Statistics** counters.</span></span>  
  
|<span data-ttu-id="5c52d-105">Compteurs ExecStatistics de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c52d-105">SQL Server Exec Statistics counters</span></span>|<span data-ttu-id="5c52d-106">Description</span><span class="sxs-lookup"><span data-stu-id="5c52d-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="5c52d-107">**Requête distribuée**</span><span class="sxs-lookup"><span data-stu-id="5c52d-107">**Distributed Query**</span></span>|<span data-ttu-id="5c52d-108">Statistiques relatives à l'exécution de requêtes distribuées</span><span class="sxs-lookup"><span data-stu-id="5c52d-108">Statistics relevant to execution of distributed queries.</span></span>|  
|<span data-ttu-id="5c52d-109">**Appels DTC**</span><span class="sxs-lookup"><span data-stu-id="5c52d-109">**DTC calls**</span></span>|<span data-ttu-id="5c52d-110">Statistiques relatives à l'exécution d'appels DTC</span><span class="sxs-lookup"><span data-stu-id="5c52d-110">Statistics relevant to execution of DTC calls.</span></span>|  
|<span data-ttu-id="5c52d-111">**Procédures étendues**</span><span class="sxs-lookup"><span data-stu-id="5c52d-111">**Extended Procedures**</span></span>|<span data-ttu-id="5c52d-112">Statistiques relatives à l'exécution de procédures étendues</span><span class="sxs-lookup"><span data-stu-id="5c52d-112">Statistics relevant to execution of extended procedures.</span></span>|  
|<span data-ttu-id="5c52d-113">**Appels OLEDB**</span><span class="sxs-lookup"><span data-stu-id="5c52d-113">**OLEDB calls**</span></span>|<span data-ttu-id="5c52d-114">Statistiques relatives à l''exécution d'appels OLEDB</span><span class="sxs-lookup"><span data-stu-id="5c52d-114">Statistics relevant to execution of OLEDB calls.</span></span>|  
  
 <span data-ttu-id="5c52d-115">Chaque compteur de l'objet contient les instances suivantes :</span><span class="sxs-lookup"><span data-stu-id="5c52d-115">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="5c52d-116">Élément</span><span class="sxs-lookup"><span data-stu-id="5c52d-116">Item</span></span>|<span data-ttu-id="5c52d-117">Description</span><span class="sxs-lookup"><span data-stu-id="5c52d-117">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5c52d-118">**Temps d'exécution moyen (ms)**</span><span class="sxs-lookup"><span data-stu-id="5c52d-118">**Average execution time (ms)**</span></span>|<span data-ttu-id="5c52d-119">Temps d'exécution moyen pour le type d'exécution sélectionné</span><span class="sxs-lookup"><span data-stu-id="5c52d-119">Average execution time of the selected type of execution.</span></span>|  
|<span data-ttu-id="5c52d-120">**Temps d'exécution cumulé (ms) par seconde**</span><span class="sxs-lookup"><span data-stu-id="5c52d-120">**Cumulative execution time (ms) per second**</span></span>|<span data-ttu-id="5c52d-121">Temps d'exécution global par seconde pour le type d'exécution sélectionné</span><span class="sxs-lookup"><span data-stu-id="5c52d-121">Aggregated execution time per second, of the selected type of execution.</span></span>|  
|<span data-ttu-id="5c52d-122">**Exécutions en cours**</span><span class="sxs-lookup"><span data-stu-id="5c52d-122">**Execs in progress**</span></span>|<span data-ttu-id="5c52d-123">Nombre d'exécutions en cours pour le type d'exécution sélectionné</span><span class="sxs-lookup"><span data-stu-id="5c52d-123">Number of execs in progress of the selected type of execution.</span></span>|  
|<span data-ttu-id="5c52d-124">**Exécutions démarrées par seconde**</span><span class="sxs-lookup"><span data-stu-id="5c52d-124">**Exec started per second**</span></span>|<span data-ttu-id="5c52d-125">Nombre d'exécutions démarrées par seconde pour le type d'exécution sélectionné</span><span class="sxs-lookup"><span data-stu-id="5c52d-125">Number of exes started per second of the selected type of execution.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c52d-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c52d-126">See Also</span></span>  
 [<span data-ttu-id="5c52d-127">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="5c52d-127">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
