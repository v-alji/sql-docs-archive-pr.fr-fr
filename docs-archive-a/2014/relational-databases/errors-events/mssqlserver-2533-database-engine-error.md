---
title: MSSQLSERVER_2533 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2533 (Database Engine error)
ms.assetid: 0418352c-0ab2-4dc7-b8b9-5c3bad94560c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1eb3e2780693a3a0ffed21ce7b9d7887615536c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699635"
---
# <a name="mssqlserver_2533"></a><span data-ttu-id="7a469-102">MSSQLSERVER_2533</span><span class="sxs-lookup"><span data-stu-id="7a469-102">MSSQLSERVER_2533</span></span>
    
## <a name="details"></a><span data-ttu-id="7a469-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7a469-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a469-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7a469-104">Product Name</span></span>|<span data-ttu-id="7a469-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a469-105">SQL Server</span></span>|  
|<span data-ttu-id="7a469-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7a469-106">Event ID</span></span>|<span data-ttu-id="7a469-107">2533</span><span class="sxs-lookup"><span data-stu-id="7a469-107">2533</span></span>|  
|<span data-ttu-id="7a469-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7a469-108">Event Source</span></span>|<span data-ttu-id="7a469-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7a469-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7a469-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7a469-110">Component</span></span>|<span data-ttu-id="7a469-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7a469-111">SQLEngine</span></span>|  
|<span data-ttu-id="7a469-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7a469-112">Symbolic Name</span></span>|<span data-ttu-id="7a469-113">DBCC_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="7a469-113">DBCC_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="7a469-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7a469-114">Message Text</span></span>|<span data-ttu-id="7a469-115">Erreur de table, la page P_ID assignée à l’ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE) n'a pas été affichée.</span><span class="sxs-lookup"><span data-stu-id="7a469-115">Table error: Page P_ID allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) was not seen.</span></span> <span data-ttu-id="7a469-116">La page n'est peut-être pas valide ou comporte un ID d'unité d'allocation incorrect dans son en-tête.</span><span class="sxs-lookup"><span data-stu-id="7a469-116">Page may be invalid or have incorrect alloc unit ID in its header.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7a469-117">Explication</span><span class="sxs-lookup"><span data-stu-id="7a469-117">Explanation</span></span>  
 <span data-ttu-id="7a469-118">Une page est allouée à l’ID d’unité d’allocation *A_ID*, mais cet ID d’unité d’allocation ne figure pas dans l’en-tête de la page.</span><span class="sxs-lookup"><span data-stu-id="7a469-118">A page is allocated to the allocation unit ID, *A_ID*, but this allocation unit ID is not in the header of the page.</span></span> <span data-ttu-id="7a469-119">L'en-tête a un ID d'unité d'allocation différent.</span><span class="sxs-lookup"><span data-stu-id="7a469-119">The header has a different allocation unit ID.</span></span> <span data-ttu-id="7a469-120">Si l'ID d'unité d'allocation de l'en-tête de la page n'est pas un objet valide, la page peut avoir une erreur de correspondance MSSQLEngine_2534.</span><span class="sxs-lookup"><span data-stu-id="7a469-120">If the allocation unit ID in the header of the page is for a valid object, the page may have a matching MSSQLEngine_2534 error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a469-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7a469-121">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="7a469-122">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="7a469-122">Look for Hardware Failure</span></span>  
 <span data-ttu-id="7a469-123">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="7a469-123">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="7a469-124">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="7a469-124">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="7a469-125">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="7a469-125">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="7a469-126">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="7a469-126">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="7a469-127">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="7a469-127">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="7a469-128">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="7a469-128">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="7a469-129">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="7a469-129">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="7a469-130">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="7a469-130">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="7a469-131">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="7a469-131">Restore from Backup</span></span>  
 <span data-ttu-id="7a469-132">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7a469-132">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="7a469-133">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="7a469-133">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="7a469-134">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="7a469-134">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="7a469-135">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="7a469-135">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="7a469-136">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="7a469-136">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7a469-137">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="7a469-137">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="7a469-138">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="7a469-138">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="7a469-139">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="7a469-139">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="7a469-140">REPAIR désalloue la page.</span><span class="sxs-lookup"><span data-stu-id="7a469-140">REPAIR will deallocate the page.</span></span> <span data-ttu-id="7a469-141">Si la page venait d'une unité d'allocation de données de ligne, l'index, s'il existe, sera reconstruit.</span><span class="sxs-lookup"><span data-stu-id="7a469-141">If the page was from an in-row data allocation unit, the index, if one exists, will be rebuilt.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7a469-142">Cette réparation peut entraîner une perte de données.</span><span class="sxs-lookup"><span data-stu-id="7a469-142">This repair may cause data loss.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a469-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a469-143">See Also</span></span>  
 [<span data-ttu-id="7a469-144">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="7a469-144">MSSQLSERVER_2534</span></span>](mssqlserver-2534-database-engine-error.md)  
  
  
