---
title: Problèmes de mise à niveau de Reporting Services (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], upgrade issues
- Reporting Services, upgrades
- upgrading Reporting Services
- report servers [Reporting Services], upgrade issues
ms.assetid: d9663f25-98d7-4508-ae3c-55a7277211bd
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 569afe735d68a724c0b4cc61ad2b7767088c2b30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614347"
---
# <a name="reporting-services-upgrade-issues-upgrade-advisor"></a><span data-ttu-id="3f442-102">Problèmes de mise à niveau de Reporting Services (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="3f442-102">Reporting Services Upgrade Issues (Upgrade Advisor)</span></span>
  <span data-ttu-id="3f442-103">Les rubriques suivantes décrivent les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] problèmes qui peuvent affecter votre mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3f442-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] issues that might affect your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="3f442-104">Les rubriques décrivent les actions que vous pouvez prendre pour atténuer l’effet de ces modifications sur votre environnement.</span><span class="sxs-lookup"><span data-stu-id="3f442-104">The topics describe actions that you can take to mitigate the effect of these changes on your environment.</span></span>  
  
 <span data-ttu-id="3f442-105">Le Conseiller de mise à niveau analyse une installation du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3f442-105">Upgrade Advisor analyzes a report server installation.</span></span> <span data-ttu-id="3f442-106">Si seuls les composants clients sont installés (par exemple, si le Concepteur de rapports est le seul composant [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installé sur l'ordinateur), aucun problème ne sera signalé.</span><span class="sxs-lookup"><span data-stu-id="3f442-106">If only client components are installed (for example, if Report Designer is the only [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] component installed on the computer), no issues will be reported.</span></span>  
  
 <span data-ttu-id="3f442-107">Selon la façon dont vous avez configuré votre installation, vous pouvez rencontrer des problèmes supplémentaires qui ne sont pas signalés par le Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="3f442-107">Depending on how you configured your installation, you may encounter additional issues that are not reported by Upgrade Advisor.</span></span> <span data-ttu-id="3f442-108">Ces problèmes n'empêchent pas la mise à niveau de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], mais ils peuvent affecter la manière dont les rapports et les applications s'exécuteront après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="3f442-108">These issues do not prevent a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] upgrade from succeeding, but they may affect how reports and applications run after an upgrade is finished.</span></span> <span data-ttu-id="3f442-109">Pour en savoir plus sur ces problèmes, consultez « Compatibilité descendante de Reporting Services » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f442-109">To learn about these issues, see "Reporting Services Backward Compatibility" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="3f442-110">Si vous ne pouvez pas utiliser le programme d'installation pour mettre à niveau une installation de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous pouvez installer une nouvelle instance de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et migrer votre installation existante vers la nouvelle instance.</span><span class="sxs-lookup"><span data-stu-id="3f442-110">If you cannot use Setup to upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation, you can install a new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance and migrate your existing installation to the new instance.</span></span> <span data-ttu-id="3f442-111">Pour plus d’informations, consultez « mettre à niveau et migrer Reporting Services » dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation en ligne, [mettre à niveau et migrer Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3f442-111">For more information, see "Upgrade and Migrate Reporting Services" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online, [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
 <span data-ttu-id="3f442-112">Les rubriques suivantes décrivent les problèmes connus signalés par le Conseiller de mise à niveau et expliquent comment vous pouvez modifier votre installation existante pour permettre l'exécution d'une mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="3f442-112">The following topics describe known issues that are reported by Upgrade Advisor, and explain how you can modify your existing installation to allow an upgrade to occur.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3f442-113">Le Conseiller de mise à niveau doit être installé sur le serveur de rapports pour analyser une instance de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f442-113">Upgrade Advisor must be installed on the report server to analyze an instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="3f442-114">ne prend pas en charge l'analyse à distance.</span><span class="sxs-lookup"><span data-stu-id="3f442-114">does not support remote analysis.</span></span>  
>   
>  <span data-ttu-id="3f442-115">Pour plus d’informations, consultez [installation du conseiller de mise à niveau](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="3f442-115">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f442-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3f442-116">In This Section</span></span>  
  
-   [<span data-ttu-id="3f442-117">Certificats clients sur le site Web du serveur de rapports &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-117">Client certificates on the report server web site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/client-certificates-on-the-report-server-web-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-118">Des extensions personnalisées ont été détectées sur le serveur de rapports &#40;le conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-118">Custom extensions were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-extensions-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-119">Des éléments de rapport personnalisés ont été détectés sur le serveur de rapports &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-119">Custom report items were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-report-items-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-120">Les composants de compatibilité descendante IIS n’ont pas été détectés &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-120">IIS backward compatibility components were not detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/iis-backward-compatibility-components-were-not-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-121">Restriction d’adresse IP détectée &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-121">IP address restriction detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/ip-address-restriction-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-122">Filtres ISAPI détectés sur le site du serveur de rapports &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-122">ISAPI filters detected on the report server site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/isapi-filters-detected-on-the-report-server-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-123">Des extensions obsolètes ont été détectées sur l’ordinateur du serveur de rapports &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-123">Obsolete extensions were detected on the report server computer &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/obsolete-extensions-were-detected-on-the-report-server-computer-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-124">La base de données du serveur de rapports n’est pas configurée &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-124">Report server database is not configured &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/report-server-database-is-not-configured-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-125">SQL Server groupe de services Web du serveur de rapports 2005 détecté &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-125">SQL Server 2005 Report Server Web Service group detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-2005-report-server-web-service-group-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-126">Les répertoires virtuels ne sont pas spécifiés &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-126">Virtual directories are unspecified &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directories-are-unspecified-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-127">Le répertoire virtuel a une méthode d’authentification non prise en charge &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-127">Virtual directory has unsupported authentication method &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directory-has-unsupported-authentication-method-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-128">Modifications des limites de l’UC et de la mémoire pour SQL Server Standard et Enterprise &#40;le conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-128">Changes to CPU and memory limits for SQL Server Standard and Enterprise &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/cpu-memory-limits-changes-sql-server-standard-enterprise-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-129">Comptes de domaine requis pour la batterie de serveurs SharePoint &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-129">Domain accounts required for SharePoint farm &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/domain-accounts-required-for-sharepoint-farm-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-130">Navigation directe vers le conseiller de mise à niveau &#40;du serveur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-130">Direct Browsing to Report Server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/direct-browsing-to-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-131">Microsoft SharePoint 2007 est installé &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-131">Microsoft SharePoint 2007 is Installed &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/microsoft-sharepoint-2007-is-installed-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-132">Microsoft SQL Server Reporting Services service partagé SharePoint est installé côte à côte &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-132">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-reporting-services-sharepoint-shared-service-side-by-side-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-133">Le conseiller de mise à niveau de Moteur de base de données Server &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="3f442-133">Incompatible Database Engine Server Collation &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/incompatible-database-engine-server-collation-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3f442-134">Autres problèmes de mise à niveau de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3f442-134">Other Reporting Services Upgrade Issues</span></span>](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md)  
  
  
