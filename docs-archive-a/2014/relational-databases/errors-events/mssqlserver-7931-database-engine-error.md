---
title: MSSQLSERVER_7931 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7931 (Database Engine error)
ms.assetid: 18e7a3dc-7d8a-41b9-8724-d2a8587b6903
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a93cc56869448d1dbcf95c1d9e1ffe1fe023e7e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610661"
---
# <a name="mssqlserver_7931"></a><span data-ttu-id="8040b-102">MSSQLSERVER_7931</span><span class="sxs-lookup"><span data-stu-id="8040b-102">MSSQLSERVER_7931</span></span>
    
## <a name="details"></a><span data-ttu-id="8040b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="8040b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8040b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8040b-104">Product Name</span></span>|<span data-ttu-id="8040b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8040b-105">SQL Server</span></span>|  
|<span data-ttu-id="8040b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="8040b-106">Event ID</span></span>|<span data-ttu-id="8040b-107">7931</span><span class="sxs-lookup"><span data-stu-id="8040b-107">7931</span></span>|  
|<span data-ttu-id="8040b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="8040b-108">Event Source</span></span>|<span data-ttu-id="8040b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8040b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8040b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="8040b-110">Component</span></span>|<span data-ttu-id="8040b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8040b-111">SQLEngine</span></span>|  
|<span data-ttu-id="8040b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="8040b-112">Symbolic Name</span></span>|<span data-ttu-id="8040b-113">DBCC2_FS_DOUBLE_ROWSET_ACTUAL_FACT</span><span class="sxs-lookup"><span data-stu-id="8040b-113">DBCC2_FS_DOUBLE_ROWSET_ACTUAL_FACT</span></span>|  
|<span data-ttu-id="8040b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="8040b-114">Message Text</span></span>|<span data-ttu-id="8040b-115">Erreur de base de données : l’ID de répertoire FileStream F_ID pour une partition a été détecté deux fois.</span><span class="sxs-lookup"><span data-stu-id="8040b-115">Database error: The FileStream directory ID F_ID for a partition was seen twice.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8040b-116">Explication</span><span class="sxs-lookup"><span data-stu-id="8040b-116">Explanation</span></span>  
 <span data-ttu-id="8040b-117">Le même ID de partition d'un répertoire Filestream a été trouvé deux fois dans les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="8040b-117">The same partition ID for a Filestream directory was found in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8040b-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="8040b-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="8040b-119">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="8040b-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="8040b-120">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="8040b-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="8040b-121">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="8040b-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="8040b-122">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="8040b-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="8040b-123">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="8040b-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="8040b-124">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="8040b-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="8040b-125">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="8040b-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="8040b-126">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="8040b-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="8040b-127">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="8040b-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="8040b-128">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="8040b-128">Restore from Backup</span></span>  
 <span data-ttu-id="8040b-129">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8040b-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="8040b-130">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="8040b-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="8040b-131">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="8040b-131">Not applicable.</span></span> <span data-ttu-id="8040b-132">Cette erreur ne peut pas être réparée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="8040b-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="8040b-133">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8040b-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
