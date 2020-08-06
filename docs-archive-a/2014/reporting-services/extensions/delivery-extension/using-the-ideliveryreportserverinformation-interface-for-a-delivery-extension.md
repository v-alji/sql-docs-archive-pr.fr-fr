---
title: Utilisation de l’interface IDeliveryReportServerInformation pour une extension de remise | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IDeliveryReportServerInformation interface
- delivery extensions [Reporting Services], retrieving report server information
ms.assetid: adbce647-18f3-470c-8114-42f8bcc95dc2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52e137d1a866305ec6435a4940fe98448bce5778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615030"
---
# <a name="using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension"></a><span data-ttu-id="e9bf6-102">Utilisation de l'interface IDeliveryReportServerInformation pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="e9bf6-102">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>
  <span data-ttu-id="e9bf6-103">L'interface <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> expose plusieurs propriétés que vous pouvez utiliser pour extraire des informations relatives à un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e9bf6-103">The <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface exposes several properties that you can use to retrieve information about a report server.</span></span> <span data-ttu-id="e9bf6-104">Vous pouvez utiliser ces informations pour remettre des notifications et des rapports.</span><span class="sxs-lookup"><span data-stu-id="e9bf6-104">You can use this information to deliver notifications and reports.</span></span> <span data-ttu-id="e9bf6-105">Lors de l'implémentation de votre classe d'extension de remise, implémentez la propriété <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> comme étant requise par l'interface <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>.</span><span class="sxs-lookup"><span data-stu-id="e9bf6-105">When implementing your delivery extension class, you implement the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> property as required by the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface.</span></span> <span data-ttu-id="e9bf6-106">La propriété <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> retourne un objet qui implémente l'interface <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation>.</span><span class="sxs-lookup"><span data-stu-id="e9bf6-106">The <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> property returns an object that implements the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface.</span></span> <span data-ttu-id="e9bf6-107">À partir de cet objet, vous pouvez obtenir une liste des extensions de rendu actuellement prises en charge par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e9bf6-107">From this object you can get a list of rendering extensions currently supported by the report server.</span></span>  
  
 <span data-ttu-id="e9bf6-108">La `for` boucle suivante peut être utilisée pour stocker une liste d’extensions de rendu actuellement disponibles sur le serveur de rapports dans un objet **ArrayList** .</span><span class="sxs-lookup"><span data-stu-id="e9bf6-108">The following `for` loop could be used to store a list of rendering extensions currently available on the report server in an **ArrayList** object.</span></span>  
  
```vb  
Dim renderFormats As New ArrayList()  
Dim e As Microsoft.ReportingServices.Interfaces.Extension  
For Each e In  ReportServerInformation.RenderingExtension  
   If e.Visible Then  
      renderFormats.Add(e.Name)  
   End If  
Next e  
```  
  
```csharp  
ArrayList renderFormats = new ArrayList();  
foreach (Microsoft.ReportingServices.Interfaces.Extension e in ReportServerInformation.RenderingExtension)  
{   
   if (e.Visible)  
   {  
      renderFormats.Add(e.Name);  
   }  
}  
```  
  
 <span data-ttu-id="e9bf6-109">Pour plus d’informations sur l’interface <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation>, consultez [Utilisation de l’interface IDeliveryReportServerInformation pour une extension de remise](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="e9bf6-109">For more information about the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface, see [Using the IDeliveryReportServerInformation Interface for a Delivery Extension](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9bf6-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9bf6-110">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="e9bf6-111">[Implémentation d’une extension de remise](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="e9bf6-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="e9bf6-112">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e9bf6-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
