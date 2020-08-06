---
title: Ajouter des projets au contrôle de code source | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- projects [SQL Server Management Studio], adding
ms.assetid: fd4616b2-a564-4a66-ac53-d1f5cba213c2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0afef4ef91e4d80db7e956d03a95a2ecffe1dc4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602293"
---
# <a name="add-projects-to-source-control"></a><span data-ttu-id="f4201-102">Ajouter des projets au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="f4201-102">Add Projects to Source Control</span></span>
  <span data-ttu-id="f4201-103">Les solutions [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] peuvent héberger plusieurs projets de script.</span><span class="sxs-lookup"><span data-stu-id="f4201-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] solutions can host multiple script projects.</span></span> <span data-ttu-id="f4201-104">La méthode d'ajout d'un projet au contrôle de code source varie selon que la solution à laquelle appartient le projet est ou non sous contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="f4201-104">How you add a project to source control depends upon whether the solution to which the project belongs is under source control.</span></span> <span data-ttu-id="f4201-105">Si la solution est sous contrôle de code source, le projet s'ajoute automatiquement au contrôle de code source lors de l'archivage de la solution.</span><span class="sxs-lookup"><span data-stu-id="f4201-105">If the solution is under source control, checking in the solution automatically adds the project to source control.</span></span> <span data-ttu-id="f4201-106">Pour plus d’informations sur l’archivage des solutions, consultez [archiver des fichiers](../../2014/database-engine/check-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="f4201-106">For more information about checking in solutions, see [Check In Files](../../2014/database-engine/check-in-files.md).</span></span>  
  
 <span data-ttu-id="f4201-107">Si la solution à laquelle appartient le projet n'est pas sous contrôle de code source, vous pouvez ajouter la solution au contrôle de code source. Celle-ci ajoute alors automatiquement les projets qu'elle contient au contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="f4201-107">If the solution that this project belongs to is not under source control, you can add that solution to source control, which then automatically adds the solution's projects.</span></span> <span data-ttu-id="f4201-108">Pour plus d’informations sur l’ajout de solutions au contrôle de code source, consultez [Ajouter des solutions au contrôle de code source](../../2014/database-engine/add-solutions-to-source-control.md).</span><span class="sxs-lookup"><span data-stu-id="f4201-108">For more information about adding solutions to source control, see [Add Solutions to Source Control](../../2014/database-engine/add-solutions-to-source-control.md).</span></span>  
  
 <span data-ttu-id="f4201-109">Si vous ne souhaitez pas ajouter la solution au contrôle de code source, vous pouvez utiliser la commande **Ajouter une sélection au contrôle de code source** pour ajouter le projet manuellement.</span><span class="sxs-lookup"><span data-stu-id="f4201-109">If you do not want to add the solution to source control, you can use the **Add Selection to Source Control** command to add the project manually.</span></span>  
  
 <span data-ttu-id="f4201-110">Les objets de base de données ne sont pas protégés directement par le fournisseur de contrôle de code source, mais vous pouvez créer des scripts d'objets de base de données et enregistrer les scripts soumis au contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="f4201-110">Database objects are not directly protected by the source control provider, but you can create scripts of database objects and save the scripts under source control.</span></span>  
  
### <a name="to-add-a-project-to-source-control"></a><span data-ttu-id="f4201-111">Pour ajouter un projet au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="f4201-111">To add a project to source control</span></span>  
  
1.  <span data-ttu-id="f4201-112">Dans l'Explorateur de solutions, sélectionnez un projet.</span><span class="sxs-lookup"><span data-stu-id="f4201-112">In Solution Explorer, select a project.</span></span>  
  
2.  <span data-ttu-id="f4201-113">Dans le menu **fichier** , pointez sur **contrôle de code source**, puis cliquez sur **Ajouter les projets sélectionnés au contrôle de code source**.</span><span class="sxs-lookup"><span data-stu-id="f4201-113">On the **File** menu, point to **Source Control**, and then click **Add Selected Projects to Source Control**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f4201-114">Si vous utilisez la commande **Ajouter les projets sélectionnés au contrôle de code source** pour ajouter un projet qui appartient à une solution sous contrôle de code source, vous êtes invité à indiquer si vous souhaitez ajouter le projet en tant que sous-dossier de la solution sous contrôle de code source ou pour ajouter le projet en tant que dossier distinct.</span><span class="sxs-lookup"><span data-stu-id="f4201-114">If you use the **Add Selected Projects to Source Control** command to add a project that belongs to a source-controlled solution, you are prompted whether you want to add the project as a subfolder of the source-controlled solution or to add the project as a separate folder.</span></span>  
  
3.  <span data-ttu-id="f4201-115">Si vous y êtes invité, connectez-vous à votre fournisseur de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="f4201-115">If prompted, log on to your source control provider.</span></span>  
  
4.  <span data-ttu-id="f4201-116">La boîte **de dialogue Ajouter au projet SourceSafe** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f4201-116">The **Add to SourceSafe Project** dialog box appears.</span></span> <span data-ttu-id="f4201-117">Le nom de votre projet s’affiche dans la zone **projet** .</span><span class="sxs-lookup"><span data-stu-id="f4201-117">The name of your project appears in the **Project** box.</span></span>  
  
5.  <span data-ttu-id="f4201-118">Dans la liste des **dossiers** , ouvrez le dossier dans lequel vous souhaitez placer votre projet.</span><span class="sxs-lookup"><span data-stu-id="f4201-118">In the **Folders** list, open the folder where you want to place your project.</span></span> <span data-ttu-id="f4201-119">Vous pouvez également cliquer sur **créer** pour créer un dossier avec le nom affiché dans la zone **projet** .</span><span class="sxs-lookup"><span data-stu-id="f4201-119">Alternatively, you can click **Create** to create a folder with the name displayed in the **Project** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4201-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f4201-120">See Also</span></span>  
 [<span data-ttu-id="f4201-121">Ajouter des solutions et des projets au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="f4201-121">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)  
  
  
