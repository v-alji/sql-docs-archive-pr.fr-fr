---
title: Unité de sauvegarde (page Contenu du support) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.contents.f1
ms.assetid: 5fc7bd22-b6d8-4af1-8a58-2e7d0b994d08
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 07204b5e05ce9fc17e6ea23450066f9f58b7cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610689"
---
# <a name="backup-device-media-contents-page"></a><span data-ttu-id="ed6c9-102">Unité de sauvegarde (page Contenu du support)</span><span class="sxs-lookup"><span data-stu-id="ed6c9-102">Backup Device (Media Contents Page)</span></span>
  <span data-ttu-id="ed6c9-103">La boîte de dialogue **Unité de sauvegarde** vous permet  d'afficher les informations de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-103">Use the **Backup Device** dialog box to view the backup information.</span></span> <span data-ttu-id="ed6c9-104">Ces informations décrivent le périphérique, le support, le jeu de supports, ainsi que le ou les jeux de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="ed6c9-105">**Pour utiliser SQL Server Management Studio pour afficher le contenu d'une unité de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="ed6c9-106">Afficher le contenu d’un fichier ou d’une bande de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="ed6c9-107">Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="ed6c9-108">Options</span><span class="sxs-lookup"><span data-stu-id="ed6c9-108">Options</span></span>  
 <span data-ttu-id="ed6c9-109">Affichez des informations sur le support individuel, le support de sauvegarde et les jeux de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-109">View information about the individual media, media set, and backup sets.</span></span>  
  
 <span data-ttu-id="ed6c9-110">**Média**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-110">**Media**</span></span>  
 <span data-ttu-id="ed6c9-111">Disque ou jeu de bandes sur lequel sont stockées les informations de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-111">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="ed6c9-112">**Séquence du support**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-112">**Media sequence**</span></span>  
 <span data-ttu-id="ed6c9-113">Répertorie le numéro de séquence du support, le numéro de séquence de la famille et, le cas échéant, l'identificateur du support miroir.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-113">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="ed6c9-114">Chaque support de sauvegarde physique est associé à un numéro de séquence de support indiquant l'ordre d'utilisation des supports.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-114">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="ed6c9-115">Le support de sauvegarde initial est référencé par le chiffre 1, le deuxième support (la première bande de continuation) par le chiffre 2 et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-115">The initial backup media is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="ed6c9-116">Lorsque le jeu de sauvegarde est restauré, ces numéros de séquence de support garantissent que l'opérateur qui effectue la restauration monte le support approprié dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-116">When the backup set is restored, the media sequence numbers ensure that the operator restoring the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="ed6c9-117">**Créé le**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-117">**Created on**</span></span>  
 <span data-ttu-id="ed6c9-118">Indique la date et l'heure de création du support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-118">Displays the creation date and time of the media set.</span></span>  
  
 <span data-ttu-id="ed6c9-119">**Support de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-119">**Media Set**</span></span>  
 <span data-ttu-id="ed6c9-120">Un support de sauvegarde est une collection ordonnée de supports de sauvegarde dans laquelle une ou plusieurs opérations de sauvegarde ont écrit en utilisant un nombre constant d'unités de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-120">A media set is an ordered collection of backup media to which one or more backup operations have written by using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="ed6c9-121">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-121">**Name**</span></span>  
 <span data-ttu-id="ed6c9-122">Indique le nom du support de sauvegarde, s'il existe.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-122">Displays the name of the media set, if any.</span></span>  
  
 <span data-ttu-id="ed6c9-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-123">**Description**</span></span>  
 <span data-ttu-id="ed6c9-124">Indique la description du support de sauvegarde, s'il existe.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-124">Displays the description of the media set, if any.</span></span>  
  
 <span data-ttu-id="ed6c9-125">**Nombre de familles de supports**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-125">**Media family count**</span></span>  
 <span data-ttu-id="ed6c9-126">Indique le nombre de familles dans le support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-126">Displays the number of families in the media set.</span></span> <span data-ttu-id="ed6c9-127">Chaque support de sauvegarde est une collection comprenant une ou plusieurs familles de supports.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-127">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="ed6c9-128">Toutes les opérations effectuées sur une unité de sauvegarde donnée (ou sur un groupe d'unités de sauvegarde miroir) constituent une seule famille de supports.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-128">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="ed6c9-129">Chaque support de sauvegarde contient une famille de supports par unité distincte (ou groupe d'unités en miroir) ; par exemple, si un support de sauvegarde utilise deux unités de sauvegarde non mises en miroir, il contient deux familles de supports.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-129">Each media set contains one media family per separate device (or group of mirrored devices); for instance, if a media set uses two non-mirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="ed6c9-130">**Jeux de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-130">**Backup sets**</span></span>  
 <span data-ttu-id="ed6c9-131">Affiche les informations relatives au(x) jeu(x) de sauvegarde contenus dans les supports.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-131">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="ed6c9-132">Un jeu de sauvegarde est le résultat d'une opération de sauvegarde réussie, dont le contenu est distribué entre les supports d'un ensemble d'unités de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-132">A backup set is the result of a successful backup operation, whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="ed6c9-133">En-tête</span><span class="sxs-lookup"><span data-stu-id="ed6c9-133">Header</span></span>|<span data-ttu-id="ed6c9-134">Valeurs</span><span class="sxs-lookup"><span data-stu-id="ed6c9-134">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="ed6c9-135">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-135">**Name**</span></span>|<span data-ttu-id="ed6c9-136">Nom du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-136">The name of the backup set.</span></span>|  
|<span data-ttu-id="ed6c9-137">**Type**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-137">**Type**</span></span>|<span data-ttu-id="ed6c9-138">Objet sauvegardé : Base de données, fichier ou *\<blank>* (pour les journaux des transactions).</span><span class="sxs-lookup"><span data-stu-id="ed6c9-138">The backed-up object: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="ed6c9-139">**Composant**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-139">**Component**</span></span>|<span data-ttu-id="ed6c9-140">Type de sauvegarde effectuée : Complète, Différentielle ou Journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-140">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="ed6c9-141">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-141">**Server**</span></span>|<span data-ttu-id="ed6c9-142">Nom de l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] qui a effectué l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-142">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="ed6c9-143">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-143">**Database**</span></span>|<span data-ttu-id="ed6c9-144">Le nom de la base de données qui a été sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-144">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="ed6c9-145">**Position**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-145">**Position**</span></span>|<span data-ttu-id="ed6c9-146">La position du jeu de sauvegarde dans le volume.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-146">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="ed6c9-147">**Date**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-147">**Date**</span></span>|<span data-ttu-id="ed6c9-148">Date et heure de fin de l'opération de sauvegarde, exprimée d'après les paramètres régionaux du client.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-148">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="ed6c9-149">**Taille**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-149">**Size**</span></span>|<span data-ttu-id="ed6c9-150">Taille du jeu de sauvegarde, exprimée en octets.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-150">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="ed6c9-151">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-151">**User Name**</span></span>|<span data-ttu-id="ed6c9-152">Nom de l'utilisateur qui a exécuté l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-152">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="ed6c9-153">**Expiration**</span><span class="sxs-lookup"><span data-stu-id="ed6c9-153">**Expiration**</span></span>|<span data-ttu-id="ed6c9-154">La date et l'heure d'expiration du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-154">The date and time the backup set expires.</span></span>|  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ed6c9-155">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ed6c9-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ed6c9-156">Définir une unité de sauvegarde logique pour un fichier de disque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-156">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="ed6c9-157">Définir une unité de sauvegarde logique pour un lecteur de bande &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-157">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="ed6c9-158">Spécifier un disque ou une bande comme destination de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-158">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="ed6c9-159">Supprimer une unité de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-159">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="ed6c9-160">Définir la date d’expiration d’une sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-160">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="ed6c9-161">Afficher le contenu d’un fichier ou d’une bande de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-161">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="ed6c9-162">Afficher les fichiers de données et les fichiers journaux dans un jeu de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-162">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="ed6c9-163">Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-163">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="ed6c9-164">Restaurer une sauvegarde à partir d’une unité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-164">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed6c9-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed6c9-165">See Also</span></span>  
 <span data-ttu-id="ed6c9-166">[Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ed6c9-166">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="ed6c9-167">Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6c9-167">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
