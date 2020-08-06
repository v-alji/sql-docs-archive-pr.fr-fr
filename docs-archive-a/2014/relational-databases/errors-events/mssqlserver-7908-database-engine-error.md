---
title: MSSQLSERVER_7908 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7908 (Database Engine error)
ms.assetid: 470045b0-ebe9-44a7-b456-480e7a516a2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b80812e0e36e5bed542f7193b7422f2de37720f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605449"
---
# <a name="mssqlserver_7908"></a><span data-ttu-id="bb463-102">MSSQLSERVER_7908</span><span class="sxs-lookup"><span data-stu-id="bb463-102">MSSQLSERVER_7908</span></span>
    
## <a name="details"></a><span data-ttu-id="bb463-103">Détails</span><span class="sxs-lookup"><span data-stu-id="bb463-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb463-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="bb463-104">Product Name</span></span>|<span data-ttu-id="bb463-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bb463-105">SQL Server</span></span>|  
|<span data-ttu-id="bb463-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="bb463-106">Event ID</span></span>|<span data-ttu-id="bb463-107">7908</span><span class="sxs-lookup"><span data-stu-id="bb463-107">7908</span></span>|  
|<span data-ttu-id="bb463-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="bb463-108">Event Source</span></span>|<span data-ttu-id="bb463-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bb463-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bb463-110">Composant</span><span class="sxs-lookup"><span data-stu-id="bb463-110">Component</span></span>|<span data-ttu-id="bb463-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bb463-111">SQLEngine</span></span>|  
|<span data-ttu-id="bb463-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="bb463-112">Symbolic Name</span></span>|<span data-ttu-id="bb463-113">DBCC2_FS_INVALID_COLUMN_LEVEL_FILE</span><span class="sxs-lookup"><span data-stu-id="bb463-113">DBCC2_FS_INVALID_COLUMN_LEVEL_FILE</span></span>|  
|<span data-ttu-id="bb463-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="bb463-114">Message Text</span></span>|<span data-ttu-id="bb463-115">Erreur de table, Le fichier 'FILE' dans l’ID de partition PN_ID n’est pas un fichier Filestream valide.</span><span class="sxs-lookup"><span data-stu-id="bb463-115">Table error: The file 'FILE' in partition ID PN_ID is not a valid Filestream file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bb463-116">Explication</span><span class="sxs-lookup"><span data-stu-id="bb463-116">Explanation</span></span>  
 <span data-ttu-id="bb463-117">Le nom d'un fichier FILESTREAM dans un répertoire de colonnes est un ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="bb463-117">The name of a FILESTREAM file in a column directory is a ROWGUID.</span></span> <span data-ttu-id="bb463-118">Si le nom d'un fichier inclus dans un répertoire de colonnes ne peut pas être converti en ROWGUID, le fichier n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="bb463-118">If a file name in a column directory cannot be converted to a ROWGUID, the file is not a valid file.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bb463-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="bb463-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="bb463-120">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="bb463-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="bb463-121">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="bb463-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="bb463-122">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="bb463-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="bb463-123">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="bb463-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="bb463-124">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="bb463-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="bb463-125">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="bb463-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="bb463-126">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="bb463-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="bb463-127">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="bb463-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="bb463-128">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="bb463-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="bb463-129">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="bb463-129">Restore from Backup</span></span>  
 <span data-ttu-id="bb463-130">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bb463-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="bb463-131">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="bb463-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="bb463-132">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="bb463-132">Not applicable.</span></span> <span data-ttu-id="bb463-133">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="bb463-133">This error cannot be repaired.</span></span> <span data-ttu-id="bb463-134">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb463-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
