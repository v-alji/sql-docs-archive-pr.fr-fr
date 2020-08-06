---
title: Assistant Conversion de projet de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.migrationwizard.f1
ms.assetid: a192b094-4d0f-4c21-b911-460ec844a49f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c47dc8ed1d0485a62128be732cc34de1dca35740
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605622"
---
# <a name="integration-services-project-conversion-wizard"></a><span data-ttu-id="bf5f0-102">Assistant Conversion de projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="bf5f0-102">Integration Services Project Conversion Wizard</span></span>
  <span data-ttu-id="bf5f0-103">**L’Assistant Conversion de projet Integration Services** convertit un projet en modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-103">The **Integration Services Project Conversion Wizard** converts a project to the project deployment model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf5f0-104">Si le projet contient une ou plusieurs sources de données, les sources de données sont supprimées quand la conversion du projet est terminée.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-104">If the project contains one or more datasources, the datasources are removed when the project conversion is completed.</span></span> <span data-ttu-id="bf5f0-105">Pour créer une connexion à une source de données pouvant être partagée par les packages du projet, ajoutez un gestionnaire de connexions au niveau du projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-105">To create a connection to a data source that can be shared by the packages in the project, add a connection manager at the project level.</span></span> <span data-ttu-id="bf5f0-106">Pour plus d’informations, consultez [Ajouter, supprimer ou partager un gestionnaire de connexions dans un package](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="bf5f0-106">For more information, see [Add, Delete, or Share a Connection Manager in a Package](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span></span>  
  
 <span data-ttu-id="bf5f0-107">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-107">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="bf5f0-108">Ouvrir l'Assistant Conversion de projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="bf5f0-108">Open the Integration Services Project Conversion Wizard</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="bf5f0-109">Définir les options sur la page Localiser les packages</span><span class="sxs-lookup"><span data-stu-id="bf5f0-109">Set Options on the Locate Packages Page</span></span>](#locate)  
  
-   [<span data-ttu-id="bf5f0-110">Définir les options sur la page Sélectionner les package</span><span class="sxs-lookup"><span data-stu-id="bf5f0-110">Set Options on the Select Packages Page</span></span>](#selectPackages)  
  
-   [<span data-ttu-id="bf5f0-111">Définir les options sur la page Sélectionner la destination</span><span class="sxs-lookup"><span data-stu-id="bf5f0-111">Set Options on the Select Destination Page</span></span>](#destination)  
  
-   [<span data-ttu-id="bf5f0-112">Définir les options sur la page Spécifier les propriétés du projet</span><span class="sxs-lookup"><span data-stu-id="bf5f0-112">Set Options on the Specify Project Properties Page</span></span>](#projectProperties)  
  
-   [<span data-ttu-id="bf5f0-113">Définir les options sur la page Mettre à jour la tâche d'exécution de package</span><span class="sxs-lookup"><span data-stu-id="bf5f0-113">Set Options on the Update Execute Package Task Page</span></span>](#executePackage)  
  
-   [<span data-ttu-id="bf5f0-114">Définir les options sur la page Sélectionner les configurations</span><span class="sxs-lookup"><span data-stu-id="bf5f0-114">Set Options on the Select Configurations Page</span></span>](#configurations)  
  
-   [<span data-ttu-id="bf5f0-115">Définir les options sur la page Créer des paramètres</span><span class="sxs-lookup"><span data-stu-id="bf5f0-115">Set Options on the Create Parameters Page</span></span>](#createParameters)  
  
-   [<span data-ttu-id="bf5f0-116">Définir les options sur la page Configurer les paramètres</span><span class="sxs-lookup"><span data-stu-id="bf5f0-116">Set Options on the Configure Parameters Page</span></span>](#configureParameters)  
  
-   [<span data-ttu-id="bf5f0-117">Définir les options de la page Vérifier</span><span class="sxs-lookup"><span data-stu-id="bf5f0-117">Set the Options on the Review page</span></span>](#review)  
  
-   [<span data-ttu-id="bf5f0-118">Définir les options de la page Effectuer la conversion</span><span class="sxs-lookup"><span data-stu-id="bf5f0-118">Set the Options on the Perform Conversion</span></span>](#conversion)  
  
##  <a name="open-the-integration-services-project-conversion-wizard"></a><a name="open_dialog"></a><span data-ttu-id="bf5f0-119">Ouvrir l’Assistant Conversion de projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="bf5f0-119">Open the Integration Services Project Conversion Wizard</span></span>  
 <span data-ttu-id="bf5f0-120">Pour ouvrir l’Assistant **Conversion de projet Integration Services** , effectuez l’une des opérations suivantes.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-120">Do one of the following to open the **Integration Services Project Conversion** Wizard.</span></span>  
  
-   <span data-ttu-id="bf5f0-121">Ouvrez le projet dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], puis dans l’Explorateur de solutions, cliquez avec le bouton droit sur le projet et sélectionnez **Convertir en modèle de déploiement de projet**.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-121">Open the project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], and then in Solution Explorer, right-click the project and click **Convert to Project Deployment Model**.</span></span>  
  
-   <span data-ttu-id="bf5f0-122">Depuis l’Explorateur d’objets dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], cliquez avec le bouton droit sur le nœud **Projets** et sélectionnez **Importer les packages**.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-122">From Object Explorer in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], right-click the **Projects** node and select **Import Packages**.</span></span>  
  
 <span data-ttu-id="bf5f0-123">Selon que vous exécutez **l’Assistant Conversion de projet Integration Services** à partir de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ou à partir de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], l’Assistant effectue différentes tâches de conversion.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-123">Depending on whether you run the **Integration Services Project Conversion Wizard** from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] or from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], the wizard performs different conversion tasks.</span></span> <span data-ttu-id="bf5f0-124">Pour plus d’informations, consultez [Déployer des projets sur le serveur Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="bf5f0-124">For more information, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
##  <a name="set-options-on-the-locate-packages-page"></a><a name="locate"></a><span data-ttu-id="bf5f0-125">Définir les options sur la page localiser les packages</span><span class="sxs-lookup"><span data-stu-id="bf5f0-125">Set Options on the Locate Packages Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf5f0-126">La page **Localiser les packages** est disponible uniquement quand vous exécutez l’Assistant à partir de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf5f0-126">The **Locate Packages** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="bf5f0-127">L’option suivante s’affiche dans la page quand vous sélectionnez **Système de fichiers** dans la liste déroulante **Source** .</span><span class="sxs-lookup"><span data-stu-id="bf5f0-127">The following option displays on the page when you select **File system** in the **Source** drop-down list.</span></span> <span data-ttu-id="bf5f0-128">Sélectionnez cette option quand le package se trouve dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-128">Select this option when the package is resides in the file system.</span></span>  
  
 <span data-ttu-id="bf5f0-129">**Folder**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-129">**Folder**</span></span>  
 <span data-ttu-id="bf5f0-130">Tapez le chemin d’accès du package ou accédez au package en cliquant sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-130">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="bf5f0-131">Les options suivantes s’affichent dans la page quand vous sélectionnez **Magasin de packages SSIS** dans la liste déroulante **Source**.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-131">The following options display on the page when you select **SSIS Package Store** in the **Source** drop-down list.</span></span> <span data-ttu-id="bf5f0-132">Pour plus d’informations sur le magasin de packages, consultez [Gestion de packages &#40;Service SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="bf5f0-132">For more information about the package store, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="bf5f0-133">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-133">**Server**</span></span>  
 <span data-ttu-id="bf5f0-134">Tapez le nom du serveur ou sélectionnez ce dernier.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-134">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="bf5f0-135">**Folder**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-135">**Folder**</span></span>  
 <span data-ttu-id="bf5f0-136">Tapez le chemin d’accès du package ou accédez au package en cliquant sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-136">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="bf5f0-137">Les options suivantes s’affichent dans la page quand vous sélectionnez **Microsoft SQL Server** dans la liste déroulante **Source** .</span><span class="sxs-lookup"><span data-stu-id="bf5f0-137">The following options display on the page when you select **Microsoft SQL Server** in the **Source** drop-down list.</span></span> <span data-ttu-id="bf5f0-138">Sélectionnez cette option quand le package se trouve dans Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf5f0-138">Select this option when the package resides in Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bf5f0-139">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-139">**Server**</span></span>  
 <span data-ttu-id="bf5f0-140">Tapez le nom du serveur ou sélectionnez ce dernier.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-140">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="bf5f0-141">**Utiliser l’authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-141">**Use Windows authentication**</span></span>  
 <span data-ttu-id="bf5f0-142">Le mode d'authentification Microsoft Windows permet à l'utilisateur de se connecter au moyen d'un compte d'utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-142">Microsoft Windows Authentication mode allows a user to connect through a Windows user account.</span></span> <span data-ttu-id="bf5f0-143">Si vous utilisez l'authentification Windows, vous n'avez pas besoin de fournir un nom d'utilisateur ou un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-143">If you use Windows Authentication, you do not need to provide a user name or password.</span></span>  
  
 <span data-ttu-id="bf5f0-144">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-144">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="bf5f0-145">Quand un utilisateur se connecte avec un nom d’accès et un mot de passe spécifiés à partir d’une connexion non autorisée, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentifie la connexion en vérifiant si un compte de connexion [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a été défini et si le mot de passe spécifié correspond à celui enregistré.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-145">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authenticates the connection by checking to see if a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="bf5f0-146">Si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ne possède pas de compte de connexion, l'authentification échoue et un message d'erreur est envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-146">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="bf5f0-147">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-147">**User name**</span></span>  
 <span data-ttu-id="bf5f0-148">Spécifiez un nom d'utilisateur lorsque vous utilisez l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-148">Specify a user name when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="bf5f0-149">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-149">**Password**</span></span>  
 <span data-ttu-id="bf5f0-150">Tapez le mot de passe lorsque vous utilisez l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-150">Provide the password when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="bf5f0-151">**Folder**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-151">**Folder**</span></span>  
 <span data-ttu-id="bf5f0-152">Tapez le chemin d’accès du package ou accédez au package en cliquant sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-152">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
##  <a name="set-options-on-the-select-packages-page"></a><a name="selectPackages"></a><span data-ttu-id="bf5f0-153">Définir les options sur la page Sélectionner les packages</span><span class="sxs-lookup"><span data-stu-id="bf5f0-153">Set Options on the Select Packages Page</span></span>  
 <span data-ttu-id="bf5f0-154">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-154">**Package Name**</span></span>  
 <span data-ttu-id="bf5f0-155">Indique le fichier de package.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-155">Lists the package file.</span></span>  
  
 <span data-ttu-id="bf5f0-156">**État**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-156">**Status**</span></span>  
 <span data-ttu-id="bf5f0-157">Indique si un package est prêt à être converti en modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-157">Indicates whether a package is ready to convert to the project deployment model.</span></span>  
  
 <span data-ttu-id="bf5f0-158">**Message**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-158">**Message**</span></span>  
 <span data-ttu-id="bf5f0-159">Affiche un message associé au package.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-159">Displays a message associated with the package.</span></span>  
  
 <span data-ttu-id="bf5f0-160">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-160">**Password**</span></span>  
 <span data-ttu-id="bf5f0-161">Affiche un mot de passe associé au package.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-161">Displays a password associated with the package.</span></span> <span data-ttu-id="bf5f0-162">Le texte du mot de passe est masqué.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-162">The password text is hidden.</span></span>  
  
 <span data-ttu-id="bf5f0-163">**Appliquer à la sélection**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-163">**Apply to selection**</span></span>  
 <span data-ttu-id="bf5f0-164">Cliquez pour appliquer le mot de passe de la zone de texte **Mot de passe** au(x) package(s) sélectionné(s).</span><span class="sxs-lookup"><span data-stu-id="bf5f0-164">Click to apply the password in the **Password** text box, to the selected package or packages.</span></span>  
  
 <span data-ttu-id="bf5f0-165">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-165">**Refresh**</span></span>  
 <span data-ttu-id="bf5f0-166">Actualise la liste des packages.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-166">Refreshes the list of packages.</span></span>  
  
##  <a name="set-options-on-the-select-destination-page"></a><a name="destination"></a><span data-ttu-id="bf5f0-167">Définir les options sur la page Sélectionner la destination</span><span class="sxs-lookup"><span data-stu-id="bf5f0-167">Set Options on the Select Destination Page</span></span>  
 <span data-ttu-id="bf5f0-168">Dans cette page, spécifiez le nom et le chemin d'accès d'un nouveau fichier de déploiement de projet (.ispac) ou sélectionnez un fichier existant.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-168">On this page, specify the name and path for a new project deployment file (.ispac) or select an existing file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf5f0-169">La page **Sélectionner la destination** est disponible uniquement quand vous exécutez l’Assistant à partir de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf5f0-169">The **Select Destination** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="bf5f0-170">**Chemin de sortie**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-170">**Output path**</span></span>  
 <span data-ttu-id="bf5f0-171">Tapez le chemin d’accès du fichier de déploiement ou accédez à ce dernier en cliquant sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-171">Type the path for the deployment file or navigate to the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="bf5f0-172">**Nom du projet**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-172">**Project name**</span></span>  
 <span data-ttu-id="bf5f0-173">Tapez le nom du projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-173">Type the project name.</span></span>  
  
 <span data-ttu-id="bf5f0-174">**Niveau de protection**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-174">**Protection level**</span></span>  
 <span data-ttu-id="bf5f0-175">Sélectionnez le niveau de protection.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-175">Select the protection level.</span></span> <span data-ttu-id="bf5f0-176">Pour plus d'informations, consultez [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="bf5f0-176">For more information, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="bf5f0-177">**Description du projet**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-177">**Project description**</span></span>  
 <span data-ttu-id="bf5f0-178">Tapez une description facultative du projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-178">Type an optional description for the project.</span></span>  
  
##  <a name="set-options-on-the-specify-project-properties-page"></a><a name="projectProperties"></a><span data-ttu-id="bf5f0-179">Définir les options sur la page spécifier les propriétés du projet</span><span class="sxs-lookup"><span data-stu-id="bf5f0-179">Set Options on the Specify Project Properties Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf5f0-180">La page **Spécifier les propriétés du projet** est disponible uniquement quand vous exécutez l’Assistant à partir de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf5f0-180">The **Specify Project Properties** page is available only when you run the wizard from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="bf5f0-181">**Nom du projet**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-181">**Project name**</span></span>  
 <span data-ttu-id="bf5f0-182">Indique le nom du projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-182">Lists the project name.</span></span>  
  
 <span data-ttu-id="bf5f0-183">**Niveau de protection**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-183">**Protection level**</span></span>  
 <span data-ttu-id="bf5f0-184">Sélectionnez le niveau de protection des packages contenus dans le projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-184">Select a protection level for the packages contained in the project.</span></span> <span data-ttu-id="bf5f0-185">Pour plus d’informations sur les niveaux de protection, consultez [Contrôle d’accès pour les données sensibles présentes dans les packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="bf5f0-185">For more information about protection levels, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="bf5f0-186">**Description du projet**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-186">**Project description**</span></span>  
 <span data-ttu-id="bf5f0-187">Si vous le souhaitez, tapez une description du projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-187">Type an optional project description.</span></span>  
  
##  <a name="set-options-on-the-update-execute-package-task-page"></a><a name="executePackage"></a><span data-ttu-id="bf5f0-188">Définir les options sur la page mettre à jour la tâche d’exécution de package</span><span class="sxs-lookup"><span data-stu-id="bf5f0-188">Set Options on the Update Execute Package Task Page</span></span>  
 <span data-ttu-id="bf5f0-189">Mettez à jour les tâches d'exécution de package contenues dans les packages pour utiliser une référence basée sur un projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-189">Update Execute Package Tasks contain in the packages, to use a project-based reference.</span></span> <span data-ttu-id="bf5f0-190">Pour plus d'informations, consultez [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="bf5f0-190">For more information, see [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span></span>  
  
 <span data-ttu-id="bf5f0-191">**Package parent**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-191">**Parent Package**</span></span>  
 <span data-ttu-id="bf5f0-192">Indique le nom du package qui exécute le package enfant à l'aide de la tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-192">Lists the name of the package that executes the child package using the Execute Package task.</span></span>  
  
 <span data-ttu-id="bf5f0-193">**Nom de la tâche**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-193">**Task name**</span></span>  
 <span data-ttu-id="bf5f0-194">Indique le nom de la tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-194">Lists the name of the Execute Package task.</span></span>  
  
 <span data-ttu-id="bf5f0-195">**Référence d'origine**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-195">**Original reference**</span></span>  
 <span data-ttu-id="bf5f0-196">Indique le chemin d'accès actuel du package enfant.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-196">Lists the current path of the child package.</span></span>  
  
 <span data-ttu-id="bf5f0-197">**Affecter une référence**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-197">**Assign reference**</span></span>  
 <span data-ttu-id="bf5f0-198">Sélectionnez un package enfant stocké dans le projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-198">Select a child package stored in the project.</span></span>  
  
##  <a name="set-options-on-the-select-configurations-page"></a><a name="configurations"></a><span data-ttu-id="bf5f0-199">Définir les options sur la page Sélectionner les configurations</span><span class="sxs-lookup"><span data-stu-id="bf5f0-199">Set Options on the Select Configurations Page</span></span>  
 <span data-ttu-id="bf5f0-200">Sélectionnez les configurations de package que vous souhaitez remplacer par des paramètres.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-200">Select the package configurations that you want to replace with parameters.</span></span>  
  
 <span data-ttu-id="bf5f0-201">**Package**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-201">**Package**</span></span>  
 <span data-ttu-id="bf5f0-202">Indique le fichier de package.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-202">Lists the package file.</span></span>  
  
 <span data-ttu-id="bf5f0-203">**Type**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-203">**Type**</span></span>  
 <span data-ttu-id="bf5f0-204">Indique le type de configuration, par exemple un fichier de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-204">Lists the type of configuration, such as an XML configuration file.</span></span>  
  
 <span data-ttu-id="bf5f0-205">**Chaîne de configuration**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-205">**Configuration String**</span></span>  
 <span data-ttu-id="bf5f0-206">Indique le chemin d'accès du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-206">Lists the path of the configuration file.</span></span>  
  
 <span data-ttu-id="bf5f0-207">**État**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-207">**Status**</span></span>  
 <span data-ttu-id="bf5f0-208">Affiche un message d'état pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-208">Displays a status message for the configuration.</span></span> <span data-ttu-id="bf5f0-209">Cliquez sur le message pour afficher l'intégralité du texte du message.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-209">Click the message to view the entire message text.</span></span>  
  
 <span data-ttu-id="bf5f0-210">**Ajouter des configurations**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-210">**Add Configurations**</span></span>  
 <span data-ttu-id="bf5f0-211">Ajoutez les configurations de package contenues dans d'autres projets à la liste des configurations disponibles que vous souhaitez remplacer à l'aide de paramètres.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-211">Add package configurations contained in other projects to the list of available configurations that you want to replace with parameters.</span></span> <span data-ttu-id="bf5f0-212">Vous pouvez sélectionner des configurations stockées dans un système de fichiers ou dans SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-212">You can select configurations stored in a file system or stored in SQL Server.</span></span>  
  
 <span data-ttu-id="bf5f0-213">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-213">**Refresh**</span></span>  
 <span data-ttu-id="bf5f0-214">Cliquez pour actualiser la liste des configurations.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-214">Click to refresh the list of configurations.</span></span>  
  
 <span data-ttu-id="bf5f0-215">**Supprimer les configurations de tous les packages après la conversion**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-215">**Remove configurations from all packages after conversion**</span></span>  
 <span data-ttu-id="bf5f0-216">Il est recommandé de supprimer toutes les configurations de projet en sélectionnant cette option.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-216">It is recommended that you remove all configurations from the project by selecting this option.</span></span>  
  
 <span data-ttu-id="bf5f0-217">Si vous ne sélectionnez pas cette option, seules les configurations que vous avez sélectionnées pour remplacement à l’aide de paramètres sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-217">If you don't select this option, only the configurations that you selected to replace with parameters are removed.</span></span>  
  
##  <a name="set-options-on-the-create-parameters-page"></a><a name="createParameters"></a><span data-ttu-id="bf5f0-218">Définir les options sur la page créer des paramètres</span><span class="sxs-lookup"><span data-stu-id="bf5f0-218">Set Options on the Create Parameters Page</span></span>  
 <span data-ttu-id="bf5f0-219">Sélectionnez le nom et l'étendue du paramètre pour chaque propriété de configuration.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-219">Select the parameter name and scope for each configuration property.</span></span>  
  
 <span data-ttu-id="bf5f0-220">**Package**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-220">**Package**</span></span>  
 <span data-ttu-id="bf5f0-221">Indique le fichier de package.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-221">Lists the package file.</span></span>  
  
 <span data-ttu-id="bf5f0-222">**Nom du paramètre**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-222">**Parameter Name**</span></span>  
 <span data-ttu-id="bf5f0-223">Indique le nom du paramètre.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-223">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="bf5f0-224">**Portée**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-224">**Scope**</span></span>  
 <span data-ttu-id="bf5f0-225">Sélectionnez l'étendue du paramètre, package ou projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-225">Select the scope of the parameter, either package or project.</span></span>  
  
##  <a name="set-options-on-the-configure-parameters-page"></a><a name="configureParameters"></a><span data-ttu-id="bf5f0-226">Définir les options sur la page Configurer les paramètres</span><span class="sxs-lookup"><span data-stu-id="bf5f0-226">Set Options on the Configure Parameters Page</span></span>  
 <span data-ttu-id="bf5f0-227">**Nom**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-227">**Name**</span></span>  
 <span data-ttu-id="bf5f0-228">Indique le nom du paramètre.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-228">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="bf5f0-229">**Portée**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-229">**Scope**</span></span>  
 <span data-ttu-id="bf5f0-230">Indique l'étendue du paramètre.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-230">Lists the scope of the parameter.</span></span>  
  
 <span data-ttu-id="bf5f0-231">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-231">**Value**</span></span>  
 <span data-ttu-id="bf5f0-232">Indique la valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-232">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="bf5f0-233">Cliquez sur le bouton de sélection en regard du champ de valeur pour configurer les propriétés du paramètre.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-233">Click the ellipsis button next to the value field to configure the parameter properties.</span></span>  
  
 <span data-ttu-id="bf5f0-234">Dans la boîte de dialogue **Définir les détails du paramètre** , vous pouvez modifier la valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-234">In the **Set Parameter Details** dialog box, you can edit the parameter value.</span></span> <span data-ttu-id="bf5f0-235">Vous pouvez également spécifier si la valeur de paramètre doit être fournie lorsque vous exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-235">You can also specify whether the parameter value must be provided when you run the package.</span></span>  
  
 <span data-ttu-id="bf5f0-236">Vous pouvez modifier la valeur dans la page **Paramètres** de la boîte de dialogue **Configurer** de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]en cliquant sur le bouton Parcourir en regard du paramètre.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-236">You can modify value in the **Parameters** page of the **Configure** dialog box in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], by clicking the browse button next to the parameter.</span></span> <span data-ttu-id="bf5f0-237">La boîte de dialogue **Définir la valeur du paramètre** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-237">The **Set Parameter Value** dialog box appears.</span></span>  
  
 <span data-ttu-id="bf5f0-238">La boîte de dialogue **Définir les détails du paramètre** indique également le type de données de la valeur de paramètre et l’origine du paramètre.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-238">The **Set Parameter Details** dialog box also lists the data type of the parameter value and the origin of the parameter.</span></span>  
  
##  <a name="set-the-options-on-the-review-page"></a><a name="review"></a><span data-ttu-id="bf5f0-239">Définir les options de la page vérifier</span><span class="sxs-lookup"><span data-stu-id="bf5f0-239">Set the Options on the Review page</span></span>  
 <span data-ttu-id="bf5f0-240">Utilisez la page **vérifier** pour confirmer les options que vous avez sélectionnées pour la conversion du projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-240">Use the **Review** page to confirm the options that you've selected for the conversion of the project.</span></span>  
  
 <span data-ttu-id="bf5f0-241">**Précédent**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-241">**Previous**</span></span>  
 <span data-ttu-id="bf5f0-242">Cliquez pour modifier une option.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-242">Click to change an option.</span></span>  
  
 <span data-ttu-id="bf5f0-243">**Convert**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-243">**Convert**</span></span>  
 <span data-ttu-id="bf5f0-244">Cliquez pour convertir le projet en modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-244">Click to convert the project to the project deployment model.</span></span>  
  
##  <a name="set-the-options-on-the-perform-conversion"></a><a name="conversion"></a><span data-ttu-id="bf5f0-245">Définir les options de l’option effectuer la conversion</span><span class="sxs-lookup"><span data-stu-id="bf5f0-245">Set the Options on the Perform Conversion</span></span>  
 <span data-ttu-id="bf5f0-246">La page Effectuer la conversion indique l'état de la conversion du projet.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-246">The Perform Conversion page shows status of the project conversion.</span></span>  
  
 <span data-ttu-id="bf5f0-247">**Action**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-247">**Action**</span></span>  
 <span data-ttu-id="bf5f0-248">Indique une étape de conversion spécifique.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-248">Lists a specific conversion step.</span></span>  
  
 <span data-ttu-id="bf5f0-249">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-249">**Result**</span></span>  
 <span data-ttu-id="bf5f0-250">Indique l'état de chaque étape de conversion.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-250">Lists the status of each conversion step.</span></span> <span data-ttu-id="bf5f0-251">Pour plus d'informations, cliquez sur le message d'état.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-251">Click the status message for more information.</span></span>  
  
 <span data-ttu-id="bf5f0-252">La conversion de projet n'est pas enregistrée tant que le projet n'est pas enregistré dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf5f0-252">The project conversion is not saved until the project is saved in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="bf5f0-253">**Enregistrer le rapport**</span><span class="sxs-lookup"><span data-stu-id="bf5f0-253">**Save report**</span></span>  
 <span data-ttu-id="bf5f0-254">Cliquez pour enregistrer un résumé de la conversion du projet dans un fichier .xml.</span><span class="sxs-lookup"><span data-stu-id="bf5f0-254">Click to save a summary of the project conversion in an .xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5f0-255">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf5f0-255">See Also</span></span>  
 [<span data-ttu-id="bf5f0-256">Déployer des projets sur le serveur Integration Services</span><span class="sxs-lookup"><span data-stu-id="bf5f0-256">Deploy Projects to Integration Services Server</span></span>](../../2014/integration-services/deploy-projects-to-integration-services-server.md)  
  
  
