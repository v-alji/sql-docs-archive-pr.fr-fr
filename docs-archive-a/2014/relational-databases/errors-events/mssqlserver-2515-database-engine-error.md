---
title: MSSQLSERVER_2515 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2515 (Database Engine error)
ms.assetid: af93aa29-70c9-4923-90af-aafadb20c1c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73b2d8b8ff01b97428ba6149f537d96044c6ae3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696879"
---
# <a name="mssqlserver_2515"></a><span data-ttu-id="b02f5-102">MSSQLSERVER_2515</span><span class="sxs-lookup"><span data-stu-id="b02f5-102">MSSQLSERVER_2515</span></span>
    
## <a name="details"></a><span data-ttu-id="b02f5-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b02f5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b02f5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b02f5-104">Product Name</span></span>|<span data-ttu-id="b02f5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b02f5-105">SQL Server</span></span>|  
|<span data-ttu-id="b02f5-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b02f5-106">Event ID</span></span>|<span data-ttu-id="b02f5-107">2515</span><span class="sxs-lookup"><span data-stu-id="b02f5-107">2515</span></span>|  
|<span data-ttu-id="b02f5-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b02f5-108">Event Source</span></span>|<span data-ttu-id="b02f5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b02f5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b02f5-110">Composant</span><span class="sxs-lookup"><span data-stu-id="b02f5-110">Component</span></span>|<span data-ttu-id="b02f5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b02f5-111">SQLEngine</span></span>|  
|<span data-ttu-id="b02f5-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b02f5-112">Symbolic Name</span></span>|<span data-ttu-id="b02f5-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span><span class="sxs-lookup"><span data-stu-id="b02f5-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span></span>|  
|<span data-ttu-id="b02f5-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b02f5-114">Message Text</span></span>|<span data-ttu-id="b02f5-115">La page P_ID, ID d'objet O_ID, ID d'index I_ID, ID de partition PN_ID, ID d'unité d'allocation A_ID (type TYPE) a été modifiée mais n'est pas marquée comme telle dans la bitmap de sauvegarde différentielle.</span><span class="sxs-lookup"><span data-stu-id="b02f5-115">Page P_ID, object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID type TYPE has been modified but is not marked modified in the differential backup bitmap.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b02f5-116">Explication</span><span class="sxs-lookup"><span data-stu-id="b02f5-116">Explanation</span></span>  
 <span data-ttu-id="b02f5-117">La page spécifiée a un numéro séquentiel dans le journal (LSN) supérieur au numéro LSN de référence différentiel dans le gestionnaire de sauvegarde de la base de données ou au numéro LSN de la base différentielle dans le bloc de contrôle des fichiers du fichier, selon celui qui est le plus récent.</span><span class="sxs-lookup"><span data-stu-id="b02f5-117">The page specified has a log sequence number (LSN) that is higher than the differential reference LSN in the BackupManager of the database, or the differential base LSN in the file control block of the file, whichever is more recent.</span></span> <span data-ttu-id="b02f5-118">Toutefois, la page n'est pas marquée comme modifiée dans la bitmap de sauvegarde différentielle.</span><span class="sxs-lookup"><span data-stu-id="b02f5-118">However, the page is not marked as changed in the differential backup bitmap.</span></span>  
  
 <span data-ttu-id="b02f5-119">Une seule page par base de données sera signalée, car cette vérification s'effectue uniquement lorsque la bitmap différentielle est sans erreur.</span><span class="sxs-lookup"><span data-stu-id="b02f5-119">Only one page per database will be reported, because this check is only performed when the differential bitmap is known to be error free.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b02f5-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b02f5-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b02f5-121">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="b02f5-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b02f5-122">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="b02f5-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b02f5-123">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="b02f5-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b02f5-124">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="b02f5-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b02f5-125">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="b02f5-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b02f5-126">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="b02f5-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b02f5-127">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="b02f5-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b02f5-128">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="b02f5-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b02f5-129">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="b02f5-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b02f5-130">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b02f5-130">Restore from Backup</span></span>  
 <span data-ttu-id="b02f5-131">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b02f5-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b02f5-132">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b02f5-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b02f5-133">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="b02f5-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="b02f5-134">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b02f5-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="b02f5-135">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="b02f5-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b02f5-136">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="b02f5-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="b02f5-137">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="b02f5-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="b02f5-138">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="b02f5-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="b02f5-139">L'exécution de REPAIR invalidera la bitmap différentielle.</span><span class="sxs-lookup"><span data-stu-id="b02f5-139">Running REPAIR will invalidate the differential bitmap.</span></span> <span data-ttu-id="b02f5-140">Vous ne pouvez pas effectuer de sauvegarde différentielle tant qu'une sauvegarde de base de données complète n'a pas été effectuée.</span><span class="sxs-lookup"><span data-stu-id="b02f5-140">You cannot perform a differential backup until a full database backup is taken.</span></span> <span data-ttu-id="b02f5-141">La sauvegarde complète fournit une base pour la reconstruction de la bitmap différentielle.</span><span class="sxs-lookup"><span data-stu-id="b02f5-141">The full database backup provides a baseline for the differential bitmap to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b02f5-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b02f5-142">See Also</span></span>  
 <span data-ttu-id="b02f5-143">[Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b02f5-143">[Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="b02f5-144">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="b02f5-144">MSSQLSERVER_2516</span></span>](mssqlserver-2516-database-engine-error.md)  
  
  
