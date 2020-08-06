---
title: Extraire les fichiers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- Visual Studio.SourceControl.CheckOutDialog
helpviewer_keywords:
- checking out files
ms.assetid: cc033727-51bb-4b58-a12b-8977ce61ff56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 151f554742bd6c381b27b58155d3f0e40e9eeb0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611319"
---
# <a name="check-out-files"></a><span data-ttu-id="7f70d-102">Extraire des fichiers</span><span class="sxs-lookup"><span data-stu-id="7f70d-102">Check Out Files</span></span>
  <span data-ttu-id="7f70d-103">À moins que [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ne soit configuré pour autoriser la modification des fichiers archivés, vous devez extraire un fichier avant de pouvoir le modifier.</span><span class="sxs-lookup"><span data-stu-id="7f70d-103">Unless you have configured the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment to permit checked-in files to be edited, you must check out a file before you can modify it.</span></span> <span data-ttu-id="7f70d-104">Lorsque vous procédez à l'extraction d'un fichier, une version du fichier est copiée sur votre disque local et l'attribut de lecture seule du fichier est désactivé.</span><span class="sxs-lookup"><span data-stu-id="7f70d-104">When you check out a file, a copy of the file version is copied to your local disk, and the read-only attribute of the file is removed.</span></span>  
  
 <span data-ttu-id="7f70d-105">Vous pouvez extraire des fichiers en mode exclusif ou en mode partagé.</span><span class="sxs-lookup"><span data-stu-id="7f70d-105">You can check files out either exclusively or in shared mode.</span></span> <span data-ttu-id="7f70d-106">Lorsque vous procédez à l'extraction d'un fichier de manière exclusive, aucun autre utilisateur ne peut l'extraire tant que vous ne l'avez pas archivé.</span><span class="sxs-lookup"><span data-stu-id="7f70d-106">When you check out a file exclusively, no other user can check out the file until you check it in.</span></span> <span data-ttu-id="7f70d-107">Lorsque vous procédez à l'extraction d'un fichier en mode partagé, d'autres utilisateurs peuvent l'extraire et le modifier ; lorsque vous l'archivez, vous pouvez être amené à fusionner la version que vous avez extraite avec les versions créées par d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7f70d-107">When you check out a file in shared mode, other users can check out and modify the file, and when you check it in, you may need to merge the version you have checked out with the versions created by other users.</span></span>  
  
 <span data-ttu-id="7f70d-108">Utilisez la commande **extraire** pour extraire des projets et des fichiers sous contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="7f70d-108">Use the **Check Out** command to check out source-controlled projects and files.</span></span> <span data-ttu-id="7f70d-109">Si vous utilisez cette commande pour extraire une solution ou un projet, tous les fichiers de la solution ou du projet sont également extraits. Toutefois, l’extraction d’un fichier de code source individuel n’entraîne pas l’extraction du projet ou de la solution auxquels il appartient.</span><span class="sxs-lookup"><span data-stu-id="7f70d-109">If you use this command to check out a solution or project, all the files in the solution or project are also checked out. However, checking out an individual source code file does not result in the check out of the project or solution to which it belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f70d-110">Si la [!INCLUDE[msCoName](../includes/msconame-md.md)] base de données Visual SourceSafe pour votre projet est configurée pour autoriser plusieurs extractions et que vous souhaitez extraire un fichier en mode exclusif, vous devez désactiver l’option **autoriser plusieurs extractions** dans la boîte de dialogue Options d’extraction **avancées** avant d’extraire le fichier.</span><span class="sxs-lookup"><span data-stu-id="7f70d-110">If the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database for your project is configured to allow multiple checkouts, and you want to check out a file exclusively, you must clear the **Allow multiple checkouts** option in the **Advanced Check Out Options** dialog box before checking out the file.</span></span> <span data-ttu-id="7f70d-111">Vous devez redémarrer [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour que ce paramètre soit pris en compte.</span><span class="sxs-lookup"><span data-stu-id="7f70d-111">You must restart the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for this setting to take effect.</span></span>  
  
### <a name="to-check-out-a-file"></a><span data-ttu-id="7f70d-112">Pour extraire un fichier</span><span class="sxs-lookup"><span data-stu-id="7f70d-112">To check out a file</span></span>  
  
1.  <span data-ttu-id="7f70d-113">Dans l'Explorateur de solutions, sélectionnez le projet ou le fichier.</span><span class="sxs-lookup"><span data-stu-id="7f70d-113">In Solution Explorer, select the project or file.</span></span>  
  
2.  <span data-ttu-id="7f70d-114">Dans le menu **fichier** , pointez sur **contrôle de code source**, puis cliquez sur **Extraire pour modification**.</span><span class="sxs-lookup"><span data-stu-id="7f70d-114">On the **File** menu, point to **Source Control**, and then click **Check Out for Edit**.</span></span>  
  
3.  <span data-ttu-id="7f70d-115">Si la boîte **de dialogue Extraire pour modification** s’affiche, sélectionnez les éléments souhaités, puis cliquez sur **extraire**. Si vous avez configuré l' [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environnement pour qu’il n’affiche pas la boîte de dialogue **extraire** , les éléments sélectionnés dans Explorateur de solutions et tous les enfants qu’ils peuvent avoir sont immédiatement extraits.</span><span class="sxs-lookup"><span data-stu-id="7f70d-115">If the **Check Out for Edit** dialog box is displayed, select the items you want, and click **Check Out**. If you have configured the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment not to display the **Check Out** dialog box, the items selected in Solution Explorer and any children they might have are checked out immediately.</span></span>  
  
     <span data-ttu-id="7f70d-116">**Vérifier**</span><span class="sxs-lookup"><span data-stu-id="7f70d-116">**Check Out**</span></span>  
     <span data-ttu-id="7f70d-117">Extrait tous les éléments sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="7f70d-117">Check out all the selected items.</span></span>  
  
     <span data-ttu-id="7f70d-118">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="7f70d-118">**Columns**</span></span>  
     <span data-ttu-id="7f70d-119">Identifiez les colonnes à afficher et l'ordre dans lequel elles s'affichent.</span><span class="sxs-lookup"><span data-stu-id="7f70d-119">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="7f70d-120">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="7f70d-120">**Comments**</span></span>  
     <span data-ttu-id="7f70d-121">Ajoutez un commentaire à associer à l'opération d'extraction.</span><span class="sxs-lookup"><span data-stu-id="7f70d-121">Specify a comment to associate with the checkout operation.</span></span>  
  
     <span data-ttu-id="7f70d-122">**Ne pas afficher la boîte de dialogue Extraire lors de l'extraction d'éléments**</span><span class="sxs-lookup"><span data-stu-id="7f70d-122">**Don't Show Check Out dialog box when checking out items**</span></span>  
     <span data-ttu-id="7f70d-123">La boîte de dialogue n'est pas affichée au cours des opérations d'extraction.</span><span class="sxs-lookup"><span data-stu-id="7f70d-123">Suppress the dialog box during checkout operations.</span></span>  
  
     <span data-ttu-id="7f70d-124">**Affichage en 2D**</span><span class="sxs-lookup"><span data-stu-id="7f70d-124">**Flat View**</span></span>  
     <span data-ttu-id="7f70d-125">Affiche les éléments que vous extrayez sous forme de liste en 2D sous leur connexion de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="7f70d-125">Display the items you are checking out as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="7f70d-126">**Modifier**</span><span class="sxs-lookup"><span data-stu-id="7f70d-126">**Edit**</span></span>  
     <span data-ttu-id="7f70d-127">Modifiez un élément sans l’extraire. Le bouton **modifier** s’affiche uniquement si vous avez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configuré pour prendre en charge la modification des fichiers archivés.</span><span class="sxs-lookup"><span data-stu-id="7f70d-127">Modify an item without checking it out. The **Edit** button appears only if you have [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configured to support the editing of checked-in files.</span></span>  
  
     <span data-ttu-id="7f70d-128">**Nom**</span><span class="sxs-lookup"><span data-stu-id="7f70d-128">**Name**</span></span>  
     <span data-ttu-id="7f70d-129">Affiche les noms des éléments disponibles en vue d'une extraction.</span><span class="sxs-lookup"><span data-stu-id="7f70d-129">Displays the names of the items available for checkout.</span></span> <span data-ttu-id="7f70d-130">Les cases à cocher activées indiquent les éléments sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="7f70d-130">Items that are selected appear with check boxes next to them.</span></span> <span data-ttu-id="7f70d-131">Si vous ne souhaitez pas extraire un élément donné, désactivez la case à cocher correspondante.</span><span class="sxs-lookup"><span data-stu-id="7f70d-131">If you do not want to check out a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="7f70d-132">**Options**</span><span class="sxs-lookup"><span data-stu-id="7f70d-132">**Options**</span></span>  
     <span data-ttu-id="7f70d-133">Affiche les options d'extraction spécifiques du plug-in de contrôle de code source quand vous cliquez sur la flèche à droite du bouton.</span><span class="sxs-lookup"><span data-stu-id="7f70d-133">Displays source control plug-in-specific checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="7f70d-134">**Sort**</span><span class="sxs-lookup"><span data-stu-id="7f70d-134">**Sort**</span></span>  
     <span data-ttu-id="7f70d-135">Trie les colonnes affichées.</span><span class="sxs-lookup"><span data-stu-id="7f70d-135">Sort the order of the displayed columns.</span></span>  
  
     <span data-ttu-id="7f70d-136">**Arborescence**</span><span class="sxs-lookup"><span data-stu-id="7f70d-136">**Tree View**</span></span>  
     <span data-ttu-id="7f70d-137">Affiche la hiérarchie de dossiers et de fichiers pour l'élément que vous extrayez.</span><span class="sxs-lookup"><span data-stu-id="7f70d-137">Display the folder and file hierarchy for the item you are checking out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f70d-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f70d-138">See Also</span></span>  
 <span data-ttu-id="7f70d-139">[Modifier les fichiers archivés](../../2014/database-engine/edit-checked-in-files.md) </span><span class="sxs-lookup"><span data-stu-id="7f70d-139">[Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md) </span></span>  
 <span data-ttu-id="7f70d-140">[Extraire automatiquement des fichiers lors de la modification](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span><span class="sxs-lookup"><span data-stu-id="7f70d-140">[Automatically Check Out Files Upon Edit](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span></span>  
 <span data-ttu-id="7f70d-141">[Annulation des extractions](../../2014/database-engine/undo-checkouts.md) </span><span class="sxs-lookup"><span data-stu-id="7f70d-141">[Undo Checkouts](../../2014/database-engine/undo-checkouts.md) </span></span>  
 [<span data-ttu-id="7f70d-142">Gérer les extractions</span><span class="sxs-lookup"><span data-stu-id="7f70d-142">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
