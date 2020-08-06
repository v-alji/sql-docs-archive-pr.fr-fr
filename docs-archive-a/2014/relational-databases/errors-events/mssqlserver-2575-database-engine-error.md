---
title: MSSQLSERVER_2575 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2575 (Database Engine error)
ms.assetid: 92dfe449-a122-4730-942b-e1d319862d20
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 461d2b57b5ace98ca624f8dc3717c98f3e9e4d67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600974"
---
# <a name="mssqlserver_2575"></a><span data-ttu-id="c11b1-102">MSSQLSERVER_2575</span><span class="sxs-lookup"><span data-stu-id="c11b1-102">MSSQLSERVER_2575</span></span>
    
## <a name="details"></a><span data-ttu-id="c11b1-103">Détails</span><span class="sxs-lookup"><span data-stu-id="c11b1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c11b1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="c11b1-104">Product Name</span></span>|<span data-ttu-id="c11b1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c11b1-105">SQL Server</span></span>|  
|<span data-ttu-id="c11b1-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="c11b1-106">Event ID</span></span>|<span data-ttu-id="c11b1-107">2575</span><span class="sxs-lookup"><span data-stu-id="c11b1-107">2575</span></span>|  
|<span data-ttu-id="c11b1-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="c11b1-108">Event Source</span></span>|<span data-ttu-id="c11b1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c11b1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c11b1-110">Composant</span><span class="sxs-lookup"><span data-stu-id="c11b1-110">Component</span></span>|<span data-ttu-id="c11b1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c11b1-111">SQLEngine</span></span>|  
|<span data-ttu-id="c11b1-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="c11b1-112">Symbolic Name</span></span>|<span data-ttu-id="c11b1-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="c11b1-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="c11b1-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="c11b1-114">Message Text</span></span>|<span data-ttu-id="c11b1-115">La page IAM (Index Allocation Map) P_ID1 est désignée par le prochain pointeur de la page IAM P_ID2 dans l'ID d'objet O_ID, ID d'index I_ID, ID de partition PN_ID, ID d'unité d'allocation A_ID (type TYPE), mais elle n'a pas été détectée lors de l'analyse.</span><span class="sxs-lookup"><span data-stu-id="c11b1-115">IAM page P_ID1 is pointed to by the next pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c11b1-116">Explication</span><span class="sxs-lookup"><span data-stu-id="c11b1-116">Explanation</span></span>  
 <span data-ttu-id="c11b1-117">Une page IAM (Index Allocation Map) a été trouvée pour l'index spécifié ; toutefois, la page IAM pour son pointeur de page suivante reste introuvable.</span><span class="sxs-lookup"><span data-stu-id="c11b1-117">An Index Allocation Map (IAM) page was found for the specified index; however, the IAM page for its next-page pointer was not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c11b1-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c11b1-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="c11b1-119">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="c11b1-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="c11b1-120">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="c11b1-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="c11b1-121">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="c11b1-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="c11b1-122">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="c11b1-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="c11b1-123">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="c11b1-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="c11b1-124">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="c11b1-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="c11b1-125">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="c11b1-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="c11b1-126">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="c11b1-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="c11b1-127">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="c11b1-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="c11b1-128">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c11b1-128">Restore from Backup</span></span>  
 <span data-ttu-id="c11b1-129">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c11b1-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="c11b1-130">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="c11b1-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="c11b1-131">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="c11b1-131">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="c11b1-132">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="c11b1-132">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="c11b1-133">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="c11b1-133">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="c11b1-134">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="c11b1-134">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="c11b1-135">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="c11b1-135">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="c11b1-136">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="c11b1-136">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="c11b1-137">DBCC reconstruira l'index.</span><span class="sxs-lookup"><span data-stu-id="c11b1-137">DBCC will rebuild the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c11b1-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c11b1-138">See Also</span></span>  
 [<span data-ttu-id="c11b1-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c11b1-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
