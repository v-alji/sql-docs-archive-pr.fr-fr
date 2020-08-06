---
title: Appel des méthodes de service web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Web service [Reporting Services], calls
- calling Web service
- Report Server Web service, SOAP
- XML Web service [Reporting Services], calls
- Report Server Web service, calls
- XML Web service [Reporting Services], SOAP
- SOAP [Reporting Services], calls
ms.assetid: f6f0c6e3-8bb5-4c44-9d19-1872edc72746
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 87f1485b4e3c0ed064e42bb3b411fece96eba8d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697503"
---
# <a name="calling-web-service-methods"></a><span data-ttu-id="da660-102">Appel des méthodes de service Web</span><span class="sxs-lookup"><span data-stu-id="da660-102">Calling Web Service Methods</span></span>
  <span data-ttu-id="da660-103">Quand vous utilisez une [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] classe proxy pour appeler des opérations de service Web, vous utilisez les méthodes de cette classe.</span><span class="sxs-lookup"><span data-stu-id="da660-103">When you use a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class to call Web service operations, you do so by using the methods of that class.</span></span> <span data-ttu-id="da660-104">Ces méthodes répondent comme toute autre méthode de classe incluse dans la bibliothèque de classes [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da660-104">These methods respond like any other method of a class in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="da660-105">Toutes les méthodes de service Web disposent d'un accès public et requièrent que vous fournissiez le nombre approprié d'arguments et de types d'arguments.</span><span class="sxs-lookup"><span data-stu-id="da660-105">All Web service methods have public access and require you to supply the appropriate number of arguments and argument types.</span></span> <span data-ttu-id="da660-106">Après avoir créé une instance de la classe proxy dans votre projet, vous pouvez appeler les méthodes pour effectuer des opérations de création de rapports via le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="da660-106">After you have created an instance of the proxy class in your project, you can call the methods to perform reporting operations via the report server.</span></span> <span data-ttu-id="da660-107">Le code C# suivant illustre l’utilisation de la méthode <xref:ReportService2010.ReportingService2010.ListChildren%2A> de la classe proxy <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="da660-107">The following C# code illustrates the use of the <xref:ReportService2010.ReportingService2010.ListChildren%2A> method of the <xref:ReportService2010.ReportingService2010> proxy class.</span></span> <span data-ttu-id="da660-108">Le code est utilisé pour effectuer un appel récurrent du service Web qui renvoie un tableau d'objets <xref:ReportService2010.CatalogItem> qui contient la liste de tous les éléments contenus dans la base de données du serveur de rapports :</span><span class="sxs-lookup"><span data-stu-id="da660-108">The code is used to make a recursive call to the Web service that returns an array of <xref:ReportService2010.CatalogItem> objects that contains a list of all items in the report server database:</span></span>  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
Dim items As CatalogItem() = rs.ListChildren("/", True)  
```  
  
```csharp  
ReportingService2010 rs = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
CatalogItem[] items = rs.ListChildren("/", true);  
```  
  
## <a name="see-also"></a><span data-ttu-id="da660-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da660-109">See Also</span></span>  
 <span data-ttu-id="da660-110">[Création d’applications à l’aide du service web et du .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="da660-110">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="da660-111">[Service web Report Server](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="da660-111">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="da660-112">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="da660-112">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
