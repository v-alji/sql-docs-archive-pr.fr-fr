---
title: Gérer les extractions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- source controls [SQL Server Management Studio], checkouts
- checkouts [SQL Server Management Studio]
- checking out files
ms.assetid: ddd4adba-d432-4005-9cb2-bb9ee3163d8e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfa25cdc27e707d4be705e66b215130c9d70ce1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614772"
---
# <a name="manage-checkouts"></a><span data-ttu-id="dae4d-102">Gérer les extractions</span><span class="sxs-lookup"><span data-stu-id="dae4d-102">Manage Checkouts</span></span>
  <span data-ttu-id="dae4d-103">Une fois un fichier ajouté au contrôle de code source, vous devez l'extraire avant de pouvoir le modifier.</span><span class="sxs-lookup"><span data-stu-id="dae4d-103">After a file has been added to source control, you must check out the file before you can modify it.</span></span> <span data-ttu-id="dae4d-104">Lorsque vous procédez à l'extraction d'un fichier du contrôle de code source, le fournisseur de contrôle de code source copie la dernière version sur votre disque local et désactive l'attribut de lecture seule du fichier.</span><span class="sxs-lookup"><span data-stu-id="dae4d-104">When you check a file out of source control, the source control provider creates a copy of the latest version on your local disk and removes the read-only attribute of the file.</span></span> <span data-ttu-id="dae4d-105">Dans certains cas, il est possible que vous deviez modifier un fichier sans procéder à son extraction.</span><span class="sxs-lookup"><span data-stu-id="dae4d-105">In some circumstances you might need to edit a file without checking out the file.</span></span> <span data-ttu-id="dae4d-106">Pour plus d’informations sur la modification d’un fichier sans vérifier le fichier, consultez [modifier les fichiers archivés](../../2014/database-engine/edit-checked-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="dae4d-106">For more information about editing a file without checking the file out, see [Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md).</span></span>  
  
 <span data-ttu-id="dae4d-107">Vous pouvez utiliser [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour extraire des fichiers manuellement ou automatiquement.</span><span class="sxs-lookup"><span data-stu-id="dae4d-107">You can use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out files manually or automatically.</span></span> <span data-ttu-id="dae4d-108">Vous pouvez extraire les fichiers manuellement en ouvrant la solution qui contient les fichiers dans l' [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environnement, puis en cliquant sur la commande **extraire** .</span><span class="sxs-lookup"><span data-stu-id="dae4d-108">You check out files manually by opening the solution that contains the files in the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment, and then clicking the **Check Out** command.</span></span> <span data-ttu-id="dae4d-109">Vous pouvez extraire des fichiers automatiquement si vous configurez l'environnement [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] à cette fin.</span><span class="sxs-lookup"><span data-stu-id="dae4d-109">You can check out files automatically if you configure the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to do so.</span></span>  
  
 <span data-ttu-id="dae4d-110">En fonction des options configurées par votre administrateur, vous pouvez également extraire des fichiers en mode exclusif ou partagé.</span><span class="sxs-lookup"><span data-stu-id="dae4d-110">Depending on the options that your administrator sets on your source control provider, you can also check out files in exclusive or shared mode.</span></span> <span data-ttu-id="dae4d-111">Lorsque vous procédez à l'extraction d'un fichier de manière exclusive, vous seul pouvez le modifier et aucun autre utilisateur ne peut l'extraire tant que vous ne l'avez pas archivé.</span><span class="sxs-lookup"><span data-stu-id="dae4d-111">When you check out a file exclusively, only you can modify it, and no other user can check out the file until you check it in.</span></span> <span data-ttu-id="dae4d-112">Lorsque vous procédez à l'extraction d'un fichier en mode partagé, n'importe quel autre utilisateur peut extraire ce même fichier.</span><span class="sxs-lookup"><span data-stu-id="dae4d-112">When you check out a file in shared mode, any number of users can check out the same file.</span></span> <span data-ttu-id="dae4d-113">À mesure que chaque utilisateur archive le fichier, le fournisseur de contrôle de code source tente de fusionner le fichier avec la dernière version serveur du fichier en question.</span><span class="sxs-lookup"><span data-stu-id="dae4d-113">As each user checks in the file, the source control provider attempts to merge the file with the latest server version of the file.</span></span> <span data-ttu-id="dae4d-114">En cas de conflits entre la version en cours d'archivage et la dernière version, le fournisseur de contrôle de code source demande à l'utilisateur de résoudre ces conflits.</span><span class="sxs-lookup"><span data-stu-id="dae4d-114">If conflicts arise between the version that is being checked in and the latest version, the source control provider prompts the user to resolve the conflicts.</span></span>  
  
 <span data-ttu-id="dae4d-115">Le tableau suivant décrit les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="dae4d-115">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="dae4d-116">Rubrique</span><span class="sxs-lookup"><span data-stu-id="dae4d-116">Topic</span></span>|<span data-ttu-id="dae4d-117">Description</span><span class="sxs-lookup"><span data-stu-id="dae4d-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="dae4d-118">Extraire des fichiers</span><span class="sxs-lookup"><span data-stu-id="dae4d-118">Check Out Files</span></span>](../../2014/database-engine/check-out-files.md)|<span data-ttu-id="dae4d-119">Explique comment extraire un fichier de façon à pouvoir le modifier.</span><span class="sxs-lookup"><span data-stu-id="dae4d-119">Provides instructions on how to check out a file so you can modify it.</span></span>|  
|[<span data-ttu-id="dae4d-120">Annuler des extractions</span><span class="sxs-lookup"><span data-stu-id="dae4d-120">Undo Checkouts</span></span>](../../2014/database-engine/undo-checkouts.md)|<span data-ttu-id="dae4d-121">Explique comment annuler une extraction existante.</span><span class="sxs-lookup"><span data-stu-id="dae4d-121">Explains how to cancel an existing checkout.</span></span>|  
|[<span data-ttu-id="dae4d-122">Extraire automatiquement des fichiers lors de leur modification</span><span class="sxs-lookup"><span data-stu-id="dae4d-122">Automatically Check Out Files Upon Edit</span></span>](../../2014/database-engine/automatically-check-out-files-upon-edit.md)|<span data-ttu-id="dae4d-123">Explique comment configurer le contrôle de code source afin d'extraire un fichier lorsque vous commencez à le modifier.</span><span class="sxs-lookup"><span data-stu-id="dae4d-123">Explains how to configure source control to check out a file when you start to edit it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dae4d-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dae4d-124">See Also</span></span>  
 <span data-ttu-id="dae4d-125">[Gérer les archivages](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="dae4d-125">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="dae4d-126">Modifier des fichiers archivés</span><span class="sxs-lookup"><span data-stu-id="dae4d-126">Edit Checked-In Files</span></span>](../../2014/database-engine/edit-checked-in-files.md)  
  
  
