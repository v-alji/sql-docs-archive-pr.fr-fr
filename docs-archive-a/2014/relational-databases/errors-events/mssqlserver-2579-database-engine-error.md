---
title: MSSQLSERVER_2579 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2579 (Database Engine error)
ms.assetid: 8f929d69-8eb4-4fe9-be52-b9680a7820db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e68cd090ff9d20b14b3456dcda66496fc2bc02d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612859"
---
# <a name="mssqlserver_2579"></a><span data-ttu-id="06935-102">MSSQLSERVER_2579</span><span class="sxs-lookup"><span data-stu-id="06935-102">MSSQLSERVER_2579</span></span>
    
## <a name="details"></a><span data-ttu-id="06935-103">Détails</span><span class="sxs-lookup"><span data-stu-id="06935-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06935-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="06935-104">Product Name</span></span>|<span data-ttu-id="06935-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="06935-105">SQL Server</span></span>|  
|<span data-ttu-id="06935-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="06935-106">Event ID</span></span>|<span data-ttu-id="06935-107">2579</span><span class="sxs-lookup"><span data-stu-id="06935-107">2579</span></span>|  
|<span data-ttu-id="06935-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="06935-108">Event Source</span></span>|<span data-ttu-id="06935-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="06935-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="06935-110">Composant</span><span class="sxs-lookup"><span data-stu-id="06935-110">Component</span></span>|<span data-ttu-id="06935-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="06935-111">SQLEngine</span></span>|  
|<span data-ttu-id="06935-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="06935-112">Symbolic Name</span></span>|<span data-ttu-id="06935-113">DBCC_EXTENT_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="06935-113">DBCC_EXTENT_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="06935-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="06935-114">Message Text</span></span>|<span data-ttu-id="06935-115">Erreur de table, l’extension P_ID, ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE) est en dehors des limites de cette base de données.</span><span class="sxs-lookup"><span data-stu-id="06935-115">Table error: Extent P_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) is beyond the range of this database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="06935-116">Explication</span><span class="sxs-lookup"><span data-stu-id="06935-116">Explanation</span></span>  
 <span data-ttu-id="06935-117">*P_ID* est un ID de page de la forme *(filenum:pageinfile)* .</span><span class="sxs-lookup"><span data-stu-id="06935-117">*P_ID* is a PageID of the form *(filenum:pageinfile)*.</span></span> <span data-ttu-id="06935-118">La valeur de *pageinfile* de cette extension est supérieure à la taille physique du fichier (*filenum*) de la base de données.</span><span class="sxs-lookup"><span data-stu-id="06935-118">The *pageinfile* of this extent is greater than the physical size of the file (*filenum)* of the database.</span></span> <span data-ttu-id="06935-119">L'extension est marquée comme étant allouée dans une page IAM pour l'ID d'unité d'allocation indiquée.</span><span class="sxs-lookup"><span data-stu-id="06935-119">The extent is marked as being allocated in an IAM page for the indicated allocation unit ID.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06935-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="06935-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="06935-121">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="06935-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="06935-122">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="06935-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="06935-123">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="06935-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="06935-124">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="06935-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="06935-125">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="06935-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="06935-126">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="06935-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="06935-127">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="06935-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="06935-128">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="06935-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="06935-129">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="06935-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="06935-130">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="06935-130">Restore from Backup</span></span>  
 <span data-ttu-id="06935-131">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="06935-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="06935-132">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="06935-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="06935-133">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="06935-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="06935-134">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="06935-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="06935-135">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="06935-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="06935-136">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="06935-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="06935-137">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="06935-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="06935-138">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="06935-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="06935-139">L'exécution de REPAIR entraînera la désallocation de l'extension de la page IAM.</span><span class="sxs-lookup"><span data-stu-id="06935-139">Running REPAIR will cause the extent to be deallocated from the IAM page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="06935-140">Cette réparation peut entraîner une perte de données.</span><span class="sxs-lookup"><span data-stu-id="06935-140">This repair may cause data loss.</span></span>  
  
  
