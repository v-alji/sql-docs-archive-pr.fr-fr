---
title: Exportation vers un fichier image (Générateur de rapports et SSRS) | Microsoft Docs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 020d8ea2-de07-4212-a2bb-2ed0df2c8db8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dc1c8539b39a99c252ebfcb0275b674f657de6c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605238"
---
# <a name="exporting-to-an-image-file-report-builder-and-ssrs"></a><span data-ttu-id="c72f0-102">Exportation vers un fichier image (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="c72f0-102">Exporting to an Image File (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c72f0-103">L'extension de rendu de type image effectue le rendu d'un rapport dans un fichier bitmap ou un métafichier.</span><span class="sxs-lookup"><span data-stu-id="c72f0-103">The Image rendering extension renders a report to a bitmap or metafile.</span></span> <span data-ttu-id="c72f0-104">Par défaut, l'extension de rendu de type image génère un fichier TIFF du rapport, qui peut être présenté dans plusieurs pages.</span><span class="sxs-lookup"><span data-stu-id="c72f0-104">By default, the Image rendering extension produces a TIFF file of the report, which can be viewed in multiple pages.</span></span> <span data-ttu-id="c72f0-105">Lorsque le client reçoit l'image, il peut l'afficher dans une visionneuse d'images et l'imprimer.</span><span class="sxs-lookup"><span data-stu-id="c72f0-105">When the client receives the image, it can be displayed in an image viewer and printed.</span></span> <span data-ttu-id="c72f0-106">Cette rubrique fournit des informations spécifiques au rendu de l'image et décrit les exceptions aux règles de rendu.</span><span class="sxs-lookup"><span data-stu-id="c72f0-106">This topic provides Image renderer-specific information and describes exceptions to the rendering rules.</span></span>  
  
 <span data-ttu-id="c72f0-107">L'extension de rendu de type image peut générer des fichiers dans l'un des formats pris en charge par [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG et TIFF.</span><span class="sxs-lookup"><span data-stu-id="c72f0-107">The Image rendering extension can generate files in any of the formats supported by [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="c72f0-108">Pour le format TIFF, le nom de fichier du flux principal est *ReportName*.tif.</span><span class="sxs-lookup"><span data-stu-id="c72f0-108">For TIFF format, the file name of the primary stream is *ReportName*.tif.</span></span> <span data-ttu-id="c72f0-109">Pour tous les autres formats dont le rendu s’effectue sur la base d’une page par fichier, le nom de fichier est *ReportName_Page.ext* .</span><span class="sxs-lookup"><span data-stu-id="c72f0-109">For all other formats, which render as a single page per file, the file name is *ReportName_Page.ext* where.</span></span> <span data-ttu-id="c72f0-110">*ext* est l'extension de fichier pour le format choisi.</span><span class="sxs-lookup"><span data-stu-id="c72f0-110">*ext* is the file extension for the chosen format.</span></span> <span data-ttu-id="c72f0-111">Pour produire un fichier dans un autre format pris en charge par Image, spécifiez l’une des chaînes répertoriées ci-dessus dans le paramètre **OutputFormatDeviceInfo** .</span><span class="sxs-lookup"><span data-stu-id="c72f0-111">To produce a file in another Image-supported format, specify any of the above listed strings in the **OutputFormatDeviceInfo** setting.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="supported-image-formats"></a><a name="SupportedImageFormats"></a> <span data-ttu-id="c72f0-112">Formats d'image pris en charge</span><span class="sxs-lookup"><span data-stu-id="c72f0-112">Supported Image Formats</span></span>  
 <span data-ttu-id="c72f0-113">Le tableau suivant indique l'extension de fichier et MimeType pour chaque format du convertisseur d'image.</span><span class="sxs-lookup"><span data-stu-id="c72f0-113">The following table shows the file extension and MimeType for each Image renderer format.</span></span>  
  
|<span data-ttu-id="c72f0-114">**Type**</span><span class="sxs-lookup"><span data-stu-id="c72f0-114">**Type**</span></span>|<span data-ttu-id="c72f0-115">**Extension**</span><span class="sxs-lookup"><span data-stu-id="c72f0-115">**Extension**</span></span>|<span data-ttu-id="c72f0-116">**MIMEType**</span><span class="sxs-lookup"><span data-stu-id="c72f0-116">**MIMEType**</span></span>|  
|--------------|-------------------|------------------|  
|<span data-ttu-id="c72f0-117">BMP</span><span class="sxs-lookup"><span data-stu-id="c72f0-117">BMP</span></span>|<span data-ttu-id="c72f0-118">bmp</span><span class="sxs-lookup"><span data-stu-id="c72f0-118">bmp</span></span>|<span data-ttu-id="c72f0-119">image/bmp</span><span class="sxs-lookup"><span data-stu-id="c72f0-119">image/bmp</span></span>|  
|<span data-ttu-id="c72f0-120">GIF</span><span class="sxs-lookup"><span data-stu-id="c72f0-120">GIF</span></span>|<span data-ttu-id="c72f0-121">GIF</span><span class="sxs-lookup"><span data-stu-id="c72f0-121">gif</span></span>|<span data-ttu-id="c72f0-122">image/gif</span><span class="sxs-lookup"><span data-stu-id="c72f0-122">image/gif</span></span>|  
|<span data-ttu-id="c72f0-123">JPEG</span><span class="sxs-lookup"><span data-stu-id="c72f0-123">JPEG</span></span>|<span data-ttu-id="c72f0-124">jpeg</span><span class="sxs-lookup"><span data-stu-id="c72f0-124">jpeg</span></span>|<span data-ttu-id="c72f0-125">image/jpeg</span><span class="sxs-lookup"><span data-stu-id="c72f0-125">image/jpeg</span></span>|  
|<span data-ttu-id="c72f0-126">PNG</span><span class="sxs-lookup"><span data-stu-id="c72f0-126">PNG</span></span>|<span data-ttu-id="c72f0-127">png</span><span class="sxs-lookup"><span data-stu-id="c72f0-127">png</span></span>|<span data-ttu-id="c72f0-128">image/png</span><span class="sxs-lookup"><span data-stu-id="c72f0-128">image/png</span></span>|  
|<span data-ttu-id="c72f0-129">TIFF</span><span class="sxs-lookup"><span data-stu-id="c72f0-129">TIFF</span></span>|<span data-ttu-id="c72f0-130">tif</span><span class="sxs-lookup"><span data-stu-id="c72f0-130">tif</span></span>|<span data-ttu-id="c72f0-131">image/tiff</span><span class="sxs-lookup"><span data-stu-id="c72f0-131">image/tiff</span></span>|  
|<span data-ttu-id="c72f0-132">EMF</span><span class="sxs-lookup"><span data-stu-id="c72f0-132">EMF</span></span>|<span data-ttu-id="c72f0-133">EMF</span><span class="sxs-lookup"><span data-stu-id="c72f0-133">emf</span></span>|<span data-ttu-id="c72f0-134">image/emf</span><span class="sxs-lookup"><span data-stu-id="c72f0-134">image/emf</span></span>|  
|<span data-ttu-id="c72f0-135">EMFPlus</span><span class="sxs-lookup"><span data-stu-id="c72f0-135">EMFPlus</span></span>|<span data-ttu-id="c72f0-136">EMF</span><span class="sxs-lookup"><span data-stu-id="c72f0-136">emf</span></span>|<span data-ttu-id="c72f0-137">image/emf</span><span class="sxs-lookup"><span data-stu-id="c72f0-137">image/emf</span></span>|  
  
  
##  <a name="rendering-multiple-pages"></a><a name="RenderingMultiplePages"></a> <span data-ttu-id="c72f0-138">Rendu de plusieurs pages</span><span class="sxs-lookup"><span data-stu-id="c72f0-138">Rendering Multiple Pages</span></span>  
 <span data-ttu-id="c72f0-139">TIFF est le seul format qui prend en charge les documents de plusieurs pages dans un unique fichier.</span><span class="sxs-lookup"><span data-stu-id="c72f0-139">TIFF is the only format that supports multiple page documents in a single file.</span></span> <span data-ttu-id="c72f0-140">D'autres formats, tels que JPG ou PNG, produisent une page à la fois et requièrent un appel séparé à l'extension de rendu pour chaque page.</span><span class="sxs-lookup"><span data-stu-id="c72f0-140">Other formats, such as JPG or PNG, output one page at a time and require a separate call to the rendering extension for each page.</span></span>  
  
  
##  <a name="interactivity"></a><a name="Interactivity"></a><span data-ttu-id="c72f0-141">Interactivité</span><span class="sxs-lookup"><span data-stu-id="c72f0-141">Interactivity</span></span>  
 <span data-ttu-id="c72f0-142">L'interactivité n'est pas prise en charge par les formats Image générés par ce convertisseur.</span><span class="sxs-lookup"><span data-stu-id="c72f0-142">Interactivity is not supported in any Image formats generated by this renderer.</span></span> <span data-ttu-id="c72f0-143">Les éléments interactifs suivants ne sont pas rendus :</span><span class="sxs-lookup"><span data-stu-id="c72f0-143">The following interactive elements are not rendered:</span></span>  
  
-   <span data-ttu-id="c72f0-144">Liens hypertexte</span><span class="sxs-lookup"><span data-stu-id="c72f0-144">Hyperlinks</span></span>  
  
-   <span data-ttu-id="c72f0-145">Afficher ou masquer</span><span class="sxs-lookup"><span data-stu-id="c72f0-145">Show or Hide</span></span>  
  
-   <span data-ttu-id="c72f0-146">Explorateur de documents</span><span class="sxs-lookup"><span data-stu-id="c72f0-146">Document Map</span></span>  
  
-   <span data-ttu-id="c72f0-147">Liens d'extraction ou interactifs</span><span class="sxs-lookup"><span data-stu-id="c72f0-147">Drillthrough or clickthrough links</span></span>  
  
-   <span data-ttu-id="c72f0-148">Tri d'utilisateur final</span><span class="sxs-lookup"><span data-stu-id="c72f0-148">End user sort</span></span>  
  
-   <span data-ttu-id="c72f0-149">En-têtes fixes</span><span class="sxs-lookup"><span data-stu-id="c72f0-149">Fixed headers</span></span>  
  
-   <span data-ttu-id="c72f0-150">Signets</span><span class="sxs-lookup"><span data-stu-id="c72f0-150">Bookmarks</span></span>  
  
  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a><span data-ttu-id="c72f0-151">Paramètres d’informations de périphérique</span><span class="sxs-lookup"><span data-stu-id="c72f0-151">Device Information Settings</span></span>  
 <span data-ttu-id="c72f0-152">Vous pouvez modifier certains paramètres par défaut pour ce convertisseur en modifiant les paramètres d'informations de périphérique.</span><span class="sxs-lookup"><span data-stu-id="c72f0-152">You can change some default settings for this renderer by changing the device information settings.</span></span> <span data-ttu-id="c72f0-153">Pour plus d'informations, consultez [Image Device Information Settings](../image-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c72f0-153">For more information, see [Image Device Information Settings](../image-device-information-settings.md).</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="c72f0-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c72f0-154">See Also</span></span>  
 <span data-ttu-id="c72f0-155">[Pagination dans Reporting Services &#40;Générateur de rapports et SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c72f0-155">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c72f0-156">[Comportements de rendu &#40;Générateur de rapports et SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c72f0-156">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c72f0-157">[Fonctionnalités interactives pour différentes extensions de rendu de rapport &#40;Générateur de rapports et SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="c72f0-157">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="c72f0-158">[Rendu des éléments de rapport &#40;Générateur de rapports et SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c72f0-158">[Rendering Report Items &#40;Report Builder and SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c72f0-159">Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c72f0-159">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
