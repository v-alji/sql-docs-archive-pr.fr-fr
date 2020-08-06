---
title: MSSQLSERVER_7935 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7935 (Database Engine error)
ms.assetid: 45ab21a3-024a-4523-9bd9-1175d01f9c8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a798438213fecf7a6867056c5fe1db033bc6beb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610649"
---
# <a name="mssqlserver_7935"></a><span data-ttu-id="ff1f9-102">MSSQLSERVER_7935</span><span class="sxs-lookup"><span data-stu-id="ff1f9-102">MSSQLSERVER_7935</span></span>
    
## <a name="details"></a><span data-ttu-id="ff1f9-103">Détails</span><span class="sxs-lookup"><span data-stu-id="ff1f9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff1f9-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="ff1f9-104">Product Name</span></span>|<span data-ttu-id="ff1f9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff1f9-105">SQL Server</span></span>|  
|<span data-ttu-id="ff1f9-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="ff1f9-106">Event ID</span></span>|<span data-ttu-id="ff1f9-107">7935</span><span class="sxs-lookup"><span data-stu-id="ff1f9-107">7935</span></span>|  
|<span data-ttu-id="ff1f9-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="ff1f9-108">Event Source</span></span>|<span data-ttu-id="ff1f9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ff1f9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ff1f9-110">Composant</span><span class="sxs-lookup"><span data-stu-id="ff1f9-110">Component</span></span>|<span data-ttu-id="ff1f9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ff1f9-111">SQLEngine</span></span>|  
|<span data-ttu-id="ff1f9-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="ff1f9-112">Symbolic Name</span></span>|<span data-ttu-id="ff1f9-113">DBCC2_FS_MISSING_COLUMN</span><span class="sxs-lookup"><span data-stu-id="ff1f9-113">DBCC2_FS_MISSING_COLUMN</span></span>|  
|<span data-ttu-id="ff1f9-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="ff1f9-114">Message Text</span></span>|<span data-ttu-id="ff1f9-115">Erreur de table, Un ID de répertoire FILESTREAM F_ID existe pour une colonne de l’ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, mais cette colonne n’existe pas dans la partition.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-115">Table error: A Filestream directory ID F_ID exists for a column of object ID O_ID, index ID I_ID, partition ID PN_ID, but that column does not exist in the partition.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ff1f9-116">Explication</span><span class="sxs-lookup"><span data-stu-id="ff1f9-116">Explanation</span></span>  
 <span data-ttu-id="ff1f9-117">Au cours de l'exécution de DBCC CHECKDB, un répertoire FILESTREAM a été trouvé pour une colonne de l'objet spécifié ; toutefois, la colonne n'a pas été trouvée dans les métadonnées correspondantes de la partition.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-117">During DBCC CHECKDB, a FILESTREAM directory was found for a column in the specified object; however, the column was not found in the corresponding metadata of the partition.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ff1f9-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="ff1f9-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="ff1f9-119">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="ff1f9-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="ff1f9-120">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="ff1f9-121">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="ff1f9-122">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="ff1f9-123">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="ff1f9-124">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="ff1f9-125">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="ff1f9-126">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="ff1f9-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="ff1f9-127">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="ff1f9-128">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="ff1f9-128">Restore from Backup</span></span>  
 <span data-ttu-id="ff1f9-129">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="ff1f9-130">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="ff1f9-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="ff1f9-131">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-131">Not applicable.</span></span> <span data-ttu-id="ff1f9-132">Cette erreur ne peut pas être réparée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ff1f9-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="ff1f9-133">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff1f9-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
