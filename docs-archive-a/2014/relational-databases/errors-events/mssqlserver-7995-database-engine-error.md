---
title: MSSQLSERVER_7995 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7995 (Database Engine error)
ms.assetid: af6d6322-3cba-43d8-be97-e6ef15f8c933
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c65cf2b16c4d7a0dcf40272f8280205a111d08e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610647"
---
# <a name="mssqlserver_7995"></a><span data-ttu-id="43a37-102">MSSQLSERVER_7995</span><span class="sxs-lookup"><span data-stu-id="43a37-102">MSSQLSERVER_7995</span></span>
    
## <a name="details"></a><span data-ttu-id="43a37-103">Détails</span><span class="sxs-lookup"><span data-stu-id="43a37-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43a37-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="43a37-104">Product Name</span></span>|<span data-ttu-id="43a37-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="43a37-105">SQL Server</span></span>|  
|<span data-ttu-id="43a37-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="43a37-106">Event ID</span></span>|<span data-ttu-id="43a37-107">7995</span><span class="sxs-lookup"><span data-stu-id="43a37-107">7995</span></span>|  
|<span data-ttu-id="43a37-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="43a37-108">Event Source</span></span>|<span data-ttu-id="43a37-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="43a37-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="43a37-110">Composant</span><span class="sxs-lookup"><span data-stu-id="43a37-110">Component</span></span>|<span data-ttu-id="43a37-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="43a37-111">SQLEngine</span></span>|  
|<span data-ttu-id="43a37-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="43a37-112">Symbolic Name</span></span>|<span data-ttu-id="43a37-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="43a37-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span></span>|  
|<span data-ttu-id="43a37-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="43a37-114">Message Text</span></span>|<span data-ttu-id="43a37-115">Base de données 'DBNAME' : des erreurs de cohérence dans les catalogues système empêchent la poursuite du traitement de DBCC CHECKNAME.</span><span class="sxs-lookup"><span data-stu-id="43a37-115">Database 'DBNAME': consistency errors in system catalogs prevent further DBCC CHECKNAME processing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="43a37-116">Explication</span><span class="sxs-lookup"><span data-stu-id="43a37-116">Explanation</span></span>  
 <span data-ttu-id="43a37-117">Le processus DBCC CHECKDB se compose des trois phases suivantes :</span><span class="sxs-lookup"><span data-stu-id="43a37-117">The DBCC CHECKDB process consists of the following three stages:</span></span>  
  
1.  <span data-ttu-id="43a37-118">Vérifications de l'allocation.</span><span class="sxs-lookup"><span data-stu-id="43a37-118">Allocation checks.</span></span> <span data-ttu-id="43a37-119">Cela est équivalent à l'exécution de DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="43a37-119">This is equivalent to running DBCC CHECKALLOC.</span></span>  
  
2.  <span data-ttu-id="43a37-120">Vérifications de cohérence des tables système.</span><span class="sxs-lookup"><span data-stu-id="43a37-120">System tables consistency checks.</span></span> <span data-ttu-id="43a37-121">Cela est équivalent à l'exécution de DBCC CHECKTABLE sur une liste réduite de tables de base système nécessaires.</span><span class="sxs-lookup"><span data-stu-id="43a37-121">This is equivalent to running DBCC CHECKTABLE on a small list of necessary system base tables.</span></span>  
  
3.  <span data-ttu-id="43a37-122">Vérifications de cohérence de la base de données complète.</span><span class="sxs-lookup"><span data-stu-id="43a37-122">Complete database consistency checks.</span></span>  
  
 <span data-ttu-id="43a37-123">Le message d'erreur MSSQLEngine_7995 est généré dans la phase 2 pour indiquer que DBCC CHECKDB a trouvé des erreurs que la commande ne peut pas réparer ou qui n'ont pas été spécifiées à REPAIR.</span><span class="sxs-lookup"><span data-stu-id="43a37-123">MSSQLEngine_7995 is raised in stage 2 to indicate that DBCC CHECKDB has found errors that the command cannot repair or that REPAIR has not been specified.</span></span> <span data-ttu-id="43a37-124">DBCC CHECKDB ne peut pas continuer avec la phase 3 car soit les tables de base système en question stockent les métadonnées pour tous les objets dans la base de données, soit les tables de base système sont endommagées.</span><span class="sxs-lookup"><span data-stu-id="43a37-124">DBCC CHECKDB cannot continue with stage 3 because either the system base tables in question store the metadata for all objects in the database or the system base tables are corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43a37-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="43a37-125">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="43a37-126">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="43a37-126">Look for Hardware Failure</span></span>  
 <span data-ttu-id="43a37-127">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="43a37-127">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="43a37-128">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="43a37-128">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="43a37-129">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="43a37-129">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="43a37-130">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="43a37-130">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="43a37-131">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="43a37-131">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="43a37-132">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="43a37-132">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="43a37-133">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="43a37-133">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="43a37-134">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="43a37-134">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="43a37-135">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="43a37-135">Restore from Backup</span></span>  
 <span data-ttu-id="43a37-136">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43a37-136">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="43a37-137">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="43a37-137">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="43a37-138">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="43a37-138">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="43a37-139">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="43a37-139">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="43a37-140">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="43a37-140">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="43a37-141">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="43a37-141">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="43a37-142">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="43a37-142">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="43a37-143">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="43a37-143">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="43a37-144">Examinez la liste des erreurs pour voir ce que REPAIR fera pour chaque erreur.</span><span class="sxs-lookup"><span data-stu-id="43a37-144">Examine the list of errors to see what REPAIR will do for each.</span></span>  
  
  
