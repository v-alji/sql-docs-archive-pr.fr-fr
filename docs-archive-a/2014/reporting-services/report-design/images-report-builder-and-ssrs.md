---
title: Images (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fcc2db5c-5c26-4607-ae2b-f65c80360536
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f0840a10cc1082ba8dc7912862f7cf34c64972d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697544"
---
# <a name="images-report-builder-and-ssrs"></a><span data-ttu-id="e40b8-102">Images [Générateur de rapports et SSRS]</span><span class="sxs-lookup"><span data-stu-id="e40b8-102">Images (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e40b8-103">Une image est un élément de rapport qui contient une référence à une image qui est incorporée dans le rapport, stockée dans une base de données, stockée sur le serveur de rapports ou stockée à un autre emplacement sur le Web.</span><span class="sxs-lookup"><span data-stu-id="e40b8-103">An image is a report item that contains a reference to an image that is embedded in the report, stored in a database, stored on the report server, or stored elsewhere on the Web.</span></span> <span data-ttu-id="e40b8-104">Une image peut se répéter avec des lignes de données.</span><span class="sxs-lookup"><span data-stu-id="e40b8-104">An image can be a picture that is repeated with rows of data.</span></span> <span data-ttu-id="e40b8-105">Vous pouvez également utiliser une image en guise d'arrière-plan pour certains éléments de rapport.</span><span class="sxs-lookup"><span data-stu-id="e40b8-105">You can also use an image as a background for certain report items.</span></span>  
  
 <span data-ttu-id="e40b8-106">Le stockage de logos sur un serveur est une bonne idée, car cela vous permet d'utiliser le même logo dans de nombreux rapports.</span><span class="sxs-lookup"><span data-stu-id="e40b8-106">Storing logos on a server is a good idea because you can use the same logo in many reports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="comparing-external-embedded-and-data-bound-images"></a><a name="ComparingImages"></a> <span data-ttu-id="e40b8-107">Comparaison entre les images externes, les images incorporées et les images liées aux données</span><span class="sxs-lookup"><span data-stu-id="e40b8-107">Comparing External, Embedded, and Data-Bound Images</span></span>  
 <span data-ttu-id="e40b8-108">Si vous utilisez une image stockée sur le serveur ou une autre image externe dans un rapport, l'élément image contient un chemin d'accès pointant vers une image située sur le serveur de rapports ou à un emplacement sur le Web.</span><span class="sxs-lookup"><span data-stu-id="e40b8-108">When you use a server-based or other external image in a report, the image item contains a path that points to an image on the report server or wherever it exists on the Web.</span></span> <span data-ttu-id="e40b8-109">Si vous utilisez une image incorporée, les données de l'image sont stockées dans la définition de rapport et elles n'existent pas sous la forme d'un fichier distinct.</span><span class="sxs-lookup"><span data-stu-id="e40b8-109">When you use an embedded image, however, the image data is stored within the report definition and does not exist as a separate file.</span></span>  
  
 <span data-ttu-id="e40b8-110">Il convient d'utiliser des images stockées sur le serveur pour insérer des logos et des images statiques partagées par plusieurs rapports ou pages Web.</span><span class="sxs-lookup"><span data-stu-id="e40b8-110">Server-based images work well for logos and static pictures that are shared among several reports or Web pages.</span></span> <span data-ttu-id="e40b8-111">En revanche, il est préférable de recourir à des images incorporées pour vous assurer qu'elles sont disponibles en permanence pour le rapport. Cependant, elles ne peuvent pas être partagées.</span><span class="sxs-lookup"><span data-stu-id="e40b8-111">Embedded images ensure that the images are always available to the report, but they cannot be shared.</span></span> <span data-ttu-id="e40b8-112">Les définitions de rapports comportant des images externes sont plus petites que les définitions avec des images incorporées.</span><span class="sxs-lookup"><span data-stu-id="e40b8-112">Report definitions with external images are smaller than definitions with embedded images.</span></span>  
  
 <span data-ttu-id="e40b8-113">Les images liées aux données peuvent également être affichées à partir de données binaires stockées dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="e40b8-113">Data-bound images can also be displayed from binary data stored in a database.</span></span> <span data-ttu-id="e40b8-114">Par exemple, les images qui jouxtent les noms de produits dans une liste de produits sont des images de base de données.</span><span class="sxs-lookup"><span data-stu-id="e40b8-114">For example, the pictures that appear alongside product names in a product list are database images.</span></span> <span data-ttu-id="e40b8-115">Dans l'image suivante, les images des bicyclettes sont stockées dans une base de données et récupérées dans le rapport pour illustrer chaque produit.</span><span class="sxs-lookup"><span data-stu-id="e40b8-115">In the following picture, the images of bicycles are stored in a database and retrieved in the report to illustrate each product.</span></span>  
  
 <span data-ttu-id="e40b8-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span><span class="sxs-lookup"><span data-stu-id="e40b8-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span></span>  
  

  
##  <a name="images-as-report-parts"></a><a name="ImagesReportParts"></a> <span data-ttu-id="e40b8-117">Images en tant que parties de rapport</span><span class="sxs-lookup"><span data-stu-id="e40b8-117">Images as Report Parts</span></span>  
 <span data-ttu-id="e40b8-118">Vous pouvez enregistrer des images hors d'un rapport en tant que parties de rapport.</span><span class="sxs-lookup"><span data-stu-id="e40b8-118">You can save images separately from a report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 
  
##  <a name="embedding-images"></a><a name="EmbedImages"></a> <span data-ttu-id="e40b8-119">Incorporation d'images</span><span class="sxs-lookup"><span data-stu-id="e40b8-119">Embedding Images</span></span>  
 <span data-ttu-id="e40b8-120">Vous pouvez incorporer des images dans un rapport de sorte que toutes les données de l'image soient stockées dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="e40b8-120">You can embed images in a report so that all image data is stored within the report definition.</span></span> <span data-ttu-id="e40b8-121">Lorsque vous incorporez une image, un encodage MIME lui est appliqué et elle est stockée sous la forme de texte dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="e40b8-121">When you embed an image, the image is MIME-encoded and stored as text in the report definition.</span></span> <span data-ttu-id="e40b8-122">L'incorporation garantit que l'image est toujours disponible pour le rapport, mais elle accroît la taille de la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="e40b8-122">Using an embedded image ensures that the image is always available to the report, but it also increases the size of the report definition.</span></span>  
  
 <span data-ttu-id="e40b8-123">Pour plus d’informations sur l’incorporation d’une image, consultez [Incorporer une image dans un rapport &#40;Générateur de rapports et SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e40b8-123">For more information about embedding an image, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="external-images"></a><a name="ExternalImages"></a> <span data-ttu-id="e40b8-124">Images externes</span><span class="sxs-lookup"><span data-stu-id="e40b8-124">External Images</span></span>  
 <span data-ttu-id="e40b8-125">Dans un rapport, vous pouvez inclure une image stockée, en spécifiant une URL pointant vers celle-ci.</span><span class="sxs-lookup"><span data-stu-id="e40b8-125">You can include stored images in a report by specifying a URL to the image.</span></span> <span data-ttu-id="e40b8-126">Lorsque vous utilisez une image externe dans un rapport, la source de l'image est définie à `External` et la valeur de l'image correspond à l'adresse URL ou au chemin d'accès de l'image.</span><span class="sxs-lookup"><span data-stu-id="e40b8-126">When you use an external image in a report, the image source is set to `External` and the value for the image is the URL address or path to the image.</span></span>  
  
 <span data-ttu-id="e40b8-127">Pour plus d’informations, consultez [Spécification de chemins d’accès à des éléments externes &#40;Générateur de rapports et SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e40b8-127">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="e40b8-128">Lorsque le rapport est exécuté dans le Générateur de rapports ou dans le Concepteur de rapports, l'aperçu utilise les informations d'identification de l'utilisateur pour afficher l'image.</span><span class="sxs-lookup"><span data-stu-id="e40b8-128">When the report is run in Report Builder or Report Designer, preview uses the credentials of the user to display the image.</span></span> <span data-ttu-id="e40b8-129">Lorsque le rapport est exécuté sur le serveur de rapports, l'image dans le rapport peut ne pas s'afficher si les informations d'identification du serveur ne sont pas suffisantes pour accéder à l'image.</span><span class="sxs-lookup"><span data-stu-id="e40b8-129">When the report is run on the report server, the image in the report may not be displayed if the server credentials are not sufficient to access the image.</span></span> <span data-ttu-id="e40b8-130">Dans ce cas, contactez votre administrateur système.</span><span class="sxs-lookup"><span data-stu-id="e40b8-130">In that case, contact your system administrator.</span></span>  
  
 <span data-ttu-id="e40b8-131">Pour plus d’informations sur l’ajout d’une image externe à un rapport, consultez [Ajouter une image externe &#40;Générateur de rapports et SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e40b8-131">For more information about adding an external image to a report, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="background-images"></a><a name="BackgroundImages"></a> <span data-ttu-id="e40b8-132">Images d'arrière-plan</span><span class="sxs-lookup"><span data-stu-id="e40b8-132">Background Images</span></span>  
 <span data-ttu-id="e40b8-133">Vous pouvez utiliser une image comme arrière-plan dans le corps du rapport ou dans un rectangle, une zone de texte, une liste, une matrice ou une table.</span><span class="sxs-lookup"><span data-stu-id="e40b8-133">You can use an image as a background image in the body of the report or in a rectangle, text box, list, matrix, or table.</span></span> <span data-ttu-id="e40b8-134">Une image d'arrière-plan et une image possèdent des propriétés semblables.</span><span class="sxs-lookup"><span data-stu-id="e40b8-134">A background image and an image have similar properties.</span></span> <span data-ttu-id="e40b8-135">Vous pouvez également indiquer la manière dont l'image est reproduite pour occuper tout l'arrière-plan de l'élément.</span><span class="sxs-lookup"><span data-stu-id="e40b8-135">You can also specify how the image is repeated to fill the background of the item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e40b8-136">Certaines extensions de rendu, par exemple l'extension de rendu HTML, effectuent le rendu de l'image d'arrière-plan destinée au corps du rapport dans le corps, et dans l'en-tête et le pied de page.</span><span class="sxs-lookup"><span data-stu-id="e40b8-136">Some rendering extensions, like the HTML rendering extension, render the background image for the report body in the body, the page header, and the page footer.</span></span> <span data-ttu-id="e40b8-137">Vous pouvez définir une image d'arrière-plan différente pour l'en-tête et le pied de page, mais si aucune image n'est spécifiée, le rapport utilise celle du corps.</span><span class="sxs-lookup"><span data-stu-id="e40b8-137">You can define a separate background image for the page header and footer, but if no image is defined, the report uses the background image of the body.</span></span> <span data-ttu-id="e40b8-138">D'autres extensions de rendu, comme Image, n'effectuent pas le rendu de l'image d'arrière-plan du corps dans l'en-tête et le pied de page.</span><span class="sxs-lookup"><span data-stu-id="e40b8-138">Other rendering extensions, like the Image rendering extension, do not render the body background image in the page header and footer.</span></span>  
  
 <span data-ttu-id="e40b8-139">Pour plus d’informations sur l’ajout d’une image d’arrière-plan, consultez [Ajouter une image d’arrière-plan &#40;Générateur de rapports et SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e40b8-139">For more information about adding a background image, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="data-bound-images"></a><a name="DataboundImages"></a> <span data-ttu-id="e40b8-140">Images liées aux données</span><span class="sxs-lookup"><span data-stu-id="e40b8-140">Data-bound Images</span></span>  
 <span data-ttu-id="e40b8-141">Vous pouvez ajouter à votre rapport des images stockées dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="e40b8-141">You can add images that are stored in a database to your report.</span></span> <span data-ttu-id="e40b8-142">Pour cela, vous utilisez le même élément de rapport de type image que celui des images statiques, mais avec un ensemble de propriétés indiquant que l'image se trouve dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="e40b8-142">You use the same image report item as the one used for static images, but with a set of properties that indicate that the image is stored in a database.</span></span> <span data-ttu-id="e40b8-143">Pour obtenir des instructions sur l’utilisation d’images liées à des données, consultez [Ajouter une image liée à des données &#40;Générateur de rapports et SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e40b8-143">To view instructions about working with data-bound images, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a> <span data-ttu-id="e40b8-144">Rubriques de procédures</span><span class="sxs-lookup"><span data-stu-id="e40b8-144">How-to Topics</span></span>  
 [<span data-ttu-id="e40b8-145">Ajouter une image externe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e40b8-145">Add an External Image &#40;Report Builder and SSRS&#41;</span></span>](add-an-external-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e40b8-146">Incorporer une image dans un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e40b8-146">Embed an Image in a Report &#40;Report Builder and SSRS&#41;</span></span>](embed-an-image-in-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e40b8-147">Ajouter une image d’arrière-plan &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e40b8-147">Add a Background Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-background-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e40b8-148">Ajouter une image liée à des données &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e40b8-148">Add a Data-Bound Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-data-bound-image-report-builder-and-ssrs.md)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="e40b8-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e40b8-149">See Also</span></span>  
 <span data-ttu-id="e40b8-150">[Exportation vers un fichier image &#40;Générateur de rapports et SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e40b8-150">[Exporting to an Image File &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e40b8-151">Comportements de rendu &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e40b8-151">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
