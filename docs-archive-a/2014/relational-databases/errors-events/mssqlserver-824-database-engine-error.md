---
title: MSSQLSERVER_824 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
ms.assetid: 2aa22246-2712-4fdb-9744-36e7e6f3175e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d57b19bc8c837b92b65728fbb0046039b862d31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605441"
---
# <a name="mssqlserver_824"></a><span data-ttu-id="076dd-102">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="076dd-102">MSSQLSERVER_824</span></span>
    
## <a name="details"></a><span data-ttu-id="076dd-103">Détails</span><span class="sxs-lookup"><span data-stu-id="076dd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="076dd-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="076dd-104">Product Name</span></span>|<span data-ttu-id="076dd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="076dd-105">SQL Server</span></span>|  
|<span data-ttu-id="076dd-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="076dd-106">Event ID</span></span>|<span data-ttu-id="076dd-107">824</span><span class="sxs-lookup"><span data-stu-id="076dd-107">824</span></span>|  
|<span data-ttu-id="076dd-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="076dd-108">Event Source</span></span>|<span data-ttu-id="076dd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="076dd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="076dd-110">Composant</span><span class="sxs-lookup"><span data-stu-id="076dd-110">Component</span></span>|<span data-ttu-id="076dd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="076dd-111">SQLEngine</span></span>|  
|<span data-ttu-id="076dd-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="076dd-112">Symbolic Name</span></span>|<span data-ttu-id="076dd-113">B_HARDSSERR</span><span class="sxs-lookup"><span data-stu-id="076dd-113">B_HARDSSERR</span></span>|  
|<span data-ttu-id="076dd-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="076dd-114">Message Text</span></span>|<span data-ttu-id="076dd-115">SQL Server a détecté une erreur d'E/S logique et relative à la cohérence.</span><span class="sxs-lookup"><span data-stu-id="076dd-115">SQL Server detected a logical consistency-based I/O error: %ls.</span></span> <span data-ttu-id="076dd-116">L'erreur %ls s'est produite pendant une opération de %S_MSG de la page %S_PGID dans la base de données avec l'ID %d au niveau du décalage %#016I64x dans le fichier '%ls'.</span><span class="sxs-lookup"><span data-stu-id="076dd-116">It occurred during a %S_MSG of page %S_PGID in database ID %d at offset %#016I64x in file '%ls'.</span></span>  <span data-ttu-id="076dd-117">Vous trouverez peut-être plus de détails dans les messages supplémentaires qui figurent dans le journal des erreurs et le journal des événements système de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="076dd-117">Additional messages in the SQL Server error log or system event log may provide more detail.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="076dd-118">Explication</span><span class="sxs-lookup"><span data-stu-id="076dd-118">Explanation</span></span>  
 <span data-ttu-id="076dd-119">Cette erreur indique que Windows considère que la page est correctement lue à partir du disque alors que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] signale qu'il y a un problème avec la page.</span><span class="sxs-lookup"><span data-stu-id="076dd-119">This error indicates that Windows reports that the page is successfully read from disk, but [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has discovered something wrong with the page.</span></span> <span data-ttu-id="076dd-120">Cette erreur est similaire à l'erreur 823, à la différence qu'elle n'a pas été détectée par Windows.</span><span class="sxs-lookup"><span data-stu-id="076dd-120">This error is similar to error 823 except that Windows did not detect the error.</span></span> <span data-ttu-id="076dd-121">Cela indique généralement un problème dans le sous-système d'E/S, comme un lecteur de disque défaillant, des problèmes avec le microprogramme d'un disque, un pilote de périphérique défectueux, etc.</span><span class="sxs-lookup"><span data-stu-id="076dd-121">This usually indicates a problem in the I/O subsystem, such as a failing disk drive, disk firmware problems, faulty device driver, and so on.</span></span> <span data-ttu-id="076dd-122">Pour plus d’informations sur les erreurs d’E/S, consultez [Concepts de base des E/S Microsoft SQL Server, chapitre 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="076dd-122">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="076dd-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="076dd-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="076dd-124">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="076dd-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="076dd-125">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="076dd-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="076dd-126">Examinez également les journaux système et d'applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows ainsi que le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="076dd-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred because of hardware failure.</span></span> <span data-ttu-id="076dd-127">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="076dd-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="076dd-128">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="076dd-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="076dd-129">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="076dd-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="076dd-130">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="076dd-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="076dd-131">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="076dd-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="076dd-132">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="076dd-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="076dd-133">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="076dd-133">Restore from Backup</span></span>  
 <span data-ttu-id="076dd-134">S'il ne s'agit pas d'un problème de matériel et qu'une sauvegarde saine est disponible, restaurez la base de données à partir de cette sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="076dd-134">If the problem is not hardware-related and a known clean backup is available, restore the database from the backup.</span></span>  
  
 <span data-ttu-id="076dd-135">Envisagez de modifier les bases de données afin qu'elles utilisent l'option PAGE_VERIFY CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="076dd-135">Consider changing the databases to use the PAGE_VERIFY CHECKSUM option.</span></span> <span data-ttu-id="076dd-136">Pour plus d’informations sur PAGE_VERIFY, consultez [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="076dd-136">For information about PAGE_VERIFY, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="076dd-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="076dd-137">See Also</span></span>  
 [<span data-ttu-id="076dd-138">Gérer la table suspect_pages &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="076dd-138">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
