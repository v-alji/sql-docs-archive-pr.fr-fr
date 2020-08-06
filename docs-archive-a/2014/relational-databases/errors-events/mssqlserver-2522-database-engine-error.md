---
title: MSSQLSERVER_2522 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2522 (Database Engine error)
ms.assetid: 19b9b00c-330f-4dd3-9052-9d88bce83849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60446c21599c02ee9c4bc96789b106b49b71582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600977"
---
# <a name="mssqlserver_2522"></a><span data-ttu-id="e2e97-102">MSSQLSERVER_2522</span><span class="sxs-lookup"><span data-stu-id="e2e97-102">MSSQLSERVER_2522</span></span>
    
## <a name="details"></a><span data-ttu-id="e2e97-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e2e97-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2e97-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e2e97-104">Product Name</span></span>|<span data-ttu-id="e2e97-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2e97-105">SQL Server</span></span>|  
|<span data-ttu-id="e2e97-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e2e97-106">Event ID</span></span>|<span data-ttu-id="e2e97-107">2522</span><span class="sxs-lookup"><span data-stu-id="e2e97-107">2522</span></span>|  
|<span data-ttu-id="e2e97-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e2e97-108">Event Source</span></span>|<span data-ttu-id="e2e97-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e2e97-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e2e97-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e2e97-110">Component</span></span>|<span data-ttu-id="e2e97-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e2e97-111">SQLEngine</span></span>|  
|<span data-ttu-id="e2e97-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e2e97-112">Symbolic Name</span></span>|<span data-ttu-id="e2e97-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="e2e97-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span></span>|  
|<span data-ttu-id="e2e97-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e2e97-114">Message Text</span></span>|<span data-ttu-id="e2e97-115">Impossible de traiter l'index I_NAME de la table O_NAME car le groupe de fichiers F_NAME n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="e2e97-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is invalid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e2e97-116">Explication</span><span class="sxs-lookup"><span data-stu-id="e2e97-116">Explanation</span></span>  
 <span data-ttu-id="e2e97-117">Ce message fourni à titre d'information indique que l'index ne peut pas être contrôlé, car l'un des ID de groupe de fichiers stocké dans les métadonnées de l'index n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="e2e97-117">This informational message indicates that the index cannot be checked because one of the filegroup IDs that is stored in the metadata of the index does not exist.</span></span> <span data-ttu-id="e2e97-118">L'ID de groupe de fichiers qui n'est pas valide peut  appartenir aux données elles-mêmes, aux données LOB (Large Object) ou aux données de dépassement de ligne.</span><span class="sxs-lookup"><span data-stu-id="e2e97-118">The filegroup ID that is not valid might pertain to the data itself, or to the large object (LOB) data, or to the row-overflow data.</span></span>  
  
 <span data-ttu-id="e2e97-119">S'il n'y a pas d'autre problème, tous les autres index du même objet seront vérifiés.</span><span class="sxs-lookup"><span data-stu-id="e2e97-119">If there are no problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e2e97-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e2e97-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="e2e97-121">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="e2e97-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="e2e97-122">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="e2e97-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="e2e97-123">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="e2e97-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="e2e97-124">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="e2e97-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="e2e97-125">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="e2e97-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="e2e97-126">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="e2e97-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="e2e97-127">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="e2e97-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="e2e97-128">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="e2e97-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="e2e97-129">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="e2e97-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="e2e97-130">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="e2e97-130">Restore from Backup</span></span>  
 <span data-ttu-id="e2e97-131">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e2e97-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="e2e97-132">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="e2e97-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="e2e97-133">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="e2e97-133">Not applicable.</span></span> <span data-ttu-id="e2e97-134">Cette erreur ne peut pas être réparée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="e2e97-134">This error cannot be repaired automatically.</span></span>  
  
  
