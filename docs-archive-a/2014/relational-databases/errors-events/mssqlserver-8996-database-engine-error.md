---
title: MSSQLSERVER_8996 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8996 (Database Engine error)
ms.assetid: 4e655cdc-945a-4a18-95dd-75f050563d26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d0cb5f0294ea471a6e300adbabc0f7b55632994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612832"
---
# <a name="mssqlserver_8996"></a><span data-ttu-id="448e6-102">MSSQLSERVER_8996</span><span class="sxs-lookup"><span data-stu-id="448e6-102">MSSQLSERVER_8996</span></span>
    
## <a name="details"></a><span data-ttu-id="448e6-103">Détails</span><span class="sxs-lookup"><span data-stu-id="448e6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="448e6-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="448e6-104">Product Name</span></span>|<span data-ttu-id="448e6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="448e6-105">SQL Server</span></span>|  
|<span data-ttu-id="448e6-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="448e6-106">Event ID</span></span>|<span data-ttu-id="448e6-107">8996</span><span class="sxs-lookup"><span data-stu-id="448e6-107">8996</span></span>|  
|<span data-ttu-id="448e6-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="448e6-108">Event Source</span></span>|<span data-ttu-id="448e6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="448e6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="448e6-110">Composant</span><span class="sxs-lookup"><span data-stu-id="448e6-110">Component</span></span>|<span data-ttu-id="448e6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="448e6-111">SQLEngine</span></span>|  
|<span data-ttu-id="448e6-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="448e6-112">Symbolic Name</span></span>|<span data-ttu-id="448e6-113">DBCC3_IAM_PAGE_RANGE_IN_WRONG_FILEGROUP</span><span class="sxs-lookup"><span data-stu-id="448e6-113">DBCC3_IAM_PAGE_RANGE_IN_WRONG_FILEGROUP</span></span>|  
|<span data-ttu-id="448e6-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="448e6-114">Message Text</span></span>|<span data-ttu-id="448e6-115">La page IAM P_ID pour l'ID d'objet O_ID, ID d'index I_ID, ID de partition PN_ID, ID d'unité d'allocation A_ID (type TYPE) contrôle les pages du groupe de fichiers FG_ID1, lesquelles doivent être dans le groupe de fichiers FG_ID2.</span><span class="sxs-lookup"><span data-stu-id="448e6-115">IAM page P_ID for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) controls pages in filegroup FG_ID1, that should be in filegroup FG_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="448e6-116">Explication</span><span class="sxs-lookup"><span data-stu-id="448e6-116">Explanation</span></span>  
 <span data-ttu-id="448e6-117">La page IAM (Index Allocation Map) *P_ID* du groupe de fichiers *FG_ID1* comprend des étendues du groupe de fichiers *FG_ID2*, ce qui est incorrect.</span><span class="sxs-lookup"><span data-stu-id="448e6-117">The index allocation map (IAM) page *P_ID* in filegroup *FG_ID1* incorrectly includes extents from filegroup *FG_ID2*.</span></span> <span data-ttu-id="448e6-118">Toutes les étendues d'une page IAM doivent se trouver dans le même groupe de fichiers qu'elle.</span><span class="sxs-lookup"><span data-stu-id="448e6-118">All extents for an IAM page should be in the same filegroup as the IAM page itself.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="448e6-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="448e6-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="448e6-120">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="448e6-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="448e6-121">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="448e6-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="448e6-122">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="448e6-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="448e6-123">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="448e6-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="448e6-124">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="448e6-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="448e6-125">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="448e6-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="448e6-126">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="448e6-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="448e6-127">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="448e6-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="448e6-128">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="448e6-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="448e6-129">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="448e6-129">Restore from Backup</span></span>  
 <span data-ttu-id="448e6-130">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="448e6-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="448e6-131">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="448e6-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="448e6-132">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="448e6-132">Not applicable.</span></span> <span data-ttu-id="448e6-133">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="448e6-133">This error cannot be repaired.</span></span> <span data-ttu-id="448e6-134">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="448e6-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
