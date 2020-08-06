---
title: MSSQLSERVER_2512 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2512 (Database Engine error)
ms.assetid: 989b527f-5b02-403c-9b7f-51580f4e7688
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da121c8b49ab8290c494d33f0f2a0ba6fded9e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698256"
---
# <a name="mssqlserver_2512"></a><span data-ttu-id="aa3d8-102">MSSQLSERVER_2512</span><span class="sxs-lookup"><span data-stu-id="aa3d8-102">MSSQLSERVER_2512</span></span>
    
## <a name="details"></a><span data-ttu-id="aa3d8-103">Détails</span><span class="sxs-lookup"><span data-stu-id="aa3d8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa3d8-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="aa3d8-104">Product Name</span></span>|<span data-ttu-id="aa3d8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa3d8-105">SQL Server</span></span>|  
|<span data-ttu-id="aa3d8-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="aa3d8-106">Event ID</span></span>|<span data-ttu-id="aa3d8-107">2512</span><span class="sxs-lookup"><span data-stu-id="aa3d8-107">2512</span></span>|  
|<span data-ttu-id="aa3d8-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="aa3d8-108">Event Source</span></span>|<span data-ttu-id="aa3d8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aa3d8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aa3d8-110">Composant</span><span class="sxs-lookup"><span data-stu-id="aa3d8-110">Component</span></span>|<span data-ttu-id="aa3d8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aa3d8-111">SQLEngine</span></span>|  
|<span data-ttu-id="aa3d8-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="aa3d8-112">Symbolic Name</span></span>|<span data-ttu-id="aa3d8-113">DBCC_DUPLICATE_KEYS</span><span class="sxs-lookup"><span data-stu-id="aa3d8-113">DBCC_DUPLICATE_KEYS</span></span>|  
|<span data-ttu-id="aa3d8-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="aa3d8-114">Message Text</span></span>|<span data-ttu-id="aa3d8-115">Erreur de table, ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE).</span><span class="sxs-lookup"><span data-stu-id="aa3d8-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="aa3d8-116">Clés en double sur la page P_ID1, emplacement SLOT1, et sur la page P_ID2, emplacement SLOT2.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-116">Duplicate keys on page P_ID1 slot SLOT1 and page P_ID2 slot SLOT2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa3d8-117">Explication</span><span class="sxs-lookup"><span data-stu-id="aa3d8-117">Explanation</span></span>  
 <span data-ttu-id="aa3d8-118">Les deux emplacements spécifiés ont des clés identiques, y compris tout `uniqueifiers`.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-118">The two specified slots have identical keys, including any `uniqueifiers`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa3d8-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="aa3d8-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="aa3d8-120">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="aa3d8-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="aa3d8-121">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="aa3d8-122">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="aa3d8-123">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="aa3d8-124">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="aa3d8-125">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="aa3d8-126">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="aa3d8-127">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="aa3d8-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="aa3d8-128">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="aa3d8-129">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="aa3d8-129">Restore from Backup</span></span>  
 <span data-ttu-id="aa3d8-130">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="aa3d8-131">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="aa3d8-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="aa3d8-132">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="aa3d8-133">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="aa3d8-134">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="aa3d8-135">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="aa3d8-136">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="aa3d8-137">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="aa3d8-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="aa3d8-138">Si chaque enregistrement est de type Ghost ou si l'index n'est pas unique, DBCC peut réparer ce problème en reconstruisant l'index.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-138">If either record is a ghost or the index is nonunique, DBCC can repair this problem by rebuilding the index.</span></span> <span data-ttu-id="aa3d8-139">Dans le cas contraire, si cela est nécessaire, REPAIR supprime l’emplacement *SLOT2* dans la page *P_ID2* ou marque l’emplacement en tant que fantôme.</span><span class="sxs-lookup"><span data-stu-id="aa3d8-139">Otherwise, if necessary, REPAIR will delete slot *SLOT2* on page *P_ID2* or mark the slot as a ghost.</span></span>  
  
  
