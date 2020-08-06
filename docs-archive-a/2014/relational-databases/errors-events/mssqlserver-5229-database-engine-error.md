---
title: MSSQLSERVER_5229 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5229 (Database Engine error)
ms.assetid: 0d9e50da-4f42-4b3a-bc84-daf05cf0e0e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 12cc4631dec430b9c4ad63f06fa20819ba3d82ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696864"
---
# <a name="mssqlserver_5229"></a><span data-ttu-id="a9723-102">MSSQLSERVER_5229</span><span class="sxs-lookup"><span data-stu-id="a9723-102">MSSQLSERVER_5229</span></span>
    
## <a name="details"></a><span data-ttu-id="a9723-103">Détails</span><span class="sxs-lookup"><span data-stu-id="a9723-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9723-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="a9723-104">Product Name</span></span>|<span data-ttu-id="a9723-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9723-105">SQL Server</span></span>|  
|<span data-ttu-id="a9723-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="a9723-106">Event ID</span></span>|<span data-ttu-id="a9723-107">5229</span><span class="sxs-lookup"><span data-stu-id="a9723-107">5229</span></span>|  
|<span data-ttu-id="a9723-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="a9723-108">Event Source</span></span>|<span data-ttu-id="a9723-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a9723-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a9723-110">Composant</span><span class="sxs-lookup"><span data-stu-id="a9723-110">Component</span></span>|<span data-ttu-id="a9723-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a9723-111">SQLEngine</span></span>|  
|<span data-ttu-id="a9723-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="a9723-112">Symbolic Name</span></span>|<span data-ttu-id="a9723-113">DBCC4_ANTIMATTER_IN_HEAP_OR_CLUSTERED_INDEX</span><span class="sxs-lookup"><span data-stu-id="a9723-113">DBCC4_ANTIMATTER_IN_HEAP_OR_CLUSTERED_INDEX</span></span>|  
|<span data-ttu-id="a9723-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="a9723-114">Message Text</span></span>|<span data-ttu-id="a9723-115">Erreur de table, ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE) ; il existe une colonne « antimatière », mais il ne s’agit pas d’un index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="a9723-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) contains an anti-matter column, but is not a nonclustered index.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a9723-116">Explication</span><span class="sxs-lookup"><span data-stu-id="a9723-116">Explanation</span></span>  
 <span data-ttu-id="a9723-117">Un segment de mémoire ou un index cluster contient une colonne « antimatière » alors qu'il ne devrait pas.</span><span class="sxs-lookup"><span data-stu-id="a9723-117">A heap or clustered index contains an antimatter column, but should not.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9723-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a9723-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a9723-119">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="a9723-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a9723-120">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="a9723-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a9723-121">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="a9723-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a9723-122">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="a9723-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a9723-123">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="a9723-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a9723-124">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="a9723-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a9723-125">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="a9723-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a9723-126">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="a9723-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a9723-127">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="a9723-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a9723-128">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a9723-128">Restore from Backup</span></span>  
 <span data-ttu-id="a9723-129">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a9723-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a9723-130">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a9723-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a9723-131">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="a9723-131">Not applicable.</span></span> <span data-ttu-id="a9723-132">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="a9723-132">This error cannot be repaired.</span></span> <span data-ttu-id="a9723-133">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9723-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
