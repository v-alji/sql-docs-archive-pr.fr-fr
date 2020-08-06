---
title: Points de terminaison du service web Report Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- management endpoints [Reporting Services]
- Web service [Reporting Services], endpoints
- endpoints [Reporting Services]
- execution endpoints [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: f3f5d85f-9359-4508-bc5a-7f78a3cf7421
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70281c5171eb37d9888d663542a7850820c81bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702380"
---
# <a name="report-server-web-service-endpoints"></a><span data-ttu-id="31a8e-102">Points de terminaison du service Web Report Server</span><span class="sxs-lookup"><span data-stu-id="31a8e-102">Report Server Web Service Endpoints</span></span>
  <span data-ttu-id="31a8e-103">Le service Web Report Server fournit plusieurs points de terminaison pour la gestion d’un serveur de rapports aussi bien que l'exécution de rapports et la navigation dans ces derniers.</span><span class="sxs-lookup"><span data-stu-id="31a8e-103">The Report Server Web service provides several endpoints for managing a report server as well as executing and navigating reports.</span></span>  
  
## <a name="the-management-endpoints"></a><span data-ttu-id="31a8e-104">Points de terminaison de gestion</span><span class="sxs-lookup"><span data-stu-id="31a8e-104">The Management Endpoints</span></span>  
 <span data-ttu-id="31a8e-105">Trois points de terminaison sont disponibles pour la gestion des objets sur un serveur de rapports, <xref:ReportService2005>, <xref:ReportService2006> et <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="31a8e-105">There are three endpoints available for managing objects on a report server, <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010>.</span></span> <span data-ttu-id="31a8e-106">Le point de terminaison <xref:ReportService2005> permet de gérer des objets sur un serveur de rapports qui est configuré pour le mode natif.</span><span class="sxs-lookup"><span data-stu-id="31a8e-106">The <xref:ReportService2005> endpoint is used for managing objects on a report server that is configured for native mode.</span></span> <span data-ttu-id="31a8e-107">Le point de terminaison <xref:ReportService2006> permet de gérer des objets sur un serveur de rapports qui est configuré pour le mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31a8e-107">The <xref:ReportService2006> endpoint is used for managing objects on a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="31a8e-108">Le point de terminaison <xref:ReportService2010> fusionne les fonctionnalités de <xref:ReportService2005> et <xref:ReportService2006> et peut gérer des objets sur un serveur de rapports configuré pour le mode natif ou intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31a8e-108">The <xref:ReportService2010> endpoint merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage objects on a report server that are configured for either native or SharePoint integrated mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="31a8e-109">Lorsqu'un serveur de rapports est configuré pour le mode intégré SharePoint, les API <xref:ReportService2005> renvoient une erreur `rsOperationNotSupportedSharePointMode`.</span><span class="sxs-lookup"><span data-stu-id="31a8e-109">When a report server is configured for SharePoint integrated mode, the <xref:ReportService2005> APIs will return an `rsOperationNotSupportedSharePointMode` error.</span></span> <span data-ttu-id="31a8e-110">Si le serveur de rapports est configuré pour le mode natif, les API <xref:ReportService2006> retournent une erreur `rsOperationNotSupportedNativeMode`.</span><span class="sxs-lookup"><span data-stu-id="31a8e-110">If the report server is configured for native mode, the <xref:ReportService2006> APIs will return an `rsOperationNotSupportedNativeMode` error.</span></span> <span data-ttu-id="31a8e-111">De la même façon, lorsque les API spécifiques au mode dans <xref:ReportService2010> sont utilisées sur des modes involontaires, les API retourneront les erreurs correspondantes.</span><span class="sxs-lookup"><span data-stu-id="31a8e-111">Similarly, when mode-specific APIs in <xref:ReportService2010> are used on unintended modes, the APIs will return the respective errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31a8e-112">Les points de terminaison <xref:ReportService2005> et <xref:ReportService2006> sont déconseillés dans [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31a8e-112">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="31a8e-113">Le point de terminaison <xref:ReportService2010> inclut les fonctionnalités des deux points de terminaison, ainsi que des fonctionnalités de gestion supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="31a8e-113">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="31a8e-114">Si le serveur de rapports est configuré pour le mode natif ou intégré SharePoint, le langage WSDL pour le point de terminaison de gestion est accessible à l'aide de l'une des adresses URL suivantes :</span><span class="sxs-lookup"><span data-stu-id="31a8e-114">If the report server is configured for native mode or SharePoint integrate mode, the WSDL for the management endpoint can be accessed using one of the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="31a8e-115">Pour plus d’informations, consultez [Accès à l’API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="31a8e-115">For more information, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="the-execution-endpoint"></a><span data-ttu-id="31a8e-116">Point de terminaison d'exécution</span><span class="sxs-lookup"><span data-stu-id="31a8e-116">The Execution Endpoint</span></span>  
 <span data-ttu-id="31a8e-117">Le point de terminaison <xref:ReportExecution2005> facilite aux développeurs la personnalisation du traitement des rapports et le rendu à partir d'un serveur de rapports dans les modes intégrés natif et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31a8e-117">The <xref:ReportExecution2005> endpoint makes it easy for developers to customize report processing and rendering from a report server in both native and SharePoint integrated modes.</span></span> <span data-ttu-id="31a8e-118">Le point de terminaison inclut des classes et des méthodes qui existaient dans des versions antérieures du service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="31a8e-118">The endpoint includes classes and methods that existed in earlier versions of the Report Server Web service.</span></span> <span data-ttu-id="31a8e-119">En outre, nombre de nouvelles classes et méthodes, exposées par le biais du point de terminaison d'exécution, ont été ajoutées au service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="31a8e-119">In addition, many new classes and methods have been added to the Report Server Web service that are exposed through the execution endpoint.</span></span>  
  
 <span data-ttu-id="31a8e-120">Le langage WSDL pour le point de terminaison de gestion est accessible à l'aide de l'adresse URL suivante :</span><span class="sxs-lookup"><span data-stu-id="31a8e-120">The WSDL for the management endpoint can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="31a8e-121">Si le serveur de rapports est configuré pour le mode intégré SharePoint, le langage WSDL est accessible à l'aide de l'URL suivante :</span><span class="sxs-lookup"><span data-stu-id="31a8e-121">If the report server is configured for SharePoint integrate mode, the WSDL can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="31a8e-122">Pour plus d’informations, consultez [Accès à l’API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="31a8e-122">For more information, please see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="sharepoint-proxy-endpoints"></a><span data-ttu-id="31a8e-123">Points de terminaison de proxy SharePoint</span><span class="sxs-lookup"><span data-stu-id="31a8e-123">SharePoint Proxy Endpoints</span></span>  
 <span data-ttu-id="31a8e-124">Lorsqu'un serveur de rapports est configuré pour le mode intégré SharePoint et que le complément [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] est installé, un jeu de points de terminaison de proxy est installé sur le serveur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31a8e-124">When a report server is configured for SharePoint integrated mode and the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in has been installed, a set of proxy endpoints are installed on the SharePoint server.</span></span> <span data-ttu-id="31a8e-125">Les points de terminaison de proxy constituent l'API primaire pour le développement de solutions de rapport lorsqu'un serveur de rapports est configuré pour le mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31a8e-125">The proxy endpoints are the primary API for developing report solutions when a report server is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="31a8e-126">Lors du développement avec les points de terminaison de proxy, le complément [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] gère l'échange des informations d'identification entre le serveur SharePoint et le serveur de rapports en mode d'authentification Compte approuvé.</span><span class="sxs-lookup"><span data-stu-id="31a8e-126">When developing against the proxy endpoints, the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in manages the exchange of credentials between the SharePoint server and the report server in Trusted account authentication mode.</span></span> <span data-ttu-id="31a8e-127">Lors du développement par rapport aux points de terminaison du serveur de rapports, l'application appelante doit gérer l'échange des informations d'identification en mode d'authentification Compte approuvé.</span><span class="sxs-lookup"><span data-stu-id="31a8e-127">When developing against the report server endpoints, the calling application will have to manage the credential exchange in Trusted account authentication mode.</span></span> <span data-ttu-id="31a8e-128">Le tableau suivant répertorie les points de terminaison installés avec le complément [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31a8e-128">The following table lists the endpoints that are installed with the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
|<span data-ttu-id="31a8e-129">Point de terminaison proxy</span><span class="sxs-lookup"><span data-stu-id="31a8e-129">Proxy Endpoint</span></span>|<span data-ttu-id="31a8e-130">Description</span><span class="sxs-lookup"><span data-stu-id="31a8e-130">Description</span></span>|  
|--------------------|-----------------|  
|<xref:ReportService2006>|<span data-ttu-id="31a8e-131">Fournit les API permettant de gérer un serveur de rapports configuré pour le mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31a8e-131">Provides the APIs for managing a report server that is configured for SharePoint integrate mode.</span></span> <span data-ttu-id="31a8e-132">**Remarque :**  Ce point de terminaison est déconseillé dans [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31a8e-132">**Note:**  This endpoint is deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span>|  
|<xref:ReportService2010>|<span data-ttu-id="31a8e-133">Fournit les API permettant de gérer un serveur de rapports configuré pour le mode natif ou intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31a8e-133">Provides the APIs for managing a report server that is configured for either native or SharePoint integrated mode.</span></span>|  
|<xref:ReportExecution2005>|<span data-ttu-id="31a8e-134">Fournit les API pour l'exécution de rapports et la navigation dans ces derniers.</span><span class="sxs-lookup"><span data-stu-id="31a8e-134">Provides the APIs for running and navigating reports.</span></span>|  
|<xref:ReportServiceAuthentication>|<span data-ttu-id="31a8e-135">Fournit les API pour l'authentification des utilisateurs avec un serveur de rapports lorsque l'application Web SharePoint est configurée pour l'authentification par formulaires.</span><span class="sxs-lookup"><span data-stu-id="31a8e-135">Provides the APIs for authenticating users against a report server when the SharePoint Web application is configured for Forms Authentication.</span></span>|  
  
 <span data-ttu-id="31a8e-136">Voici des exemples d'adresses URL pour le référencement des points de terminaison de proxy sur un site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31a8e-136">The following are example URLs for referencing the proxy endpoints on a SharePoint site.</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportService2010.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportServiceAuthentication.asmx  
```  
  
## <a name="see-also"></a><span data-ttu-id="31a8e-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31a8e-137">See Also</span></span>  
 [<span data-ttu-id="31a8e-138">Création d’applications à l’aide du service web et du .NET Framework</span><span class="sxs-lookup"><span data-stu-id="31a8e-138">Building Applications Using the Web Service and the .NET Framework</span></span>](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
