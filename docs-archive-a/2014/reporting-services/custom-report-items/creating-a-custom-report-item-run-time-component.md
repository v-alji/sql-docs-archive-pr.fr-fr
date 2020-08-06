---
title: Création d’un composant d’exécution d’éléments de rapport personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: b3e15a4a-98f8-4dbb-b847-bbcb20327051
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 50c5c0211bc5cd1359af9d1493782bd9d96c2b3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600661"
---
# <a name="creating-a-custom-report-item-run-time-component"></a><span data-ttu-id="62b76-102">Création d'un composant d'exécution d'élément de rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="62b76-102">Creating a Custom Report Item Run-Time Component</span></span>
  <span data-ttu-id="62b76-103">Le composant d’exécution d’élément de rapport personnalisé est implémenté en tant que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] composant à l’aide de tout langage conforme CLS et est appelé par le processeur de rapports au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="62b76-103">The custom report item run-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component using any CLS-compliant language, and is called by the report processor at run time.</span></span> <span data-ttu-id="62b76-104">Les propriétés du composant d'exécution sont définies dans l'environnement de conception en modifiant le composant de conception d'élément de rapport personnalisé y correspondant.</span><span class="sxs-lookup"><span data-stu-id="62b76-104">You define the properties for the run-time component in the design environment by modifying the custom report item's corresponding design-time component.</span></span>  

<!--
Replacing the following multiValue.....

ms.technology: 
  - "docset-sql-devref"
  - "reporting-services-native"

.....with the following single value.....

ms.technology: reporting-services
.

(GeneMi = MightyPen  ,  2019-04-20  ,  DevO= 1515083)
-->

 <span data-ttu-id="62b76-105">Pour un exemple d’élément de rapport personnalisé totalement implémenté, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="62b76-105">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="definition-and-instance-objects"></a><span data-ttu-id="62b76-106">Objets d'instance et de définition</span><span class="sxs-lookup"><span data-stu-id="62b76-106">Definition and Instance Objects</span></span>  
 <span data-ttu-id="62b76-107">Avant d’implémenter un élément de rapport personnalisé, il est important de comprendre la différence entre *objets de définition* et *objets d’instance*.</span><span class="sxs-lookup"><span data-stu-id="62b76-107">Before implementing a custom report item it is important to understand the difference between *definition objects* and *instance objects*.</span></span> <span data-ttu-id="62b76-108">Les objets de définition fournissent la représentation RDL de l'élément de rapport personnalisé alors que les objets d'instance sont les versions évaluées des objets de définition.</span><span class="sxs-lookup"><span data-stu-id="62b76-108">Definition objects provide the RDL representation of the custom report item whereas instance objects are the evaluated versions of the definition objects.</span></span> <span data-ttu-id="62b76-109">Il n'existe qu'un seul objet de définition pour chaque élément du rapport.</span><span class="sxs-lookup"><span data-stu-id="62b76-109">There is only one definition object for each item on the report.</span></span> <span data-ttu-id="62b76-110">Lorsque vous accédez aux propriétés d'un objet de définition qui contient des expressions, vous obtenez une chaîne d'expression non-évaluée.</span><span class="sxs-lookup"><span data-stu-id="62b76-110">When accessing properties on a definition object that contain expressions, you will get the unevaluated expression string.</span></span> <span data-ttu-id="62b76-111">Les objets d'instance contiennent les versions évaluées des objets de définition et peuvent avoir une relation un-à-plusieurs avec l'objet de définition d'un élément.</span><span class="sxs-lookup"><span data-stu-id="62b76-111">Instance objects contain the evaluated versions of the definition objects and can have a one-to-many relationship with an item's definition object.</span></span> <span data-ttu-id="62b76-112">Par exemple, lorsque la région de données <xref:Microsoft.ReportingServices.OnDemandReportRendering.Tablix> d'un rapport contient un composant <xref:Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem> dans l'une de ses lignes de détails, un seul objet de définition y correspond. En revanche, plusieurs objets d'instance sont spécifiés, un pour chaque ligne que comporte la région de données.</span><span class="sxs-lookup"><span data-stu-id="62b76-112">For example, if a report has a <xref:Microsoft.ReportingServices.OnDemandReportRendering.Tablix> data region that contains a <xref:Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem> in a detail row, there will be only one definition object but there will be an instance object for each row in the data region.</span></span>  
  
## <a name="implementing-the-icustomreportitem-interface"></a><span data-ttu-id="62b76-113">Implémentation de l'interface ICustomReportItem</span><span class="sxs-lookup"><span data-stu-id="62b76-113">Implementing the ICustomReportItem Interface</span></span>  
 <span data-ttu-id="62b76-114">Pour créer un composant d'exécution `CustomReportItem`, vous devez implémenter l'interface <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> définie dans le fichier Microsoft.ReportingServices.ProcessingCore.dll :</span><span class="sxs-lookup"><span data-stu-id="62b76-114">To create a `CustomReportItem` run-time component you will need to implement the <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> interface that is defined in the Microsoft.ReportingServices.ProcessingCore.dll:</span></span>  
  
```csharp  
namespace Microsoft.ReportingServices.OnDemandReportRendering  
{  
    public interface ICustomReportItem  
    {  
        void GenerateReportItemDefinition(CustomReportItem customReportItem);  
void EvaluateReportItemInstance(CustomReportItem customReportItem);  
    }  
}  
```  
  
 <span data-ttu-id="62b76-115">Une fois l'interface <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> implémentée, deux stubs de méthode sont générés : <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> et <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="62b76-115">After you have implemented the <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> interface, two method stubs will be generated for you: <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> and <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>.</span></span> <span data-ttu-id="62b76-116">La méthode <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> est appelée en premier et est utilisée pour définir des propriétés de définition et créer l'objet <xref:Microsoft.ReportingServices.OnDemandReportRendering.Image> qui contiendra à la fois les propriétés de définition et d'instance utilisées pour le rendu de l'élément.</span><span class="sxs-lookup"><span data-stu-id="62b76-116">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> method is called first and is used for setting definition properties and creating the <xref:Microsoft.ReportingServices.OnDemandReportRendering.Image> object that will contain both the definition and instance properties that are used for rendering the item.</span></span> <span data-ttu-id="62b76-117">La méthode <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A> est appelée une fois les objets de définition évalués. Elle fournit en outre les objets d'instance utilisés pour le rendu de l'élément.</span><span class="sxs-lookup"><span data-stu-id="62b76-117">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A> method is called after the definition objects have been evaluated, and it provides the instance objects that will be used for rendering the item.</span></span>  
  
 <span data-ttu-id="62b76-118">L'exemple suivant illustre l'implémentation d'un élément de rapport personnalisé qui restitue le nom du contrôle sous la forme d'une image.</span><span class="sxs-lookup"><span data-stu-id="62b76-118">The following is an example implementation of a custom report item that renders the name of the control as an image.</span></span>  
  
```csharp  
namespace Microsoft.Samples.ReportingServices  
{  
    using System;  
    using System.Collections.Generic;  
    using System.Collections.Specialized;  
    using System.Drawing.Imaging;  
    using System.IO;  
    using System.Text;  
    using Microsoft.ReportingServices.OnDemandReportRendering;  
  
    public class PolygonsCustomReportItem : ICustomReportItem  
    {  
        #region ICustomReportItem Members  
  
        public void GenerateReportItemDefinition(CustomReportItem cri)  
        {  
            // Create the Image object that will be   
            // used to render the custom report item  
            cri.CreateCriImageDefinition();  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
        }  
  
        public void EvaluateReportItemInstance(CustomReportItem cri)  
        {  
            // Get the Image definition  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
  
            // Create the image for the custom report item  
            polygonImage.ImageInstance.ImageData = DrawImage(cri);  
        }  
  
        #endregion  
  
        /// <summary>  
        /// Creates an image of the CustomReportItem's name  
        /// </summary>  
        private byte[] DrawImage(CustomReportItem customReportItem)  
        {  
            int width = 1;          // pixels  
            int height = 1;         // pixels  
            int resolution = 75;    // dpi  
  
            System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            System.Drawing.Graphics graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Get the Font for the Text  
            System.Drawing.Font font = new System.Drawing.Font(System.Drawing.FontFamily.GenericMonospace,  
                12, System.Drawing.FontStyle.Regular);  
  
            // Get the Brush for drawing the Text  
            System.Drawing.Brush brush = new System.Drawing.SolidBrush(System.Drawing.Color.LightGreen);  
  
            // Get the measurements for the image  
            System.Drawing.SizeF maxStringSize = graphics.MeasureString(customReportItem.Name, font);  
            width = (int)(maxStringSize.Width + 2 * font.GetHeight(resolution));  
            height = (int)(maxStringSize.Height + 2 * font.GetHeight(resolution));  
  
            bitmap.Dispose();  
            bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            graphics.Dispose();  
            graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Draw the text  
            graphics.DrawString(customReportItem.Name, font, brush, font.GetHeight(resolution),   
                font.GetHeight(resolution));  
  
            // Create the byte array of the image data  
            MemoryStream memoryStream = new MemoryStream();  
            bitmap.Save(memoryStream, ImageFormat.Bmp);  
            memoryStream.Position = 0;  
            byte[] imageData = new byte[memoryStream.Length];  
            memoryStream.Read(imageData, 0, imageData.Length);  
  
            return imageData;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="62b76-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62b76-119">See Also</span></span>  
 <span data-ttu-id="62b76-120">[Architecture des éléments de rapports personnalisés](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="62b76-120">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="62b76-121">[Création d’un composant au moment de la conception d’éléments de rapport personnalisés](creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="62b76-121">[Creating a Custom Report Item Design-Time Component](creating-a-custom-report-item-design-time-component.md) </span></span>  
 <span data-ttu-id="62b76-122">[Bibliothèques de classes d’éléments de rapports personnalisés](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="62b76-122">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="62b76-123">Procédure : déployer un élément de rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="62b76-123">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
