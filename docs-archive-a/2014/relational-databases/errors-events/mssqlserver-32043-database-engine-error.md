---
title: MSSQLSERVER_32043 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32043 (Database Engine error)
ms.assetid: a0c48ae3-4c8c-419c-afb5-579fcefac01d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2febc7173c8144451c7a9b0576f2293d5594c6df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600973"
---
# <a name="mssqlserver_32043"></a><span data-ttu-id="3833f-102">MSSQLSERVER_32043</span><span class="sxs-lookup"><span data-stu-id="3833f-102">MSSQLSERVER_32043</span></span>
    
## <a name="details"></a><span data-ttu-id="3833f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="3833f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3833f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="3833f-104">Product Name</span></span>|<span data-ttu-id="3833f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3833f-105">SQL Server</span></span>|  
|<span data-ttu-id="3833f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="3833f-106">Event ID</span></span>|<span data-ttu-id="3833f-107">32043</span><span class="sxs-lookup"><span data-stu-id="3833f-107">32043</span></span>|  
|<span data-ttu-id="3833f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="3833f-108">Event Source</span></span>|<span data-ttu-id="3833f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3833f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3833f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="3833f-110">Component</span></span>|<span data-ttu-id="3833f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3833f-111">SQLEngine</span></span>|  
|<span data-ttu-id="3833f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="3833f-112">Symbolic Name</span></span>|<span data-ttu-id="3833f-113">SQLErrorNum32043</span><span class="sxs-lookup"><span data-stu-id="3833f-113">SQLErrorNum32043</span></span>|  
|<span data-ttu-id="3833f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="3833f-114">Message Text</span></span>|<span data-ttu-id="3833f-115">L'alerte relative au journal non restauré s'est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="3833f-115">The alert for 'unrestored log' has been raised.</span></span> <span data-ttu-id="3833f-116">La valeur actuelle de '%d' dépasse le seuil '%d'.</span><span class="sxs-lookup"><span data-stu-id="3833f-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3833f-117">Explication</span><span class="sxs-lookup"><span data-stu-id="3833f-117">Explanation</span></span>  
 <span data-ttu-id="3833f-118">Cet événement de mise en miroir de bases de données est émis sur l'instance du serveur miroir pour indiquer que la quantité de journal non restauré a atteint la valeur de seuil définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3833f-118">This database mirroring event is issued on the mirror server instance to indicate that the amount of unrestored log reached a user-specified threshold value.</span></span> <span data-ttu-id="3833f-119">En règle générale, cet événement se produit car les performances du système ont changé.</span><span class="sxs-lookup"><span data-stu-id="3833f-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="3833f-120">Soit la bande passante entre les deux systèmes a diminué, soit la charge a augmenté.</span><span class="sxs-lookup"><span data-stu-id="3833f-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="3833f-121">Un journal non restauré est un journal qui a été reçu par l'instance du serveur miroir et qui a été écrit sur le disque, mais qui attend d'être restauré dans la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="3833f-121">An unrestored log is a log that has been received by the mirror server instance and written to disk but is waiting to be restored to the mirror database.</span></span> <span data-ttu-id="3833f-122">La quantité de journal non restauré en kilo-octets (Ko) est une mesure de performance qui peut vous aider à évaluer le temps de basculement actuel.</span><span class="sxs-lookup"><span data-stu-id="3833f-122">The amount of unrestored log in kilobytes (KB) is a performance metric that can help you evaluate the current failover time.</span></span> <span data-ttu-id="3833f-123">La durée requise pour l'application du journal non restauré constitue le principal facteur du temps de basculement, auquel s'ajoute un petit laps de temps supplémentaire nécessaire pour récupérer la base de données et la mettre en ligne.</span><span class="sxs-lookup"><span data-stu-id="3833f-123">The time that is required to apply the unrestored log is the main factor in failover time, along with a short additional time that is required to recover the database and bring it online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3833f-124">Lorsque le basculement est automatique, la durée nécessaire au système pour détecter la défaillance est indépendante du temps de basculement.</span><span class="sxs-lookup"><span data-stu-id="3833f-124">For an automatic failover, the time for the system to notice the failure is independent of the failover time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3833f-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="3833f-125">User Action</span></span>  
 <span data-ttu-id="3833f-126">Vérifiez les charges incombant aux instances du serveur principal et du serveur miroir et à leur connexion réseau pour déterminer la cause du problème.</span><span class="sxs-lookup"><span data-stu-id="3833f-126">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3833f-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3833f-127">See Also</span></span>  
 <span data-ttu-id="3833f-128">[Mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3833f-128">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="3833f-129">Utiliser des seuils d’avertissement et d’alertes sur des métriques de performances de mise en miroir &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3833f-129">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
