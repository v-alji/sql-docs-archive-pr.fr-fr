---
title: Publier des rapports | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], publishing
- publishing reports [Reporting Services]
ms.assetid: ef5a514e-e818-4041-a8b0-15835f9a046b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb54308a6b15260d4c336950f231d0ee40836430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600615"
---
# <a name="publish-reports"></a><span data-ttu-id="51ee5-102">Publier des rapports</span><span class="sxs-lookup"><span data-stu-id="51ee5-102">Publish Reports</span></span>
  <span data-ttu-id="51ee5-103">Dans[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], vous pouvez publier l’ensemble des rapports et sources de données partagées dans un projet Report Server sur un serveur de rapports en déployant le projet, ou vous pouvez publier un rapport unique.</span><span class="sxs-lookup"><span data-stu-id="51ee5-103">From[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can publish either all the reports and shared data sources in a Report Server project to a report server by deploying the project, or you can publish a single report.</span></span> <span data-ttu-id="51ee5-104">Avant de pouvoir publier un rapport, vous devez spécifier l'URL du serveur de rapports cible.</span><span class="sxs-lookup"><span data-stu-id="51ee5-104">Before you can publish a report you must specify the URL of the target report server.</span></span> <span data-ttu-id="51ee5-105">Pour plus d’informations, consultez [Définir des propriétés de déploiement &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="51ee5-105">For more information, see [Set Deployment Properties &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span></span>  
  
 <span data-ttu-id="51ee5-106">Vous pouvez utiliser la version [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour ouvrir, modifier, afficher un aperçu, enregistrer et publier des rapports [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] et [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="51ee5-106">You can use the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] version of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to open, modify, preview, save, and publish both [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] and [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] reports.</span></span> <span data-ttu-id="51ee5-107">Pour plus d’informations, consultez [Déploiement et prise en charge des versions dans les outils de données SQL Server &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="51ee5-107">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
### <a name="to-publish-all-reports-in-a-project"></a><span data-ttu-id="51ee5-108">Pour publier tous les rapports d'un projet</span><span class="sxs-lookup"><span data-stu-id="51ee5-108">To publish all reports in a project</span></span>  
  
-   <span data-ttu-id="51ee5-109">Dans le menu **générer** , cliquez \*\*sur \<report project name> déployer \*\*.</span><span class="sxs-lookup"><span data-stu-id="51ee5-109">On the **Build** menu, click **Deploy \<report project name>**.</span></span> <span data-ttu-id="51ee5-110">Vous pouvez également, dans l’Explorateur de solutions, cliquer avec le bouton droit sur le projet de rapport, puis cliquer sur **Déployer**.</span><span class="sxs-lookup"><span data-stu-id="51ee5-110">Alternatively, in Solution Explorer, right-click the report project and then click **Deploy**.</span></span> <span data-ttu-id="51ee5-111">Vous pouvez consulter l'état du processus de publication dans la fenêtre Sortie.</span><span class="sxs-lookup"><span data-stu-id="51ee5-111">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="51ee5-112">Lorsque vous déployez un projet Report Server, les sources de données partagées dans le projet de rapport sont également déployées.</span><span class="sxs-lookup"><span data-stu-id="51ee5-112">When you deploy a Report Server project, the shared data sources in the report project are also deployed.</span></span>  
  
### <a name="to-publish-a-single-report"></a><span data-ttu-id="51ee5-113">Pour publier un seul rapport</span><span class="sxs-lookup"><span data-stu-id="51ee5-113">To publish a single report</span></span>  
  
-   <span data-ttu-id="51ee5-114">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le rapport, puis cliquez sur **Déployer**.</span><span class="sxs-lookup"><span data-stu-id="51ee5-114">In Solution Explorer, right-click the report and then click **Deploy**.</span></span> <span data-ttu-id="51ee5-115">Vous pouvez consulter l'état du processus de publication dans la fenêtre Sortie.</span><span class="sxs-lookup"><span data-stu-id="51ee5-115">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="51ee5-116">Lorsque vous publiez un rapport, vous devez également déployer les sources de données partagées que le rapport utilise.</span><span class="sxs-lookup"><span data-stu-id="51ee5-116">When you publish a report, you must also deploy the shared data sources that the report uses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ee5-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51ee5-117">See Also</span></span>  
 <span data-ttu-id="51ee5-118">[Publication de sources de données et de rapports](reports/publishing-data-sources-and-reports.md) </span><span class="sxs-lookup"><span data-stu-id="51ee5-118">[Publishing Data Sources and Reports](reports/publishing-data-sources-and-reports.md) </span></span>  
 <span data-ttu-id="51ee5-119">[Aperçu des rapports](reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="51ee5-119">[Previewing Reports](reports/previewing-reports.md) </span></span>  
 <span data-ttu-id="51ee5-120">[Publication de rapports sur un serveur de rapports](reports/publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="51ee5-120">[Publishing Reports to a Report Server](reports/publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="51ee5-121">[Recherche, affichage et gestion de rapports &#40;Générateur de rapports et SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="51ee5-121">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="51ee5-122">Exportation de rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="51ee5-122">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](report-builder/export-reports-report-builder-and-ssrs.md)  
  
  
