---
title: Accès à l’API SOAP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- XML Web service [Reporting Services], WSDL
- Web service [Reporting Services], SOAP
- calling Web service
- SOAP [Reporting Services], accessing
- Report Server Web service, SOAP
- Web service [Reporting Services], WSDL
- WSDL [Reporting Services]
- XML Web service [Reporting Services], SOAP
- Report Server Web service, WSDL
- referencing WSDL
ms.assetid: 63bb870a-4dbf-46bd-8921-78f8ebe5fd75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e8a0c21bb53deff746cfd916b6ae2c96fa0de19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613288"
---
# <a name="accessing-the-soap-api"></a><span data-ttu-id="32037-102">Accès à l'API  SOAP</span><span class="sxs-lookup"><span data-stu-id="32037-102">Accessing the SOAP API</span></span>
  <span data-ttu-id="32037-103">Le service Web Report Server utilise le protocole SOAP (Simple Object Access Protocol) sur HTTP et joue le rôle d'interface de communication entre les programmes clients et le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="32037-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) over HTTP and acts as a communications interface between client programs and the report server.</span></span> <span data-ttu-id="32037-104">Le service Web fournit deux points de terminaison ; un pour l'exécution des rapports et un autre pour la gestion des rapports. Par ailleurs, il se compose de méthodes et d'un jeu d'objets de type complexe que vous pouvez utiliser pour accéder aux fonctionnalités complètes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32037-104">The Web service provides two endpoints - one for report execution and one for report management - and consists of methods and a set of complex type objects that you can use to access the complete functionality of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="32037-105">Pour appeler le service, vous devez référencer WSDL (Web Services Description Language) Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="32037-105">To call the service, you must reference the Reporting Services Web Services Description Language (WSDL).</span></span>  
  
## <a name="referencing-the-reporting-services-wsdl"></a><span data-ttu-id="32037-106">Référencement deWSDL Reporting Services</span><span class="sxs-lookup"><span data-stu-id="32037-106">Referencing the Reporting Services WSDL</span></span>  
 <span data-ttu-id="32037-107">Pour parvenir à appeler un service Web, vous devez savoir comment accéder à ce service, quelles opérations sont prises en charge, quels paramètres sont attendus et ce que ce service retourne.</span><span class="sxs-lookup"><span data-stu-id="32037-107">To call a Web service successfully, you must know how to access the service, what operations the service supports, what parameters the service expects, and what the service returns.</span></span> <span data-ttu-id="32037-108">WSDL fournit ces informations dans un document XML qui peut être lu ou traité par un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="32037-108">WSDL provides this information in an XML document that can be read or processed by a computer.</span></span>  
  
 <span data-ttu-id="32037-109">Les services Web Report Server sont exposés dans trois points de terminaison différents.</span><span class="sxs-lookup"><span data-stu-id="32037-109">The Report Server Web services are exposed in three different endpoints.</span></span> <span data-ttu-id="32037-110">Le nom du fichier WSDL est différent pour chaque point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="32037-110">The name of the WSDL file is different for each endpoint.</span></span> <span data-ttu-id="32037-111">Le point de terminaison <xref:ReportService2010> contient des méthodes pour gérer des objets dans un serveur de rapports en mode natif ou intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="32037-111">The <xref:ReportService2010> endpoint contains methods for managing objects in a Report Server in either native or SharePoint integrated mode.</span></span> <span data-ttu-id="32037-112">L'accès au fichier WSDL de ce point de terminaison est réalisé à travers `ReportService2010.asmx?wsdl.`.</span><span class="sxs-lookup"><span data-stu-id="32037-112">The WSDL for this endpoint is accessed through `ReportService2010.asmx?wsdl.`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32037-113">Les points de terminaison <xref:ReportService2005> et <xref:ReportService2006> sont déconseillés dans [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32037-113">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="32037-114">Le point de terminaison <xref:ReportService2010> inclut les fonctionnalités des deux points de terminaison, ainsi que des fonctionnalités de gestion supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="32037-114">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
-   <span data-ttu-id="32037-115">Le point de terminaison <xref:ReportExecution2005> permet aux développeurs de traiter les rapports par programme et d'en effectuer le rendu sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="32037-115">The <xref:ReportExecution2005> endpoint allows developers to programmatically process and render reports in a Report Server.</span></span> <span data-ttu-id="32037-116">L’accès au WSDL de ce point de terminaison s’effectue à l’aide de `ReportExecution2005.asmx?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="32037-116">The WSDL for this endpoint is accessed through `ReportExecution2005.asmx?wsdl`.</span></span>  
  
 <span data-ttu-id="32037-117">WSDL peut être utilisé par les kits de développement qui prennent en charge SOAP et les services Web, tels que le kit de développement [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] logiciel (SDK).</span><span class="sxs-lookup"><span data-stu-id="32037-117">WSDL can be consumed by development kits that support SOAP and Web services, such as the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="32037-118">L'exemple suivant montre le format de l'URL au fichier WSDL de gestion [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32037-118">The following example shows the format of the URL to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] management WSDL file:</span></span>  
  
```  
http://server/reportserver/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="32037-119">Le tableau suivant décrit chaque élément de l'URL.</span><span class="sxs-lookup"><span data-stu-id="32037-119">The following table describes each element in the URL.</span></span>  
  
|<span data-ttu-id="32037-120">Élément de l'URL</span><span class="sxs-lookup"><span data-stu-id="32037-120">URL element</span></span>|<span data-ttu-id="32037-121">Description</span><span class="sxs-lookup"><span data-stu-id="32037-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="32037-122">*server*</span><span class="sxs-lookup"><span data-stu-id="32037-122">*server*</span></span>|<span data-ttu-id="32037-123">Nom du serveur sur lequel le serveur de rapports est déployé.</span><span class="sxs-lookup"><span data-stu-id="32037-123">The name of the server on which the report server is deployed.</span></span>|  
|<span data-ttu-id="32037-124">*ReportServer*</span><span class="sxs-lookup"><span data-stu-id="32037-124">*reportserver*</span></span>|<span data-ttu-id="32037-125">Nom du dossier qui contient le service Web XML.</span><span class="sxs-lookup"><span data-stu-id="32037-125">The name of the folder that contains the XML Web service.</span></span> <span data-ttu-id="32037-126">Cet élément est configuré au moment de l'installation.</span><span class="sxs-lookup"><span data-stu-id="32037-126">This is configured during setup.</span></span>|  
|<span data-ttu-id="32037-127">*\<endpoint name>. asmx*</span><span class="sxs-lookup"><span data-stu-id="32037-127">*\<endpoint name>.asmx*</span></span>|<span data-ttu-id="32037-128">Nom du point de terminaison du service Web.</span><span class="sxs-lookup"><span data-stu-id="32037-128">The name of the web service endpoint.</span></span>|  
  
 <span data-ttu-id="32037-129">Pour plus d'informations sur le format WSDL, consultez la spécification WSDL du W3C (World Wide Consortium) à l'adresse http://www.w3.org/TR/wsdl.</span><span class="sxs-lookup"><span data-stu-id="32037-129">For more information about the WSDL format, see the World Wide Web Consortium (W3C) WSDL specification at http://www.w3.org/TR/wsdl.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32037-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32037-130">See Also</span></span>  
 <span data-ttu-id="32037-131">[Création d’applications à l’aide du service web et du .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="32037-131">[Building Applications Using the Web Service and the .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="32037-132">Service Web des serveurs de rapports</span><span class="sxs-lookup"><span data-stu-id="32037-132">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
