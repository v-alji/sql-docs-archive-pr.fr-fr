---
title: Ajouter des éléments existants à un projet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 084b3879-e96b-45a7-b421-6a4b0db2b92b
author: stevestein
ms.author: sstein
ms.openlocfilehash: cffa683bfa2a2c81c059d887231531f03d5c892b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614284"
---
# <a name="add-existing-items-to-a-project"></a><span data-ttu-id="57684-102">Ajouter des éléments existants à un projet</span><span class="sxs-lookup"><span data-stu-id="57684-102">Add Existing Items to a Project</span></span>
  <span data-ttu-id="57684-103">Vous pouvez ajouter des éléments à un projet pour étendre la fonctionnalité de l'application.</span><span class="sxs-lookup"><span data-stu-id="57684-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="57684-104">Un élément existant peut être une requête ou un fichier divers.</span><span class="sxs-lookup"><span data-stu-id="57684-104">An existing item can be a query or a miscellaneous file.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="57684-105">comporte deux types de projets : les projets de script [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les projets de script Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="57684-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="57684-106">Les fichiers de requête que vous pouvez ajouter au projet sont déterminés par le type du projet.</span><span class="sxs-lookup"><span data-stu-id="57684-106">The project type determines the query files that you can add to the project.</span></span> <span data-ttu-id="57684-107">Par exemple, vous pouvez ajouter une requête [!INCLUDE[tsql](../../includes/tsql-md.md)] (fichier doté de l'extension .sql) à un projet de script [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mais vous ne pouvez pas l'ajouter à un projet de script de services d'analyse.</span><span class="sxs-lookup"><span data-stu-id="57684-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span> <span data-ttu-id="57684-108">Pour associer d’autres extensions de fichier à un type de projet, consultez [associer des extensions de fichier à un éditeur de code](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span><span class="sxs-lookup"><span data-stu-id="57684-108">To associate additional file extensions to a project type, see [Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span></span>  
  
### <a name="to-add-an-existing-query-or-a-miscellaneous-file-to-a-project"></a><span data-ttu-id="57684-109">Pour ajouter une requête existante ou un fichier divers à un projet</span><span class="sxs-lookup"><span data-stu-id="57684-109">To add an existing query or a miscellaneous file to a project</span></span>  
  
1.  <span data-ttu-id="57684-110">Dans l'Explorateur de solutions, sélectionnez un projet cible.</span><span class="sxs-lookup"><span data-stu-id="57684-110">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="57684-111">Dans le menu **Projet** , cliquez sur **Ajouter un élément existant**.</span><span class="sxs-lookup"><span data-stu-id="57684-111">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
     <span data-ttu-id="57684-112">**Look in**</span><span class="sxs-lookup"><span data-stu-id="57684-112">**Look in**</span></span>  
     <span data-ttu-id="57684-113">Recherche les fichiers ou dossiers à ajouter au projet dans cette liste.</span><span class="sxs-lookup"><span data-stu-id="57684-113">Locate the files or folders to add to your project from this list.</span></span> <span data-ttu-id="57684-114">Pour les services Web XML et les applications Web ASP.NET, les fichiers se trouvent sur un serveur Web.</span><span class="sxs-lookup"><span data-stu-id="57684-114">For XML Web services and ASP.NET Web applications, the files are located on the Web server.</span></span>  
  
     <span data-ttu-id="57684-115">**Bureau**</span><span class="sxs-lookup"><span data-stu-id="57684-115">**Desktop**</span></span>  
     <span data-ttu-id="57684-116">Affiche les fichiers et les dossiers situés sur le bureau.</span><span class="sxs-lookup"><span data-stu-id="57684-116">Displays the files and folders located on the desktop.</span></span>  
  
     <span data-ttu-id="57684-117">**Mes Projets**</span><span class="sxs-lookup"><span data-stu-id="57684-117">**My Projects**</span></span>  
     <span data-ttu-id="57684-118">Affiche les fichiers et les dossiers à l’emplacement **Mes projets** par défaut.</span><span class="sxs-lookup"><span data-stu-id="57684-118">Displays the files and folders at the default **My Projects** location.</span></span>  
  
     <span data-ttu-id="57684-119">**Poste de travail**</span><span class="sxs-lookup"><span data-stu-id="57684-119">**My Computer**</span></span>  
     <span data-ttu-id="57684-120">Affiche le contenu du dossier **Poste de travail** .</span><span class="sxs-lookup"><span data-stu-id="57684-120">Displays the contents of your **My Computer** folder.</span></span>  
  
     <span data-ttu-id="57684-121">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="57684-121">**File name**</span></span>  
     <span data-ttu-id="57684-122">Utilisez cette option pour filtrer les fichiers et les dossiers affichés.</span><span class="sxs-lookup"><span data-stu-id="57684-122">Use this option to filter the files and folders that are displayed.</span></span> <span data-ttu-id="57684-123">Entrez une partie ou l'intégralité du nom de fichier servant de filtre. Vous pouvez utiliser l'astérisque (`*`) comme caractère générique.</span><span class="sxs-lookup"><span data-stu-id="57684-123">Enter the full or partial file name on which to filter; use an asterisk (`*`) as a wildcard.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57684-124">Vous pouvez naviguer jusqu’à un emplacement sur le web ou sur le réseau en entrant une URL ou un chemin réseau dans la zone de texte **Nom de fichier** .</span><span class="sxs-lookup"><span data-stu-id="57684-124">Navigate to Web and network locations by entering the URL or network path in the **File name** box.</span></span> <span data-ttu-id="57684-125">Par exemple, **http://mywebsite** affiche les fichiers disponibles à l’emplacement monsiteweb, tandis que **\\\myserver\myshare** affiche les fichiers disponibles à l’emplacement partage sur monserveur.</span><span class="sxs-lookup"><span data-stu-id="57684-125">For example, **http://mywebsite** displays the files available at the mywebsite Web location, and **\\\myserver\myshare** displays the files available at the myshare location on myserver.</span></span>  
  
     <span data-ttu-id="57684-126">**Fichiers de type**</span><span class="sxs-lookup"><span data-stu-id="57684-126">**Files of type**</span></span>  
     <span data-ttu-id="57684-127">Utilisez cette option pour filtrer les fichiers selon leur extension de fichier.</span><span class="sxs-lookup"><span data-stu-id="57684-127">Use this option to filter files based on file extension.</span></span> <span data-ttu-id="57684-128">Chaque produit affiche la liste des filtres par défaut correspondant aux types de fichiers les plus courants.</span><span class="sxs-lookup"><span data-stu-id="57684-128">Each product lists default filters of the most common file types.</span></span>  
  
     <span data-ttu-id="57684-129">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="57684-129">**Add**</span></span>  
     <span data-ttu-id="57684-130">Utilisez ce bouton déroulant pour ajouter l'élément au projet et ouvrez l'élément dans son éditeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="57684-130">Use this drop-down button to add the item to the project and open the item in its default editor.</span></span>  
  
    -   <span data-ttu-id="57684-131">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="57684-131">**Add**</span></span>  
  
         <span data-ttu-id="57684-132">Copie l'élément existant dans le dossier de votre projet sur le disque et ajoute l'élément au projet sélectionné dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="57684-132">Copies the existing item to your project folder on disk and adds the item under the selected project in Solution Explorer.</span></span> <span data-ttu-id="57684-133">Aucune modification apportée à l'élément n'est répercutée à l'emplacement d'origine.</span><span class="sxs-lookup"><span data-stu-id="57684-133">Any changes made to the item are not reflected in the item at the original location.</span></span> <span data-ttu-id="57684-134">Il s'agit de l'éditeur par défaut pour le type de fichier.</span><span class="sxs-lookup"><span data-stu-id="57684-134">This is the default editor for the file type.</span></span>  
  
    -   <span data-ttu-id="57684-135">**Ajouter comme lien**</span><span class="sxs-lookup"><span data-stu-id="57684-135">**Add As Link**</span></span>  
  
         <span data-ttu-id="57684-136">Ajoute le fichier sélectionné au projet et l'ouvre avec l'éditeur par défaut pour le type de fichier.</span><span class="sxs-lookup"><span data-stu-id="57684-136">Adds the selected file to the project and opens it with the default editor for the file type.</span></span> <span data-ttu-id="57684-137">Cette option ouvre le fichier sélectionné à l'origine et ne copie pas le fichier dans le dossier du projet.</span><span class="sxs-lookup"><span data-stu-id="57684-137">This option opens the originally selected file and does not copy the file to the project folder.</span></span>  
  
3.  <span data-ttu-id="57684-138">Si vous ajoutez des fichiers de requête, la boîte de dialogue de connexion vous invite à spécifier une connexion pour la requête.</span><span class="sxs-lookup"><span data-stu-id="57684-138">If you are adding query files, the connection dialog will prompt you to specify a connection for the query.</span></span> <span data-ttu-id="57684-139">Vous pouvez cliquer sur **Annuler** dans la boîte de dialogue de connexion si vous ne souhaitez pas associer de connexion à la requête.</span><span class="sxs-lookup"><span data-stu-id="57684-139">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the query.</span></span>  
  
4.  <span data-ttu-id="57684-140">Le fichier est ajouté au dossier **Requêtes** ou **Fichiers divers** du projet.</span><span class="sxs-lookup"><span data-stu-id="57684-140">The file will be added to the **Queries** or **Miscellaneous Files** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57684-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57684-141">See Also</span></span>  
 <span data-ttu-id="57684-142">[Explorateur de solutions](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="57684-142">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="57684-143">[Ajouter de nouveaux éléments à un projet](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="57684-143">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="57684-144">Enlever ou supprimer un élément ou un projet</span><span class="sxs-lookup"><span data-stu-id="57684-144">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
