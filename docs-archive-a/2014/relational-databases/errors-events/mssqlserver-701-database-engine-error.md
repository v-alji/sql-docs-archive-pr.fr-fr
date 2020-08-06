---
title: MSSQLSERVER_701 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 701 (Database Engine error)
ms.assetid: 3b975000-63a1-43c2-a40f-89d0a8a36bef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 542535223d3e394c72079092411add143de61545
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603532"
---
# <a name="mssqlserver_701"></a><span data-ttu-id="0eafd-102">MSSQLSERVER_701</span><span class="sxs-lookup"><span data-stu-id="0eafd-102">MSSQLSERVER_701</span></span>
    
## <a name="details"></a><span data-ttu-id="0eafd-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0eafd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0eafd-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0eafd-104">Product Name</span></span>|<span data-ttu-id="0eafd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0eafd-105">SQL Server</span></span>|  
|<span data-ttu-id="0eafd-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0eafd-106">Event ID</span></span>|<span data-ttu-id="0eafd-107">701</span><span class="sxs-lookup"><span data-stu-id="0eafd-107">701</span></span>|  
|<span data-ttu-id="0eafd-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0eafd-108">Event Source</span></span>|<span data-ttu-id="0eafd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0eafd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0eafd-110">Composant</span><span class="sxs-lookup"><span data-stu-id="0eafd-110">Component</span></span>|<span data-ttu-id="0eafd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0eafd-111">SQLEngine</span></span>|  
|<span data-ttu-id="0eafd-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0eafd-112">Symbolic Name</span></span>|<span data-ttu-id="0eafd-113">NOSYSMEM</span><span class="sxs-lookup"><span data-stu-id="0eafd-113">NOSYSMEM</span></span>|  
|<span data-ttu-id="0eafd-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0eafd-114">Message Text</span></span>|<span data-ttu-id="0eafd-115">Mémoire système insuffisante pour exécuter cette requête.</span><span class="sxs-lookup"><span data-stu-id="0eafd-115">There is insufficient system memory to run this query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0eafd-116">Explication</span><span class="sxs-lookup"><span data-stu-id="0eafd-116">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0eafd-117">n'a pas réussi à allouer suffisamment de mémoire pour exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="0eafd-117">has failed to allocate sufficient memory to run the query.</span></span> <span data-ttu-id="0eafd-118">Cela peut être dû à diverses raisons, notamment des paramètres de système d’exploitation, une disponibilité de mémoire physique ou des limites de mémoire sur la charge de travail en cours.</span><span class="sxs-lookup"><span data-stu-id="0eafd-118">This can be caused by a variety of reasons including operating system settings, physical memory availability, or memory limits on the current workload.</span></span> <span data-ttu-id="0eafd-119">Dans la plupart des cas, la transaction qui a échoué n’est pas la cause de cette erreur.</span><span class="sxs-lookup"><span data-stu-id="0eafd-119">In most cases, the transaction that failed is not the cause of this error.</span></span>  
  
 <span data-ttu-id="0eafd-120">Les requêtes de diagnostic, telles que les instructions DBCC, peuvent échouer parce que la mémoire du serveur est insuffisante.</span><span class="sxs-lookup"><span data-stu-id="0eafd-120">Diagnostic queries, such as DBCC statements, may fail because server the does not have sufficient memory.</span></span>  
  
 <span data-ttu-id="0eafd-121">Le délai a été dépassé pendant l'attente de ressources mémoire pour exécuter la requête dans le pool de ressources 'default'.</span><span class="sxs-lookup"><span data-stu-id="0eafd-121">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0eafd-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0eafd-122">User Action</span></span>  
 <span data-ttu-id="0eafd-123">Si vous n'utilisez pas le gouverneur de ressources, nous vous recommandons de vérifier l'état général et la charge du serveur, ou les paramètres du pool de ressources ou du groupe de charges de travail.</span><span class="sxs-lookup"><span data-stu-id="0eafd-123">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="0eafd-124">La liste suivante présente les procédures générales à suivre pour résoudre les erreurs de mémoire.</span><span class="sxs-lookup"><span data-stu-id="0eafd-124">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="0eafd-125">Vérifiez si d'autres applications ou services consomment de la mémoire sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="0eafd-125">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="0eafd-126">Reconfigurez les applications ou les services moins importants pour consommer moins de mémoire.</span><span class="sxs-lookup"><span data-stu-id="0eafd-126">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="0eafd-127">Commencez la collecte des compteurs de l’analyseur de performances pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  **: Buffer Manager**, **SQL Server : Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="0eafd-127">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="0eafd-128">Vérifiez les paramètres de configuration de la mémoire de SQL Server suivants :</span><span class="sxs-lookup"><span data-stu-id="0eafd-128">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="0eafd-129">**Mémoire maximum du serveur**</span><span class="sxs-lookup"><span data-stu-id="0eafd-129">**max server memory**</span></span>  
  
    -   <span data-ttu-id="0eafd-130">**Mémoire minimum du serveur**</span><span class="sxs-lookup"><span data-stu-id="0eafd-130">**min server memory**</span></span>  
  
    -   <span data-ttu-id="0eafd-131">**Mémoire minimum par requête**</span><span class="sxs-lookup"><span data-stu-id="0eafd-131">**min memory per query**</span></span>  
  
     <span data-ttu-id="0eafd-132">Identifiez les paramètres inhabituels.</span><span class="sxs-lookup"><span data-stu-id="0eafd-132">Notice unusual settings.</span></span> <span data-ttu-id="0eafd-133">Si besoin est, corrigez-les.</span><span class="sxs-lookup"><span data-stu-id="0eafd-133">Correct them as necessary.</span></span> <span data-ttu-id="0eafd-134">Prenez en compte l'augmentation de la mémoire requise.</span><span class="sxs-lookup"><span data-stu-id="0eafd-134">Account for increased memory requirements.</span></span> <span data-ttu-id="0eafd-135">Les paramètres par défaut sont répertoriés dans la rubrique « Définition des options de configuration de serveur » de la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0eafd-135">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="0eafd-136">Observez la sortie de DBCC MEMORYSTATUS et la façon dont elle change lorsque vous voyez ces messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="0eafd-136">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="0eafd-137">Vérifiez la charge de travail (par exemple, le nombre de sessions simultanées, les requêtes en cours d'exécution).</span><span class="sxs-lookup"><span data-stu-id="0eafd-137">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="0eafd-138">Les actions ci-dessous peuvent éventuellement augmenter la quantité de mémoire disponible pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="0eafd-138">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="0eafd-139">Si des applications autres que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consomment des ressources, essayez d'arrêter l'exécution de ces applications ou envisagez de les exécuter sur un serveur distinct.</span><span class="sxs-lookup"><span data-stu-id="0eafd-139">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="0eafd-140">Vous relâcherez ainsi la pression sur la mémoire externe.</span><span class="sxs-lookup"><span data-stu-id="0eafd-140">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="0eafd-141">Si vous avez configuré le paramètre **Mémoire maximum du serveur**, augmentez sa valeur.</span><span class="sxs-lookup"><span data-stu-id="0eafd-141">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="0eafd-142">Exécutez les commandes DBCC ci-dessous pour libérer plusieurs caches mémoire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0eafd-142">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="0eafd-143">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="0eafd-143">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="0eafd-144">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="0eafd-144">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="0eafd-145">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="0eafd-145">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="0eafd-146">Si le problème persiste, vous devez poursuivre vos recherches et éventuellement, réduire la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="0eafd-146">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
