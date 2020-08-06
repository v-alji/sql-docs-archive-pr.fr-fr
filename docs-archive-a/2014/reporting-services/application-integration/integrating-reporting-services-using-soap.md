---
title: Intégration de Reporting Services à l’aide de SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, application integration
- SOAP [Reporting Services]
- SOAP [Reporting Services], about report integration
- integrating reports [Reporting Services]
- Web service [Reporting Services], application integration
ms.assetid: 6bc17af5-883c-4bfa-87d9-48cd7056d145
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7b6fffd65b22900d7c505c4b50ec290b95fe9ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600659"
---
# <a name="integrating-reporting-services-using-soap"></a><span data-ttu-id="8aac0-102">Intégration de Reporting Services à l'aide de SOAP</span><span class="sxs-lookup"><span data-stu-id="8aac0-102">Integrating Reporting Services Using SOAP</span></span>
  <span data-ttu-id="8aac0-103">L' [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API SOAP fournit plusieurs points de terminaison de service Web pour développer des solutions de création de rapports personnalisées.</span><span class="sxs-lookup"><span data-stu-id="8aac0-103">The [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API provides several Web service endpoints for developing custom reporting solutions.</span></span> <span data-ttu-id="8aac0-104">Les points de terminaison se répartissent actuellement dans deux catégories : la gestion et l'exécution.</span><span class="sxs-lookup"><span data-stu-id="8aac0-104">The endpoints currently fall into two categories: management and execution.</span></span> <span data-ttu-id="8aac0-105">Les fonctionnalités de gestion sont exposées par le biais des points de terminaison <xref:ReportService2005>, <xref:ReportService2006> et <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="8aac0-105">The management functionality is exposed through the <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010> endpoints.</span></span> <span data-ttu-id="8aac0-106">Le point de terminaison <xref:ReportService2005> est utilisé pour gérer un serveur de rapports configuré en mode natif et le point de terminaison <xref:ReportService2006> est utilisé pour gérer un serveur de rapports configuré pour le mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8aac0-106">The <xref:ReportService2005> endpoint is used for managing a report server that is configured in native mode and the <xref:ReportService2006> endpoint is used for managing a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="8aac0-107">Le <xref:ReportService2010> fusionne les fonctionnalités de <xref:ReportService2005> et de <xref:ReportService2006> et peut gérer un serveur de rapports configuré pour le mode natif ou intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8aac0-107">The <xref:ReportService2010> merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage a report server that is configured for either native or SharePoint integrated mode.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8aac0-108">Les points de terminaison <xref:ReportService2005> et <xref:ReportService2006> sont déconseillés dans [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aac0-108">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="8aac0-109">Le point de terminaison <xref:ReportService2010> inclut les fonctionnalités des deux points de terminaison, ainsi que des fonctionnalités de gestion supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="8aac0-109">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="8aac0-110">Les fonctionnalités d'exécution sont exposées par le biais du point de terminaison <xref:ReportExecution2005> et elles sont utilisées lorsque le serveur de rapports est configuré en mode natif ou intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8aac0-110">The execution functionality is exposed through the <xref:ReportExecution2005> endpoint and it is used when the report server is configured in native or SharePoint integrated mode.</span></span> <span data-ttu-id="8aac0-111">Les rubriques suivantes montrent comment ces points de terminaison peuvent être utilisés pour développer des solutions de création de rapports dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, SharePoint et les applications Web.</span><span class="sxs-lookup"><span data-stu-id="8aac0-111">The following topics show how these endpoints can be used for developing reporting solutions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, SharePoint, and Web applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8aac0-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8aac0-112">In This Section</span></span>  
 [<span data-ttu-id="8aac0-113">Utilisation de l'API SOAP dans une application Windows</span><span class="sxs-lookup"><span data-stu-id="8aac0-113">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
 <span data-ttu-id="8aac0-114">Décrit comment utiliser l'API SOAP pour intégrer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans un environnement Windows.</span><span class="sxs-lookup"><span data-stu-id="8aac0-114">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Windows environment.</span></span>  
  
 [<span data-ttu-id="8aac0-115">Utilisation de l'API SOAP dans une application Web</span><span class="sxs-lookup"><span data-stu-id="8aac0-115">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
 <span data-ttu-id="8aac0-116">Décrit comment utiliser l'API SOAP pour intégrer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans un environnement Web.</span><span class="sxs-lookup"><span data-stu-id="8aac0-116">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aac0-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8aac0-117">See Also</span></span>  
 <span data-ttu-id="8aac0-118">[Intégration de Reporting Services dans des applications](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="8aac0-118">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="8aac0-119">[Service web Report Server](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="8aac0-119">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 [<span data-ttu-id="8aac0-120">Création d’applications à l’aide du service web et du .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8aac0-120">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
