---
title: MSSQLSERVER_5233 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5233 (Database Engine error)
ms.assetid: 7a855afa-2d3b-49b7-adef-197b99fc98b1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0a5e2c603652534a6d3093a01da0a926a7195954
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612843"
---
# <a name="mssqlserver_5233"></a><span data-ttu-id="e9047-102">MSSQLSERVER_5233</span><span class="sxs-lookup"><span data-stu-id="e9047-102">MSSQLSERVER_5233</span></span>
    
## <a name="details"></a><span data-ttu-id="e9047-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e9047-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9047-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e9047-104">Product Name</span></span>|<span data-ttu-id="e9047-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9047-105">SQL Server</span></span>|  
|<span data-ttu-id="e9047-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e9047-106">Event ID</span></span>|<span data-ttu-id="e9047-107">5233</span><span class="sxs-lookup"><span data-stu-id="e9047-107">5233</span></span>|  
|<span data-ttu-id="e9047-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e9047-108">Event Source</span></span>|<span data-ttu-id="e9047-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e9047-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e9047-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e9047-110">Component</span></span>|<span data-ttu-id="e9047-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e9047-111">SQLEngine</span></span>|  
|<span data-ttu-id="e9047-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e9047-112">Symbolic Name</span></span>|<span data-ttu-id="e9047-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="e9047-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="e9047-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e9047-114">Message Text</span></span>|<span data-ttu-id="e9047-115">Erreur de table : ID d'unité d'allocation A_ID, page P_ID.</span><span class="sxs-lookup"><span data-stu-id="e9047-115">Table error: alloc unit ID A_ID, page P_ID.</span></span> <span data-ttu-id="e9047-116">Échec du test (TEST).</span><span class="sxs-lookup"><span data-stu-id="e9047-116">The test (TEST) failed.</span></span> <span data-ttu-id="e9047-117">Les valeurs sont VAL1 et VAL2.</span><span class="sxs-lookup"><span data-stu-id="e9047-117">The values are VAL1 and VAL2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e9047-118">Explication</span><span class="sxs-lookup"><span data-stu-id="e9047-118">Explanation</span></span>  
 <span data-ttu-id="e9047-119">L’audit de la page *P_ID* a échoué en raison d’une altération dans l’en-tête de la page.</span><span class="sxs-lookup"><span data-stu-id="e9047-119">Page *P_ID* has failed auditing due to a corruption in its page header.</span></span> <span data-ttu-id="e9047-120">La chaîne contenue dans TEST indique le test qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="e9047-120">The string in TEST gives the actual test that failed.</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="e9047-121">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="e9047-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="e9047-122">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="e9047-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="e9047-123">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="e9047-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="e9047-124">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="e9047-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="e9047-125">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="e9047-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="e9047-126">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="e9047-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="e9047-127">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="e9047-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="e9047-128">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="e9047-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="e9047-129">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="e9047-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="e9047-130">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="e9047-130">Restore from Backup</span></span>  
 <span data-ttu-id="e9047-131">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e9047-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="e9047-132">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="e9047-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="e9047-133">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="e9047-133">Not applicable.</span></span> <span data-ttu-id="e9047-134">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="e9047-134">This error cannot be repaired.</span></span> <span data-ttu-id="e9047-135">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9047-135">If you cannot restore the database from a backup, contact Microsoft Customer Service and Support (CSS).</span></span>  
  
  
