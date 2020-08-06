---
title: Verrous, catégorie d’événement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Locks event category [SQL Server]
- SQL Server event classes, Locks event category
- event classes [SQL Server], Locks event category
- lock escalation [SQL Server], locks event category
ms.assetid: 27d6afa2-7dab-4fe7-a1ad-064b879dc654
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a202279021e3e6c7c3c44a167792bb9439567aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602145"
---
# <a name="locks-event-category"></a><span data-ttu-id="bedd4-102">Verrous, catégorie d’événement</span><span class="sxs-lookup"><span data-stu-id="bedd4-102">Locks Event Category</span></span>
  <span data-ttu-id="bedd4-103">Utilisez les classes d’événements de la catégorie d’événements **Locks** pour surveiller l’activité de verrouillage dans une instance du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bedd4-103">Use the event classes in the **Locks** event category to monitor locking activity in an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="bedd4-104">Ces classes d'événements facilitent la recherche de problèmes de verrouillage dus au fait que plusieurs utilisateurs lisent et modifient simultanément des données.</span><span class="sxs-lookup"><span data-stu-id="bedd4-104">These event classes can help you investigate locking problems caused by multiple users reading and modifying data concurrently.</span></span>  
  
 <span data-ttu-id="bedd4-105">Du fait que le [!INCLUDE[ssDE](../../includes/ssde-md.md)] traite souvent de nombreux verrous, la capture des classes d’événements **Locks** peut générer une surcharge importante sur le processeur et créer des tables ou des fichiers de trace volumineux.</span><span class="sxs-lookup"><span data-stu-id="bedd4-105">Because the [!INCLUDE[ssDE](../../includes/ssde-md.md)] often processes many locks, capturing the **Locks** event classes during a trace can incur significant overhead and result in large trace files or tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bedd4-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bedd4-106">In This Section</span></span>  
  
|<span data-ttu-id="bedd4-107">Rubrique</span><span class="sxs-lookup"><span data-stu-id="bedd4-107">Topic</span></span>|<span data-ttu-id="bedd4-108">Description</span><span class="sxs-lookup"><span data-stu-id="bedd4-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bedd4-109">Deadlock Graph, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="bedd4-109">Deadlock Graph Event Class</span></span>](deadlock-graph-event-class.md)|<span data-ttu-id="bedd4-110">Fournit une description XML d'un blocage.</span><span class="sxs-lookup"><span data-stu-id="bedd4-110">Provides an XML description of a deadlock.</span></span>|  
|[<span data-ttu-id="bedd4-111">Classe d'événements Lock:Acquired</span><span class="sxs-lookup"><span data-stu-id="bedd4-111">Lock:Acquired Event Class</span></span>](lock-acquired-event-class.md)|<span data-ttu-id="bedd4-112">Indique qu'un verrou a été acquis sur une ressource, par exemple une ligne d'une table.</span><span class="sxs-lookup"><span data-stu-id="bedd4-112">Indicates that a lock has been acquired on a resource, such as a row in a table.</span></span>|  
|[<span data-ttu-id="bedd4-113">Classe d'événements Lock:Cancel</span><span class="sxs-lookup"><span data-stu-id="bedd4-113">Lock:Cancel Event Class</span></span>](lock-cancel-event-class.md)|<span data-ttu-id="bedd4-114">Trace les requêtes de verrous qui ont été annulées avant l'acquisition du verrou (par exemple pour empêcher un blocage).</span><span class="sxs-lookup"><span data-stu-id="bedd4-114">Tracks requests for locks that were canceled before the lock was acquired (for example, to prevent a deadlock).</span></span>|  
|[<span data-ttu-id="bedd4-115">Classe d'événements Lock:Deadlock Chain</span><span class="sxs-lookup"><span data-stu-id="bedd4-115">Lock:Deadlock Chain Event Class</span></span>](lock-deadlock-chain-event-class.md)|<span data-ttu-id="bedd4-116">Contrôle les conditions de blocage et les objets impliqués.</span><span class="sxs-lookup"><span data-stu-id="bedd4-116">Monitors when deadlock conditions occur and which objects are involved.</span></span>|  
|[<span data-ttu-id="bedd4-117">Classe d'événements Lock:Deadlock</span><span class="sxs-lookup"><span data-stu-id="bedd4-117">Lock:Deadlock Event Class</span></span>](lock-deadlock-event-class.md)|<span data-ttu-id="bedd4-118">Trace à quel moment une transaction a demandé un verrou sur une ressource déjà verrouillée par une autre transaction, ce qui provoque un blocage.</span><span class="sxs-lookup"><span data-stu-id="bedd4-118">Tracks when a transaction has requested a lock on a resource already locked by another transaction, resulting in a deadlock.</span></span>|  
|[<span data-ttu-id="bedd4-119">Classe d'événements Lock:Escalation</span><span class="sxs-lookup"><span data-stu-id="bedd4-119">Lock:Escalation Event Class</span></span>](lock-escalation-event-class.md)|<span data-ttu-id="bedd4-120">Indique qu'un verrouillage spécifique s'est transformé en verrouillage de plus grande ampleur.</span><span class="sxs-lookup"><span data-stu-id="bedd4-120">Indicates that a finer-grained lock has been converted to a coarser-grained lock.</span></span>|  
|[<span data-ttu-id="bedd4-121">Lock:Released, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="bedd4-121">Lock:Released Event Class</span></span>](lock-released-event-class.md)|<span data-ttu-id="bedd4-122">Trace la libération d'un verrou.</span><span class="sxs-lookup"><span data-stu-id="bedd4-122">Tracks when a lock is released.</span></span>|  
|[<span data-ttu-id="bedd4-123">Classe d’événements Lock:Timeout &#40;timeout &#62; 0&#41;</span><span class="sxs-lookup"><span data-stu-id="bedd4-123">Lock:Timeout &#40;timeout &#62; 0&#41; Event Class</span></span>](lock-timeout-timeout-0-event-class.md)|<span data-ttu-id="bedd4-124">Trace à quel moment les demandes de verrous ne sont pas possibles car une autre transaction possède un verrou de blocage sur la ressource demandée.</span><span class="sxs-lookup"><span data-stu-id="bedd4-124">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span> <span data-ttu-id="bedd4-125">Cet événement se produit uniquement lorsque la valeur d'expiration du verrou est supérieure à zéro (0).</span><span class="sxs-lookup"><span data-stu-id="bedd4-125">This event occurs only in situations where the lock time-out value is greater than zero.</span></span>|  
|[<span data-ttu-id="bedd4-126">Lock:Timeout, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="bedd4-126">Lock:Timeout Event Class</span></span>](lock-timeout-event-class.md)|<span data-ttu-id="bedd4-127">Trace à quel moment les demandes de verrous ne sont pas possibles car une autre transaction possède un verrou de blocage sur la ressource demandée.</span><span class="sxs-lookup"><span data-stu-id="bedd4-127">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span>|  
  
  
