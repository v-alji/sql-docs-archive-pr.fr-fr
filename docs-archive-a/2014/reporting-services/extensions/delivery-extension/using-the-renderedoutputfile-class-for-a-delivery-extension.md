---
title: Utilisation de la classe RenderedOutputFile pour une extension de remise | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RenderedOutputFile class
- data streams [Reporting Services]
- delivery extensions [Reporting Services], data streams
ms.assetid: 8b591801-42d5-49fa-b710-bf7e6917accf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1dcbf250a367326e5cad528384e533a9ac9d945b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615029"
---
# <a name="using-the-renderedoutputfile-class-for-a-delivery-extension"></a><span data-ttu-id="98bc6-102">Utilisation de la classe RenderedOutputFile pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="98bc6-102">Using the RenderedOutputFile Class for a Delivery Extension</span></span>
  <span data-ttu-id="98bc6-103">La classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> représente un flux de données et des informations relatives aux propriétés associées du flux de données.</span><span class="sxs-lookup"><span data-stu-id="98bc6-103">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class represents a data stream and information about the data stream's associated properties.</span></span> <span data-ttu-id="98bc6-104">La propriété **Data** de la classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> est utilisée pour représenter un rapport rendu ou signaler une ressource en tant qu’objet **Stream**.</span><span class="sxs-lookup"><span data-stu-id="98bc6-104">The **Data** property of the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class is used to represent a rendered report or report resource as a **Stream** object.</span></span>  
  
 <span data-ttu-id="98bc6-105">La méthode <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> de l’objet **Report** retourne un tableau d’un ou plusieurs objets <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> qui constituent un rapport rendu unique.</span><span class="sxs-lookup"><span data-stu-id="98bc6-105">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the **Report** object returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together constitute a single rendered report.</span></span> <span data-ttu-id="98bc6-106">Le premier objet <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> est le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="98bc6-106">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="98bc6-107">Les autres objets <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> sont des ressources qui doivent être remises avec les données du rapport (par exemple, un fichier HTML et les images associées).</span><span class="sxs-lookup"><span data-stu-id="98bc6-107">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="98bc6-108">Les extensions de rendu qui sont des extensions de rendu de flux unique (IMAGE, PDF, MHTML et EXCEL) renvoient un seul objet <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="98bc6-108">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and EXCEL) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="98bc6-109">Pour un exemple d’utilisation de la classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="98bc6-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98bc6-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98bc6-110">See Also</span></span>  
 <span data-ttu-id="98bc6-111">[Implémentation d’une extension de remise](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="98bc6-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="98bc6-112">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="98bc6-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
