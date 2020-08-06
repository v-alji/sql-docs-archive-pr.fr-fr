---
title: Solutions (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- solutions [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d06a8a05-7201-4055-8cf3-21bcb4e82c25
author: stevestein
ms.author: sstein
ms.openlocfilehash: 836d3b3002d72541ad88ae55eac6d951530e0ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603756"
---
# <a name="solutions-sql-server-management-studio"></a><span data-ttu-id="24691-102">Solutions (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="24691-102">Solutions (SQL Server Management Studio)</span></span>
  <span data-ttu-id="24691-103">Une solution [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] est une collection d'un ou plusieurs projets connexes.</span><span class="sxs-lookup"><span data-stu-id="24691-103">A [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution is a collection of one or more related projects.</span></span> <span data-ttu-id="24691-104">Les projets sont des conteneurs que les développeurs utilisent pour organiser des fichiers associés, tels que des ensembles de scripts d'administration couramment utilisés.</span><span class="sxs-lookup"><span data-stu-id="24691-104">Projects are containers that developers use to organize related files, such as sets of commonly used administration scripts.</span></span>  
  
## <a name="solution-overview"></a><span data-ttu-id="24691-105">Vue d'ensemble de la solution</span><span class="sxs-lookup"><span data-stu-id="24691-105">Solution Overview</span></span>  
 <span data-ttu-id="24691-106">Vous pouvez utiliser [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] en tant que plateforme de développement de scripts pour le [!INCLUDE[ssDE](../../includes/ssde-md.md)] et [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24691-106">You can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] as a script development platform for [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="24691-107">Utilisez les éditeurs de code de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] pour développer des scripts et des requêtes pour les bases de données relationnelles et multidimensionnelles, et collectez des scripts associés et les requêtes ensemble dans les projets.</span><span class="sxs-lookup"><span data-stu-id="24691-107">Use the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] code editors to develop scripts and queries for relational and multidimensional databases, and collect related scripts and queries together in projects.</span></span>  
  
 <span data-ttu-id="24691-108">Les projets peuvent contenir :</span><span class="sxs-lookup"><span data-stu-id="24691-108">Projects can contain:</span></span>  
  
-   <span data-ttu-id="24691-109">des requêtes et des scripts qui implémentent des processus de production ;</span><span class="sxs-lookup"><span data-stu-id="24691-109">Queries and scripts that implement production processes.</span></span>  
  
-   <span data-ttu-id="24691-110">des informations de connexion et des fichiers utilisés par les requêtes et les scripts.</span><span class="sxs-lookup"><span data-stu-id="24691-110">Connection information and files used by the queries and scripts.</span></span>  
  
 <span data-ttu-id="24691-111">Un ou plusieurs projets associés peuvent être combinés dans une solution.</span><span class="sxs-lookup"><span data-stu-id="24691-111">One or more related projects can be combined in a solution.</span></span> <span data-ttu-id="24691-112">Les solutions et les projets peuvent être gérés à l'aide du volet Explorateur de solutions dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24691-112">Solutions and projects can be managed by using the Solution Explorer pane in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="24691-113">Les solutions et projets peuvent être intégrés dans une base de données [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) (ou d'autres fournisseurs tiers de contrôle de code source) pour effectuer le suivi des modifications et la gestion du cycle de vie du développement.</span><span class="sxs-lookup"><span data-stu-id="24691-113">Solutions and projects can be integrated into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) database or other third-party source control providers, for development change tracking and life-cycle management.</span></span>  
  
## <a name="solution-tasks"></a><span data-ttu-id="24691-114">Tâches de solution</span><span class="sxs-lookup"><span data-stu-id="24691-114">Solution Tasks</span></span>  
  
|<span data-ttu-id="24691-115">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="24691-115">Task Description</span></span>|<span data-ttu-id="24691-116">Rubrique</span><span class="sxs-lookup"><span data-stu-id="24691-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="24691-117">Décrit comment créer une nouvelle solution qui peut ensuite être utilisée pour contenir un ou plusieurs projets.</span><span class="sxs-lookup"><span data-stu-id="24691-117">Describes how to create a new solution that can then be used to contain one or more projects.</span></span>|[<span data-ttu-id="24691-118">Créer une solution</span><span class="sxs-lookup"><span data-stu-id="24691-118">Create a New Solution</span></span>](create-a-new-solution.md)|  
|<span data-ttu-id="24691-119">Décrit comment ouvrir une solution existante dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="24691-119">Describes how to open an existing solution in Solution Explorer.</span></span>|[<span data-ttu-id="24691-120">Ouvrir une solution existante</span><span class="sxs-lookup"><span data-stu-id="24691-120">Open an Existing Solution</span></span>](open-an-existing-solution.md)|  
|<span data-ttu-id="24691-121">Décrit comment fermer une solution.</span><span class="sxs-lookup"><span data-stu-id="24691-121">Describes how to close a solution.</span></span>|[<span data-ttu-id="24691-122">Fermer une solution</span><span class="sxs-lookup"><span data-stu-id="24691-122">Close a Solution</span></span>](close-a-solution.md)|  
|<span data-ttu-id="24691-123">Décrit comment supprimer une solution.</span><span class="sxs-lookup"><span data-stu-id="24691-123">Describes how to delete a solution.</span></span>|[<span data-ttu-id="24691-124">Supprimer une solution</span><span class="sxs-lookup"><span data-stu-id="24691-124">Delete a Solution</span></span>](delete-a-solution.md)|  
|<span data-ttu-id="24691-125">Décrit comment copier des éléments entre des projets.</span><span class="sxs-lookup"><span data-stu-id="24691-125">Describes how to copy items between projects.</span></span>|[<span data-ttu-id="24691-126">Copier des éléments d’une solution</span><span class="sxs-lookup"><span data-stu-id="24691-126">Copy Items in a Solution</span></span>](copy-items-in-a-solution.md)|  
|<span data-ttu-id="24691-127">Décrit comment supprimer des éléments dans un projet ou un projet complet.</span><span class="sxs-lookup"><span data-stu-id="24691-127">Describes how to delete items in a project, or an entire project.</span></span>|[<span data-ttu-id="24691-128">Enlever ou supprimer un élément ou un projet</span><span class="sxs-lookup"><span data-stu-id="24691-128">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)|  
|<span data-ttu-id="24691-129">Décrit comment déplacer des éléments entre des projets dans une solution.</span><span class="sxs-lookup"><span data-stu-id="24691-129">Describes how to move items between projects in a solution.</span></span>|[<span data-ttu-id="24691-130">Déplacer des éléments dans une solution</span><span class="sxs-lookup"><span data-stu-id="24691-130">Move Items in a Solution</span></span>](move-items-in-a-solution.md)|  
|<span data-ttu-id="24691-131">Décrit comment renommer une solution ou les éléments de la solution.</span><span class="sxs-lookup"><span data-stu-id="24691-131">Describes how to rename a solution or the items in the solution.</span></span>|[<span data-ttu-id="24691-132">Renommer des solutions et des éléments de projet</span><span class="sxs-lookup"><span data-stu-id="24691-132">Rename Solutions and Project Items</span></span>](rename-solutions-and-project-items.md)|  
  
## <a name="see-also"></a><span data-ttu-id="24691-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24691-133">See Also</span></span>  
 <span data-ttu-id="24691-134">[Explorateur de solutions](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="24691-134">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="24691-135">[Projets &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="24691-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="24691-136">Contrôle de code source de l'Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="24691-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
