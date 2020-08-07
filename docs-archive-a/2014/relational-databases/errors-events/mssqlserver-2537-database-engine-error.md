---
title: MSSQLSERVER_2537 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2537 (Database Engine error)
ms.assetid: 0af6ff69-d75a-4c39-8da2-9bd0695277c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c227867bac5a0ea5789ba653414444d011e5910d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612871"
---
# <a name="mssqlserver_2537"></a><span data-ttu-id="42ce8-102">MSSQLSERVER_2537</span><span class="sxs-lookup"><span data-stu-id="42ce8-102">MSSQLSERVER_2537</span></span>
    
## <a name="details"></a><span data-ttu-id="42ce8-103">Détails</span><span class="sxs-lookup"><span data-stu-id="42ce8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42ce8-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="42ce8-104">Product Name</span></span>|<span data-ttu-id="42ce8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="42ce8-105">SQL Server</span></span>|  
|<span data-ttu-id="42ce8-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="42ce8-106">Event ID</span></span>|<span data-ttu-id="42ce8-107">2537</span><span class="sxs-lookup"><span data-stu-id="42ce8-107">2537</span></span>|  
|<span data-ttu-id="42ce8-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="42ce8-108">Event Source</span></span>|<span data-ttu-id="42ce8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="42ce8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="42ce8-110">Composant</span><span class="sxs-lookup"><span data-stu-id="42ce8-110">Component</span></span>|<span data-ttu-id="42ce8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="42ce8-111">SQLEngine</span></span>|  
|<span data-ttu-id="42ce8-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="42ce8-112">Symbolic Name</span></span>|<span data-ttu-id="42ce8-113">DBCC_RECORD_CHECK_FAILED</span><span class="sxs-lookup"><span data-stu-id="42ce8-113">DBCC_RECORD_CHECK_FAILED</span></span>|  
|<span data-ttu-id="42ce8-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="42ce8-114">Message Text</span></span>|<span data-ttu-id="42ce8-115">Erreur de table, ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE), page P_ID, ligne ROW_ID.</span><span class="sxs-lookup"><span data-stu-id="42ce8-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page P_ID, row ROW_ID.</span></span> <span data-ttu-id="42ce8-116">Échec du contrôle de l'enregistrement (CHECK_TEXT).</span><span class="sxs-lookup"><span data-stu-id="42ce8-116">Record check (CHECK_TEXT) failed.</span></span> <span data-ttu-id="42ce8-117">Les valeurs sont VALUE1 et VALUE2.</span><span class="sxs-lookup"><span data-stu-id="42ce8-117">Values are VALUE1 and VALUE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="42ce8-118">Explication</span><span class="sxs-lookup"><span data-stu-id="42ce8-118">Explanation</span></span>  
 <span data-ttu-id="42ce8-119">La ligne ROW_ID (ou une colonne de la ligne) ne remplit pas les conditions décrites dans CHECK_TEXT ou n'a pas réussi ce test.</span><span class="sxs-lookup"><span data-stu-id="42ce8-119">The row ROW_ID (or a column in the row) failed the test or condition described by CHECK_TEXT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42ce8-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="42ce8-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="42ce8-121">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="42ce8-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="42ce8-122">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="42ce8-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="42ce8-123">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="42ce8-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="42ce8-124">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="42ce8-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="42ce8-125">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="42ce8-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="42ce8-126">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="42ce8-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="42ce8-127">Si vous soupçonnez qu'il s'agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="42ce8-127">If you suspect that write-caching is the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="42ce8-128">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="42ce8-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="42ce8-129">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="42ce8-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="42ce8-130">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="42ce8-130">Restore from Backup</span></span>  
 <span data-ttu-id="42ce8-131">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="42ce8-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="42ce8-132">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="42ce8-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="42ce8-133">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="42ce8-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="42ce8-134">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="42ce8-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="42ce8-135">Puis, exécutez DBCC CHECKDB avec la clause REPAIR recommandée.</span><span class="sxs-lookup"><span data-stu-id="42ce8-135">Then, run DBCC CHECKDB with the recommended REPAIR clause.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="42ce8-136">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="42ce8-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="42ce8-137">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="42ce8-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="42ce8-138">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="42ce8-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="42ce8-139">REPAIR reconstruira l'index, si index il y a.</span><span class="sxs-lookup"><span data-stu-id="42ce8-139">REPAIR will rebuild the index if an index exists.</span></span>  
  
 <span data-ttu-id="42ce8-140">**Attention** Cette réparation peut entraîner une perte de données.</span><span class="sxs-lookup"><span data-stu-id="42ce8-140">**Caution** This repair may cause data loss.</span></span>  
  
  
