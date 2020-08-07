---
title: MSSQLSERVER_8645 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8645 (Database Engine error)
ms.assetid: 63d6d6d7-3850-4061-8e96-b1fa665e3180
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7be9774452e2008c34ecb52d228a0123992c5368
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611809"
---
# <a name="mssqlserver_8645"></a><span data-ttu-id="2d754-102">MSSQLSERVER_8645</span><span class="sxs-lookup"><span data-stu-id="2d754-102">MSSQLSERVER_8645</span></span>
    
## <a name="details"></a><span data-ttu-id="2d754-103">Détails</span><span class="sxs-lookup"><span data-stu-id="2d754-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2d754-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="2d754-104">Product Name</span></span>|<span data-ttu-id="2d754-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2d754-105">SQL Server</span></span>|  
|<span data-ttu-id="2d754-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="2d754-106">Event ID</span></span>|<span data-ttu-id="2d754-107">8645</span><span class="sxs-lookup"><span data-stu-id="2d754-107">8645</span></span>|  
|<span data-ttu-id="2d754-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="2d754-108">Event Source</span></span>|<span data-ttu-id="2d754-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2d754-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2d754-110">Composant</span><span class="sxs-lookup"><span data-stu-id="2d754-110">Component</span></span>|<span data-ttu-id="2d754-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2d754-111">SQLEngine</span></span>|  
|<span data-ttu-id="2d754-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="2d754-112">Symbolic Name</span></span>|<span data-ttu-id="2d754-113">MEMTIMEDOUT_ERR</span><span class="sxs-lookup"><span data-stu-id="2d754-113">MEMTIMEDOUT_ERR</span></span>|  
|<span data-ttu-id="2d754-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="2d754-114">Message Text</span></span>|<span data-ttu-id="2d754-115">Dépassement du délai lors de l'attente des ressources mémoire pour l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="2d754-115">A time out occurred while waiting for memory resources to execute the query.</span></span> <span data-ttu-id="2d754-116">Réexécutez la requête.</span><span class="sxs-lookup"><span data-stu-id="2d754-116">Rerun the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2d754-117">Explication</span><span class="sxs-lookup"><span data-stu-id="2d754-117">Explanation</span></span>  
 <span data-ttu-id="2d754-118">Le délai a été dépassé pendant l'attente de ressources mémoire pour exécuter la requête dans le pool de ressources 'default'.</span><span class="sxs-lookup"><span data-stu-id="2d754-118">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2d754-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2d754-119">User Action</span></span>  
 <span data-ttu-id="2d754-120">Si vous n'utilisez pas le gouverneur de ressources, nous vous recommandons de vérifier l'état général et la charge du serveur, ou les paramètres du pool de ressources ou du groupe de charges de travail.</span><span class="sxs-lookup"><span data-stu-id="2d754-120">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="2d754-121">La liste suivante présente les procédures générales à suivre pour résoudre les erreurs de mémoire.</span><span class="sxs-lookup"><span data-stu-id="2d754-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="2d754-122">Vérifiez si d'autres applications ou services consomment de la mémoire sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="2d754-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="2d754-123">Reconfigurez les applications ou les services moins importants pour consommer moins de mémoire.</span><span class="sxs-lookup"><span data-stu-id="2d754-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="2d754-124">Démarrez la collecte des compteurs de l’analyseur de performances pour **SQL Server : Buffer Manager**, **SQL Server : Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="2d754-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="2d754-125">Vérifiez les paramètres de configuration de la mémoire de SQL Server suivants :</span><span class="sxs-lookup"><span data-stu-id="2d754-125">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="2d754-126">**Mémoire maximum du serveur**</span><span class="sxs-lookup"><span data-stu-id="2d754-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="2d754-127">**Mémoire minimum du serveur**</span><span class="sxs-lookup"><span data-stu-id="2d754-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="2d754-128">**Mémoire minimum par requête**</span><span class="sxs-lookup"><span data-stu-id="2d754-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="2d754-129">Identifiez les paramètres inhabituels.</span><span class="sxs-lookup"><span data-stu-id="2d754-129">Notice unusual settings.</span></span> <span data-ttu-id="2d754-130">Si besoin est, corrigez-les.</span><span class="sxs-lookup"><span data-stu-id="2d754-130">Correct them as necessary.</span></span> <span data-ttu-id="2d754-131">Prenez en compte l'augmentation de la mémoire requise pour [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d754-131">Account for increased memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2d754-132">Les paramètres par défaut sont répertoriés dans la rubrique « Définition des options de configuration de serveur » de la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2d754-132">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="2d754-133">Observez la sortie de DBCC MEMORYSTATUS et la façon dont elle change lorsque vous voyez ces messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="2d754-133">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="2d754-134">Vérifiez la charge de travail (par exemple, le nombre de sessions simultanées, les requêtes en cours d'exécution).</span><span class="sxs-lookup"><span data-stu-id="2d754-134">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="2d754-135">Les actions ci-dessous peuvent éventuellement augmenter la quantité de mémoire disponible pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="2d754-135">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="2d754-136">Si des applications autres que SQL Server consomment des ressources, essayez d'arrêter l'exécution de ces applications ou envisagez de les exécuter sur un serveur distinct.</span><span class="sxs-lookup"><span data-stu-id="2d754-136">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="2d754-137">Vous relâcherez ainsi la pression sur la mémoire externe.</span><span class="sxs-lookup"><span data-stu-id="2d754-137">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="2d754-138">Si vous avez configuré le paramètre **Mémoire maximum du serveur**, augmentez sa valeur.</span><span class="sxs-lookup"><span data-stu-id="2d754-138">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="2d754-139">Exécutez les commandes DBCC ci-dessous pour libérer plusieurs caches mémoire SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2d754-139">Run the following DBCC commands to free several SQL Server memory caches.</span></span>  
  
-   <span data-ttu-id="2d754-140">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="2d754-140">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="2d754-141">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="2d754-141">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="2d754-142">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="2d754-142">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="2d754-143">Si le problème persiste, vous devez poursuivre vos recherches et éventuellement, réduire la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="2d754-143">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
