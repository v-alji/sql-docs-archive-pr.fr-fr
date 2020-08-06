---
title: Unité de sauvegarde (page Général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.general.f1
ms.assetid: c557e37d-319e-4adb-a0c1-94189b15d2ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d73bdf3ce4b88214286b5f232924d811716a247e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601522"
---
# <a name="backup-device-general-page"></a><span data-ttu-id="dcb79-102">Unité de sauvegarde (page Général)</span><span class="sxs-lookup"><span data-stu-id="dcb79-102">Backup Device (General Page)</span></span>
  <span data-ttu-id="dcb79-103">Utilisez la page **Général** pour spécifier ou afficher les propriétés générales d'une unité logique de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dcb79-103">Use the **General** page to specify or view the general properties of a logical backup device.</span></span>  
  
 <span data-ttu-id="dcb79-104">**Pour utiliser SQL Server Management Studio pour afficher le contenu d'une unité de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="dcb79-104">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="dcb79-105">Afficher le contenu d’un fichier ou d’une bande de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-105">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="dcb79-106">Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-106">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="dcb79-107">Options</span><span class="sxs-lookup"><span data-stu-id="dcb79-107">Options</span></span>  
 <span data-ttu-id="dcb79-108">**Nom du périphérique**</span><span class="sxs-lookup"><span data-stu-id="dcb79-108">**Device name**</span></span>  
 <span data-ttu-id="dcb79-109">Permet d'afficher le nom d'une unité logique de sauvegarde existante ou de spécifier le nom d'une nouvelle unité logique de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dcb79-109">View the name of an existing logical backup device or specify the name of a new logical backup device.</span></span>  
  
 <span data-ttu-id="dcb79-110">**Bande**</span><span class="sxs-lookup"><span data-stu-id="dcb79-110">**Tape**</span></span>  
 <span data-ttu-id="dcb79-111">Permet d’afficher ou de sélectionner l’unité à bande de destination dans la liste **Bande** .</span><span class="sxs-lookup"><span data-stu-id="dcb79-111">View or select the destination tape device in the **Tape** list.</span></span> <span data-ttu-id="dcb79-112">Cette option est disponible uniquement si un lecteur de bande est connecté à l’ordinateur qui exécute l’instance du moteur de base de données [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcb79-112">This option is available only if a tape drive is attached to the computer that is running the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcb79-113">Les unités de sauvegarde sur bande situées sur des ordinateurs distants ne sont pas des destinations de sauvegarde valides.</span><span class="sxs-lookup"><span data-stu-id="dcb79-113">Tape backup devices on remote computers are not valid backup destinations.</span></span>  
  
 <span data-ttu-id="dcb79-114">**File**</span><span class="sxs-lookup"><span data-stu-id="dcb79-114">**File**</span></span>  
 <span data-ttu-id="dcb79-115">Permet d'afficher le fichier de destination d'une unité logique de sauvegarde existante ou de spécifier un fichier de destination pour une nouvelle unité logique de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dcb79-115">View the destination file of an existing logical backup device, or specify a destination file for a new logical backup device.</span></span>  
  
-   <span data-ttu-id="dcb79-116">S'il s'agit d'une unité logique de sauvegarde existante, le chemin d'accès du fichier de sauvegarde s'affiche.</span><span class="sxs-lookup"><span data-stu-id="dcb79-116">For an existing logical backup device, the path of the backup file is displayed.</span></span> <span data-ttu-id="dcb79-117">Le champ **Fichier** n'est pas modifiable et le bouton Parcourir n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="dcb79-117">The **File** field is not editable, and the Browse button is unavailable.</span></span>  
  
-   <span data-ttu-id="dcb79-118">S'il s'agit d'une nouvelle unité logique de sauvegarde, vous devez fournir le chemin d'accès du fichier de sauvegarde pour lequel vous définissez l'unité logique de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dcb79-118">For a new logical backup device, you must supply the path of the backup file for which you are defining the logical backup device.</span></span> <span data-ttu-id="dcb79-119">Il n'est pas nécessaire que le fichier existe déjà.</span><span class="sxs-lookup"><span data-stu-id="dcb79-119">This file does not have to exist yet.</span></span>  
  
     <span data-ttu-id="dcb79-120">Pour spécifier un fichier de sauvegarde local, vous pouvez cliquer sur le bouton Parcourir à droite de la zone de texte **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="dcb79-120">To specify a local backup file, you can click the Browse button to the right of the **File** text box.</span></span> <span data-ttu-id="dcb79-121">Ensuite, dans la boîte de dialogue **Rechercher les fichiers de base de données** , naviguez jusqu'aux emplacements des lecteurs fixes de l'ordinateur exécutant l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="dcb79-121">Then, in the **Locate Database Files** dialog box, you can navigate to any location on any of the fixed drives on the computer running the server instance.</span></span> <span data-ttu-id="dcb79-122">Si le fichier de sauvegarde n'existe pas déjà, vous devez taper le nom du fichier que vous souhaitez utiliser dans le champ **Nom de fichier** de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dcb79-122">If the backup file does not exist yet, you must enter the filename you want to use in the **File name** field of that dialog box.</span></span>  
  
     <span data-ttu-id="dcb79-123">Vous pouvez également modifier le champ **Fichier** manuellement pour remplacer le chemin d'accès, le nom de fichier et l'extension par défaut.</span><span class="sxs-lookup"><span data-stu-id="dcb79-123">Alternatively, you can edit the **File** field manually to override the default path, file name, and extension.</span></span> <span data-ttu-id="dcb79-124">Pour spécifier un fichier distant en tant que destination de sauvegarde, tapez son nom complet UNC (Universal Naming Convention).</span><span class="sxs-lookup"><span data-stu-id="dcb79-124">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="dcb79-125">Pour plus d’informations, consultez [Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dcb79-125">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dcb79-126">Étant donné que la sauvegarde de données sur un réseau peut faire l'objet d'erreurs réseau, nous vous recommandons de vérifier l'opération de sauvegarde lorsqu'elle est terminée.</span><span class="sxs-lookup"><span data-stu-id="dcb79-126">Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="dcb79-127">Pour plus d’informations, consultez [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcb79-127">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcb79-128">Notes </span><span class="sxs-lookup"><span data-stu-id="dcb79-128">Remarks</span></span>  
 <span data-ttu-id="dcb79-129">Les sauvegardes sur un jeu comprenant une ou plusieurs unités de sauvegarde constituent un seul jeu de supports.</span><span class="sxs-lookup"><span data-stu-id="dcb79-129">The backups on a set of one or more backup devices compose a single media set.</span></span> <span data-ttu-id="dcb79-130">Un *support de sauvegarde* est un ensemble ordonné de supports de sauvegarde (bandes ou fichiers disques) sur lequel une ou plusieurs opérations de sauvegarde ont été écrites en utilisant un type et un nombre fixes d'unités de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dcb79-130">A *media set* is an ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span> <span data-ttu-id="dcb79-131">Pour plus d’informations sur les supports de sauvegarde, consultez [Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dcb79-131">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="dcb79-132">L'unité physique de sauvegarde correspondant à une unité logique de sauvegarde est initialisée lorsque la première sauvegarde sur support de sauvegarde est écrite sur l'unité logique de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dcb79-132">The physical backup device corresponding to a logical backup device is initialized when the first backup in the media set is written to the logical backup device.</span></span> <span data-ttu-id="dcb79-133">Si l'unité physique de sauvegarde est un fichier qui n'existe pas déjà, il est créé à ce moment-là.</span><span class="sxs-lookup"><span data-stu-id="dcb79-133">If the physical backup device is a file that does not exist yet, it is created at that time.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="dcb79-134">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="dcb79-134">Related Tasks</span></span>  
  
-   [<span data-ttu-id="dcb79-135">Définir une unité de sauvegarde logique pour un fichier de disque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-135">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="dcb79-136">Définir une unité de sauvegarde logique pour un lecteur de bande &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-136">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="dcb79-137">Spécifier un disque ou une bande comme destination de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-137">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="dcb79-138">Supprimer une unité de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-138">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="dcb79-139">Définir la date d’expiration d’une sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-139">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="dcb79-140">Afficher le contenu d’un fichier ou d’une bande de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-140">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="dcb79-141">Afficher les fichiers de données et les fichiers journaux dans un jeu de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-141">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="dcb79-142">Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-142">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="dcb79-143">Restaurer une sauvegarde à partir d’une unité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-143">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="dcb79-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dcb79-144">See Also</span></span>  
 <span data-ttu-id="dcb79-145">[Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dcb79-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="dcb79-146">Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dcb79-146">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
