---
title: MSSQLSERVER_7987 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7987 (Database Engine error)
ms.assetid: 314aebf1-6cdf-488d-a274-ce967fadb57b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2fec3cf707e2e9923084f48096a88c60655513e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701219"
---
# <a name="mssqlserver_7987"></a><span data-ttu-id="50085-102">MSSQLSERVER_7987</span><span class="sxs-lookup"><span data-stu-id="50085-102">MSSQLSERVER_7987</span></span>
    
## <a name="details"></a><span data-ttu-id="50085-103">Détails</span><span class="sxs-lookup"><span data-stu-id="50085-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50085-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="50085-104">Product Name</span></span>|<span data-ttu-id="50085-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="50085-105">SQL Server</span></span>|  
|<span data-ttu-id="50085-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="50085-106">Event ID</span></span>|<span data-ttu-id="50085-107">7987</span><span class="sxs-lookup"><span data-stu-id="50085-107">7987</span></span>|  
|<span data-ttu-id="50085-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="50085-108">Event Source</span></span>|<span data-ttu-id="50085-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="50085-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="50085-110">Composant</span><span class="sxs-lookup"><span data-stu-id="50085-110">Component</span></span>|<span data-ttu-id="50085-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="50085-111">SQLEngine</span></span>|  
|<span data-ttu-id="50085-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="50085-112">Symbolic Name</span></span>|<span data-ttu-id="50085-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="50085-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span></span>|  
|<span data-ttu-id="50085-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="50085-114">Message Text</span></span>|<span data-ttu-id="50085-115">Pré-vérifications de table système : non-correspondance de liaisons de chaînes dans l’ID d’objet O_ID.</span><span class="sxs-lookup"><span data-stu-id="50085-115">System table pre-checks: Object ID O_ID has chain linkage mismatch.</span></span> <span data-ttu-id="50085-116">P_ID1->suiv. = P_ID2, mais P_ID2->préc. = P_ID3.</span><span class="sxs-lookup"><span data-stu-id="50085-116">P_ID1->next = P_ID2, but P_ID2->prev = P_ID3.</span></span> <span data-ttu-id="50085-117">Vérifiez l'instruction qui s'est arrêtée en raison d'une erreur irréparable.</span><span class="sxs-lookup"><span data-stu-id="50085-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="50085-118">Explication</span><span class="sxs-lookup"><span data-stu-id="50085-118">Explanation</span></span>  
 <span data-ttu-id="50085-119">La première étape d'un DBCC CHECKDB consiste à effectuer des prévérifications sur les pages de données des tables système critiques.</span><span class="sxs-lookup"><span data-stu-id="50085-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="50085-120">Toute erreur détectée à ce stade étant irréparable, DBCC CHECKDB s'arrête immédiatement.</span><span class="sxs-lookup"><span data-stu-id="50085-120">If any errors are found, they cannot be repaired; therefore, the DBCC CHECKDB terminates immediately.</span></span>  
  
 <span data-ttu-id="50085-121">Le pointeur de page suivante de la page *P_ID1* pointe vers la page *P_ID2* ; toutefois, le pointeur de page précédente de la page *P_ID2* pointe vers la page *P_ID3*, mais ne pointe pas en retour, vers la page *P_ID1*, comme il le devrait.</span><span class="sxs-lookup"><span data-stu-id="50085-121">The next page pointer of page *P_ID1* points to page *P_ID2*; however, the previous page pointer of page *P_ID2* points to page *P_ID3* but not back to page *P_ID1*, as it should.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="50085-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="50085-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="50085-123">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="50085-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="50085-124">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="50085-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="50085-125">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="50085-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="50085-126">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="50085-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="50085-127">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="50085-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="50085-128">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="50085-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="50085-129">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="50085-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="50085-130">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="50085-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="50085-131">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="50085-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="50085-132">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="50085-132">Restore from Backup</span></span>  
 <span data-ttu-id="50085-133">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="50085-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="50085-134">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="50085-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="50085-135">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="50085-135">Not applicable.</span></span> <span data-ttu-id="50085-136">Cette erreur ne peut pas être réparée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="50085-136">This error cannot be repaired automatically.</span></span> <span data-ttu-id="50085-137">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service de support technique de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50085-137">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
