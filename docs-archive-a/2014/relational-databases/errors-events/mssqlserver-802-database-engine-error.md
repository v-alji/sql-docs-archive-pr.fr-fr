---
title: MSSQLSERVER_802 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 802 (Database Engine error)
ms.assetid: 5892ed24-4dcb-4bf9-a8a4-a7ca898832d5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9edcdda1410d7651f7c7531ef98c64c85741f15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615167"
---
# <a name="mssqlserver_802"></a><span data-ttu-id="a0923-102">MSSQLSERVER_802</span><span class="sxs-lookup"><span data-stu-id="a0923-102">MSSQLSERVER_802</span></span>
    
## <a name="details"></a><span data-ttu-id="a0923-103">Détails</span><span class="sxs-lookup"><span data-stu-id="a0923-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0923-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="a0923-104">Product Name</span></span>|<span data-ttu-id="a0923-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a0923-105">SQL Server</span></span>|  
|<span data-ttu-id="a0923-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="a0923-106">Event ID</span></span>|<span data-ttu-id="a0923-107">802</span><span class="sxs-lookup"><span data-stu-id="a0923-107">802</span></span>|  
|<span data-ttu-id="a0923-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="a0923-108">Event Source</span></span>|<span data-ttu-id="a0923-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a0923-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a0923-110">Composant</span><span class="sxs-lookup"><span data-stu-id="a0923-110">Component</span></span>|<span data-ttu-id="a0923-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a0923-111">SQLEngine</span></span>|  
|<span data-ttu-id="a0923-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="a0923-112">Symbolic Name</span></span>|<span data-ttu-id="a0923-113">NO_BUFS</span><span class="sxs-lookup"><span data-stu-id="a0923-113">NO_BUFS</span></span>|  
|<span data-ttu-id="a0923-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="a0923-114">Message Text</span></span>|<span data-ttu-id="a0923-115">Mémoire disponible insuffisante dans le pool de mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="a0923-115">There is insufficient memory available in the buffer pool.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a0923-116">Explication</span><span class="sxs-lookup"><span data-stu-id="a0923-116">Explanation</span></span>  
 <span data-ttu-id="a0923-117">Ceci survient lorsque le pool de mémoires tampons est plein et a atteint sa taille maximale.</span><span class="sxs-lookup"><span data-stu-id="a0923-117">This is caused when the buffer pool is full and the buffer pool can not grow any larger.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a0923-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a0923-118">User Action</span></span>  
 <span data-ttu-id="a0923-119">La liste suivante présente les procédures générales à suivre pour résoudre les erreurs de mémoire.</span><span class="sxs-lookup"><span data-stu-id="a0923-119">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="a0923-120">Vérifiez si d'autres applications ou services consomment de la mémoire sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="a0923-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="a0923-121">Reconfigurez les applications ou les services moins importants pour consommer moins de mémoire.</span><span class="sxs-lookup"><span data-stu-id="a0923-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="a0923-122">Commencez la collecte des compteurs de l’analyseur de performances pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  **: Buffer Manager**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  **: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="a0923-122">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="a0923-123">Vérifiez les paramètres de configuration de la mémoire de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suivants :</span><span class="sxs-lookup"><span data-stu-id="a0923-123">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="a0923-124">**Mémoire maximum du serveur**</span><span class="sxs-lookup"><span data-stu-id="a0923-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="a0923-125">**Mémoire minimum du serveur**</span><span class="sxs-lookup"><span data-stu-id="a0923-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="a0923-126">**Mémoire minimum par requête**</span><span class="sxs-lookup"><span data-stu-id="a0923-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="a0923-127">Identifiez tout paramètre inhabituel et corrigez-le si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a0923-127">Notice any unusual settings and correct them as necessary.</span></span> <span data-ttu-id="a0923-128">Prenez en compte l'augmentation de la mémoire requise pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0923-128">Account for increased memory requirements for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a0923-129">Les paramètres par défaut sont répertoriés dans la rubrique « Définition des options de configuration de serveur » de la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0923-129">Default settings are listed in "Setting Server Configuration Options" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="a0923-130">Observez la sortie de DBCC MEMORYSTATUS et la façon dont elle change lorsque vous voyez ces messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="a0923-130">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="a0923-131">Vérifiez la charge de travail (le nombre de sessions simultanées, les requêtes en cours d'exécution).</span><span class="sxs-lookup"><span data-stu-id="a0923-131">Check the workload (number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="a0923-132">Les actions ci-dessous peuvent éventuellement augmenter la quantité de mémoire disponible pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a0923-132">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="a0923-133">Si des applications voisines de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consomment des ressources, essayez d'en interrompre l'exécution ou pensez à les exécuter sur un serveur séparé.</span><span class="sxs-lookup"><span data-stu-id="a0923-133">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping these applications or running them on a separate server.</span></span>  
  
-   <span data-ttu-id="a0923-134">Si vous avez configuré le paramètre **max server memory**, augmentez sa valeur.</span><span class="sxs-lookup"><span data-stu-id="a0923-134">If you have configured **max server memory,** increase the setting.</span></span>  
  
 <span data-ttu-id="a0923-135">Exécutez les commandes DBCC ci-dessous pour libérer plusieurs caches mémoire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0923-135">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="a0923-136">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="a0923-136">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="a0923-137">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="a0923-137">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="a0923-138">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="a0923-138">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="a0923-139">Si le problème persiste, vous devez poursuivre vos recherches et éventuellement, réduire la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="a0923-139">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
