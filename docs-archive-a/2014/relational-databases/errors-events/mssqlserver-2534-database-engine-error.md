---
title: MSSQLSERVER_2534 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2534 (Database Engine error)
ms.assetid: 121cf99d-0722-494c-be24-3369c1a0badc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 409c429f961cd8357bfa2e40663c33f3c1f2e36d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612876"
---
# <a name="mssqlserver_2534"></a><span data-ttu-id="0aa04-102">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="0aa04-102">MSSQLSERVER_2534</span></span>
    
## <a name="details"></a><span data-ttu-id="0aa04-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0aa04-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0aa04-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0aa04-104">Product Name</span></span>|<span data-ttu-id="0aa04-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0aa04-105">SQL Server</span></span>|  
|<span data-ttu-id="0aa04-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0aa04-106">Event ID</span></span>|<span data-ttu-id="0aa04-107">2534</span><span class="sxs-lookup"><span data-stu-id="0aa04-107">2534</span></span>|  
|<span data-ttu-id="0aa04-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0aa04-108">Event Source</span></span>|<span data-ttu-id="0aa04-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0aa04-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0aa04-110">Composant</span><span class="sxs-lookup"><span data-stu-id="0aa04-110">Component</span></span>|<span data-ttu-id="0aa04-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0aa04-111">SQLEngine</span></span>|  
|<span data-ttu-id="0aa04-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0aa04-112">Symbolic Name</span></span>|<span data-ttu-id="0aa04-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span><span class="sxs-lookup"><span data-stu-id="0aa04-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span></span>|  
|<span data-ttu-id="0aa04-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0aa04-114">Message Text</span></span>|<span data-ttu-id="0aa04-115">Erreur de table, la page P_ID, dont l’en-tête indique qu'elle est assignée à l’ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE), est assignée par un autre objet.</span><span class="sxs-lookup"><span data-stu-id="0aa04-115">Table error: Page P_ID, whose header indicates it as being allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), is allocated by another object.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0aa04-116">Explication</span><span class="sxs-lookup"><span data-stu-id="0aa04-116">Explanation</span></span>  
 <span data-ttu-id="0aa04-117">L’en-tête de la page contient l’ID d’unité d’allocation *A_ID*, mais aucune des pages IAM (Index Allocation Map) de cette unité d’allocation n’alloue la page.</span><span class="sxs-lookup"><span data-stu-id="0aa04-117">The header of the page contains the allocation unit ID, *A_ID*, but none of the Index Allocation Map (IAM) pages of that allocation unit allocates the page.</span></span> <span data-ttu-id="0aa04-118">L'en-tête de la page ne contenant pas l'ID d'unité d'allocation correct, la page génère une erreur de correspondance MSSQLServer_2533 qui se réfère à l'ID d'unité d'allocation auquel la page est de fait allouée.</span><span class="sxs-lookup"><span data-stu-id="0aa04-118">Therefore, the header of the page contains the wrong allocation unit ID, and the page will have a matching MSSQLServer_2533 error that corresponds to the allocation unit ID to which the page is actually allocated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0aa04-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0aa04-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="0aa04-120">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="0aa04-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="0aa04-121">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="0aa04-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="0aa04-122">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="0aa04-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="0aa04-123">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="0aa04-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="0aa04-124">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="0aa04-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="0aa04-125">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="0aa04-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="0aa04-126">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="0aa04-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="0aa04-127">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="0aa04-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="0aa04-128">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="0aa04-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="0aa04-129">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="0aa04-129">Restore from Backup</span></span>  
 <span data-ttu-id="0aa04-130">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0aa04-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="0aa04-131">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="0aa04-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="0aa04-132">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="0aa04-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="0aa04-133">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="0aa04-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="0aa04-134">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="0aa04-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="0aa04-135">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="0aa04-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="0aa04-136">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="0aa04-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="0aa04-137">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="0aa04-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="0aa04-138">REPAIR reconstruira l'index, si index il y a.</span><span class="sxs-lookup"><span data-stu-id="0aa04-138">REPAIR will rebuild the index if an index exists.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="0aa04-139">Le fait d’exécuter REPAIR pour corriger l’erreur de correspondance [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) libère la page avant la reconstruction.</span><span class="sxs-lookup"><span data-stu-id="0aa04-139">Running REPAIR for the matching [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) error deallocates the page before the rebuild.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="0aa04-140">Cette réparation peut entraîner une perte de données.</span><span class="sxs-lookup"><span data-stu-id="0aa04-140">This repair may cause data loss.</span></span>  
  
  
