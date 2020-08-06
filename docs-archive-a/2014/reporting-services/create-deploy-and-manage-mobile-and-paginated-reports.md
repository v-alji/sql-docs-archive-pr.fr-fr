---
title: Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services]
- SSRS
- reports [Reporting Services], about reports
- Reporting Services
- SQL Server Reporting Services
ms.assetid: b8d18d3d-9db0-43e7-8286-7b46cc3a37ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0418acaab54032148f4bc6d42d06c97070b89e1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695444"
---
# <a name="reporting-services-ssrs"></a><span data-ttu-id="c3e92-102">Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="c3e92-102">Reporting Services (SSRS)</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="c3e92-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]fournit une gamme complète d’outils et de services prêts à l’emploi pour vous aider à créer, déployer et gérer des rapports pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c3e92-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="c3e92-104">intègre des fonctionnalités de programmation qui vous permettent d'étendre et de personnaliser votre fonctionnalité de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="c3e92-104">includes programming features that enable you to extend and customize your reporting functionality.</span></span>

 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="c3e92-105">est une plateforme de création de rapports basée sur serveur qui fournit des fonctionnalités complètes de création de rapports pour diverses sources de données.</span><span class="sxs-lookup"><span data-stu-id="c3e92-105">is a server-based reporting platform that provides comprehensive reporting functionality for a variety of data sources.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="c3e92-106">comprend un ensemble complet d’outils permettant de créer, gérer et remettre des rapports, ainsi que des API qui permettent aux développeurs d’intégrer ou d’étendre le traitement des données et des rapports dans des applications personnalisées.</span><span class="sxs-lookup"><span data-stu-id="c3e92-106">includes a complete set of tools for you to create, manage, and deliver reports, and APIs that enable developers to integrate or extend data and report processing in custom applications.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="c3e92-107">les outils fonctionnent dans l' [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] environnement et sont entièrement intégrés aux [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Outils et aux composants.</span><span class="sxs-lookup"><span data-stu-id="c3e92-107">tools work within the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] environment and are fully integrated with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tools and components.</span></span>

 <span data-ttu-id="c3e92-108">Avec [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], vous pouvez créer des rapports de type interactif, tabulaire, graphique ou libre à partir de sources de données XML, relationnelles et multidimensionnelles.</span><span class="sxs-lookup"><span data-stu-id="c3e92-108">With [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], you can create interactive, tabular, graphical, or free-form reports from relational, multidimensional, or XML-based data sources.</span></span> <span data-ttu-id="c3e92-109">Les rapports peuvent inclure une visualisation complète des données, y compris des graphiques, des cartes et des graphiques sparkline.</span><span class="sxs-lookup"><span data-stu-id="c3e92-109">Reports can include rich data visualization, including charts, maps, and sparklines.</span></span> <span data-ttu-id="c3e92-110">Vous pouvez publier des rapports, planifier leur traitement ou y accéder à la demande.</span><span class="sxs-lookup"><span data-stu-id="c3e92-110">You can publish reports, schedule report processing, or access reports on-demand.</span></span> <span data-ttu-id="c3e92-111">Vous pouvez sélectionner divers formats d’affichage, exporter des rapports vers d'autres applications comme [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]et vous abonner à des rapports publiés.</span><span class="sxs-lookup"><span data-stu-id="c3e92-111">You can select from a variety of viewing formats, export reports to other applications such as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], and subscribe to published reports.</span></span> <span data-ttu-id="c3e92-112">Les rapports que vous créez peuvent être consultés par le biais d'une connexion Internet ou en tant qu'application [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows ou site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c3e92-112">The reports that you create can be viewed over a Web-based connection or as part of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows application or SharePoint site.</span></span> <span data-ttu-id="c3e92-113">Vous pouvez également créer des alertes de données sur des rapports publiés sur un site SharePoint et recevoir des messages électroniques lorsque les données du rapport sont modifiées.</span><span class="sxs-lookup"><span data-stu-id="c3e92-113">You can also create data alerts on reports published to a SharePoint site and receive email messages when report data changes.</span></span>

 <span data-ttu-id="c3e92-114">Pour plus d’informations sur les nouvelles fonctionnalités de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , consultez [nouveautés &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c3e92-114">For more information about features new in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [What's New &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span></span>

 <span data-ttu-id="c3e92-115">Pour plus d'informations sur les autres composants, outils et ressources de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , consultez la [Documentation en ligne de SQL Server](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="c3e92-115">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>

 <span data-ttu-id="c3e92-116">Icône **Parcourir le contenu par dossier de zone** ![Folder icon](media/hlp-16folder.gif "Icône de dossier") [Reporting Services serveur de rapports](../../2014/reporting-services/reporting-services-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-116">**Browse Content by Area** ![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Report Server](../../2014/reporting-services/reporting-services-report-server.md)</span></span>

 <span data-ttu-id="c3e92-117">![Icône de dossier](media/hlp-16folder.gif "Icône de dossier") [Reporting Services des rapports &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-117">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Reports &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span></span>

 <span data-ttu-id="c3e92-118">![Icône de dossier](media/hlp-16folder.gif "Icône de dossier") [données de rapport &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-118">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Data &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span></span>

 <span data-ttu-id="c3e92-119">![Folder icon](media/hlp-16folder.gif "Icône de dossier") [Paramètres de rapport de l’icône de dossier &#40;Générateur de rapports et de concepteur de rapports&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-119">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span></span>

 <span data-ttu-id="c3e92-120">![Icône de dossier](media/hlp-16folder.gif "Icône de dossier") [parties de rapport dans Concepteur de rapports &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-120">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parts in Report Designer &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span></span>

 <span data-ttu-id="c3e92-121">![Folder icon](media/hlp-16folder.gif "Icône de dossier") [Planifications](subscriptions/schedules.md) d’icône de dossier</span><span class="sxs-lookup"><span data-stu-id="c3e92-121">![Folder icon](media/hlp-16folder.gif "Folder icon") [Schedules](subscriptions/schedules.md)</span></span>

 <span data-ttu-id="c3e92-122">![Icône de dossier](media/hlp-16folder.gif "Icône de dossier") [abonnements et &#40;de remise Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-122">![Folder icon](media/hlp-16folder.gif "Folder icon") [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span></span>

 <span data-ttu-id="c3e92-123">![Icône de dossier](media/hlp-16folder.gif "Icône de dossier") [Reporting Services des alertes de données](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-123">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>

 <span data-ttu-id="c3e92-124">![Icône de dossier](media/hlp-16folder.gif "Icône de dossier") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span><span class="sxs-lookup"><span data-stu-id="c3e92-124">![Folder icon](media/hlp-16folder.gif "Folder icon") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span></span>

 <span data-ttu-id="c3e92-125">![Icône de dossier](media/hlp-16folder.gif "Icône de dossier") [Reporting Services sécurité et protection](security/reporting-services-security-and-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-125">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Security and Protection](security/reporting-services-security-and-protection.md)</span></span>

 <span data-ttu-id="c3e92-126">![Icône de dossier](media/hlp-16folder.gif "Icône de dossier") [accès URL &#40;SSRS&#41;](url-access-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-126">![Folder icon](media/hlp-16folder.gif "Folder icon") [URL Access &#40;SSRS&#41;](url-access-ssrs.md)</span></span>

 <span data-ttu-id="c3e92-127">Extensions d' ![icône de dossier](media/hlp-16folder.gif "Icône de dossier") [&#40;SSRS&#41;](extensions-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-127">![Folder icon](media/hlp-16folder.gif "Folder icon") [Extensions &#40;SSRS&#41;](extensions-ssrs.md)</span></span>

 <span data-ttu-id="c3e92-128">![Icône de dossier](media/hlp-16folder.gif "Icône de dossier") [Reporting Services outils](tools/reporting-services-tools.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-128">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Tools](tools/reporting-services-tools.md)</span></span>

 <span data-ttu-id="c3e92-129">![Folder icon](media/hlp-16folder.gif "Icône de dossier") Informations [de référence sur les erreurs et événements de l’icône de dossier &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-129">![Folder icon](media/hlp-16folder.gif "Folder icon") [Errors and Events Reference &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span></span>

 <span data-ttu-id="c3e92-130">Informations de référence sur la fonctionnalité d' ![icône de dossier](media/hlp-16folder.gif "Icône de dossier") [&#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="c3e92-130">![Folder icon](media/hlp-16folder.gif "Folder icon") [Feature Reference &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="c3e92-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3e92-131">See Also</span></span>
 [<span data-ttu-id="c3e92-132">Centre de ressources SQL Server</span><span class="sxs-lookup"><span data-stu-id="c3e92-132">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?linkID=219676)


