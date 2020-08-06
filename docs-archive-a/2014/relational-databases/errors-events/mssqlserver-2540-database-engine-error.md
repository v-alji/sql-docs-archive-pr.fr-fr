---
title: MSSQLSERVER_2540 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2540 (Database Engine error)
ms.assetid: eb5ee2be-acbb-4fb7-9b45-dc6200bde06e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4a49abeadcd49263ea7d0701ee468a36882179cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696875"
---
# <a name="mssqlserver_2540"></a><span data-ttu-id="540dc-102">MSSQLSERVER_2540</span><span class="sxs-lookup"><span data-stu-id="540dc-102">MSSQLSERVER_2540</span></span>
    
## <a name="details"></a><span data-ttu-id="540dc-103">Détails</span><span class="sxs-lookup"><span data-stu-id="540dc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="540dc-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="540dc-104">Product Name</span></span>|<span data-ttu-id="540dc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="540dc-105">SQL Server</span></span>|  
|<span data-ttu-id="540dc-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="540dc-106">Event ID</span></span>|<span data-ttu-id="540dc-107">2540</span><span class="sxs-lookup"><span data-stu-id="540dc-107">2540</span></span>|  
|<span data-ttu-id="540dc-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="540dc-108">Event Source</span></span>|<span data-ttu-id="540dc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="540dc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="540dc-110">Composant</span><span class="sxs-lookup"><span data-stu-id="540dc-110">Component</span></span>|<span data-ttu-id="540dc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="540dc-111">SQLEngine</span></span>|  
|<span data-ttu-id="540dc-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="540dc-112">Symbolic Name</span></span>|<span data-ttu-id="540dc-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span><span class="sxs-lookup"><span data-stu-id="540dc-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span></span>|  
|<span data-ttu-id="540dc-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="540dc-114">Message Text</span></span>|<span data-ttu-id="540dc-115">Le système ne peut pas réparer seul cette erreur.</span><span class="sxs-lookup"><span data-stu-id="540dc-115">The system cannot self repair this error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="540dc-116">Explication</span><span class="sxs-lookup"><span data-stu-id="540dc-116">Explanation</span></span>  
 <span data-ttu-id="540dc-117">Ce message d'erreur indique des problèmes qui ne peuvent pas être réparés automatiquement, tels que des métadonnées endommagées, des dommages sur les pages PFS (Page Free Space) ou des dommages dans certaines tables de base système critiques.</span><span class="sxs-lookup"><span data-stu-id="540dc-117">This error message indicates problems that cannot be repaired automatically, such as corrupt metadata, Page Free Space (PFS) page corruptions, or corruptions in certain critical system base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="540dc-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="540dc-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="540dc-119">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="540dc-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="540dc-120">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="540dc-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="540dc-121">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="540dc-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="540dc-122">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="540dc-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="540dc-123">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="540dc-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="540dc-124">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="540dc-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="540dc-125">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="540dc-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="540dc-126">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="540dc-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="540dc-127">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="540dc-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="540dc-128">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="540dc-128">Restore from Backup</span></span>  
 <span data-ttu-id="540dc-129">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="540dc-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="540dc-130">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="540dc-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="540dc-131">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="540dc-131">Not applicable.</span></span> <span data-ttu-id="540dc-132">Cette erreur ne peut pas être réparée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="540dc-132">This error cannot be repaired automatically.</span></span>  
  
  
