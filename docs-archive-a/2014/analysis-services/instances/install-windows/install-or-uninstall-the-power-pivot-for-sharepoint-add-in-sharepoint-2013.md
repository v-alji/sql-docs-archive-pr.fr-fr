---
title: Installer ou désinstaller le complément PowerPivot pour SharePoint (SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: fe13ce8b-9369-4126-928a-9426f9119424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7df54d11021163167149e5b0c1edd960fee1a2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697280"
---
# <a name="install-or-uninstall-the-powerpivot-for-sharepoint-add-in-sharepoint-2013"></a><span data-ttu-id="e1a61-102">Installer ou désinstaller le complément PowerPivot pour SharePoint (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="e1a61-102">Install or Uninstall the PowerPivot for SharePoint Add-in (SharePoint 2013)</span></span>
  [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] <span data-ttu-id="e1a61-103">est un ensemble de composants de serveur d’applications et de services principaux qui fournissent l’accès aux données [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] dans une batterie de serveurs [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1a61-103">is a collection of application server components and back-end services that provide [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] data access in a [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] farm.</span></span> <span data-ttu-id="e1a61-104">Le complément [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] pour SharePoint (**spPowerpivot.msi**) est un package d’installation utilisé pour installer les composants de serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="e1a61-104">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint add-in (**spPowerpivot.msi**) is an installer package used to install the application server components.</span></span>

-   <span data-ttu-id="e1a61-105">Ce complément n'est pas requis pour les déploiements SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="e1a61-105">The add-in is not required for SharePoint 2010 deployments.</span></span>

-   <span data-ttu-id="e1a61-106">Ce complément n'est pas requis dans un déploiement à un seul serveur qui inclut SharePoint 2013 et [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-106">The add-in is not required on a single server deployment that includes SharePoint 2013 and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="e1a61-107">Les composants installés par le complément sont inclus lorsque vous installez un serveur [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-107">The components installed by the add-in are included when you install an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] server in SharePoint mode.</span></span> <span data-ttu-id="e1a61-108">Pour consulter des exemples de schéma de déploiement avec le complément, consultez [Deployment Topologies for SQL Server BI Features in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="e1a61-108">For diagrams of example deployments with the add-in, see [Deployment Topologies for SQL Server BI Features in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span></span>

 <span data-ttu-id="e1a61-109">**Remarque :** cette rubrique décrit l'installation des fichiers solution [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] et de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] pour l'outil de Configuration de SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="e1a61-109">**Note:** This topic describes installing the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] solution files and [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span> <span data-ttu-id="e1a61-110">Après l’installation, consultez la rubrique suivante pour plus d’informations sur l’outil de configuration et les fonctionnalités supplémentaires, [configurer PowerPivot et déployer des Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="e1a61-110">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

 <span data-ttu-id="e1a61-111">Pour plus d'informations sur le téléchargement de **spPowerPivot.msi**, consultez [Microsoft® SQL Server® 2014 PowerPivot® pour Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span><span class="sxs-lookup"><span data-stu-id="e1a61-111">For information on how to download **spPowerPivot.msi**, see [Microsoft® SQL Server® 2014 PowerPivot® for Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span></span>

 <span data-ttu-id="e1a61-112">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="e1a61-112">**In this topic:**</span></span>

-   [<span data-ttu-id="e1a61-113">Arrière-plan</span><span class="sxs-lookup"><span data-stu-id="e1a61-113">Background</span></span>](#bkmk_background)

-   [<span data-ttu-id="e1a61-114">Où installer spPowerPivot.msi ?</span><span class="sxs-lookup"><span data-stu-id="e1a61-114">Where to Install spPowerPivot.msi?</span></span>](#bkmk_where_to_install)

-   [<span data-ttu-id="e1a61-115">Spécifications et conditions préalables requises</span><span class="sxs-lookup"><span data-stu-id="e1a61-115">Requirements and Prerequisites</span></span>](#bkmk_prereq)

-   [<span data-ttu-id="e1a61-116">Pour installer PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="e1a61-116">To Install PowerPivot for SharePoint</span></span>](#bkmk_install)

-   [<span data-ttu-id="e1a61-117">Déployer les fichiers solution SharePoint avec l'outil de configuration PowerPivot pour SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="e1a61-117">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>](#bkmk_deploy_solution)

-   [<span data-ttu-id="e1a61-118">Désinstaller ou réparer le complément</span><span class="sxs-lookup"><span data-stu-id="e1a61-118">Uninstall or repair the add-in</span></span>](#bkmk_remove_addin)

##  <a name="background"></a><a name="bkmk_background"></a> <span data-ttu-id="e1a61-119">Arrière-plan</span><span class="sxs-lookup"><span data-stu-id="e1a61-119">Background</span></span>

-   <span data-ttu-id="e1a61-120">**Serveur d’applications :** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] disponibles dans SharePoint 2013 incluent l’utilisation de classeurs comme source de données, l’actualisation planifiée des données et le tableau de bord de gestion [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1a61-120">**Application Server:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] functionality in SharePoint 2013 includes using workbooks as a data source, scheduled data refresh, and the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] Management Dashboard.</span></span>

     [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)]<span data-ttu-id="e1a61-121">est un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] package de Windows Installer (**spPowerpivot.msi**) qui déploie Analysis Services bibliothèques clientes et copie [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] les fichiers d’installation sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e1a61-121">is a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Installer package (**spPowerpivot.msi**) that deploys Analysis Services client libraries and copies [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] installation files to the computer.</span></span> <span data-ttu-id="e1a61-122">Le programme d'installation ne déploie pas ou ne configure pas de fonctionnalités [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-122">The installer does not deploy or configure [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] features in SharePoint.</span></span> <span data-ttu-id="e1a61-123">Les composants suivants s'installent par défaut :</span><span class="sxs-lookup"><span data-stu-id="e1a61-123">The following components install by default:</span></span>

    -   [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] <span data-ttu-id="e1a61-124">2013. Ce composant inclut des scripts PowerShell (fichiers .ps1), des packages de solution SharePoint (.wsp) et l'outil de configuration [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 pour déployer [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] dans une batterie de serveurs SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="e1a61-124">2013. This component includes PowerShell scripts (.ps1 files), SharePoint solution packages (.wsp), and the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 configuration tool to deploy [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in a SharePoint 2013 farm.</span></span>

    -   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="e1a61-125">Fournisseur OLE DB pour Analysis Services (MSOLAP).</span><span class="sxs-lookup"><span data-stu-id="e1a61-125">OLE DB Provider for Analysis Services (MSOLAP).</span></span>

    -   <span data-ttu-id="e1a61-126">Fournisseur de données ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="e1a61-126">ADOMD.NET data provider.</span></span>

    -   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="e1a61-127">.</span><span class="sxs-lookup"><span data-stu-id="e1a61-127">Analysis Management Objects.</span></span>

-   <span data-ttu-id="e1a61-128">**Services principaux :** si vous utilisez [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] pour Excel pour créer des classeurs qui contiennent des données analytiques, Excel Services doit être configuré avec un serveur BI exécutant [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en mode SharePoint pour accéder à ces données dans un environnement serveur.</span><span class="sxs-lookup"><span data-stu-id="e1a61-128">**Backend services:** If you use [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for Excel to create workbooks that contain analytical data, you must have Excel Services configured with a BI server running [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode to access that data in a server environment.</span></span> <span data-ttu-id="e1a61-129">Vous pouvez exécuter le programme d'installation de SQL Server sur un ordinateur qui possède un serveur SharePoint 2013 installé, ou sur un autre ordinateur sans logiciel SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-129">You can run SQL Server Setup on a computer that has SharePoint Server 2013 installed, or on a different computer that has no SharePoint software.</span></span> <span data-ttu-id="e1a61-130">Analysis Services n'a pas de dépendances de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-130">Analysis Services does not have any dependencies on SharePoint.</span></span>

     <span data-ttu-id="e1a61-131">Pour plus d'informations sur l'installation, la désinstallation et la configuration des services principaux, consultez :</span><span class="sxs-lookup"><span data-stu-id="e1a61-131">For more information on installing, uninstalling, and configuring the backend services, see the following:</span></span>

    -   [<span data-ttu-id="e1a61-132">PowerPivot for SharePoint 2013 Installation</span><span class="sxs-lookup"><span data-stu-id="e1a61-132">PowerPivot for SharePoint 2013 Installation</span></span>](https://docs.microsoft.com/analysis-services/instances/install-windows/install-analysis-services-in-power-pivot-mode)

    -   [<span data-ttu-id="e1a61-133">Désinstaller PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="e1a61-133">Uninstall PowerPivot for SharePoint</span></span>](../../../sql-server/install/uninstall-power-pivot-for-sharepoint.md)

##  <a name="where-to-install-sppowerpivotmsi"></a><a name="bkmk_where_to_install"></a><span data-ttu-id="e1a61-134">Où installer spPowerPivot.msi ?</span><span class="sxs-lookup"><span data-stu-id="e1a61-134">Where to Install spPowerPivot.msi?</span></span>
 <span data-ttu-id="e1a61-135">La meilleure pratique recommandée consiste à installer **spPowerPivot.msi** sur tous les serveurs de la batterie de serveurs SharePoint pour la cohérence de configuration, y compris les serveurs d’applications et les serveurs Web frontaux.</span><span class="sxs-lookup"><span data-stu-id="e1a61-135">A recommended best practice is to install **spPowerPivot.msi** on all servers in the SharePoint farm for configuration consistency, including application servers and web-front end servers.</span></span> <span data-ttu-id="e1a61-136">Le package d'installation inclut les fournisseurs de données Analysis Services, ainsi que l'outil de configuration de [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1a61-136">The installer package includes the Analysis Services data providers as well as the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] configuration tool.</span></span> <span data-ttu-id="e1a61-137">Lorsque vous installez **spPowerPivot.msi** , vous pouvez personnaliser l'installation en excluant des composants.</span><span class="sxs-lookup"><span data-stu-id="e1a61-137">When you install **spPowerPivot.msi** you can customize the installation by excluding individual components.</span></span>

 <span data-ttu-id="e1a61-138">**Fournisseurs de données :** plusieurs technologies SharePoint et SQL Server utilisent des fournisseurs de données Analysis Services, y compris Excel Services, PerformancePoint Services et Power View.</span><span class="sxs-lookup"><span data-stu-id="e1a61-138">**Data providers:** Several SharePoint and SQL Server technologies use the Analysis Services data providers including Excel Services, PerformancePoint Services, and Power View.</span></span> <span data-ttu-id="e1a61-139">L'installation de **spPowerPivot.msi** sur tous les serveurs SharePoint garantit que l'ensemble complet des fournisseurs de données Analysis Services et la connectivité PowerPivot sont constamment disponibles dans la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="e1a61-139">Installing **spPowerPivot.msi** on all SharePoint servers ensures the full set of Analysis Services data providers and PowerPivot connectivity is consistently available across the farm.</span></span>

> [!NOTE]
>  <span data-ttu-id="e1a61-140">Vous devez installer les fournisseurs de données Analysis Services sur un serveur SharePoint 2013 à l'aide de **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-140">You must install the Analysis Services data providers on a SharePoint 2013 server using **spPowerPivot.msi**.</span></span> <span data-ttu-id="e1a61-141">D'autres packages d'installation disponibles dans le Feature Pack [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] ne sont pas pris en charge, car ils n'incluent pas les fichiers de prise en charge de SharePoint 2013 dont les fournisseurs de données ont besoin dans cet environnement.</span><span class="sxs-lookup"><span data-stu-id="e1a61-141">Other installer packages available in the [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] Feature Pack are not supported because these packages do not include the SharePoint 2013 support files that the data providers require in this environment.</span></span>

 <span data-ttu-id="e1a61-142">**Outil de configuration :** l'outil de configuration PowerPivot pour SharePoint 2013 est requis sur un seul des serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-142">**Configuration Tool:** The PowerPivot for SharePoint 2013 configuration tool is required on only one of the SharePoint servers.</span></span> <span data-ttu-id="e1a61-143">Toutefois, la meilleure pratique recommandée dans les batteries de plusieurs serveurs consiste à installer l'outil de configuration sur au moins deux serveurs de façon à ce que vous ayez accès à l'outil de configuration si un des deux serveurs est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="e1a61-143">However a recommended best practice in multi-server farms is to install the configuration tool on at least two servers so you have access to the configuration tool if one of the two servers is offline.</span></span>

##  <a name="requirements-and-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="e1a61-144">Configuration requise et conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e1a61-144">Requirements and Prerequisites</span></span>

-   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="e1a61-145">SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1a61-145">SharePoint Server 2013.</span></span>

-   <span data-ttu-id="e1a61-146">**spPowerPivot.msi** n’est disponible que sur les systèmes d’exploitation 64 bits, conformément aux spécifications des produits et technologies SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-146">**spPowerPivot.msi** is 64-bit only, in accordance with the requirements of SharePoint products and technologies.</span></span>

-   <span data-ttu-id="e1a61-147">Serveur [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] en mode PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e1a61-147">A [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] server in PowerPivot mode.</span></span> <span data-ttu-id="e1a61-148">Excel Services utilisera l'instance SQL Server Analysis Services en tant que serveur PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e1a61-148">Excel Services will use the SQL Server Analysis Services instance as a PowerPivot server.</span></span> <span data-ttu-id="e1a61-149">Analysis Services peut s'exécuter sur un ordinateur local ou distant.</span><span class="sxs-lookup"><span data-stu-id="e1a61-149">Analysis Services can run on the local or a remote computer.</span></span>

-   <span data-ttu-id="e1a61-150">**Autorisations :** pour installer [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], l'utilisateur actuel doit être administrateur sur l'ordinateur et membre du groupe Administrateur de batterie de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-150">**Permissions:** To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], the current user is required to be an administrator on the computer and a SharePoint Farm Administrators group.</span></span>

-   <span data-ttu-id="e1a61-151">Pour plus d’informations sur la configuration requise et les conditions préalables requises [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] , consultez [configurations matérielle et logicielle requises pour Analysis Services Server en Mode SharePoint &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e1a61-151">For more information on [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] requirements and pre-requisites, go to [Hardware and Software Requirements for Analysis Services Server in SharePoint Mode &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span></span>

##  <a name="to-install-powerpivot-for-sharepoint"></a><a name="bkmk_install"></a><span data-ttu-id="e1a61-152">Pour installer PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="e1a61-152">To Install PowerPivot for SharePoint</span></span>
 <span data-ttu-id="e1a61-153">Le package d’installation **spPowerpivot.msi** prend en charge à la fois une interface utilisateur graphique et une installation en mode ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e1a61-153">The **spPowerpivot.msi** installer package supports both a graphical user interface and a command-line mode.</span></span> <span data-ttu-id="e1a61-154">Les deux méthodes d'installation requièrent que vous exécutiez le fichier .msi avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="e1a61-154">Both methods of installation require that you run the .msi with administrator privileges.</span></span> <span data-ttu-id="e1a61-155">Après l’installation, consultez la rubrique suivante pour plus d’informations sur l’outil de configuration et les fonctionnalités supplémentaires, [configurer PowerPivot et déployer des Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="e1a61-155">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

### <a name="user-interface-installation"></a><span data-ttu-id="e1a61-156">Installation de l'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e1a61-156">User interface installation</span></span>
 <span data-ttu-id="e1a61-157">Pour installer [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] avec l'interface utilisateur graphique, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e1a61-157">To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] with the graphical user interface, complete the following steps:</span></span>

1.  <span data-ttu-id="e1a61-158">Exécutez **SpPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-158">Run **SpPowerPivot.msi**.</span></span>

2.  <span data-ttu-id="e1a61-159">Dans la page Bienvenue, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-159">Click **Next** on the Welcome page.</span></span>

3.  <span data-ttu-id="e1a61-160">Lisez et acceptez le contrat de licence, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-160">Review and accept the license agreement, then click **Next**.</span></span>

4.  <span data-ttu-id="e1a61-161">Dans la page **Sélection de fonctionnalités** , toutes les fonctionnalités sont sélectionnées par défaut.</span><span class="sxs-lookup"><span data-stu-id="e1a61-161">On the **Feature Selection** page, all of the features are selected by default.</span></span>

5.  <span data-ttu-id="e1a61-162">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-162">Click **Next**.</span></span>

6.  <span data-ttu-id="e1a61-163">Cliquez sur **Installer** pour terminer l'installation.</span><span class="sxs-lookup"><span data-stu-id="e1a61-163">Click **Install** to install to finish the installation.</span></span>

### <a name="command-line-installation"></a><span data-ttu-id="e1a61-164">Installation à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="e1a61-164">Command Line Installation</span></span>
 <span data-ttu-id="e1a61-165">Pour une installation à partir de la ligne de commande, ouvrez une invite de commandes avec des autorisations administratives, puis exécutez **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-165">For a command-line installation, open a command prompt with administrative permissions, and then run the **spPowerPivot.msi**.</span></span> <span data-ttu-id="e1a61-166">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e1a61-166">For example:</span></span>

 <span data-ttu-id="e1a61-167">`Msiexec.exe /i SpPowerPivot.msi`.</span><span class="sxs-lookup"><span data-stu-id="e1a61-167">`Msiexec.exe /i SpPowerPivot.msi`.</span></span>

 <span data-ttu-id="e1a61-168">Pour créer un journal d'installation, utilisez les commutateurs d'enregistrement MsiExec standards.</span><span class="sxs-lookup"><span data-stu-id="e1a61-168">To create an installation log, use the standard MsiExec logging switches.</span></span> <span data-ttu-id="e1a61-169">L’exemple suivant crée le fichier journal « Install_Log.txt » à l’aide du commutateur de journalisation verbose « v ».</span><span class="sxs-lookup"><span data-stu-id="e1a61-169">The following example creates the log file "Install_Log.txt" using the "v" verbose logging switch.</span></span>

```cmd
Msiexec.exe /i SpPowerPivot.msi /L v c:\test\Install_Log.txt
```

### <a name="quiet-command-line-installation-for-scripting"></a><span data-ttu-id="e1a61-170">Installation silencieuse de script à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="e1a61-170">Quiet Command Line Installation for scripting</span></span>
 <span data-ttu-id="e1a61-171">Vous pouvez utiliser les commutateurs **/q** ou **/Quiet** pour une installation « silencieuse » qui n’affiche pas de boîtes de dialogue ou d’avertissements.</span><span class="sxs-lookup"><span data-stu-id="e1a61-171">You can use the **/q** or **/quiet** switches for a "quiet" installation that will not display any dialogs or warnings.</span></span> <span data-ttu-id="e1a61-172">L'installation silencieuse est utile si vous souhaitez écrire un script d'installation du complément.</span><span class="sxs-lookup"><span data-stu-id="e1a61-172">The quiet installation is useful if you want to script the installation of the add-in.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="e1a61-173">Si vous utilisez le commutateur **/q** pour une installation silencieuse à partir de la ligne de commande, le Contrat de Licence Utilisateur Final ne sera pas affiché.</span><span class="sxs-lookup"><span data-stu-id="e1a61-173">If you use the **/q** switch for a silent command line installation, the end-user license agreement will not be displayed.</span></span> <span data-ttu-id="e1a61-174">Quelle que soit la méthode d'installation, l'utilisation de ce logiciel est régie par un contrat de licence et vous devez respecter les termes contractuels de ce contrat.</span><span class="sxs-lookup"><span data-stu-id="e1a61-174">Regardless of the installation method, the use of this software is governed by a license agreement and you are responsible for complying with the license agreement.</span></span>

#### <a name="to-perform-a-quiet-installation"></a><span data-ttu-id="e1a61-175">Pour effectuer une installation silencieuse</span><span class="sxs-lookup"><span data-stu-id="e1a61-175">To perform a quiet installation</span></span>

1.  <span data-ttu-id="e1a61-176">Ouvrez une invite **de commandes avec des autorisations d’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-176">Open a command prompt **with administrator permissions**.</span></span>

2.  <span data-ttu-id="e1a61-177">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e1a61-177">Run the following command:</span></span>

    ```cmd
    Msiexec.exe /i spPowerPivot.msi /q
    ```

### <a name="command-line-installation-to-include-specific-components"></a><span data-ttu-id="e1a61-178">Installation à partir de la ligne de commande pour inclure des composants spécifiques</span><span class="sxs-lookup"><span data-stu-id="e1a61-178">Command Line Installation to include specific components</span></span>
 <span data-ttu-id="e1a61-179">L'outil de configuration [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] n'est pas requis sur chaque serveur SharePoint, mais il est néanmoins recommandé de l'installer sur au moins deux serveurs de façon à ce qu'il soit disponible lorsque vous en avez besoin.</span><span class="sxs-lookup"><span data-stu-id="e1a61-179">The [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool is not required on every SharePoint server, however it is recommended to install it on at least two servers so the configuration tool is available when you need it.</span></span>

 <span data-ttu-id="e1a61-180">Lorsque vous installez le fichier spPowerPivot.msi, vous pouvez utiliser les options de ligne de commande pour installer des éléments spécifiques, comme les fournisseurs de données, et non l'outil de configuration [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1a61-180">When you install the spPowerPivot.msi, you can use the command line options to install specific items, such as the data providers and not the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool.</span></span> <span data-ttu-id="e1a61-181">La ligne de commande suivante est un exemple d'installation de tous les composants, à l'exception de l'outil de configuration :</span><span class="sxs-lookup"><span data-stu-id="e1a61-181">The following command line is an example of installing all components except the configuration tool:</span></span>

```
Msiexec /i spPowerPivot.msi AGREETOLICENSE="yes" ADDLOCAL=" SQL_OLAPDM,SQL_ADOMD,SQL_AMO,SQLAS_SP_Common"
```

|<span data-ttu-id="e1a61-182">Option</span><span class="sxs-lookup"><span data-stu-id="e1a61-182">Option</span></span>|<span data-ttu-id="e1a61-183">Description</span><span class="sxs-lookup"><span data-stu-id="e1a61-183">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="e1a61-184">Analysis_Server_SP_addin</span><span class="sxs-lookup"><span data-stu-id="e1a61-184">Analysis_Server_SP_addin</span></span>|<span data-ttu-id="e1a61-185">Configuration PowerPivot</span><span class="sxs-lookup"><span data-stu-id="e1a61-185">PowerPivot Configuration</span></span>|
|<span data-ttu-id="e1a61-186">SQL_OLAPDM</span><span class="sxs-lookup"><span data-stu-id="e1a61-186">SQL_OLAPDM</span></span>|<span data-ttu-id="e1a61-187">MSOLAP</span><span class="sxs-lookup"><span data-stu-id="e1a61-187">MSOLAP</span></span>|
|<span data-ttu-id="e1a61-188">SQL_ADOMD</span><span class="sxs-lookup"><span data-stu-id="e1a61-188">SQL_ADOMD</span></span>|<span data-ttu-id="e1a61-189">fournisseur ADOMD.net</span><span class="sxs-lookup"><span data-stu-id="e1a61-189">ADOMD.net provider</span></span>|
|<span data-ttu-id="e1a61-190">SQL_AMO</span><span class="sxs-lookup"><span data-stu-id="e1a61-190">SQL_AMO</span></span>|<span data-ttu-id="e1a61-191">Fournisseur AMO</span><span class="sxs-lookup"><span data-stu-id="e1a61-191">AMO provider</span></span>|
|<span data-ttu-id="e1a61-192">SQLAS_SP_Common</span><span class="sxs-lookup"><span data-stu-id="e1a61-192">SQLAS_SP_Common</span></span>|<span data-ttu-id="e1a61-193">Composants communs Analysis Services pour SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="e1a61-193">Analysis Services common components for SharePoint 2013</span></span>|

##  <a name="deploy-the-sharepoint-solution-files-with-the-powerpivot-for-sharepoint-2013-configuration-tool"></a><a name="bkmk_deploy_solution"></a><span data-ttu-id="e1a61-194">Déployer les fichiers solution SharePoint avec l’outil de configuration PowerPivot pour SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="e1a61-194">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>
 <span data-ttu-id="e1a61-195">Trois des fichiers copiés sur le disque dur par spPowerPivot.msi sont des fichiers solution de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-195">Three of the files copied to the hard drive by spPowerPivot.msi are SharePoint solution files.</span></span> <span data-ttu-id="e1a61-196">L'étendue d'un fichier solution correspond au niveau de l'application Web, alors que l'étendue des autres fichiers correspond au niveau de la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="e1a61-196">The scope of one solution file is the Web application level while the scope of the other files is the farm level.</span></span> <span data-ttu-id="e1a61-197">Les fichiers sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="e1a61-197">The files are the following:</span></span>

-   `PowerPivotFarmSolution.wsp`

-   `PowerPivotFarm14Solution.wsp`

-   `PowerPivotWebApplicationSolution.wsp`

 <span data-ttu-id="e1a61-198">Les fichiers solution sont copiés dans le dossier suivant :</span><span class="sxs-lookup"><span data-stu-id="e1a61-198">The solution files are copied to the following folder:</span></span>

 `C:\Program Files\Microsoft SQL Server\120\Tools\PowerPivotTools\SPAddinConfiguration\Resources`

 <span data-ttu-id="e1a61-199">Après l'installation du fichier .msi, exécutez l'outil de configuration [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] pour configurer et déployer des solutions dans la batterie de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a61-199">Following the .msi installation, run the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration Tool to configure and deploy the solutions in the SharePoint farm.</span></span>

### <a name="to-start-the-configuration-tool"></a><span data-ttu-id="e1a61-200">Pour démarrer l’outil de configuration de</span><span class="sxs-lookup"><span data-stu-id="e1a61-200">To start the configuration tool</span></span> 

 <span data-ttu-id="e1a61-201">Dans l’écran de démarrage de Windows, tapez « Power », puis dans les résultats de la recherche d’applications, cliquez sur **PowerPivot pour SharePoint Configuration 2013**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-201">From the Windows Start screen type "power" and in the Apps search results, click **PowerPivot for SharePoint 2013 Configuration**.</span></span> <span data-ttu-id="e1a61-202">Notez que les résultats de la recherche peuvent inclure deux liens car le programme d'installation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installe des outils de configuration de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] distincts pour SharePoint 2010 et SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="e1a61-202">Note that the search results may include two links because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] setup installs separate [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] configuration tools for SharePoint 2010 and SharePoint 2013.</span></span> <span data-ttu-id="e1a61-203">Lancez l'outil Configuration de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] pour SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="e1a61-203">Make sure you start the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span>

 <span data-ttu-id="e1a61-204">![deux outils de configuration PowerPivot](../../media/as-powerpivot-configtools-bothicons.gif "deux outils de configuration PowerPivot")</span><span class="sxs-lookup"><span data-stu-id="e1a61-204">![two powerpivot configuration tools](../../media/as-powerpivot-configtools-bothicons.gif "two powerpivot configuration tools")</span></span>

 <span data-ttu-id="e1a61-205">**Ou**</span><span class="sxs-lookup"><span data-stu-id="e1a61-205">**Or**</span></span>

1.  <span data-ttu-id="e1a61-206">Accédez à **Démarrer**, **Tous les programmes**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-206">Go to **Start**, **All Programs**.</span></span>

2.  <span data-ttu-id="e1a61-207">Cliquez sur **Microsoft SQL Server 2014**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-207">Click **Microsoft SQL Server 2014**.</span></span>

3.  <span data-ttu-id="e1a61-208">Cliquez sur **Outils de configuration**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-208">Click **Configuration Tools**.</span></span>

4.  <span data-ttu-id="e1a61-209">Cliquez sur **Configuration (PowerPivot pour SharePoint 2013)**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-209">Click **PowerPivot for SharePoint 2013 Configuration**.</span></span>

 <span data-ttu-id="e1a61-210">Pour plus d'informations sur l'outil de configuration, consultez [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e1a61-210">For more information on the configuration tool, see [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span></span>

##  <a name="uninstall-or-repair-the-add-in"></a><a name="bkmk_remove_addin"></a><span data-ttu-id="e1a61-211">Désinstaller ou réparer le complément</span><span class="sxs-lookup"><span data-stu-id="e1a61-211">Uninstall or repair the add-in</span></span>

> [!CAUTION]
>  <span data-ttu-id="e1a61-212">Si vous désinstallez **spPowerPivot.msi** , les fournisseurs de données et l'outil de configuration sont désinstallés.</span><span class="sxs-lookup"><span data-stu-id="e1a61-212">If you uninstall **spPowerPivot.msi** the data providers and the configuration tool are uninstalled.</span></span> <span data-ttu-id="e1a61-213">Désinstaller les fournisseurs de données empêchera le serveur de se connecter à PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e1a61-213">Uninstalling the data providers will cause the server to be unable to connect to PowerPivot.</span></span>

 <span data-ttu-id="e1a61-214">Pour désinstaller ou réparer [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] , procédez selon l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e1a61-214">You can uninstall or repair [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] using one of the following methods:</span></span>

1.  <span data-ttu-id="e1a61-215">**Panneau de configuration Windows :** Sélectionnez **Microsoft SQL Server 2012 PowerPivot pour SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-215">**Windows control panel:** Select **Microsoft SQL Server 2012 PowerPivot for SharePoint 2013**.</span></span> <span data-ttu-id="e1a61-216">Cliquez sur **Désinstaller** ou **Réparer**.</span><span class="sxs-lookup"><span data-stu-id="e1a61-216">Click either **Uninstall** or **Repair**.</span></span>

2.  <span data-ttu-id="e1a61-217">Exécutez le fichier spPowerPivot.msi et sélectionnez l'option **Supprimer** ou **Réparer** .</span><span class="sxs-lookup"><span data-stu-id="e1a61-217">Run the spPowerPivot.msi and select the **Remove** option or the **Repair** option.</span></span>

 <span data-ttu-id="e1a61-218">**Ligne de commande :** pour réparer ou désinstaller PowerPivot pour SharePoint 2013 à l'aide de la ligne de commande, ouvrez une invite de commandes **avec des autorisations d'administrateur** et exécutez l'une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e1a61-218">**Command Line:** To repair or uninstall PowerPivot for SharePoint 2013 using the command line, open a command prompt **with administrator permissions** and run one of the following commands:</span></span>

-   <span data-ttu-id="e1a61-219">Pour réparer, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e1a61-219">To Repair, run the following command:</span></span>

    ```cmd
    msiexec.exe /f spPowerPivot.msi
    ```

 <span data-ttu-id="e1a61-220">OU</span><span class="sxs-lookup"><span data-stu-id="e1a61-220">OR</span></span>

-   <span data-ttu-id="e1a61-221">Pour désinstaller, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e1a61-221">To uninstall, run the following command:</span></span>

    ```cmd
    msiexec.exe /uninstall spPowerPivot.msi
    ```
