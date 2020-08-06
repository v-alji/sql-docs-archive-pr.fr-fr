---
title: Archiver des fichiers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckInDialog
helpviewer_keywords:
- checking in files
ms.assetid: 0657a387-8411-4406-bef9-d262a5bfa269
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 070c1dfa5dd057cf777980f7022752a97a4dc84c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611320"
---
# <a name="check-in-files"></a><span data-ttu-id="8ccf1-102">Archiver des fichiers</span><span class="sxs-lookup"><span data-stu-id="8ccf1-102">Check In Files</span></span>
  <span data-ttu-id="8ccf1-103">Pour mettre à la disposition d'autres utilisateurs des fichiers sous contrôle de code source auxquels vous avez apporté des modifications, vous devez archiver ces fichiers dans le contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-103">To make source-controlled files that you have modified available to other users, you must check the files into source control.</span></span> <span data-ttu-id="8ccf1-104">Lorsque vous archivez un fichier, la version que vous archivez s'inscrit dans le fournisseur de contrôle de code source et devient la dernière version de ce fichier.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-104">When you check in a file, the version you check in is written to the source control provider and becomes the latest version of the file.</span></span>  
  
 <span data-ttu-id="8ccf1-105">Vous pouvez utiliser la commande **Archiver** pour archiver les fichiers.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-105">You can use the **Check In** command to check in files.</span></span> <span data-ttu-id="8ccf1-106">Lorsque vous utilisez cette commande pour archiver une solution ou un projet, tous les fichiers figurant dans cette solution ou dans ce projet sont également archivés.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-106">If you use this command to check in a solution or project, all the files in the solution or project are also checked in.</span></span> <span data-ttu-id="8ccf1-107">Lorsque vous archivez un fichier de code source individuel, cela n'entraîne toutefois pas l'archivage du projet ou de la solution dont il fait partie.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-107">However, checking in an individual source code file does not result in the check-in of the project or solution to which it belongs.</span></span>  
  
### <a name="to-check-in-a-file"></a><span data-ttu-id="8ccf1-108">Pour archiver un fichier</span><span class="sxs-lookup"><span data-stu-id="8ccf1-108">To check in a file</span></span>  
  
1.  <span data-ttu-id="8ccf1-109">Dans l'Explorateur de solutions, cliquez avec le bouton droit sur le fichier à archiver, puis cliquez sur **Archiver**.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-109">In Solution Explorer, right-click the file to check in, and then click **Check In**.</span></span>  
  
2.  <span data-ttu-id="8ccf1-110">Si la boîte de dialogue **Archivage** apparaît, sélectionnez les options appropriées, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-110">If the **Check In** dialog box appears, select the appropriate options, and then click **OK**.</span></span>  
  
     <span data-ttu-id="8ccf1-111">**Date d'arrivée**</span><span class="sxs-lookup"><span data-stu-id="8ccf1-111">**Check In**</span></span>  
     <span data-ttu-id="8ccf1-112">Archive tous les éléments sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-112">Check in all the selected items.</span></span>  
  
     <span data-ttu-id="8ccf1-113">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="8ccf1-113">**Columns**</span></span>  
     <span data-ttu-id="8ccf1-114">Identifiez les colonnes à afficher et l'ordre dans lequel elles s'affichent.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-114">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="8ccf1-115">**Commentaires**</span><span class="sxs-lookup"><span data-stu-id="8ccf1-115">**Comments**</span></span>  
     <span data-ttu-id="8ccf1-116">Ajoutez un commentaire à associer à l'opération d'archivage.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-116">Add a comment to associate with the check-in operation.</span></span>  
  
     <span data-ttu-id="8ccf1-117">**Ne pas afficher la boîte de dialogue Archiver lors de l'archivage d'éléments**</span><span class="sxs-lookup"><span data-stu-id="8ccf1-117">**Don't show Check in dialog box when checking in items**</span></span>  
     <span data-ttu-id="8ccf1-118">Supprime la boîte de dialogue pendant les archivages.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-118">Suppress the dialog box during check-in operations.</span></span>  
  
     <span data-ttu-id="8ccf1-119">**Affichage en 2D**</span><span class="sxs-lookup"><span data-stu-id="8ccf1-119">**Flat View**</span></span>  
     <span data-ttu-id="8ccf1-120">Affiche les fichiers que vous archivez sous forme de liste en 2D sous leur connexion de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-120">Display the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="8ccf1-121">**Nom**</span><span class="sxs-lookup"><span data-stu-id="8ccf1-121">**Name**</span></span>  
     <span data-ttu-id="8ccf1-122">Affiche le nom des éléments à archiver.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-122">Displays the names of the items to check in.</span></span> <span data-ttu-id="8ccf1-123">Les cases à cocher en regard des éléments affichés sont activées.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-123">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="8ccf1-124">Si vous ne souhaitez pas archiver un élément donné, désactivez la case à cocher correspondante.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-124">If you do not want to check in a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="8ccf1-125">**Options**</span><span class="sxs-lookup"><span data-stu-id="8ccf1-125">**Options**</span></span>  
     <span data-ttu-id="8ccf1-126">Affiche des options d'archivage propres au plug-in de contrôle de code source lorsque vous cliquez sur la flèche située à droite du bouton.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-126">Displays source control plug-in-specific check-in options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="8ccf1-127">**Sort**</span><span class="sxs-lookup"><span data-stu-id="8ccf1-127">**Sort**</span></span>  
     <span data-ttu-id="8ccf1-128">Permet d'ordonner les colonnes d'affichage.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-128">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="8ccf1-129">**Arborescence**</span><span class="sxs-lookup"><span data-stu-id="8ccf1-129">**Tree View**</span></span>  
     <span data-ttu-id="8ccf1-130">Affiche la hiérarchie des dossiers et des fichiers pour les éléments que vous archivez.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-130">Display the folder and file hierarchy for the items you are checking in.</span></span>  
  
 <span data-ttu-id="8ccf1-131">Si le fichier que vous avez archivé ne fait pas partie d'une extraction partagée, l'environnement [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] archive alors immédiatement le fichier.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-131">If the file you have checked in is not part of a shared checkout, the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment checks in the file immediately.</span></span> <span data-ttu-id="8ccf1-132">Sinon, il peut vous demander de fusionner votre version avec celles créées par d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8ccf1-132">Otherwise, it may prompt you to merge your version with versions created by other users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ccf1-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ccf1-133">See Also</span></span>  
 <span data-ttu-id="8ccf1-134">[Afficher la liste des fichiers modifiés](../../2014/database-engine/view-a-list-of-modified-files.md) </span><span class="sxs-lookup"><span data-stu-id="8ccf1-134">[View a List of Modified Files](../../2014/database-engine/view-a-list-of-modified-files.md) </span></span>  
 [<span data-ttu-id="8ccf1-135">Gérer les archivages</span><span class="sxs-lookup"><span data-stu-id="8ccf1-135">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)  
  
  
