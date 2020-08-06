---
title: Gestion des avertissements et des erreurs qui ne lèvent pas d’exceptions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], warnings that don't cause
- warnings [Reporting Services]
ms.assetid: 475c0713-6265-44e7-9ebc-ebdd1b89e0af
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 88d3daf63cf5f04975a2941d0634f357ce81456c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702395"
---
# <a name="handling-warnings-and-cases-that-do-not-cause-exceptions"></a><span data-ttu-id="6d050-102">Gestion des avertissements et des erreurs qui ne lèvent pas d'exceptions</span><span class="sxs-lookup"><span data-stu-id="6d050-102">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="6d050-103">ne lève pas d'exceptions pour les avertissements et certaines erreurs.</span><span class="sxs-lookup"><span data-stu-id="6d050-103">does not throw exceptions for warnings and certain errors.</span></span> <span data-ttu-id="6d050-104">Par exemple, lorsque vous utilisez la méthode <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> pour publier un nouveau rapport sur un serveur de rapports, tous les avertissements qui se produisent sont retournés sous la forme d'un tableau d'objets <xref:ReportService2010.Warning>.</span><span class="sxs-lookup"><span data-stu-id="6d050-104">For example, when you use the <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> method to publish a new report to a report server, any warnings that occur are returned as an array of <xref:ReportService2010.Warning> objects.</span></span> <span data-ttu-id="6d050-105">Ces avertissements doivent être gérés et affichés afin que les mesures appropriées puisse être prises.</span><span class="sxs-lookup"><span data-stu-id="6d050-105">These warnings should be handled and displayed so that appropriate action can be taken.</span></span>  
  
```vb  
Try  
   rs.CreateCatalogItem(name, parentFolder, False, definition, Nothing, warnings)  
  
   If Not (warnings.Length = 0) Then  
      Dim warning As Warning  
      For Each warning In warnings  
         Console.WriteLine(warning.Message)  
      Next warning  
   Else  
      Console.WriteLine("Report {0} created successfully with no warnings", name)  
   End If  
  
Catch ex As SoapException  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   rs.CreateCatalogItem("Report", name, parentFolder, false, definition, null, out warnings);  
  
   if (warnings.Length != 0)  
   {  
      foreach (Warning warning in warnings)  
      {  
         Console.WriteLine(warning.Message);  
      }  
   }  
   else  
      Console.WriteLine("Report {0} created successfully with no warnings", name);  
}  
  
catch (SoapException ex)  
{  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
 <span data-ttu-id="6d050-106">Les erreurs peuvent également être gérées en évaluant les valeurs de retour de certaines méthodes.</span><span class="sxs-lookup"><span data-stu-id="6d050-106">Another way to handle errors is to evaluate the return values of certain methods.</span></span> <span data-ttu-id="6d050-107">Par exemple, la méthode <xref:ReportService2010.ReportingService2010.FindItems%2A> peut être utilisée pour rechercher des éléments spécifiques dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="6d050-107">For example, the <xref:ReportService2010.ReportingService2010.FindItems%2A> method can be used to search for specific items in the report server database.</span></span> <span data-ttu-id="6d050-108">Si aucun élément correspondant aux critères de recherche n'est trouvé, un tableau null d'objets <xref:ReportService2010.CatalogItem> est retourné.</span><span class="sxs-lookup"><span data-stu-id="6d050-108">If no items are found that match the search criteria, a null array of <xref:ReportService2010.CatalogItem> objects is returned.</span></span> <span data-ttu-id="6d050-109">Vous devez évaluer le tableau, vérifier la présence d'éléments `null` et informer l'utilisateur si aucun élément n'a été trouvé.</span><span class="sxs-lookup"><span data-stu-id="6d050-109">You should evaluate the array, check for `null`, and let the user know if no items were found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d050-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d050-110">See Also</span></span>  
 <xref:ReportService2010.CatalogItem>   
 <span data-ttu-id="6d050-111">[Présentation de la gestion des exceptions dans Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="6d050-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="6d050-112">Classe SoapException Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6d050-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
