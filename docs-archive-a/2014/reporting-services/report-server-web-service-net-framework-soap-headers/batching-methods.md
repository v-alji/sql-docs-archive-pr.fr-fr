---
title: Méthodes de traitement par lot | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- methods [Reporting Services], batches
- BatchHeader SOAP header
- Web service [Reporting Services], methods
- Report Server Web service, batching
- batches [Reporting Services]
- XML Web service [Reporting Services], methods
- locking [Reporting Services]
- multiple Web service methods
ms.assetid: 86435534-c9fe-4b49-b88c-7fb6d21976b0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c778da186fdbbfaed17b9635d9ca7309a369552b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613292"
---
# <a name="batching-methods"></a><span data-ttu-id="796b6-102">Méthodes de traitement par lot</span><span class="sxs-lookup"><span data-stu-id="796b6-102">Batching Methods</span></span>
  <span data-ttu-id="796b6-103">L'utilisation d'en-têtes SOAP dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] vous permet d'inclure plusieurs méthodes Web Service dans une même opération.</span><span class="sxs-lookup"><span data-stu-id="796b6-103">The use of SOAP headers in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enables you to include multiple Web service methods in a single operation.</span></span> <span data-ttu-id="796b6-104">Les méthodes sont exécutées dans la portée d'une transaction de base de données unique, dans l'ordre de leur appel.</span><span class="sxs-lookup"><span data-stu-id="796b6-104">Methods run within the scope of a single database transaction, in the order in which they are called.</span></span>  
  
 <span data-ttu-id="796b6-105">La restauration est un avantage offert par l'utilisation de plusieurs méthodes de traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="796b6-105">Rollback is one advantage of using multiple-method batch operations.</span></span> <span data-ttu-id="796b6-106">En cas d'erreur sur un appel de méthode au cours de l'exécution d'un lot, le serveur de rapports arrête l'exécution du lot et restaure les opérations précédentes.</span><span class="sxs-lookup"><span data-stu-id="796b6-106">If an error occurs on any of the method calls while a batch is running, the report server stops running the batch and rolls back any previous operations.</span></span> <span data-ttu-id="796b6-107">Cette opération est utile lorsqu'un appel de méthode dépend de l'achèvement réussi d'autres appels de méthode dans ce lot.</span><span class="sxs-lookup"><span data-stu-id="796b6-107">This is useful when a method call depends on the successful completion of other method calls in that batch.</span></span>  
  
 <span data-ttu-id="796b6-108">Le service Web ne fournit pas de sémantique de verrouillage pour les traitements par lots de plusieurs méthodes.</span><span class="sxs-lookup"><span data-stu-id="796b6-108">The Web service does not provide locking semantics for multiple-method batch operations.</span></span> <span data-ttu-id="796b6-109">Les lignes dans la base de données du serveur de rapports ne sont pas verrouillées pour la mise à jour tant que le message n'a pas été envoyé au serveur et la commande Execute appelée.</span><span class="sxs-lookup"><span data-stu-id="796b6-109">Rows in the report server database are not locked for updating until the message is sent to the server and the Execute command is called.</span></span>  
  
 <span data-ttu-id="796b6-110">Il n'y a pas non plus de contrôles concurrentiels pour garantir que la base de données n'a pas changé depuis la dernière lecture des données.</span><span class="sxs-lookup"><span data-stu-id="796b6-110">There are also no concurrency controls to guarantee that the database has not changed since the data was last read.</span></span> <span data-ttu-id="796b6-111">Si deux clients modifient le même élément, la dernière mise à jour réussit si les paramètres sont encore valides (par exemple, l'élément n'a pas été renommé).</span><span class="sxs-lookup"><span data-stu-id="796b6-111">If two clients modify the same item, the last update succeeds if the parameters are still valid (for example, the item has not been renamed).</span></span>  
  
 <span data-ttu-id="796b6-112">L'exemple suivant appelle la méthode <xref:ReportService2005.ReportingService2005.CreateFolder%2A> trois fois et exécute ces appels comme un lot unique.</span><span class="sxs-lookup"><span data-stu-id="796b6-112">The following example calls the <xref:ReportService2005.ReportingService2005.CreateFolder%2A> method three times and runs these calls as a single batch.</span></span> <span data-ttu-id="796b6-113">Si un des appels à <xref:ReportService2005.ReportingService2005.CreateFolder%2A> échoue, le lot entier est annulé.</span><span class="sxs-lookup"><span data-stu-id="796b6-113">If any of the calls to <xref:ReportService2005.ReportingService2005.CreateFolder%2A> fail, the entire batch is canceled.</span></span>  
  
```vb  
Imports System  
Imports System.Web.Services.Protocols  
Imports myNamespace.MyReferenceName  
  
Class Sample  
    Sub Main(args() As String)  
        Dim rs As New ReportingService2005()  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
      ' Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        Dim bh As New BatchHeader()  
  
        bh.BatchId = service.CreateBatch()  
        rs.BatchHeaderValue = bh  
        rs.CreateFolder("New Folder1", "/", Nothing)  
        rs.CreateFolder("New Folder2", "/", Nothing)  
        rs.CreateFolder("New Folder3", "/", Nothing)  
  
        Console.WriteLine("Creating folders...")  
        rs.BatchHeaderValue = bh  
        rs.ExecuteBatch()  
        Console.WriteLine("Folders created successfully.")  
  
        rs.BatchHeaderValue = Nothing  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Web.Services.Protocols;   
using myNamespace.MyReferenceName;  
  
class Sample  
{  
    static void Main(string[] args)  
    {  
        ReportingService2005 rs = new ReportingService2005();  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
      // Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        BatchHeader bh = new BatchHeader();  
  
        bh1.BatchID = service.CreateBatch();  
        rs.BatchHeaderValue = bh;  
        rs.CreateFolder("New Folder1", "/", null);  
        rs.CreateFolder("New Folder2", "/", null);  
        rs.CreateFolder("New Folder3", "/", null);  
  
        Console.WriteLine("Creating folders...");  
        rs.BatchHeaderValue = bh1;  
        rs.ExecuteBatch();  
        Console.WriteLine("Folders created successfully.");  
  
        rs.BatchHeaderValue = null;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="796b6-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="796b6-114">See Also</span></span>  
 <xref:ReportService2005.ReportingService2005.CancelBatch%2A>   
 <xref:ReportService2005.ReportingService2005.CreateBatch%2A>   
 <span data-ttu-id="796b6-115">[Référence technique &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="796b6-115">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="796b6-116">Utilisation des en-têtes SOAP de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="796b6-116">Using Reporting Services SOAP Headers</span></span>](using-reporting-services-soap-headers.md)  
  
  
