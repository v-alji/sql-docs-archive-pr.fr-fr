---
title: HelpLink, élément | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- HelpLink element
- SoapException class
ms.assetid: a4489103-a874-44c2-8f75-95cb238928ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 97d87e11174ae2b628b760f707ec2b1db49f9e75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697512"
---
# <a name="helplink-element"></a>Élément HelpLink
  L’élément **HelpLink** de la propriété **Detail** est une chaîne d’URL générée par le serveur de rapports. L'URL cible une page Web gérée par le centre d'Aide et de support [!INCLUDE[msCoName](../../../includes/msconame-md.md)] et fournit une aide et des articles de base de connaissances supplémentaires sur les erreurs spécifiques qui se produisent dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]. La syntaxe de l'URL est la suivante :  
  
 **http://** www.Microsoft.com **/** Products **/** EE **/** Transform. aspx **? Valeur EvtSrc** = _value_ **&valeur EvtID** = _value_ **&** = _value_ **&valeur ProdVer** = _value_  
  
 Le tableau suivant répertorie les arguments de l’URL **HelpLink**.  
  
|Argument|Valeur|  
|--------------|-----------|  
|**EvtSrc**|"Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings"|  
|**EvtID**|Par exemple, rsReservedItem est le code d'erreur du serveur de rapports.|  
|**ProdName**|"Microsoft SQL%20Server%20Reporting%20Services." La valeur du nom de produit est encodée dans l'URL.|  
|**ProdVer**|Numéro de version de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]. La valeur « 8,00 » indique [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .|  
  
 L’exemple suivant illustre l’URL **HelpLink** retournée pour le code d’erreur `rsReservedItem` . Cette erreur se produit lorsqu'un utilisateur essaie de modifier ou supprimer un élément réservé dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] :  
  
```  
https://www.microsoft.com/products/ee/transform.aspx?  
EvtSrc=Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings  
&EvtID=rsReservedItem&ProdName=Microsoft%20SQL%20Server%20Reporting%20Services&ProdVer=8.00  
```  
  
 Vous pouvez accéder à l’élément **HelpLink** dans votre code à l’aide de la classe **SoapException**.  
  
```vb  
Try  
   rs.DeleteItem("/Report1")  
  
Catch e As SoapException  
   Console.WriteLine(e.Detail("HelpLink").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   rs.DeleteItem("/Report1");  
}  
  
catch (SoapException e)  
{  
   Console.WriteLine(e.Detail["HelpLink"].InnerXml);  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Présentation de la gestion des exceptions dans Reporting Services](../introducing-exception-handling-in-reporting-services.md)   
 [Reporting Services SoapException (classe)](reporting-services-soapexception-class.md)   
 [Utilisation de la propriété Detail pour gérer des erreurs spécifiques](../best-practices/using-the-detail-property-to-handle-specific-errors.md)  
  
  
