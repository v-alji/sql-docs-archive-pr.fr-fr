---
title: Importer et exporter des packages (service SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], importing
- packages [Integration Services], exporting
- importing packages
- exporting packages
ms.assetid: ef18ec11-b536-47d9-abd1-794099f43486
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b69f9d23431ed86f6b84be6857b7104cd8ba3dcc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611908"
---
# <a name="import-and-export-packages-ssis-service"></a><span data-ttu-id="d3cb4-102">Importer et exporter des packages (Service SSIS)</span><span class="sxs-lookup"><span data-stu-id="d3cb4-102">Import and Export Packages (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="d3cb4-103">Cette rubrique présente le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un service Windows qui permet de gérer les packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="d3cb4-104">prend en charge le service pour la compatibilité avec les versions antérieures de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3cb4-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="d3cb4-105">À compter de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], vous pouvez gérer des objets tels que des packages sur le serveur Integration Services.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="d3cb4-106">Les packages peuvent être enregistrés dans la table sysssispackages de la base de données msdb de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-106">Packages can be saved either in the sysssispackages table in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database or in the file system.</span></span>  
  
 <span data-ttu-id="d3cb4-107">Le magasin de packages, qui est le stockage logique que le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contrôle et gère, peut inclure la base de données msdb et les dossiers du système de fichiers spécifiés dans le fichier de configuration pour le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-107">The package store, which is the logical storage that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service monitors and manages, can include both the msdb database and the file system folders specified in the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="d3cb4-108">Vous pouvez importer et exporter des packages entre les types de stockage suivants :</span><span class="sxs-lookup"><span data-stu-id="d3cb4-108">You can import and export packages between the following storage types:</span></span>  
  
-   <span data-ttu-id="d3cb4-109">Les dossiers du système de fichiers n'importe où dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-109">File system folders anywhere in the file system.</span></span>  
  
-   <span data-ttu-id="d3cb4-110">Les dossiers dans le magasin de packages SSIS.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-110">Folders in the SSIS Package Store.</span></span> <span data-ttu-id="d3cb4-111">Les deux dossiers par défaut sont appelés « Système de fichiers » et « MSDB ».</span><span class="sxs-lookup"><span data-stu-id="d3cb4-111">The two default folders are named File System and MSDB.</span></span>  
  
-   <span data-ttu-id="d3cb4-112">La base de données msdb [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-112">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="d3cb4-113">vous donne la possibilité d'importer et d'exporter des packages, et ce faisant, de modifier le format et l'emplacement de stockage des packages.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-113">gives you the ability to import and export packages, and by doing this change the storage format and location of packages.</span></span> <span data-ttu-id="d3cb4-114">Les fonctionnalités d’importation et d’exportation vous permettent d’ajouter des packages au système de fichiers, au magasin de packages ou à la base de données msdb, et de copier des packages d’un format de stockage vers un autre.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-114">Using the import and export features, you can add packages to the file system, package store, or msdb database, and copy packages from one storage format to another.</span></span> <span data-ttu-id="d3cb4-115">Par exemple, les packages enregistrés dans msdb peuvent être copiés dans le système de fichiers et vice versa.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-115">For example, packages saved in msdb can be copied to the file system and vice versa.</span></span>  
  
 <span data-ttu-id="d3cb4-116">Vous pouvez aussi copier un package dans un format différent à l’aide de l’utilitaire d’invite de commandes **dtutil** (dtutil.exe).</span><span class="sxs-lookup"><span data-stu-id="d3cb4-116">You can also copy a package to a different format using the **dtutil** command prompt utility (dtutil.exe).</span></span> <span data-ttu-id="d3cb4-117">Pour plus d’informations, consultez [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="d3cb4-117">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
## <a name="to-import-or-export-a-package"></a><span data-ttu-id="d3cb4-118">Pour exporter ou importer un package</span><span class="sxs-lookup"><span data-stu-id="d3cb4-118">To import or export a package</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3cb4-119">Cette rubrique décrit le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , qui fait partie de [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3cb4-119">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that is part of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="d3cb4-120">prend en charge le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pour la compatibilité descendante avec [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3cb4-120">supports the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service for backward compatibility with [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="d3cb4-121">Pour plus d’informations sur la gestion des packages dans [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], consultez [Serveur Integration Services &#40;SSIS&#41;](catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d3cb4-121">For information about managing packages in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], see [Integration Services &#40;SSIS&#41; Server](catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="d3cb4-122">Vous pouvez importer ou exporter un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] depuis ou vers les emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="d3cb4-122">You can import or export an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from or to the following locations:</span></span>  
  
-   <span data-ttu-id="d3cb4-123">Vous pouvez importer un package stocké dans une instance de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], dans le système de fichiers ou dans le magasin de packages [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3cb4-123">You can import a package that is stored in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], in the file system, or in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span> <span data-ttu-id="d3cb4-124">Le package importé est enregistré dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou dans un dossier dans le magasin de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-124">The imported package is saved to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to a folder in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span>  
  
-   <span data-ttu-id="d3cb4-125">Vous pouvez exporter un package stocké dans une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], dans le système de fichiers ou dans le magasin de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] vers un format ou un emplacement de stockage différent.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-125">You can export a package that is stored in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], the file system, or the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store to a different storage format and location.</span></span>  
  
 <span data-ttu-id="d3cb4-126">Toutefois, il existe des restrictions relatives à l'importation et à l'exportation d'un package entre des versions différentes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d3cb4-126">However, there are some restrictions on importing and exporting a package between different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="d3cb4-127">Vous pouvez importer dans une instance de [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)]des packages provenant d'une instance de [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], mais vous ne pouvez pas exporter de packages vers une instance de [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3cb4-127">On an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], you can import packages from an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], but you cannot export packages to an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="d3cb4-128">Dans une instance de [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], vous ne pouvez pas importer de packages provenant d'une instance de [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], ni exporter de packages vers une telle instance.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-128">On an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you cannot import packages from, or export packages to, an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="d3cb4-129">Les procédures ci-dessous montrent comment utiliser [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour importer et exporter un package.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-129">The following procedures describe how to use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to import or export a package.</span></span>  
  
#### <a name="to-import-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="d3cb4-130">Pour importer un package à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d3cb4-130">To import a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="d3cb4-131">Cliquez sur **Démarrer**, pointez sur **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], puis cliquez sur **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-131">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="d3cb4-132">Dans la boîte de dialogue **Se connecter au serveur** , définissez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3cb4-132">In the **Connect to Server** dialog box set the following options:</span></span>  
  
    -   <span data-ttu-id="d3cb4-133">Dans la zone **Type de serveur** , sélectionnez **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-133">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="d3cb4-134">Dans la zone **Nom du serveur**, indiquez le nom du serveur ou cliquez sur **\<Browse for more...>** , puis recherchez le serveur à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-134">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="d3cb4-135">Si l'Explorateur d'objets n'est pas ouvert, dans le menu **Affichage** , cliquez sur **Explorateur d'objets**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-135">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="d3cb4-136">Dans l'Explorateur d'objets, développez le dossier **Packages stockés** .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-136">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="d3cb4-137">Développez les sous-dossiers afin de rechercher celui dans lequel vous souhaitez importer un package.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-137">Expand the subfolders to locate the folder into which you want to import a package.</span></span>  
  
6.  <span data-ttu-id="d3cb4-138">Cliquez avec le bouton droit sur le dossier, puis cliquez sur **Importer un package**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-138">Right-click the folder, click **Import Package**.</span></span> <span data-ttu-id="d3cb4-139">Effectuez ensuite l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3cb4-139">and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="d3cb4-140">Pour importer à partir d'une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], sélectionnez l'option **SQL Server** , puis spécifiez le serveur et le mode d'authentification.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-140">To import from an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="d3cb4-141">Si vous sélectionnez l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , indiquez un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-141">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="d3cb4-142">Cliquez sur le bouton Parcourir **(...)** , sélectionnez le package à importer, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-142">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
    -   <span data-ttu-id="d3cb4-143">Pour importer à partir d'un système de fichiers, sélectionnez l'option **Système de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-143">To import from the file system, select the **File system** option.</span></span>  
  
         <span data-ttu-id="d3cb4-144">Cliquez sur le bouton Parcourir **(...)** , sélectionnez le package à importer, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-144">Click the browse button **(...)**, select the package to import, and then click **Open.**</span></span>  
  
    -   <span data-ttu-id="d3cb4-145">Pour importer à partir du magasin de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] , sélectionnez l'option **Magasin de packages SSIS** et spécifiez le serveur.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-145">To import from the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, select the **SSIS Package Store** option and specify the server.</span></span>  
  
         <span data-ttu-id="d3cb4-146">Cliquez sur le bouton Parcourir **(...)** , sélectionnez le package à importer, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-146">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="d3cb4-147">Si vous le souhaitez, mettez à jour le nom du package.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-147">Optionally, update the package name.</span></span>  
  
8.  <span data-ttu-id="d3cb4-148">Pour mettre à jour le niveau de protection du package, cliquez sur le bouton Parcourir **(...)** et sélectionnez un niveau de protection différent dans la boîte de dialogue **Niveau de protection du package** .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-148">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="d3cb4-149">Si l'option **Chiffrer les données sensibles avec un mot de passe** ou **Chiffrer toutes les données avec un mot de passe** est sélectionnée, tapez un mot de passe et confirmez-le.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-149">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
9. <span data-ttu-id="d3cb4-150">Cliquez sur **OK** pour terminer l'importation.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-150">Click **OK** to complete the import.</span></span>  
  
#### <a name="to-export-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="d3cb4-151">Pour exporter un package à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d3cb4-151">To export a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="d3cb4-152">Cliquez sur **Démarrer**, pointez sur **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], puis cliquez sur **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-152">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="d3cb4-153">Dans la boîte de dialogue **Se connecter au serveur** , définissez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3cb4-153">In the **Connect to Server** dialog box, set the following options:</span></span>  
  
    -   <span data-ttu-id="d3cb4-154">Dans la zone **Type de serveur** , sélectionnez **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-154">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="d3cb4-155">Dans la zone **Nom du serveur**, indiquez le nom du serveur ou cliquez sur **\<Browse for more...>** , puis recherchez le serveur à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-155">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="d3cb4-156">Si l'Explorateur d'objets n'est pas ouvert, dans le menu **Affichage** , cliquez sur **Explorateur d'objets**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-156">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="d3cb4-157">Dans l'Explorateur d'objets, développez le dossier **Packages stockés** .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-157">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="d3cb4-158">Développez les sous-dossiers pour localiser le package à exporter.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-158">Expand the subfolders to locate the package you want to export.</span></span>  
  
6.  <span data-ttu-id="d3cb4-159">Cliquez avec le bouton droit sur le package, cliquez sur **Exporter**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3cb4-159">Right-click the package, click **Export**, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="d3cb4-160">Pour exporter un package vers une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], sélectionnez l'option **SQL Server** , puis indiquez le serveur et sélectionnez le mode d'authentification.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-160">To export to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="d3cb4-161">Si vous sélectionnez l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , indiquez un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-161">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="d3cb4-162">Cliquez sur le bouton Parcourir **(...)** , puis développez le dossier **Packages SSIS** pour rechercher le dossier dans lequel enregistrer le package.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-162">Click the browse button **(...)**, and expand the **SSIS Packages** folder to locate the folder to which you want to save the package.</span></span> <span data-ttu-id="d3cb4-163">Si vous le souhaitez, mettez à jour le nom par défaut du package, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-163">Optionally, update the default name of the package, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="d3cb4-164">Pour exporter un package vers le système de fichiers, sélectionnez l'option **Système de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-164">To export to the file system, select the **File System** option.</span></span>  
  
         <span data-ttu-id="d3cb4-165">Cliquez sur le bouton Parcourir **(...)** pour rechercher le dossier dans lequel exporter le package, tapez le nom du fichier de package, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-165">Click the browse button **(...)** to locate the folder to which you want to export the package, type the name of the package file, and then click **Save.**</span></span>  
  
    -   <span data-ttu-id="d3cb4-166">Pour exporter un package vers le magasin de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] , sélectionnez l'option **Magasin de packages SSIS** , puis indiquez le serveur.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-166">To export to the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store, select the **SSIS Package Store** option, and specify the server.</span></span>  
  
         <span data-ttu-id="d3cb4-167">Cliquez sur le bouton Parcourir **(...)** , développez le dossier **Packages SSIS**, puis sélectionnez le dossier dans lequel enregistrer le package.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-167">Click the browse button **(...)**, expand the **SSIS Packages** folder, and select the folder to which you want to save the package.</span></span> <span data-ttu-id="d3cb4-168">Si vous le souhaitez, entrez un nouveau nom pour le package dans la zone de texte **Nom du package** .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-168">Optionally, enter a new name for the package in the **Package Name** text box.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="d3cb4-169">Pour mettre à jour le niveau de protection du package, cliquez sur le bouton Parcourir **(...)** et sélectionnez un niveau de protection différent dans la boîte de dialogue **Niveau de protection du package** .</span><span class="sxs-lookup"><span data-stu-id="d3cb4-169">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="d3cb4-170">Si l'option **Chiffrer les données sensibles avec un mot de passe** ou **Chiffrer toutes les données avec un mot de passe** est sélectionnée, tapez un mot de passe et confirmez-le.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-170">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
8.  <span data-ttu-id="d3cb4-171">Cliquez sur **OK** pour terminer l'exportation.</span><span class="sxs-lookup"><span data-stu-id="d3cb4-171">Click **OK** to complete the export.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3cb4-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3cb4-172">See Also</span></span>  
 [<span data-ttu-id="d3cb4-173">Gestion de packages &#40;Service SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d3cb4-173">Package Management &#40;SSIS Service&#41;</span></span>](service/package-management-ssis-service.md)  
  
  
