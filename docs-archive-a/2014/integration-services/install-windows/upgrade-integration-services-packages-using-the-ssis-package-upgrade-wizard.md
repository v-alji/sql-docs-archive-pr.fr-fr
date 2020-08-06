---
title: Mettre à niveau des packages Integration Services à l’aide de l’Assistant Mise à niveau de packages SSIS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, upgrading
- upgrading Integration Services packages
ms.assetid: 9359275a-48f5-4d1e-8ae7-e797759e3ccf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bcafd1c9750d8333639ca2d315512a2c2b8759c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605637"
---
# <a name="upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="cc0ef-102">Mettre à niveau des packages Integration Services à l'aide de l'Assistant Mise à niveau de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="cc0ef-102">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>
  <span data-ttu-id="cc0ef-103">Vous pouvez mettre à niveau des packages créés dans des versions antérieures d' [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] vers le format [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilisé par [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc0ef-103">You can upgrade packages that were created in earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] format that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cc0ef-104">fournit l'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] à cet effet.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-104">provides the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard to help in this process.</span></span> <span data-ttu-id="cc0ef-105">Étant donné que vous pouvez configurer l'Assistant pour qu'il sauvegarde vos packages d'origine, vous pouvez continuer à les utiliser si vous rencontrez des problèmes de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-105">Because you can configure the wizard to backup up your original packages, you can continue to use the original packages if you experience upgrade difficulties.</span></span>  
  
 <span data-ttu-id="cc0ef-106">L'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] est installé lors de l'installation de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc0ef-106">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is installed when [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc0ef-107">L'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] est disponible dans les éditions Standard, Enterprise et Developer de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc0ef-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is available in the Standard, Enterprise, and Developer Editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cc0ef-108">Pour plus d’informations sur la mise à niveau des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , consultez [Mettre à niveau des packages Integration Services](upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="cc0ef-108">For more information about how to upgrade [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, see [Upgrade Integration Services Packages](upgrade-integration-services-packages.md).</span></span>  
  
 <span data-ttu-id="cc0ef-109">Le reste de cette rubrique décrit comment exécuter l'Assistant et sauvegarder les packages d'origine.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-109">The remainder of this topic describes how to run the wizard and back up the original packages.</span></span>  
  
## <a name="running-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="cc0ef-110">Exécution de l'Assistant Mise à niveau de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="cc0ef-110">Running the SSIS Package Upgrade Wizard</span></span>  
 <span data-ttu-id="cc0ef-111">Vous pouvez exécuter l'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] à partir de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ou de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-111">You can run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or at the command prompt.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-data-tools"></a><span data-ttu-id="cc0ef-112">Pour exécuter l'Assistant à partir de l'outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="cc0ef-112">To run the wizard from SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="cc0ef-113">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], créez ou ouvrez un projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc0ef-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="cc0ef-114">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le nœud **Packages SSIS** , puis cliquez sur **Mettre à niveau tous les packages** pour mettre à niveau tous les packages sous ce nœud.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-114">In Solution Explorer, right-click the **SSIS Packages** node, and then click **Upgrade All Packages** to upgrade all the packages under this node.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cc0ef-115">Lorsque vous ouvrez un projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient des packages [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] ou [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ouvre automatiquement l'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc0ef-115">When you open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] packages, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] automatically opens the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-management-studio"></a><span data-ttu-id="cc0ef-116">Pour exécuter l'Assistant à partir de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc0ef-116">To run the wizard from SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="cc0ef-117">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], développez le nœud **Packages stockés** , cliquez avec le bouton droit sur le nœud **Système de fichiers** ou **MSDB** , puis cliquez sur **Mettre à niveau les packages**.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-117">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], expand the **Stored Packages** node, and right-click the **File System** or **MSDB** node, and then click **Upgrade Packages**.</span></span>  
  
#### <a name="to-run-the-wizard-at-the-command-prompt"></a><span data-ttu-id="cc0ef-118">Pour exécuter l'Assistant à l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="cc0ef-118">To run the wizard at the command prompt</span></span>  
  
-   <span data-ttu-id="cc0ef-119">À l’invite de commandes, exécutez le fichier SSISUpgrade.exe à partir du dossier **C:\Program Files\Microsoft SQL Server\120\DTS\Binn**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-119">At the command prompt, run the SSISUpgrade.exe file from the **C:\Program Files\Microsoft SQL Server\120\DTS\Binn** folder.</span></span>  
  
## <a name="backing-up-the-original-packages"></a><span data-ttu-id="cc0ef-120">Sauvegarde des packages d'origine</span><span class="sxs-lookup"><span data-stu-id="cc0ef-120">Backing Up the Original Packages</span></span>  
 <span data-ttu-id="cc0ef-121">Pour sauvegarder les packages d'origine, les packages d'origine et les package mis à niveau doivent être stockés dans le même dossier du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-121">To back up the original packages, both the original packages and the upgraded packages must be stored in the same folder in the file system.</span></span> <span data-ttu-id="cc0ef-122">Selon la façon dont vous exécutez l'Assistant, cet emplacement de stockage peut être sélectionné automatiquement.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-122">Depending on how you run the wizard, this storage location might be automatically selected.</span></span>  
  
-   <span data-ttu-id="cc0ef-123">Lorsque vous exécutez l'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] à partir de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], l'Assistant stocke automatiquement à la fois les packages d'origine et les packages mis à niveau dans le même dossier dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-123">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the wizard automatically stores both the original packages and upgraded packages in the same folder in the file system.</span></span>  
  
-   <span data-ttu-id="cc0ef-124">Lorsque vous exécutez l'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] à partir de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de l'invite de commandes, vous pouvez spécifier différents emplacements de stockage pour les packages d'origine et les packages mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-124">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, you can specify different storage locations for the original and upgraded packages.</span></span> <span data-ttu-id="cc0ef-125">Pour sauvegarder les packages d'origine, n'oubliez pas de spécifier que les packages d'origine et les packages mis à niveau sont stockés dans le même dossier du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-125">To back up the original packages, make sure to specify that both the original and upgraded packages are stored in the same folder in the file system.</span></span> <span data-ttu-id="cc0ef-126">Si vous spécifiez d'autres options de stockage, l'Assistant ne sera pas en mesure de sauvegarder les packages d'origine.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-126">If you specify any other storage options, the wizard will not be able to back up the original packages.</span></span>  
  
 <span data-ttu-id="cc0ef-127">Lorsqu'il sauvegarde les packages d'origine, l'Assistant stocke une copie des packages d'origine dans un dossier **SSISBackupFolder** .</span><span class="sxs-lookup"><span data-stu-id="cc0ef-127">When the wizard backs up the original packages, the wizard stores a copy of the original packages in an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="cc0ef-128">Il crée le dossier **SSISBackupFolder** en tant que sous-dossier du dossier qui contient les packages d'origine et les packages mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-128">The wizard creates this **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-management-studio-or-at-the-command-prompt"></a><span data-ttu-id="cc0ef-129">Pour sauvegarder les packages d'origine dans SQL Server Management Studio ou à l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="cc0ef-129">To back up the original packages in SQL Server Management Studio or at the command prompt</span></span>  
  
1.  <span data-ttu-id="cc0ef-130">Enregistrez les packages d'origine à un emplacement du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-130">Save the original packages to a location on the file system.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cc0ef-131">L'option de sauvegarde de l'Assistant fonctionne uniquement avec les packages stockés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-131">The backup option in the wizard only works with packages that have been stored to the file system.</span></span>  
  
2.  <span data-ttu-id="cc0ef-132">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou à l'invite de commandes, exécutez l'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc0ef-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
3.  <span data-ttu-id="cc0ef-133">Dans la page **Sélectionner l'emplacement source** de l'Assistant, définissez la propriété **Source du package** à **Système de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-133">On the **Select Source Location** page of the wizard, set the **Package source** property to **File System**.</span></span>  
  
4.  <span data-ttu-id="cc0ef-134">Dans la page **Sélectionner l’emplacement de destination** de l’Assistant, sélectionnez **Enregistrer à l’emplacement source** pour enregistrer les packages mis à niveau au même emplacement que les packages d’origine.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-134">On the **Select Destination Location** page of the wizard, select **Save to source location** tosave the upgraded packages to the same location as the original packages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cc0ef-135">L'option de sauvegarde de l'Assistant n'est disponible que lorsque les packages mis à niveau sont stockés dans le même dossier que les packages d'origine.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-135">The backup option in the wizard is available only when the upgraded packages are stored in the same folder as the original packages.</span></span>  
  
5.  <span data-ttu-id="cc0ef-136">Dans la page **Sélectionner les options de gestion des packages** de l'Assistant, sélectionnez l'option **Sauvegarder les packages d'origine** .</span><span class="sxs-lookup"><span data-stu-id="cc0ef-136">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-data-tools"></a><span data-ttu-id="cc0ef-137">Pour sauvegarder les packages d'origine dans les outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="cc0ef-137">To back up the original packages in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="cc0ef-138">Enregistrez les packages d'origine à un emplacement du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-138">Save the original packages to a location on the file system.</span></span>  
  
2.  <span data-ttu-id="cc0ef-139">Dans la page **Sélectionner les options de gestion des packages** de l'Assistant, sélectionnez l'option **Sauvegarder les packages d'origine** .</span><span class="sxs-lookup"><span data-stu-id="cc0ef-139">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="cc0ef-140">L’option **sauvegarder les packages d’origine** ne s’affiche pas lorsque vous ouvrez un [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] projet ou dans, ce [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] qui lance automatiquement l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-140">The **Backup original packages** option is not displayed when you open a [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], which automatically launches the wizard.</span></span>  
  
3.  <span data-ttu-id="cc0ef-141">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], exécutez l'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc0ef-141">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
  
