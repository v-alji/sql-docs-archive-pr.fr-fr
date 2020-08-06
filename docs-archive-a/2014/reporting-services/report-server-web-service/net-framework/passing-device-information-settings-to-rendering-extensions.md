---
title: Transmission de paramètres d’informations de périphérique aux extensions de rendu | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- device information settings [Reporting Services]
- Render method
- Report Server Web service, device information settings
- Web service [Reporting Services], device information settings
- XML Web service [Reporting Services], device information settings
- passing device information [Reporting Services]
- rendering extensions [Reporting Services], device information settings
- rendering [Reporting Services], settings
- device information settings [Reporting Services], about device information settings
- extensions [Reporting Services], device information settings
ms.assetid: fe718939-7efe-4c7f-87cb-5f5b09caeff4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea50de3955ab152cbd92d5fd50ef8b2281a67eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697491"
---
# <a name="passing-device-information-settings-to-rendering-extensions"></a><span data-ttu-id="bc70b-102">Transmission de paramètres d'informations de périphérique aux extensions de rendu</span><span class="sxs-lookup"><span data-stu-id="bc70b-102">Passing Device Information Settings to Rendering Extensions</span></span>
  <span data-ttu-id="bc70b-103">Dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], les paramètres d'informations de périphérique sont utilisés pour passer les paramètres de rendu à l'extension de rendu définie.</span><span class="sxs-lookup"><span data-stu-id="bc70b-103">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="bc70b-104">Les paramètres du service Web Report Server sont passés comme élément XML **DeviceInfo** , puis sont traités par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bc70b-104">Settings in the Report Server Web service are passed as a **DeviceInfo** XML element and processed by the report server.</span></span> <span data-ttu-id="bc70b-105">Des valeurs par défaut étant attribuées aux paramètres d'informations de périphérique, ces paramètres sont considérés comme des arguments facultatifs lors du processus de rendu.</span><span class="sxs-lookup"><span data-stu-id="bc70b-105">Because device information settings have default values, they are considered optional arguments in the rendering process.</span></span> <span data-ttu-id="bc70b-106">Toutefois, vous pouvez utiliser ces paramètres afin de personnaliser le rendu et remplacer les valeurs par défaut fournies par le serveur.</span><span class="sxs-lookup"><span data-stu-id="bc70b-106">However, you can use device information settings to customize rendering and to override the default values that are supplied by the server.</span></span>  
  
 <span data-ttu-id="bc70b-107">Les paramètres d'informations de périphérique peuvent être spécifiés de diverses manières.</span><span class="sxs-lookup"><span data-stu-id="bc70b-107">You can specify device information settings in a variety of ways.</span></span> <span data-ttu-id="bc70b-108">Vous pouvez utiliser la méthode Render dans un programme.</span><span class="sxs-lookup"><span data-stu-id="bc70b-108">Programmatically, you can use the Render method.</span></span> <span data-ttu-id="bc70b-109">Si vous accédez à un rapport à l'aide de son URL, vous pouvez spécifier les informations de périphérique sous la forme de paramètres d'URL.</span><span class="sxs-lookup"><span data-stu-id="bc70b-109">If you are accessing a report through its URL, you can specify device information as URL parameters.</span></span> <span data-ttu-id="bc70b-110">Enfin, vous pouvez modifier les paramètres d'informations de périphérique dans les fichiers de configuration [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] et ainsi spécifier les paramètres de rendu de manière globale.</span><span class="sxs-lookup"><span data-stu-id="bc70b-110">You can also edit the device information settings in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files to specify rendering parameters globally.</span></span> <span data-ttu-id="bc70b-111">Pour plus d’informations sur la spécification des paramètres de rendu de manière globale, consultez [Personnaliser les paramètres d’extension de rendu dans RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="bc70b-111">For more information about specifying rendering parameters globally, see [Customize Rendering Extension Parameters in RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md).</span></span>  
  
## <a name="passing-device-information-using-the-render-method"></a><span data-ttu-id="bc70b-112">Passage des informations de périphérique à l'aide de la méthode Render</span><span class="sxs-lookup"><span data-stu-id="bc70b-112">Passing Device Information Using the Render Method</span></span>  
 <span data-ttu-id="bc70b-113">Pour passer des paramètres d'informations de périphérique à l'extension de rendu définie, utilisez la méthode <xref:ReportExecution2005.ReportExecutionService.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc70b-113">To pass device information settings to a rendering extension, use the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="bc70b-114">Par exemple, la chaîne XML suivante peut être passée à la méthode <xref:ReportExecution2005.ReportExecutionService.Render%2A> pour créer un fragment HTML quand le rapport est restitué au format HTML.</span><span class="sxs-lookup"><span data-stu-id="bc70b-114">For example, the following XML string can be passed to the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method to create an HTML fragment when rendering to HTML.</span></span>  
  
```  
<DeviceInfo>  
   <HTMLFragment>True</HTMLFragment>  
</DeviceInfo>  
```  
  
 <span data-ttu-id="bc70b-115">Lorsqu'un rapport est restitué sous la forme d'un fragment HTML, son contenu est placé dans un élément TABLE et aucun élément HTML ou BODY n'est utilisé.</span><span class="sxs-lookup"><span data-stu-id="bc70b-115">When a report is rendered as an HTML fragment, the content of the report is contained within a TABLE element without the use of an HTML or BODY element.</span></span> <span data-ttu-id="bc70b-116">Vous pouvez utiliser ce fragment afin d'intégrer le rapport concerné à un document HTML existant.</span><span class="sxs-lookup"><span data-stu-id="bc70b-116">You can use the HTML fragment to incorporate the report into an existing HTML document.</span></span> <span data-ttu-id="bc70b-117">Pour plus d’informations sur les paramètres d’informations de périphérique utilisés pour le format HTML, consultez [Paramètres d’informations de périphérique HTML](../../html-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="bc70b-117">For more information about device information settings for HTML output, see [HTML Device Information Settings](../../html-device-information-settings.md).</span></span>  
  
## <a name="passing-device-information-using-url-access"></a><span data-ttu-id="bc70b-118">Passage d'informations de périphérique à l'aide d'un accès URL</span><span class="sxs-lookup"><span data-stu-id="bc70b-118">Passing Device Information Using URL Access</span></span>  
 <span data-ttu-id="bc70b-119">Vous pouvez également passer des paramètres d'informations de périphérique en utilisant un accès URL.</span><span class="sxs-lookup"><span data-stu-id="bc70b-119">You can also pass device information settings through URL access.</span></span> <span data-ttu-id="bc70b-120">Les paramètres d'informations de périphérique sont alors passés sous la forme de paramètres d'URL.</span><span class="sxs-lookup"><span data-stu-id="bc70b-120">Device information settings are passed as URL parameters.</span></span> <span data-ttu-id="bc70b-121">La chaîne d'accès URL suivante peut être passée au serveur de rapports pour générer un rapport rendu ne comportant pas de barre d'outils de visionneuse HTML.</span><span class="sxs-lookup"><span data-stu-id="bc70b-121">The following URL access string can be passed to the report server to generate a rendered report without the HTML viewer toolbar.</span></span>  
  
```  
http://<Server Name>/reportserver?/SampleReports/Sales Order Detail&rs:Command=Render&rs:Format=HTML4.0&rc:Toolbar=False  
```  
  
 <span data-ttu-id="bc70b-122">Pour plus d’informations, consultez [Spécifier les paramètres d’informations de périphérique dans une URL](../../specify-device-information-settings-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="bc70b-122">For more information, see [Specify Device Information Settings in a URL](../../specify-device-information-settings-in-a-url.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc70b-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc70b-123">See Also</span></span>  
 <span data-ttu-id="bc70b-124">[Paramètres d’informations de périphérique pour les extensions de rendu &#40;Reporting Services&#41;](../../device-information-settings-for-rendering-extensions-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="bc70b-124">[Device Information Settings for Rendering Extensions &#40;Reporting Services&#41;](../../device-information-settings-for-rendering-extensions-reporting-services.md) </span></span>  
 <span data-ttu-id="bc70b-125">[Personnaliser les paramètres d’extension de rendu dans RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="bc70b-125">[Customize Rendering Extension Parameters in RSReportServer.Config](../../customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="bc70b-126">Création d’applications à l’aide du service web et du .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bc70b-126">Building Applications Using the Web Service and the .NET Framework</span></span>](building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
