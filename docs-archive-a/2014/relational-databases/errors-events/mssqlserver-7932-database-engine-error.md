---
title: MSSQLSERVER_7932 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7932 (Database Engine error)
ms.assetid: e2ad218a-3249-4f18-8b32-09f0030765a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 237d9be3e0f22664adb061d3bba526c9878d3bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610660"
---
# <a name="mssqlserver_7932"></a><span data-ttu-id="fd8f9-102">MSSQLSERVER_7932</span><span class="sxs-lookup"><span data-stu-id="fd8f9-102">MSSQLSERVER_7932</span></span>
    
## <a name="details"></a><span data-ttu-id="fd8f9-103">Détails</span><span class="sxs-lookup"><span data-stu-id="fd8f9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd8f9-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="fd8f9-104">Product Name</span></span>|<span data-ttu-id="fd8f9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd8f9-105">SQL Server</span></span>|  
|<span data-ttu-id="fd8f9-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="fd8f9-106">Event ID</span></span>|<span data-ttu-id="fd8f9-107">7932</span><span class="sxs-lookup"><span data-stu-id="fd8f9-107">7932</span></span>|  
|<span data-ttu-id="fd8f9-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="fd8f9-108">Event Source</span></span>|<span data-ttu-id="fd8f9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fd8f9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fd8f9-110">Composant</span><span class="sxs-lookup"><span data-stu-id="fd8f9-110">Component</span></span>|<span data-ttu-id="fd8f9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fd8f9-111">SQLEngine</span></span>|  
|<span data-ttu-id="fd8f9-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="fd8f9-112">Symbolic Name</span></span>|<span data-ttu-id="fd8f9-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span><span class="sxs-lookup"><span data-stu-id="fd8f9-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span></span>|  
|<span data-ttu-id="fd8f9-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="fd8f9-114">Message Text</span></span>|<span data-ttu-id="fd8f9-115">Erreur de table, l’ID de répertoire FILESTREAM correspondant à l’ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, figure dans le groupe de fichiers FG_ID1, alors qu'il devrait être dans le groupe de fichiers FG_ID2.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-115">Table error: The FileStream directory ID F_ID for object ID O_ID, index ID I_ID, partition ID PN_ID is in filegroup FG_ID1, but should be in filegroup FG_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fd8f9-116">Explication</span><span class="sxs-lookup"><span data-stu-id="fd8f9-116">Explanation</span></span>  
 <span data-ttu-id="fd8f9-117">Au cours de l'exécution de DBCC CHECKDB, le stockage FILESTREAM de l'objet spécifié a été détecté dans le mauvais groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-117">During DBCC CHECKDB, the FILESTREAM storage for the specified object was detected in the wrong filegroup.</span></span> <span data-ttu-id="fd8f9-118">Il peut s'agir d'une altération dans les métadonnées de l'objet.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-118">This could be a corruption in the metadata of the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fd8f9-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="fd8f9-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="fd8f9-120">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="fd8f9-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="fd8f9-121">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="fd8f9-122">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="fd8f9-123">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="fd8f9-124">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="fd8f9-125">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="fd8f9-126">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="fd8f9-127">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="fd8f9-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="fd8f9-128">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="fd8f9-129">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="fd8f9-129">Restore from Backup</span></span>  
 <span data-ttu-id="fd8f9-130">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="fd8f9-131">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="fd8f9-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="fd8f9-132">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-132">Not applicable.</span></span> <span data-ttu-id="fd8f9-133">Cette erreur ne peut pas être réparée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="fd8f9-133">This error cannot be repaired automatically.</span></span> <span data-ttu-id="fd8f9-134">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd8f9-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
