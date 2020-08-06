---
title: MSSQLSERVER_8651 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8651 (Database Engine error)
ms.assetid: 4cc3498d-5449-4c4e-b1f9-3271831c725a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a385350a05edee3759ab83d318e365f5b4f3e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698232"
---
# <a name="mssqlserver_8651"></a><span data-ttu-id="4081f-102">MSSQLSERVER_8651</span><span class="sxs-lookup"><span data-stu-id="4081f-102">MSSQLSERVER_8651</span></span>
    
## <a name="details"></a><span data-ttu-id="4081f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="4081f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4081f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="4081f-104">Product Name</span></span>|<span data-ttu-id="4081f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4081f-105">SQL Server</span></span>|  
|<span data-ttu-id="4081f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="4081f-106">Event ID</span></span>|<span data-ttu-id="4081f-107">8651</span><span class="sxs-lookup"><span data-stu-id="4081f-107">8651</span></span>|  
|<span data-ttu-id="4081f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="4081f-108">Event Source</span></span>|<span data-ttu-id="4081f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4081f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4081f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="4081f-110">Component</span></span>|<span data-ttu-id="4081f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4081f-111">SQLEngine</span></span>|  
|<span data-ttu-id="4081f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="4081f-112">Symbolic Name</span></span>|<span data-ttu-id="4081f-113">MEMGRANT_ERR</span><span class="sxs-lookup"><span data-stu-id="4081f-113">MEMGRANT_ERR</span></span>|  
|<span data-ttu-id="4081f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="4081f-114">Message Text</span></span>|<span data-ttu-id="4081f-115">Impossible d'exécuter l'opération demandée, car la mémoire est insuffisante.</span><span class="sxs-lookup"><span data-stu-id="4081f-115">Could not perform the requested operation because the minimum query memory is not available.</span></span> <span data-ttu-id="4081f-116">Diminuez la valeur configurée pour l'option de configuration de serveur « min memory per query ».</span><span class="sxs-lookup"><span data-stu-id="4081f-116">Decrease the configured value for the 'min memory per query' server configuration option.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4081f-117">Explication</span><span class="sxs-lookup"><span data-stu-id="4081f-117">Explanation</span></span>  
 <span data-ttu-id="4081f-118">D'autres processus consomment de la mémoire du serveur (provoquant des insuffisances de mémoire dans le serveur).</span><span class="sxs-lookup"><span data-stu-id="4081f-118">Other processes are consuming server memory (exerting memory pressure in the server).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4081f-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="4081f-119">User Action</span></span>  
 <span data-ttu-id="4081f-120">Diminuez la valeur configurée pour l'option de configuration de serveur « min memory per query » ou diminuez la charge des requêtes sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="4081f-120">Either decrease the configured value for the min memory per query' server configuration option or reduce the query load to the server.</span></span>  
  
 <span data-ttu-id="4081f-121">La liste suivante présente les procédures générales à suivre pour résoudre les erreurs de mémoire.</span><span class="sxs-lookup"><span data-stu-id="4081f-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="4081f-122">Vérifiez si d'autres applications ou services consomment de la mémoire sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="4081f-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="4081f-123">Reconfigurez les applications ou les services moins importants pour consommer moins de mémoire.</span><span class="sxs-lookup"><span data-stu-id="4081f-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="4081f-124">Démarrez la collecte des compteurs de l’analyseur de performances pour **SQL Server : Buffer Manager**, **SQL Server : Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="4081f-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="4081f-125">Vérifiez les paramètres de configuration de la mémoire de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suivants :</span><span class="sxs-lookup"><span data-stu-id="4081f-125">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="4081f-126">**Mémoire maximum du serveur**</span><span class="sxs-lookup"><span data-stu-id="4081f-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="4081f-127">**Mémoire minimum du serveur**</span><span class="sxs-lookup"><span data-stu-id="4081f-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="4081f-128">**Mémoire minimum par requête**</span><span class="sxs-lookup"><span data-stu-id="4081f-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="4081f-129">Identifiez les paramètres inhabituels.</span><span class="sxs-lookup"><span data-stu-id="4081f-129">Notice unusual settings.</span></span> <span data-ttu-id="4081f-130">Si besoin est, corrigez-les.</span><span class="sxs-lookup"><span data-stu-id="4081f-130">Correct them as necessary.</span></span> <span data-ttu-id="4081f-131">Les paramètres par défaut sont répertoriés dans la rubrique « Définition des options de configuration de serveur » de la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4081f-131">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="4081f-132">Vérifiez la charge de travail (par exemple, le nombre de sessions simultanées, les requêtes en cours d'exécution).</span><span class="sxs-lookup"><span data-stu-id="4081f-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="4081f-133">Les actions ci-dessous peuvent éventuellement augmenter la quantité de mémoire disponible pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4081f-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="4081f-134">Si des applications autres que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consomment des ressources, essayez d'arrêter l'exécution de ces applications ou envisagez de les exécuter sur un serveur distinct.</span><span class="sxs-lookup"><span data-stu-id="4081f-134">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="4081f-135">Vous relâcherez ainsi la pression sur la mémoire externe.</span><span class="sxs-lookup"><span data-stu-id="4081f-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="4081f-136">Si vous avez configuré le paramètre **Mémoire maximum du serveur**, augmentez sa valeur.</span><span class="sxs-lookup"><span data-stu-id="4081f-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="4081f-137">Exécutez les commandes DBCC ci-dessous pour libérer plusieurs caches mémoire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4081f-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="4081f-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="4081f-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="4081f-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="4081f-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="4081f-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="4081f-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="4081f-141">Si le problème persiste, vous devez poursuivre vos recherches et éventuellement, réduire la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="4081f-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4081f-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4081f-142">See Also</span></span>  
 <span data-ttu-id="4081f-143">[DBCC FREESYSTEMCACHE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4081f-143">[DBCC FREESYSTEMCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span></span>  
 <span data-ttu-id="4081f-144">[DBCC FREESESSIONCACHE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4081f-144">[DBCC FREESESSIONCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span></span>  
 <span data-ttu-id="4081f-145">[DBCC FREEPROCCACHE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4081f-145">[DBCC FREEPROCCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span></span>  
 <span data-ttu-id="4081f-146">[Options de configuration de serveur &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4081f-146">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="4081f-147">[SQL Server, objet Gestionnaire de tampons](../performance-monitor/sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="4081f-147">[SQL Server, Buffer Manager Object](../performance-monitor/sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="4081f-148">SQL Server, objet Memory Manager</span><span class="sxs-lookup"><span data-stu-id="4081f-148">SQL Server, Memory Manager Object</span></span>](../performance-monitor/sql-server-memory-manager-object.md)  
  
  
