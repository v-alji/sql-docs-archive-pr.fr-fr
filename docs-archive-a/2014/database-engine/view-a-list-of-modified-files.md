---
title: Afficher la liste des fichiers modifiés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckinWindow
helpviewer_keywords:
- listing modified files
- modified files list [SQL Server]
- checking in files
ms.assetid: 1b053719-8500-4300-a169-fffca5801dd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a2899ab9889908089d17b3c929e7bf4b2dfe2185
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612459"
---
# <a name="view-a-list-of-modified-files"></a><span data-ttu-id="f2fad-102">Afficher une liste de fichiers modifiés</span><span class="sxs-lookup"><span data-stu-id="f2fad-102">View a List of Modified Files</span></span>
  <span data-ttu-id="f2fad-103">Vous pouvez utiliser la fenêtre **archivages en attente** pour afficher à tout moment une liste des fichiers extraits dans la solution actuelle et pour archiver ces fichiers avec un seul clic de bouton.</span><span class="sxs-lookup"><span data-stu-id="f2fad-103">You can use the **Pending Checkins** window to display at all times a list of the checked-out files in the current solution, and to check in these files with a single button click.</span></span>  
  
### <a name="to-view-a-list-of-modified-files"></a><span data-ttu-id="f2fad-104">Pour afficher une liste de fichiers modifiés</span><span class="sxs-lookup"><span data-stu-id="f2fad-104">To view a list of modified files</span></span>  
  
1.  <span data-ttu-id="f2fad-105">Dans le menu **affichage** , cliquez sur **archivages en attente**.</span><span class="sxs-lookup"><span data-stu-id="f2fad-105">On the **View** menu, click **Pending Checkins**.</span></span>  
  
2.  <span data-ttu-id="f2fad-106">Pour archiver les fichiers sélectionnés, cliquez sur **Archiver**.</span><span class="sxs-lookup"><span data-stu-id="f2fad-106">To check in the selected files, click **Check In**.</span></span> <span data-ttu-id="f2fad-107">Vous pouvez également ancrer la fenêtre **archivages en attente** sur le côté droit de l' [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environnement afin de pouvoir archiver les fichiers une fois que vous avez fini de travailler.</span><span class="sxs-lookup"><span data-stu-id="f2fad-107">Alternatively, you can dock the **Pending Checkins** window on the right side of the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment so that you can check in the files when you are finished working.</span></span>  
  
     <span data-ttu-id="f2fad-108">**Date d'arrivée**</span><span class="sxs-lookup"><span data-stu-id="f2fad-108">**Check In**</span></span>  
     <span data-ttu-id="f2fad-109">Archive la solution.</span><span class="sxs-lookup"><span data-stu-id="f2fad-109">Checks in the solution.</span></span>  
  
     <span data-ttu-id="f2fad-110">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="f2fad-110">**Comments**</span></span>  
     <span data-ttu-id="f2fad-111">Associe un commentaire de texte simple à l'archivage en attente.</span><span class="sxs-lookup"><span data-stu-id="f2fad-111">Associates a plain text comment with the pending check in.</span></span> <span data-ttu-id="f2fad-112">Un commentaire est créé et associé à chaque version d'un projet, et stocké dans la base de données de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="f2fad-112">A comment is created and associated with each version of a project, and stored in the source control database.</span></span>  
  
     <span data-ttu-id="f2fad-113">**Options**</span><span class="sxs-lookup"><span data-stu-id="f2fad-113">**Options**</span></span>  
     <span data-ttu-id="f2fad-114">Spécifie les actions que doit prendre le contrôle de code source lorsque vous cliquez sur le bouton **Archiver** .</span><span class="sxs-lookup"><span data-stu-id="f2fad-114">Specifies the actions that source control should take when you click the **Check In** button.</span></span>  
  
    -   <span data-ttu-id="f2fad-115">**Conserver tous les éléments extraits**</span><span class="sxs-lookup"><span data-stu-id="f2fad-115">**Keep All Checked Out**</span></span>  
  
         <span data-ttu-id="f2fad-116">Spécifie que vos modifications doivent être inscrites sur le fournisseur de contrôle de code source, alors que les fichiers doivent rester extraits.</span><span class="sxs-lookup"><span data-stu-id="f2fad-116">Specifies that your changes should be written to the source control provider but that the files should remain checked out.</span></span>  
  
     <span data-ttu-id="f2fad-117">**Sort**</span><span class="sxs-lookup"><span data-stu-id="f2fad-117">**Sort**</span></span>  
     <span data-ttu-id="f2fad-118">Spécifie l'ordre de tri des colonnes figurant dans la liste Éléments.</span><span class="sxs-lookup"><span data-stu-id="f2fad-118">Specifies the sort order for the columns displayed in the Items list.</span></span>  
  
     <span data-ttu-id="f2fad-119">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="f2fad-119">**Columns**</span></span>  
     <span data-ttu-id="f2fad-120">Affiche la liste des colonnes que vous pouvez ajouter à la liste Éléments de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="f2fad-120">Displays a list of the columns you can add to the window's Items list.</span></span>  
  
     <span data-ttu-id="f2fad-121">**Arborescence**</span><span class="sxs-lookup"><span data-stu-id="f2fad-121">**Tree View**</span></span>  
     <span data-ttu-id="f2fad-122">Affiche la hiérarchie des dossiers et des fichiers pour la solution ou le projet que vous archivez.</span><span class="sxs-lookup"><span data-stu-id="f2fad-122">Displays the folder and file hierarchy for the solution or project you are checking in.</span></span>  
  
     <span data-ttu-id="f2fad-123">**Affichage en 2D**</span><span class="sxs-lookup"><span data-stu-id="f2fad-123">**Flat View**</span></span>  
     <span data-ttu-id="f2fad-124">Affiche les fichiers que vous archivez sous forme de listes en 2D sous leur connexion de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="f2fad-124">Displays the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="f2fad-125">**Comparer les versions**</span><span class="sxs-lookup"><span data-stu-id="f2fad-125">**Compare Versions**</span></span>  
     <span data-ttu-id="f2fad-126">Ouvre la boîte de dialogue **options de différences** de Visual SourceSafe, qui compare un fichier sélectionné dans votre projet d’environnement de développement à tout autre fichier sélectionné et affiche les différences, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="f2fad-126">Opens the Visual SourceSafe **Difference Options** dialog box, which compares a selected file in your development environment project to any other selected file and shows you the differences, if any.</span></span>  
  
     <span data-ttu-id="f2fad-127">**Annuler l'extraction**</span><span class="sxs-lookup"><span data-stu-id="f2fad-127">**Undo checkout**</span></span>  
     <span data-ttu-id="f2fad-128">Annule l’extraction de tous les éléments sélectionnés dans la fenêtre **archivages en attente** .</span><span class="sxs-lookup"><span data-stu-id="f2fad-128">Reverses the checkout of all items selected in the **Pending Checkins** window.</span></span>  
  
     <span data-ttu-id="f2fad-129">**Nom**</span><span class="sxs-lookup"><span data-stu-id="f2fad-129">**Name**</span></span>  
     <span data-ttu-id="f2fad-130">Affiche une liste des éléments à archiver.</span><span class="sxs-lookup"><span data-stu-id="f2fad-130">Displays a list of the items available for check in.</span></span> <span data-ttu-id="f2fad-131">Les cases à cocher situées en regard des éléments concernés sont activées.</span><span class="sxs-lookup"><span data-stu-id="f2fad-131">Items appear with the check box next to them selected.</span></span> <span data-ttu-id="f2fad-132">Si vous ne souhaitez pas archiver un élément donné, désactivez la case à cocher correspondante.</span><span class="sxs-lookup"><span data-stu-id="f2fad-132">If you do not want to check in a particular item, clear the check box next to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2fad-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2fad-133">See Also</span></span>  
 <span data-ttu-id="f2fad-134">[Gérer les archivages](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="f2fad-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="f2fad-135">Gérer les extractions</span><span class="sxs-lookup"><span data-stu-id="f2fad-135">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
