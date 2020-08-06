---
title: Sélectionner la destination de la sauvegarde, boîte de dialogue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdest.f1
ms.assetid: f79e824b-1525-45de-8ede-513563af41b6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ffd1d2529dd13e42689bcf168c972d757fb5499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612405"
---
# <a name="select-backup-destination"></a><span data-ttu-id="cf5c5-102">Sélectionner la destination de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="cf5c5-102">Select Backup Destination</span></span>
  <span data-ttu-id="cf5c5-103">Utilisez la boîte de dialogue **Sélectionner la destination de la sauvegarde** pour choisir le périphérique de destination de vos sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-103">Use the **Select Backup Destination** dialog box to select a device as your backup destination.</span></span> <span data-ttu-id="cf5c5-104">La destination de la sauvegarde peut être un disque ou une unité logique de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-104">A backup destination can be either a disk or a logical backup device.</span></span>  
  
 <span data-ttu-id="cf5c5-105">**Pour utiliser SQL Server Management Studio pour sauvegarder une base de données**</span><span class="sxs-lookup"><span data-stu-id="cf5c5-105">**To use SQL Server Management Studio to back up a database**</span></span>  
  
-   [<span data-ttu-id="cf5c5-106">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf5c5-106">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="cf5c5-107">Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf5c5-107">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="cf5c5-108">Sauvegarder des fichiers et des groupes de fichiers &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf5c5-108">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="cf5c5-109">Sauvegarder un journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf5c5-109">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="cf5c5-110">Options</span><span class="sxs-lookup"><span data-stu-id="cf5c5-110">Options</span></span>  
 <span data-ttu-id="cf5c5-111">Les options de cette boîte de dialogue varient selon que vous sélectionnez un disque ou une bande comme destination de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-111">The options of this dialog box depend on whether you are selecting a destination on disk or on tape.</span></span>  
  
 <span data-ttu-id="cf5c5-112">**Destinations sur disque**</span><span class="sxs-lookup"><span data-stu-id="cf5c5-112">**Destination on disk**</span></span>  
 <span data-ttu-id="cf5c5-113">Pour spécifier une destination de sauvegarde, sélectionnez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-113">To specify a backup destination, choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf5c5-114">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="cf5c5-114">**File name**</span></span>|<span data-ttu-id="cf5c5-115">Sélectionnez cette option pour entrer le nom d'un fichier local ou distant de destination de la sauvegarde, dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-115">Choose this option to enter a local or remote file as the backup destination in the text box.</span></span><br /><br /> <span data-ttu-id="cf5c5-116">Pour spécifier un fichier local, cliquez sur le bouton Parcourir à droite de la zone de texte et accédez à un fichier sur les lecteurs fixes de l’ordinateur qui exécute le serveur, ou entrez directement le chemin d’accès complet et le nom de fichier. par exemple, `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak` .</span><span class="sxs-lookup"><span data-stu-id="cf5c5-116">To specify a local file, click the browse button to the right of the text box and navigate to a file on the fixed drives of the computer running the server, or enter the full path and file name directly; for example, `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak`.</span></span><br /><br /> <span data-ttu-id="cf5c5-117">Pour spécifier un fichier distant en tant que destination de sauvegarde, tapez son nom complet UNC (Universal Naming Convention).</span><span class="sxs-lookup"><span data-stu-id="cf5c5-117">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="cf5c5-118">Pour plus d’informations, consultez [Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cf5c5-118">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span><br /><br /> <span data-ttu-id="cf5c5-119">**\*\* Important \*\*** Étant donné que la sauvegarde de données sur un réseau peut faire l’objet d’erreurs réseau, nous vous recommandons de vérifier l’opération de sauvegarde quand elle est terminée.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-119">**\*\* Important \*\*** Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="cf5c5-120">Pour plus d’informations, consultez [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cf5c5-120">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>|  
|<span data-ttu-id="cf5c5-121">**unité de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="cf5c5-121">**Backup device**</span></span>|<span data-ttu-id="cf5c5-122">Choisissez cette option pour sélectionner une unité logique de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-122">Choose this option to select a logical backup device.</span></span><br /><br /> <span data-ttu-id="cf5c5-123">Remarque : Pour plus d’informations sur la création d’une unité de sauvegarde sur disque, consultez [Définir une unité de sauvegarde logique pour un fichier de disque &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cf5c5-123">Note: For information about how to create a disk backup device, see [Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span></span>|  
  
 <span data-ttu-id="cf5c5-124">**Destinations sur bande**</span><span class="sxs-lookup"><span data-stu-id="cf5c5-124">**Destination on tape**</span></span>  
 <span data-ttu-id="cf5c5-125">Indiquez comme destination de la sauvegarde un lecteur de bande connecté physiquement à l’ordinateur serveur (celui qui exécute l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="cf5c5-125">Specify a backup destination on a tape drive physically connected to the computer running the server (that is, the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]).</span></span> <span data-ttu-id="cf5c5-126">Choisissez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-126">Choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf5c5-127">**Lecteur de bande**</span><span class="sxs-lookup"><span data-stu-id="cf5c5-127">**Tape drive**</span></span>|<span data-ttu-id="cf5c5-128">Choisissez cette option pour sélectionner un lecteur de bande choisi comme destination de la sauvegarde dans la liste des lecteurs de bande physiquement connectés à l'ordinateur qui exécute l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-128">Choose this option to select a tape drive as the backup destination from the list of tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="cf5c5-129">Remarque : Les unités de sauvegarde sur bande situées sur des ordinateurs distants ne sont pas des destinations de sauvegarde valides.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-129">Note: Tape backup devices on remote computers are not valid backup destinations.</span></span>|  
|<span data-ttu-id="cf5c5-130">**unité de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="cf5c5-130">**Backup device**</span></span>|<span data-ttu-id="cf5c5-131">Choisissez cette option pour sélectionner une unité logique de sauvegarde existante.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-131">Choose this option to select an existing logical backup device.</span></span> <span data-ttu-id="cf5c5-132">Ces unités logiques de sauvegarde correspondent aux lecteurs de bande connectés physiquement à l'ordinateur exécutant l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="cf5c5-132">These logical backup devices correspond to tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="cf5c5-133">Remarque : Pour plus d’informations sur la création d’une unité de sauvegarde sur bande, consultez [Définir une unité de sauvegarde logique pour un lecteur de bande &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cf5c5-133">Note: For information about how to create a tape backup device, see [Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf5c5-134"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf5c5-134">See Also</span></span>  
 <span data-ttu-id="cf5c5-135">[Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cf5c5-135">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="cf5c5-136">Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf5c5-136">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
