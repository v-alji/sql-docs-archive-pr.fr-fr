---
title: Général (boîte de dialogue restaurer la base de données) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.restoredbdialog.f1
ms.assetid: 319e7ef5-c9c7-4e50-8690-02a90aed006f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25a49e17227fc2ed6b7b18d2e0964cd8812cbdcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614236"
---
# <a name="general-restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="93d95-102">Général (boîte de dialogue Restaurer la base de données) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="93d95-102">General (Restore Database Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="93d95-103">La page **Général** de la boîte de dialogue **Restaurer la base de données** de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] permet de spécifier le fichier de sauvegarde et les paramètres généraux à utiliser lors de la restauration d'une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93d95-103">Use the **General** page of the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to specify the backup file and general settings to use when restoring an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="93d95-104">Pour chaque fichier de sauvegarde, l'utilisateur qui exécute la commande de restauration doit avoir l'autorisation de lire à partir de l'emplacement de sauvegarde spécifié pour chaque fichier.</span><span class="sxs-lookup"><span data-stu-id="93d95-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="93d95-105">Pour restaurer une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui n'est pas installée sur le serveur, l'utilisateur doit également être un membre du rôle serveur pour cette instance d' [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93d95-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="93d95-106">Pour remplacer une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , l’utilisateur doit avoir l’un des rôles suivants : membre du rôle serveur pour l’instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou membre d’un rôle de base de données avec les autorisations de contrôle total (Administrateur) sur la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="93d95-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93d95-107">Après la restauration d'une base de données existante, l'utilisateur qui a restauré la base de données peut perdre l'accès à la base de données restaurée.</span><span class="sxs-lookup"><span data-stu-id="93d95-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="93d95-108">Cette perte d'accès peut se produire si, au moment de la sauvegarde, l'utilisateur n'était pas un membre du rôle de serveur ou un membre du rôle de base de données avec les autorisations de contrôle total (Administrateur).</span><span class="sxs-lookup"><span data-stu-id="93d95-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="93d95-109">**Pour afficher la page Général dans la boîte de dialogue Restaurer la base de données**</span><span class="sxs-lookup"><span data-stu-id="93d95-109">**To display the General page in the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="93d95-110">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], cliquez avec le bouton droit sur le dossier **Bases de données** d’une instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou sur une base de données dans **l’Explorateur d’objets**, cliquez sur **Restaurer**puis, sous **Sélectionner une page**, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="93d95-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, click **Restore**, and then under **Select a page**, click **General**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="93d95-111">Options</span><span class="sxs-lookup"><span data-stu-id="93d95-111">Options</span></span>  
 <span data-ttu-id="93d95-112">**Script**</span><span class="sxs-lookup"><span data-stu-id="93d95-112">**Script**</span></span>  
 <span data-ttu-id="93d95-113">Crée un script de restauration basé sur les options sélectionnées dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="93d95-113">Creates a restore script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="93d95-114">Le script de restauration est écrit en langage de script [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ASSL).</span><span class="sxs-lookup"><span data-stu-id="93d95-114">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="93d95-115">Par défaut, lorsque vous cliquez sur l'icône **Script** , le script de restauration est envoyé dans une nouvelle fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="93d95-115">Clicking the **Script** icon sends the restore script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="93d95-116">Un menu s'affiche lorsque vous cliquez sur la flèche **Script** . Il vous permet de choisir où envoyer le script de restauration :</span><span class="sxs-lookup"><span data-stu-id="93d95-116">Clicking the **Script** arrow displays a menu that allows you to choose where to send the restore script:</span></span>  
  
-   <span data-ttu-id="93d95-117">Vers une nouvelle fenêtre de requête (par défaut).</span><span class="sxs-lookup"><span data-stu-id="93d95-117">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="93d95-118">Vers un fichier.</span><span class="sxs-lookup"><span data-stu-id="93d95-118">To a file.</span></span>  
  
-   <span data-ttu-id="93d95-119">Vers le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="93d95-119">To the clipboard.</span></span>  
  
-   <span data-ttu-id="93d95-120">Vers un travail.</span><span class="sxs-lookup"><span data-stu-id="93d95-120">To a job.</span></span>  
  
 <span data-ttu-id="93d95-121">**Restaurer la base de données**</span><span class="sxs-lookup"><span data-stu-id="93d95-121">**Restore database**</span></span>  
 <span data-ttu-id="93d95-122">Sélectionnez la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à restaurer.</span><span class="sxs-lookup"><span data-stu-id="93d95-122">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to restore.</span></span>  
  
 <span data-ttu-id="93d95-123">**À partir du fichier de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="93d95-123">**From backup file**</span></span>  
 <span data-ttu-id="93d95-124">Sélectionnez le fichier de sauvegarde à partir duquel restaurer la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] choisie.</span><span class="sxs-lookup"><span data-stu-id="93d95-124">Select the backup file from which to restore the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="93d95-125">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="93d95-125">**Browse**</span></span>  
 <span data-ttu-id="93d95-126">Cliquez sur cette option pour afficher la boîte de dialogue **Rechercher les fichiers de base de données** et sélectionner le chemin et le nom du fichier de sauvegarde à utiliser.</span><span class="sxs-lookup"><span data-stu-id="93d95-126">Click to display the **Locate Database Files** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="93d95-127">Pour plus d’informations sur la boîte de dialogue **Rechercher les fichiers de base de données**, consultez [Boîte de dialogue Rechercher les fichiers de base de données &#40;Analysis Services - Données multidimensionnelles&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="93d95-127">For more information about the **Locate Database Files** dialog box, see [Locate Database Files Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="93d95-128">**Autoriser le remplacement de la base de données**</span><span class="sxs-lookup"><span data-stu-id="93d95-128">**Allow database overwrite**</span></span>  
 <span data-ttu-id="93d95-129">Sélectionnez cette option pour autoriser [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à restaurer le contenu du fichier de sauvegarde sélectionné sur les objets existants dans la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] choisie.</span><span class="sxs-lookup"><span data-stu-id="93d95-129">Select to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to restore the contents of the selected backup file over any existing objects in the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="93d95-130">**Inclure des informations sur la sécurité**</span><span class="sxs-lookup"><span data-stu-id="93d95-130">**Include security information**</span></span>  
 <span data-ttu-id="93d95-131">Sélectionnez cette option pour copier les informations sur la sécurité stockées dans le fichier de sauvegarde vers la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93d95-131">Select to copy any security information stored in the backup file to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="93d95-132">Lorsque cette option est sélectionnée, vous pouvez choisir la quantité d'informations sur la sécurité dans la liste déroulante activée par l'option.</span><span class="sxs-lookup"><span data-stu-id="93d95-132">If this option is selected, you can choose the amount of security information from the drop-down list enabled by selecting this option.</span></span> <span data-ttu-id="93d95-133">Les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="93d95-133">The following options are available:</span></span>  
  
|<span data-ttu-id="93d95-134">Option</span><span class="sxs-lookup"><span data-stu-id="93d95-134">Option</span></span>|<span data-ttu-id="93d95-135">Description</span><span class="sxs-lookup"><span data-stu-id="93d95-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="93d95-136">**Copier tout**</span><span class="sxs-lookup"><span data-stu-id="93d95-136">**Copy All**</span></span>|<span data-ttu-id="93d95-137">Restaure les rôles de base de données contenus dans le fichier de sauvegarde, ainsi que les comptes d'utilisateurs associés aux rôles.</span><span class="sxs-lookup"><span data-stu-id="93d95-137">Restores the database roles contained in the backup file, as well as the user accounts associated with the roles.</span></span>|  
|<span data-ttu-id="93d95-138">**Ignorer l'appartenance**</span><span class="sxs-lookup"><span data-stu-id="93d95-138">**Skip Membership**</span></span>|<span data-ttu-id="93d95-139">Restaure les rôles de base de données contenus dans le fichier de sauvegarde, sans restaurer les comptes d'utilisateurs associés aux rôles.</span><span class="sxs-lookup"><span data-stu-id="93d95-139">Restores the database roles contained in the backup file, but does not restore the user accounts associated with the roles.</span></span>|  
  
 <span data-ttu-id="93d95-140">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="93d95-140">**Password**</span></span>  
 <span data-ttu-id="93d95-141">Si le fichier de sauvegarde est chiffré, tapez le mot de passe utilisé lors de son chiffrement.</span><span class="sxs-lookup"><span data-stu-id="93d95-141">If the backup file is encrypted, type the password used to encrypt the backup file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d95-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93d95-142">See Also</span></span>  
 <span data-ttu-id="93d95-143">[Boîte de dialogue restaurer la base de données &#40;Analysis Services-données multidimensionnelles&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="93d95-143">[Restore Database Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="93d95-144">[Boîte de dialogue partitions &#40;boîte de dialogue restaurer la base de données&#41; &#40;Analysis Services-données multidimensionnelles&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="93d95-144">[Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="93d95-145">Sauvegarde et restauration de bases de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="93d95-145">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
