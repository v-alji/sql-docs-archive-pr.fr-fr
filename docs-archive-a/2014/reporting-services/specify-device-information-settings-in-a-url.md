---
title: Spécifier les paramètres d’informations des périphériques dans une URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], URLs
- URL access [Reporting Services], device information settings
ms.assetid: cb7f7577-c6a8-4e6f-8e60-5ec0760f29c3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00cd1fdc3b5fbe129ae4d51b220a11bc48b4744c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703771"
---
# <a name="specify-device-information-settings-in-a-url"></a><span data-ttu-id="01995-102">Spécifier les paramètres d'informations de périphérique dans une URL</span><span class="sxs-lookup"><span data-stu-id="01995-102">Specify Device Information Settings in a URL</span></span>
  <span data-ttu-id="01995-103">Les paramètres d'informations de périphérique sont des paramètres qui sont transmis à une extension de rendu.</span><span class="sxs-lookup"><span data-stu-id="01995-103">Device information settings are parameters that are passed to a rendering extension.</span></span> <span data-ttu-id="01995-104">Si vous utilisez les méthodes du service Web Report Server [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour effectuer le rendu d'un rapport, un élément XML `DeviceInfo` est transmis en tant que paramètre d'entrée.</span><span class="sxs-lookup"><span data-stu-id="01995-104">If you use the methods of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service to render a report, a `DeviceInfo` XML element is passed as an input parameter.</span></span> <span data-ttu-id="01995-105">Les éléments enfants de l'élément `DeviceInfo` sont spécifiques aux paramètres d'informations de périphérique de différentes extensions de rendu.</span><span class="sxs-lookup"><span data-stu-id="01995-105">Child elements of the `DeviceInfo` element are specific to the device information settings of different rendering extensions.</span></span> <span data-ttu-id="01995-106">Vous pouvez inclure des paramètres d’informations de périphérique dans une URL en utilisant la chaîne de paramètre *rc:tag=value* , où *tag* est le nom de l’élément des paramètres d’informations de périphérique en cours d’accès.</span><span class="sxs-lookup"><span data-stu-id="01995-106">You can include device information settings in a URL by using the *rc:tag=value* parameter string, where *tag* is the name of the device information settings element being accessed.</span></span> <span data-ttu-id="01995-107">Pour plus d’informations sur les paramètres d’informations de périphérique dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], consultez [Transmission de paramètres d’informations de périphérique aux extensions de rendu](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="01995-107">For more information about device information settings in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01995-108">Exemple</span><span class="sxs-lookup"><span data-stu-id="01995-108">Example</span></span>  
 <span data-ttu-id="01995-109">L’exemple suivant définit le format du rapport spécifié sur JPEG en utilisant le paramètre d’informations de périphérique *OutputFormat* de l’extension de rendu d’image (les sauts de ligne ont été ajoutés pour la lisibilité) :</span><span class="sxs-lookup"><span data-stu-id="01995-109">The following example sets the format of the specified report to JPEG by using the *OutputFormat* device information setting of the image rendering extension (the line breaks have been added for legibility):</span></span>  
  
```  
http://servername/reportserver?/SampleReports  
/Employee Sales Summary&EmployeeID=38&rs:  
Command=Render&rs:Format=IMAGE&rc:OutputFormat=JPEG  
```  
  
## <a name="see-also"></a><span data-ttu-id="01995-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01995-110">See Also</span></span>  
 <span data-ttu-id="01995-111">[Accès URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="01995-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="01995-112">Référence de paramètres d'accès URL</span><span class="sxs-lookup"><span data-stu-id="01995-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
