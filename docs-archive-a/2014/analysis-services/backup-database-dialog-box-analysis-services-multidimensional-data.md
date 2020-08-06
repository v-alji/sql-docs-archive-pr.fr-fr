---
title: Boîte de dialogue sauvegarder la base de données (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Backup.f1
ms.assetid: 7811ce7d-6c37-4189-bfa6-ef36fb4932db
author: minewiskan
ms.author: owend
ms.openlocfilehash: 48cf094353c53213864dae656af94ae791442105
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602608"
---
# <a name="backup-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="40c65-102">Boîte de dialogue Sauvegarder la base de données (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="40c65-102">Backup Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="40c65-103">Utilisez la boîte de dialogue **Sauvegarder la base de données** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour sauvegarder une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dans un fichier de sauvegarde en utilisant le format de fichier de sauvegarde .abf [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40c65-103">Use the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to back up an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="40c65-104">Pour chaque fichier de sauvegarde, l'utilisateur qui exécute la commande de sauvegarde doit avoir l'autorisation d'écrire dans l'emplacement de sauvegarde spécifié pour chaque fichier.</span><span class="sxs-lookup"><span data-stu-id="40c65-104">For each backup file, the user who runs the backup command must have permission to write to the backup location specified for each file.</span></span> <span data-ttu-id="40c65-105">L’utilisateur doit aussi avoir l’un des rôles suivants : membre d’un rôle serveur pour l’instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou membre d’un rôle de base de données avec les autorisations de contrôle total (Administrateur) sur la base de données à sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="40c65-105">Also, the user must have one of the following roles: a member of a server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be backed up.</span></span>  
  
 <span data-ttu-id="40c65-106">**Pour afficher la boîte de dialogue Sauvegarder la base de données**</span><span class="sxs-lookup"><span data-stu-id="40c65-106">**To display the Backup Database dialog box**</span></span>  
  
-   <span data-ttu-id="40c65-107">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], cliquez avec le bouton droit sur le dossier **Bases de données** d’une instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou sur une base de données dans **l’Explorateur d’objets**, puis cliquez sur **Sauvegarder**.</span><span class="sxs-lookup"><span data-stu-id="40c65-107">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Backup**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="40c65-108">Options</span><span class="sxs-lookup"><span data-stu-id="40c65-108">Options</span></span>  
 <span data-ttu-id="40c65-109">**Script**</span><span class="sxs-lookup"><span data-stu-id="40c65-109">**Script**</span></span>  
 <span data-ttu-id="40c65-110">Crée un script de sauvegarde basé sur les options sélectionnées dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="40c65-110">Creates a backup script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="40c65-111">Le script de restauration est écrit en langage de script [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ASSL).</span><span class="sxs-lookup"><span data-stu-id="40c65-111">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="40c65-112">Par défaut, lorsque vous cliquez sur l'icône **Script** , le script de sauvegarde est envoyé dans une nouvelle fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="40c65-112">Clicking the **Script** icon sends the backup script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="40c65-113">Un menu s'affiche lorsque vous cliquez sur la flèche **Script** . Il vous permet de choisir où envoyer le script de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="40c65-113">Clicking the **Script** arrow displays a menu that allows you to choose where to send the backup script:</span></span>  
  
-   <span data-ttu-id="40c65-114">Vers une nouvelle fenêtre de requête (par défaut).</span><span class="sxs-lookup"><span data-stu-id="40c65-114">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="40c65-115">Vers un fichier.</span><span class="sxs-lookup"><span data-stu-id="40c65-115">To a file.</span></span>  
  
-   <span data-ttu-id="40c65-116">Vers le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="40c65-116">To the clipboard.</span></span>  
  
-   <span data-ttu-id="40c65-117">Vers un travail.</span><span class="sxs-lookup"><span data-stu-id="40c65-117">To a job.</span></span>  
  
 <span data-ttu-id="40c65-118">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="40c65-118">**Database**</span></span>  
 <span data-ttu-id="40c65-119">Affiche le nom de la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="40c65-119">Displays the name of the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="40c65-120">**Fichier de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="40c65-120">**Backup file**</span></span>  
 <span data-ttu-id="40c65-121">Tapez le chemin d'accès complet et le nom du fichier de sauvegarde à utiliser.</span><span class="sxs-lookup"><span data-stu-id="40c65-121">Type the full path and file name of the backup file to use.</span></span>  
  
 <span data-ttu-id="40c65-122">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="40c65-122">**Browse**</span></span>  
 <span data-ttu-id="40c65-123">Cliquez pour afficher la boîte de dialogue **Enregistrer le fichier sous** et sélectionnez le chemin et le nom du fichier de sauvegarde à utiliser.</span><span class="sxs-lookup"><span data-stu-id="40c65-123">Click to display the **Save File As** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="40c65-124">Pour plus d’informations sur la boîte de dialogue **Enregistrer le fichier sous**, consultez [Boîte de dialogue Enregistrer le fichier sous &#40;Analysis Services - Données multidimensionnelles&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="40c65-124">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="40c65-125">**Autoriser le remplacement du fichier**</span><span class="sxs-lookup"><span data-stu-id="40c65-125">**Allow file overwrite**</span></span>  
 <span data-ttu-id="40c65-126">Sélectionnez cette option pour remplacer un fichier de sauvegarde existant ou un fichier de sauvegarde distant, s'il en existe un.</span><span class="sxs-lookup"><span data-stu-id="40c65-126">Select to overwrite an existing backup file or remote backup file, if one exists.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40c65-127">Si cette option n'est pas sélectionnée et que le fichier de sauvegarde défini dans **Fichier de sauvegarde** ou un fichier de sauvegarde distant défini dans **Fichier de sauvegarde distant** existe, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="40c65-127">If this option is not selected and the backup file specified in **Backup file** or a remote backup file specified in **Remote backup file** exists, an error occurs.</span></span>  
  
 <span data-ttu-id="40c65-128">**Appliquer la compression**</span><span class="sxs-lookup"><span data-stu-id="40c65-128">**Apply compression**</span></span>  
 <span data-ttu-id="40c65-129">Sélectionnez cette option pour compresser le contenu du fichier de sauvegarde et, si définis, les fichiers de sauvegarde distants.</span><span class="sxs-lookup"><span data-stu-id="40c65-129">Select to compress the contents of the backup file and, if specified, remote backup files.</span></span>  
  
 <span data-ttu-id="40c65-130">**Chiffrer le fichier de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="40c65-130">**Encrypt backup file**</span></span>  
 <span data-ttu-id="40c65-131">Sélectionnez cette option pour chiffrer le fichier de sauvegarde en utilisant le mot de passe défini dans **Mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="40c65-131">Select to encrypt the backup file using the password supplied in **Password**.</span></span>  
  
 <span data-ttu-id="40c65-132">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="40c65-132">**Password**</span></span>  
 <span data-ttu-id="40c65-133">Tapez le mot de passe à utiliser lors du chiffrement du fichier de sauvegarde, et si définis, des fichiers de sauvegarde distants.</span><span class="sxs-lookup"><span data-stu-id="40c65-133">Type the password to use when encrypting the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40c65-134"> Cette option est activée uniquement si **Chiffrer le fichier de sauvegarde** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="40c65-134">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="40c65-135">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="40c65-135">**Confirm Password**</span></span>  
 <span data-ttu-id="40c65-136">Tapez le mot de passe entré dans **Mot de passe** pour confirmer le mot de passe du fichier de sauvegarde et, s’ils sont spécifiés, des fichiers de sauvegarde distants.</span><span class="sxs-lookup"><span data-stu-id="40c65-136">Type the password entered in **Password** to confirm the password for the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40c65-137"> Cette option est activée uniquement si **Chiffrer le fichier de sauvegarde** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="40c65-137">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="40c65-138">**Partitions distantes de la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="40c65-138">**Backup remote partition(s)**</span></span>  
 <span data-ttu-id="40c65-139">Sélectionnez cette option pour inclure les informations d'emplacement et les données des partitions distantes dans le fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="40c65-139">Select to include location information and data for remote partitions in the backup file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40c65-140">Cette option est activée uniquement si la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sélectionnée utilise des partitions distantes.</span><span class="sxs-lookup"><span data-stu-id="40c65-140">This option is enabled only if the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database uses remote partitions.</span></span>  
  
 <span data-ttu-id="40c65-141">**Emplacement de la sauvegarde de la partition distante**</span><span class="sxs-lookup"><span data-stu-id="40c65-141">**Remote partition backup location**</span></span>  
 <span data-ttu-id="40c65-142">Affiche l'emplacement des partitions distantes associées à la base de données sélectionnée, ainsi que le fichier de sauvegarde distant utilisé pour sauvegarder les données et les métadonnées des partions distantes.</span><span class="sxs-lookup"><span data-stu-id="40c65-142">Displays the location of remote partitions associated with the selected database, as well as the remote backup file used to back up the data and metadata for the remote partitions.</span></span> <span data-ttu-id="40c65-143">Les colonnes suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="40c65-143">The following columns are available:</span></span>  
  
|<span data-ttu-id="40c65-144">Colonne</span><span class="sxs-lookup"><span data-stu-id="40c65-144">Column</span></span>|<span data-ttu-id="40c65-145">Description</span><span class="sxs-lookup"><span data-stu-id="40c65-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="40c65-146">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="40c65-146">**Server**</span></span>|<span data-ttu-id="40c65-147">Affiche l'instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui gère les partitions distantes.</span><span class="sxs-lookup"><span data-stu-id="40c65-147">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that manages the remote partitions.</span></span>|  
|<span data-ttu-id="40c65-148">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="40c65-148">**Database**</span></span>|<span data-ttu-id="40c65-149">Affiche la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui contient les partitions distantes.</span><span class="sxs-lookup"><span data-stu-id="40c65-149">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that contains the remote partitions.</span></span>|  
|<span data-ttu-id="40c65-150">**Liste des partitions**</span><span class="sxs-lookup"><span data-stu-id="40c65-150">**Partition List**</span></span>|<span data-ttu-id="40c65-151">Affiche la liste des partitions distantes contenues dans la base de données affichée dans **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="40c65-151">Displays the list of remote partitions contained by the database displayed in **Database**.</span></span>|  
|<span data-ttu-id="40c65-152">**Fichier de sauvegarde distant**</span><span class="sxs-lookup"><span data-stu-id="40c65-152">**Remote backup file**</span></span>|<span data-ttu-id="40c65-153">Tapez le chemin complet et le nom du fichier de sauvegarde distant à utiliser, ou cliquez sur le bouton représentant des points de suspension (**...**) pour afficher la boîte de dialogue **Enregistrer le fichier sous** et sélectionner le chemin et le nom du fichier de sauvegarde distant à utiliser.</span><span class="sxs-lookup"><span data-stu-id="40c65-153">Type the full path and file name of the remote backup file to use, or click the ellipsis button (**...**) to display the **Save File As** dialog box and select the path and file name of the remote backup file to use.</span></span> <span data-ttu-id="40c65-154">Pour plus d’informations sur la boîte de dialogue **Enregistrer le fichier sous**, consultez [Boîte de dialogue Enregistrer le fichier sous &#40;Analysis Services - Données multidimensionnelles&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="40c65-154">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40c65-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40c65-155">See Also</span></span>  
 <span data-ttu-id="40c65-156">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="40c65-156">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="40c65-157">Sauvegarde et restauration de bases de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="40c65-157">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
