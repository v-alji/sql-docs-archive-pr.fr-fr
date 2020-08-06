---
title: Installation pour SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 09/09/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
f1_keywords:
- sql12.portal.Installation.f1
helpviewer_keywords:
- installing SQL Server, initial installation
- installation [SQL Server]
- initial installation [SQL Server]
ms.assetid: edd75f68-dc62-4479-a596-57ce8ad632e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 62630400f276b00de8acfa875244558cdb39e47b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697108"
---
# <a name="installation-for-sql-server-2014"></a><span data-ttu-id="30986-102">Installation de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="30986-102">Installation for SQL Server 2014</span></span>
 ## <a name="download-sql-server-2014-express"></a>[<span data-ttu-id="30986-103">Télécharger SQL Server Express 2014</span><span class="sxs-lookup"><span data-stu-id="30986-103">Download SQL Server 2014 Express</span></span>](http://www.hanselman.com/blog/DownloadSQLServerExpress.aspx)
  <span data-ttu-id="30986-104">**Nous vous remercions de [Scott Hanselman](http://www.hanselman.com/) pour la collecte de tous les liens du package d’installation en un seul endroit.**</span><span class="sxs-lookup"><span data-stu-id="30986-104">**Thank you to [Scott Hanselman](http://www.hanselman.com/) for collecting all of the installer package links in one place!**</span></span>
  
  <span data-ttu-id="30986-105">L'Assistant Installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournit une arborescence de fonctionnalités unique pour installer tous les composants [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="30986-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard provides a single feature tree to install all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]  
  
-   [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]  
  
-   <span data-ttu-id="30986-106">Outils d'administration</span><span class="sxs-lookup"><span data-stu-id="30986-106">Management tools</span></span>  
  
-   <span data-ttu-id="30986-107">Composants de connectivité</span><span class="sxs-lookup"><span data-stu-id="30986-107">Connectivity components</span></span>  
  
 <span data-ttu-id="30986-108">Vous pouvez installer chaque composant individuellement ou sélectionner une combinaison de composants ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="30986-108">You can install each component individually or select a combination of the components listed above.</span></span> <span data-ttu-id="30986-109">Pour faire le meilleur choix parmi les éditions et les composants disponibles dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consultez [éditions et composants de SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) et [fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="30986-109">To make the best choice among the editions and components available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) and [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="30986-110">est disponible en éditions 32 bits et 64 bits.</span><span class="sxs-lookup"><span data-stu-id="30986-110">is available in 32-bit and 64-bit editions.</span></span>
 
 <span data-ttu-id="30986-111">**Essayez-le :**</span><span class="sxs-lookup"><span data-stu-id="30986-111">**Try it out:**</span></span>  
  
-   <span data-ttu-id="30986-112">Vous avez un compte Azure ?</span><span class="sxs-lookup"><span data-stu-id="30986-112">Have an Azure account?</span></span>  <span data-ttu-id="30986-113">Cliquez **[ici](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** pour lancer une machine virtuelle avec SQL Server 2014 Service Pack 1 (SP1) déjà installé.</span><span class="sxs-lookup"><span data-stu-id="30986-113">Then go **[Here](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** to spin up a Virtual Machine with SQL Server 2014 Service Pack 1 (SP1) already installed.</span></span> <span data-ttu-id="30986-114">Pour plus d’informations sur SQL Server 2014 (SP1), consultez les [informations de version de SQL Server 2014 Service Pack 1](https://support.microsoft.com/kb/3058865).</span><span class="sxs-lookup"><span data-stu-id="30986-114">For more information on SQL Server 2014 (SP1), see [SQL Server 2014 Service Pack 1 release information](https://support.microsoft.com/kb/3058865).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30986-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="30986-115">In This Section</span></span>  
 <span data-ttu-id="30986-116">Que vous utilisiez l'Assistant Installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou l'invite de commandes pour installer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le processus d'installation implique les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="30986-116">Regardless of whether you use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or the command prompt to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Setup involves the following steps:</span></span>  
  
 [<span data-ttu-id="30986-117">Planification d'une installation SQL Server</span><span class="sxs-lookup"><span data-stu-id="30986-117">Planning a SQL Server Installation</span></span>](../../sql-server/install/planning-a-sql-server-installation.md)  
 <span data-ttu-id="30986-118">Décrit comment préparer l'ordinateur pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="30986-118">Describes how to prepare your computer for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="30986-119">Configuration matérielle et logicielle requise.</span><span class="sxs-lookup"><span data-stu-id="30986-119">Hardware and software requirements.</span></span>  
  
-   <span data-ttu-id="30986-120">Vérifier les spécifications de l'Outil d'analyse de configuration système et les problèmes bloquants.</span><span class="sxs-lookup"><span data-stu-id="30986-120">System Configuration Checker requirements and blocking issues.</span></span>  
  
-   <span data-ttu-id="30986-121">Considérations sur la sécurité.</span><span class="sxs-lookup"><span data-stu-id="30986-121">Security considerations.</span></span>  
  
 [<span data-ttu-id="30986-122">Installer SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="30986-122">Install SQL Server 2014</span></span>](install-sql-server.md)  
 <span data-ttu-id="30986-123">Décrit les options d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30986-123">Describes installation options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="30986-124">Mettre à niveau vers SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="30986-124">Upgrade to SQL Server 2014</span></span>](upgrade-sql-server.md)  
 <span data-ttu-id="30986-125">Décrit les options pour effectuer une mise à niveau vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30986-125">Describes options for upgrading to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="30986-126">Désinstaller SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="30986-126">Uninstall SQL Server 2014</span></span>](../../sql-server/install/uninstall-sql-server.md)  
 <span data-ttu-id="30986-127">Décrit les procédures pour désinstaller [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30986-127">Describes procedures to uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span></span>  
  
 [<span data-ttu-id="30986-128">Installation d'un cluster de basculement SQL Server</span><span class="sxs-lookup"><span data-stu-id="30986-128">SQL Server Failover Cluster Installation</span></span>](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md)  
 <span data-ttu-id="30986-129">Cette section de la documentation d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] décrit comment installer et configurer un cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30986-129">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install, and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
 [<span data-ttu-id="30986-130">Installer les fonctionnalités BI de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="30986-130">Install SQL Server 2014 BI Features</span></span>](../../sql-server/install/install-sql-server-business-intelligence-features.md)  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="30986-131">Les fonctions qui font partie de la plateforme BI de Microsoft sont notamment [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], ainsi que plusieurs applications clientes servant à créer ou utiliser des données analytiques.</span><span class="sxs-lookup"><span data-stu-id="30986-131">features that are part of the Microsoft BI platform include [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and several client applications used for creating or working with analytical data.</span></span> <span data-ttu-id="30986-132">Cette section de la documentation de l'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explique comment installer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30986-132">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="30986-133">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="30986-133">Related Sections</span></span>  
 [<span data-ttu-id="30986-134">Rubriques de procédures relatives à l'installation</span><span class="sxs-lookup"><span data-stu-id="30986-134">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
 <span data-ttu-id="30986-135">Fournit des liens vers des rubriques de procédure pour installer [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à partir de l'Assistant Installation, à partir de l'invite de commandes, à l'aide des fichiers de configuration, puis à l'aide de SysPrep.</span><span class="sxs-lookup"><span data-stu-id="30986-135">Provides links to procedural topics for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from the installation wizard, from the command prompt, by using configuration files, and by using SysPrep.</span></span>  
  
 [<span data-ttu-id="30986-136">Installer SQL Server fonctionnalités BI avec SharePoint &#40;PowerPivot et Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="30986-136">Install SQL Server BI Features with SharePoint &#40;PowerPivot and Reporting Services&#41;</span></span>](../../sql-server/install/install-sql-server-bi-features-sharepoint-powerpivot-reporting-services.md)  
 <span data-ttu-id="30986-137">Cette section explique comment installer les fonctionnalités de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans un environnement SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30986-137">This section explains how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features in a SharePoint environment.</span></span> <span data-ttu-id="30986-138">Elle identifie les fonctionnalités [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibles en fonction d'une version et d'une édition spécifiques de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30986-138">It identifies which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features are available given a specific version and edition of SharePoint.</span></span> <span data-ttu-id="30986-139">Elle inclut également des procédures d'installation de PowerPivot pour SharePoint et Reporting Services en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30986-139">It also includes installation procedures for PowerPivot for SharePoint and Reporting Services in SharePoint mode.</span></span>  
  
 [<span data-ttu-id="30986-140">Installation d'exemples et d'exemples de bases de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="30986-140">Installing SQL Server Samples and Sample Databases</span></span>](https://sqlserversamples.codeplex.com/)  
 <span data-ttu-id="30986-141">Explique comment installer et configurer les exemples et les exemples de bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30986-141">Describes how to install and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples and sample databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30986-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="30986-142">See Also</span></span>  
 <span data-ttu-id="30986-143">[Nouveautés de l’installation de SQL Server](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="30986-143">[What's New in SQL Server Installation](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="30986-144">Configuration matérielle et logicielle requise pour l’installation de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="30986-144">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
