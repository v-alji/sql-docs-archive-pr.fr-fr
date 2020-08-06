---
title: Contenu de l’unité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.bnrdevicecontents.f1
ms.assetid: 95e1902e-8c7a-4830-bdf9-1a6aca414a24
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c904718eca671b1965a95d0d400f3f6fa075b500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604584"
---
# <a name="device-contents-sql-server"></a><span data-ttu-id="bd422-102">Contenu de l'unité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bd422-102">Device Contents (SQL Server)</span></span>
  <span data-ttu-id="bd422-103">Utilisez cette boîte de dialogue pour consulter les informations de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-103">Use this dialog box to view the backup information.</span></span> <span data-ttu-id="bd422-104">Ces informations décrivent le périphérique, le support, le jeu de supports, ainsi que le ou les jeux de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="bd422-105">**Pour utiliser SQL Server Management Studio pour afficher le contenu d'une unité de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="bd422-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="bd422-106">Afficher le contenu d’un fichier ou d’une bande de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd422-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="bd422-107">Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd422-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="bd422-108">Options</span><span class="sxs-lookup"><span data-stu-id="bd422-108">Options</span></span>  
 <span data-ttu-id="bd422-109">**Média**</span><span class="sxs-lookup"><span data-stu-id="bd422-109">**Media**</span></span>  
 <span data-ttu-id="bd422-110">Disque ou jeu de bandes sur lequel sont stockées les informations de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-110">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="bd422-111">**Séquence du support**</span><span class="sxs-lookup"><span data-stu-id="bd422-111">**Media sequence**</span></span>  
 <span data-ttu-id="bd422-112">Répertorie le numéro de séquence du support, le numéro de séquence de la famille et, le cas échéant, l'identificateur du support miroir.</span><span class="sxs-lookup"><span data-stu-id="bd422-112">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="bd422-113">Chaque support de sauvegarde physique est associé à un numéro de séquence de support indiquant l'ordre d'utilisation des supports.</span><span class="sxs-lookup"><span data-stu-id="bd422-113">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="bd422-114">Le support de sauvegarde initial est référencé par le chiffre 1, le deuxième support (la première bande de continuation) par le chiffre 2 et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="bd422-114">The initial backup medium is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="bd422-115">Lors de la restauration du jeu de sauvegarde, les numéros de séquence des supports garantissent que l'opérateur effectuant la restauration monte le bon support dans le bon ordre.</span><span class="sxs-lookup"><span data-stu-id="bd422-115">When the backup set is restored, the media sequence numbers ensure that the operator that restores the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="bd422-116">**Créé le**</span><span class="sxs-lookup"><span data-stu-id="bd422-116">**Created on**</span></span>  
 <span data-ttu-id="bd422-117">Affiche la date de création du support.</span><span class="sxs-lookup"><span data-stu-id="bd422-117">Displays the media date.</span></span>  
  
 <span data-ttu-id="bd422-118">**Support de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="bd422-118">**Media Set**</span></span>  
 <span data-ttu-id="bd422-119">Un support de sauvegarde est une collection ordonnée de supports de sauvegarde dans lesquels une ou plusieurs opérations de sauvegarde ont effectué des écritures en utilisant un nombre constant d'unités de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-119">A media set is an ordered collection of backup media to which one or more backup operations have written using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="bd422-120">**Nom**</span><span class="sxs-lookup"><span data-stu-id="bd422-120">**Name**</span></span>  
 <span data-ttu-id="bd422-121">Affiche le nom du support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-121">Displays the name of the media set.</span></span>  
  
 <span data-ttu-id="bd422-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="bd422-122">**Description**</span></span>  
 <span data-ttu-id="bd422-123">Affiche la description du support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-123">Displays the description media set.</span></span>  
  
 <span data-ttu-id="bd422-124">**Nombre de familles de supports**</span><span class="sxs-lookup"><span data-stu-id="bd422-124">**Media family count**</span></span>  
 <span data-ttu-id="bd422-125">Affiche le nombre de familles de supports.</span><span class="sxs-lookup"><span data-stu-id="bd422-125">Displays the media family count.</span></span> <span data-ttu-id="bd422-126">Chaque support de sauvegarde est une collection comprenant une ou plusieurs familles de supports.</span><span class="sxs-lookup"><span data-stu-id="bd422-126">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="bd422-127">Toutes les opérations effectuées sur une unité de sauvegarde donnée (ou sur un groupe d'unités de sauvegarde miroir) constituent une seule famille de supports.</span><span class="sxs-lookup"><span data-stu-id="bd422-127">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="bd422-128">Chaque support de sauvegarde contient une famille de supports par unité de sauvegarde (ou groupe d'unités miroir) ; par exemple, si un support de sauvegarde utilise deux unités de sauvegarde qui n'ont pas été mises en miroir, le support de sauvegarde contient deux familles de supports.</span><span class="sxs-lookup"><span data-stu-id="bd422-128">Each media set contains one media family per separate device (or group of mirrored devices); for example, if a media set uses two nonmirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="bd422-129">**Jeux de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="bd422-129">**Backup sets**</span></span>  
 <span data-ttu-id="bd422-130">Affiche les informations relatives au(x) jeu(x) de sauvegarde contenus dans les supports.</span><span class="sxs-lookup"><span data-stu-id="bd422-130">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="bd422-131">Un jeu de sauvegarde est le résultat d'une opération de sauvegarde réussie dont le contenu est divisé entre les supports présents dans le jeu d'unités de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-131">A backup set is the result of a successful backup operation whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="bd422-132">En-tête</span><span class="sxs-lookup"><span data-stu-id="bd422-132">Header</span></span>|<span data-ttu-id="bd422-133">Valeurs</span><span class="sxs-lookup"><span data-stu-id="bd422-133">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="bd422-134">**Nom**</span><span class="sxs-lookup"><span data-stu-id="bd422-134">**Name**</span></span>|<span data-ttu-id="bd422-135">Nom du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-135">The name of the backup set.</span></span>|  
|<span data-ttu-id="bd422-136">**Type**</span><span class="sxs-lookup"><span data-stu-id="bd422-136">**Type**</span></span>|<span data-ttu-id="bd422-137">Type de sauvegarde effectuée : Complète, Différentielle ou Journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="bd422-137">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="bd422-138">**Composant**</span><span class="sxs-lookup"><span data-stu-id="bd422-138">**Component**</span></span>|<span data-ttu-id="bd422-139">Composant sauvegardé : Base de données, fichier ou *\<blank>* (pour les journaux des transactions).</span><span class="sxs-lookup"><span data-stu-id="bd422-139">The backed-up component: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="bd422-140">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="bd422-140">**Server**</span></span>|<span data-ttu-id="bd422-141">Nom de l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] qui a effectué l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-141">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="bd422-142">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="bd422-142">**Database**</span></span>|<span data-ttu-id="bd422-143">Le nom de la base de données qui a été sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="bd422-143">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="bd422-144">**Position**</span><span class="sxs-lookup"><span data-stu-id="bd422-144">**Position**</span></span>|<span data-ttu-id="bd422-145">La position du jeu de sauvegarde dans le volume.</span><span class="sxs-lookup"><span data-stu-id="bd422-145">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="bd422-146">**Date**</span><span class="sxs-lookup"><span data-stu-id="bd422-146">**Date**</span></span>|<span data-ttu-id="bd422-147">Date et heure de fin de l'opération de sauvegarde, exprimée d'après les paramètres régionaux du client.</span><span class="sxs-lookup"><span data-stu-id="bd422-147">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="bd422-148">**Taille**</span><span class="sxs-lookup"><span data-stu-id="bd422-148">**Size**</span></span>|<span data-ttu-id="bd422-149">Taille du jeu de sauvegarde, exprimée en octets.</span><span class="sxs-lookup"><span data-stu-id="bd422-149">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="bd422-150">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="bd422-150">**User Name**</span></span>|<span data-ttu-id="bd422-151">Nom de l'utilisateur qui a exécuté l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-151">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="bd422-152">**Expiration**</span><span class="sxs-lookup"><span data-stu-id="bd422-152">**Expiration**</span></span>|<span data-ttu-id="bd422-153">La date et l'heure d'expiration du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bd422-153">The date and time the backup set expires.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd422-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd422-154">See Also</span></span>  
 [<span data-ttu-id="bd422-155">Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd422-155">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
