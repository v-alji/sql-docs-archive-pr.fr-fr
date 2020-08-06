---
title: Sélectionner l’emplacement de destination (Assistant Mise à niveau de packages SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectdestinationlocation.f1
ms.assetid: 89274a71-0ffe-4889-84df-f5a7d78459ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9411157434c3dbb9fb033f7b63b5e6041fd8f75d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614726"
---
# <a name="select-destination-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="73e8e-102">Sélectionner l'emplacement de destination (Assistant Mise à niveau de packages SSIS)</span><span class="sxs-lookup"><span data-stu-id="73e8e-102">Select Destination Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="73e8e-103">Utilisez la page **Sélectionner l’emplacement de destination** pour spécifier la destination dans laquelle enregistrer les packages mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="73e8e-103">Use the **Select Destination Location** page to specify the destination to which to save the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73e8e-104">Cette page est disponible uniquement quand vous exécutez l’Assistant Mise à niveau de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] à partir de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou de l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="73e8e-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="73e8e-105">**Pour exécuter l'Assistant Mise à niveau de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="73e8e-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="73e8e-106">Mettre à niveau des packages Integration Services à l'aide de l'Assistant Mise à niveau de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="73e8e-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="73e8e-107">Options statiques</span><span class="sxs-lookup"><span data-stu-id="73e8e-107">Static Options</span></span>  
 <span data-ttu-id="73e8e-108">**Enregistrer à l'emplacement source**</span><span class="sxs-lookup"><span data-stu-id="73e8e-108">**Save to source location**</span></span>  
 <span data-ttu-id="73e8e-109">Enregistrez les packages mis à niveau dans le même emplacement que celui spécifié dans la page **Sélectionner l’emplacement source** de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="73e8e-109">Save the upgraded packages to the same location as specified on the **Select Source Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="73e8e-110">Si vous voulez que l’Assistant sauvegarde les packages d’origine quand ils sont stockés dans le système de fichiers, sélectionnez l’option **Enregistrer à l’emplacement source** .</span><span class="sxs-lookup"><span data-stu-id="73e8e-110">If the original packages are stored in the file system and you want the wizard to back up those packages, select the **Save to source location** option.</span></span> <span data-ttu-id="73e8e-111">Pour plus d’informations, consultez [Mettre à niveau des packages Integration Services à l’aide de l’Assistant Mise à niveau de packages SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="73e8e-111">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
 <span data-ttu-id="73e8e-112">**Sélectionner le nouvel emplacement de destination**</span><span class="sxs-lookup"><span data-stu-id="73e8e-112">**Select new destination location**</span></span>  
 <span data-ttu-id="73e8e-113">Enregistrez les packages mis à niveau dans l'emplacement de destination qui est spécifié sur cette page.</span><span class="sxs-lookup"><span data-stu-id="73e8e-113">Save the upgraded packages to the destination location that is specified on this page.</span></span>  
  
 <span data-ttu-id="73e8e-114">**Source du package**</span><span class="sxs-lookup"><span data-stu-id="73e8e-114">**Package source**</span></span>  
 <span data-ttu-id="73e8e-115">Spécifiez l'emplacement où les packages de mise à niveau doivent être stockés.</span><span class="sxs-lookup"><span data-stu-id="73e8e-115">Specify where the upgrade packages are to be stored.</span></span> <span data-ttu-id="73e8e-116">Cette option a les valeurs répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="73e8e-116">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="73e8e-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="73e8e-117">Value</span></span>|<span data-ttu-id="73e8e-118">Description</span><span class="sxs-lookup"><span data-stu-id="73e8e-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73e8e-119">**Système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="73e8e-119">**File System**</span></span>|<span data-ttu-id="73e8e-120">Indique que les packages mis à niveau doivent être enregistrés dans un dossier sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="73e8e-120">Indicates that the upgraded packages are to be saved to a folder on the local computer.</span></span>|  
|<span data-ttu-id="73e8e-121">**Magasin de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="73e8e-121">**SSIS Package Store**</span></span>|<span data-ttu-id="73e8e-122">Indique que les packages mis à niveau doivent être enregistrés dans le magasin de packages Integration Services.</span><span class="sxs-lookup"><span data-stu-id="73e8e-122">Indicates that the upgraded packages are to be saved to the Integration Services package store.</span></span> <span data-ttu-id="73e8e-123">Le magasin de packages se compose de l'ensemble des dossiers du système de fichiers gérés par Integration Services.</span><span class="sxs-lookup"><span data-stu-id="73e8e-123">The package store consists of the set of file system folders that the Integration Services service manages.</span></span> <span data-ttu-id="73e8e-124">Pour plus d’informations, consultez [Gestion de packages &#40;Service SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="73e8e-124">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="73e8e-125">La sélection de cette valeur affiche les options dynamiques **Source du package** correspondantes.</span><span class="sxs-lookup"><span data-stu-id="73e8e-125">Selecting this value displays the corresponding **Package source** dynamics options.</span></span>|  
|<span data-ttu-id="73e8e-126">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="73e8e-126">**Microsoft SQL Server**</span></span>|<span data-ttu-id="73e8e-127">Indique que les packages mis à niveau doivent enregistrés dans une instance existante de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73e8e-127">Indicates that the upgraded packages are to be saved to an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="73e8e-128">La sélection de cette valeur affiche les options **Source du package** dynamiques correspondantes.</span><span class="sxs-lookup"><span data-stu-id="73e8e-128">Selecting this value displays the corresponding dynamic **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="73e8e-129">**Folder**</span><span class="sxs-lookup"><span data-stu-id="73e8e-129">**Folder**</span></span>  
 <span data-ttu-id="73e8e-130">Tapez le nom d’un dossier dans lequel enregistrer les packages mis à niveau, ou cliquez sur **Parcourir** et recherchez le dossier.</span><span class="sxs-lookup"><span data-stu-id="73e8e-130">Type the name of a folder to which the upgraded packages will be saved, or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="73e8e-131">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="73e8e-131">**Browse**</span></span>  
 <span data-ttu-id="73e8e-132">Recherchez le dossier dans lequel les packages mis à niveau seront enregistrés.</span><span class="sxs-lookup"><span data-stu-id="73e8e-132">Browse to locate the folder to which the upgraded packages will be saved.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="73e8e-133">Options dynamiques de la source du package</span><span class="sxs-lookup"><span data-stu-id="73e8e-133">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="73e8e-134">Source du package = Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="73e8e-134">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="73e8e-135">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="73e8e-135">**Server**</span></span>  
 <span data-ttu-id="73e8e-136">Tapez le nom du serveur sur lequel les packages de mise à niveau seront enregistrés, ou sélectionnez un serveur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="73e8e-136">Type the name of the server to which the upgrade packages will be saved, or select a server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="73e8e-137">Source du package = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="73e8e-137">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="73e8e-138">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="73e8e-138">**Server**</span></span>  
 <span data-ttu-id="73e8e-139">Tapez le nom du serveur sur lequel les packages de mise à niveau seront enregistrés, ou sélectionnez ce serveur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="73e8e-139">Type the name of the server to which the upgrade packages will be saved, or select this server in the list.</span></span>  
  
 <span data-ttu-id="73e8e-140">**Utiliser l’authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="73e8e-140">**Use Windows authentication**</span></span>  
 <span data-ttu-id="73e8e-141">Permet d'utiliser l'authentification Windows pour se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="73e8e-141">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="73e8e-142">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="73e8e-142">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="73e8e-143">Permet d’utiliser l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="73e8e-143">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="73e8e-144">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vous devez fournir un nom d’utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="73e8e-144">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="73e8e-145">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="73e8e-145">**User name**</span></span>  
 <span data-ttu-id="73e8e-146">Tapez le nom d’utilisateur à utiliser pendant l’utilisation de l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="73e8e-146">Type the user name to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="73e8e-147">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="73e8e-147">**Password**</span></span>  
 <span data-ttu-id="73e8e-148">Tapez le mot de passe à utiliser pendant l’utilisation de l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="73e8e-148">Type the password to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e8e-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="73e8e-149">See Also</span></span>  
 [<span data-ttu-id="73e8e-150">Mettre à niveau des packages Integration Services</span><span class="sxs-lookup"><span data-stu-id="73e8e-150">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
