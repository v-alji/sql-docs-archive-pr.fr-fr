---
title: MSSQLSERVER_7906 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7906 (Database Engine error)
ms.assetid: 9638a764-4ac1-40ae-a614-2726ebcc6ba4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57485a8f330f186a4abd83182c6035168ed38e0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605453"
---
# <a name="mssqlserver_7906"></a><span data-ttu-id="e3d64-102">MSSQLSERVER_7906</span><span class="sxs-lookup"><span data-stu-id="e3d64-102">MSSQLSERVER_7906</span></span>
    
## <a name="details"></a><span data-ttu-id="e3d64-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e3d64-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3d64-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e3d64-104">Product Name</span></span>|<span data-ttu-id="e3d64-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3d64-105">SQL Server</span></span>|  
|<span data-ttu-id="e3d64-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e3d64-106">Event ID</span></span>|<span data-ttu-id="e3d64-107">7906</span><span class="sxs-lookup"><span data-stu-id="e3d64-107">7906</span></span>|  
|<span data-ttu-id="e3d64-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e3d64-108">Event Source</span></span>|<span data-ttu-id="e3d64-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e3d64-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e3d64-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e3d64-110">Component</span></span>|<span data-ttu-id="e3d64-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e3d64-111">SQLEngine</span></span>|  
|<span data-ttu-id="e3d64-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e3d64-112">Symbolic Name</span></span>|<span data-ttu-id="e3d64-113">DBCC2_FS_INVALID_TOP_LEVEL_FILE</span><span class="sxs-lookup"><span data-stu-id="e3d64-113">DBCC2_FS_INVALID_TOP_LEVEL_FILE</span></span>|  
|<span data-ttu-id="e3d64-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e3d64-114">Message Text</span></span>|<span data-ttu-id="e3d64-115">Erreur de base de données : le fichier "FILE" n’est pas un fichier Filestream valide.</span><span class="sxs-lookup"><span data-stu-id="e3d64-115">Database error: The file 'FILE' is not a valid Filestream file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e3d64-116">Explication</span><span class="sxs-lookup"><span data-stu-id="e3d64-116">Explanation</span></span>  
 <span data-ttu-id="e3d64-117">À l'exception de certains fichiers spéciaux, tels que « filestream.hdr », aucun fichier ne doit figurer directement dans l'espace de données Filestream.</span><span class="sxs-lookup"><span data-stu-id="e3d64-117">Except for some special files such as, 'filestream.hdr', no files should be found directly under the Filestream dataspace.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e3d64-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e3d64-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="e3d64-119">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="e3d64-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="e3d64-120">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="e3d64-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="e3d64-121">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="e3d64-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="e3d64-122">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="e3d64-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="e3d64-123">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="e3d64-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="e3d64-124">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="e3d64-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="e3d64-125">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="e3d64-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="e3d64-126">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="e3d64-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="e3d64-127">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="e3d64-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="e3d64-128">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="e3d64-128">Restore from Backup</span></span>  
 <span data-ttu-id="e3d64-129">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e3d64-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="e3d64-130">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="e3d64-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="e3d64-131">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="e3d64-131">Not applicable.</span></span> <span data-ttu-id="e3d64-132">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="e3d64-132">This error cannot be repaired.</span></span> <span data-ttu-id="e3d64-133">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3d64-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
