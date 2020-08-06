---
title: Sélectionner l’emplacement source (Assistant Mise à niveau de packages SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectsourcelocation.f1
ms.assetid: 429f146e-edb4-4401-a225-f2c8468971c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e24eec77dc87a6215f9d686cf5af964cc244d68d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695816"
---
# <a name="select-source-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="0f0ab-102">Sélectionner l'emplacement source (Assistant Mise à niveau de packages SSIS)</span><span class="sxs-lookup"><span data-stu-id="0f0ab-102">Select Source Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="0f0ab-103">Utilisez la page **Sélectionner l’emplacement source** pour spécifier la source à partir de laquelle effectuer la mise à niveau de packages.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-103">Use the **Select Source Location** page to specify the source from which to upgrade packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f0ab-104">Cette page est disponible uniquement quand vous exécutez l’Assistant Mise à niveau de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] à partir de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou de l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="0f0ab-105">**Pour exécuter l'Assistant Mise à niveau de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="0f0ab-106">Mettre à niveau des packages Integration Services à l'aide de l'Assistant Mise à niveau de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="0f0ab-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="0f0ab-107">Options statiques</span><span class="sxs-lookup"><span data-stu-id="0f0ab-107">Static Options</span></span>  
 <span data-ttu-id="0f0ab-108">**Source du package**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-108">**Package source**</span></span>  
 <span data-ttu-id="0f0ab-109">Sélectionnez l'emplacement de stockage qui contient les packages à mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-109">Select the storage location that contains the packages to be upgraded.</span></span> <span data-ttu-id="0f0ab-110">Cette option a les valeurs répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-110">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="0f0ab-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="0f0ab-111">Value</span></span>|<span data-ttu-id="0f0ab-112">Description</span><span class="sxs-lookup"><span data-stu-id="0f0ab-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f0ab-113">**Système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-113">**File System**</span></span>|<span data-ttu-id="0f0ab-114">Indique que les packages à mettre à niveau se trouvent dans un dossier sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-114">Indicates that the packages to be upgraded are in a folder on the local computer.</span></span><br /><br /> <span data-ttu-id="0f0ab-115">Pour que l'Assistant sauvegarde les packages d'origine avant de les mettre à niveau, les packages d'origine doivent être stockés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-115">To have the wizard back up the original packages before upgrading those packages, the original packages must be stored in the file system.</span></span> <span data-ttu-id="0f0ab-116">Pour plus d'informations, consultez la rubrique de procédure.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-116">For more information, see How To Topic.</span></span>|  
|<span data-ttu-id="0f0ab-117">**Magasin de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-117">**SSIS Package Store**</span></span>|<span data-ttu-id="0f0ab-118">Indique que les packages à mettre à niveau se trouvent dans le magasin de packages.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-118">Indicates that the packages to be upgraded are in the package store.</span></span> <span data-ttu-id="0f0ab-119">Le magasin de packages se compose de l’ensemble des dossiers du système de fichiers gérés par le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f0ab-119">The package store consists of the set of file system folders that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span> <span data-ttu-id="0f0ab-120">Pour plus d’informations, consultez [Gestion de packages &#40;Service SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="0f0ab-120">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="0f0ab-121">La sélection de cette valeur affiche les options dynamiques **Source du package** correspondantes.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-121">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
|<span data-ttu-id="0f0ab-122">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-122">**Microsoft SQL Server**</span></span>|<span data-ttu-id="0f0ab-123">Indique que les packages à mettre à niveau proviennent d’une instance existante de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f0ab-123">Indicates the packages to be upgraded are from an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="0f0ab-124">La sélection de cette valeur affiche les options dynamiques **Source du package** correspondantes.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-124">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="0f0ab-125">**Folder**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-125">**Folder**</span></span>  
 <span data-ttu-id="0f0ab-126">Tapez le nom d’un dossier qui contient les packages à mettre à niveau, ou cliquez sur **Parcourir** et recherchez le dossier.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-126">Type the name of a folder that contains the packages you want to upgrade or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="0f0ab-127">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-127">**Browse**</span></span>  
 <span data-ttu-id="0f0ab-128">Recherchez le dossier qui contient les packages à mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-128">Browse to locate the folder that contains the packages you want to upgrade.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="0f0ab-129">Options dynamiques de la source du package</span><span class="sxs-lookup"><span data-stu-id="0f0ab-129">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="0f0ab-130">Source du package = Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="0f0ab-130">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="0f0ab-131">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-131">**Server**</span></span>  
 <span data-ttu-id="0f0ab-132">Tapez le nom du serveur sur lesquels se trouvent les packages à mettre à niveau ou sélectionnez ce serveur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-132">Type the name of the server that has the packages to be upgraded, or select this server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="0f0ab-133">Source du package = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="0f0ab-133">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="0f0ab-134">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-134">**Server**</span></span>  
 <span data-ttu-id="0f0ab-135">Tapez le nom du serveur sur lesquels se trouvent les packages à mettre à niveau ou sélectionnez ce serveur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-135">Type the name of the server that has the packages to be upgraded, or select this server from the list.</span></span>  
  
 <span data-ttu-id="0f0ab-136">**Utiliser l’authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-136">**Use Windows authentication**</span></span>  
 <span data-ttu-id="0f0ab-137">Permet d'utiliser l'authentification Windows pour se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-137">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="0f0ab-138">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-138">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="0f0ab-139">Permet d’utiliser l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-139">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="0f0ab-140">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vous devez fournir un nom d’utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-140">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="0f0ab-141">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-141">**User name**</span></span>  
 <span data-ttu-id="0f0ab-142">Tapez le nom d’utilisateur que l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilisera pour se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-142">Type the user name that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
 <span data-ttu-id="0f0ab-143">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="0f0ab-143">**Password**</span></span>  
 <span data-ttu-id="0f0ab-144">Tapez le mot de passe que l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilisera pour se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="0f0ab-144">Type the password that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f0ab-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f0ab-145">See Also</span></span>  
 [<span data-ttu-id="0f0ab-146">Mettre à niveau des packages Integration Services</span><span class="sxs-lookup"><span data-stu-id="0f0ab-146">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
