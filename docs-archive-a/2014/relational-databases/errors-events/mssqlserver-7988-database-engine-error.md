---
title: MSSQLSERVER_7988 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7988 (Database Engine error)
ms.assetid: 29b967b8-de30-4618-99a8-8b1155e69026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 984cb03aeb5feaa230762e200304f16cd8c5df08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699617"
---
# <a name="mssqlserver_7988"></a><span data-ttu-id="a5f1b-102">MSSQLSERVER_7988</span><span class="sxs-lookup"><span data-stu-id="a5f1b-102">MSSQLSERVER_7988</span></span>
    
## <a name="details"></a><span data-ttu-id="a5f1b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="a5f1b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5f1b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="a5f1b-104">Product Name</span></span>|<span data-ttu-id="a5f1b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5f1b-105">SQL Server</span></span>|  
|<span data-ttu-id="a5f1b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="a5f1b-106">Event ID</span></span>|<span data-ttu-id="a5f1b-107">7988</span><span class="sxs-lookup"><span data-stu-id="a5f1b-107">7988</span></span>|  
|<span data-ttu-id="a5f1b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="a5f1b-108">Event Source</span></span>|<span data-ttu-id="a5f1b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a5f1b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a5f1b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="a5f1b-110">Component</span></span>|<span data-ttu-id="a5f1b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a5f1b-111">SQLEngine</span></span>|  
|<span data-ttu-id="a5f1b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="a5f1b-112">Symbolic Name</span></span>|<span data-ttu-id="a5f1b-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span><span class="sxs-lookup"><span data-stu-id="a5f1b-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span></span>|  
|<span data-ttu-id="a5f1b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="a5f1b-114">Message Text</span></span>|<span data-ttu-id="a5f1b-115">Pré-vérifications de table système : ID d’objet O_ID.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="a5f1b-116">Boucle dans la chaîne des données détectée à P_ID.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-116">Loop in data chain detected at P_ID.</span></span> <span data-ttu-id="a5f1b-117">Vérifiez l'instruction qui s'est arrêtée en raison d'une erreur irréparable.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a5f1b-118">Explication</span><span class="sxs-lookup"><span data-stu-id="a5f1b-118">Explanation</span></span>  
 <span data-ttu-id="a5f1b-119">La première étape d'un DBCC CHECKDB consiste à effectuer des prévérifications sur les pages de données des tables système critiques.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="a5f1b-120">Toute erreur détectée à ce stade étant irréparable, DBCC CHECKDB s’arrête immédiatement.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-120">If any errors are found, they cannot be repaired; therefore, DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="a5f1b-121">Une boucle de liaison de page a été détectée dans la page *P_ID*.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-121">A page linkage loop has been detected on page *P_ID*.</span></span> <span data-ttu-id="a5f1b-122">Cela se produit lorsque les pointeurs d'une page menant à la page suivante finissent par revenir à cette page.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-122">A page linkage loop occurs when the next page pointers from a page eventually return to the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a5f1b-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a5f1b-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a5f1b-124">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="a5f1b-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a5f1b-125">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a5f1b-126">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a5f1b-127">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a5f1b-128">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a5f1b-129">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a5f1b-130">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a5f1b-131">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="a5f1b-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a5f1b-132">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a5f1b-133">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a5f1b-133">Restore from Backup</span></span>  
 <span data-ttu-id="a5f1b-134">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a5f1b-135">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a5f1b-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a5f1b-136">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-136">Not applicable.</span></span> <span data-ttu-id="a5f1b-137">Cette erreur ne peut pas être réparée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a5f1b-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="a5f1b-138">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service de support technique de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5f1b-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
