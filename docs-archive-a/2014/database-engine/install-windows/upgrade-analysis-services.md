---
title: Mettre à niveau Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- upgrading databases
- databases [Analysis Services], upgrading
- installing Analysis Services, side-by-side installations
- Analysis Services upgrades
- Analysis Services upgrades, about upgrading Analysis Services
- SSAS, database migration
- upgrading Analysis Services
- installing Analysis Services, upgrading
- SSAS, upgrading
ms.assetid: a131d329-386e-4470-aaa9-ffcde4e5ec0c
author: Minewiskan
ms.author: owend
ms.openlocfilehash: 78bf7f27233bcfd46bc1f189324eddc72adcc961
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603614"
---
# <a name="upgrade-analysis-services"></a><span data-ttu-id="896c4-102">Mettre à niveau Analysis Services</span><span class="sxs-lookup"><span data-stu-id="896c4-102">Upgrade Analysis Services</span></span>
  <span data-ttu-id="896c4-103">Utilisez le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour mettre à niveau [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896c4-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="896c4-104">Pour plus d’informations sur la mise à niveau [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode SharePoint, consultez [mettre à niveau PowerPivot pour SharePoint](upgrade-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="896c4-104">For detailed information on upgrading [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in SharePoint mode, see [Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md).</span></span> <span data-ttu-id="896c4-105">Pour plus d’informations sur la mise à niveau d’une instance de SQL Server existante, consultez [mise à niveau vers SQL Server 2014 à l’aide de l’Assistant installation &#40;&#41;d’installation ](upgrade-sql-server-using-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="896c4-105">For more information about upgrading an existing SQL Server instance, see [Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;](upgrade-sql-server-using-the-installation-wizard-setup.md).</span></span>  
  
## <a name="known-upgrade-issues"></a><span data-ttu-id="896c4-106">Problèmes de mise à niveau connus</span><span class="sxs-lookup"><span data-stu-id="896c4-106">Known Upgrade Issues</span></span>  
 <span data-ttu-id="896c4-107">Avant d'effectuer la mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="896c4-107">Before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], review the following:</span></span>  
  
-   <span data-ttu-id="896c4-108">[Notes de publication de SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="896c4-108">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
-   <span data-ttu-id="896c4-109">Pour savoir quelles [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fonctionnalités et fonctionnalités ont été supprimées, déconseillées ou modifiées, consultez [Analysis Services la compatibilité descendante](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span><span class="sxs-lookup"><span data-stu-id="896c4-109">To learn which [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] features and functionality have been discontinued, deprecated, or changed see [Analysis Services Backward Compatibility](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span></span>  
  
## <a name="pre-upgrade-checklist"></a><span data-ttu-id="896c4-110">Liste de contrôle préalable à la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="896c4-110">Pre-Upgrade Checklist</span></span>  
 <span data-ttu-id="896c4-111">Avant d'effectuer la mise à niveau, passez en revue les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="896c4-111">Before upgrading, review the following information:</span></span>  
  
-   [<span data-ttu-id="896c4-112">Mises à niveau de la version et de l’édition prises en charge</span><span class="sxs-lookup"><span data-stu-id="896c4-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="896c4-113">Configuration matérielle et logicielle requise pour l’installation de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="896c4-113">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
-   [<span data-ttu-id="896c4-114">Paramètres de l’outil d’analyse de configuration système</span><span class="sxs-lookup"><span data-stu-id="896c4-114">Check Parameters for the System Configuration Checker</span></span>](check-parameters-for-the-system-configuration-checker.md)  
  
-   [<span data-ttu-id="896c4-115">Considérations sur la sécurité pour une installation SQL Server</span><span class="sxs-lookup"><span data-stu-id="896c4-115">Security Considerations for a SQL Server Installation</span></span>](../../sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
-   [<span data-ttu-id="896c4-116">Sauvegarde et restauration de bases de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="896c4-116">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
-   [<span data-ttu-id="896c4-117">Utiliser le Conseiller de mise à niveau pour la préparation des mises à niveau</span><span class="sxs-lookup"><span data-stu-id="896c4-117">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
## <a name="upgrading-analysis-services"></a><span data-ttu-id="896c4-118">Mise à niveau d'Analysis Services</span><span class="sxs-lookup"><span data-stu-id="896c4-118">Upgrading Analysis Services</span></span>  
 <span data-ttu-id="896c4-119">Différentes approches s'offrent à vous pour mettre à niveau le serveur et les données :</span><span class="sxs-lookup"><span data-stu-id="896c4-119">You can choose from several approaches to upgrade server and data:</span></span>  
  
-   <span data-ttu-id="896c4-120">Une **mise à niveau sur place** remplace les fichiers programme existants par les [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] fichiers programme.</span><span class="sxs-lookup"><span data-stu-id="896c4-120">An **in-place upgrade** replaces the existing program files with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] program files.</span></span> <span data-ttu-id="896c4-121">Les bases de données restent au même emplacement.</span><span class="sxs-lookup"><span data-stu-id="896c4-121">Databases remain in the same location.</span></span> <span data-ttu-id="896c4-122">Les dossiers programme sont mis à jour pour refléter le nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="896c4-122">Program folders are updated to reflect the new name.</span></span>  
  
-   <span data-ttu-id="896c4-123">Une **mise à niveau côte à côte** est une nouvelle installation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sur le même ordinateur qui a une instance de Analysis Services existante.</span><span class="sxs-lookup"><span data-stu-id="896c4-123">A **side-by-side upgrade** is a new installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on the same computer that has an existing Analysis Services instance.</span></span> <span data-ttu-id="896c4-124">Vous pouvez déplacer les bases de données vers la nouvelle instance du même ordinateur, puis désinstaller l'ancienne version si vous n'en avez plus l'utilité.</span><span class="sxs-lookup"><span data-stu-id="896c4-124">You can move databases over to the new instance on the same computer, and then uninstall the old version if you no longer use it.</span></span>  
  
-   <span data-ttu-id="896c4-125">Vous pouvez également installer Analysis Services sur le nouveau matériel, puis migrer les bases de données existantes vers ce serveur.</span><span class="sxs-lookup"><span data-stu-id="896c4-125">You can also install Analysis Services on new hardware and then migrate existing databases to that server.</span></span>  
  
## <a name="in-place-upgrade"></a><span data-ttu-id="896c4-126">Mise à niveau sur place</span><span class="sxs-lookup"><span data-stu-id="896c4-126">In-place Upgrade</span></span>  
 <span data-ttu-id="896c4-127">Vous pouvez mettre à niveau une instance existante de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et, dans le cadre du processus de mise à niveau, migrer automatiquement les bases de données existantes de l’ancienne instance vers la nouvelle instance.</span><span class="sxs-lookup"><span data-stu-id="896c4-127">You can upgrade an existing instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and, as part of the upgrade process, automatically migrate existing databases from the old instance to the new instance.</span></span> <span data-ttu-id="896c4-128">Comme les métadonnées et les données binaires sont compatibles entre les deux versions, vous conserverez les données après la mise à niveau et vous n'avez pas à migrer les données manuellement.</span><span class="sxs-lookup"><span data-stu-id="896c4-128">Because the metadata and binary data is compatible between the two versions, you will retain the data after you upgrade and you do not have to manually migrate the data.</span></span>  
  
 <span data-ttu-id="896c4-129">Pour mettre à niveau une instance existante, exécutez le programme d'installation et spécifiez le nom de l'instance existante comme nom de la nouvelle instance.</span><span class="sxs-lookup"><span data-stu-id="896c4-129">To upgrade an existing instance, run Setup and specify the name of the existing instance as the name of the new instance.</span></span>  
  
## <a name="upgrading-databases"></a><span data-ttu-id="896c4-130">Mise à niveau des bases de données</span><span class="sxs-lookup"><span data-stu-id="896c4-130">Upgrading Databases</span></span>  
 <span data-ttu-id="896c4-131">Les bases de données créées dans les versions antérieures d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] s'exécutent sur le serveur mis à niveau sous un ancien paramétrage de niveau de compatibilité de base de données.</span><span class="sxs-lookup"><span data-stu-id="896c4-131">Databases that were created in previous versions of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] run on the upgraded server under an older database compatibility level setting.</span></span> <span data-ttu-id="896c4-132">Le niveau de compatibilité des bases de données créées dans les versions suivantes est 105.</span><span class="sxs-lookup"><span data-stu-id="896c4-132">Databases created in the following versions, have a database compatibility level of 105.</span></span> <span data-ttu-id="896c4-133">Vous pouvez modifier le niveau de compatibilité si vous souhaitez utiliser des fonctionnalités qui nécessitent un niveau de compatibilité de base de données plus récent.</span><span class="sxs-lookup"><span data-stu-id="896c4-133">You can change the compatibility level if you want to use features that require a newer database compatibility level.</span></span> <span data-ttu-id="896c4-134">Une autre solution consiste à exécuter les bases de données sur le serveur mis à niveau en utilisant les paramètres d'origine.</span><span class="sxs-lookup"><span data-stu-id="896c4-134">Otherwise, you can run the databases on the upgraded server using the original settings.</span></span> <span data-ttu-id="896c4-135">Pour plus d’informations, consultez [définir le niveau de compatibilité d’une base de données multidimensionnelle &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="896c4-135">For more information, see [Set the Compatibility Level of a Multidimensional Database &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span></span>  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="896c4-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="896c4-136">See Also</span></span>  
 <span data-ttu-id="896c4-137">[Fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="896c4-137">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="896c4-138">[Planification d'une installation SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="896c4-138">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="896c4-139">[Compréhension de l’architecture Microsoft OLAP](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span><span class="sxs-lookup"><span data-stu-id="896c4-139">[Understanding Microsoft OLAP Architecture](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span></span>  
 <span data-ttu-id="896c4-140">[Mettre à niveau PowerPivot pour SharePoint](upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="896c4-140">[Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="896c4-141">[Installer Analysis Services en mode multidimensionnel et d’exploration de données](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span><span class="sxs-lookup"><span data-stu-id="896c4-141">[Install Analysis Services in Multidimensional and Data Mining Mode](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span></span>  
 [<span data-ttu-id="896c4-142">PowerPivot for SharePoint 2010 Installation</span><span class="sxs-lookup"><span data-stu-id="896c4-142">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
