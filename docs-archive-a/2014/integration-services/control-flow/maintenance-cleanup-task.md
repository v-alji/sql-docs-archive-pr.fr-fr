---
title: Nettoyage de maintenance, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.maintenancecleanuptask.f1
helpviewer_keywords:
- deleting files
- removing files
- Maintenance Cleanup task
ms.assetid: 73ad3cd6-9a6d-44cf-905f-c56aa658bf42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4d39dd775402adadbe51eaadc530f4feb288ab9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604067"
---
# <a name="maintenance-cleanup-task"></a><span data-ttu-id="161bc-102">Tâche de nettoyage de maintenance</span><span class="sxs-lookup"><span data-stu-id="161bc-102">Maintenance Cleanup Task</span></span>
  <span data-ttu-id="161bc-103">La tâche de nettoyage de maintenance supprime les fichiers associés aux plans de maintenance, notamment des fichiers de sauvegarde de base de données et des rapports créés par les plans de maintenance.</span><span class="sxs-lookup"><span data-stu-id="161bc-103">The Maintenance Cleanup task removes files related to maintenance plans, including database backup files and reports created by maintenance plans.</span></span> <span data-ttu-id="161bc-104">Pour plus d’informations, consultez [Plans de maintenance](../../relational-databases/maintenance-plans/maintenance-plans.md) et [Sauvegarde et restauration des bases de données SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="161bc-104">For more information, see [Maintenance Plans](../../relational-databases/maintenance-plans/maintenance-plans.md) and [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="161bc-105">En utilisant la tâche de nettoyage de maintenance, un package peut supprimer les fichiers de sauvegarde ou les rapports de plan de maintenance sur le serveur spécifié.</span><span class="sxs-lookup"><span data-stu-id="161bc-105">By using the Maintenance Cleanup task, a package can remove the backup files or maintenance plan reports on the specified server.</span></span> <span data-ttu-id="161bc-106">La tâche de nettoyage de maintenance inclut une option permettant de supprimer un fichier spécifique ou un groupe de fichiers dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="161bc-106">The Maintenance Cleanup task includes an option to remove a specific file or remove a group of files in a folder.</span></span> <span data-ttu-id="161bc-107">Vous pouvez facultativement spécifier l'extension des fichiers à supprimer.</span><span class="sxs-lookup"><span data-stu-id="161bc-107">Optionally you can specify the extension of the files to delete.</span></span>  
  
 <span data-ttu-id="161bc-108">Lorsque vous configurez la tâche de nettoyage de maintenance pour supprimer des fichiers de sauvegarde, l'extension de nom de fichier par défaut est BAK.</span><span class="sxs-lookup"><span data-stu-id="161bc-108">When you configure the Maintenance Cleanup task to remove backup files, the default file name extension is BAK.</span></span> <span data-ttu-id="161bc-109">Pour les fichiers de rapport, l'extension de nom de fichier par défaut est TXT.</span><span class="sxs-lookup"><span data-stu-id="161bc-109">For report files, the default file name extension is TXT.</span></span> <span data-ttu-id="161bc-110">Vous pouvez mettre à jour les extensions en fonction de vos besoins à condition qu'elles ne comportent pas plus de 256 caractères.</span><span class="sxs-lookup"><span data-stu-id="161bc-110">You can update the extensions to suit your needs; the only limitation is that extensions must be less than 256 characters long.</span></span>  
  
 <span data-ttu-id="161bc-111">Il convient généralement de supprimer les anciens fichiers devenus inutiles, et la tâche de nettoyage de maintenance peut être configurée pour supprimer les fichiers ayant atteint un âge spécifié.</span><span class="sxs-lookup"><span data-stu-id="161bc-111">Typically, you want to remove old files that are no longer needed, and the Maintenance Cleanup task can be configured to delete files that have reached a specified age.</span></span> <span data-ttu-id="161bc-112">Par exemple, la tâche peut être configurée pour supprimer les fichiers datant de plus de quatre semaines.</span><span class="sxs-lookup"><span data-stu-id="161bc-112">For example, the task can be configured to delete files that are older than four weeks.</span></span> <span data-ttu-id="161bc-113">Vous pouvez spécifier l'âge des fichiers à supprimer en indiquant des jours, des semaines, des mois ou des années.</span><span class="sxs-lookup"><span data-stu-id="161bc-113">You can specify the age of files to delete by using days, weeks, months, or years.</span></span> <span data-ttu-id="161bc-114">Si vous ne spécifiez pas l'âge minimal des fichiers à supprimer, tous les fichiers du type spécifié sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="161bc-114">If you do not specify the minimum age of files to delete, all files of the specified type are deleted.</span></span>  
  
 <span data-ttu-id="161bc-115">Contrairement aux versions antérieures de la tâche de nettoyage de maintenance, la version [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne supprime pas automatiquement les fichiers dans les sous-répertoires du répertoire spécifié.</span><span class="sxs-lookup"><span data-stu-id="161bc-115">In contrast to earlier versions of the Maintenance Cleanup task, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version of the task does not automatically delete files in the subdirectories of the specified directory.</span></span> <span data-ttu-id="161bc-116">Cette contrainte réduit la surface d'exposition d'une attaque pouvant exploiter la fonctionnalité de la tâche de nettoyage de maintenance pour supprimer des fichiers par malveillance.</span><span class="sxs-lookup"><span data-stu-id="161bc-116">This constraint reduces the surface area of any attack that could exploit the functionality of the Maintenance Cleanup task to delete files maliciously.</span></span> <span data-ttu-id="161bc-117">Pour supprimer les sous-dossiers de premier niveau, vous devez choisir de le faire de manière explicite en activant l’option **Inclure les sous-dossiers de premier niveau** dans la boîte de dialogue **Tâche de nettoyage de maintenance** .</span><span class="sxs-lookup"><span data-stu-id="161bc-117">To delete the first-level subfolders, you must explicitly elect to do this by checking the **Include first-level subfolders** option in the **Maintenance Cleanup Task** dialog box.</span></span>  
  
## <a name="configuration-of-the-maintenance-cleanup-task"></a><span data-ttu-id="161bc-118">Configuration de la tâche de nettoyage de maintenance</span><span class="sxs-lookup"><span data-stu-id="161bc-118">Configuration of the Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="161bc-119">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="161bc-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="161bc-120">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="161bc-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="161bc-121">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="161bc-121">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="161bc-122">Tâche de nettoyage de maintenance &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="161bc-122">Maintenance Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/maintenance-cleanup-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="161bc-123">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="161bc-123">Related Tasks</span></span>  
 <span data-ttu-id="161bc-124">Pour plus d’informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Définir les propriétés d’une tâche ou d’un conteneur](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="161bc-124">For details about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="161bc-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="161bc-125">See Also</span></span>  
 <span data-ttu-id="161bc-126">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="161bc-126">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="161bc-127">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="161bc-127">Control Flow</span></span>](control-flow.md)  
  
  
