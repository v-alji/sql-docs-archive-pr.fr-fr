---
title: MSSQLSERVER_8974 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8974 (Database Engine error)
ms.assetid: 52098678-0858-4a14-ad07-37ebbafca5fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3107f5b62caf04e232532c2d2b93d5da19fb53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615153"
---
# <a name="mssqlserver_8974"></a><span data-ttu-id="7a6ae-102">MSSQLSERVER_8974</span><span class="sxs-lookup"><span data-stu-id="7a6ae-102">MSSQLSERVER_8974</span></span>
    
## <a name="details"></a><span data-ttu-id="7a6ae-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7a6ae-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a6ae-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7a6ae-104">Product Name</span></span>|<span data-ttu-id="7a6ae-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a6ae-105">SQL Server</span></span>|  
|<span data-ttu-id="7a6ae-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7a6ae-106">Event ID</span></span>|<span data-ttu-id="7a6ae-107">8974</span><span class="sxs-lookup"><span data-stu-id="7a6ae-107">8974</span></span>|  
|<span data-ttu-id="7a6ae-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7a6ae-108">Event Source</span></span>|<span data-ttu-id="7a6ae-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7a6ae-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7a6ae-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7a6ae-110">Component</span></span>|<span data-ttu-id="7a6ae-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7a6ae-111">SQLEngine</span></span>|  
|<span data-ttu-id="7a6ae-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7a6ae-112">Symbolic Name</span></span>|<span data-ttu-id="7a6ae-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span><span class="sxs-lookup"><span data-stu-id="7a6ae-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span></span>|  
|<span data-ttu-id="7a6ae-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7a6ae-114">Message Text</span></span>|<span data-ttu-id="7a6ae-115">Erreur de table, ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE).</span><span class="sxs-lookup"><span data-stu-id="7a6ae-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="7a6ae-116">Le nœud de données hors ligne page P_ID1, emplacement S_ID1, ID de texte TEXT_ID est référencé par la page P_ID2, emplacement S_ID2 et par la page P_ID3, emplacement P_ID3.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-116">The off-row data node at page P_ID1, slot S_ID1, text ID TEXT_ID is pointed to by page P_ID2, slot S_ID2 and by page P_ID3, slot P_ID3.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7a6ae-117">Explication</span><span class="sxs-lookup"><span data-stu-id="7a6ae-117">Explanation</span></span>  
 <span data-ttu-id="7a6ae-118">Un nœud de données hors ligne a deux enregistrements de données ou d'index qui le répertorient en tant que nœud enfant.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-118">An off-row data node has two data or index records that list it as a child node.</span></span> <span data-ttu-id="7a6ae-119">Un nœud ne peut avoir qu'un nœud parent.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-119">A node can have only one parent node.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a6ae-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7a6ae-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="7a6ae-121">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="7a6ae-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="7a6ae-122">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="7a6ae-123">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="7a6ae-124">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="7a6ae-125">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="7a6ae-126">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="7a6ae-127">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="7a6ae-128">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="7a6ae-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="7a6ae-129">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="7a6ae-130">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="7a6ae-130">Restore from Backup</span></span>  
 <span data-ttu-id="7a6ae-131">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="7a6ae-132">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="7a6ae-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="7a6ae-133">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="7a6ae-134">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="7a6ae-135">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7a6ae-136">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="7a6ae-137">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="7a6ae-138">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="7a6ae-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="7a6ae-139">Le nœud de données hors ligne de la page *P_ID1* sera supprimé, ainsi que les deux références des pages *P_ID2* et *P_ID3*.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-139">The off-row data node on page *P_ID1* will be deleted and both references on pages *P_ID2* and *P_ID3* will be deleted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7a6ae-140">Cette réparation peut entraîner une perte de données.</span><span class="sxs-lookup"><span data-stu-id="7a6ae-140">This repair might cause data loss.</span></span>  
  
  
