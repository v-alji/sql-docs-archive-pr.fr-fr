---
title: Informations de référence sur l’interface utilisateur de l’utilitaire d’exécution de package (DtExecUI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtexecui.general.f1
- sql12.dts.dtexecui.executionoptions.f1
- sql12.dts.dtexecui.configuration.f1
- sql12.dts.dtexecui.setvalues.f1
- sql12.dts.dtexecui.commandline.f1
- sql12.dts.dtexecui.commandfiles.f1
- sql12.dts.dtexecui.verification.f1
- sql12.dts.dtexecui.datasources.f1
- sql12.dts.dtexecui.reporting.f1
- sql12.dts.dtexecui.logging.f1
helpviewer_keywords:
- DTExecUI utility
ms.assetid: 3d71df39-126b-4c8e-bd77-128bbd5b0887
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 13601983a4ab841a2b64ff8e4fc722fcf5ae496c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611153"
---
# <a name="execute-package-utility-dtexecui-ui-reference"></a><span data-ttu-id="3c857-102">Référence de l'interface utilisateur de l'utilitaire d'exécution de package (DtExecUI)</span><span class="sxs-lookup"><span data-stu-id="3c857-102">Execute Package Utility (DtExecUI) UI Reference</span></span>
  <span data-ttu-id="3c857-103">Utilisez l' **Utilitaire d'exécution de package** pour exécuter des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c857-103">Use the **Execute Package Utility** to run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="3c857-104">L’utilitaire exécute les packages stockés à l’un des trois emplacements suivants : la base de données [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le magasin de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] et le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="3c857-104">The utility runs packages that are stored in one of three locations: [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store, and the file system.</span></span> <span data-ttu-id="3c857-105">Cette interface utilisateur, qui peut être ouverte depuis [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou en tapant `dtexecui` dans une invite de commandes, est une alternative à l’exécution de packages à l’aide de l’outil d’invite de commandes **dtexec** .</span><span class="sxs-lookup"><span data-stu-id="3c857-105">This user interface, which can be opened from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by typing `dtexecui` at a command prompt, is an alternative to running packages by using the **DTExec** command prompt tool.</span></span>  
  
 <span data-ttu-id="3c857-106">Les packages sont exécutés dans le même processus que l’utilitaire **dtexecui.exe** .</span><span class="sxs-lookup"><span data-stu-id="3c857-106">Packages execute in the same process as the **dtexecui.exe** utility.</span></span> <span data-ttu-id="3c857-107">Cet utilitaire étant un outil 32 bits, les packages exécutés à l’aide de **dtexecui.exe** dans un environnement 64 bits s’exécutent dans Windows sur Win32 (WOW).</span><span class="sxs-lookup"><span data-stu-id="3c857-107">Because this utility is a 32-bit tool, packages run by using **dtexecui.exe** in a 64-bit environment run in Windows on Win32 (WOW).</span></span> <span data-ttu-id="3c857-108">Quand vous développez et testez des commandes à l’aide de l’utilitaire dtexecui.exe sur un ordinateur 64 bits, effectuez les tests en mode 64 bits en utilisant la version 64 bits de **dtexec.exe** avant de déployer ou de planifier les commandes sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="3c857-108">When developing and testing commands by using the dtexecui.exe utility on a 64-bit computer, you should test the commands in 64-bit mode by using the 64-bit version of **dtexec.exe** before deploying or scheduling the commands on a production server.</span></span>  
  
 <span data-ttu-id="3c857-109">L’ **utilitaire d’exécution de package** est une interface utilisateur graphique de l’outil d’invite de commandes **DTExec** .</span><span class="sxs-lookup"><span data-stu-id="3c857-109">The **Execute Package Utility** is a graphical user interface for the **DTExec** command prompt tool.</span></span> <span data-ttu-id="3c857-110">L’interface utilisateur facilite la configuration des options et assemble automatiquement la ligne de commande qui est transmise à l’outil d’invite de commandes **DTExec** lorsque vous exécutez le package à partir des options spécifiées.</span><span class="sxs-lookup"><span data-stu-id="3c857-110">The user interface makes it easy to configure options and it automatically assembles the command line that is passed to the **DTExec** command prompt tool when you run the package from the specified options.</span></span>  
  
 <span data-ttu-id="3c857-111">L’ **utilitaire d’exécution de package** permet également d’assembler les lignes de commande que vous utilisez lorsque vous exécutez **DTExec** directement.</span><span class="sxs-lookup"><span data-stu-id="3c857-111">The **Execute Package Utility** can also be used to assemble command lines that you use when running **DTExec** directly.</span></span>  
  
### <a name="to-open-execute-package-utility-in-sql-server-management-studio"></a><span data-ttu-id="3c857-112">Pour ouvrir l'Utilitaire d'exécution de package dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3c857-112">To open Execute Package Utility in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="3c857-113">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez sur **Explorateur d'objets** dans le menu **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="3c857-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="3c857-114">Dans l'Explorateur d'objets, cliquez sur **Se connecter**, puis sur **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="3c857-114">In Object Explorer, click **Connect**, and then click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="3c857-115">Dans la boîte de dialogue **Se connecter au serveur** , entrez le nom du serveur dans la liste **Nom du serveur** , puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="3c857-115">In the **Connect to Server** dialog box, enter the server name in the **Server name** list, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="3c857-116">Développez le dossier **Packages stockés**et ses sous-dossiers, cliquez avec le bouton droit sur le package à exécuter, puis cliquez sur **Exécuter le package**.</span><span class="sxs-lookup"><span data-stu-id="3c857-116">Expand the **Stored Package**s folder and subfolders, right-click the package you want to run, and then click **Run Package**.</span></span>  
  
### <a name="to-open-the-execute-package-utility-at-the-command-prompt"></a><span data-ttu-id="3c857-117">Pour ouvrir l'Utilitaire d'exécution de package à l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="3c857-117">To open the Execute Package Utility at the Command Prompt</span></span>  
  
-   <span data-ttu-id="3c857-118">Dans une fenêtre d'invite de commandes, exécutez `dtexecui`.</span><span class="sxs-lookup"><span data-stu-id="3c857-118">In a command prompt window, run `dtexecui`.</span></span>  
  
 <span data-ttu-id="3c857-119">Les sections suivantes décrivent les pages de la boîte de dialogue **Utilitaire d'exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-119">The following sections describe pages of the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="general-page"></a><span data-ttu-id="3c857-120">Page Général</span><span class="sxs-lookup"><span data-stu-id="3c857-120">General Page</span></span>  
 <span data-ttu-id="3c857-121">Utilisez la page **Général** de la boîte de dialogue **Utilitaire d'exécution de package** pour spécifier le nom et l'emplacement d'un package.</span><span class="sxs-lookup"><span data-stu-id="3c857-121">Use the **General** page of the **Execute Package Utility** dialog box to specify a package name and location.</span></span>  
  
 <span data-ttu-id="3c857-122">L'utilitaire d'exécution de package (dtexecui.exe) exécute toujours un package sur l'ordinateur local, même si le package est enregistré sur un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="3c857-122">The Execute Package utility (dtexecui.exe) always runs a package on the local computer, even if the package is saved on a remote server.</span></span> <span data-ttu-id="3c857-123">Si le package distant utilise des fichiers de configuration qui sont toujours enregistrés sur le serveur distant, l'utilitaire d'exécution de package risque de ne pas trouver l'emplacement des configurations, faisant ainsi échouer le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-123">If the remote package uses configuration files that also are saved on the remote server, then the Execute Package utility may not locate the configurations and the package fails.</span></span> <span data-ttu-id="3c857-124">Pour éviter ce problème, les configurations doivent être référencées par un nom de partage UNC, tel que \\\monserveur\monfichier.</span><span class="sxs-lookup"><span data-stu-id="3c857-124">To avoid this problem, the configurations must be referenced by using a Universal Naming Convention (UNC) share name like \\\myserver\myfile.</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="3c857-125">Options statiques</span><span class="sxs-lookup"><span data-stu-id="3c857-125">Static Options</span></span>  
 <span data-ttu-id="3c857-126">**Source du package**</span><span class="sxs-lookup"><span data-stu-id="3c857-126">**Package source**</span></span>  
 <span data-ttu-id="3c857-127">Spécifiez l'emplacement du package à exécuter, à l'aide des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="3c857-127">Specify the location of the package to run, using the following options:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c857-128">Valeur</span><span class="sxs-lookup"><span data-stu-id="3c857-128">Value</span></span>|<span data-ttu-id="3c857-129">Description</span><span class="sxs-lookup"><span data-stu-id="3c857-129">Description</span></span>|  
|<span data-ttu-id="3c857-130">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3c857-130">**SQL Server**</span></span>|<span data-ttu-id="3c857-131">Sélectionnez cette option lorsque le package se trouve dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c857-131">Select this option when the package resides in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3c857-132">Spécifiez une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et fournissez un nom d'utilisateur et un mot de passe pour l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c857-132">Specify an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and provide a user name and password for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="3c857-133">Chaque nom d’utilisateur et chaque mot de passe ajoutent les options **/USER** _nom_utilisateur_ et **/PASSWORD** _mot_de_passe_ à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="3c857-133">Each user name and password adds the **/USER** _username_ and **/PASSWORD** _password_ options to the command prompt.</span></span>|  
|<span data-ttu-id="3c857-134">**Système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="3c857-134">**File system**</span></span>|<span data-ttu-id="3c857-135">Sélectionnez cette option lorsque le package se trouve dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="3c857-135">Select this option when the package resides in the file system.</span></span>|  
|<span data-ttu-id="3c857-136">**Magasin de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="3c857-136">**SSIS Package Store**</span></span>|<span data-ttu-id="3c857-137">Sélectionnez cette option lorsque le package se trouve dans le magasin de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c857-137">Select this option when the package resides in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span>|  
  
 <span data-ttu-id="3c857-138">Chacune des sélections ci-dessus comporte la série d'options suivante :</span><span class="sxs-lookup"><span data-stu-id="3c857-138">Each of these selections has the following set of options.</span></span>  
  
 <span data-ttu-id="3c857-139">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-139">**Execute**</span></span>  
 <span data-ttu-id="3c857-140">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-140">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-141">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-141">**Close**</span></span>  
 <span data-ttu-id="3c857-142">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-142">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="3c857-143">Options dynamiques</span><span class="sxs-lookup"><span data-stu-id="3c857-143">Dynamic Options</span></span>  
  
#### <a name="package-source--sql-server"></a><span data-ttu-id="3c857-144">Source du package = SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c857-144">Package Source = SQL Server</span></span>  
 <span data-ttu-id="3c857-145">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="3c857-145">**Server**</span></span>  
 <span data-ttu-id="3c857-146">Tapez le nom du serveur où se trouve le package ou choisissez un serveur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3c857-146">Type the name of the server where the package resides, or select a server from the list.</span></span>  
  
 <span data-ttu-id="3c857-147">**Connexion au serveur**</span><span class="sxs-lookup"><span data-stu-id="3c857-147">**Log on to the server**</span></span>  
 <span data-ttu-id="3c857-148">Indiquez si le package doit utiliser l’authentification Windows ou l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour se connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c857-148">Specify whether the package should use Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3c857-149">L'authentification Windows est recommandée pour renforcer la sécurité.</span><span class="sxs-lookup"><span data-stu-id="3c857-149">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="3c857-150">Avec l'authentification Windows, vous n'avez pas à spécifier un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="3c857-150">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="3c857-151">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="3c857-151">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="3c857-152">Sélectionnez cette option pour utiliser l’authentification Windows et connectez-vous à l’aide d’un compte d’utilisateur [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="3c857-152">Select this option to use Windows Authentication and log on using a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="3c857-153">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3c857-153">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="3c857-154">Sélectionnez cette option pour utiliser l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c857-154">Select this option to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="3c857-155">Quand un utilisateur se connecte avec un nom d’accès et un mot de passe spécifiés à partir d’une connexion non autorisée, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] réalise l’authentification en vérifiant si un compte de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été défini et si le mot de passe spécifié correspond à celui enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="3c857-155">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="3c857-156">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas trouver le compte de connexion, l'authentification échoue et l'utilisateur reçoit un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="3c857-156">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3c857-157">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="3c857-157">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="3c857-158">**Package**</span><span class="sxs-lookup"><span data-stu-id="3c857-158">**Package**</span></span>  
 <span data-ttu-id="3c857-159">Tapez le nom du package ou cliquez sur le bouton de sélection **(...)** pour identifier l’emplacement d’un package grâce à la boîte de dialogue **Sélectionner un package SSIS**.</span><span class="sxs-lookup"><span data-stu-id="3c857-159">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
#### <a name="package-source--file-system"></a><span data-ttu-id="3c857-160">Source du package = Système de fichiers</span><span class="sxs-lookup"><span data-stu-id="3c857-160">Package Source = File System</span></span>  
 <span data-ttu-id="3c857-161">**Package**</span><span class="sxs-lookup"><span data-stu-id="3c857-161">**Package**</span></span>  
 <span data-ttu-id="3c857-162">Tapez le nom du package ou cliquez sur le bouton qui contient des points de suspension **(...)** pour identifier l’emplacement d’un package grâce à la boîte de dialogue Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="3c857-162">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the Open dialog box.</span></span> <span data-ttu-id="3c857-163">Par défaut, cette boîte de dialogue répertorie uniquement les fichiers dotés de l'extension .dtsx.</span><span class="sxs-lookup"><span data-stu-id="3c857-163">By default, the dialog box lists only files that have the .dtsx extension.</span></span>  
  
#### <a name="package-source--ssis-package-store"></a><span data-ttu-id="3c857-164">Source du package = Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="3c857-164">Package Source = SSIS Package Store</span></span>  
 <span data-ttu-id="3c857-165">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="3c857-165">**Server**</span></span>  
 <span data-ttu-id="3c857-166">Tapez le nom de l'ordinateur où se trouve le package ou choisissez un ordinateur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3c857-166">Type the name of the computer where the package resides, or select a computer from the list.</span></span>  
  
 <span data-ttu-id="3c857-167">**Connexion au serveur**</span><span class="sxs-lookup"><span data-stu-id="3c857-167">**Log on to the server**</span></span>  
 <span data-ttu-id="3c857-168">Indiquez si le package doit utiliser l'authentification Microsoft Windows pour se connecter à la source du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-168">Specify whether the package should use Microsoft Windows Authentication to connect to the package source.</span></span> <span data-ttu-id="3c857-169">L'authentification Windows est recommandée pour renforcer la sécurité.</span><span class="sxs-lookup"><span data-stu-id="3c857-169">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="3c857-170">Avec l'authentification Windows, vous n'avez pas à spécifier un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="3c857-170">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="3c857-171">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="3c857-171">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="3c857-172">Sélectionnez cette option pour utiliser l'authentification Windows et connectez-vous à l'aide d'un compte d'utilisateur Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="3c857-172">Select this option to use Windows Authentication and log on using a Microsoft Windows user account.</span></span>  
  
 <span data-ttu-id="3c857-173">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3c857-173">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="3c857-174">Cette option est désactivée quand vous exécutez un package stocké dans le **Magasin de packages SSIS**.</span><span class="sxs-lookup"><span data-stu-id="3c857-174">This option is not available when you run a package stored in the **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="3c857-175">**Package**</span><span class="sxs-lookup"><span data-stu-id="3c857-175">**Package**</span></span>  
 <span data-ttu-id="3c857-176">Tapez le nom du package ou cliquez sur le bouton de sélection **(...)** pour identifier l’emplacement d’un package grâce à la boîte de dialogue **Sélectionner un package SSIS**.</span><span class="sxs-lookup"><span data-stu-id="3c857-176">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
## <a name="configurations-page"></a><span data-ttu-id="3c857-177">Page Configurations</span><span class="sxs-lookup"><span data-stu-id="3c857-177">Configurations Page</span></span>  
 <span data-ttu-id="3c857-178">Utilisez la page **Configurations** de la boîte de dialogue **Utilitaire d'exécution de package** pour sélectionner les fichiers de configuration à charger au moment de l'exécution et spécifier l'ordre de chargement.</span><span class="sxs-lookup"><span data-stu-id="3c857-178">Use the **Configurations** page of the **Execute Package Utility** dialog box to select the configuration files to load at run time, and to specify the order in which they load.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c857-179">Options</span><span class="sxs-lookup"><span data-stu-id="3c857-179">Options</span></span>  
 <span data-ttu-id="3c857-180">**Fichiers de configuration**</span><span class="sxs-lookup"><span data-stu-id="3c857-180">**Configuration files**</span></span>  
 <span data-ttu-id="3c857-181">Répertorie les configurations que le package utilise.</span><span class="sxs-lookup"><span data-stu-id="3c857-181">Lists the configurations that the package uses.</span></span> <span data-ttu-id="3c857-182">Chaque fichier de configuration ajoute une option **/CONFIGFILE nom_fichier** à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="3c857-182">Each configuration file adds a **/CONFIGFILE filename** option to the command prompt.</span></span>  
  
 <span data-ttu-id="3c857-183">**Touches de direction**</span><span class="sxs-lookup"><span data-stu-id="3c857-183">**Arrow keys**</span></span>  
 <span data-ttu-id="3c857-184">Sélectionnez un fichier de configuration dans la liste et utilisez les touches de direction à droite pour modifier l'ordre de chargement.</span><span class="sxs-lookup"><span data-stu-id="3c857-184">Select a configuration file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="3c857-185">Les configurations se chargent à partir du haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="3c857-185">Configurations load in order starting from the top of the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c857-186">Si plusieurs configurations modifient la même propriété, la dernière configuration chargée est utilisée.</span><span class="sxs-lookup"><span data-stu-id="3c857-186">If multiple configurations modify the same property, the configuration that loads last is used.</span></span>  
  
 <span data-ttu-id="3c857-187">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="3c857-187">**Add**</span></span>  
 <span data-ttu-id="3c857-188">Ajoute des configurations au moyen de la boîte de dialogue **Ouvrir** .</span><span class="sxs-lookup"><span data-stu-id="3c857-188">Click to add configurations using the **Open** dialog box.</span></span> <span data-ttu-id="3c857-189">Par défaut, cette boîte de dialogue affiche uniquement les fichiers ayant l'extension .dtsconfig.</span><span class="sxs-lookup"><span data-stu-id="3c857-189">By default, the dialog box lists only files that have the .dtsconfig extension.</span></span>  
  
 <span data-ttu-id="3c857-190">**Remove**</span><span class="sxs-lookup"><span data-stu-id="3c857-190">**Remove**</span></span>  
 <span data-ttu-id="3c857-191">Sélectionnez un fichier de configuration dans la liste, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="3c857-191">Select a configuration file in the list and then click **Remove**.</span></span>  
  
 <span data-ttu-id="3c857-192">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-192">**Execute**</span></span>  
 <span data-ttu-id="3c857-193">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-193">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-194">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-194">**Close**</span></span>  
 <span data-ttu-id="3c857-195">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-195">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-files-page"></a><span data-ttu-id="3c857-196">Page Fichiers de commandes</span><span class="sxs-lookup"><span data-stu-id="3c857-196">Command Files Page</span></span>  
 <span data-ttu-id="3c857-197">La page **Fichiers de commandes** de la boîte de dialogue **Utilitaire d'exécution de package** permet de sélectionner les fichiers de commandes devant être chargés au moment de l'exécution du programme.</span><span class="sxs-lookup"><span data-stu-id="3c857-197">Use the **Command Files** page of the **Execute Package Utility** dialog box to select the command files to load at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c857-198">Options</span><span class="sxs-lookup"><span data-stu-id="3c857-198">Options</span></span>  
 <span data-ttu-id="3c857-199">**Fichiers de commandes**</span><span class="sxs-lookup"><span data-stu-id="3c857-199">**Command files**</span></span>  
 <span data-ttu-id="3c857-200">Répertorie les fichiers de commandes que le package utilise.</span><span class="sxs-lookup"><span data-stu-id="3c857-200">Lists the command files that the package uses.</span></span> <span data-ttu-id="3c857-201">Un package peut utiliser plusieurs fichiers afin de définir des options de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="3c857-201">A package can use multiple files to set command-line options.</span></span>  
  
 <span data-ttu-id="3c857-202">**Touches de direction**</span><span class="sxs-lookup"><span data-stu-id="3c857-202">**Arrow keys**</span></span>  
 <span data-ttu-id="3c857-203">Permet de choisir un fichier de commandes dans la liste puis de changer l'ordre de séquence de chargement des fichiers par les touches fléchées de droite.</span><span class="sxs-lookup"><span data-stu-id="3c857-203">Select a command file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="3c857-204">Ces fichiers se chargent dans l'ordre en partant du haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="3c857-204">Command files load in order, starting from the top of the list.</span></span>  
  
 <span data-ttu-id="3c857-205">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="3c857-205">**Add**</span></span>  
 <span data-ttu-id="3c857-206">Ce bouton vous permet d’ouvrir la boîte de dialogue **Ouvrir** pour ajouter un fichier de commandes.</span><span class="sxs-lookup"><span data-stu-id="3c857-206">Click to add a command file, using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="3c857-207">**Remove**</span><span class="sxs-lookup"><span data-stu-id="3c857-207">**Remove**</span></span>  
 <span data-ttu-id="3c857-208">Permet de sélectionner un fichier de commandes dans la zone de texte, puis de le supprimer par le biais du bouton **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="3c857-208">Select a command file in the text box, and then remove it using the **Remove** button.</span></span>  
  
 <span data-ttu-id="3c857-209">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-209">**Execute**</span></span>  
 <span data-ttu-id="3c857-210">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-210">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-211">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-211">**Close**</span></span>  
 <span data-ttu-id="3c857-212">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-212">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="connection-managers-page"></a><span data-ttu-id="3c857-213">Page Gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="3c857-213">Connection Managers Page</span></span>  
 <span data-ttu-id="3c857-214">Utilisez la page **Gestionnaires de connexions** de la boîte de dialogue **Utilitaire d'exécution de package** pour modifier les chaînes de connexion des gestionnaires de connexions qu'utilise le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-214">Use the **Connection Managers** page of the **Execute Package Utility** dialog box to edit the connection strings of the connection managers that the package uses.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c857-215">Options</span><span class="sxs-lookup"><span data-stu-id="3c857-215">Options</span></span>  
 <span data-ttu-id="3c857-216">**Gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="3c857-216">**Connection Manager**</span></span>  
 <span data-ttu-id="3c857-217">Cochez cette case pour pouvoir modifier la colonne **Chaîne de connexion** .</span><span class="sxs-lookup"><span data-stu-id="3c857-217">Select its check box to make the **Connection String** column editable.</span></span>  
  
 <span data-ttu-id="3c857-218">**Description**</span><span class="sxs-lookup"><span data-stu-id="3c857-218">**Description**</span></span>  
 <span data-ttu-id="3c857-219">Affiche la description de chaque gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="3c857-219">View a description for each connection manager.</span></span> <span data-ttu-id="3c857-220">Les descriptions ne peuvent pas être modifiées.</span><span class="sxs-lookup"><span data-stu-id="3c857-220">Descriptions cannot be edited.</span></span>  
  
 <span data-ttu-id="3c857-221">**Chaîne de connexion**</span><span class="sxs-lookup"><span data-stu-id="3c857-221">**Connection String**</span></span>  
 <span data-ttu-id="3c857-222">Modifie la chaîne de connexion d'un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="3c857-222">Edit the connection string for a connection manager.</span></span> <span data-ttu-id="3c857-223">Ce champ est modifiable uniquement lorsque la case à cocher **Gestionnaire de connexions** est activée.</span><span class="sxs-lookup"><span data-stu-id="3c857-223">This field is editable only when the **Connection Manager** check box is selected.</span></span>  
  
 <span data-ttu-id="3c857-224">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-224">**Execute**</span></span>  
 <span data-ttu-id="3c857-225">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-225">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-226">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-226">**Close**</span></span>  
 <span data-ttu-id="3c857-227">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-227">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="execution-options-page"></a><span data-ttu-id="3c857-228">Page Options d'exécution</span><span class="sxs-lookup"><span data-stu-id="3c857-228">Execution Options Page</span></span>  
 <span data-ttu-id="3c857-229">Utilisez la page **Options d’exécution** de la boîte de dialogue **Utilitaire d’exécution de package** pour spécifier les options d’exécution du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-229">Use the **Execution Options** page of the **Execute Package Utility** dialog box to specify run-time options for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c857-230">Options</span><span class="sxs-lookup"><span data-stu-id="3c857-230">Options</span></span>  
 <span data-ttu-id="3c857-231">**Mettre le package en échec en cas d'avertissements de validation**</span><span class="sxs-lookup"><span data-stu-id="3c857-231">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="3c857-232">Indique si le package échoue si un avertissement de validation est détecté.</span><span class="sxs-lookup"><span data-stu-id="3c857-232">Indicate whether the package fails if a validation warning occurs.</span></span>  
  
 <span data-ttu-id="3c857-233">**Valider le package sans l'exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-233">**Validate package without executing**</span></span>  
 <span data-ttu-id="3c857-234">Indique si le package est seulement validé.</span><span class="sxs-lookup"><span data-stu-id="3c857-234">Indicate whether the package is validated only.</span></span>  
  
 <span data-ttu-id="3c857-235">**Maximum d'exécutables simultanés**</span><span class="sxs-lookup"><span data-stu-id="3c857-235">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="3c857-236">Indique si vous souhaitez spécifier le nombre maximal d'exécutables qui peuvent s'exécuter simultanément dans le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-236">Indicate whether you want to specify the maximum number of executables that can run in the package at the same time.</span></span> <span data-ttu-id="3c857-237">Après avoir activé cette case à cocher, utilisez la zone de sélection numérique pour spécifier le nombre maximal d'exécutables.</span><span class="sxs-lookup"><span data-stu-id="3c857-237">After you select this check box, use the spin box to specify the maximum number of executables.</span></span>  
  
 <span data-ttu-id="3c857-238">**Activer les points de contrôle de package**</span><span class="sxs-lookup"><span data-stu-id="3c857-238">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="3c857-239">Indique s'il faut activer les points de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-239">Indicate whether to enable package checkpoints.</span></span>  
  
 <span data-ttu-id="3c857-240">**Fichier de point de contrôle**</span><span class="sxs-lookup"><span data-stu-id="3c857-240">**Checkpoint file**</span></span>  
 <span data-ttu-id="3c857-241">Affiche le fichier de points de contrôle que le package utilise, si vous activez les points de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-241">List the checkpoint file the package uses, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="3c857-242">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="3c857-242">**Browse**</span></span>  
 <span data-ttu-id="3c857-243">Cliquez sur le bouton Parcourir **(...)** pour rechercher le fichier de points de contrôle au moyen de la boîte de dialogue **Ouvrir**, si vous activez les points de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-243">Click the browse button **(...)** to locate the checkpoint file using the **Open** dialog box, if you enable package checkpoints.</span></span> <span data-ttu-id="3c857-244">Si un fichier de points de contrôle est déjà spécifié, il est remplacé par le fichier sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3c857-244">If a checkpoint file is already specified, it is replaced by the selected file.</span></span>  
  
 <span data-ttu-id="3c857-245">**Substituer les options de redémarrage**</span><span class="sxs-lookup"><span data-stu-id="3c857-245">**Override restart options**</span></span>  
 <span data-ttu-id="3c857-246">Indique s'il faut ignorer les options de redémarrage, si vous activez les points de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-246">Indicate whether to override restart options, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="3c857-247">**Option de redémarrage**</span><span class="sxs-lookup"><span data-stu-id="3c857-247">**Restart option**</span></span>  
 <span data-ttu-id="3c857-248">Indique comment utiliser les points de contrôle si vous ignorez les options de redémarrage.</span><span class="sxs-lookup"><span data-stu-id="3c857-248">Select how to use checkpoints, if you override restart options.</span></span>  
  
 <span data-ttu-id="3c857-249">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-249">**Execute**</span></span>  
 <span data-ttu-id="3c857-250">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-250">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-251">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-251">**Close**</span></span>  
 <span data-ttu-id="3c857-252">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-252">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="reporting-page"></a><span data-ttu-id="3c857-253">Page Création de rapports</span><span class="sxs-lookup"><span data-stu-id="3c857-253">Reporting Page</span></span>  
 <span data-ttu-id="3c857-254">La page **Création de rapports** de la boîte de dialogue **Utilitaire d'exécution de package** permet de spécifier les événements et informations relatifs au package à consigner dans la console lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-254">Use the **Reporting** page of the **Execute Package Utility** dialog box to specify the events and information about the package to log to the console when the package runs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c857-255">Options</span><span class="sxs-lookup"><span data-stu-id="3c857-255">Options</span></span>  
 <span data-ttu-id="3c857-256">**Événements de la console**</span><span class="sxs-lookup"><span data-stu-id="3c857-256">**Console events**</span></span>  
 <span data-ttu-id="3c857-257">Indique les événements et types de messages à reporter.</span><span class="sxs-lookup"><span data-stu-id="3c857-257">Indicate the events and types of messages to report.</span></span>  
  
 <span data-ttu-id="3c857-258">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="3c857-258">**None**</span></span>  
 <span data-ttu-id="3c857-259">Sélectionnez cette option pour ne pas générer de rapports.</span><span class="sxs-lookup"><span data-stu-id="3c857-259">Select for no reporting.</span></span>  
  
 <span data-ttu-id="3c857-260">**Erreurs**</span><span class="sxs-lookup"><span data-stu-id="3c857-260">**Errors**</span></span>  
 <span data-ttu-id="3c857-261">Sélectionnez cette option pour générer un rapport sur les messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="3c857-261">Select to report error messages.</span></span>  
  
 <span data-ttu-id="3c857-262">**Avertissements**</span><span class="sxs-lookup"><span data-stu-id="3c857-262">**Warnings**</span></span>  
 <span data-ttu-id="3c857-263">Sélectionnez cette option pour générer un rapport sur les messages d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="3c857-263">Select to report warning messages.</span></span>  
  
 <span data-ttu-id="3c857-264">**Événements personnalisés**</span><span class="sxs-lookup"><span data-stu-id="3c857-264">**Custom Events**</span></span>  
 <span data-ttu-id="3c857-265">Sélectionnez cette option pour générer un rapport sur les événements personnalisés.</span><span class="sxs-lookup"><span data-stu-id="3c857-265">Select to report custom event messages.</span></span>  
  
 <span data-ttu-id="3c857-266">**Événements de pipeline**</span><span class="sxs-lookup"><span data-stu-id="3c857-266">**Pipeline Events**</span></span>  
 <span data-ttu-id="3c857-267">Sélectionnez cette option pour générer un rapport sur les messages d'événements de flux de données.</span><span class="sxs-lookup"><span data-stu-id="3c857-267">Select to report data flow events messages.</span></span>  
  
 <span data-ttu-id="3c857-268">**Informations**</span><span class="sxs-lookup"><span data-stu-id="3c857-268">**Information**</span></span>  
 <span data-ttu-id="3c857-269">Sélectionnez cette option pour générer un rapport sur les messages d'information.</span><span class="sxs-lookup"><span data-stu-id="3c857-269">Select to report information messages.</span></span>  
  
 <span data-ttu-id="3c857-270">**Verbose**</span><span class="sxs-lookup"><span data-stu-id="3c857-270">**Verbose**</span></span>  
 <span data-ttu-id="3c857-271">Sélectionnez cette option pour utiliser les rapports de commentaire.</span><span class="sxs-lookup"><span data-stu-id="3c857-271">Select to use verbose reporting.</span></span>  
  
 <span data-ttu-id="3c857-272">**Écriture dans le journal de la console**</span><span class="sxs-lookup"><span data-stu-id="3c857-272">**Console logging**</span></span>  
 <span data-ttu-id="3c857-273">Spécifiez les informations à écrire dans le journal lorsque l'événement sélectionné se produit.</span><span class="sxs-lookup"><span data-stu-id="3c857-273">Specify the information that you want written to the log when the selected event occurs.</span></span>  
  
 <span data-ttu-id="3c857-274">**Nom**</span><span class="sxs-lookup"><span data-stu-id="3c857-274">**Name**</span></span>  
 <span data-ttu-id="3c857-275">Sélectionnez cette option pour générer un rapport sur le nom de la personne qui a créé le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-275">Select to report the name of the person who created the package.</span></span>  
  
 <span data-ttu-id="3c857-276">**Ordinateur**</span><span class="sxs-lookup"><span data-stu-id="3c857-276">**Computer**</span></span>  
 <span data-ttu-id="3c857-277">Sélectionnez cette option pour générer un rapport sur le nom de l'ordinateur sur lequel le package s'exécute.</span><span class="sxs-lookup"><span data-stu-id="3c857-277">Select to report the name of the computer the package is running on.</span></span>  
  
 <span data-ttu-id="3c857-278">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="3c857-278">**Operator**</span></span>  
 <span data-ttu-id="3c857-279">Sélectionnez cette option pour générer un rapport sur le nom de la personne qui a lancé le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-279">Select to report the name of the person who started the package.</span></span>  
  
 <span data-ttu-id="3c857-280">**Nom de la source**</span><span class="sxs-lookup"><span data-stu-id="3c857-280">**Source name**</span></span>  
 <span data-ttu-id="3c857-281">Sélectionnez cette option pour générer un rapport sur le nom du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-281">Select to report the package name.</span></span>  
  
 <span data-ttu-id="3c857-282">**GUID source**</span><span class="sxs-lookup"><span data-stu-id="3c857-282">**Source GUID**</span></span>  
 <span data-ttu-id="3c857-283">Sélectionnez cette option pour générer un rapport sur le GUID du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-283">Select to report the package GUID.</span></span>  
  
 <span data-ttu-id="3c857-284">**GUID d'exécution**</span><span class="sxs-lookup"><span data-stu-id="3c857-284">**Execution GUID**</span></span>  
 <span data-ttu-id="3c857-285">Sélectionnez cette option pour générer un rapport sur le GUID de l'instance d'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-285">Select to report the GUID of the package execution instance.</span></span>  
  
 <span data-ttu-id="3c857-286">**Message**</span><span class="sxs-lookup"><span data-stu-id="3c857-286">**Message**</span></span>  
 <span data-ttu-id="3c857-287">Sélectionnez cette option pour générer un rapport sur les messages.</span><span class="sxs-lookup"><span data-stu-id="3c857-287">Select to report messages.</span></span>  
  
 <span data-ttu-id="3c857-288">**Heure de début et heure de fin**</span><span class="sxs-lookup"><span data-stu-id="3c857-288">**Start time and end time**</span></span>  
 <span data-ttu-id="3c857-289">Sélectionnez cette option pour générer un rapport sur l'heure à laquelle le package a commencé et s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="3c857-289">Select to report when the package began and finished.</span></span>  
  
 <span data-ttu-id="3c857-290">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-290">**Execute**</span></span>  
 <span data-ttu-id="3c857-291">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-291">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-292">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-292">**Close**</span></span>  
 <span data-ttu-id="3c857-293">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-293">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="logging-page"></a><span data-ttu-id="3c857-294">Page Enregistrement</span><span class="sxs-lookup"><span data-stu-id="3c857-294">Logging Page</span></span>  
 <span data-ttu-id="3c857-295">La page **Enregistrement** de la boîte de dialogue **Utilitaire d'exécution de package** permet de créer des modules fournisseur d'informations mis à disposition du package au moment de l'exécution du programme.</span><span class="sxs-lookup"><span data-stu-id="3c857-295">Use the **Logging** page of the **Execute Package Utility** dialog box to make log providers available to the package at run time.</span></span> <span data-ttu-id="3c857-296">Vous devez fournir le type du module fournisseur d'informations du package ainsi que la chaîne de connexion afin de pouvoir vous connecter au journal.</span><span class="sxs-lookup"><span data-stu-id="3c857-296">Provide the package log provider type and the connection string for connecting to the log.</span></span> <span data-ttu-id="3c857-297">Chaque entrée de module fournisseur d’informations ajoute une option **/LOGGER**_ID_classe_ à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="3c857-297">Each log provider entry adds a **/LOGGER**_classid_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c857-298">Options</span><span class="sxs-lookup"><span data-stu-id="3c857-298">Options</span></span>  
 <span data-ttu-id="3c857-299">**Module fournisseur d’informations**</span><span class="sxs-lookup"><span data-stu-id="3c857-299">**Log Provider**</span></span>  
 <span data-ttu-id="3c857-300">Permet de choisir un module fournisseur d'informations dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3c857-300">Select a log provider from the list.</span></span>  
  
 <span data-ttu-id="3c857-301">**Chaîne de configuration**</span><span class="sxs-lookup"><span data-stu-id="3c857-301">**Configuration String**</span></span>  
 <span data-ttu-id="3c857-302">Permet de choisir un nom pour le gestionnaire de connexions à partir du package pointant vers l'emplacement du journal ou de saisir complètement la chaîne de connexion afin de pouvoir se connecter au module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="3c857-302">Select the name of the connection manager from the package that points to the log location, or type the connection string for connecting to the log provider.</span></span>  
  
 <span data-ttu-id="3c857-303">**Remove**</span><span class="sxs-lookup"><span data-stu-id="3c857-303">**Remove**</span></span>  
 <span data-ttu-id="3c857-304">Permet de sélectionner un module fournisseur d'informations pour le supprimer.</span><span class="sxs-lookup"><span data-stu-id="3c857-304">Select a log provider and click to remove it.</span></span>  
  
 <span data-ttu-id="3c857-305">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-305">**Execute**</span></span>  
 <span data-ttu-id="3c857-306">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-306">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-307">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-307">**Close**</span></span>  
 <span data-ttu-id="3c857-308">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-308">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="set-values-page"></a><span data-ttu-id="3c857-309">Page Valeurs définies</span><span class="sxs-lookup"><span data-stu-id="3c857-309">Set Values Page</span></span>  
 <span data-ttu-id="3c857-310">Utilisez la page **Valeurs définies** de la boîte de dialogue **Utilitaire d'exécution de package** pour définir les valeurs des propriétés des packages, des fichiers exécutables, des connexions, des variables et des modules fournisseur d'informations. Pour cela, tapez les chemins d'accès aux propriétés et leurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="3c857-310">Use the **Set Values** page of the **Execute Package Utility** dialog box to set the property values of packages, executables, connections, variables, and log providers by typing the paths of properties and the property values.</span></span> <span data-ttu-id="3c857-311">Chaque entrée de chemin d’accès ajoute une option **/SET**_chemin_propriété;valeur_ à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="3c857-311">Each path entry adds a **/SET**_propertypath;value_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c857-312">Options</span><span class="sxs-lookup"><span data-stu-id="3c857-312">Options</span></span>  
 <span data-ttu-id="3c857-313">**Chemin de la propriété**</span><span class="sxs-lookup"><span data-stu-id="3c857-313">**Property Path**</span></span>  
 <span data-ttu-id="3c857-314">Tapez le chemin d'accès à la propriété.</span><span class="sxs-lookup"><span data-stu-id="3c857-314">Type the path of the property.</span></span> <span data-ttu-id="3c857-315">Le chemin doit comporter une barre oblique inverse (\\) pour indiquer que l’élément suivant est un conteneur, un point pour indiquer que l’élément suivant est une propriété et des parenthèses pour indiquer un membre d’une collection.</span><span class="sxs-lookup"><span data-stu-id="3c857-315">The path syntax uses a backslash (\\) to indicate that the following item is a container, the period (.) to indicate the following item is a property, and brackets to indicate a collection member.</span></span> <span data-ttu-id="3c857-316">Il est possible d'identifier le membre par son index ou son nom.</span><span class="sxs-lookup"><span data-stu-id="3c857-316">The member can be identified by its index or its name.</span></span> <span data-ttu-id="3c857-317">Par exemple, le chemin d'accès à une variable d'un package est : \Package.Variables[MyVariable].Value.</span><span class="sxs-lookup"><span data-stu-id="3c857-317">For example, the property path of a package variable is \Package.Variables[MyVariable].Value.</span></span>  
  
 <span data-ttu-id="3c857-318">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="3c857-318">**Value**</span></span>  
 <span data-ttu-id="3c857-319">Tapez la valeur de la propriété.</span><span class="sxs-lookup"><span data-stu-id="3c857-319">Type the value of the property.</span></span>  
  
 <span data-ttu-id="3c857-320">**Remove**</span><span class="sxs-lookup"><span data-stu-id="3c857-320">**Remove**</span></span>  
 <span data-ttu-id="3c857-321">Sélectionnez le chemin d'accès à une propriété et cliquez dessus pour la supprimer.</span><span class="sxs-lookup"><span data-stu-id="3c857-321">Select a property path and click to remove it.</span></span>  
  
 <span data-ttu-id="3c857-322">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-322">**Execute**</span></span>  
 <span data-ttu-id="3c857-323">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-323">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-324">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-324">**Close**</span></span>  
 <span data-ttu-id="3c857-325">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-325">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="verification-page"></a><span data-ttu-id="3c857-326">Page Vérification</span><span class="sxs-lookup"><span data-stu-id="3c857-326">Verification Page</span></span>  
 <span data-ttu-id="3c857-327">Utilisez la page **Vérification** de la boîte de dialogue **Exécuter le package** pour spécifier les critères de vérification du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-327">Use the **Verification** page of the **Execute Package** dialog box to set criteria for verifying the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c857-328">Options</span><span class="sxs-lookup"><span data-stu-id="3c857-328">Options</span></span>  
 <span data-ttu-id="3c857-329">**Exécuter uniquement les packages signés**</span><span class="sxs-lookup"><span data-stu-id="3c857-329">**Execute only signed packages**</span></span>  
 <span data-ttu-id="3c857-330">Exécute uniquement les packages signés.</span><span class="sxs-lookup"><span data-stu-id="3c857-330">Select to execute only packages that have been signed.</span></span>  
  
 <span data-ttu-id="3c857-331">**Vérifier la build du package**</span><span class="sxs-lookup"><span data-stu-id="3c857-331">**Verify package build**</span></span>  
 <span data-ttu-id="3c857-332">Vérifie la build du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-332">Select to verify the package build.</span></span>  
  
 <span data-ttu-id="3c857-333">Build</span><span class="sxs-lookup"><span data-stu-id="3c857-333">Build</span></span>  
 <span data-ttu-id="3c857-334">Spécifiez le numéro séquentiel de la build du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-334">Specify the sequential Build number associated with the build.</span></span>  
  
 <span data-ttu-id="3c857-335">**Vérifier l'ID de package**</span><span class="sxs-lookup"><span data-stu-id="3c857-335">**Verify package ID**</span></span>  
 <span data-ttu-id="3c857-336">Vérifie la version l'ID du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-336">Select to verify the package ID.</span></span>  
  
 <span data-ttu-id="3c857-337">ID du package</span><span class="sxs-lookup"><span data-stu-id="3c857-337">Package ID</span></span>  
 <span data-ttu-id="3c857-338">Spécifiez le numéro d'identification du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-338">Specify the package identification number.</span></span>  
  
 <span data-ttu-id="3c857-339">**Vérifier l'ID de version**</span><span class="sxs-lookup"><span data-stu-id="3c857-339">**Verify version ID**</span></span>  
 <span data-ttu-id="3c857-340">Vérifie l'ID de la version du package.</span><span class="sxs-lookup"><span data-stu-id="3c857-340">Select to verify the version ID.</span></span>  
  
 <span data-ttu-id="3c857-341">ID de version</span><span class="sxs-lookup"><span data-stu-id="3c857-341">Version ID</span></span>  
 <span data-ttu-id="3c857-342">Spécifiez le numéro d'identification de la version.</span><span class="sxs-lookup"><span data-stu-id="3c857-342">Specify the version identification number.</span></span>  
  
 <span data-ttu-id="3c857-343">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-343">**Execute**</span></span>  
 <span data-ttu-id="3c857-344">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-344">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-345">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-345">**Close**</span></span>  
 <span data-ttu-id="3c857-346">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-346">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-line-page"></a><span data-ttu-id="3c857-347">Page Ligne de commande</span><span class="sxs-lookup"><span data-stu-id="3c857-347">Command Line Page</span></span>  
 <span data-ttu-id="3c857-348">Le nœud **Ligne de commande** de la boîte de dialogue **Utilitaire d'exécution du package** permet de modifier la ligne de commande ayant été générée par les options créées par les différentes boîtes de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3c857-348">Use the **Command Line** node of the **Execute Package Utility** dialog box to edit the command line that has been generated by the options created by the various dialogs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c857-349">Options</span><span class="sxs-lookup"><span data-stu-id="3c857-349">Options</span></span>  
 <span data-ttu-id="3c857-350">**Restaurer les options d'origine**</span><span class="sxs-lookup"><span data-stu-id="3c857-350">**Restore the original options**</span></span>  
 <span data-ttu-id="3c857-351">Permet de ramener la ligne de commande à son état initial.</span><span class="sxs-lookup"><span data-stu-id="3c857-351">Click to restore the command line to its original state.</span></span> <span data-ttu-id="3c857-352">Utilisez cette option si vous avez apporté des modifications par le biais de l’option **Modifier la ligne de commande manuellement** et que vous voulez restaurer les options de ligne de commande initiales.</span><span class="sxs-lookup"><span data-stu-id="3c857-352">Use this option if you have made modifications using the **Edit the command line manually** option and want to restore the original command-line options.</span></span>  
  
 <span data-ttu-id="3c857-353">**Modifier la ligne de commande manuellement**</span><span class="sxs-lookup"><span data-stu-id="3c857-353">**Edit the command line manually**</span></span>  
 <span data-ttu-id="3c857-354">Permet de modifier la ligne de commande figurant dans la zone de texte **Ligne de commande** .</span><span class="sxs-lookup"><span data-stu-id="3c857-354">Click to edit the command line in the **Command line** text box.</span></span>  
  
 <span data-ttu-id="3c857-355">**Ligne de commande**</span><span class="sxs-lookup"><span data-stu-id="3c857-355">**Command line**</span></span>  
 <span data-ttu-id="3c857-356">Affiche la ligne de commande actuelle.</span><span class="sxs-lookup"><span data-stu-id="3c857-356">Displays the current command line.</span></span> <span data-ttu-id="3c857-357">Cet élément est modifiable si vous avez activé l'option de modifier la ligne de commande manuellement.</span><span class="sxs-lookup"><span data-stu-id="3c857-357">Editable if you selected the option to edit the command line manually.</span></span>  
  
 <span data-ttu-id="3c857-358">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="3c857-358">**Execute**</span></span>  
 <span data-ttu-id="3c857-359">Permet d'exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="3c857-359">Click to run the package.</span></span>  
  
 <span data-ttu-id="3c857-360">**Close**</span><span class="sxs-lookup"><span data-stu-id="3c857-360">**Close**</span></span>  
 <span data-ttu-id="3c857-361">Ferme la boîte de dialogue **Utilitaire d’exécution de package** .</span><span class="sxs-lookup"><span data-stu-id="3c857-361">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c857-362">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c857-362">See Also</span></span>  
 [<span data-ttu-id="3c857-363">Utilitaire dtexec</span><span class="sxs-lookup"><span data-stu-id="3c857-363">dtexec Utility</span></span>](dtexec-utility.md)  
  
  
