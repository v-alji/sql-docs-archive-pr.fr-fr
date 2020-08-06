---
title: Fichiers gérant les solutions et les projets | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], files
- .ssmssln files
- .ssmsmobileproj files
- .ssmsasproj files
- .ssmssqlproj files
- .sqlsuo files
- files [SQL Server Management Studio], projects
ms.assetid: e19d2859-0b97-4727-ac27-c4c226d86b2f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c94f1f853263c3969961de91ec95b921f5d78ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700560"
---
# <a name="files-that-manage-solutions-and-projects"></a><span data-ttu-id="080b9-102">Fichiers gérant les solutions et les projets</span><span class="sxs-lookup"><span data-stu-id="080b9-102">Files That Manage Solutions and Projects</span></span>
  <span data-ttu-id="080b9-103">Cette rubrique décrit les types de fichiers spécifiques de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="080b9-103">This topic describes the file types that are specific to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="080b9-104">Par défaut, toutes les solutions et leurs projets sont créés dans \Mes documents\SQL Server Management Studio\Projects.</span><span class="sxs-lookup"><span data-stu-id="080b9-104">By default, all solutions and their projects are created in \My Documents\SQL Server Management Studio Projects.</span></span>  
  
## <a name="management-studio-solution-files"></a><span data-ttu-id="080b9-105">Fichiers solutions Management Studio</span><span class="sxs-lookup"><span data-stu-id="080b9-105">Management Studio Solution Files</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="080b9-106">utilise d’autres types de fichiers que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou que [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="080b9-106">uses different file types than [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span></span> <span data-ttu-id="080b9-107">Cela signifie que vous ne pouvez pas ouvrir une solution [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="080b9-107">This means you cannot open a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or in Visual Studio.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="080b9-108">Les fichiers solutions permettent à l’Explorateur de solutions d’afficher une interface graphique pour gérer vos fichiers.</span><span class="sxs-lookup"><span data-stu-id="080b9-108">solution files allow Solution Explorer to display a graphical interface for managing your files.</span></span>  
  
|<span data-ttu-id="080b9-109">Extension</span><span class="sxs-lookup"><span data-stu-id="080b9-109">Extension</span></span>|<span data-ttu-id="080b9-110">Type de fichier</span><span class="sxs-lookup"><span data-stu-id="080b9-110">File type</span></span>|<span data-ttu-id="080b9-111">Description</span><span class="sxs-lookup"><span data-stu-id="080b9-111">Description</span></span>|<span data-ttu-id="080b9-112">Créé par</span><span class="sxs-lookup"><span data-stu-id="080b9-112">Created by</span></span>|  
|---------------|---------------|-----------------|----------------|  
|<span data-ttu-id="080b9-113">.ssmssln</span><span class="sxs-lookup"><span data-stu-id="080b9-113">.ssmssln</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="080b9-114">Objet Solution</span><span class="sxs-lookup"><span data-stu-id="080b9-114">Solution Object</span></span>|<span data-ttu-id="080b9-115">Fournit l’environnement avec des références à l’emplacement sur le disque des projets, des éléments de projets et de la solution [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="080b9-115">Provides the environment with references to the location on disk of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] projects, project items, and solution</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]|  
  
## <a name="management-studio-project-files"></a><span data-ttu-id="080b9-116">Fichiers projet Management Studio</span><span class="sxs-lookup"><span data-stu-id="080b9-116">Management Studio Project Files</span></span>  
 <span data-ttu-id="080b9-117">À l'instar des solutions qui contiennent des fichiers solutions qui gèrent les objets d'une solution, les projets contiennent des fichiers projet.</span><span class="sxs-lookup"><span data-stu-id="080b9-117">In the same way that solutions contain solution files that manage objects in a solution, projects contain project files.</span></span> <span data-ttu-id="080b9-118">Le type de fichier projet créé par [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour un projet dépend du modèle utilisé pour créer le projet.</span><span class="sxs-lookup"><span data-stu-id="080b9-118">The type of project file that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates for a project depends on the template used to create the project.</span></span> <span data-ttu-id="080b9-119">Le tableau ci-dessous décrit le type de fichier créé pour chaque projet.</span><span class="sxs-lookup"><span data-stu-id="080b9-119">The following table describes the type of file created for each project.</span></span>  
  
|<span data-ttu-id="080b9-120">Extension</span><span class="sxs-lookup"><span data-stu-id="080b9-120">Extension</span></span>|<span data-ttu-id="080b9-121">Modèle de projet</span><span class="sxs-lookup"><span data-stu-id="080b9-121">Project template</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="080b9-122">.ssmssqlproj</span><span class="sxs-lookup"><span data-stu-id="080b9-122">.ssmssqlproj</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="080b9-123">Projet de script</span><span class="sxs-lookup"><span data-stu-id="080b9-123">Scripts Project</span></span>|  
|<span data-ttu-id="080b9-124">.ssmsasproj</span><span class="sxs-lookup"><span data-stu-id="080b9-124">.ssmsasproj</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="080b9-125">Projet de script</span><span class="sxs-lookup"><span data-stu-id="080b9-125">Scripts Project</span></span>|  
  
## <a name="location-of-solution-level-files"></a><span data-ttu-id="080b9-126">Emplacement des fichiers de niveau solution</span><span class="sxs-lookup"><span data-stu-id="080b9-126">Location of Solution-Level Files</span></span>  
 <span data-ttu-id="080b9-127">Par défaut, les fichiers de niveau solution sont créés dans le répertoire physique du premier projet créé avec la solution.</span><span class="sxs-lookup"><span data-stu-id="080b9-127">By default, solution-level files are created in the physical directory of the first project that is created with the solution.</span></span> <span data-ttu-id="080b9-128">Vous pouvez spécifier un répertoire pour la solution lors de la création d'une solution ou lors de la création d'un nouveau projet.</span><span class="sxs-lookup"><span data-stu-id="080b9-128">You can specify a directory for the solution by creating a solution, or you can specify the directory when you create a new project.</span></span>  
  
 <span data-ttu-id="080b9-129">Si votre structure de répertoires est identique à la structure logique affichée dans l'Explorateur de solutions, il est plus facile de trouver et de partager les fichiers solutions et projet avec d'autres développeurs.</span><span class="sxs-lookup"><span data-stu-id="080b9-129">If you have a directory structure similar to the logical structure shown in Solution Explorer, project and solution files are easier to locate and share with other developers on a team.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="080b9-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="080b9-130">See Also</span></span>  
 <span data-ttu-id="080b9-131">[Gérer les fichiers avec encodage](manage-files-with-encoding.md) </span><span class="sxs-lookup"><span data-stu-id="080b9-131">[Manage Files with Encoding](manage-files-with-encoding.md) </span></span>  
 <span data-ttu-id="080b9-132">[Fichiers divers](miscellaneous-files.md) </span><span class="sxs-lookup"><span data-stu-id="080b9-132">[Miscellaneous Files](miscellaneous-files.md) </span></span>  
 <span data-ttu-id="080b9-133">[Explorateur de solutions](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="080b9-133">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="080b9-134">[Solutions &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="080b9-134">[Solutions &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="080b9-135">[Projets &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="080b9-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="080b9-136">Contrôle de code source de l'Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="080b9-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
