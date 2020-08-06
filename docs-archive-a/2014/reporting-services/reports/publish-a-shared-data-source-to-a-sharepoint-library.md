---
title: Publier une source de données partagée sur une bibliothèque SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], publishing to a SharePoint library
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 966ed425-3ce2-4e76-8237-3c1c977954ae
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77ee25535ccb98638ae02ca64e3bcbfc88291c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696403"
---
# <a name="publish-a-shared-data-source-to-a-sharepoint-library"></a><span data-ttu-id="8e3bd-102">publier une source de données partagée sur une bibliothèque SharePoint</span><span class="sxs-lookup"><span data-stu-id="8e3bd-102">Publish a Shared Data Source to a SharePoint Library</span></span>
  <span data-ttu-id="8e3bd-103">Pour publier une source de données partagée sur un serveur de rapports s'exécutant en mode intégré SharePoint, vous devez définir les propriétés du projet de rapport dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-103">To publish a shared data source to a report server that is running in SharePoint integrated mode, you must set the report project properties in Report Designer.</span></span> <span data-ttu-id="8e3bd-104">Dans les propriétés du projet, toutes les références aux serveurs, aux rapports et aux sources de données partagées doivent être des URL complètes.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span>  
  
 <span data-ttu-id="8e3bd-105">Vous devez disposer de l’autorisation **Membre** ou **Propriétaire** sur le site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-105">You must have **Member** or **Owner** permission on the SharePoint site.</span></span> <span data-ttu-id="8e3bd-106">Pour plus d’informations, consultez [Exemples d’URL pour les éléments de rapport publiés sur un serveur de rapports en mode SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="8e3bd-106">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-shared-data-source-to-a-sharepoint-site"></a><span data-ttu-id="8e3bd-107">Pour publier une source de données partagée sur un site SharePoint</span><span class="sxs-lookup"><span data-stu-id="8e3bd-107">To publish a shared data source to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="8e3bd-108">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez un projet Report Server nouveau ou existant.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open your existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="8e3bd-109">Dans le menu **Projet** , cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-109">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="8e3bd-110">La _\<project>_ boîte de dialogue **pages de propriétés** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-110">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="8e3bd-111">Choisissez la **Configuration** que vous utilisez pour publier sur un site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-111">Choose the **Configuration** you use to publish to a SharePoint site.</span></span>  
  
4.  <span data-ttu-id="8e3bd-112">Si vous voulez publier les sources de données partagées dans votre projet et remplacer celles précédemment publiées, attribuez à **OverwriteDataSources** la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-112">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="8e3bd-113">(Facultatif) Pour **TargetDataSourceFolder**, tapez l’URL d’une bibliothèque SharePoint ou d’un dossier de bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-113">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder.</span></span> <span data-ttu-id="8e3bd-114">Par exemple : *http://TestServer/TestSite/Documents/DataSources*.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-114">For example, *http://TestServer/TestSite/Documents/DataSources*.</span></span>  
  
     <span data-ttu-id="8e3bd-115">Si vous ne spécifiez pas de valeur, la valeur **TargetReportFolder** est utilisée.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-115">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="8e3bd-116">Pour **TargetReportFolder**, tapez l’URL d’une bibliothèque ou d’un dossier de bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-116">For **TargetReportFolder**, type a URL to a library or library folder.</span></span> <span data-ttu-id="8e3bd-117">Par exemple, http:*//ServeurTest/SiteTest/Documents/Rapports*.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-117">For example, http:*//TestServer/TestSite/Documents/Reports*.</span></span>  
  
7.  <span data-ttu-id="8e3bd-118">Pour **TargetServerURL**, tapez l’URL d’un sous-site ou d’un site SharePoint de niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="8e3bd-119">Si vous ne spécifiez aucun site, le site de premier niveau par défaut est utilisé.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-119">If you do not specify a site, the default top-level site is used.</span></span> <span data-ttu-id="8e3bd-120">Par exemple, http://*nomserveur*, http://*nomserveur*/*site*ou http://*nomserveur*/*site*/*sous-site*.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-120">For example, http://*servername*, http://*servername*/*site*, or http://*servername*/*site*/*subsite*.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="8e3bd-121">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur la source de données partagée à publier, puis cliquez sur **Déployer**.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-121">In Solution Explorer, right-click the shared data source you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="8e3bd-122">La source de données est publiée à l’emplacement spécifié dans **TargetDataSourceFolder**.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-122">The data source is published to the location specified in **TargetDataSourceFolder**.</span></span> <span data-ttu-id="8e3bd-123">Les erreurs de déploiement apparaissent dans la fenêtre Sortie.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-123">Deployment errors appear in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e3bd-124">Une fois que vous avez publié une source de données partagée sur un site SharePoint, l'extension de nom de fichier devient .rsds.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-124">After you publish a shared data source to a SharePoint site, the file name extension is changed to .rsds.</span></span> <span data-ttu-id="8e3bd-125">Vous pouvez modifier et gérer directement une source de données partagée sur le site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8e3bd-125">You can edit and manage a shared data source directly on the SharePoint site.</span></span> <span data-ttu-id="8e3bd-126">Pour plus d’informations, consultez [Créer et gérer des sources de données partagées &#40;Reporting Services en mode intégré SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="8e3bd-126">For more information, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3bd-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e3bd-127">See Also</span></span>  
 <span data-ttu-id="8e3bd-128">[Publier un rapport dans une bibliothèque SharePoint](publish-a-report-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="8e3bd-128">[Publish a Report to a SharePoint Library](publish-a-report-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="8e3bd-129">[Exemples d’URL pour les éléments de rapport publiés sur un serveur de rapports en mode SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="8e3bd-129">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="8e3bd-130">[Pages de propriétés du projet, boîte de dialogue](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="8e3bd-130">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="8e3bd-131">[Définir les propriétés de déploiement &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="8e3bd-131">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="8e3bd-132">[Publication de rapports sur un serveur de rapports](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="8e3bd-132">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 [<span data-ttu-id="8e3bd-133">Utiliser une connexion de données Office &#40;.odc&#41; avec les rapports &#40;Reporting Services en mode intégré SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="8e3bd-133">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
