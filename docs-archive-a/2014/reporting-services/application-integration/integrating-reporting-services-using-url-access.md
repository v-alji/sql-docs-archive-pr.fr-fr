---
title: Intégration de Reporting Services à l’aide de l’accès URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- URL access [Reporting Services], about URL access
- integrating reports [Reporting Services]
ms.assetid: f1014f7d-fafa-4aa8-8bd2-5bdba835d9b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fedf4ce3011d9caae9d673acf354265537115057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703956"
---
# <a name="integrating-reporting-services-using-url-access"></a><span data-ttu-id="95327-102">Intégration de Reporting Services à l'aide de l'accès URL</span><span class="sxs-lookup"><span data-stu-id="95327-102">Integrating Reporting Services Using URL Access</span></span>
  <span data-ttu-id="95327-103">Avec l'accès URL, vous accédez aux rapports via l'URL d'un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="95327-103">With URL access, you access reports through a report server URL.</span></span> <span data-ttu-id="95327-104">Une demande d'URL vous permet d'accéder à un serveur de rapports spécifique ainsi qu'aux rapports, ressources et autres éléments inclus dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="95327-104">A URL request enables you to access a specific report server as well as the reports, resources, and other items in the report server database.</span></span> <span data-ttu-id="95327-105">Vous pouvez également personnaliser la consultation des rapports et la navigation pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="95327-105">You can also customize the report viewing and navigation experience for your users.</span></span> <span data-ttu-id="95327-106">La chaîne de requête de l'URL contient des paramètres d'informations de périphérique, ainsi que des paramètres de rapport ciblés sur votre rapport et la sortie de rendu choisie.</span><span class="sxs-lookup"><span data-stu-id="95327-106">The query string of the URL contains device information settings, as well as report parameters targeted at your report and the chosen rendering output.</span></span> <span data-ttu-id="95327-107">La façon dont le serveur de rapports gère les demandes d'URL dépend des paramètres, des préfixes de paramètres et du type d'élément auquel vous accédez via l'URL.</span><span class="sxs-lookup"><span data-stu-id="95327-107">The way the report server handles URL requests depends on the parameters, parameter prefixes, and type of item that you are accessing through the URL.</span></span>  
  
 <span data-ttu-id="95327-108">Vous pouvez utiliser l'accès URL pour incorporer des liens hypertexte dans des rapports et d'autres éléments de serveur de rapports dans les applications que vous développez, qu'il s'agisse d'un environnement Windows ou Web.</span><span class="sxs-lookup"><span data-stu-id="95327-108">You can use URL access to embed hyperlinks to reports and other report server items in the applications that you develop, whether in a Windows or Web environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95327-109">Les rubriques de cette section vous fournissent quelques idées de base pour l'intégration.</span><span class="sxs-lookup"><span data-stu-id="95327-109">The topics in the section provide you with some basic ideas for integration.</span></span> <span data-ttu-id="95327-110">Vous pouvez utiliser ces informations pour commencer à concevoir et développer vos propres scénarios d'intégration [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95327-110">You can use the information to begin to design and develop your own [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] integration scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95327-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="95327-111">In This Section</span></span>  
 [<span data-ttu-id="95327-112">Utilisation de l'accès URL dans une application Web</span><span class="sxs-lookup"><span data-stu-id="95327-112">Using URL Access in a Web Application</span></span>](integrating-reporting-services-using-url-access-web-application.md)  
 <span data-ttu-id="95327-113">Décrit comment utiliser l'accès URL pour intégrer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans un environnement Web.</span><span class="sxs-lookup"><span data-stu-id="95327-113">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
 [<span data-ttu-id="95327-114">Utilisation de l'accès URL dans une application Windows</span><span class="sxs-lookup"><span data-stu-id="95327-114">Using URL Access in a Windows Application</span></span>](integrating-reporting-services-using-url-access-windows-application.md)  
 <span data-ttu-id="95327-115">Décrit comment utiliser l'accès URL pour intégrer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans un environnement [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32.</span><span class="sxs-lookup"><span data-stu-id="95327-115">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95327-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95327-116">See Also</span></span>  
 <span data-ttu-id="95327-117">[Intégration de Reporting Services dans des applications](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="95327-117">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="95327-118">Accès URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="95327-118">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
