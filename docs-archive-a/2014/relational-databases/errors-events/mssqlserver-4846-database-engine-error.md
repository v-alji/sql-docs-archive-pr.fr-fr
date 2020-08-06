---
title: MSSQLSERVER_4846 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4846 (Database Engine error)
ms.assetid: a455e809-1883-4c7d-b3e3-835ee5bfe258
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 923137645aae72476fb4b2ae33f0cbbf3e81c2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698243"
---
# <a name="mssqlserver_4846"></a><span data-ttu-id="c9940-102">MSSQLSERVER_4846</span><span class="sxs-lookup"><span data-stu-id="c9940-102">MSSQLSERVER_4846</span></span>
    
## <a name="details"></a><span data-ttu-id="c9940-103">Détails</span><span class="sxs-lookup"><span data-stu-id="c9940-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9940-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="c9940-104">Product Name</span></span>|<span data-ttu-id="c9940-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9940-105">SQL Server</span></span>|  
|<span data-ttu-id="c9940-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="c9940-106">Event ID</span></span>|<span data-ttu-id="c9940-107">4846</span><span class="sxs-lookup"><span data-stu-id="c9940-107">4846</span></span>|  
|<span data-ttu-id="c9940-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="c9940-108">Event Source</span></span>|<span data-ttu-id="c9940-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c9940-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c9940-110">Composant</span><span class="sxs-lookup"><span data-stu-id="c9940-110">Component</span></span>|<span data-ttu-id="c9940-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c9940-111">SQLEngine</span></span>|  
|<span data-ttu-id="c9940-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="c9940-112">Symbolic Name</span></span>|<span data-ttu-id="c9940-113">BULKPROV_MEMORY</span><span class="sxs-lookup"><span data-stu-id="c9940-113">BULKPROV_MEMORY</span></span>|  
|<span data-ttu-id="c9940-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="c9940-114">Message Text</span></span>|<span data-ttu-id="c9940-115">Le fournisseur de données en bloc n'est pas parvenu à allouer de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="c9940-115">The bulk data provider failed to allocate memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9940-116">Explication</span><span class="sxs-lookup"><span data-stu-id="c9940-116">Explanation</span></span>  
 <span data-ttu-id="c9940-117">L'allocation de mémoire a échoué.</span><span class="sxs-lookup"><span data-stu-id="c9940-117">Memory allocation failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9940-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9940-118">User Action</span></span>  
 <span data-ttu-id="c9940-119">Pour corriger des erreurs de mémoire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c9940-119">Follow these general steps to troubleshoot memory errors:</span></span>  
  
1.  <span data-ttu-id="c9940-120">Vérifiez si d'autres applications ou services consomment de la mémoire sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="c9940-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="c9940-121">Reconfigurez les applications ou les services moins importants pour consommer moins de mémoire.</span><span class="sxs-lookup"><span data-stu-id="c9940-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="c9940-122">Démarrez la collecte des compteurs de l’analyseur de performances pour **SQL Server : Buffer Manager**, **SQL Server : Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="c9940-122">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="c9940-123">Vérifiez les paramètres de configuration de la mémoire de SQL Server suivants :</span><span class="sxs-lookup"><span data-stu-id="c9940-123">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="c9940-124">**Mémoire maximum du serveur**</span><span class="sxs-lookup"><span data-stu-id="c9940-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="c9940-125">**Mémoire minimum du serveur**</span><span class="sxs-lookup"><span data-stu-id="c9940-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="c9940-126">**Mémoire minimum par requête**</span><span class="sxs-lookup"><span data-stu-id="c9940-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="c9940-127">Notez tous les paramètres inhabituels.</span><span class="sxs-lookup"><span data-stu-id="c9940-127">Notice any unusual settings.</span></span> <span data-ttu-id="c9940-128">Si besoin est, corrigez-les.</span><span class="sxs-lookup"><span data-stu-id="c9940-128">Correct them as necessary.</span></span> <span data-ttu-id="c9940-129">Prenez en compte la mémoire requise pour [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9940-129">Account for memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="c9940-130">Les paramètres par défaut sont répertoriés dans la rubrique « Définition des options de configuration de serveur » de la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c9940-130">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="c9940-131">Observez la sortie de DBCC MEMORYSTATUS et la façon dont elle change lorsque vous voyez ces messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="c9940-131">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="c9940-132">Vérifiez la charge de travail (par exemple, le nombre de sessions simultanées, les requêtes en cours d'exécution).</span><span class="sxs-lookup"><span data-stu-id="c9940-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="c9940-133">Les actions ci-dessous peuvent éventuellement augmenter la quantité de mémoire disponible pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c9940-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="c9940-134">Si des applications autres que SQL Server consomment des ressources, essayez d'arrêter l'exécution de ces applications ou envisagez de les exécuter sur un serveur distinct.</span><span class="sxs-lookup"><span data-stu-id="c9940-134">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="c9940-135">Vous relâcherez ainsi la pression sur la mémoire externe.</span><span class="sxs-lookup"><span data-stu-id="c9940-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="c9940-136">Si vous avez configuré le paramètre **Mémoire maximum du serveur**, augmentez sa valeur.</span><span class="sxs-lookup"><span data-stu-id="c9940-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="c9940-137">Exécutez les commandes DBCC ci-dessous pour libérer plusieurs caches mémoire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9940-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="c9940-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="c9940-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="c9940-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="c9940-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="c9940-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="c9940-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="c9940-141">Si le problème persiste, vous devez poursuivre vos recherches et éventuellement, réduire la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="c9940-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
