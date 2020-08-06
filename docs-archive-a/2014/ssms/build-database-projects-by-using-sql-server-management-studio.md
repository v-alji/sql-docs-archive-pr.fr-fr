---
title: Créer des projets de base de données à l’aide de SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], database projects
- database projects [SQL Server]
- projects [SQL Server Management Studio], about projects
- projects [SQL Server Management Studio]
ms.assetid: c2e80045-894d-44cf-b65c-e547ed738947
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3ddf3f61e69623716b2987c5c4d849398e822d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599782"
---
# <a name="build-database-projects-by-using-sql-server-management-studio"></a><span data-ttu-id="79abd-102">Créer des projets de base de données à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="79abd-102">Build Database Projects by Using SQL Server Management Studio</span></span>
  <span data-ttu-id="79abd-103">Un projet de script de base de données est un ensemble organisé de scripts, d'informations de connexion et de modèles qui sont tous associés à une base de données ou une partie d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="79abd-103">A database script project is an organized set of scripts, connection information, and templates that are all associated with a database or one part of a database.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="79abd-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fournit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour l’administration et la conception de bases de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dans le contexte d’un projet de script.</span><span class="sxs-lookup"><span data-stu-id="79abd-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provides the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for administering and designing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] databases within the context of a script project.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="79abd-105">inclut des concepteurs, des éditeurs, des guides et des assistants pour aider les utilisateurs lors du développement, du déploiement et de la gestion de bases de données.</span><span class="sxs-lookup"><span data-stu-id="79abd-105">includes designers, editors, guides and wizards to assist users in developing, deploying and maintaining databases.</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="79abd-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="79abd-106">SQL Server Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="79abd-107">est une suite d’outils d’administration pour la gestion des composants appartenant à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79abd-107">is a suite of administrative tools for managing the components belonging to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="79abd-108">Cet environnement intégré permet aux utilisateurs d'effectuer de nombreuses tâches, telles que la sauvegarde de données, l'édition de requêtes et l'automatisation de fonctions courantes, au sein d'une même interface.</span><span class="sxs-lookup"><span data-stu-id="79abd-108">This integrated environment allows users to perform a variety of tasks, such as backing up data, editing queries, and automating common functions within a single interface.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="79abd-109">propose les outils suivants :</span><span class="sxs-lookup"><span data-stu-id="79abd-109">includes the following tools:</span></span>  
  
-   <span data-ttu-id="79abd-110">L'Éditeur de code, qui est un éditeur de scripts très fourni pour l'écriture et l'édition de scripts.</span><span class="sxs-lookup"><span data-stu-id="79abd-110">Code Editor is a rich script editor for writing and editing scripts.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="79abd-111">fournit quatre versions de l’Éditeur de code : l’Éditeur de requête de [!INCLUDE[ssDE](../includes/ssde-md.md)] pour les scripts [!INCLUDE[tsql](../includes/tsql-md.md)] , l’Éditeur de requête DMX, l’Éditeur de requête MDX et l’Éditeur de requête XML/A.</span><span class="sxs-lookup"><span data-stu-id="79abd-111">provides four versions of the Code Editor; the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor for [!INCLUDE[tsql](../includes/tsql-md.md)] scripts, the DMX Query Editor, the MDX Query Editor, and the XML/A Query Editor.</span></span>  
  
-   <span data-ttu-id="79abd-112">L'Explorateur d'objets pour la localisation, la modification, l'écriture de script ou l'exécution d'objets appartenant aux instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79abd-112">Object Explorer for locating, modifying, scripting or running objects belonging to instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="79abd-113">L'Explorateur de modèles pour la localisation et l'écriture de scripts de modèles.</span><span class="sxs-lookup"><span data-stu-id="79abd-113">Template Explorer for locating and scripting templates.</span></span>  
  
-   <span data-ttu-id="79abd-114">L'Explorateur de solutions pour l'organisation et le stockage de scripts associés en tant que parties d'un projet.</span><span class="sxs-lookup"><span data-stu-id="79abd-114">Solution Explorer for organizing and storing related scripts as parts of a project.</span></span>  
  
-   <span data-ttu-id="79abd-115">La fenêtre Propriétés pour l'affichage des propriétés actuelles des objets sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="79abd-115">Properties Window for displaying the current properties of selected objects.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="79abd-116">prend en charge des processus de travail efficaces en fournissant :</span><span class="sxs-lookup"><span data-stu-id="79abd-116">supports efficient work processes by providing:</span></span>  
  
-   <span data-ttu-id="79abd-117">L'accès déconnecté.</span><span class="sxs-lookup"><span data-stu-id="79abd-117">Disconnected access.</span></span> <span data-ttu-id="79abd-118">Vous pouvez écrire et éditer des scripts sans vous connecter à une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79abd-118">You can write and edit scripts without connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="79abd-119">L'écriture de script à partir de n'importe quelle boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="79abd-119">Scripting from any dialog box.</span></span> <span data-ttu-id="79abd-120">Vous pouvez créer un script à partir de n'importe quelle boîte de dialogue afin de pouvoir lire, modifier, stocker et réutiliser les scripts après les avoir créés.</span><span class="sxs-lookup"><span data-stu-id="79abd-120">You can create a script from any dialog box so that you can read, modify, store and reuse the scripts after you create them.</span></span>  
  
-   <span data-ttu-id="79abd-121">Boîtes de dialogue non modales.</span><span class="sxs-lookup"><span data-stu-id="79abd-121">Nonmodal dialog boxes.</span></span> <span data-ttu-id="79abd-122">Lorsque vous accédez à une boîte de dialogue de l'interface utilisateur, vous pouvez parcourir d'autres ressources dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] sans fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="79abd-122">When you access a UI dialog box you can browse other resources in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] without closing the dialog box.</span></span>  
  
## <a name="solutions-and-script-projects"></a><span data-ttu-id="79abd-123">Solutions et projets de script</span><span class="sxs-lookup"><span data-stu-id="79abd-123">Solutions and Script Projects</span></span>  
 <span data-ttu-id="79abd-124">L'Explorateur de solutions est un utilitaire qui stocke et rouvre les solutions de bases de données.</span><span class="sxs-lookup"><span data-stu-id="79abd-124">Solution Explorer is a utility to store and reopen database solutions.</span></span> <span data-ttu-id="79abd-125">Les solutions organisent les fichiers et projets de script associés.</span><span class="sxs-lookup"><span data-stu-id="79abd-125">Solutions organize related script projects and files.</span></span> <span data-ttu-id="79abd-126">Les projets de script stockent les fichiers de script [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , les modèles SQL, les informations de connexion et d'autres fichiers divers.</span><span class="sxs-lookup"><span data-stu-id="79abd-126">Script projects store [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] script files, SQL templates, connection information and other miscellaneous files.</span></span> <span data-ttu-id="79abd-127">Lorsqu'un script est enregistré dans un projet de script, les utilisateurs peuvent :</span><span class="sxs-lookup"><span data-stu-id="79abd-127">When a script is saved in a script project, users are able to:</span></span>  
  
-   <span data-ttu-id="79abd-128">Maintenir le contrôle des versions sur les scripts.</span><span class="sxs-lookup"><span data-stu-id="79abd-128">Maintain version control on scripts.</span></span>  
  
-   <span data-ttu-id="79abd-129">Stocker les options de résultats avec un script.</span><span class="sxs-lookup"><span data-stu-id="79abd-129">Store results options with a script.</span></span>  
  
-   <span data-ttu-id="79abd-130">Organiser les scripts associés dans un projet de script unique.</span><span class="sxs-lookup"><span data-stu-id="79abd-130">Organize related scripts in a single script project.</span></span>  
  
-   <span data-ttu-id="79abd-131">Enregistrer les informations de connexion avec des scripts.</span><span class="sxs-lookup"><span data-stu-id="79abd-131">Save connection information with scripts.</span></span>  
  
 <span data-ttu-id="79abd-132">L'Explorateur de solutions est un outil destiné aux développeurs qui créent et réutilisent des scripts associés à un même projet.</span><span class="sxs-lookup"><span data-stu-id="79abd-132">Solution Explorer is a tool for developers who are creating and reusing scripts that are related to the same project.</span></span> <span data-ttu-id="79abd-133">Si une tâche similaire est requise ultérieurement, vous pouvez réutiliser un groupe de scripts stockés dans un projet.</span><span class="sxs-lookup"><span data-stu-id="79abd-133">If a similar task is required later, you can use group of scripts that were stored in a project.</span></span> <span data-ttu-id="79abd-134">Si vous avez déjà créé des applications avec [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], l’Explorateur de solutions vous semblera très familier.</span><span class="sxs-lookup"><span data-stu-id="79abd-134">If you have created applications by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], you will find Solution Explorer very familiar.</span></span>  
  
 <span data-ttu-id="79abd-135">Une solution est constituée d'un ou plusieurs projets de script.</span><span class="sxs-lookup"><span data-stu-id="79abd-135">A solution consists of one or more script projects.</span></span> <span data-ttu-id="79abd-136">Un projet est constitué d'un ou plusieurs scripts ou connexions.</span><span class="sxs-lookup"><span data-stu-id="79abd-136">A project consists of one or more scripts or connections.</span></span> <span data-ttu-id="79abd-137">Un projet peut également comprendre des fichiers qui ne sont pas des scripts.</span><span class="sxs-lookup"><span data-stu-id="79abd-137">A project may also include nonscript files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79abd-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79abd-138">See Also</span></span>  
 <span data-ttu-id="79abd-139">[Utiliser SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="79abd-139">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="79abd-140">[Éditeurs de texte et de requête &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="79abd-140">[Query and Text Editors &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="79abd-141">Solutions &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="79abd-141">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solution/solutions-sql-server-management-studio.md)  
  
  
