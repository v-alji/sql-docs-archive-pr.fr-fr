---
title: MSSQLSERVER_8993 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8993 (Database Engine error)
ms.assetid: 06aac110-a41c-4853-bc8e-a83e8535b8be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5ee9497e9c4484fd885803c0feff20362a159ff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600966"
---
# <a name="mssqlserver_8993"></a><span data-ttu-id="24b7a-102">MSSQLSERVER_8993</span><span class="sxs-lookup"><span data-stu-id="24b7a-102">MSSQLSERVER_8993</span></span>
    
## <a name="details"></a><span data-ttu-id="24b7a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="24b7a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24b7a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="24b7a-104">Product Name</span></span>|<span data-ttu-id="24b7a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="24b7a-105">SQL Server</span></span>|  
|<span data-ttu-id="24b7a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="24b7a-106">Event ID</span></span>|<span data-ttu-id="24b7a-107">8993</span><span class="sxs-lookup"><span data-stu-id="24b7a-107">8993</span></span>|  
|<span data-ttu-id="24b7a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="24b7a-108">Event Source</span></span>|<span data-ttu-id="24b7a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="24b7a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="24b7a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="24b7a-110">Component</span></span>|<span data-ttu-id="24b7a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="24b7a-111">SQLEngine</span></span>|  
|<span data-ttu-id="24b7a-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="24b7a-112">Symbolic Name</span></span>|<span data-ttu-id="24b7a-113">DBCC3_MISSING_FORWARDED_ROW</span><span class="sxs-lookup"><span data-stu-id="24b7a-113">DBCC3_MISSING_FORWARDED_ROW</span></span>|  
|<span data-ttu-id="24b7a-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="24b7a-114">Message Text</span></span>|<span data-ttu-id="24b7a-115">ID d'objet O_ID, page de ligne transmise P_ID1, l'emplacement S_ID1 pointe vers la page P_ID2, emplacement S_ID2.</span><span class="sxs-lookup"><span data-stu-id="24b7a-115">Object ID O_ID, forwarding row page P_ID1, slot S_ID1 points to page P_ID2, slot S_ID2.</span></span> <span data-ttu-id="24b7a-116">Aucune ligne transmise n’a été trouvée.</span><span class="sxs-lookup"><span data-stu-id="24b7a-116">Did not encounter forwarded row.</span></span> <span data-ttu-id="24b7a-117">Une erreur d'allocation s'est peut-être produite.</span><span class="sxs-lookup"><span data-stu-id="24b7a-117">Possible allocation error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="24b7a-118">Explication</span><span class="sxs-lookup"><span data-stu-id="24b7a-118">Explanation</span></span>  
 <span data-ttu-id="24b7a-119">Une ligne de transfert d'un segment de mémoire pointe vers une ligne transmise inexistante.</span><span class="sxs-lookup"><span data-stu-id="24b7a-119">A forwarding row in a heap points to a nonexistent forwarded row.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="24b7a-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="24b7a-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="24b7a-121">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="24b7a-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="24b7a-122">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="24b7a-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="24b7a-123">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="24b7a-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="24b7a-124">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="24b7a-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="24b7a-125">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="24b7a-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="24b7a-126">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="24b7a-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="24b7a-127">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="24b7a-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="24b7a-128">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="24b7a-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="24b7a-129">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="24b7a-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="24b7a-130">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="24b7a-130">Restore from Backup</span></span>  
 <span data-ttu-id="24b7a-131">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="24b7a-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="24b7a-132">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="24b7a-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="24b7a-133">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="24b7a-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="24b7a-134">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="24b7a-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="24b7a-135">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="24b7a-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="24b7a-136">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="24b7a-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="24b7a-137">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="24b7a-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="24b7a-138">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="24b7a-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="24b7a-139">La ligne de transfert sera supprimée et tous les index non cluster seront reconstruits.</span><span class="sxs-lookup"><span data-stu-id="24b7a-139">The forwarding row will be deleted and any nonclustered indexes will be rebuilt.</span></span>  
  
  
