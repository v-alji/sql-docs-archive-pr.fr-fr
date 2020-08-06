---
title: SQL Server, objet Broker TO Statistics | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Broker Transmission Object object
- 'SQL Server: Broker Transmission Object'
ms.assetid: b5bc5dde-e540-4848-8aa3-5735c51df2fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 93d9c24a175dedfee171eccfccb34673501660ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612771"
---
# <a name="sql-server-broker-to-statistics-object"></a><span data-ttu-id="f5b4e-102">SQL Server, objet Broker TO Statistics</span><span class="sxs-lookup"><span data-stu-id="f5b4e-102">SQL Server, Broker TO Statistics Object</span></span>
  <span data-ttu-id="f5b4e-103">L’objet de performance SQLServer:Broker TO Statistics communique des informations sur le nombre de fois que des boîtes de dialogue [!INCLUDE[ssSB](../../includes/sssb-md.md)] demandent des objets de transmission, et sur la fréquence à laquelle des objets de transmission sont écrits dans **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-103">The SQLServer:Broker TO Statistics performance object reports information about how many times [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialogs request transmission objects, and how often transmission objects are written to **tempdb**.</span></span>  
  
 <span data-ttu-id="f5b4e-104">Les objets de transmission enregistrent l'état de transmissions de message pour un dialogue [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5b4e-104">Transmission objects record the state of message transmissions for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialog.</span></span> <span data-ttu-id="f5b4e-105">Ils sont stockés en mémoire.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-105">They are stored in memory.</span></span> <span data-ttu-id="f5b4e-106">Pour libérer de la mémoire, [!INCLUDE[ssSB](../../includes/sssb-md.md)] écrit périodiquement des lots d’objets de transmission inactifs dans des tables de travail **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-106">To free memory, [!INCLUDE[ssSB](../../includes/sssb-md.md)] periodically writes batches of inactive transmission objects to work tables in **tempdb**.</span></span>  
  
 <span data-ttu-id="f5b4e-107">Le tableau ci-dessous répertorie les compteurs que cet objet contient.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-107">The following table lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="f5b4e-108">Compteurs de Statistiques des objets de transmission de Service Broker</span><span class="sxs-lookup"><span data-stu-id="f5b4e-108">SQL Server Broker TO Statistics counters</span></span>|<span data-ttu-id="f5b4e-109">Description</span><span class="sxs-lookup"><span data-stu-id="f5b4e-109">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<span data-ttu-id="f5b4e-110">**Durée moy. des écritures par lot**</span><span class="sxs-lookup"><span data-stu-id="f5b4e-110">**Avg. Length of Batched Writes**</span></span>|<span data-ttu-id="f5b4e-111">Nombre moyen d'objets de transmission enregistrés dans un lot.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-111">The average number of transmission objects saved in a batch.</span></span>|  
|<span data-ttu-id="f5b4e-112">**Durée moy. d’écriture d’un lot (ms)**</span><span class="sxs-lookup"><span data-stu-id="f5b4e-112">**Avg. Time To Write Batch (ms)**</span></span>|<span data-ttu-id="f5b4e-113">Nombre moyen de millisecondes requises pour enregistrer un lot d'objets de transmission.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-113">The average number of milliseconds required to save a batch of transmission objects.</span></span>|  
|<span data-ttu-id="f5b4e-114">**Durée moy. entre chaque lot (ms)**</span><span class="sxs-lookup"><span data-stu-id="f5b4e-114">**Avg. Time Between Batches (ms)**</span></span>|<span data-ttu-id="f5b4e-115">Nombre moyen de millisecondes entre des écritures de lots d'objets de transmission.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-115">The average number of milliseconds between writes of transmission object batches.</span></span>|  
|<span data-ttu-id="f5b4e-116">**Objets de transmission obtenus/s**</span><span class="sxs-lookup"><span data-stu-id="f5b4e-116">**Tran Object Gets/sec**</span></span>|<span data-ttu-id="f5b4e-117">Nombre de fois par seconde que les dialogues ont demandé des objets de transmission.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-117">The number of times per second that dialogs requested transmission objects.</span></span>|  
|<span data-ttu-id="f5b4e-118">**Nombre d'objets de transmission marqués comme modifiés/s**</span><span class="sxs-lookup"><span data-stu-id="f5b4e-118">**Tran Objects Marked Dirty/sec**</span></span>|<span data-ttu-id="f5b4e-119">Nombre de fois par seconde que les objets de transmission ont été marqués comme modifiés.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-119">The number of times per second that transmission objects were marked as dirty.</span></span> <span data-ttu-id="f5b4e-120">Les objets de transmission sont marqués comme modifiés par la première modification qui entraîne une différence entre la copie en mémoire et la copie stockée dans **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-120">Transmission objects are marked as dirty by the first modification that causes the in-memory copy to differ from the copy stored in **tempdb**.</span></span> <span data-ttu-id="f5b4e-121">Les objets de transmission sont modifiés lorsque [!INCLUDE[ssSB](../../includes/sssb-md.md)] doit enregistrer une modification dans l'état des transmissions de message pour le dialogue.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-121">Transmission objects are modified when [!INCLUDE[ssSB](../../includes/sssb-md.md)] has to record a change in the state of message transmissions for the dialog.</span></span>|  
|<span data-ttu-id="f5b4e-122">**Objets de transmission écrits/s**</span><span class="sxs-lookup"><span data-stu-id="f5b4e-122">**Tran Object Writes/sec**</span></span>|<span data-ttu-id="f5b4e-123">Nombre de fois par seconde où un lot d’objets de transmission a été écrit dans les tables de travail **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="f5b4e-123">The number of times per second that a batch of transmission objects were written to **tempdb** work tables.</span></span> <span data-ttu-id="f5b4e-124">De grands nombres d'écritures peuvent indiquer que la mémoire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est accentuée.</span><span class="sxs-lookup"><span data-stu-id="f5b4e-124">Large numbers of writes could indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory is being stressed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5b4e-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5b4e-125">See Also</span></span>  
 <span data-ttu-id="f5b4e-126">[SQL Server - Objet Access Methods](sql-server-access-methods-object.md) </span><span class="sxs-lookup"><span data-stu-id="f5b4e-126">[SQL Server, Access Methods Object](sql-server-access-methods-object.md) </span></span>  
 <span data-ttu-id="f5b4e-127">[Objet SQLServer:Memory Manager](sql-server-memory-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="f5b4e-127">[SQL Server, Memory Manager Object](sql-server-memory-manager-object.md) </span></span>  
 [<span data-ttu-id="f5b4e-128">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="f5b4e-128">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
