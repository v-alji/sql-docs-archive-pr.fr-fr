---
title: Utilisation de la classe Rapport pour une extension de remise | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], report information
- Report class
ms.assetid: 1145ac63-eafd-452a-82af-16f85b1676dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a3f750c2383253636db255cbe9f1ce0ee676a9d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615026"
---
# <a name="using-the-report-class-for-a-delivery-extension"></a><span data-ttu-id="8d6f7-102">Utilisation de la classe Report pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="8d6f7-102">Using the Report Class for a Delivery Extension</span></span>
  <span data-ttu-id="8d6f7-103">La classe <xref:Microsoft.ReportingServices.Interfaces.Report> représente un rapport dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-103">The <xref:Microsoft.ReportingServices.Interfaces.Report> class represents a report in the report server database.</span></span> <span data-ttu-id="8d6f7-104">Tout abonnement est associé à un rapport spécifique.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-104">Any subscription is associated with a specific report.</span></span> <span data-ttu-id="8d6f7-105">Le rapport est contenu dans la notification.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-105">The report is contained in the notification.</span></span> <span data-ttu-id="8d6f7-106">Votre extension de remise peut utiliser l'objet <xref:Microsoft.ReportingServices.Interfaces.Report> qui fait partie de la notification pour effectuer le rendu du rapport.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-106">Your delivery extension can use the <xref:Microsoft.ReportingServices.Interfaces.Report> object that is part of the notification to render the report.</span></span> <span data-ttu-id="8d6f7-107">L'objet <xref:Microsoft.ReportingServices.Interfaces.Report> contient également des propriétés spécifiques au rapport, telles que l'URL au rapport sur le serveur de rapports et le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-107">The <xref:Microsoft.ReportingServices.Interfaces.Report> object also contains report-specific properties, such as the URL to the report on the report server and the name of the report.</span></span> <span data-ttu-id="8d6f7-108">Toutes ces propriétés peuvent être utilisées dans le cadre de votre fournisseur de remise.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-108">These properties can all be used as part of your delivery provider.</span></span>  
  
 <span data-ttu-id="8d6f7-109">La méthode <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> de la classe <xref:Microsoft.ReportingServices.Interfaces.Report> peut être utilisée pour effectuer le rendu d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-109">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the <xref:Microsoft.ReportingServices.Interfaces.Report> class can be used to render a report.</span></span> <span data-ttu-id="8d6f7-110">La méthode <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> retourne un tableau d'un ou plusieurs objets <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> qui constituent un rapport rendu unique.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-110">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together comprise a single rendered report.</span></span> <span data-ttu-id="8d6f7-111">Le premier objet <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> est le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-111">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="8d6f7-112">Les autres objets <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> sont des ressources qui doivent être remises avec les données du rapport (par exemple, un fichier HTML et les images associées).</span><span class="sxs-lookup"><span data-stu-id="8d6f7-112">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="8d6f7-113">Les extensions de rendu qui sont des extensions de rendu de flux unique (IMAGE, PDF, MHTML et Excel) retournent un seul objet <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-113">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and Excel) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="8d6f7-114">L'objet <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>, qui contient le flux du rapport, peut être inclus dans le cadre d'une remise.</span><span class="sxs-lookup"><span data-stu-id="8d6f7-114">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object, which contains the report stream, can be included as part of a delivery.</span></span>  
  
 <span data-ttu-id="8d6f7-115">Pour un exemple d’utilisation de la classe <xref:Microsoft.ReportingServices.Interfaces.Report>, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="8d6f7-115">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Report> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d6f7-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d6f7-116">See Also</span></span>  
 <span data-ttu-id="8d6f7-117">[Implémentation d’une extension de remise](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="8d6f7-117">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 <span data-ttu-id="8d6f7-118">[Bibliothèque d’extensions Reporting Services](../reporting-services-extension-library.md) </span><span class="sxs-lookup"><span data-stu-id="8d6f7-118">[Reporting Services Extension Library](../reporting-services-extension-library.md) </span></span>  
 [<span data-ttu-id="8d6f7-119">Utilisation de la classe RenderedOutputFile pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="8d6f7-119">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
  
  
