---
title: MSSQLSERVER_5256 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5256 (Database Engine error)
ms.assetid: 6fe254b4-2926-446f-8b20-0f1d921a4615
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9146b7744e78550463cbec4c05df5fd75a049898
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702916"
---
# <a name="mssqlserver_5256"></a><span data-ttu-id="b6e25-102">MSSQLSERVER_5256</span><span class="sxs-lookup"><span data-stu-id="b6e25-102">MSSQLSERVER_5256</span></span>
    
## <a name="details"></a><span data-ttu-id="b6e25-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b6e25-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6e25-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b6e25-104">Product Name</span></span>|<span data-ttu-id="b6e25-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b6e25-105">SQL Server</span></span>|  
|<span data-ttu-id="b6e25-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b6e25-106">Event ID</span></span>|<span data-ttu-id="b6e25-107">5256</span><span class="sxs-lookup"><span data-stu-id="b6e25-107">5256</span></span>|  
|<span data-ttu-id="b6e25-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b6e25-108">Event Source</span></span>|<span data-ttu-id="b6e25-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b6e25-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b6e25-110">Composant</span><span class="sxs-lookup"><span data-stu-id="b6e25-110">Component</span></span>|<span data-ttu-id="b6e25-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b6e25-111">SQLEngine</span></span>|  
|<span data-ttu-id="b6e25-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b6e25-112">Symbolic Name</span></span>|<span data-ttu-id="b6e25-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="b6e25-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="b6e25-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b6e25-114">Message Text</span></span>|<span data-ttu-id="b6e25-115">Erreur de table : ID d'unité d'allocation A_ID, la page P_ID1 contient un ID de page incorrect dans son en-tête de page.</span><span class="sxs-lookup"><span data-stu-id="b6e25-115">Table error: alloc unit ID A_ID, page P_ID1 contains an incorrect page ID in its page header.</span></span> <span data-ttu-id="b6e25-116">PageId dans l'en-tête de page = P_ID2.</span><span class="sxs-lookup"><span data-stu-id="b6e25-116">The PageId in the page header = P_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b6e25-117">Explication</span><span class="sxs-lookup"><span data-stu-id="b6e25-117">Explanation</span></span>  
 <span data-ttu-id="b6e25-118">L’en-tête de page de la page *P_ID1* contient un ID de page incorrect, *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="b6e25-118">The page header of page *P_ID1* contains an incorrect page ID, *P_ID2*.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b6e25-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b6e25-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b6e25-120">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="b6e25-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b6e25-121">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="b6e25-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b6e25-122">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="b6e25-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b6e25-123">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="b6e25-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b6e25-124">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="b6e25-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b6e25-125">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="b6e25-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b6e25-126">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="b6e25-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b6e25-127">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="b6e25-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b6e25-128">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="b6e25-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b6e25-129">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="b6e25-129">Restore from Backup</span></span>  
 <span data-ttu-id="b6e25-130">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b6e25-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b6e25-131">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b6e25-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b6e25-132">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="b6e25-132">Not applicable.</span></span> <span data-ttu-id="b6e25-133">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="b6e25-133">This error cannot be repaired.</span></span> <span data-ttu-id="b6e25-134">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6e25-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
