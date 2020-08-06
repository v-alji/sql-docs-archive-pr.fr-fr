---
title: Explorateur de solutions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- solutions [SQL Server Management Studio], about solutions
- SQL Server Management Studio [SQL Server], items
- items [SQL Server]
ms.assetid: 0df09843-0d4f-4925-bc6c-99265035a0c1
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa312f5e097fa1c59b9ba545709dc964a184c3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603758"
---
# <a name="solution-explorer"></a><span data-ttu-id="d99d8-102">Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="d99d8-102">Solution Explorer</span></span>
  <span data-ttu-id="d99d8-103">Le volet Explorateur de solutions dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fournit des conteneurs appelés projets pour la gestion des éléments, tels que les scripts de base de données, les requêtes, les connexions de données et les fichiers.</span><span class="sxs-lookup"><span data-stu-id="d99d8-103">The Solution Explorer pane in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides containers called projects for managing items such as database scripts, queries, data connections, and files.</span></span> <span data-ttu-id="d99d8-104">Un ou plusieurs projets qui sont liés entre eux peuvent être combinés dans un conteneur appelé solution.</span><span class="sxs-lookup"><span data-stu-id="d99d8-104">One or more projects that are related to each other can be combined in a container called a solution.</span></span>  
  
 <span data-ttu-id="d99d8-105">Une solution contient un ou plusieurs projets, qu'accompagnent les fichiers et les métadonnées qui permettent de définir la solution dans son entier.</span><span class="sxs-lookup"><span data-stu-id="d99d8-105">A solution includes one or more projects, plus files and metadata that help define the solution as a whole.</span></span> <span data-ttu-id="d99d8-106">Un projet est un ensemble de fichiers, qu'accompagnent les métadonnées correspondantes telles que les informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="d99d8-106">A project is a set of files, plus related metadata such as connection information.</span></span> <span data-ttu-id="d99d8-107">Les solutions et les projets contiennent des éléments qui représentent les scripts, les requêtes, les informations de connexion et les fichiers dont vous avez besoin pour créer votre solution de base de données.</span><span class="sxs-lookup"><span data-stu-id="d99d8-107">Solutions and projects contain items that represent the scripts, queries, connection information and files that you need to create your database solution.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="benefits-of-using-solutions"></a><span data-ttu-id="d99d8-108">Avantages de l'utilisation des solutions</span><span class="sxs-lookup"><span data-stu-id="d99d8-108">Benefits of Using Solutions</span></span>  
 <span data-ttu-id="d99d8-109">Utilisez ces conteneurs pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d99d8-109">Use these containers to:</span></span>  
  
-   <span data-ttu-id="d99d8-110">Implémenter le contrôle de code source sur les requêtes et les scripts.</span><span class="sxs-lookup"><span data-stu-id="d99d8-110">Implement source control on queries and scripts.</span></span>  
  
-   <span data-ttu-id="d99d8-111">Gérer les paramètres de votre solution dans son entier ou les paramètres de projets individuels.</span><span class="sxs-lookup"><span data-stu-id="d99d8-111">Manage settings for your solution as a whole or for individual projects.</span></span>  
  
-   <span data-ttu-id="d99d8-112">Gérer les informations de gestion des fichiers tout en vous concentrant sur les éléments composant votre solution de base de données.</span><span class="sxs-lookup"><span data-stu-id="d99d8-112">Handle the details of file management while you focus on items that make up your database solution.</span></span>  
  
-   <span data-ttu-id="d99d8-113">Ajouter des éléments à plusieurs projets de la solution ou à la solution elle-même sans faire référence à l'élément dans chaque projet.</span><span class="sxs-lookup"><span data-stu-id="d99d8-113">Add items that are useful to multiple projects in the solution or to the solution without referencing the item in each project.</span></span>  
  
-   <span data-ttu-id="d99d8-114">Travailler sur des fichiers divers et indépendants des solutions ou des projets.</span><span class="sxs-lookup"><span data-stu-id="d99d8-114">Work on miscellaneous files that are independent from solutions or projects.</span></span>  
  
 <span data-ttu-id="d99d8-115">Les éléments contenus dans les projets dépendent du type de projet et de l'utilisation ou non de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d99d8-115">The items contained in projects depend on the project type and whether you are using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d99d8-116">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="d99d8-116">Related Tasks</span></span>  
 <span data-ttu-id="d99d8-117">Utilisez les rubriques ci-dessous pour commencer à utiliser les solutions SQL Server :</span><span class="sxs-lookup"><span data-stu-id="d99d8-117">Use the following topics to get started with SQL Server Solutions:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d99d8-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="d99d8-118">**Description**</span></span>|<span data-ttu-id="d99d8-119">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="d99d8-119">**Topic**</span></span>|  
|<span data-ttu-id="d99d8-120">Décrit comment collecter un ou plusieurs projets dans une solution.</span><span class="sxs-lookup"><span data-stu-id="d99d8-120">Describes how to collect one or more projects in a solution.</span></span>|[<span data-ttu-id="d99d8-121">Solutions &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d99d8-121">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solutions-sql-server-management-studio.md)|  
|<span data-ttu-id="d99d8-122">Décrit comment créer un projet et ajouter des éléments comme les scripts et les connexions.</span><span class="sxs-lookup"><span data-stu-id="d99d8-122">Describes how to create a project and add items like scripts and connections.</span></span>|[<span data-ttu-id="d99d8-123">Projets &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d99d8-123">Projects &#40;SQL Server Management Studio&#41;</span></span>](projects-sql-server-management-studio.md)|  
|<span data-ttu-id="d99d8-124">Décrit comment intégrer des solutions ou plusieurs projets dans un système de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d99d8-124">Describes how to integrate solutions or individual projects into a source code control system.</span></span>|[<span data-ttu-id="d99d8-125">Contrôle de code source de l'Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="d99d8-125">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)|  
|<span data-ttu-id="d99d8-126">Fournit des informations sur les fichiers utilisés par [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour gérer les solutions et les fichiers.</span><span class="sxs-lookup"><span data-stu-id="d99d8-126">Provides information about the files used by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage solutions and files.</span></span>|[<span data-ttu-id="d99d8-127">Fichiers gérant les solutions et les projets</span><span class="sxs-lookup"><span data-stu-id="d99d8-127">Files That Manage Solutions and Projects</span></span>](files-that-manage-solutions-and-projects.md)|  
  
  
