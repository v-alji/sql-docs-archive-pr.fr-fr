---
title: Créer un projet de Integration Services | Microsoft Docs
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
ms.assetid: 1e23f259-0401-4333-ab4f-89809aae63b1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f62d3ac2d33bb51a0ccc3b77d9f8b5ec0f52b345
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604070"
---
# <a name="create-a-new-integration-services-project"></a><span data-ttu-id="128a5-102">Créer un projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="128a5-102">Create a New Integration Services Project</span></span>
  <span data-ttu-id="128a5-103">Cette procédure permet de créer un projet et une solution [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="128a5-103">This procedure creates a new project and a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] solution.</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="128a5-104">Pour créer un nouveau projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="128a5-104">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="128a5-105">Ouvrez [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="128a5-105">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="128a5-106">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet**.</span><span class="sxs-lookup"><span data-stu-id="128a5-106">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="128a5-107">Dans la boîte de dialogue **Nouveau projet**, dans le volet **Modèles**, sélectionnez **Projet Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="128a5-107">In the **New Project** dialog box, in the **Templates** pane, select the **Integration Services Project** template.</span></span>  
  
     <span data-ttu-id="128a5-108">Le modèle **Projet Integration Services** crée un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient un package unique vide.</span><span class="sxs-lookup"><span data-stu-id="128a5-108">The **Integration Services Project** template creates an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains a single, empty package.</span></span>  
  
4.  <span data-ttu-id="128a5-109">(Facultatif) modifiez le nom et l'emplacement du projet.</span><span class="sxs-lookup"><span data-stu-id="128a5-109">(Optional) Edit the project name and the location.</span></span>  
  
     <span data-ttu-id="128a5-110">Le nom de la solution est automatiquement mis à jour pour correspondre au nom du projet.</span><span class="sxs-lookup"><span data-stu-id="128a5-110">The solution name is automatically updated to match the project name.</span></span>  
  
5.  <span data-ttu-id="128a5-111">Pour créer un dossier distinct pour le fichier de solution, sélectionnez **Créer le répertoire pour la solution**.</span><span class="sxs-lookup"><span data-stu-id="128a5-111">To create a separate folder for the solution file, select **Create directory for solution**.</span></span> <span data-ttu-id="128a5-112">Il s'agit de l'option par défaut.</span><span class="sxs-lookup"><span data-stu-id="128a5-112">This is the default option.</span></span>  
  
6.  <span data-ttu-id="128a5-113">Si un logiciel de contrôle de code source est installé sur l’ordinateur, sélectionnez **Ajouter au contrôle de code source** pour associer le projet au contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="128a5-113">If source control software is installed on the computer, select **Add to source control**  to associate the project with source control.</span></span>  
  
7.  <span data-ttu-id="128a5-114">Si le logiciel de contrôle de code source est [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, la boîte de dialogue **Connexion à Visual SourceSafe** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="128a5-114">If the source control software is [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, the **Visual SourceSafe Login** dialog box opens.</span></span> <span data-ttu-id="128a5-115">Dans **Connexion à Visual SourceSafe**, indiquez un nom d’utilisateur, un mot de passe et le nom de la base de données [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="128a5-115">In **Visual SourceSafe Login**, provide a user name, a password, and the name of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database.</span></span> <span data-ttu-id="128a5-116">Cliquez sur **Parcourir** pour localiser la base de données.</span><span class="sxs-lookup"><span data-stu-id="128a5-116">Click **Browse** to locate the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="128a5-117">Pour afficher et modifier le plug-in du contrôle de code source sélectionné et configurer l’environnement du contrôle de code source, cliquez sur **Options** dans le menu **Outils**, puis développez le nœud **Contrôle de code source**.</span><span class="sxs-lookup"><span data-stu-id="128a5-117">To view and change the selected source control plug-in and to configure the source control environment, click **Options** on the **Tools** menu, and then expand the **Source Control** node.</span></span>  
  
8.  <span data-ttu-id="128a5-118">Cliquez sur **OK** pour ajouter la solution à la solution **Explorer**r et ajouter le projet à la solution.</span><span class="sxs-lookup"><span data-stu-id="128a5-118">Click **OK** to add the solution to **Solution Explore**r and add the project to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="128a5-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="128a5-119">See Also</span></span>  
 <span data-ttu-id="128a5-120">[Integration Services &#40;projets de&#41; SSIS](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="128a5-120">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="128a5-121">Ajouter ou supprimer un projet Integration Services dans une solution</span><span class="sxs-lookup"><span data-stu-id="128a5-121">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
