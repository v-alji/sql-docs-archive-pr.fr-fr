---
title: Créer un projet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], creating
ms.assetid: 7897be19-365b-4b06-bcf0-8a669f67a673
author: stevestein
ms.author: sstein
ms.openlocfilehash: 269feee7225ceb09b1c2ed86419b19ec4001c1f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611476"
---
# <a name="create-a-project"></a><span data-ttu-id="5dd25-102">Créer un projet</span><span class="sxs-lookup"><span data-stu-id="5dd25-102">Create a Project</span></span>
  <span data-ttu-id="5dd25-103">Vous pouvez créer un ou plusieurs projets à l'intérieur d'une solution existante.</span><span class="sxs-lookup"><span data-stu-id="5dd25-103">You can create one or more projects within an existing solution.</span></span>  
  
### <a name="to-create-a-new-project-and-add-it-to-a-solution"></a><span data-ttu-id="5dd25-104">Pour créer un projet et l'ajouter à une solution</span><span class="sxs-lookup"><span data-stu-id="5dd25-104">To create a new project and add it to a solution</span></span>  
  
1.  <span data-ttu-id="5dd25-105">Dans l'Explorateur de solutions, sélectionnez la solution de votre choix.</span><span class="sxs-lookup"><span data-stu-id="5dd25-105">In Solution Explorer, select the solution.</span></span>  
  
2.  <span data-ttu-id="5dd25-106">Dans le menu **Fichier** , pointez sur **Ajouter**, puis cliquez sur **Nouveau projet**.</span><span class="sxs-lookup"><span data-stu-id="5dd25-106">On the **File** menu, point to **Add**, and click **New Project**.</span></span>  
  
3.  <span data-ttu-id="5dd25-107">Dans la boîte de dialogue  **Nouveau projet** , cliquez sur un type de projet.</span><span class="sxs-lookup"><span data-stu-id="5dd25-107">In the  **New Project** dialog box, click a type of project.</span></span>  
  
     <span data-ttu-id="5dd25-108">**Modèles**</span><span class="sxs-lookup"><span data-stu-id="5dd25-108">**Templates**</span></span>  
     <span data-ttu-id="5dd25-109">Dans la zone **Modèles** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="5dd25-109">In the **Templates** box, select a template.</span></span> <span data-ttu-id="5dd25-110">Une brève description du modèle de projet sélectionné apparaît sous la zone **Modèles** .</span><span class="sxs-lookup"><span data-stu-id="5dd25-110">A brief description of the selected project template appears beneath the **Templates** box.</span></span>  
  
     <span data-ttu-id="5dd25-111">**Nom**</span><span class="sxs-lookup"><span data-stu-id="5dd25-111">**Name**</span></span>  
     <span data-ttu-id="5dd25-112">Entrez le nom du projet de script que vous voulez créer.</span><span class="sxs-lookup"><span data-stu-id="5dd25-112">Enter the name of the script project you want to create.</span></span> <span data-ttu-id="5dd25-113">Un dossier avec un nom identique à celui du projet est également créé à l’emplacement indiqué dans le champ **Emplacement** .</span><span class="sxs-lookup"><span data-stu-id="5dd25-113">A folder with the same name as the project is also created in the location displayed in the **Location** field.</span></span> <span data-ttu-id="5dd25-114">Pour certains projets, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] crée des fichiers sources et de prise en charge, qu'il place dans le dossier du nouveau projet.</span><span class="sxs-lookup"><span data-stu-id="5dd25-114">For some projects, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates source and other supporting files and adds them to the new project folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5dd25-115">Pour certains types de projets, la zone de texte **Nom** n’est pas disponible car l’indication de l’emplacement définit le nom.</span><span class="sxs-lookup"><span data-stu-id="5dd25-115">For some project types, the **Name** text box is unavailable because specifying the location sets the name.</span></span> <span data-ttu-id="5dd25-116">Par exemple, les applications Web et les services Web sont situés sur un serveur Web et leur nom est dérivé du répertoire virtuel spécifié sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="5dd25-116">For example, Web applications and Web services are located on a Web server and derive their name from the virtual directory specified on that server.</span></span>  
  
     <span data-ttu-id="5dd25-117">Les noms ne peuvent pas contenir les caractères suivants :</span><span class="sxs-lookup"><span data-stu-id="5dd25-117">Names cannot contain the following characters:</span></span>  
  
    -   <span data-ttu-id="5dd25-118">dièse (#)</span><span class="sxs-lookup"><span data-stu-id="5dd25-118">Pound (#)</span></span>  
  
    -   <span data-ttu-id="5dd25-119">Pourcentage (%)</span><span class="sxs-lookup"><span data-stu-id="5dd25-119">Percent (%)</span></span>  
  
    -   <span data-ttu-id="5dd25-120">Esperluette (&)</span><span class="sxs-lookup"><span data-stu-id="5dd25-120">Ampersand (&)</span></span>  
  
    -   <span data-ttu-id="5dd25-121">astérisque (\*)</span><span class="sxs-lookup"><span data-stu-id="5dd25-121">Asterisk (\*)</span></span>  
  
    -   <span data-ttu-id="5dd25-122">barre verticale (|)</span><span class="sxs-lookup"><span data-stu-id="5dd25-122">Vertical bar (|)</span></span>  
  
    -   <span data-ttu-id="5dd25-123">Barre oblique inverse (\\)</span><span class="sxs-lookup"><span data-stu-id="5dd25-123">Backslash (\\)</span></span>  
  
    -   <span data-ttu-id="5dd25-124">deux-points (:)</span><span class="sxs-lookup"><span data-stu-id="5dd25-124">Colon (:)</span></span>  
  
    -   <span data-ttu-id="5dd25-125">guillemets (")</span><span class="sxs-lookup"><span data-stu-id="5dd25-125">Quotation mark (")</span></span>  
  
    -   <span data-ttu-id="5dd25-126">Inférieur à (\<)</span><span class="sxs-lookup"><span data-stu-id="5dd25-126">Less than (\<)</span></span>  
  
    -   <span data-ttu-id="5dd25-127">Supérieur à (>)</span><span class="sxs-lookup"><span data-stu-id="5dd25-127">Greater than (>)</span></span>  
  
    -   <span data-ttu-id="5dd25-128">point d'interrogation (?)</span><span class="sxs-lookup"><span data-stu-id="5dd25-128">Question mark (?)</span></span>  
  
    -   <span data-ttu-id="5dd25-129">barre oblique (/)</span><span class="sxs-lookup"><span data-stu-id="5dd25-129">Forward slash (/)</span></span>  
  
    -   <span data-ttu-id="5dd25-130">espaces à gauche ou à droite (' ')</span><span class="sxs-lookup"><span data-stu-id="5dd25-130">Leading or trailing spaces (' ')</span></span>  
  
    -   <span data-ttu-id="5dd25-131">noms réservés pour Microsoft Windows ou MS-DOS (« nul », « aux », « con », « com1 », « lpt1 », etc.)</span><span class="sxs-lookup"><span data-stu-id="5dd25-131">Names reserved for Microsoft Windows or MS-DOS, such as ("nul", "aux", "con", "com1", "lpt1", and so on)</span></span>  
  
     <span data-ttu-id="5dd25-132">**Lieu**</span><span class="sxs-lookup"><span data-stu-id="5dd25-132">**Location**</span></span>  
     <span data-ttu-id="5dd25-133">Entrez l'emplacement dans lequel vous voulez créer votre projet ou choisissez-en un dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5dd25-133">Enter the location where you want to create your project, or choose one from the list.</span></span>  
  
     <span data-ttu-id="5dd25-134">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="5dd25-134">**Browse**</span></span>  
     <span data-ttu-id="5dd25-135">Affiche la boîte de dialogue **Emplacement du projet** , afin que vous puissiez naviguer jusqu’au répertoire dans lequel le projet doit être enregistré.</span><span class="sxs-lookup"><span data-stu-id="5dd25-135">Displays the **Project Location** dialog box, allowing you to navigate to a new directory in which to save the project.</span></span>  
  
     <span data-ttu-id="5dd25-136">**Solution**</span><span class="sxs-lookup"><span data-stu-id="5dd25-136">**Solution**</span></span>  
     <span data-ttu-id="5dd25-137">Sélectionnez **Créer une nouvelle solution** pour créer une solution dans l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="5dd25-137">Select **Create new Solution** to create a solution in Solution Explorer.</span></span> <span data-ttu-id="5dd25-138">Sélectionnez **Ajouter à la solution** pour ajouter le nouveau projet à la solution ouverte dans l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="5dd25-138">Select **Add to Solution** to add the new project to the solution currently open in Solution Explorer.</span></span>  
  
     <span data-ttu-id="5dd25-139">**Créer le répertoire pour la solution**</span><span class="sxs-lookup"><span data-stu-id="5dd25-139">**Create directory for Solution**</span></span>  
     <span data-ttu-id="5dd25-140">Sélectionnez cette option pour activer la zone de texte **Nom de solution** .</span><span class="sxs-lookup"><span data-stu-id="5dd25-140">Select to enable the **(Solution) Name** text box.</span></span> <span data-ttu-id="5dd25-141">Cette option crée un nouveau répertoire portant le nom choisi pour le projet et la solution.</span><span class="sxs-lookup"><span data-stu-id="5dd25-141">This option creates a new directory of the name you choose for your project and solution.</span></span>  
  
     <span data-ttu-id="5dd25-142">**Nom de solution**</span><span class="sxs-lookup"><span data-stu-id="5dd25-142">**Solution Name**</span></span>  
     <span data-ttu-id="5dd25-143">Entrez le nom de la nouvelle solution dans laquelle le projet doit être créé.</span><span class="sxs-lookup"><span data-stu-id="5dd25-143">Enter the name of the new solution in which you want your project to be created.</span></span> <span data-ttu-id="5dd25-144">Par défaut, ce champ utilise le même nom que celui qui a été entré dans le champ **Nom** .</span><span class="sxs-lookup"><span data-stu-id="5dd25-144">By default, this field uses the same name as entered in the **Name** field.</span></span>  
  
     <span data-ttu-id="5dd25-145">**Remarque** Pour accéder à cette option, vous devez cocher les cases **Créer une nouvelle solution** dans **Solution** et **Créer un répertoire pour la solution** .</span><span class="sxs-lookup"><span data-stu-id="5dd25-145">**Note** To access this option, you must select both the **Create New Solution** in the **Solution** and the **Create directory for Solution** check boxes.</span></span> <span data-ttu-id="5dd25-146">Certains modèles de projet, comme les applications Web, ne prennent pas en charge cette option.</span><span class="sxs-lookup"><span data-stu-id="5dd25-146">Some project templates do not support this option, such as Web applications.</span></span>  
  
     <span data-ttu-id="5dd25-147">**Ajouter au contrôle de code source**</span><span class="sxs-lookup"><span data-stu-id="5dd25-147">**Add to Source Control**</span></span>  
     <span data-ttu-id="5dd25-148">Si cette case est cochée, l’application de contrôle de code source s’ouvre quand vous cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5dd25-148">When this check box is selected, your source control application opens when you click **OK**.</span></span> <span data-ttu-id="5dd25-149">Pour poursuivre, fournissez les informations requises par l'application de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="5dd25-149">Complete any information required by your source control application to continue.</span></span> <span data-ttu-id="5dd25-150">Pour utiliser cette option, une application cliente de contrôle de code source doit être installée.</span><span class="sxs-lookup"><span data-stu-id="5dd25-150">You must have a source control client application installed to use this option.</span></span>  
  
4.  <span data-ttu-id="5dd25-151">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5dd25-151">Click **OK**.</span></span>  
  
 <span data-ttu-id="5dd25-152">Vous pouvez attribuer un nom au projet de script mais vous ne pouvez pas modifier les noms de dossiers qui sont attribués par [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5dd25-152">You can set a name for the script project, but the folder names are established by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and cannot be changed.</span></span> <span data-ttu-id="5dd25-153">Vous pouvez configurer la spécification de lecteur et de chemin d’accès pour l’ensemble commun des dossiers à l’aide de la boîte de dialogue **Ajouter un nouveau projet** .</span><span class="sxs-lookup"><span data-stu-id="5dd25-153">You can configure the drive and path specification for the common set of folders by using the **Add New Project** dialog box.</span></span> <span data-ttu-id="5dd25-154">Cliquez avec le bouton droit sur l’icône de la solution dans **l’Explorateur de solutions**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5dd25-154">Right-click the solution icon in **Solution Explorer**, and then click **Add**.</span></span> <span data-ttu-id="5dd25-155">L’emplacement par défaut pour les dossiers de projets de scripts est : C:\Documents and Settings\\*nom_utilisateur*\My Documents\SQL Server Management Studio\Projects\\.</span><span class="sxs-lookup"><span data-stu-id="5dd25-155">The default location for script project folders is: C:\Documents and Settings\\*username*\My Documents\SQL Server Management Studio\Projects\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd25-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5dd25-156">See Also</span></span>  
 <span data-ttu-id="5dd25-157">[Explorateur de solutions](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="5dd25-157">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="5dd25-158">[Ajouter un projet existant à une solution](add-an-existing-project-to-a-solution.md) </span><span class="sxs-lookup"><span data-stu-id="5dd25-158">[Add an Existing Project to a Solution](add-an-existing-project-to-a-solution.md) </span></span>  
 <span data-ttu-id="5dd25-159">[Ajouter de nouveaux éléments à un projet](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="5dd25-159">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 <span data-ttu-id="5dd25-160">[Ajouter des éléments existants à un projet](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="5dd25-160">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 <span data-ttu-id="5dd25-161">[Modifier l’emplacement par défaut des projets](change-the-default-location-for-projects.md) </span><span class="sxs-lookup"><span data-stu-id="5dd25-161">[Change the Default Location for Projects](change-the-default-location-for-projects.md) </span></span>  
 <span data-ttu-id="5dd25-162">[Supprimer ou supprimer un élément ou un projet](remove-or-delete-an-item-or-project.md) </span><span class="sxs-lookup"><span data-stu-id="5dd25-162">[Remove or Delete an Item or Project](remove-or-delete-an-item-or-project.md) </span></span>  
 [<span data-ttu-id="5dd25-163">Supprimer une solution</span><span class="sxs-lookup"><span data-stu-id="5dd25-163">Delete a Solution</span></span>](delete-a-solution.md)  
  
  
