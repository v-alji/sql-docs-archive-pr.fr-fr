---
title: Ajouter de nouveaux éléments à un projet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 76af8692-324f-4f5e-b1a0-d72ca8a107e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: c73c58952c7801b3a0e2c86652feb461292cf37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614283"
---
# <a name="add-new-items-to-a-project"></a><span data-ttu-id="10d12-102">Ajouter de nouveaux éléments à un projet</span><span class="sxs-lookup"><span data-stu-id="10d12-102">Add New Items to a Project</span></span>
  <span data-ttu-id="10d12-103">Vous pouvez ajouter des éléments à un projet pour étendre la fonctionnalité de l'application.</span><span class="sxs-lookup"><span data-stu-id="10d12-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="10d12-104">Un nouvel élément peut être une requête ou une connexion.</span><span class="sxs-lookup"><span data-stu-id="10d12-104">A new item can be a query or a connection.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="10d12-105">comporte deux types de projets : les projets de script [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les projets de script Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="10d12-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="10d12-106">Les éléments que vous pouvez ajouter au projet sont déterminés par le type du projet.</span><span class="sxs-lookup"><span data-stu-id="10d12-106">The project type determines the items that you can add to the project.</span></span> <span data-ttu-id="10d12-107">Par exemple, vous pouvez ajouter une requête [!INCLUDE[tsql](../../includes/tsql-md.md)] (fichier doté de l'extension .sql) à un projet de script [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mais vous ne pouvez pas l'ajouter à un projet de script de services d'analyse.</span><span class="sxs-lookup"><span data-stu-id="10d12-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="10d12-108">ne vous autorise pas à créer des dossiers dans les projets.</span><span class="sxs-lookup"><span data-stu-id="10d12-108">does not allow you to create folders within projects.</span></span> <span data-ttu-id="10d12-109">Pour organiser votre travail, créez plusieurs projets dans la solution.</span><span class="sxs-lookup"><span data-stu-id="10d12-109">To organize your work, create multiple projects within the solution.</span></span>  
  
### <a name="to-add-a-new-query-to-an-existing-project"></a><span data-ttu-id="10d12-110">Pour ajouter une nouvelle requête à un projet existant</span><span class="sxs-lookup"><span data-stu-id="10d12-110">To add a new query to an existing project</span></span>  
  
1.  <span data-ttu-id="10d12-111">Dans l'Explorateur de solutions, sélectionnez un projet cible.</span><span class="sxs-lookup"><span data-stu-id="10d12-111">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="10d12-112">Dans le menu **Projet** , cliquez sur **Ajouter un nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="10d12-112">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="10d12-113">Dans cette boîte de dialogue **Ajouter un nouvel élément** , sélectionnez une catégorie dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="10d12-113">In the **Add New Item** dialog box, select a category in the left pane.</span></span>  
  
4.  <span data-ttu-id="10d12-114">Sélectionnez un modèle de requête dans le volet droit, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="10d12-114">Select a query template in the right pane, and then click **Add**.</span></span> <span data-ttu-id="10d12-115">La nouvelle requête est ajoutée au dossier **Requêtes** du projet.</span><span class="sxs-lookup"><span data-stu-id="10d12-115">The new query is added in the **Queries** folder of the project.</span></span>  
  
5.  <span data-ttu-id="10d12-116">Dans la boîte de dialogue **Se connecter au moteur de base de données** , spécifiez une connexion pour la nouvelle requête, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="10d12-116">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="10d12-117">Vous pouvez cliquer sur **Annuler** dans la boîte de dialogue de connexion si vous ne souhaitez pas associer de connexion à la nouvelle requête.</span><span class="sxs-lookup"><span data-stu-id="10d12-117">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the new query.</span></span>  
  
6.  <span data-ttu-id="10d12-118">Si vous le souhaitez, renommez la requête dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="10d12-118">Rename the query in Solution Explorer if you wish.</span></span>  
  
### <a name="to-add-a-new-connection-to-an-existing-project"></a><span data-ttu-id="10d12-119">Pour ajouter une nouvelle connexion à un projet existant</span><span class="sxs-lookup"><span data-stu-id="10d12-119">To add a new connection to an existing project</span></span>  
  
1.  <span data-ttu-id="10d12-120">Dans l'Explorateur de solutions, sélectionnez un projet cible.</span><span class="sxs-lookup"><span data-stu-id="10d12-120">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="10d12-121">Dans le menu **Projet** , cliquez sur **Ajouter un nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="10d12-121">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="10d12-122">Sélectionnez **Connexion** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="10d12-122">Select **Connection** in the left pane.</span></span>  
  
4.  <span data-ttu-id="10d12-123">Sélectionnez **Nouvelle connexion** dans le volet droit, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="10d12-123">Select **New Connection** in the right pane, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="10d12-124">Dans la boîte de dialogue **Se connecter au moteur de base de données** , spécifiez une connexion pour la nouvelle requête, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="10d12-124">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="10d12-125">La nouvelle connexion est ajoutée au dossier **Connexions** du projet.</span><span class="sxs-lookup"><span data-stu-id="10d12-125">The new connection gets added in the **Connections** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d12-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10d12-126">See Also</span></span>  
 <span data-ttu-id="10d12-127">[Explorateur de solutions](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="10d12-127">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="10d12-128">[Associer des extensions de fichier à un éditeur de code](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span><span class="sxs-lookup"><span data-stu-id="10d12-128">[Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span></span>  
 <span data-ttu-id="10d12-129">[Ajouter des éléments existants à un projet](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="10d12-129">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="10d12-130">Enlever ou supprimer un élément ou un projet</span><span class="sxs-lookup"><span data-stu-id="10d12-130">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
