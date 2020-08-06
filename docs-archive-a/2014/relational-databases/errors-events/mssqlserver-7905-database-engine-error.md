---
title: MSSQLSERVER_7905 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7905 (Database Engine error)
ms.assetid: cf19fbbb-7158-45f2-8778-8f3cad7f574a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 253bf03c1bfacccfd809cd417163eb9d54644f28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605455"
---
# <a name="mssqlserver_7905"></a><span data-ttu-id="c9f62-102">MSSQLSERVER_7905</span><span class="sxs-lookup"><span data-stu-id="c9f62-102">MSSQLSERVER_7905</span></span>
    
## <a name="details"></a><span data-ttu-id="c9f62-103">Détails</span><span class="sxs-lookup"><span data-stu-id="c9f62-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9f62-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="c9f62-104">Product Name</span></span>|<span data-ttu-id="c9f62-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9f62-105">SQL Server</span></span>|  
|<span data-ttu-id="c9f62-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="c9f62-106">Event ID</span></span>|<span data-ttu-id="c9f62-107">7905</span><span class="sxs-lookup"><span data-stu-id="c9f62-107">7905</span></span>|  
|<span data-ttu-id="c9f62-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="c9f62-108">Event Source</span></span>|<span data-ttu-id="c9f62-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c9f62-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c9f62-110">Composant</span><span class="sxs-lookup"><span data-stu-id="c9f62-110">Component</span></span>|<span data-ttu-id="c9f62-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c9f62-111">SQLEngine</span></span>|  
|<span data-ttu-id="c9f62-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="c9f62-112">Symbolic Name</span></span>|<span data-ttu-id="c9f62-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="c9f62-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span></span>|  
|<span data-ttu-id="c9f62-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="c9f62-114">Message Text</span></span>|<span data-ttu-id="c9f62-115">Erreur de base de données : le répertoire 'DIRECTORY' n'est pas un répertoire Filestream valide.</span><span class="sxs-lookup"><span data-stu-id="c9f62-115">Database error: The directory 'DIRECTORY' is not a valid Filestream directory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9f62-116">Explication</span><span class="sxs-lookup"><span data-stu-id="c9f62-116">Explanation</span></span>  
 <span data-ttu-id="c9f62-117">Le nom d'un répertoire d'ensemble de lignes est l'ID de partition de la partition, sauf pour les noms des répertoires d'ensemble de lignes spéciaux tels que « ghost ».</span><span class="sxs-lookup"><span data-stu-id="c9f62-117">The name of a rowset directory is the partition ID of the partition, except for the special rowset directory names such as 'ghost'.</span></span> <span data-ttu-id="c9f62-118">Si un nom de répertoire d'ensemble de lignes ne peut pas être converti en ID de partition, le répertoire n'est pas un répertoire d'ensemble de lignes valide.</span><span class="sxs-lookup"><span data-stu-id="c9f62-118">If a rowset directory name cannot be converted to a partition ID, the directory is not a valid rowset directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9f62-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9f62-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="c9f62-120">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="c9f62-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="c9f62-121">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="c9f62-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="c9f62-122">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="c9f62-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="c9f62-123">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="c9f62-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="c9f62-124">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="c9f62-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="c9f62-125">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="c9f62-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="c9f62-126">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="c9f62-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="c9f62-127">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="c9f62-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="c9f62-128">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="c9f62-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="c9f62-129">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="c9f62-129">Restore from Backup</span></span>  
 <span data-ttu-id="c9f62-130">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c9f62-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="c9f62-131">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="c9f62-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="c9f62-132">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="c9f62-132">Not applicable.</span></span> <span data-ttu-id="c9f62-133">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="c9f62-133">This error cannot be repaired.</span></span> <span data-ttu-id="c9f62-134">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9f62-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
