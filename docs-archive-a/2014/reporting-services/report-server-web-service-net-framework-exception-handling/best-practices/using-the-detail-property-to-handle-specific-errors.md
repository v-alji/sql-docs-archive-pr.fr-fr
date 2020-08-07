---
title: Utilisation de la propriété Detail pour gérer des erreurs spécifiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], Detail property
- Detail property
- InnerText property
ms.assetid: 4392633d-b46b-41e6-bc12-efb64e166704
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f8ac62dc381d8f665a44fc0897ba1f4215aa8e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703832"
---
# <a name="using-the-detail-property-to-handle-specific-errors"></a><span data-ttu-id="3ef46-102">Utilisation de la propriété Detail pour gérer des erreurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="3ef46-102">Using the Detail Property to Handle Specific Errors</span></span>
  <span data-ttu-id="3ef46-103">Pour mieux classifier les exceptions, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] retourne des informations supplémentaires sur l’erreur dans la propriété**InnerText** des éléments enfants dans la propriété **Detail** de l’exception SOAP.</span><span class="sxs-lookup"><span data-stu-id="3ef46-103">To further classify exceptions, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] returns additional error information in the **InnerText** property of the child elements in the SOAP exception's **Detail** property.</span></span> <span data-ttu-id="3ef46-104">Dans la mesure où la propriété **Detail** est un objet **XmlNode**, vous pouvez accéder au texte interne de l’élément enfant **Message** à l’aide du code indiqué ci-après.</span><span class="sxs-lookup"><span data-stu-id="3ef46-104">Because the **Detail** property is an **XmlNode** object, you can access the inner text of the **Message** child element using the following code.</span></span>  
  
 <span data-ttu-id="3ef46-105">Pour obtenir la liste de tous les éléments enfants disponibles dans la propriété **Detail**, consultez [Detail, propriété](../soapexception-class/detail-property.md).</span><span class="sxs-lookup"><span data-stu-id="3ef46-105">For a list of all of the available child elements contained in the **Detail** property, see [Detail Property](../soapexception-class/detail-property.md).</span></span> <span data-ttu-id="3ef46-106">Pour plus d’informations, consultez « Detail Property » dans la [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentation du kit de développement logiciel (SDK).</span><span class="sxs-lookup"><span data-stu-id="3ef46-106">For more information, see "Detail Property" in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   ' The exception is a SOAP exception, so use  
   ' the Detail property's Message element.  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   // The exception is a SOAP exception, so use  
   // the Detail property's Message element.  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   If ex.Detail("ErrorCode").InnerXml = "rsInvalidItemName" Then  
   End If ' Perform an action based on the specific error code  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   if (ex.Detail["ErrorCode"].InnerXml == "rsInvalidItemName")  
   {  
      // Perform an action based on the specific error code  
   }  
}  
```  
  
 <span data-ttu-id="3ef46-107">La ligne de code suivante écrit le code d'erreur spécifique qui est retourné dans l'exception SOAP sur la console.</span><span class="sxs-lookup"><span data-stu-id="3ef46-107">The following line of code writes the specific error code being returned in the SOAP Exception to the console.</span></span> <span data-ttu-id="3ef46-108">Vous pouvez également évaluer le code d'erreur et effectuer des actions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3ef46-108">You could also evaluate the error code and perform specific actions.</span></span>  
  
```vb  
Console.WriteLine(ex.Detail("ErrorCode").InnerXml)  
```  
  
```csharp  
Console.WriteLine(ex.Detail["ErrorCode"].InnerXml);  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ef46-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3ef46-109">See Also</span></span>  
 <span data-ttu-id="3ef46-110">[Présentation de la gestion des exceptions dans Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="3ef46-110">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="3ef46-111">[Reporting Services SoapException (classe)](../soapexception-class/reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="3ef46-111">[Reporting Services SoapException Class](../soapexception-class/reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="3ef46-112">Table d'erreurs SoapException</span><span class="sxs-lookup"><span data-stu-id="3ef46-112">SoapException Errors Table</span></span>](../soapexception-class/soapexception-errors-table.md)  
  
  
