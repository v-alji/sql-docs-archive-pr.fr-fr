---
title: Publier un rapport dans une bibliothèque SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- deploying [Reporting Services], reports in SharePoint integrated mode
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 3f6dfc28-50d8-4231-bd25-871b5f77cce6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23b74ffb04bf1e13523dcf6ec5d774089d80f73b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696407"
---
# <a name="publish-a-report-to-a-sharepoint-library"></a><span data-ttu-id="b47a5-102">publier un rapport dans une bibliothèque SharePoint</span><span class="sxs-lookup"><span data-stu-id="b47a5-102">Publish a Report to a SharePoint Library</span></span>
  <span data-ttu-id="b47a5-103">Pour publier un rapport sur un site SharePoint configuré pour l'intégration SharePoint, vous devez définir les propriétés du projet dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b47a5-103">To publish a report to a SharePoint site configured for SharePoint integration, you must set the project properties in Report Designer.</span></span> <span data-ttu-id="b47a5-104">Dans les propriétés du projet, toutes les références aux serveurs, aux rapports et aux sources de données partagées doivent être des URL complètes.</span><span class="sxs-lookup"><span data-stu-id="b47a5-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span> <span data-ttu-id="b47a5-105">Dans la définition de rapport, toutes les références aux sous-rapports, aux rapports d'extraction et aux ressources, telles que des images Web, doivent être des URL complètes.</span><span class="sxs-lookup"><span data-stu-id="b47a5-105">In the report definition, all references to subreports, drillthrough reports, and resources such as Web-based images, must be fully qualified URLS.</span></span>  
  
 <span data-ttu-id="b47a5-106">Vous devez avoir l’autorisation de **Membre** ou de **Propriétaire** sur le site SharePoint pour définir les propriétés du projet.</span><span class="sxs-lookup"><span data-stu-id="b47a5-106">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span> <span data-ttu-id="b47a5-107">Pour plus d’informations, consultez [Exemples d’URL pour les éléments de rapport publiés sur un serveur de rapports en mode SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b47a5-107">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-report-to-a-sharepoint-site"></a><span data-ttu-id="b47a5-108">Pour publier un rapport sur un site SharePoint</span><span class="sxs-lookup"><span data-stu-id="b47a5-108">To publish a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="b47a5-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez un projet Report Server nouveau ou existant.</span><span class="sxs-lookup"><span data-stu-id="b47a5-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open an existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="b47a5-110">Dans le menu **Projet** , cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b47a5-110">From the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="b47a5-111">La _\<project>_ boîte de dialogue **pages de propriétés** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="b47a5-111">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b47a5-112">Dans la liste **Configuration** , sélectionnez le nom d’une configuration de build de solution à utiliser pour générer et publier votre rapport.</span><span class="sxs-lookup"><span data-stu-id="b47a5-112">In the **Configuration** list, select the name of a solution build configuration to use to build and publish your report.</span></span> <span data-ttu-id="b47a5-113">La configuration actuelle est indiquée comme **active**( *\<configuration>* ).</span><span class="sxs-lookup"><span data-stu-id="b47a5-113">The current configuration is listed as **Active**(*\<configuration>*).</span></span>  
  
4.  <span data-ttu-id="b47a5-114">Si vous voulez publier les sources de données partagées dans votre projet et remplacer celles précédemment publiées, attribuez à **OverwriteDataSources** la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="b47a5-114">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="b47a5-115">Facultatif Pour **TargetDataSourceFolder**, tapez une URL vers une bibliothèque SharePoint ou un dossier de bibliothèque (par exemple, *http://TestServer/TestSite/Documents/DataSources)* .</span><span class="sxs-lookup"><span data-stu-id="b47a5-115">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder (for example, *http://TestServer/TestSite/Documents/DataSources)*.</span></span>  
  
     <span data-ttu-id="b47a5-116">Si vous ne spécifiez pas de valeur, la valeur **TargetReportFolder** est utilisée.</span><span class="sxs-lookup"><span data-stu-id="b47a5-116">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="b47a5-117">Pour **TargetReportFolder**, tapez une URL vers une bibliothèque ou un dossier de bibliothèque (par exemple, *http://TestServer/TestSite/Documents/Reports)* .</span><span class="sxs-lookup"><span data-stu-id="b47a5-117">For **TargetReportFolder**, type a URL to a library or library folder (for example, *http://TestServer/TestSite/Documents/Reports)*.</span></span>  
  
7.  <span data-ttu-id="b47a5-118">Pour **TargetServerURL**, tapez l’URL d’un sous-site ou d’un site SharePoint de niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="b47a5-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="b47a5-119">Si vous ne spécifiez pas de site, le site de niveau supérieur par défaut est utilisé (par exemple,, *http://servername* *http://servername/site* ou *http://servername/site/subsite* ).</span><span class="sxs-lookup"><span data-stu-id="b47a5-119">If you do not specify a site, the default top-level site is used (for example, *http://servername*, *http://servername/site*, or *http://servername/site/subsite*).</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="b47a5-120">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le rapport à publier, puis cliquez sur **Déployer**.</span><span class="sxs-lookup"><span data-stu-id="b47a5-120">In Solution Explorer, right-click the report you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="b47a5-121">Le rapport est publié à l’emplacement spécifié dans **TargetReportFolder**.</span><span class="sxs-lookup"><span data-stu-id="b47a5-121">The report is published to the location specified in **TargetReportFolder**.</span></span> <span data-ttu-id="b47a5-122">Les erreurs de déploiement apparaissent dans la fenêtre Sortie.</span><span class="sxs-lookup"><span data-stu-id="b47a5-122">Deployment errors appear in the Output window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b47a5-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b47a5-123">See Also</span></span>  
 <span data-ttu-id="b47a5-124">[Pages de propriétés du projet, boîte de dialogue](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="b47a5-124">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="b47a5-125">[Définir les propriétés de déploiement &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="b47a5-125">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="b47a5-126">[Publication de rapports sur un serveur de rapports](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="b47a5-126">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="b47a5-127">[Exemples d’URL pour les éléments de rapport publiés sur un serveur de rapports en mode SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="b47a5-127">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 [<span data-ttu-id="b47a5-128">Utiliser une connexion de données Office &#40;.odc&#41; avec les rapports &#40;Reporting Services en mode intégré SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="b47a5-128">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
