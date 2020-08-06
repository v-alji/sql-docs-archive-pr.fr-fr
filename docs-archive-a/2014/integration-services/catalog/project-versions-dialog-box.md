---
title: Boîte de dialogue Versions du projet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.versions.f1
ms.assetid: a48a387c-2e70-45bc-be2e-26e57a9bb2c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 998dd194c2a056121fd6f7a404e75c7080b85aa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705363"
---
# <a name="project-versions-dialog-box"></a><span data-ttu-id="d5eeb-102">Boîte de dialogue de versions du projet</span><span class="sxs-lookup"><span data-stu-id="d5eeb-102">Project Versions Dialog Box</span></span>
  <span data-ttu-id="d5eeb-103">Utilisez la boîte de dialogue **Versions du projet** pour afficher les versions d'un projet et pour restaurer une version précédente.</span><span class="sxs-lookup"><span data-stu-id="d5eeb-103">Use the **Project Versions** dialog box to view versions of a project and to restore a previous version.</span></span>  
  
 <span data-ttu-id="d5eeb-104">Vous pouvez également afficher les versions antérieures dans la vue [catalog.object_versions &#40;base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) et utiliser la procédure stockée [catalog.restore_project &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) pour les restaurer.</span><span class="sxs-lookup"><span data-stu-id="d5eeb-104">You can also view previous versions in the [catalog.object_versions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) view, and use the [catalog.restore_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) stored procedure to restore previous versions.</span></span>  
  
 <span data-ttu-id="d5eeb-105">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="d5eeb-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="d5eeb-106">Ouvrir la boîte de dialogue Versions du projet</span><span class="sxs-lookup"><span data-stu-id="d5eeb-106">Open the Project Versions dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="d5eeb-107">Restaurer une version de projet</span><span class="sxs-lookup"><span data-stu-id="d5eeb-107">Restore a Project Version</span></span>](#restore)  
  
##  <a name="open-the-project-versions-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="d5eeb-108">Ouvrir la boîte de dialogue Versions du projet</span><span class="sxs-lookup"><span data-stu-id="d5eeb-108">Open the Project Versions dialog box</span></span>  
  
1.  <span data-ttu-id="d5eeb-109">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5eeb-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="d5eeb-110">Autrement dit, connectez-vous à l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5eeb-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="d5eeb-111">Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .</span><span class="sxs-lookup"><span data-stu-id="d5eeb-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="d5eeb-112">Développez le nœud **Catalogues Integration Services** pour afficher le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="d5eeb-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="d5eeb-113">Le nœud **SSISDB** contient un ou plusieurs dossiers, qui contiennent chacun un ou plusieurs projets.</span><span class="sxs-lookup"><span data-stu-id="d5eeb-113">The **SSISDB** node contains one or more folders that each contain one or more projects.</span></span> <span data-ttu-id="d5eeb-114">Développez le dossier qui contient le projet qui vous intéresse.</span><span class="sxs-lookup"><span data-stu-id="d5eeb-114">Expand the folder that contains the project you are interested in.</span></span>  
  
5.  <span data-ttu-id="d5eeb-115">Cliquez avec le bouton droit sur le projet, puis cliquez sur **Versions**.</span><span class="sxs-lookup"><span data-stu-id="d5eeb-115">Right-click the project, and then click **Versions**.</span></span>  
  
 <span data-ttu-id="d5eeb-116">Dans la boîte de dialogue **Versions du projet** , le tableau **Versions** affiche la liste des versions de projet déployées sur le serveur, avec la date et l’heure de déploiement de la version, la date et l’heure de restauration de la version (si elle a été restaurée), la description de la version et un identificateur de version.</span><span class="sxs-lookup"><span data-stu-id="d5eeb-116">In the **Project Versions** dialog box, the **Versions** table displays the list of versions of the project that have been deployed on the server, with the date and time the version was deployed, the date and time the version was restored (if it was restored), the version description, and a version identifier.</span></span> <span data-ttu-id="d5eeb-117">La version active est indiquée par une coche dans la colonne **En cours** du tableau.</span><span class="sxs-lookup"><span data-stu-id="d5eeb-117">The currently active version is indicated with a check mark in the **Current** column of the table.</span></span>  
  
##  <a name="restore-a-project-version"></a><a name="restore"></a> <span data-ttu-id="d5eeb-118">Restaurer une version de projet</span><span class="sxs-lookup"><span data-stu-id="d5eeb-118">Restore a Project Version</span></span>  
 <span data-ttu-id="d5eeb-119">Pour restaurer une version antérieure d'un projet, sélectionnez la version dans le tableau **Versions** , puis cliquez sur **Restaurer la version sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="d5eeb-119">To restore a previous version of a project, select the version in the **Versions** table, and then click **Restore to Selected Version**.</span></span> <span data-ttu-id="d5eeb-120">Le projet est restauré à la version sélectionnée et cette dernière est indiquée par une coche dans la colonne **En cours** du tableau **Versions** .</span><span class="sxs-lookup"><span data-stu-id="d5eeb-120">The project is restored to the selected version and that version is indicated with a check mark in the **Current** column of the **Versions** table.</span></span>  
  
  
