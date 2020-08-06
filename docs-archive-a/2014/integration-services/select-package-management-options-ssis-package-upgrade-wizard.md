---
title: Sélectionner les options de Package Management (Assistant Mise à niveau de packages SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectpackagemgtoptions.f1
ms.assetid: 810fc020-51cd-43ed-9f35-af99b4f35947
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5113ad5a1f6758a75742ca58aef04ce92168649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614724"
---
# <a name="select-package-management-options-ssis-package-upgrade-wizard"></a><span data-ttu-id="bd83b-102">Sélectionner les options de gestion des packages (Assistant Mise à niveau de packages SSIS)</span><span class="sxs-lookup"><span data-stu-id="bd83b-102">Select Package Management Options (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="bd83b-103">Utilisez la page **Sélectionner les options de gestion des packages** pour spécifier des options permettant de mettre à niveau des packages.</span><span class="sxs-lookup"><span data-stu-id="bd83b-103">Use the **Select Package Management Options** page to specify options for upgrading packages.</span></span>  
  
 <span data-ttu-id="bd83b-104">**Pour exécuter l'Assistant Mise à niveau de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="bd83b-104">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="bd83b-105">Mettre à niveau des packages Integration Services à l'aide de l'Assistant Mise à niveau de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="bd83b-105">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="bd83b-106">Options</span><span class="sxs-lookup"><span data-stu-id="bd83b-106">Options</span></span>  
 <span data-ttu-id="bd83b-107">**Mettre à jour les chaînes de connexion pour l'utilisation des nouveaux noms de fournisseurs**</span><span class="sxs-lookup"><span data-stu-id="bd83b-107">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="bd83b-108">Mettez à jour les chaînes de connexion afin d'utiliser les noms des fournisseurs suivants pour la version actuelle d' [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bd83b-108">Update the connection strings to use the names for the following providers for the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="bd83b-109">Fournisseur OLE DB pour [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd83b-109">OLE DB Provider for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="bd83b-110">Native Client</span><span class="sxs-lookup"><span data-stu-id="bd83b-110">Native Client</span></span>  
  
 <span data-ttu-id="bd83b-111">L'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] met à jour uniquement les chaînes de connexion qui sont stockées dans des gestionnaires de connexions.</span><span class="sxs-lookup"><span data-stu-id="bd83b-111">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="bd83b-112">Il ne met pas à jour les chaînes de connexion qui sont construites dynamiquement à l'aide du langage d'expression [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou en utilisant du code dans une tâche de script.</span><span class="sxs-lookup"><span data-stu-id="bd83b-112">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="bd83b-113">**Valider les packages mis à niveau**</span><span class="sxs-lookup"><span data-stu-id="bd83b-113">**Validate upgrade packages**</span></span>  
 <span data-ttu-id="bd83b-114">Validez les packages de mise à niveau et enregistrez uniquement ceux dont la validation a réussi.</span><span class="sxs-lookup"><span data-stu-id="bd83b-114">Validate the upgrade packages and save only those upgrade packages that pass validation.</span></span>  
  
 <span data-ttu-id="bd83b-115">Si vous ne sélectionnez pas cette option, l'Assistant ne validera pas les packages de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="bd83b-115">If you do not select this option, the wizard will not validate upgrade packages.</span></span> <span data-ttu-id="bd83b-116">Par conséquent, il les enregistrera tous, qu'ils soient valides ou non.</span><span class="sxs-lookup"><span data-stu-id="bd83b-116">Therefore, the wizard will save all upgrade packages, regardless of whether the packages are valid or not.</span></span> <span data-ttu-id="bd83b-117">L’Assistant enregistre les packages de mise à niveau dans la destination spécifiée dans la page **Sélectionner l’emplacement de destination** de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="bd83b-117">The wizard saves upgrade packages to the destination that is specified on the **SelectDestination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="bd83b-118">La validation ralentit le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="bd83b-118">Validation adds time to the upgrade process.</span></span> <span data-ttu-id="bd83b-119">Nous vous recommandons de ne pas sélectionner cette option pour les packages volumineux qui sont susceptibles d'être mis à niveau avec succès.</span><span class="sxs-lookup"><span data-stu-id="bd83b-119">We recommend that you do not select this option for large packages that are likely to be upgraded successfully.</span></span>  
  
 <span data-ttu-id="bd83b-120">**Créer des ID de package**</span><span class="sxs-lookup"><span data-stu-id="bd83b-120">**Create new package IDs**</span></span>  
 <span data-ttu-id="bd83b-121">Créez de nouveaux ID de package pour les packages de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="bd83b-121">Create new package IDs for the upgrade packages.</span></span>  
  
 <span data-ttu-id="bd83b-122">**Continuer le processus de mise à niveau lorsque la mise à niveau d’un package échoue**</span><span class="sxs-lookup"><span data-stu-id="bd83b-122">**Continue upgrade process when a package upgrade fails**</span></span>  
 <span data-ttu-id="bd83b-123">Spécifiez que, quand un package ne peut pas être mis à niveau, l’Assistant Mise à niveau de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] continue à mettre à niveau les packages restants.</span><span class="sxs-lookup"><span data-stu-id="bd83b-123">Specify that when a package cannot be upgraded, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard continues to upgrade the remaining packages.</span></span>  
  
 <span data-ttu-id="bd83b-124">**Conflits de noms de packages**</span><span class="sxs-lookup"><span data-stu-id="bd83b-124">**Package name conflicts**</span></span>  
 <span data-ttu-id="bd83b-125">Spécifiez la façon dont l'Assistant doit gérer les packages qui portent le même nom.</span><span class="sxs-lookup"><span data-stu-id="bd83b-125">Specify how the wizard should handle packages that have the same name.</span></span> <span data-ttu-id="bd83b-126">Cette option a les valeurs répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="bd83b-126">This option has the values listed in the following table.</span></span>  
  
 <span data-ttu-id="bd83b-127">**Remplacer les fichiers de packages existants**</span><span class="sxs-lookup"><span data-stu-id="bd83b-127">**Overwrite existing package files**</span></span>  
 <span data-ttu-id="bd83b-128">Remplace le package existant par le package de mise à niveau du même nom.</span><span class="sxs-lookup"><span data-stu-id="bd83b-128">Replaces the existing package with the upgrade package of the same name.</span></span>  
  
 <span data-ttu-id="bd83b-129">**Ajouter des suffixes numériques pour mettre à niveau les noms de packages**</span><span class="sxs-lookup"><span data-stu-id="bd83b-129">**Add numeric suffixes to upgrade package names**</span></span>  
 <span data-ttu-id="bd83b-130">Ajoute un suffixe numérique au nom du package de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="bd83b-130">Adds a numeric suffix to the name of the upgrade package.</span></span>  
  
 <span data-ttu-id="bd83b-131">**Ne pas mettre à niveau les packages**</span><span class="sxs-lookup"><span data-stu-id="bd83b-131">**Do not upgrade packages**</span></span>  
 <span data-ttu-id="bd83b-132">Arrête la mise à niveau des packages et affiche une erreur à la fin de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="bd83b-132">Stops the packages from being upgraded and displays an error when you complete the wizard.</span></span>  
  
 <span data-ttu-id="bd83b-133">Ces options ne sont pas disponibles quand vous sélectionnez l’option **Enregistrer à l’emplacement source** dans la page **Sélectionner l’emplacement de destination** de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="bd83b-133">These options are not available when you select the **Save to source location** option on the **Select Destination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="bd83b-134">**Ignorer les configurations**</span><span class="sxs-lookup"><span data-stu-id="bd83b-134">**Ignore Configurations**</span></span>  
 <span data-ttu-id="bd83b-135">Ne charge pas les configurations de package pendant la mise à niveau des packages.</span><span class="sxs-lookup"><span data-stu-id="bd83b-135">Does not load package configurations during the package upgrade.</span></span> <span data-ttu-id="bd83b-136">L'activation de cette option réduit le temps requis pour mettre à niveau le package.</span><span class="sxs-lookup"><span data-stu-id="bd83b-136">Selecting this option reduces the time required to upgrade the package.</span></span>  
  
 <span data-ttu-id="bd83b-137">**Sauvegarder les packages d’origine**</span><span class="sxs-lookup"><span data-stu-id="bd83b-137">**Backup original packages**</span></span>  
 <span data-ttu-id="bd83b-138">Cette option demande à l’Assistant de sauvegarder les packages d’origine dans un dossier **SSISBackupFolder** .</span><span class="sxs-lookup"><span data-stu-id="bd83b-138">Have the wizard back up the original packages to an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="bd83b-139">L’Assistant crée le dossier **SSISBackupFolder** en tant que sous-dossier du dossier qui contient les packages d’origine et les packages mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="bd83b-139">The wizard creates the **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd83b-140">Cette option est disponible uniquement lorsque vous spécifiez que les packages d'origine et les packages mis à niveau sont stockés dans le système de fichiers et dans le même dossier.</span><span class="sxs-lookup"><span data-stu-id="bd83b-140">This option is available only when you specify that the original packages and the upgraded packages are stored in the file system and in the same folder.</span></span>  
  
 <span data-ttu-id="bd83b-141">Pour plus d’informations, consultez [Mettre à niveau des packages Integration Services à l’aide de l’Assistant Mise à niveau de packages SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="bd83b-141">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd83b-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd83b-142">See Also</span></span>  
 [<span data-ttu-id="bd83b-143">Mettre à niveau des packages Integration Services</span><span class="sxs-lookup"><span data-stu-id="bd83b-143">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
