---
title: MSSQLSERVER_2577 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2577 (Database Engine error)
ms.assetid: f53256a2-2fb0-47fd-9ed9-c45389104145
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9e4b7b85f59ba721eae6b4a0ac8db1b2d288422d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612863"
---
# <a name="mssqlserver_2577"></a><span data-ttu-id="18393-102">MSSQLSERVER_2577</span><span class="sxs-lookup"><span data-stu-id="18393-102">MSSQLSERVER_2577</span></span>
    
## <a name="details"></a><span data-ttu-id="18393-103">Détails</span><span class="sxs-lookup"><span data-stu-id="18393-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="18393-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="18393-104">Product Name</span></span>|<span data-ttu-id="18393-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="18393-105">SQL Server</span></span>|  
|<span data-ttu-id="18393-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="18393-106">Event ID</span></span>|<span data-ttu-id="18393-107">2577</span><span class="sxs-lookup"><span data-stu-id="18393-107">2577</span></span>|  
|<span data-ttu-id="18393-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="18393-108">Event Source</span></span>|<span data-ttu-id="18393-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="18393-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="18393-110">Composant</span><span class="sxs-lookup"><span data-stu-id="18393-110">Component</span></span>|<span data-ttu-id="18393-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="18393-111">SQLEngine</span></span>|  
|<span data-ttu-id="18393-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="18393-112">Symbolic Name</span></span>|<span data-ttu-id="18393-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="18393-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="18393-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="18393-114">Message Text</span></span>|<span data-ttu-id="18393-115">Les numéros de séquence de chaînes sont désordonnés dans la chaîne IAM de l'ID d'objet O_ID, ID d'index I_ID, ID de partition PN_ID, ID d'unité d'allocation A_ID (type TYPE).</span><span class="sxs-lookup"><span data-stu-id="18393-115">Chain sequence numbers out of order in the Index Allocation Map (IAM) chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="18393-116">La page P_ID1 avec le numéro de séquence SEQUENCE1 pointe vers la page P_ID2 avec le numéro de séquence SEQUENCE2.</span><span class="sxs-lookup"><span data-stu-id="18393-116">Page P_ID1 with sequence number SEQUENCE1 points to page P_ID2 with sequence number SEQUENCE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="18393-117">Explication</span><span class="sxs-lookup"><span data-stu-id="18393-117">Explanation</span></span>  
 <span data-ttu-id="18393-118">Chaque page IAM (Index Allocation Map) possède un numéro de séquence.</span><span class="sxs-lookup"><span data-stu-id="18393-118">Every Index Allocation Map (IAM) page has a sequence number.</span></span> <span data-ttu-id="18393-119">Ce numéro de séquence correspond à la position de la page IAM dans la chaîne IAM.</span><span class="sxs-lookup"><span data-stu-id="18393-119">The sequence number is the position of the IAM page within the IAM chain.</span></span> <span data-ttu-id="18393-120">La règle est que les numéros de séquence augmentent d'une unité pour chaque page IAM.</span><span class="sxs-lookup"><span data-stu-id="18393-120">The rule is that sequence numbers increase by one for each IAM page.</span></span> <span data-ttu-id="18393-121">La page IAM *P_ID2* possède un numéro de séquence qui ne respecte pas cette règle.</span><span class="sxs-lookup"><span data-stu-id="18393-121">IAM page, *P_ID2*, has a sequence number that does not follow this rule.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="18393-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="18393-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="18393-123">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="18393-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="18393-124">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="18393-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="18393-125">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="18393-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="18393-126">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="18393-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="18393-127">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="18393-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="18393-128">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="18393-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="18393-129">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="18393-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="18393-130">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="18393-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="18393-131">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="18393-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="18393-132">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="18393-132">Restore from Backup</span></span>  
 <span data-ttu-id="18393-133">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="18393-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="18393-134">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="18393-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="18393-135">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="18393-135">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="18393-136">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="18393-136">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="18393-137">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="18393-137">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="18393-138">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="18393-138">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="18393-139">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="18393-139">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="18393-140">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="18393-140">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="18393-141">L'exécution de REPAIR reconstruira la chaîne IAM.</span><span class="sxs-lookup"><span data-stu-id="18393-141">Running REPAIR will rebuild the IAM chain.</span></span> <span data-ttu-id="18393-142">REPAIR commence par séparer la chaîne IAM existante en deux moitiés.</span><span class="sxs-lookup"><span data-stu-id="18393-142">REPAIR first splits the existing IAM chain in two halves.</span></span> <span data-ttu-id="18393-143">La première moitié de la chaîne s’achèvera par la page IAM *P_ID1*.</span><span class="sxs-lookup"><span data-stu-id="18393-143">The first half of the chain will end with IAM page, *P_ID1*.</span></span> <span data-ttu-id="18393-144">Le pointeur de page suivante de la page *P_ID1* sera défini avec les valeurs (0:0).</span><span class="sxs-lookup"><span data-stu-id="18393-144">The next page pointer of the *P_ID1* page will be set to (0:0).</span></span> <span data-ttu-id="18393-145">La seconde moitié de la chaîne commencera par la page IAM *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="18393-145">The second half of the chain will start with IAM page, *P_ID2*.</span></span> <span data-ttu-id="18393-146">Le pointeur de page précédente de la page *P_ID2* sera défini avec les valeurs (0:0).</span><span class="sxs-lookup"><span data-stu-id="18393-146">The previous page pointer of the *P_ID2* page will be set to (0:0).</span></span>  
  
 <span data-ttu-id="18393-147">REPAIR assemblera alors les deux moitiés de la chaîne et régénérera les numéros de séquence de la chaîne IAM.</span><span class="sxs-lookup"><span data-stu-id="18393-147">REPAIR will then connect the two haves of the chain together and regenerate the sequence numbers for the IAM chain.</span></span> <span data-ttu-id="18393-148">Toutes les pages IAM qui ne peuvent pas être réparées seront désallouées.</span><span class="sxs-lookup"><span data-stu-id="18393-148">Any IAM pages that cannot be repaired will be deallocated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="18393-149">Cette réparation peut entraîner une perte de données.</span><span class="sxs-lookup"><span data-stu-id="18393-149">This repair may cause data loss.</span></span>  
  
  
