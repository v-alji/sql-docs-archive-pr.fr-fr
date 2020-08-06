---
title: Intégration de Reporting Services à des applications | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- integrating reports [Reporting Services]
- custom applications [SSRS]
- Reporting Services, application integration
- application integration [Reporting Services]
- reports [Reporting Services], integrating
ms.assetid: 49eb539c-d89b-4291-839a-0ec1a65cd270
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ab92008c5beb4d931e8e781857d766bb56a1efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600665"
---
# <a name="integrating-reporting-services-into-applications"></a><span data-ttu-id="a3ed7-102">Intégration de Reporting Services dans les applications</span><span class="sxs-lookup"><span data-stu-id="a3ed7-102">Integrating Reporting Services into Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="a3ed7-103">est une plate-forme de création de rapports ouverte et extensible conçue pour fournir aux développeurs un jeu complet d'API  pour développer des solutions.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-103">is an open and extensible reporting platform designed to provide developers with a comprehensive set of APIs for developing solutions.</span></span>  
  
 <span data-ttu-id="a3ed7-104">Il existe trois options pour [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] l’intégration dans des applications personnalisées : le service Web Report Server, également appelé [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API SOAP, les contrôles ReportViewer pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] et l’accès URL.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-104">There are three options for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into custom applications: the Report Server Web service, also known as the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API, the ReportViewer controls for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)], and URL access.</span></span> <span data-ttu-id="a3ed7-105">Chaque option représente une approche différente de l'intégration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans vos applications.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-105">Each option provides a different approach for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span>  
  
## <a name="report-server-web-service"></a><span data-ttu-id="a3ed7-106">service Web Report Server</span><span class="sxs-lookup"><span data-stu-id="a3ed7-106">Report Server Web Service</span></span>  
 <span data-ttu-id="a3ed7-107">Le service Web Report Server constitue la principale interface de développement avec [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3ed7-107">The Report Server Web service is the primary interface for developing against [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="a3ed7-108">Que vous développiez du code pour gérer votre catalogue de rapports ou pour effectuer le rendu de rapports dans un format pris en charge, le service Web propose toutes les méthodes nécessaires pour intégrer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans vos applications.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-108">Whether you are developing code to manage your report catalog or developing code to render reports to a supported format, the Web service exposes all the necessary methods to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span> <span data-ttu-id="a3ed7-109">Ainsi, par exemple, le Gestionnaire de rapports, qui est inclus dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], utilise le service web pour gérer la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-109">An example of one such application is Report Manager, which is included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]; it uses the Web service to manage the report server database.</span></span>  
  
## <a name="reportviewer-controls-for-visual-studio"></a><span data-ttu-id="a3ed7-110">Contrôles ReportViewer pour Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a3ed7-110">ReportViewer Controls for Visual Studio</span></span>  
 <span data-ttu-id="a3ed7-111">Les contrôles ReportViewer inclus dans [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] sont utilisés pour intégrer la consultation de rapports dans vos applications.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-111">The ReportViewer controls included with [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] are used for integrating report viewing into your applications.</span></span> <span data-ttu-id="a3ed7-112">Il existe deux contrôles : un pour les applications Windows Forms et un autre pour les applications Web Forms.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-112">There are two controls: one for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="a3ed7-113">Chaque contrôle propose une fonctionnalité de consultation des rapports qui ont été déployés sur un serveur de rapports et permet d'effectuer le rendu de rapports dans un environnement où un aucun serveur de rapports n'est installé.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-113">Each control provides the capability for viewing reports that have been deployed to a report server as well as the ability to render reports that exist in an environment where a report server has not been installed.</span></span>  
  
## <a name="url-access"></a><span data-ttu-id="a3ed7-114">Accès URL</span><span class="sxs-lookup"><span data-stu-id="a3ed7-114">URL Access</span></span>  
 <span data-ttu-id="a3ed7-115">L'accès URL est une autre option d'intégration de la consultation de rapports dans vos applications si les contrôles ReportViewer ne sont pas proposés en option.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-115">URL access is another option for integrating report viewing into your applications if the ReportViewer controls are not an option.</span></span> <span data-ttu-id="a3ed7-116">Par ailleurs, l'accès URL est utile pour envoyer aux utilisateurs des liens vers des rapports par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-116">In addition, URL access is useful for sending links to reports to users via e-mail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3ed7-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a3ed7-117">In This Section</span></span>  
 [<span data-ttu-id="a3ed7-118">Intégration de Reporting Services à l’aide de SOAP</span><span class="sxs-lookup"><span data-stu-id="a3ed7-118">Integrating Reporting Services Using SOAP</span></span>](../application-integration/integrating-reporting-services-using-soap.md)  
 <span data-ttu-id="a3ed7-119">Décrit comment intégrer la navigation et la gestion des rapports [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans vos applications de gestion existantes à l'aide du service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-119">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation and management into your existing business applications using the Report Server Web service.</span></span>  
  
 [<span data-ttu-id="a3ed7-120">Intégration de Reporting Services à l'aide des contrôles ReportViewer</span><span class="sxs-lookup"><span data-stu-id="a3ed7-120">Integrating Reporting Services Using the ReportViewer Controls</span></span>](../application-integration/integrating-reporting-services-using-reportviewer-controls.md)  
 <span data-ttu-id="a3ed7-121">Décrit comment intégrer la consultation de rapports dans vos applications existantes à l'aide de contrôles ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-121">Describes how to integrate report viewing into your existing applications using the ReportViewer controls.</span></span>  
  
 [<span data-ttu-id="a3ed7-122">Intégration d’Reporting Services à l’aide de l’accès URL</span><span class="sxs-lookup"><span data-stu-id="a3ed7-122">Integrating Reporting Services Using URL Access</span></span>](../application-integration/integrating-reporting-services-using-url-access.md)  
 <span data-ttu-id="a3ed7-123">Décrit comment intégrer la navigation entre les rapports [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans vos applications de gestion existantes à l'aide de l'accès URL.</span><span class="sxs-lookup"><span data-stu-id="a3ed7-123">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation into your existing business applications using URL access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ed7-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3ed7-124">See Also</span></span>  
 <span data-ttu-id="a3ed7-125">[Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a3ed7-125">[Report Manager  &#40;SSRS Native Mode&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="a3ed7-126">[Choix entre l’accès URL et SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span><span class="sxs-lookup"><span data-stu-id="a3ed7-126">[Choosing Between URL Access and SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span></span>  
 <span data-ttu-id="a3ed7-127">[Référence technique &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3ed7-127">[Technical Reference &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="a3ed7-128">Service Web des serveurs de rapports</span><span class="sxs-lookup"><span data-stu-id="a3ed7-128">Report Server Web Service</span></span>](../report-server-web-service/report-server-web-service.md)  
  
  
