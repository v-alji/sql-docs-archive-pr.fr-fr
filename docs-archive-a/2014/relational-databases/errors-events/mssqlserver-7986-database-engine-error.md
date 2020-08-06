---
title: MSSQLSERVER_7986 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7986 (Database Engine error)
ms.assetid: ae64276c-4e1e-4ef3-9ee9-ebeb2f61e565
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4f7d312987a2692c95f2cf6dbe0c86a4b2acbe6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702908"
---
# <a name="mssqlserver_7986"></a><span data-ttu-id="0bddb-102">MSSQLSERVER_7986</span><span class="sxs-lookup"><span data-stu-id="0bddb-102">MSSQLSERVER_7986</span></span>
    
## <a name="details"></a><span data-ttu-id="0bddb-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0bddb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0bddb-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0bddb-104">Product Name</span></span>|<span data-ttu-id="0bddb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0bddb-105">SQL Server</span></span>|  
|<span data-ttu-id="0bddb-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0bddb-106">Event ID</span></span>|<span data-ttu-id="0bddb-107">7986</span><span class="sxs-lookup"><span data-stu-id="0bddb-107">7986</span></span>|  
|<span data-ttu-id="0bddb-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0bddb-108">Event Source</span></span>|<span data-ttu-id="0bddb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0bddb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0bddb-110">Composant</span><span class="sxs-lookup"><span data-stu-id="0bddb-110">Component</span></span>|<span data-ttu-id="0bddb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0bddb-111">SQLEngine</span></span>|  
|<span data-ttu-id="0bddb-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0bddb-112">Symbolic Name</span></span>|<span data-ttu-id="0bddb-113">DBCC2_PRE_CHECKS_CROSS_OBJECT_LINKAGE</span><span class="sxs-lookup"><span data-stu-id="0bddb-113">DBCC2_PRE_CHECKS_CROSS_OBJECT_LINKAGE</span></span>|  
|<span data-ttu-id="0bddb-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0bddb-114">Message Text</span></span>|<span data-ttu-id="0bddb-115">Pré-vérifications de table système : l’ID d’objet ID O_ID possède une liaison de chaînes croisées.</span><span class="sxs-lookup"><span data-stu-id="0bddb-115">System table pre-checks: Object ID O_ID has cross-object chain linkage.</span></span> <span data-ttu-id="0bddb-116">La page P_ID1 pointe vers P_ID2 dans l'ID d'unité d'allocation A_ID1 (doit être A_ID2).</span><span class="sxs-lookup"><span data-stu-id="0bddb-116">Page P_ID1 points to P_ID2 in alloc unit ID A_ID1 (should be A_ID2).</span></span> <span data-ttu-id="0bddb-117">L’instruction de vérification s’est arrêtée en raison d’une erreur irréparable.</span><span class="sxs-lookup"><span data-stu-id="0bddb-117">Check statement terminated due to unrepairable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0bddb-118">Explication</span><span class="sxs-lookup"><span data-stu-id="0bddb-118">Explanation</span></span>  
 <span data-ttu-id="0bddb-119">La première étape d'un DBCC CHECKDB consiste à effectuer des prévérifications sur les pages de données des tables système critiques.</span><span class="sxs-lookup"><span data-stu-id="0bddb-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="0bddb-120">Toute erreur détectée à ce stade étant irréparable, DBCC CHECKDB s'arrête immédiatement.</span><span class="sxs-lookup"><span data-stu-id="0bddb-120">If any errors are found, they cannot be repaired; therefore, the DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="0bddb-121">Le pointeur de page suivant de la page *P_ID1* dans le niveau de données de l’objet spécifié pointe vers une page, *P_ID2*, dans un objet différent.</span><span class="sxs-lookup"><span data-stu-id="0bddb-121">The next page pointer of page *P_ID1* in the data level of the specified object points to a page, *P_ID2*, in a different object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0bddb-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0bddb-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="0bddb-123">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="0bddb-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="0bddb-124">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="0bddb-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="0bddb-125">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="0bddb-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="0bddb-126">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="0bddb-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="0bddb-127">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="0bddb-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="0bddb-128">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="0bddb-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="0bddb-129">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="0bddb-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="0bddb-130">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="0bddb-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="0bddb-131">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="0bddb-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="0bddb-132">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="0bddb-132">Restore from Backup</span></span>  
 <span data-ttu-id="0bddb-133">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0bddb-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="0bddb-134">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="0bddb-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="0bddb-135">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="0bddb-135">Not applicable.</span></span> <span data-ttu-id="0bddb-136">Cette erreur ne peut pas être réparée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="0bddb-136">This error cannot be repaired automatically.</span></span> <span data-ttu-id="0bddb-137">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bddb-137">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
