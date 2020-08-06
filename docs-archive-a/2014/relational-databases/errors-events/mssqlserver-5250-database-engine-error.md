---
title: MSSQLSERVER_5250 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5250 (Database Engine error)
ms.assetid: f4a1d0e8-f27f-4cb8-a25d-040b40555dcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace26b88aca5b00c23aff3fe48f7c1d04ef35245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702920"
---
# <a name="mssqlserver_5250"></a><span data-ttu-id="e009e-102">MSSQLSERVER_5250</span><span class="sxs-lookup"><span data-stu-id="e009e-102">MSSQLSERVER_5250</span></span>
    
## <a name="details"></a><span data-ttu-id="e009e-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e009e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e009e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e009e-104">Product Name</span></span>|<span data-ttu-id="e009e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e009e-105">SQL Server</span></span>|  
|<span data-ttu-id="e009e-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e009e-106">Event ID</span></span>|<span data-ttu-id="e009e-107">5250</span><span class="sxs-lookup"><span data-stu-id="e009e-107">5250</span></span>|  
|<span data-ttu-id="e009e-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e009e-108">Event Source</span></span>|<span data-ttu-id="e009e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e009e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e009e-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e009e-110">Component</span></span>|<span data-ttu-id="e009e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e009e-111">SQLEngine</span></span>|  
|<span data-ttu-id="e009e-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e009e-112">Symbolic Name</span></span>|<span data-ttu-id="e009e-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="e009e-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span></span>|  
|<span data-ttu-id="e009e-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e009e-114">Message Text</span></span>|<span data-ttu-id="e009e-115">Erreur de base de données : PAGE_TYPE, la page P_ID de la base de données 'NAME' (ID de base de données DB_ID) n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="e009e-115">Database error: PAGE_TYPE page P_ID for database 'NAME' (database ID DB_ID) is invalid.</span></span> <span data-ttu-id="e009e-116">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="e009e-116">This error cannot be repaired.</span></span> <span data-ttu-id="e009e-117">Vous devez effectuer une restauration à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e009e-117">You must restore from backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e009e-118">Explication</span><span class="sxs-lookup"><span data-stu-id="e009e-118">Explanation</span></span>  
 <span data-ttu-id="e009e-119">Une page d'en-tête de fichier ou une page de démarrage est endommagée dans la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e009e-119">A file header page or boot page in the specified database is corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e009e-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e009e-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="e009e-121">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="e009e-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="e009e-122">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="e009e-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="e009e-123">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="e009e-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="e009e-124">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="e009e-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="e009e-125">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="e009e-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="e009e-126">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="e009e-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="e009e-127">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="e009e-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="e009e-128">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="e009e-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="e009e-129">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="e009e-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="e009e-130">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="e009e-130">Restore from Backup</span></span>  
 <span data-ttu-id="e009e-131">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e009e-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="e009e-132">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="e009e-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="e009e-133">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="e009e-133">Not applicable.</span></span> <span data-ttu-id="e009e-134">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="e009e-134">This error cannot be repaired.</span></span> <span data-ttu-id="e009e-135">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e009e-135">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
