---
title: Développement d’un projet de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 6e90b016-36a5-415e-9440-a20199fffff0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da648b3b09b25fa2a7b1cf886ad1bf770296f5ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613560"
---
# <a name="development-of-an-integration-services-project"></a><span data-ttu-id="c4147-102">Développement d'un projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="c4147-102">Development of an Integration Services Project</span></span>
  <span data-ttu-id="c4147-103">Vous ajoutez des packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] aux projets.</span><span class="sxs-lookup"><span data-stu-id="c4147-103">You add [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to projects.</span></span> <span data-ttu-id="c4147-104">Pour créer et utiliser des projets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , vous devez installer l’environnement [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4147-104">To create and work with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects, you must install the [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] environment.</span></span> <span data-ttu-id="c4147-105">Pour plus d’informations, consultez [Installer Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="c4147-105">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
 <span data-ttu-id="c4147-106">Quand vous créez un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], la boîte de dialogue **Nouveau projet** inclut un modèle **Projet Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="c4147-106">When you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the **New Project** dialog box includes an **Integration Services Project** template.</span></span> <span data-ttu-id="c4147-107">Ce modèle de projet crée un nouveau projet qui contient un package unique.</span><span class="sxs-lookup"><span data-stu-id="c4147-107">This project template creates a new project that contains a single package.</span></span>  
  
## <a name="projects-and-solutions"></a><span data-ttu-id="c4147-108">Projets et solutions</span><span class="sxs-lookup"><span data-stu-id="c4147-108">Projects and Solutions</span></span>  
 <span data-ttu-id="c4147-109">Les projets sont stockés dans leur solution.</span><span class="sxs-lookup"><span data-stu-id="c4147-109">Projects are stored in solutions.</span></span> <span data-ttu-id="c4147-110">Vous pouvez créer une solution, puis ajouter un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] à cette solution.</span><span class="sxs-lookup"><span data-stu-id="c4147-110">You can create a solution first and then add an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the solution.</span></span> <span data-ttu-id="c4147-111">S’il n’existe aucune solution, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] en crée une automatiquement dès que vous commencez à créer le projet.</span><span class="sxs-lookup"><span data-stu-id="c4147-111">If no solution exists, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] automatically creates one for you when you first create the project.</span></span> <span data-ttu-id="c4147-112">Une solution peut contenir plusieurs projets de différents types.</span><span class="sxs-lookup"><span data-stu-id="c4147-112">A solution can contain multiple projects of different types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4147-113">Par défaut, quand vous créez un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], la solution n’apparaît pas dans le volet **Explorateur de solutions** .</span><span class="sxs-lookup"><span data-stu-id="c4147-113">By default, when you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the solution is not shown in the **Solution Explorer** pane.</span></span> <span data-ttu-id="c4147-114">Pour modifier ce comportement par défaut, dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="c4147-114">To change this default behavior, on the **Tools** menus, click **Options**.</span></span> <span data-ttu-id="c4147-115">Dans la boîte de dialogue **Options** , développez **Projets et solutions**, puis cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="c4147-115">In the **Options** dialog box, expand **Projects and Solutions**, and then click **General**.</span></span> <span data-ttu-id="c4147-116">Dans la page **Général** , sélectionnez **Toujours afficher la solution**.</span><span class="sxs-lookup"><span data-stu-id="c4147-116">On the **General** page, select **Always show solution**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c4147-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="c4147-117">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c4147-118">Créer un projet de Integration Services</span><span class="sxs-lookup"><span data-stu-id="c4147-118">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="c4147-119">Ajouter un élément à un projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="c4147-119">Add an Item to an Integration Services Project</span></span>](../../2014/integration-services/add-an-item-to-an-integration-services-project.md)  
  
-   [<span data-ttu-id="c4147-120">Ajouter ou supprimer un projet Integration Services dans une solution</span><span class="sxs-lookup"><span data-stu-id="c4147-120">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
