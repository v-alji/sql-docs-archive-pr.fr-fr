---
title: Configuration et administration d’un serveur de rapports (mode Reporting Services SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 846e86d0-fbbb-426c-97f9-f179cd42b390
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ce7c1f524eec4785ddbc25d95c641d070ecbf408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707283"
---
# <a name="configuration-and-administration-of-a-report-server-reporting-services-sharepoint-mode"></a><span data-ttu-id="18c3a-102">Configuration et administration d'un serveur de rapports (mode SharePoint de Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="18c3a-102">Configuration and Administration of a Report Server (Reporting Services SharePoint Mode)</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="18c3a-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] est une plateforme de création de rapports basée sur serveur qui fournit une gamme complète d’outils et de services prêts à l’emploi pour vous aider à créer, déployer et gérer des rapports pour votre organisation, ainsi que des fonctionnalités de programmation qui vous permettent d’étendre et de personnaliser vos fonctionnalités de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="18c3a-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] is a server-based reporting platform that provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization, as well as programming features that enable you to extend and customize your reporting functionality.</span></span> <span data-ttu-id="18c3a-104">Vous pouvez intégrer votre environnement de création de rapports à un produit SharePoint afin de tirer parti des avantages liés à l'utilisation de l'environnement de collaboration fourni par les sites SharePoint.</span><span class="sxs-lookup"><span data-stu-id="18c3a-104">You can integrate your reporting environment with a SharePoint product to experience the benefits of using the collaborative environment provided by SharePoint sites.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18c3a-105">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="18c3a-105">In this section</span></span>  
 <span data-ttu-id="18c3a-106">Utilisez les sections suivantes pour vous aider à comprendre entre autres les concepts, scénarios de déploiement et procédures pour l'intégration de votre environnement [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] à un produit ou une technologie SharePoint :</span><span class="sxs-lookup"><span data-stu-id="18c3a-106">Use the following sections to help you understand concepts, deployment scenarios, procedures, and more for integrating your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] environment with a SharePoint product or technology:</span></span>  
  
-   <span data-ttu-id="18c3a-107">Options de menu dans une bibliothèque SharePoint</span><span class="sxs-lookup"><span data-stu-id="18c3a-107">Menu options in a SharePoint document library</span></span>  
  
    -   [<span data-ttu-id="18c3a-108">Gestionnaire des alertes de données pour les utilisateurs SharePoint</span><span class="sxs-lookup"><span data-stu-id="18c3a-108">Data Alert Manager for SharePoint Users</span></span>](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md)  
  
    -   [<span data-ttu-id="18c3a-109">Créer et gérer des abonnements pour les serveurs de rapports en mode Sharepoint</span><span class="sxs-lookup"><span data-stu-id="18c3a-109">Create and Manage Subscriptions for SharePoint Mode Report Servers</span></span>](subscriptions/create-and-manage-subscriptions-for-sharepoint-mode-report-servers.md)  
  
    -   [<span data-ttu-id="18c3a-110">Mettre à jour les informations d'identification dans les sources de données de rapport à partir d'un site SharePoint</span><span class="sxs-lookup"><span data-stu-id="18c3a-110">Update Credentials in Report Data Sources from a SharePoint Site</span></span>](report-data/update-credentials-in-report-data-sources-from-a-sharepoint-site.md)  
  
    -   [<span data-ttu-id="18c3a-111">Gérer des datasets partagés</span><span class="sxs-lookup"><span data-stu-id="18c3a-111">Manage Shared Datasets</span></span>](report-data/manage-shared-datasets.md)  
  
    -   [<span data-ttu-id="18c3a-112">Définir les paramètres sur un rapport publié &#40;Reporting Services en mode intégré SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="18c3a-112">Set Parameters on a Published Report &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="18c3a-113">Définir les options de traitement &#40;Reporting Services en mode intégré SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="18c3a-113">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="18c3a-114">Options d’actualisation du cache &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="18c3a-114">Cache Refresh Options &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/cache-refresh-options-report-manager.md)  
  
-   [<span data-ttu-id="18c3a-115">Fonctionnalités de collection de sites de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="18c3a-115">Reporting Services Site Collection Features</span></span>](../../2014/reporting-services/reporting-services-site-collection-features.md)  
  
-   [<span data-ttu-id="18c3a-116">Activer les fonctionnalités d'intégration Report Server et Power View dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="18c3a-116">Activate the Report Server and Power View Integration Features in SharePoint</span></span>](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md)  
  
-   [<span data-ttu-id="18c3a-117">Paramètres et fonctions du site Reporting Services &#40;mode SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="18c3a-117">Reporting Services Site Settings and Site Features&#40;SharePoint Mode&#41;</span></span>](../../2014/reporting-services/reporting-services-site-settings-and-site-features-sharepoint-mode.md)  
  
-   [<span data-ttu-id="18c3a-118">Activer la fonctionnalité Synchronisation de fichiers de serveur de rapports dans l'Administration centrale de SharePoint</span><span class="sxs-lookup"><span data-stu-id="18c3a-118">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>](../../2014/reporting-services/activate-report-server-file-sync-feature-sharepoint-central-administration.md)  
  
-   [<span data-ttu-id="18c3a-119">Ajouter des types de contenu de serveur de rapports à une bibliothèque &#40;Reporting Services en mode intégré SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="18c3a-119">Add Report Server Content Types to a Library &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/add-reporting-services-content-types-to-a-sharepoint-library.md)  
  
-   [<span data-ttu-id="18c3a-120">Rapports en mode local et rapports en mode connecté dans la Visionneuse de rapports &#40;Reporting Services en mode SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="18c3a-120">Local Mode vs. Connected Mode Reports in the Report Viewer &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/local-vs-connected-mode-report-viewer-reporting-services-sharepoint-mode.md)  
  
-   [<span data-ttu-id="18c3a-121">Télécharger des documents vers une bibliothèque SharePoint &#40;Reporting Services en mode SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="18c3a-121">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
-   [<span data-ttu-id="18c3a-122">Définir les options de traitement &#40;Reporting Services en mode intégré SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="18c3a-122">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
 <span data-ttu-id="18c3a-123">Pour plus d’informations générales sur [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], consultez [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18c3a-123">For more general information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="18c3a-124">Pour plus d'informations sur les autres composants, outils et ressources de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , consultez la [Documentation en ligne de SQL Server](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="18c3a-124">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>  
  
  
