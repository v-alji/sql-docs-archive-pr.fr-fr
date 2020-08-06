---
title: MSSQLSERVER_7904 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7904 (Database Engine error)
ms.assetid: d047920c-f864-4338-b15f-49820886fbc5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5e7be2e8413bc0267a642360da66a6a9ec0de8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605454"
---
# <a name="mssqlserver_7904"></a><span data-ttu-id="72706-102">MSSQLSERVER_7904</span><span class="sxs-lookup"><span data-stu-id="72706-102">MSSQLSERVER_7904</span></span>
    
## <a name="details"></a><span data-ttu-id="72706-103">Détails</span><span class="sxs-lookup"><span data-stu-id="72706-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="72706-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="72706-104">Product Name</span></span>|<span data-ttu-id="72706-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="72706-105">SQL Server</span></span>|  
|<span data-ttu-id="72706-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="72706-106">Event ID</span></span>|<span data-ttu-id="72706-107">7904</span><span class="sxs-lookup"><span data-stu-id="72706-107">7904</span></span>|  
|<span data-ttu-id="72706-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="72706-108">Event Source</span></span>|<span data-ttu-id="72706-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="72706-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="72706-110">Composant</span><span class="sxs-lookup"><span data-stu-id="72706-110">Component</span></span>|<span data-ttu-id="72706-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="72706-111">SQLEngine</span></span>|  
|<span data-ttu-id="72706-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="72706-112">Symbolic Name</span></span>|<span data-ttu-id="72706-113">DBCC2_FS_MISSING_FILE</span><span class="sxs-lookup"><span data-stu-id="72706-113">DBCC2_FS_MISSING_FILE</span></span>|  
|<span data-ttu-id="72706-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="72706-114">Message Text</span></span>|<span data-ttu-id="72706-115">Erreur de table, le fichier Filestream correspondant à l’ID de colonne C_ID, ROWGUID RG_ID dans l’ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID est introuvable.</span><span class="sxs-lookup"><span data-stu-id="72706-115">Table error: The filestream file for column ID C_ID, ROWGUID RG_ID in object ID O_ID, index ID I_ID, partition ID PN_ID was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="72706-116">Explication</span><span class="sxs-lookup"><span data-stu-id="72706-116">Explanation</span></span>  
 <span data-ttu-id="72706-117">Une valeur de colonne d'une partition ne possède pas de fichier FILESTREAM correspondant dans le répertoire de colonne FILESTREAM correspondant.</span><span class="sxs-lookup"><span data-stu-id="72706-117">A column value of a partition does not have a matching FILESTREAM file in the corresponding FILESTREAM column directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="72706-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="72706-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="72706-119">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="72706-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="72706-120">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="72706-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="72706-121">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="72706-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="72706-122">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="72706-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="72706-123">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="72706-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="72706-124">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="72706-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="72706-125">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="72706-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="72706-126">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="72706-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="72706-127">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="72706-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="72706-128">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="72706-128">Restore from Backup</span></span>  
 <span data-ttu-id="72706-129">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="72706-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="72706-130">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="72706-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="72706-131">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="72706-131">Not applicable.</span></span> <span data-ttu-id="72706-132">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="72706-132">This error cannot be repaired.</span></span> <span data-ttu-id="72706-133">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72706-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
