---
title: Intégration de Reporting Services à l’aide des contrôles ReportViewer | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- ReportViewer controls
- integrating reports [Reporting Services]
ms.assetid: 3ba47fb4-73a9-4059-89fd-329adebe94a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 18e28dbf1557bf36106b454738d0c0bfc037f2a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600664"
---
# <a name="integrating-reporting-services-using-the-reportviewer-controls"></a><span data-ttu-id="0edd2-102">Intégration de Reporting Services à l'aide des contrôles ReportViewer</span><span class="sxs-lookup"><span data-stu-id="0edd2-102">Integrating Reporting Services Using the ReportViewer Controls</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="0edd2-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)]fournit deux contrôles ReportViewer permettant d’intégrer les fonctionnalités d’affichage des rapports dans vos applications.</span><span class="sxs-lookup"><span data-stu-id="0edd2-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] provides two ReportViewer controls for integrating report viewing functionality into your applications.</span></span> <span data-ttu-id="0edd2-104">Il existe une version pour les applications Windows Forms et une version pour les applications Web Forms.</span><span class="sxs-lookup"><span data-stu-id="0edd2-104">There is a version for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="0edd2-105">Chaque contrôle offre des fonctionnalités similaires, mais chacun est conçu pour un environnement particulier.</span><span class="sxs-lookup"><span data-stu-id="0edd2-105">Each control provides similar functionality but each is designed to target their individual environments.</span></span> <span data-ttu-id="0edd2-106">Les deux contrôles peuvent traiter des rapports qui ont été déployés sur un serveur de rapports (mode de traitement à distance) ou qui ont été copiés sur un ordinateur où [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] n’a pas été installé (mode de traitement local).</span><span class="sxs-lookup"><span data-stu-id="0edd2-106">Both controls can process reports that have been deployed to a report server (remote processing mode) or have been copied to a computer where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] has not been installed (local processing mode).</span></span>  
  
 <span data-ttu-id="0edd2-107">Le contrôle ReportViewer n'offre pas la prise en charge intégrée de l'adaptation dynamique à différents appareils avec différentes résolutions d'écran.</span><span class="sxs-lookup"><span data-stu-id="0edd2-107">The ReportViewer control does not include built-in support for dynamically adapting to different devices with different screen resolutions.</span></span>  
  
## <a name="remote-processing-mode"></a><span data-ttu-id="0edd2-108">Mode de traitement à distance</span><span class="sxs-lookup"><span data-stu-id="0edd2-108">Remote Processing Mode</span></span>  
 <span data-ttu-id="0edd2-109">Le mode de traitement à distance est la méthode recommandée pour consulter les rapports qui ont été déployés sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0edd2-109">Remote processing mode is the preferred method for viewing reports that have been deployed to a report server.</span></span> <span data-ttu-id="0edd2-110">Le mode de traitement à distance offre les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="0edd2-110">Remote processing mode provides the following advantages:</span></span>  
  
-   <span data-ttu-id="0edd2-111">Le traitement à distance offre une solution optimisée pour l'exécution de rapports car le rapport est traité par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0edd2-111">Remote processing provides an optimized solution for running reports because the report is processed by the report server.</span></span>  
  
-   <span data-ttu-id="0edd2-112">Dans la mesure où l'ensemble du traitement est géré par le serveur de rapports, une demande de rapport peut être traitée par plusieurs serveurs de rapports dans un déploiement avec montée en puissance parallèle ou par un serveur doté de plusieurs processeurs dans un déploiement avec montée en puissance par unité.</span><span class="sxs-lookup"><span data-stu-id="0edd2-112">Because all processing is handled by the report server, a report request can be processed by multiple report servers in a scale-out deployment or a server that has multiple processors in a scale-up scenario.</span></span>  
  
 <span data-ttu-id="0edd2-113">Par ailleurs, les rapports exécutés en mode à distance peuvent utiliser l'ensemble des fonctionnalités du serveur de rapports, notamment toutes les extensions de rendu et de données.</span><span class="sxs-lookup"><span data-stu-id="0edd2-113">In addition, reports run in remote mode can utilize the full functionality of the report server including all rendering and data extensions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0edd2-114">La liste des extensions disponibles pour le contrôle ReportViewer lorsqu'il s'exécute en mode de traitement à distance dépend de l'édition de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] qui est installée sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0edd2-114">The list of extensions available to the ReportViewer control when it is running in remote processing mode depends on the edition of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is installed on the report server.</span></span>  
  
## <a name="local-processing-mode"></a><span data-ttu-id="0edd2-115">Mode de traitement local</span><span class="sxs-lookup"><span data-stu-id="0edd2-115">Local Processing Mode</span></span>  
 <span data-ttu-id="0edd2-116">Le mode de traitement local est une autre méthode d'affichage et de rendu des rapports qui peut être utilisée lorsque [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] n'est pas installé.</span><span class="sxs-lookup"><span data-stu-id="0edd2-116">Local processing mode provides an alternative method for viewing and rendering reports when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is not installed.</span></span> <span data-ttu-id="0edd2-117">Contrairement au traitement à distance, seul un sous-ensemble des fonctionnalités fournies par le serveur de rapports est disponible dans le contrôle.</span><span class="sxs-lookup"><span data-stu-id="0edd2-117">Unlike remote processing only a subset of the functionality provided by the report server is available in the control.</span></span> <span data-ttu-id="0edd2-118">En mode de traitement local, le traitement des données n'est pas géré par le contrôle, mais implémenté par l'application hôte.</span><span class="sxs-lookup"><span data-stu-id="0edd2-118">In local processing mode, data processing is not handled by the control but rather implemented by the hosting application.</span></span> <span data-ttu-id="0edd2-119">Cependant, le traitement des rapports est géré par le contrôle lui-même.</span><span class="sxs-lookup"><span data-stu-id="0edd2-119">However report processing is handled by the control itself.</span></span> <span data-ttu-id="0edd2-120">En mode de traitement local, seules les extensions de rendu PDF, Excel, Word et Image sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="0edd2-120">In local processing mode, only the PDF, Excel, Word, and Image rendering extensions are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0edd2-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0edd2-121">See Also</span></span>  
 <span data-ttu-id="0edd2-122">[Intégration de Reporting Services dans des applications](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="0edd2-122">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="0edd2-123">Créer des rapports SSRS à l’aide de Visual Studio (blog)</span><span class="sxs-lookup"><span data-stu-id="0edd2-123">Create SSRS Reports Using Visual Studio (Blog)</span></span>](https://jwcooney.com/2015/01/07/ssrs-basics-set-up-visual-studio-to-write-a-new-ssrs-report/)  
  
  
