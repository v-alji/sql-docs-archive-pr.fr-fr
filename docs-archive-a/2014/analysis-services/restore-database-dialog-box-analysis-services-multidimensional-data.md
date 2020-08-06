---
title: Boîte de dialogue restaurer la base de données (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Restore.f1
ms.assetid: a3990d47-55e2-424e-8eac-87edc937e806
author: minewiskan
ms.author: owend
ms.openlocfilehash: f45a41eb10e81e1cfe1100045cc4d00353cb11fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710887"
---
# <a name="restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d5aa4-102">Boîte de dialogue Restaurer la base de données (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="d5aa4-102">Restore Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d5aa4-103">La boîte de dialogue **Restaurer la base de données** de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] permet de restaurer une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à partir d'un fichier de sauvegarde portant l'extension .abf ([!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File).</span><span class="sxs-lookup"><span data-stu-id="d5aa4-103">Use the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database from a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d5aa4-104">Pour chaque fichier de sauvegarde, l'utilisateur qui exécute la commande de restauration doit avoir l'autorisation de lire à partir de l'emplacement de sauvegarde spécifié pour chaque fichier.</span><span class="sxs-lookup"><span data-stu-id="d5aa4-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="d5aa4-105">Pour restaurer une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui n'est pas installée sur le serveur, l'utilisateur doit également être un membre du rôle serveur pour cette instance d' [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5aa4-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="d5aa4-106">Pour remplacer une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , l’utilisateur doit avoir l’un des rôles suivants : membre du rôle serveur pour l’instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou membre d’un rôle de base de données avec les autorisations de contrôle total (Administrateur) sur la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="d5aa4-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5aa4-107">Après la restauration d'une base de données existante, l'utilisateur qui a restauré la base de données peut perdre l'accès à la base de données restaurée.</span><span class="sxs-lookup"><span data-stu-id="d5aa4-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="d5aa4-108">Cette perte d'accès peut se produire si, au moment de la sauvegarde, l'utilisateur n'était pas un membre du rôle de serveur ou un membre du rôle de base de données avec les autorisations de contrôle total (Administrateur).</span><span class="sxs-lookup"><span data-stu-id="d5aa4-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="d5aa4-109">**Pour afficher la boîte de dialogue Restaurer la base de données**</span><span class="sxs-lookup"><span data-stu-id="d5aa4-109">**To display the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="d5aa4-110">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], cliquez avec le bouton droit sur le dossier **Bases de données** d’une instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou sur une base de données dans **l’Explorateur d’objets**, puis cliquez sur **Restaurer**.</span><span class="sxs-lookup"><span data-stu-id="d5aa4-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Restore**.</span></span>  
  
 <span data-ttu-id="d5aa4-111">La boîte de dialogue **Restaurer la base de données** contient les pages suivantes.</span><span class="sxs-lookup"><span data-stu-id="d5aa4-111">The **Restore Database** dialog box contains the following pages.</span></span>  
  
## <a name="pages"></a><span data-ttu-id="d5aa4-112">Pages</span><span class="sxs-lookup"><span data-stu-id="d5aa4-112">Pages</span></span>  
 <span data-ttu-id="d5aa4-113">**Général**</span><span class="sxs-lookup"><span data-stu-id="d5aa4-113">**General**</span></span>  
 <span data-ttu-id="d5aa4-114">Cette page permet de sélectionner la base de données à restaurer, le fichier de sauvegarde, ainsi que les options générales et le mot de passe permettant cette restauration.</span><span class="sxs-lookup"><span data-stu-id="d5aa4-114">Use this page to select the database to restore, the backup file from which to restore the database, as well as the general options and password to use while restoring the database.</span></span> <span data-ttu-id="d5aa4-115">Pour plus d’informations sur cette page, consultez [Général &#40;boîte de dialogue Restaurer la base de données&#41; &#40;Analysis Services - Données multidimensionnelles&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="d5aa4-115">For more information about this page, see [General &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="d5aa4-116">**Partitions**</span><span class="sxs-lookup"><span data-stu-id="d5aa4-116">**Partitions**</span></span>  
 <span data-ttu-id="d5aa4-117">Cette page sert à restaurer les partitions locales vers des emplacements spécifiés, ainsi que restaurer les partitions distantes à partir de fichiers de sauvegarde à distance.</span><span class="sxs-lookup"><span data-stu-id="d5aa4-117">Use this page to restore local partitions to specified locations, and to restore remote partitions from remote backup files.</span></span> <span data-ttu-id="d5aa4-118">Pour plus d’informations sur cette page, consultez [Partitions &#40;boîte de dialogue Restaurer la base de données&#41; &#40;Analysis Services - Données multidimensionnelles&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="d5aa4-118">For more information about this page, see [Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5aa4-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5aa4-119">See Also</span></span>  
 <span data-ttu-id="d5aa4-120">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d5aa4-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d5aa4-121">Sauvegarde et restauration de bases de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d5aa4-121">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
