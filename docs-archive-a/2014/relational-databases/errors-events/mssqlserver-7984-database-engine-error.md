---
title: MSSQLSERVER_7984 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7984 (Database Engine error)
ms.assetid: e3192f56-e4e2-41da-b132-65f1e7540b1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7f92fe4f3751621e0cc636ffcd2d4de73b348d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612379"
---
# <a name="mssqlserver_7984"></a><span data-ttu-id="43b0a-102">MSSQLSERVER_7984</span><span class="sxs-lookup"><span data-stu-id="43b0a-102">MSSQLSERVER_7984</span></span>
    
## <a name="details"></a><span data-ttu-id="43b0a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="43b0a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43b0a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="43b0a-104">Product Name</span></span>|<span data-ttu-id="43b0a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="43b0a-105">SQL Server</span></span>|  
|<span data-ttu-id="43b0a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="43b0a-106">Event ID</span></span>|<span data-ttu-id="43b0a-107">7984</span><span class="sxs-lookup"><span data-stu-id="43b0a-107">7984</span></span>|  
|<span data-ttu-id="43b0a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="43b0a-108">Event Source</span></span>|<span data-ttu-id="43b0a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="43b0a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="43b0a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="43b0a-110">Component</span></span>|<span data-ttu-id="43b0a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="43b0a-111">SQLEngine</span></span>|  
|<span data-ttu-id="43b0a-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="43b0a-112">Symbolic Name</span></span>|<span data-ttu-id="43b0a-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span><span class="sxs-lookup"><span data-stu-id="43b0a-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span></span>|  
|<span data-ttu-id="43b0a-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="43b0a-114">Message Text</span></span>|<span data-ttu-id="43b0a-115">Pré-vérifications de table système : ID d’objet O_ID.</span><span class="sxs-lookup"><span data-stu-id="43b0a-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="43b0a-116">La page P_ID possède un type de page PAGETYPE.</span><span class="sxs-lookup"><span data-stu-id="43b0a-116">Page P_ID has unexpected page type PAGETYPE.</span></span> <span data-ttu-id="43b0a-117">Vérifiez l'instruction qui s'est arrêtée en raison d'une erreur irréparable.</span><span class="sxs-lookup"><span data-stu-id="43b0a-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="43b0a-118">Explication</span><span class="sxs-lookup"><span data-stu-id="43b0a-118">Explanation</span></span>  
 <span data-ttu-id="43b0a-119">Une page avec un type autre que DATA_PAGE a été trouvée dans le niveau de données de l'objet spécifié.</span><span class="sxs-lookup"><span data-stu-id="43b0a-119">A page with a type other than DATA_PAGE was found in the data level of the specified object.</span></span> <span data-ttu-id="43b0a-120">Cette erreur est générée au cours de la première phase des vérifications de la commande DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="43b0a-120">This error is raised during the first phase of the DBCC CHECKDB command checks.</span></span> <span data-ttu-id="43b0a-121">Au cours de cette phase, DBCC CHECKDB effectue des vérifications primitives sur les pages de données des tables de base système critiques.</span><span class="sxs-lookup"><span data-stu-id="43b0a-121">During this phase, DBCC CHECKDB performs primitive checks on the data pages of critical system base tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43b0a-122">Si des erreurs sont détectées dans les tables système, les erreurs ne peuvent pas être réparées ; par conséquent, la commande DBCC CHECKDB se termine immédiatement.</span><span class="sxs-lookup"><span data-stu-id="43b0a-122">If any errors are found in the system tables, the errors cannot be repaired; therefore, the DBCC CHECKDB command ends immediately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43b0a-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="43b0a-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="43b0a-124">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="43b0a-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="43b0a-125">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="43b0a-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="43b0a-126">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="43b0a-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="43b0a-127">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="43b0a-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="43b0a-128">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="43b0a-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="43b0a-129">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="43b0a-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="43b0a-130">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="43b0a-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="43b0a-131">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="43b0a-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="43b0a-132">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="43b0a-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="43b0a-133">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="43b0a-133">Restore from Backup</span></span>  
 <span data-ttu-id="43b0a-134">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43b0a-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="43b0a-135">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="43b0a-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="43b0a-136">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="43b0a-136">Not applicable.</span></span> <span data-ttu-id="43b0a-137">Cette erreur ne peut pas être réparée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="43b0a-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="43b0a-138">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service de support technique de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43b0a-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
