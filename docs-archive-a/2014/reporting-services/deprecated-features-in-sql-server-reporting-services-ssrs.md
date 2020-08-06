---
title: Fonctionnalités dépréciées dans SQL Server Reporting Services dans SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- deprecated features [Reporting Services]
- HTML OWC rendering extension [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: 3876c01e-f81d-4cce-9104-5106a8c369e6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af858ae94bf5ea3d9f0cfe0b99759442dabd6629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610493"
---
# <a name="deprecated-features-in-sql-server-reporting-services-in-sql-server-2014"></a><span data-ttu-id="e57f3-102">Fonctions déconseillées dans SQL Server Reporting Services dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="e57f3-102">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>
  <span data-ttu-id="e57f3-103">Cette rubrique décrit les fonctionnalités déconseillées de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e57f3-103">This topic describes the deprecated [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="e57f3-104">Les fonctionnalités sont toujours disponibles dans la version dans laquelle elles sont déconseillées ; toutefois, leur suppression est planifiée dans une version future de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e57f3-104">The features are still available in the release in which they are deprecated; however the features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e57f3-105">Les fonctions déconseillées ne doivent pas être utilisées dans de nouvelles applications.</span><span class="sxs-lookup"><span data-stu-id="e57f3-105">Deprecated features should not be used in new applications.</span></span>  
  
 <span data-ttu-id="e57f3-106">Dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="e57f3-106">In this topic:</span></span>  
  
-   [<span data-ttu-id="e57f3-107">Fonctions dépréciées dans SQL Server 2014 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e57f3-107">SQL Server 2014 Reporting Services Deprecated Features</span></span>](#bkmk_2014)  
  
-   [<span data-ttu-id="e57f3-108">Fonctions déconseillées dans SQL Server 2012 SP1 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e57f3-108">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>](#bkmk_2012sp1)  
  
-   [<span data-ttu-id="e57f3-109">Fonctions déconseillées dans SQL Server 2012 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e57f3-109">SQL Server 2012 Reporting Services Deprecated Features</span></span>](#bkmk_2012)  
  
-   [<span data-ttu-id="e57f3-110">Fonctions déconseillées dans SQL Server 2008 R2 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e57f3-110">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>](#bkmk_kj)  
  
##  <a name="sql-server-2014-reporting-services-deprecated-features"></a><a name="bkmk_2014"></a><span data-ttu-id="e57f3-111">SQL Server 2014 Reporting Services fonctionnalités déconseillées</span><span class="sxs-lookup"><span data-stu-id="e57f3-111">SQL Server 2014 Reporting Services Deprecated Features</span></span>  
  
### <a name="features-not-supported-in-the-next-version-of-sql-server"></a><span data-ttu-id="e57f3-112">Fonctionnalités non prises en charge dans la prochaine version de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e57f3-112">Features Not Supported in the Next Version of SQL Server</span></span>  
 <span data-ttu-id="e57f3-113">Les fonctionnalités suivantes ne seront [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pas prises en charge dans la **prochaine** version de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e57f3-113">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features will not be supported in the **next** version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e57f3-114">Évitez d'utiliser ces fonctionnalités dans vos nouveaux développements et modifiez dès que possible les applications qui y ont recours.</span><span class="sxs-lookup"><span data-stu-id="e57f3-114">Do not use these features in new development work, and modify applications that currently use these features as soon as possible.</span></span>  
  
#### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="e57f3-115">Paramètres d'informations de périphérique d'extension de rendu HTML</span><span class="sxs-lookup"><span data-stu-id="e57f3-115">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="e57f3-116">Les paramètres d'informations de périphérique suivants pour l'extension de rendu HTML sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-116">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="e57f3-117">ActionScript</span><span class="sxs-lookup"><span data-stu-id="e57f3-117">ActionScript</span></span>  
  
-   <span data-ttu-id="e57f3-118">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="e57f3-118">ActiveXControls</span></span>  
  
-   <span data-ttu-id="e57f3-119">GetImage</span><span class="sxs-lookup"><span data-stu-id="e57f3-119">GetImage</span></span>  
  
-   <span data-ttu-id="e57f3-120">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="e57f3-120">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="e57f3-121">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="e57f3-121">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="e57f3-122">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="e57f3-122">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="e57f3-123">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="e57f3-123">StreamRoot</span></span>  
  
-   <span data-ttu-id="e57f3-124">UsePx</span><span class="sxs-lookup"><span data-stu-id="e57f3-124">UsePx</span></span>  
  
-   <span data-ttu-id="e57f3-125">Zoom</span><span class="sxs-lookup"><span data-stu-id="e57f3-125">Zoom</span></span>  
  
 <span data-ttu-id="e57f3-126">Pour plus d'informations sur l'extension de rendu HTML, consultez [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e57f3-126">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
#### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="e57f3-127">Rendu dans Microsoft Word et Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="e57f3-127">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="e57f3-128">Les extensions de rendu BIFF8[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] génèrent des rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] au format BIFF (Binary Interchange File Format) pour [!INCLUDE[msCoName](../includes/msconame-md.md)] Word et [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="e57f3-128">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="e57f3-129">comprend les extensions qui s’affichent au [!INCLUDE[msCoName](../includes/msconame-md.md)] format Office 2007-2010 Open XML.</span><span class="sxs-lookup"><span data-stu-id="e57f3-129">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
#### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="e57f3-130">Langage RDL (Report Definition Language) version 2005 et antérieures</span><span class="sxs-lookup"><span data-stu-id="e57f3-130">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="e57f3-131">Le langage Report Definition Language (RDL) version 2005 et antérieures est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="e57f3-131">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="e57f3-132">Pour plus d’informations sur le langage RDL, consultez [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e57f3-132">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="e57f3-133">Pour plus d'informations sur la mise à niveau des rapports, consultez [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="e57f3-133">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
#### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="e57f3-134">Éléments de rapport personnalisés SQL Server version 2005 et antérieures</span><span class="sxs-lookup"><span data-stu-id="e57f3-134">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="e57f3-135">Les éléments de rapport personnalisés compilés pour [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 et les versions antérieures sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-135">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="e57f3-136">Instantanés Reporting Services version 2005 et antérieures</span><span class="sxs-lookup"><span data-stu-id="e57f3-136">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="e57f3-137">les instantanés rendus avec [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 et les versions antérieures sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-137">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="report-models"></a><span data-ttu-id="e57f3-138">Modèles de rapport</span><span class="sxs-lookup"><span data-stu-id="e57f3-138">Report Models</span></span>  
 <span data-ttu-id="e57f3-139">Les modèles de rapport du langage de modélisation sémantique (SMDL) sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-139">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="e57f3-140">Bien que vous puissiez continuer à utiliser des modèles de rapport existants comme sources de données dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] les rapports, vous devez envisager de mettre à jour vos rapports afin de supprimer leur dépendance vis-à-vis des modèles de rapport.</span><span class="sxs-lookup"><span data-stu-id="e57f3-140">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="e57f3-141">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]n’inclut pas les outils permettant de créer ou de mettre à jour des modèles de rapport.</span><span class="sxs-lookup"><span data-stu-id="e57f3-141">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="e57f3-142">Pour plus d’informations, consultez [modifications avec rupture dans SQL Server Reporting Services dans SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="e57f3-142">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
#### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="e57f3-143">Méthodes déconseillées dans le point de terminaison de service Web</span><span class="sxs-lookup"><span data-stu-id="e57f3-143">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="e57f3-144">Les opérations suivantes sont déconseillées dans le point de terminaison de service Web <xref:ReportService2010.ReportingService2010> :</span><span class="sxs-lookup"><span data-stu-id="e57f3-144">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
#### <a name="sharepoint-web-parts"></a><span data-ttu-id="e57f3-145">Composants WebPart de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e57f3-145">SharePoint Web Parts</span></span>  
 <span data-ttu-id="e57f3-146">Le fichier CAB d'installation **RSWebParts.cab** et les composants WebPart de SharePoint qui peuvent être extraits du fichier CAB, sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-146">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="e57f3-147">Les composants WebPart déconseillés sont Report Explorer (**SPExplorer.dwp**) et Report Viewer (**SPViewer.dwp**).</span><span class="sxs-lookup"><span data-stu-id="e57f3-147">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="e57f3-148">Pour plus d'informations sur les composants WebPart déconseillés, consultez [Afficher et explorer des rapports en mode natif à l'aide de composants WebPart SharePoint (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx).</span><span class="sxs-lookup"><span data-stu-id="e57f3-148">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
### <a name="features-not-supported-in-a-future-version-of-sql-server"></a><span data-ttu-id="e57f3-149">Fonctionnalités non prises en charge dans une future version de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e57f3-149">Features Not Supported in a Future Version of SQL Server</span></span>  
 <span data-ttu-id="e57f3-150">Les fonctions suivantes du [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] seront prises en charge dans la prochaine version de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mais seront supprimées dans une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e57f3-150">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="e57f3-151">La version spécifique de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] n'a pas été déterminée.</span><span class="sxs-lookup"><span data-stu-id="e57f3-151">The specific version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has not been determined.</span></span>  
  
 <span data-ttu-id="e57f3-152">Aucune fonctionnalité [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] n'a été déconseillée dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e57f3-152">No [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features were deprecated in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="sql-server-2012-sp1-reporting-services-deprecated-features"></a><a name="bkmk_2012sp1"></a><span data-ttu-id="e57f3-153">SQL Server 2012 SP1 Reporting Services fonctionnalités déconseillées</span><span class="sxs-lookup"><span data-stu-id="e57f3-153">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="e57f3-154">Cette section décrit les fonctionnalités [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] déconseillées dans [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e57f3-154">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span></span> <span data-ttu-id="e57f3-155">Les fonctions suivantes du [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] seront prises en charge dans la prochaine version de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], mais seront supprimées dans une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e57f3-155">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="e57f3-156">La version spécifique de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] n'a pas été déterminée.</span><span class="sxs-lookup"><span data-stu-id="e57f3-156">The specific version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] has not been determined.</span></span>  
  
### <a name="sharepoint-web-parts"></a><span data-ttu-id="e57f3-157">Composants WebPart de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e57f3-157">SharePoint Web Parts</span></span>  
 <span data-ttu-id="e57f3-158">Le fichier CAB d'installation **RSWebParts.cab** et les composants WebPart de SharePoint qui peuvent être extraits du fichier CAB, sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-158">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="e57f3-159">Les composants WebPart déconseillés sont Report Explorer (**SPExplorer.dwp**) et Report Viewer (**SPViewer.dwp**).</span><span class="sxs-lookup"><span data-stu-id="e57f3-159">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="e57f3-160">Pour plus d'informations sur les composants WebPart déconseillés, consultez [Afficher et explorer des rapports en mode natif à l'aide de composants WebPart SharePoint (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx).</span><span class="sxs-lookup"><span data-stu-id="e57f3-160">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
##  <a name="sql-server-2012-reporting-services-deprecated-features"></a><a name="bkmk_2012"></a><span data-ttu-id="e57f3-161">SQL Server 2012 Reporting Services fonctionnalités déconseillées</span><span class="sxs-lookup"><span data-stu-id="e57f3-161">SQL Server 2012 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="e57f3-162">Cette section décrit les fonctionnalités [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] déconseillées dans [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e57f3-162">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="e57f3-163">Paramètres d'informations de périphérique d'extension de rendu HTML</span><span class="sxs-lookup"><span data-stu-id="e57f3-163">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="e57f3-164">Les paramètres d'informations de périphérique suivants pour l'extension de rendu HTML sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-164">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="e57f3-165">ActionScript</span><span class="sxs-lookup"><span data-stu-id="e57f3-165">ActionScript</span></span>  
  
-   <span data-ttu-id="e57f3-166">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="e57f3-166">ActiveXControls</span></span>  
  
-   <span data-ttu-id="e57f3-167">GetImage</span><span class="sxs-lookup"><span data-stu-id="e57f3-167">GetImage</span></span>  
  
-   <span data-ttu-id="e57f3-168">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="e57f3-168">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="e57f3-169">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="e57f3-169">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="e57f3-170">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="e57f3-170">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="e57f3-171">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="e57f3-171">StreamRoot</span></span>  
  
-   <span data-ttu-id="e57f3-172">UsePx</span><span class="sxs-lookup"><span data-stu-id="e57f3-172">UsePx</span></span>  
  
-   <span data-ttu-id="e57f3-173">Zoom</span><span class="sxs-lookup"><span data-stu-id="e57f3-173">Zoom</span></span>  
  
 <span data-ttu-id="e57f3-174">Pour plus d'informations sur l'extension de rendu HTML, consultez [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e57f3-174">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="e57f3-175">Rendu dans Microsoft Word et Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="e57f3-175">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="e57f3-176">Les extensions de rendu BIFF8[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] génèrent des rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] au format BIFF (Binary Interchange File Format) pour [!INCLUDE[msCoName](../includes/msconame-md.md)] Word et [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="e57f3-176">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="e57f3-177">comprend les extensions qui s’affichent au [!INCLUDE[msCoName](../includes/msconame-md.md)] format Office 2007-2010 Open XML.</span><span class="sxs-lookup"><span data-stu-id="e57f3-177">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="e57f3-178">Langage RDL (Report Definition Language) version 2005 et antérieures</span><span class="sxs-lookup"><span data-stu-id="e57f3-178">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="e57f3-179">Le langage Report Definition Language (RDL) version 2005 et antérieures est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="e57f3-179">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="e57f3-180">Pour plus d’informations sur le langage RDL, consultez [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e57f3-180">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="e57f3-181">Pour plus d'informations sur la mise à niveau des rapports, consultez [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="e57f3-181">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="e57f3-182">Éléments de rapport personnalisés SQL Server version 2005 et antérieures</span><span class="sxs-lookup"><span data-stu-id="e57f3-182">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="e57f3-183">Les éléments de rapport personnalisés compilés pour [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 et les versions antérieures sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-183">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="e57f3-184">Instantanés Reporting Services version 2005 et antérieures</span><span class="sxs-lookup"><span data-stu-id="e57f3-184">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="e57f3-185">les instantanés rendus avec [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 et les versions antérieures sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-185">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="report-models"></a><span data-ttu-id="e57f3-186">Modèles de rapport</span><span class="sxs-lookup"><span data-stu-id="e57f3-186">Report Models</span></span>  
 <span data-ttu-id="e57f3-187">Les modèles de rapport du langage de modélisation sémantique (SMDL) sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="e57f3-187">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="e57f3-188">Bien que vous puissiez continuer à utiliser des modèles de rapport existants comme sources de données dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] les rapports, vous devez envisager de mettre à jour vos rapports afin de supprimer leur dépendance vis-à-vis des modèles de rapport.</span><span class="sxs-lookup"><span data-stu-id="e57f3-188">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="e57f3-189">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]n’inclut pas les outils permettant de créer ou de mettre à jour des modèles de rapport.</span><span class="sxs-lookup"><span data-stu-id="e57f3-189">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="e57f3-190">Pour plus d’informations, consultez [modifications avec rupture dans SQL Server Reporting Services dans SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="e57f3-190">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="e57f3-191">Méthodes déconseillées dans le point de terminaison de service Web</span><span class="sxs-lookup"><span data-stu-id="e57f3-191">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="e57f3-192">Les opérations suivantes sont déconseillées dans le point de terminaison de service Web <xref:ReportService2010.ReportingService2010> :</span><span class="sxs-lookup"><span data-stu-id="e57f3-192">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
##  <a name="sql-server-2008-r2-reporting-services-deprecated-features"></a><a name="bkmk_kj"></a><span data-ttu-id="e57f3-193">SQL Server 2008 R2 Reporting Services fonctionnalités déconseillées</span><span class="sxs-lookup"><span data-stu-id="e57f3-193">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e57f3-194">SQL Server 2008 R2 étant une mise à niveau de version secondaire de SQL Server 2008, nous vous recommandons d'examiner également le contenu de la section SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="e57f3-194">Because SQL Server 2008 R2 is a minor version upgrade of SQL Server 2008, we recommend that you also review the content in the SQL Server 2008 section.</span></span>  
  
### <a name="report-server-web-service-endpoints"></a><span data-ttu-id="e57f3-195">Points de terminaison du service Web Report Server</span><span class="sxs-lookup"><span data-stu-id="e57f3-195">Report Server Web Service Endpoints</span></span>  
 <span data-ttu-id="e57f3-196">Les services Web <xref:ReportService2005.ReportingService2005> et <xref:ReportService2006.ReportingService2006> ont été déconseillés dans cette version.</span><span class="sxs-lookup"><span data-stu-id="e57f3-196">The Web services <xref:ReportService2005.ReportingService2005> and <xref:ReportService2006.ReportingService2006> have been deprecated in this release.</span></span> <span data-ttu-id="e57f3-197">Ces points de terminaison ont été remplacés par un nouveau point de terminaison : <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="e57f3-197">These endpoints have been replaced by a new endpoint: <xref:ReportService2010.ReportingService2010>.</span></span>  
  
 <span data-ttu-id="e57f3-198">Le nouveau point de terminaison inclut toutes les fonctionnalités disponibles dans les points de terminaison déconseillés et les nouvelles fonctionnalités présentées dans SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e57f3-198">The new endpoint includes all the functionality available in the deprecated endpoints and the new features introduced in SQL Server 2008 R2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57f3-199">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e57f3-199">See Also</span></span>  
 <span data-ttu-id="e57f3-200">[Nouveautés &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="e57f3-200">[What's New &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span></span>  
 <span data-ttu-id="e57f3-201">[Compatibilité descendante](../getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="e57f3-201">[Backward Compatibility](../getting-started/backward-compatibility.md) </span></span>  
 <span data-ttu-id="e57f3-202">[Changements de comportement apportés à SQL Server Reporting Services dans SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="e57f3-202">[Behavior Changes to SQL Server Reporting Services  in SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span></span>  
 [<span data-ttu-id="e57f3-203">Fonctionnalités supprimées dans SQL Server Reporting Services dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="e57f3-203">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)  
  
  
