---
title: Enlever ou supprimer un élément ou un projet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting project items
- projects [SQL Server Management Studio], item removal
- removing project items
ms.assetid: 3fd92434-70f5-466e-bef0-7e0fd73ddb1c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 679911f15d6c47f4274180602a5376c4ec03c77b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603763"
---
# <a name="remove-or-delete-an-item-or-project"></a><span data-ttu-id="604bc-102">Enlever ou supprimer un élément ou un projet</span><span class="sxs-lookup"><span data-stu-id="604bc-102">Remove or Delete an Item or Project</span></span>
  <span data-ttu-id="604bc-103">Les éléments de projet des projets [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sont les requêtes, les connexions et les fichiers divers.</span><span class="sxs-lookup"><span data-stu-id="604bc-103">Project items in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] projects are Queries, Connections, and Miscellaneous files.</span></span> <span data-ttu-id="604bc-104">Vous pouvez enlever des requêtes et des fichiers divers de projet d'une solution sans effacer du support de stockage les fichiers.</span><span class="sxs-lookup"><span data-stu-id="604bc-104">You can remove project queries and miscellaneous files from your solution without erasing the files from storage.</span></span> <span data-ttu-id="604bc-105">Supprimez un projet ou un élément lorsqu'il n'est plus utile dans la solution en cours mais que vous souhaitez l'insérer dans une autre solution.</span><span class="sxs-lookup"><span data-stu-id="604bc-105">Remove a project or item when it is not useful in the current solution but you want to include it in another solution.</span></span>  
  
### <a name="to-remove-a-project-item"></a><span data-ttu-id="604bc-106">Pour supprimer un élément de projet</span><span class="sxs-lookup"><span data-stu-id="604bc-106">To remove a project item</span></span>  
  
1.  <span data-ttu-id="604bc-107">Dans l'Explorateur de solutions, sélectionnez l'élément de projet à enlever.</span><span class="sxs-lookup"><span data-stu-id="604bc-107">In Solution Explorer, select the project item you want to remove.</span></span>  
  
2.  <span data-ttu-id="604bc-108">Dans le menu **Edition** , cliquez sur **Enlever**.</span><span class="sxs-lookup"><span data-stu-id="604bc-108">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="604bc-109">Dans la boîte de dialogue de confirmation, cliquez sur **Enlever** pour enlever l’élément du projet.</span><span class="sxs-lookup"><span data-stu-id="604bc-109">On the confirmation dialog, click **Remove** to remove the item from the project.</span></span>  
  
 <span data-ttu-id="604bc-110">Un élément enlevé existe toujours dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="604bc-110">A removed item still exists on the file system.</span></span> <span data-ttu-id="604bc-111">Par conséquent, après avoir enlevé un élément, vous pouvez toujours l'ajouter à sa solution initiale ou à une autre solution.</span><span class="sxs-lookup"><span data-stu-id="604bc-111">Therefore, you can add a removed item to its original solution or to another solution.</span></span>  
  
#### <a name="to-remove-a-project"></a><span data-ttu-id="604bc-112">Pour enlever un projet</span><span class="sxs-lookup"><span data-stu-id="604bc-112">To remove a project</span></span>  
  
1.  <span data-ttu-id="604bc-113">Dans l'Explorateur de solutions, sélectionnez le projet à enlever.</span><span class="sxs-lookup"><span data-stu-id="604bc-113">In Solution Explorer, select the project you want to remove.</span></span>  
  
2.  <span data-ttu-id="604bc-114">Dans le menu **Edition** , cliquez sur **Enlever**.</span><span class="sxs-lookup"><span data-stu-id="604bc-114">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="604bc-115">Dans la boîte de dialogue de confirmation, cliquez sur **OK**pour enlever le projet de la solution.</span><span class="sxs-lookup"><span data-stu-id="604bc-115">On the confirmation dialog, click **OK**, to remove the project from the solution.</span></span>  
  
 <span data-ttu-id="604bc-116">Vous pouvez supprimer de façon permanente un projet, mais vous devez d'abord enlever les références au projet des solutions [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , puis utiliser l'Explorateur [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows pour supprimer définitivement du système de stockage les fichiers associés.</span><span class="sxs-lookup"><span data-stu-id="604bc-116">You can delete a project permanently, but you first need to remove any references to the project from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solutions, and then use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer to permanently delete the associated files from storage.</span></span>  
  
#### <a name="to-delete-a-project"></a><span data-ttu-id="604bc-117">Pour supprimer un projet</span><span class="sxs-lookup"><span data-stu-id="604bc-117">To delete a project</span></span>  
  
1.  <span data-ttu-id="604bc-118">Dans l'Explorateur de solutions, enlevez le projet que vous souhaitez supprimer de la solution.</span><span class="sxs-lookup"><span data-stu-id="604bc-118">In Solution Explorer, remove the project you want to delete from the solution.</span></span>  
  
2.  <span data-ttu-id="604bc-119">Dans l'Explorateur Windows, recherchez et sélectionnez les fichiers associés au projet ou à l'élément que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="604bc-119">In Windows Explorer, locate and select the files associated with the project or item you want to delete.</span></span>  
  
3.  <span data-ttu-id="604bc-120">Dans le menu **Fichier** , cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="604bc-120">On the **File** menu, click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604bc-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="604bc-121">See Also</span></span>  
 <span data-ttu-id="604bc-122">[Explorateur de solutions](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="604bc-122">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="604bc-123">[Ajouter de nouveaux éléments à un projet](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="604bc-123">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="604bc-124">Ajouter des éléments existants à un projet</span><span class="sxs-lookup"><span data-stu-id="604bc-124">Add Existing Items to a Project</span></span>](add-existing-items-to-a-project.md)  
  
  
