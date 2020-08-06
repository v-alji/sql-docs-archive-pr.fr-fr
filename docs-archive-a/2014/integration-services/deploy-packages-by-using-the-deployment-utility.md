---
title: Déployer des packages à l’aide de l’utilitaire de déploiement | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], installing
- installing packages
- dependencies [Integration Services]
- deploying packages [Integration Services], installing
ms.assetid: eaf4b56e-2023-4d17-971c-703031da758c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a09ad307dc0215fca679cfb1ef5a37031f951caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703223"
---
# <a name="deploy-packages-by-using-the-deployment-utility"></a><span data-ttu-id="b7e56-102">Déployer des packages à l’aide de l’utilitaire de déploiement</span><span class="sxs-lookup"><span data-stu-id="b7e56-102">Deploy Packages by Using the Deployment Utility</span></span>
  <span data-ttu-id="b7e56-103">Après avoir créé un utilitaire de déploiement pour installer les packages d’un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur un ordinateur différent de celui sur lequel cet utilitaire a été créé, vous devez d’abord copier le dossier de déploiement vers l’ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="b7e56-103">When you have built a deployment utility to install packages from an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project on a different computer than the one on which the deployment utility was built, you must first copy the deployment folder to the destination computer.</span></span>  
  
 <span data-ttu-id="b7e56-104">Le chemin du dossier de déploiement est spécifié dans la propriété DeploymentOutputPath du projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pour lequel vous avez créé l’utilitaire de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b7e56-104">The path of the deployment folder is specified in the DeploymentOutputPath property of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you created the deployment utility.</span></span> <span data-ttu-id="b7e56-105">Le chemin d’accès par défaut est bin\Deployment, lié au projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7e56-105">The default path is bin\Deployment, relative to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="b7e56-106">Pour plus d’informations, consultez [Créer un utilitaire de déploiement](../../2014/integration-services/create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b7e56-106">For more information, see [Create a Deployment Utility](../../2014/integration-services/create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="b7e56-107">Vous utilisez l'Assistant Installation de package pour installer les packages.</span><span class="sxs-lookup"><span data-stu-id="b7e56-107">You use the Package Installation Wizard to install the packages.</span></span> <span data-ttu-id="b7e56-108">Pour lancer l'Assistant, double-cliquez sur l'utilitaire de déploiement après avoir copié le dossier de déploiement sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b7e56-108">To launch the wizard, double-click the deployment utility file after you have copied the deployment folder to the server.</span></span> <span data-ttu-id="b7e56-109">Le fichier se nomme \<project name>.SSISDeploymentManifest et se trouve dans le dossier de déploiement sur l’ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="b7e56-109">This file is named \<project name>.SSISDeploymentManifest, and can be found in the deployment folder on the destination computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7e56-110">En fonction de la version du package que vous déployez, une erreur risque de se produire si différentes version de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sont installées côte à côte.</span><span class="sxs-lookup"><span data-stu-id="b7e56-110">Depending on the version of the package that you are deploying, you might encounter an error if you have different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installed side-by-side.</span></span> <span data-ttu-id="b7e56-111">Cette erreur vient du fait que l'extension de nom de fichier .SSISDeploymentManifest est la même pour toutes les versions d' [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7e56-111">This error can occur because the .SSISDeploymentManifest file name extension is the same for all versions of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="b7e56-112">Si vous double-cliquez sur le fichier, cela entraîne l’appel du programme d’installation (dtsinstall.exe) correspondant à la version installée en dernier d’ [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], laquelle risque d’être différente de la version du fichier de l’utilitaire de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b7e56-112">Double-clicking the file calls the installer (dtsinstall.exe) for the most recently installed version of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], which might not be the same version as the deployment utility file.</span></span> <span data-ttu-id="b7e56-113">Pour contourner ce problème, exécutez la version appropriée de dtsinstall.exe à partir de la ligne de commande, puis indiquez le chemin d'accès du fichier de l'utilitaire de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b7e56-113">To work around this problem, run the correct version of dtsinstall.exe from the command line, and provide the path of the deployment utility file.</span></span>  
  
 <span data-ttu-id="b7e56-114">L'Assistant Installation de package vous accompagne dans le processus d'installation des packages sur le système de fichiers et sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7e56-114">The Package Installation Wizard guides you through the steps to install packages to the file system or to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b7e56-115">Vous pouvez configurer l'installation de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="b7e56-115">You can configure the installation in the following ways:</span></span>  
  
-   <span data-ttu-id="b7e56-116">Choix du type d'emplacement et emplacement d'installation des packages.</span><span class="sxs-lookup"><span data-stu-id="b7e56-116">Choosing the location type and location to install the packages.</span></span>  
  
-   <span data-ttu-id="b7e56-117">Choix de l'emplacement d'installation des dépendances de package.</span><span class="sxs-lookup"><span data-stu-id="b7e56-117">Choosing location to install package dependencies.</span></span>  
  
-   <span data-ttu-id="b7e56-118">Validation des packages après leur installation sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="b7e56-118">Validating the packages after they are installed on the target server.</span></span>  
  
 <span data-ttu-id="b7e56-119">Les dépendances basées sur les fichiers pour les packages sont toujours installées sur le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="b7e56-119">The file-based dependencies for packages are always installed to the file system.</span></span> <span data-ttu-id="b7e56-120">Si vous installez un package sur le système de fichiers, les dépendances sont installées dans le même dossier que celui indiqué pour le package.</span><span class="sxs-lookup"><span data-stu-id="b7e56-120">If you install a package to the file system, the dependencies are installed in the same folder as the one that you specify for the package.</span></span> <span data-ttu-id="b7e56-121">Si vous installez un package sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vous pouvez spécifier le dossier dans lequel les dépendances basées sur les fichiers seront stockées.</span><span class="sxs-lookup"><span data-stu-id="b7e56-121">If you install a package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify the folder in which to store the file-based dependencies.</span></span>  
  
 <span data-ttu-id="b7e56-122">Si le package comprend des configurations que vous voulez modifier pour qu'elles soient utilisées sur l'ordinateur de destination, vous pouvez mettre à jour les valeurs des propriétés à l'aide de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="b7e56-122">If the package includes configurations that you want to modify for use on the destination computer, you can update the values of the properties by using the wizard.</span></span>  
  
 <span data-ttu-id="b7e56-123">Outre l’installation des packages à l’aide de l’Assistant Installation de package, vous pouvez copier et déplacer des packages à l’aide de l’utilitaire d’invite de commandes **dtutil** .</span><span class="sxs-lookup"><span data-stu-id="b7e56-123">In addition to installing packages by using the Package Installation Wizard, you can copy and move packages by using the **dtutil** command prompt utility.</span></span> <span data-ttu-id="b7e56-124">Pour plus d’informations, consultez [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b7e56-124">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-deploy-packages-to-an-instance-of-sql-server"></a><span data-ttu-id="b7e56-125">Pour déployer des packages sur une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7e56-125">To deploy packages to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="b7e56-126">Ouvrez le dossier de déploiement sur l'ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="b7e56-126">Open the deployment folder on the target computer.</span></span>  
  
2.  <span data-ttu-id="b7e56-127">Double-cliquez sur le fichier manifeste, \<project name>.SSISDeploymentManifest, pour démarrer l’Assistant Installation de package.</span><span class="sxs-lookup"><span data-stu-id="b7e56-127">Double-click the manifest file, \<project name>.SSISDeploymentManifest, to start the Package Installation Wizard.</span></span>  
  
3.  <span data-ttu-id="b7e56-128">Dans la page **Déployer les packages SSIS** , sélectionnez l’option **Déploiement sur SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="b7e56-128">On the **Deploy SSIS Packages** page, select the **SQL Server deployment** option.</span></span>  
  
4.  <span data-ttu-id="b7e56-129">Vous pouvez, si vous le souhaitez, sélectionner **Valider les packages après l’installation** pour valider les packages après qu’ils ont été installés sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="b7e56-129">Optionally, select **Validate packages after installation** to validate packages after they are installed on the target server.</span></span>  
  
5.  <span data-ttu-id="b7e56-130">Dans la page **Spécifier le serveur SQL cible** , spécifiez l’instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sur laquelle les packages doivent être installés et sélectionnez un mode d’authentification.</span><span class="sxs-lookup"><span data-stu-id="b7e56-130">On the **Specify Target SQL Server** page, specify the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to install the packages to and select an authentication mode.</span></span> <span data-ttu-id="b7e56-131">Si vous sélectionnez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vous devez fournir un nom d’utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="b7e56-131">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and a password.</span></span>  
  
6.  <span data-ttu-id="b7e56-132">Dans la page **Sélectionner le dossier d’installation** , spécifiez le dossier du système de fichiers dans lequel installer les dépendances du package.</span><span class="sxs-lookup"><span data-stu-id="b7e56-132">On the **Select Installation Folder** page, specify the folder in the file system for the package dependencies that will be installed.</span></span>  
  
7.  <span data-ttu-id="b7e56-133">Si le package comprend des configurations, vous pouvez les modifier en mettant à jour des valeurs dans la liste **Valeur** dans la page Configurer les packages.</span><span class="sxs-lookup"><span data-stu-id="b7e56-133">If the package includes configurations, you can edit configurations by updating values in the **Value** list on the Configure Packages page.</span></span>  
  
8.  <span data-ttu-id="b7e56-134">Si vous avez choisi de valider les packages après l'installation, affichez les résultats de validation des packages déployés.</span><span class="sxs-lookup"><span data-stu-id="b7e56-134">If you elected to validate packages after installation, view the validation results of the deployed packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e56-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7e56-135">See Also</span></span>  
 [<span data-ttu-id="b7e56-136">Déploiement de packages &#40;&#41;SSIS</span><span class="sxs-lookup"><span data-stu-id="b7e56-136">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
