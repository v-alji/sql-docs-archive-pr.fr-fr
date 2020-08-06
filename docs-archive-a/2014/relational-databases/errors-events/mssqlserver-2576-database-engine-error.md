---
title: MSSQLSERVER_2576 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2576 (Database Engine error)
ms.assetid: b727cc2f-c76c-46f8-bbbe-5e7a05a6eabf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f378051c7844bf08d617db56666d69b22ecf732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603533"
---
# <a name="mssqlserver_2576"></a><span data-ttu-id="7ec03-102">MSSQLSERVER_2576</span><span class="sxs-lookup"><span data-stu-id="7ec03-102">MSSQLSERVER_2576</span></span>
    
## <a name="details"></a><span data-ttu-id="7ec03-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7ec03-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ec03-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7ec03-104">Product Name</span></span>|<span data-ttu-id="7ec03-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ec03-105">SQL Server</span></span>|  
|<span data-ttu-id="7ec03-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7ec03-106">Event ID</span></span>|<span data-ttu-id="7ec03-107">2576</span><span class="sxs-lookup"><span data-stu-id="7ec03-107">2576</span></span>|  
|<span data-ttu-id="7ec03-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7ec03-108">Event Source</span></span>|<span data-ttu-id="7ec03-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7ec03-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7ec03-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7ec03-110">Component</span></span>|<span data-ttu-id="7ec03-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7ec03-111">SQLEngine</span></span>|  
|<span data-ttu-id="7ec03-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7ec03-112">Symbolic Name</span></span>|<span data-ttu-id="7ec03-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="7ec03-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="7ec03-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7ec03-114">Message Text</span></span>|<span data-ttu-id="7ec03-115">La page IAM P_ID1 est désignée par le pointeur antérieur de la page IAM P_ID2 dans l'ID d'objet O_ID, ID d'index I_ID, ID de partition PN_ID, ID d'unité d'allocation A_ID (type TYPE), mais elle n'a pas été détectée lors de l'analyse.</span><span class="sxs-lookup"><span data-stu-id="7ec03-115">The Index Allocation Map (IAM) page P_ID1 is pointed to by the previous pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ec03-116">Explication</span><span class="sxs-lookup"><span data-stu-id="7ec03-116">Explanation</span></span>  
 <span data-ttu-id="7ec03-117">Une page IAM ou une entrée de métadonnées n'a pas été localisée, bien qu'une référence à la page existe comme lien à la page précédente d'une autre page IAM, dans une chaîne IAM.</span><span class="sxs-lookup"><span data-stu-id="7ec03-117">An Index Allocation Map (IAM) page or metadata entry was not located, even though a reference to the page exists as the previous page link on another IAM page in an IAM chain.</span></span> <span data-ttu-id="7ec03-118">Si la page *P_ID1* est (0:0), la page IAM, *P_ID2*, correspond au début d’une chaîne IAM et l’entrée de métadonnées pour la chaîne IAM est manquante.</span><span class="sxs-lookup"><span data-stu-id="7ec03-118">If the *P_ID1* page is (0:0), the IAM page, *P_ID2*, is the start of an IAM chain, and the metadata entry for the IAM chain is missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ec03-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7ec03-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="7ec03-120">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="7ec03-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="7ec03-121">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="7ec03-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="7ec03-122">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="7ec03-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="7ec03-123">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="7ec03-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="7ec03-124">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="7ec03-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="7ec03-125">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="7ec03-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="7ec03-126">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="7ec03-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="7ec03-127">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="7ec03-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="7ec03-128">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="7ec03-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="7ec03-129">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="7ec03-129">Restore from Backup</span></span>  
 <span data-ttu-id="7ec03-130">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7ec03-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="7ec03-131">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="7ec03-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="7ec03-132">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="7ec03-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="7ec03-133">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="7ec03-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="7ec03-134">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="7ec03-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7ec03-135">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="7ec03-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="7ec03-136">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="7ec03-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="7ec03-137">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="7ec03-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="7ec03-138">REPAIR essaiera de reconstruire la chaîne IAM impliquant la page *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="7ec03-138">REPAIR will try to rebuild the IAM chain involving the *P_ID2* page.</span></span> <span data-ttu-id="7ec03-139">La reconstruction de la chaîne peut impliquer la suppression de pages de la chaîne ou la suppression de la chaîne entière si les métadonnées sont endommagées.</span><span class="sxs-lookup"><span data-stu-id="7ec03-139">Rebuilding the chain may involve removing pages from the chain, or removing the whole chain if the metadata is corrupted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7ec03-140">Cette réparation peut entraîner une perte de données.</span><span class="sxs-lookup"><span data-stu-id="7ec03-140">This repair may cause data loss.</span></span>  
  
  
