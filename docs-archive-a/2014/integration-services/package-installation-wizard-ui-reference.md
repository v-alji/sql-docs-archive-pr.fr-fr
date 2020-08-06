---
title: Informations de référence sur l’interface utilisateur de l’Assistant Installation de package | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.deploymentwizard.confirminstallation.f1
- sql12.dts.deploymentwizard.deploydtspackages.f1
- sql12.dts.deploymentwizard.selectinstfolder.f1
- sql12.dts.deploymentwizard.specifytargetsqlserver.f1
- sql12.dts.deploymentwizard.welcome.f1
- sql12.dts.deploymentwizard.finish.f1
- sql12.dts.deploymentwizard.configurepackages.f1
- sql12.dts.deploymentwizard.packagevalidation.f1
helpviewer_keywords:
- Package Installer Wizard
ms.assetid: 6fca44d9-5001-4644-bcf3-c2d10a674b97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c15b423c66891e799f7f8dcd27682036dce6d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696960"
---
# <a name="package-installation-wizard-ui-reference"></a><span data-ttu-id="c6869-102">Référence de l'interface utilisateur de l'Assistant Installation de package</span><span class="sxs-lookup"><span data-stu-id="c6869-102">Package Installation Wizard UI Reference</span></span>
  <span data-ttu-id="c6869-103">**L’Assistant Installation de package** permet de déployer un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , dont les packages et les divers fichiers qu’il contient, ainsi que les dépendances de package éventuelles.</span><span class="sxs-lookup"><span data-stu-id="c6869-103">Use the **Package Installation Wizard** to deploy a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, including the packages and miscellaneous files it contains and any package dependencies.</span></span>  
  
 <span data-ttu-id="c6869-104">Avant de déployer des packages, vous pouvez créer des configurations, puis déployer ces dernières avec les packages.</span><span class="sxs-lookup"><span data-stu-id="c6869-104">Before you deploy packages, you can create configurations and then deploy them with the packages.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="c6869-105">utilise les configurations pour mettre à jour dynamiquement les propriétés des packages et les objets de package au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="c6869-105">uses configurations to dynamically update properties of packages and package objects at run time.</span></span> <span data-ttu-id="c6869-106">Par exemple, il est possible de définir dynamiquement à l'exécution la chaîne de connexion d'une connexion OLE DB en fournissant une configuration qui mappe une valeur avec la propriété contenant la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="c6869-106">For example, the connection string of an OLE DB connection can be set dynamically at run time by providing a configuration that maps a value to the property that contains the connection string.</span></span>  
  
 <span data-ttu-id="c6869-107">Vous ne pouvez pas exécuter l'Assistant Installation de package tant que vous n'avez pas généré un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et créé un utilitaire de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c6869-107">You cannot run the Package Installation Wizard until you build an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and create a deployment utility.</span></span> <span data-ttu-id="c6869-108">Pour plus d’informations, consultez [Déployer des packages à l’aide de l’utilitaire de déploiement](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="c6869-108">For more information, see [Deploy Packages by Using the Deployment Utility](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="c6869-109">Les sections suivantes décrivent les pages de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="c6869-109">The following sections describe pages of the wizard.</span></span>  
  
## <a name="welcome-to-the-package-installation-wizard-page"></a><span data-ttu-id="c6869-110">Page Assistant Installation de package</span><span class="sxs-lookup"><span data-stu-id="c6869-110">Welcome to the Package Installation Wizard Page</span></span>  
 <span data-ttu-id="c6869-111">**L’Assistant Installation de package** vous permet de déployer un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pour lequel vous avez créé un utilitaire de déploiement de package.</span><span class="sxs-lookup"><span data-stu-id="c6869-111">Use the **Package Installation Wizard** to deploy an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you built a package deployment utility.</span></span>  
  
 <span data-ttu-id="c6869-112">**Ne plus afficher cette page de démarrage**</span><span class="sxs-lookup"><span data-stu-id="c6869-112">**Do not show this starting page again**</span></span>  
 <span data-ttu-id="c6869-113">Ignorer la page de démarrage à la prochaine exécution de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="c6869-113">Select to skip the starting page when you run the wizard again.</span></span>  
  
 <span data-ttu-id="c6869-114">**Next**</span><span class="sxs-lookup"><span data-stu-id="c6869-114">**Next**</span></span>  
 <span data-ttu-id="c6869-115">Permet de passer à la page suivante de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="c6869-115">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="c6869-116">**Terminer**</span><span class="sxs-lookup"><span data-stu-id="c6869-116">**Finish**</span></span>  
 <span data-ttu-id="c6869-117">Passez directement à la page Fin de l'Assistant Installation de package.</span><span class="sxs-lookup"><span data-stu-id="c6869-117">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="c6869-118">Utilisez cette option si vous êtes revenu en arrière dans les pages de l'Assistant pour examiner vos choix et si vous avez spécifié toutes les options obligatoires.</span><span class="sxs-lookup"><span data-stu-id="c6869-118">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="configure-packages-page"></a><span data-ttu-id="c6869-119">Page Configurer les packages</span><span class="sxs-lookup"><span data-stu-id="c6869-119">Configure Packages Page</span></span>  
 <span data-ttu-id="c6869-120">Utilisez la page **Configurer les packages** pour modifier la configuration des packages.</span><span class="sxs-lookup"><span data-stu-id="c6869-120">Use the **Configure Packages** page to edit package configurations.</span></span>  
  
### <a name="options"></a><span data-ttu-id="c6869-121">Options</span><span class="sxs-lookup"><span data-stu-id="c6869-121">Options</span></span>  
 <span data-ttu-id="c6869-122">**Fichier de configuration**</span><span class="sxs-lookup"><span data-stu-id="c6869-122">**Configuration file**</span></span>  
 <span data-ttu-id="c6869-123">Modifie le contenu d'un fichier de configuration sélectionné dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c6869-123">Edit the contents of a configuration file by selecting the file from the list.</span></span>  
  
 <span data-ttu-id="c6869-124">**Rubriques connexes :** [Créer des configurations de package](../../2014/integration-services/create-package-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="c6869-124">**Related Topics:** [Create Package Configurations](../../2014/integration-services/create-package-configurations.md)</span></span>  
  
 <span data-ttu-id="c6869-125">**Chemin d’accès**</span><span class="sxs-lookup"><span data-stu-id="c6869-125">**Path**</span></span>  
 <span data-ttu-id="c6869-126">Affiche le chemin d'accès de la propriété à configurer.</span><span class="sxs-lookup"><span data-stu-id="c6869-126">View the path of the property to be configured.</span></span>  
  
 <span data-ttu-id="c6869-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="c6869-127">**Type**</span></span>  
 <span data-ttu-id="c6869-128">Affiche le type des données de la propriété.</span><span class="sxs-lookup"><span data-stu-id="c6869-128">View the data type of the property.</span></span>  
  
 <span data-ttu-id="c6869-129">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="c6869-129">**Value**</span></span>  
 <span data-ttu-id="c6869-130">Spécifiez la valeur de la configuration.</span><span class="sxs-lookup"><span data-stu-id="c6869-130">Specify the value of the configuration.</span></span>  
  
 <span data-ttu-id="c6869-131">**Next**</span><span class="sxs-lookup"><span data-stu-id="c6869-131">**Next**</span></span>  
 <span data-ttu-id="c6869-132">Permet de passer à la page suivante de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="c6869-132">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="c6869-133">**Terminer**</span><span class="sxs-lookup"><span data-stu-id="c6869-133">**Finish**</span></span>  
 <span data-ttu-id="c6869-134">Passez directement à la page Fin de l'Assistant Installation de package.</span><span class="sxs-lookup"><span data-stu-id="c6869-134">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="c6869-135">Utilisez cette option si vous êtes revenu en arrière dans les pages de l'Assistant pour examiner vos choix et si vous avez spécifié toutes les options obligatoires.</span><span class="sxs-lookup"><span data-stu-id="c6869-135">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="confirm-installation-page"></a><span data-ttu-id="c6869-136">Page Confirmer l'installation</span><span class="sxs-lookup"><span data-stu-id="c6869-136">Confirm Installation Page</span></span>  
 <span data-ttu-id="c6869-137">La page **Confirmer l’installation** permet de lancer l’installation de packages, de visualiser l’état et les informations que l’Assistant utilise pour installer les fichiers du projet spécifié.</span><span class="sxs-lookup"><span data-stu-id="c6869-137">Use the **Confirm Installation** page to start the installation of packages, to view the status, and to view the information that the wizard will use to install files from the specified project.</span></span>  
  
 <span data-ttu-id="c6869-138">**Next**</span><span class="sxs-lookup"><span data-stu-id="c6869-138">**Next**</span></span>  
 <span data-ttu-id="c6869-139">Installe les packages et leurs dépendances et passe à la page suivante de l'Assistant une fois l'installation terminée.</span><span class="sxs-lookup"><span data-stu-id="c6869-139">Install the packages and their dependencies and go to the next wizard page when installation is completed.</span></span>  
  
 <span data-ttu-id="c6869-140">**État**</span><span class="sxs-lookup"><span data-stu-id="c6869-140">**Status**</span></span>  
 <span data-ttu-id="c6869-141">Affiche la progression de l'installation du package.</span><span class="sxs-lookup"><span data-stu-id="c6869-141">Shows the progress of the package installation.</span></span>  
  
 <span data-ttu-id="c6869-142">**Terminer**</span><span class="sxs-lookup"><span data-stu-id="c6869-142">**Finish**</span></span>  
 <span data-ttu-id="c6869-143">Accédez à la page Fin de l'Assistant Installation de package.</span><span class="sxs-lookup"><span data-stu-id="c6869-143">Go to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="c6869-144">Utilisez cette option si vous êtes revenu en arrière dans les pages de l'Assistant pour revoir vos choix et si vous avez spécifié toutes les options indispensables.</span><span class="sxs-lookup"><span data-stu-id="c6869-144">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all the required options.</span></span>  
  
## <a name="deploy-ssis-packages-page"></a><span data-ttu-id="c6869-145">Page Déployer les packages SSIS</span><span class="sxs-lookup"><span data-stu-id="c6869-145">Deploy SSIS Packages Page</span></span>  
 <span data-ttu-id="c6869-146">La page **Déployer les packages SSIS** permet d’indiquer à quel emplacement les packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et leurs dépendances doivent être installés.</span><span class="sxs-lookup"><span data-stu-id="c6869-146">Use the **Deploy SSIS Packages** page to specify where to install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="c6869-147">Options</span><span class="sxs-lookup"><span data-stu-id="c6869-147">Options</span></span>  
 <span data-ttu-id="c6869-148">**Déploiement sur le système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="c6869-148">**File system deployment**</span></span>  
 <span data-ttu-id="c6869-149">Déploie les packages et leurs dépendances dans un dossier du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c6869-149">Deploy packages and dependencies in a specified folder in the file system.</span></span>  
  
 <span data-ttu-id="c6869-150">**Déploiement sur SQL Server**</span><span class="sxs-lookup"><span data-stu-id="c6869-150">**SQL Server deployment**</span></span>  
 <span data-ttu-id="c6869-151">Déploie les packages et leurs dépendances dans une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6869-151">Deploy packages and dependencies in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c6869-152">Utilisez cette option si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] partage des packages entre serveurs.</span><span class="sxs-lookup"><span data-stu-id="c6869-152">Use this option if [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shares packages between servers.</span></span> <span data-ttu-id="c6869-153">Toutes les dépendances de package sont installées dans le dossier spécifié du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c6869-153">Any package dependencies are installed in the specified folder in the file system.</span></span>  
  
 <span data-ttu-id="c6869-154">**Valider les packages après l'installation**</span><span class="sxs-lookup"><span data-stu-id="c6869-154">**Validate packages after installation**</span></span>  
 <span data-ttu-id="c6869-155">Indique si les packages doivent être validés après installation.</span><span class="sxs-lookup"><span data-stu-id="c6869-155">Indicate whether to validate packages after installation.</span></span>  
  
 <span data-ttu-id="c6869-156">**Next**</span><span class="sxs-lookup"><span data-stu-id="c6869-156">**Next**</span></span>  
 <span data-ttu-id="c6869-157">Permet de passer à la page suivante de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="c6869-157">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="c6869-158">**Terminer**</span><span class="sxs-lookup"><span data-stu-id="c6869-158">**Finish**</span></span>  
 <span data-ttu-id="c6869-159">Passez directement à la page Fin de l'Assistant Installation de package.</span><span class="sxs-lookup"><span data-stu-id="c6869-159">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="c6869-160">Utilisez cette option si vous êtes revenu en arrière dans les pages de l'Assistant pour examiner vos choix et si vous avez spécifié toutes les options obligatoires.</span><span class="sxs-lookup"><span data-stu-id="c6869-160">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="packages-validation-page"></a><span data-ttu-id="c6869-161">Page Validation des packages</span><span class="sxs-lookup"><span data-stu-id="c6869-161">Packages Validation Page</span></span>  
 <span data-ttu-id="c6869-162">La page **Validation des packages** permet d’afficher et de suivre la progression de la validation des packages et les résultats de cette validation.</span><span class="sxs-lookup"><span data-stu-id="c6869-162">Use the **Packages Validation** page to view the progress and results of the package validation.</span></span>  
  
 <span data-ttu-id="c6869-163">**Next**</span><span class="sxs-lookup"><span data-stu-id="c6869-163">**Next**</span></span>  
 <span data-ttu-id="c6869-164">Permet de passer à la page suivante de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="c6869-164">Go to the next page in the wizard.</span></span>  
  
## <a name="select-installation-folder-page"></a><span data-ttu-id="c6869-165">Page Sélectionner le dossier d'installation</span><span class="sxs-lookup"><span data-stu-id="c6869-165">Select Installation Folder Page</span></span>  
 <span data-ttu-id="c6869-166">La page **Sélectionner le dossier d’installation** permet de définir le dossier du système de fichiers dans lequel les packages et leurs dépendances sont installés.</span><span class="sxs-lookup"><span data-stu-id="c6869-166">Use the **Select Installation Folder** page to specify the file system folder in which to install the packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="c6869-167">Options</span><span class="sxs-lookup"><span data-stu-id="c6869-167">Options</span></span>  
 <span data-ttu-id="c6869-168">**Folder**</span><span class="sxs-lookup"><span data-stu-id="c6869-168">**Folder**</span></span>  
 <span data-ttu-id="c6869-169">Définissez le chemin d'accès et le dossier de copie du package et de ses dépendances.</span><span class="sxs-lookup"><span data-stu-id="c6869-169">Specify the path and folder in which to copy the package and its dependencies.</span></span>  
  
 <span data-ttu-id="c6869-170">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="c6869-170">**Browse**</span></span>  
 <span data-ttu-id="c6869-171">Accédez au dossier cible via la boîte de dialogue **Rechercher un dossier** .</span><span class="sxs-lookup"><span data-stu-id="c6869-171">Browse to the target folder by using the **Browse For Folder** dialog box.</span></span>  
  
 <span data-ttu-id="c6869-172">**Next**</span><span class="sxs-lookup"><span data-stu-id="c6869-172">**Next**</span></span>  
 <span data-ttu-id="c6869-173">Permet de passer à la page suivante de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="c6869-173">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="c6869-174">**Terminer**</span><span class="sxs-lookup"><span data-stu-id="c6869-174">**Finish**</span></span>  
 <span data-ttu-id="c6869-175">Passez directement à la page Fin de l'Assistant Installation de package.</span><span class="sxs-lookup"><span data-stu-id="c6869-175">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="c6869-176">Utilisez cette option si vous voulez revenir dans les pages de l'Assistant pour vérifier vos choix et si vous avez défini toutes les options nécessaires.</span><span class="sxs-lookup"><span data-stu-id="c6869-176">Use this option if you have backtracked through the wizard pages to revise your choices and if have specified all of the required options.</span></span>  
  
## <a name="specify-target-sql-server-page"></a><span data-ttu-id="c6869-177">Page Spécifier le serveur SQL cible</span><span class="sxs-lookup"><span data-stu-id="c6869-177">Specify Target SQL Server Page</span></span>  
 <span data-ttu-id="c6869-178">La page **Spécifier le serveur SQL cible** permet de spécifier les options de déploiement du package dans une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6869-178">Use the **Specify Target SQL Server** page to specify options for deploying the package to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="options"></a><span data-ttu-id="c6869-179">Options</span><span class="sxs-lookup"><span data-stu-id="c6869-179">Options</span></span>  
 <span data-ttu-id="c6869-180">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="c6869-180">**Server name**</span></span>  
 <span data-ttu-id="c6869-181">Permet de spécifier le nom du serveur pour lequel doit s'effectuer le déploiement des packages.</span><span class="sxs-lookup"><span data-stu-id="c6869-181">Specify the name of the server to deploy the packages to.</span></span>  
  
 <span data-ttu-id="c6869-182">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="c6869-182">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="c6869-183">Permet d'indiquer si la méthode d'authentification Windows doit être utilisée pour ouvrir une session sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c6869-183">Specify whether to use Windows Authentication to log on to the server.</span></span> <span data-ttu-id="c6869-184">L'authentification Windows est recommandée pour renforcer la sécurité.</span><span class="sxs-lookup"><span data-stu-id="c6869-184">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="c6869-185">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="c6869-185">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="c6869-186">Permet d'indiquer si la méthode d'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] doit être utilisée pour ouvrir une session sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c6869-186">Specify whether the package should use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to log on to the server.</span></span> <span data-ttu-id="c6869-187">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vous devez fournir un nom d’utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c6869-187">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="c6869-188">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="c6869-188">**User name**</span></span>  
 <span data-ttu-id="c6869-189">Indique un nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6869-189">Specify a user name.</span></span>  
  
 <span data-ttu-id="c6869-190">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="c6869-190">**Password**</span></span>  
 <span data-ttu-id="c6869-191">Permet de spécifier un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c6869-191">Specify a password.</span></span>  
  
 <span data-ttu-id="c6869-192">**Chemin d'accès au package**</span><span class="sxs-lookup"><span data-stu-id="c6869-192">**Package path**</span></span>  
 <span data-ttu-id="c6869-193">Spécifiez le nom du dossier logique ou entrez « / » pour le dossier par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6869-193">Specify the name of the logical folder, or enter "/" for the default folder.</span></span>  
  
 <span data-ttu-id="c6869-194">Pour sélectionner le dossier dans la boîte de dialogue **Package SSIS** , cliquez sur Parcourir (...). La boîte de dialogue ne fournit toutefois pas de moyen de sélectionner le dossier par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6869-194">To select the folder in the **SSIS Package** dialog box, click browse (...). However, the dialog box does not provide a means to select the default folder.</span></span> <span data-ttu-id="c6869-195">Si vous souhaitez utiliser le dossier par défaut, vous devez entrer « / » dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="c6869-195">If you want to use the default folder, you have to enter "/" in the text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6869-196">Si vous n’entrez pas de chemin de package valide, le message d’erreur suivant apparaît : « Un ou plusieurs arguments ne sont pas valides ».</span><span class="sxs-lookup"><span data-stu-id="c6869-196">If you do not enter a valid package path, the following error message appears: "One or more arguments are invalid."</span></span>  
  
 <span data-ttu-id="c6869-197">**Se fier au serveur pour le chiffrement**</span><span class="sxs-lookup"><span data-stu-id="c6869-197">**Rely on server storage for encryption**</span></span>  
 <span data-ttu-id="c6869-198">Permet d’utiliser les fonctionnalités de sécurité du [!INCLUDE[ssDE](../includes/ssde-md.md)] pour sécuriser les packages.</span><span class="sxs-lookup"><span data-stu-id="c6869-198">Select to use security features of the [!INCLUDE[ssDE](../includes/ssde-md.md)] to help secure the packages.</span></span>  
  
 <span data-ttu-id="c6869-199">**Next**</span><span class="sxs-lookup"><span data-stu-id="c6869-199">**Next**</span></span>  
 <span data-ttu-id="c6869-200">Permet de passer à la page suivante de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="c6869-200">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="c6869-201">**Terminer**</span><span class="sxs-lookup"><span data-stu-id="c6869-201">**Finish**</span></span>  
 <span data-ttu-id="c6869-202">Passez directement à la page Fin de l'Assistant Installation de package.</span><span class="sxs-lookup"><span data-stu-id="c6869-202">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="c6869-203">Utilisez cette option si vous êtes revenu en arrière dans les pages de l'Assistant pour examiner vos choix et si vous avez spécifié toutes les options obligatoires.</span><span class="sxs-lookup"><span data-stu-id="c6869-203">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="finish-the-package-installation-page"></a><span data-ttu-id="c6869-204">Page Fin de l'Assistant Installation de package</span><span class="sxs-lookup"><span data-stu-id="c6869-204">Finish the Package Installation Page</span></span>  
 <span data-ttu-id="c6869-205">La page **Fin de l’Assistant Installation de package** permet d’obtenir un résumé des résultats de l’installation des packages.</span><span class="sxs-lookup"><span data-stu-id="c6869-205">Use the **Finish the Package Installation Wizard** page to view a summary of the package installation results.</span></span> <span data-ttu-id="c6869-206">Cette page fournit des détails comme le nom du projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] déployé, les packages installés, les fichiers de configuration et l’emplacement de l’installation.</span><span class="sxs-lookup"><span data-stu-id="c6869-206">This page provides details such as the name of the deployed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, the packages that were installed, the configuration files, and the installation location.</span></span>  
  
 <span data-ttu-id="c6869-207">**Terminer**</span><span class="sxs-lookup"><span data-stu-id="c6869-207">**Finish**</span></span>  
 <span data-ttu-id="c6869-208">Pour quitter l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="c6869-208">Exit the wizard by clicking **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6869-209">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6869-209">See Also</span></span>  
 [<span data-ttu-id="c6869-210">Déploiement de packages &#40;&#41;SSIS</span><span class="sxs-lookup"><span data-stu-id="c6869-210">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
