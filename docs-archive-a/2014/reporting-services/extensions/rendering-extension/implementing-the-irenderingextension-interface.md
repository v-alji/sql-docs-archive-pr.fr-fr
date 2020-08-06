---
title: Implémentation de l’interface IRenderingExtension | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IRenderingExtension interface
- rendering extensions [Reporting Services], IRenderingExtension interface
ms.assetid: 74b2f2b7-6796-42da-ab7d-b05891ad4001
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f57c4aa41ccfed165b69581cbf3917e4dfbb4960
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610485"
---
# <a name="implementing-the-irenderingextension-interface"></a><span data-ttu-id="79715-102">Implémentation de l'interface IRenderingExtension</span><span class="sxs-lookup"><span data-stu-id="79715-102">Implementing the IRenderingExtension Interface</span></span>
  <span data-ttu-id="79715-103">L'extension de rendu prend les résultats d'une définition de rapport qui est combinée aux données réelles et restitue les données résultantes dans un format utilisable.</span><span class="sxs-lookup"><span data-stu-id="79715-103">The rendering extension takes the results from a report definition that is combined with the actual data and renders the resulting data to a format that is useable.</span></span> <span data-ttu-id="79715-104">La transformation de la combinaison des données et de la mise en forme s'effectue par le biais d'une classe CLR (Common Language Runtime) qui implémente <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span><span class="sxs-lookup"><span data-stu-id="79715-104">The transformation of the combined data and formatting is done by using a common language runtime (CLR) class that implements <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span></span> <span data-ttu-id="79715-105">Cela transforme le modèle objet en un format de sortie qui est consommable par une visionneuse, une imprimante ou une autre cible de sortie.</span><span class="sxs-lookup"><span data-stu-id="79715-105">This transforms the object model into an output format that is consumable by a viewer, printer, or other output target.</span></span>  
  
 <span data-ttu-id="79715-106"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> a trois méthodes qui doivent être codées :</span><span class="sxs-lookup"><span data-stu-id="79715-106">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> has three methods that must be coded:</span></span>  
  
-   <span data-ttu-id="79715-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> : effectue le rendu du rapport.</span><span class="sxs-lookup"><span data-stu-id="79715-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> - renders the report.</span></span>  
  
-   <span data-ttu-id="79715-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> : effectue le rendu d'un flux spécifique à partir du rapport.</span><span class="sxs-lookup"><span data-stu-id="79715-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> - renders a specific stream from the report.</span></span>  
  
-   <span data-ttu-id="79715-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> :  obtient des informations supplémentaires, telles que des icônes, nécessaires pour le rapport.</span><span class="sxs-lookup"><span data-stu-id="79715-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> - gets additional information, such as icons, that are required for the report.</span></span>  
  
 <span data-ttu-id="79715-110">Ces méthodes sont traitées en détail dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="79715-110">The following sections discuss these methods in more detail.</span></span>  
  
## <a name="render-method"></a><span data-ttu-id="79715-111">Méthode Render</span><span class="sxs-lookup"><span data-stu-id="79715-111">Render Method</span></span>  
 <span data-ttu-id="79715-112">La méthode <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> contient des arguments qui représentent les objets suivants :</span><span class="sxs-lookup"><span data-stu-id="79715-112">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> method contains arguments that represent the following objects:</span></span>  
  
-   <span data-ttu-id="79715-113">L’objet *report* lui-même que vous souhaitez restituer.</span><span class="sxs-lookup"><span data-stu-id="79715-113">The *report* that you want to render.</span></span> <span data-ttu-id="79715-114">Cet objet contient des informations sur les propriétés, les données et la disposition du rapport.</span><span class="sxs-lookup"><span data-stu-id="79715-114">This object contains properties, data, and layout information for the report.</span></span> <span data-ttu-id="79715-115">Le rapport est la racine de l'arborescence du modèle objet de rapport.</span><span class="sxs-lookup"><span data-stu-id="79715-115">The report is the root of the report object model tree.</span></span>  
  
-   <span data-ttu-id="79715-116">Le paramètre *ServerParameters* qui contient l’objet dictionnaire de chaînes ainsi que les paramètres du serveur de rapports, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="79715-116">The *ServerParameters* that contain the string dictionary object, with the parameters for the report server, if any.</span></span>  
  
-   <span data-ttu-id="79715-117">Le paramètre *deviceInfo* qui contient les paramètres de périphérique.</span><span class="sxs-lookup"><span data-stu-id="79715-117">The *deviceInfo* parameter that contain the device settings.</span></span> <span data-ttu-id="79715-118">Pour plus d’informations, consultez [Passage de paramètres d’informations sur les appareils aux extensions de rendu](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="79715-118">For more information, see [Passing Device Information Settings to Rendering Extensions](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
-   <span data-ttu-id="79715-119">Le paramètre *clientCapabilities* qui contient un objet dictionnaire <xref:System.Collections.Specialized.NameValueCollection> qui a des informations relatives au client destinataire du rendu.</span><span class="sxs-lookup"><span data-stu-id="79715-119">The *clientCapabilities* parameter that contains a <xref:System.Collections.Specialized.NameValueCollection> dictionary object that has information about the client to which you are rendering.</span></span>  
  
-   <span data-ttu-id="79715-120">Le paramètre *RenderProperties* qui contient les informations relatives au résultat de rendu.</span><span class="sxs-lookup"><span data-stu-id="79715-120">The *RenderProperties* that contains information about the rendering result.</span></span>  
  
-   <span data-ttu-id="79715-121">La fonction *createAndRegisterStream* est une fonction de délégué à appeler pour obtenir un flux de données de rendu.</span><span class="sxs-lookup"><span data-stu-id="79715-121">The *createAndRegisterStream* is a delegate function to be called to get a stream to render into.</span></span>  
  
### <a name="deviceinfo-parameter"></a><span data-ttu-id="79715-122">Paramètre deviceInfo</span><span class="sxs-lookup"><span data-stu-id="79715-122">deviceInfo Parameter</span></span>  
 <span data-ttu-id="79715-123">Le paramètre *deviceInfo* contient des paramètres de rendu, pas des paramètres de rapport.</span><span class="sxs-lookup"><span data-stu-id="79715-123">The *deviceInfo* parameter contains rendering parameters, not report parameters.</span></span> <span data-ttu-id="79715-124">Ces paramètres de rendu sont passés à l'extension de rendu.</span><span class="sxs-lookup"><span data-stu-id="79715-124">These rendering parameters are passed to the rendering extension.</span></span> <span data-ttu-id="79715-125">Les valeurs *deviceInfo* sont converties en un objet <xref:System.Collections.Specialized.NameValueCollection> par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="79715-125">The *deviceInfo* values are converted into a <xref:System.Collections.Specialized.NameValueCollection> object by the report server.</span></span> <span data-ttu-id="79715-126">Les éléments dans le paramètre *deviceInfo* sont traités comme des valeurs non sensibles à la casse.</span><span class="sxs-lookup"><span data-stu-id="79715-126">Items in the *deviceInfo* parameter are treated as case-insensitive values.</span></span> <span data-ttu-id="79715-127">Si la demande de rendu résulte d’un accès URL, les paramètres d’URL de type `rc:key=value` sont convertis en paires clé/valeur dans l’objet dictionnaire *deviceInfo*.</span><span class="sxs-lookup"><span data-stu-id="79715-127">If the render request came as a result of URL access, the URL parameters in the form `rc:key=value` are converted to key/value pairs in the *deviceInfo* dictionary object.</span></span> <span data-ttu-id="79715-128">Le code de détection du navigateur fournit également les éléments suivants dans le dictionnaire *clientCapabilities* : EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type et AcceptLanguage.</span><span class="sxs-lookup"><span data-stu-id="79715-128">The browser detection code also provides the following items in the *clientCapabilities* dictionary: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type, and AcceptLanguage.</span></span> <span data-ttu-id="79715-129">Toute paire nom/valeur dans *deviceInfo* qui n’est pas interprétée par l’extension de rendu est ignorée.</span><span class="sxs-lookup"><span data-stu-id="79715-129">Any name/value pair in the *deviceInfo* parameter that is not understood by the rendering extension is ignored.</span></span> <span data-ttu-id="79715-130">L'exemple de code suivant montre un exemple de méthode <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> qui extrait des icônes :</span><span class="sxs-lookup"><span data-stu-id="79715-130">The following code sample shows a sample <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method that retrieves icons:</span></span>  
  
```csharp  
public void GetRenderingResource (CreateStream createStreamCallback, NameValueCollection deviceInfo)  
{  
    string[] iconTagValues = deviceInfo.GetValues("Icon");  
    if ((iconTagValues != null) && (iconTagValues.Length > 0) )  
    {  
        // Create a stream to output to.  
        Stream outputStream = createStreamCallback(m_iconResourceName, "gif", null, "image/gif", false);  
        // Get the GIF image for one of the buttons on the toolbar  
        Image requiredImage = (Image) m_resourcemanager.GetObject(m_iconResourceName  
        // Write the image to the output stream  
        requiredImage.Save(outputStream, requiredImage.RawFormat);  
    }  
    return;  
}  
```  
  
## <a name="renderstream-method"></a><span data-ttu-id="79715-131">Méthode RenderStream</span><span class="sxs-lookup"><span data-stu-id="79715-131">RenderStream Method</span></span>  
 <span data-ttu-id="79715-132">La méthode <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> restitue un flux particulier à partir du rapport.</span><span class="sxs-lookup"><span data-stu-id="79715-132">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> method renders a particular stream from the report.</span></span> <span data-ttu-id="79715-133">Tous les flux sont créés pendant l'appel <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> initial, mais les flux ne sont pas renvoyés initialement au client.</span><span class="sxs-lookup"><span data-stu-id="79715-133">All streams are created during the initial <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> call, but the streams are not returned to the client initially.</span></span> <span data-ttu-id="79715-134">Cette méthode est utilisée pour des flux secondaires (par exemple, des images dans le rendu HTML) ou des pages supplémentaires d'une extension de rendu multi-page (par exemple, Image/EMF).</span><span class="sxs-lookup"><span data-stu-id="79715-134">This method is used for secondary streams, such as images in HTML rendering, or additional pages of a multi-page rendering extension, such as Image/EMF.</span></span>  
  
## <a name="getrenderingresource-method"></a><span data-ttu-id="79715-135">Méthode GetRenderingResource</span><span class="sxs-lookup"><span data-stu-id="79715-135">GetRenderingResource Method</span></span>  
 <span data-ttu-id="79715-136">La méthode <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> extrait les informations sans exécuter un rendu entier du rapport.</span><span class="sxs-lookup"><span data-stu-id="79715-136">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method retrieves the information without executing an entire rendering of the report.</span></span> <span data-ttu-id="79715-137">Il arrive que le rapport requière des informations qui ne nécessitent pas le rendu du rapport lui-même.</span><span class="sxs-lookup"><span data-stu-id="79715-137">There are times when the report requires information that does not require the report itself to be rendered.</span></span> <span data-ttu-id="79715-138">Par exemple, si vous avez besoin de l’icône associée à l’extension de rendu, utilisez le paramètre *DeviceInfo* contenant la balise unique **\<Icon>** .</span><span class="sxs-lookup"><span data-stu-id="79715-138">For example, if you need the icon associated with the rendering extension, use the *deviceInfo* parameter containing the single tag **\<Icon>**.</span></span> <span data-ttu-id="79715-139">Utilisez, dans ce cas, la méthode <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>.</span><span class="sxs-lookup"><span data-stu-id="79715-139">In these cases, you can use the <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79715-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79715-140">See Also</span></span>  
 <span data-ttu-id="79715-141">[Implémentation d’une extension de rendu](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="79715-141">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 [<span data-ttu-id="79715-142">Vue d'ensemble des extensions de rendu</span><span class="sxs-lookup"><span data-stu-id="79715-142">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
  
  
