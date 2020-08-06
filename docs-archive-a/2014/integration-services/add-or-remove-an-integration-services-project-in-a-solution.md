---
title: Ajouter ou supprimer un projet Integration Services dans une solution | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- Integration Services projects, adding
- SQL Server Integration Services projects, adding
- SSIS projects, adding
- projects [Integration Services], adding
ms.assetid: f01f6475-b63c-41dc-82ac-b62162b3adf7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49984c61047a6b716015bd72e518b73cb08b3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600207"
---
# <a name="add-or-remove-an-integration-services-project-in-a-solution"></a><span data-ttu-id="971e3-102">Ajouter ou supprimer un projet Integration Services dans une solution</span><span class="sxs-lookup"><span data-stu-id="971e3-102">Add or Remove an Integration Services Project in a Solution</span></span>
  <span data-ttu-id="971e3-103">Les procédures suivantes décrivent comment ajouter ou supprimer un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dans une solution.</span><span class="sxs-lookup"><span data-stu-id="971e3-103">The following procedures descibe how to add or remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in a solution.</span></span>  
  
 <span data-ttu-id="971e3-104">Vous pouvez uniquement ajouter un projet à une solution existante ou supprimer un projet d'une solution, lorsque la solution est visible dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="971e3-104">You can only add a project to an existing solution, or remove a project from a solution, when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="971e3-105">Si vous avez sélectionné l’option **toujours afficher la solution** dans [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] affiche une solution même lorsque cette solution contient un seul projet.</span><span class="sxs-lookup"><span data-stu-id="971e3-105">If you have selected the **Always show solution** option in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution even when that solution contains only one project.</span></span> <span data-ttu-id="971e3-106">Dans le cas contraire, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] affiche une solution uniquement lorsque cette solution contient plusieurs projets.</span><span class="sxs-lookup"><span data-stu-id="971e3-106">Otherwise, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution only when that solution contains more than one project.</span></span> <span data-ttu-id="971e3-107">Les projets supplémentaires peuvent être des projets [!INCLUDE[ssIS](../includes/ssis-md.md)] ou des projets d'autres types.</span><span class="sxs-lookup"><span data-stu-id="971e3-107">The additional projects can be either [!INCLUDE[ssIS](../includes/ssis-md.md)] projects or projects of other types.</span></span>  
  
## <a name="adding-an-integration-services-project"></a><span data-ttu-id="971e3-108">Ajout d'un projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="971e3-108">Adding an Integration Services Project</span></span>  
 <span data-ttu-id="971e3-109">Quand vous ajoutez un projet, vous pouvez créer un nouveau projet vide dans [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou ajouter un projet que vous avez déjà créé pour une autre solution.</span><span class="sxs-lookup"><span data-stu-id="971e3-109">When you add a project, you can have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] create a new, blank project, or you can add a project that you have already created for a different solution.</span></span> <span data-ttu-id="971e3-110">Vous pouvez uniquement ajouter un projet à une solution existante quand la solution est visible dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="971e3-110">You can only add a project to an existing solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
#### <a name="to-add-a-new-integration-services-project-to-a-solution"></a><span data-ttu-id="971e3-111">Pour ajouter un nouveau projet Integration Services à une solution</span><span class="sxs-lookup"><span data-stu-id="971e3-111">To add a new Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="971e3-112">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez la solution à laquelle vous souhaitez ajouter un nouveau projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="971e3-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="971e3-113">Cliquez avec le bouton droit sur la solution, cliquez sur **Ajouter**, puis sur **Nouveau projet**.</span><span class="sxs-lookup"><span data-stu-id="971e3-113">Right-click the solution, click **Add**, and then click **New Project**.</span></span>  
  
    -   <span data-ttu-id="971e3-114">Dans le menu **Fichier** , pointez sur **Ajouter**, puis cliquez sur **Nouveau projet**.</span><span class="sxs-lookup"><span data-stu-id="971e3-114">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="971e3-115">Dans la boîte de dialogue **Ajouter un nouveau projet** , dans le volet **Modèles** , cliquez sur **Projet Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="971e3-115">In the **Add New Project** dialog box, click **Integration Services Project** in the **Templates** pane.</span></span>  
  
3.  <span data-ttu-id="971e3-116">Éventuellement, modifiez le nom et l'emplacement du projet.</span><span class="sxs-lookup"><span data-stu-id="971e3-116">Optionally, edit the project name and location.</span></span>  
  
4.  <span data-ttu-id="971e3-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="971e3-117">Click **OK**.</span></span>  
  
#### <a name="to-add-an-existing-integration-services-project-to-a-solution"></a><span data-ttu-id="971e3-118">Pour ajouter un projet Integration Services existant à une solution</span><span class="sxs-lookup"><span data-stu-id="971e3-118">To add an existing Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="971e3-119">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez la solution à laquelle vous souhaitez ajouter un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] existant, puis effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="971e3-119">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="971e3-120">Cliquez avec le bouton droit sur la solution, pointez sur **Ajouter**, puis cliquez sur **Projet existant**.</span><span class="sxs-lookup"><span data-stu-id="971e3-120">Right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  
  
    -   <span data-ttu-id="971e3-121">Dans le menu **Fichier** , cliquez sur **Ajouter**, puis sur **Projet existant**.</span><span class="sxs-lookup"><span data-stu-id="971e3-121">On the **File** menu, click **Add**, and then click **Existing Project**.</span></span>  
  
2.  <span data-ttu-id="971e3-122">Dans la boîte de dialogue **Ajouter un projet existant** , recherchez le projet à ajouter, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="971e3-122">In the **Add Existing Project** dialog box, browse to locate the project you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="971e3-123">Le projet est ajouté au dossier de la solution dans l' **Explorateur de solutions**.</span><span class="sxs-lookup"><span data-stu-id="971e3-123">The project is added to the solution folder in **Solution Explorer**.</span></span>  
  
## <a name="removing-an-integration-services-project"></a><span data-ttu-id="971e3-124">Suppression d'un projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="971e3-124">Removing an Integration Services Project</span></span>  
 <span data-ttu-id="971e3-125">Vous ne pouvez supprimer un projet d'une solution que lorsque la solution est visible dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="971e3-125">You can only remove a project from a solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="971e3-126">Une fois que la solution est visible, vous pouvez tout supprimer mais devez conserver un projet.</span><span class="sxs-lookup"><span data-stu-id="971e3-126">After the solution is visible, you can remove all except one project.</span></span> <span data-ttu-id="971e3-127">Lorsqu'il ne reste qu'un seul projet, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] n'affiche plus le dossier des solutions et vous ne pouvez pas supprimer le dernier projet.</span><span class="sxs-lookup"><span data-stu-id="971e3-127">As soon as only one project remains, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no longer displays the solution folder and you cannot remove the last project.</span></span>  
  
#### <a name="to-remove-an-integration-services-project-from-a-solution"></a><span data-ttu-id="971e3-128">Pour supprimer un projet Integration Services d'une solution</span><span class="sxs-lookup"><span data-stu-id="971e3-128">To remove an Integration Services project from a solution</span></span>  
  
1.  <span data-ttu-id="971e3-129">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez la solution dans laquelle vous souhaitez supprimer un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="971e3-129">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution from which you want to remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="971e3-130">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le projet, puis cliquez sur **Décharger le projet**.</span><span class="sxs-lookup"><span data-stu-id="971e3-130">In Solution Explorer, right-click the project, and then click **Unload Project**.</span></span>  
  
3.  <span data-ttu-id="971e3-131">Cliquez sur **OK** pour confirmer la suppression.</span><span class="sxs-lookup"><span data-stu-id="971e3-131">Click **OK** to confirm the removal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971e3-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="971e3-132">See Also</span></span>  
 <span data-ttu-id="971e3-133">[Integration Services &#40;projets de&#41; SSIS](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="971e3-133">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="971e3-134">Créer un projet de Integration Services</span><span class="sxs-lookup"><span data-stu-id="971e3-134">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
  
