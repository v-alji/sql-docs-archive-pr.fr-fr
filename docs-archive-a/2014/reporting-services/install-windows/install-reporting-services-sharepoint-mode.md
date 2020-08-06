---
title: Reporting Services l’installation en mode SharePoint (SharePoint 2010 et SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- default configuration [Reporting Services]
- installing Reporting Services, SharePoint integrated mode
- installation options [Reporting Services]
ms.assetid: ac6cba68-2665-4a39-8fa3-cb7d7e6723c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c27b6f9fbeebcc896b1a6097cb51e8d2e15924bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601285"
---
# <a name="reporting-services-sharepoint-mode-installation-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="48be3-102">Installation du mode SharePoint de Reporting Services (SharePoint 2010 et SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="48be3-102">Reporting Services SharePoint Mode Installation (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="48be3-103">en mode SharePoint est un ensemble de composants serveur qui assurent la génération et la remise de rapports, basés sur [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] les [!INCLUDE[msCoName](../../includes/msconame-md.md)] produits et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48be3-103">in SharePoint mode is a collection of server components that provide report generation and delivery, based on [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] SharePoint products.</span></span>  
  
 <span data-ttu-id="48be3-104">L'exécution de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode SharePoint fournit [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] et les fonctionnalités d'alerte de données.</span><span class="sxs-lookup"><span data-stu-id="48be3-104">Running [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode provides the [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] and data alerting features.</span></span> <span data-ttu-id="48be3-105">Pour plus d’informations sur les fonctionnalités en mode SharePoint, consultez la section « prise en charge des fonctionnalités et différences de comportement par le mode serveur » dans [Reporting Services Report Server](../reporting-services-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="48be3-105">For more information regarding features in SharePoint mode, see the section "Feature Support and Behavior Differences by Server Mode" in [Reporting Services Report Server](../reporting-services-report-server.md)</span></span>  
  
 <span data-ttu-id="48be3-106">Il existe deux installations fondamentales nécessaires pour [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode SharePoint :</span><span class="sxs-lookup"><span data-stu-id="48be3-106">There are two fundamental installations needed for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode:</span></span>  
  
|<span data-ttu-id="48be3-107">Installation</span><span class="sxs-lookup"><span data-stu-id="48be3-107">Installation</span></span>|<span data-ttu-id="48be3-108">Description</span><span class="sxs-lookup"><span data-stu-id="48be3-108">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="48be3-109">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Complément pour les produits SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48be3-109">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>|<span data-ttu-id="48be3-110">Le complément installe les pages et les fonctionnalités de l'interface utilisateur de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sur un serveur Web frontal SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48be3-110">The add-in installs the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] user interface (UI) pages and features on a SharePoint web front-end server.</span></span> <span data-ttu-id="48be3-111">Les fonctionnalités d'interface utilisateur incluent [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], les pages d'administration dans l'Administration centrale de SharePoint, les pages de fonctionnalités utilisées dans les bibliothèques de documents SharePoint et pages d'alerte de données [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48be3-111">The UI features include [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], administration pages in SharePoint Central Administration, feature pages used within SharePoint document libraries, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Data Alerting pages.</span></span>|  
|<span data-ttu-id="48be3-112">Le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] serveur de rapports installé en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="48be3-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server installed in SharePoint Mode</span></span>|<span data-ttu-id="48be3-113">Le serveur de rapports gère les données et le traitement et le rendu des rapports, ainsi que le traitement des abonnement et des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="48be3-113">The report server handles the data and report processing and rendering as well subscription and Data Alert processing.</span></span> <span data-ttu-id="48be3-114">Le serveur de rapports en mode SharePoint est conçu et installé en tant que service partagé SharePoint.</span><span class="sxs-lookup"><span data-stu-id="48be3-114">The SharePoint mode report server is architected and installed as a SharePoint Shared Service.</span></span>|  
  
 <span data-ttu-id="48be3-115">Pour installer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], utilisez le support d'installation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48be3-115">To install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], use the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media.</span></span>  
  
 <span data-ttu-id="48be3-116">Pour obtenir des instructions sur les scénarios de déploiement avancé, consultez [liste de vérification du déploiement : Reporting Services, Power View et PowerPivot pour SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) et liste de vérification du [déploiement : installer Reporting Services dans une batterie de serveurs SharePoint existante](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span><span class="sxs-lookup"><span data-stu-id="48be3-116">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Install Reporting Services into an Existing SharePoint Farm](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48be3-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="48be3-117">In This Section</span></span>  
 [<span data-ttu-id="48be3-118">Combinaisons prises en charge de SharePoint et Reporting Services Server et des compléments &#40;SQL Server 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="48be3-118">Supported Combinations of SharePoint and Reporting Services Server and Add-in &#40;SQL Server 2014&#41;</span></span>](supported-combinations-of-sharepoint-and-reporting-services-server.md)  
  
 [<span data-ttu-id="48be3-119">Installer le mode SharePoint de Reporting Services pour SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="48be3-119">Install Reporting Services SharePoint Mode for SharePoint 2013</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md)  
  
 [<span data-ttu-id="48be3-120">Installer Reporting Services mode SharePoint pour SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="48be3-120">Install Reporting Services SharePoint Mode for SharePoint 2010</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="48be3-121">Installer ou désinstaller le complément Reporting Services pour SharePoint &#40;SharePoint 2010 et SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="48be3-121">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
 [<span data-ttu-id="48be3-122">Où trouver le complément Reporting Services pour les produits SharePoint</span><span class="sxs-lookup"><span data-stu-id="48be3-122">Where to find the Reporting Services add-in for SharePoint Products</span></span>](where-to-find-the-reporting-services-add-in-for-sharepoint-products.md)  
  
 [<span data-ttu-id="48be3-123">Ajouter un serveur de rapports supplémentaire à une batterie &#40;montée en puissance SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="48be3-123">Add an Additional Report Server to a Farm &#40;SSRS Scale-out&#41;</span></span>](add-an-additional-report-server-to-a-farm-ssrs-scale-out.md)  
  
 [<span data-ttu-id="48be3-124">Ajouter un serveur Web frontal Reporting Services supplémentaire à une batterie</span><span class="sxs-lookup"><span data-stu-id="48be3-124">Add an Additional Reporting Services Web Front-end to a Farm</span></span>](add-an-additional-reporting-services-web-front-end-to-a-farm.md)  
  
 [<span data-ttu-id="48be3-125">Configurer la messagerie électronique pour une application de service Reporting Services &#40;SharePoint 2010 et SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="48be3-125">Configure E-mail for a Reporting Services Service Application &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](configure-e-mail-for-a-reporting-services-service-application.md)  
  
 [<span data-ttu-id="48be3-126">Configurer les abonnements et les alertes pour les applications de service de SSRS</span><span class="sxs-lookup"><span data-stu-id="48be3-126">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>](provision-subscriptions-and-alerts-for-ssrs-service-applications.md)  
  
 [<span data-ttu-id="48be3-127">Service d’jetons Revendications vers Windows &#40;C2WTS&#41; et Reporting Services</span><span class="sxs-lookup"><span data-stu-id="48be3-127">Claims to Windows Token Service &#40;C2WTS&#41; and Reporting Services</span></span>](../../sql-server/install/claims-to-windows-token-service-c2wts-and-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="48be3-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48be3-128">See Also</span></span>  
 <span data-ttu-id="48be3-129">[Architecture et flux de travail des alertes de données](../reporting-services-data-alerts.md#AlertingWF) </span><span class="sxs-lookup"><span data-stu-id="48be3-129">[Data Alerts Architecture and Workflow](../reporting-services-data-alerts.md#AlertingWF) </span></span>  
 [<span data-ttu-id="48be3-130">Gestionnaire des alertes de données pour les administrateurs d’alertes</span><span class="sxs-lookup"><span data-stu-id="48be3-130">Data Alert Manager for Alerting Administrators</span></span>](../data-alert-manager-for-alerting-administrators.md)  
  
  
