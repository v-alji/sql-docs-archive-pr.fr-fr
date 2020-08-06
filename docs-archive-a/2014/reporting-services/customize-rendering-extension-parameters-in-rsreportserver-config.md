---
title: Personnaliser les paramètres d’extension de rendu dans RSReportServer.Config | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- configuration options [Reporting Services]
- DeviceInfo settings
- rendering extensions [Reporting Services], overriding behaviors
- parameters [Reporting Services], report rendering
- overriding report rendering behavior
- extensions [Reporting Services], rendering
ms.assetid: 3bf7ab2b-70bb-41c8-acda-227994d15aed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35a01e12fa4016d03717b008e4241c3be5e55236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708996"
---
# <a name="customize-rendering-extension-parameters-in-rsreportserverconfig"></a><span data-ttu-id="76360-102">Personnaliser les paramètres d'extension de rendu dans RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="76360-102">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>
  <span data-ttu-id="76360-103">Vous pouvez spécifier des paramètres d'extension de rendu dans le fichier de configuration RSReportServer afin de remplacer le comportement de la génération de rapport par défaut pour les rapports exécutés sur un serveur de rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76360-103">You can specify rendering extension parameters in the RSReportServer configuration file to override default report rendering behavior for reports that run on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="76360-104">Vous pouvez modifier les paramètres d'extension de rendu pour obtenir les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="76360-104">You can modify rendering extension parameters to achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="76360-105">modifier l'affichage du nom de l'extension de rendu dans la liste Exporter de la barre d'outils Rapport (par exemple, pour remplacer « Web archive » par « MHTML »), ou localiser le nom dans une autre langue ;</span><span class="sxs-lookup"><span data-stu-id="76360-105">Change how the rendering extension name appears in the Export list of the report toolbar (for example, to change "Web archive" to "MHTML"), or localize the name to a different language.</span></span>  
  
-   <span data-ttu-id="76360-106">créer plusieurs instances de la même extension de rendu afin de gérer différentes options de présentation de rapport (par exemple, une version en mode Portrait et Paysage de l'extension de rendu Image) ;</span><span class="sxs-lookup"><span data-stu-id="76360-106">Create multiple instances of the same rendering extension to support different report presentation options (for example, a portrait and landscape mode version of the Image rendering extension).</span></span>  
  
-   <span data-ttu-id="76360-107">modifier les paramètres d'extension de rendu par défaut afin d'utiliser d'autres valeurs (par exemple, l'extension de rendu Image utilise TIFF comme format de sortie par défaut ; vous pouvez modifier les paramètres d'extension et utiliser le format EMF à la place).</span><span class="sxs-lookup"><span data-stu-id="76360-107">Change the default rendering extension parameters to use different values (for example, the Image rendering extension uses TIFF as the default output format; you can modify the extension parameters to use EMF instead).</span></span>  
  
 <span data-ttu-id="76360-108">La modification des paramètres d'extension de rendu affecte uniquement les opérations de rendu sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="76360-108">Changing the rendering extension parameters only affects rendering operations on the report server.</span></span> <span data-ttu-id="76360-109">Vous ne pouvez pas remplacer les paramètres d'extension de rendu en mode d'aperçu de rapport dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="76360-109">You cannot override rendering extension settings in report preview in Report Designer.</span></span>  
  
 <span data-ttu-id="76360-110">La spécification des paramètres d'extension de rendu dans les fichiers de configuration a des répercussions globales sur les extensions de rendu.</span><span class="sxs-lookup"><span data-stu-id="76360-110">Specifying rendering extension parameters in the configuration files affects rendering extensions globally.</span></span> <span data-ttu-id="76360-111">Les paramètres des fichiers de configuration sont utilisés à la place des valeurs par défaut chaque fois qu'une extension de rendu particulière est employée.</span><span class="sxs-lookup"><span data-stu-id="76360-111">The settings in the configuration files are used in place of default values whenever a particular rendering extension is used.</span></span> <span data-ttu-id="76360-112">Si vous souhaitez définir des paramètres d’extension de rendu pour une opération de rapport ou de rendu spécifique, vous devez spécifier par programmation les informations sur l’appareil à l’aide de la méthode <xref:ReportExecution2005.ReportExecutionService.Render%2A> ou en spécifiant les paramètres d’informations d’appareil sur une URL de rapport.</span><span class="sxs-lookup"><span data-stu-id="76360-112">If you want to set rendering extension parameters for a specific report or render operation, you must specify device information programmatically using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method or by specifying device information settings on a report URL.</span></span> <span data-ttu-id="76360-113">Pour obtenir la liste complète des paramètres d’informations sur l’appareil et davantage d’informations sur la spécification de paramètres d’informations sur l’appareil pour une opération de rendu, consultez [Transmission de paramètres d’informations de périphérique aux extensions de rendu](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="76360-113">For more information about specifying device information settings for a render operation, and to view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="finding-and-modifying-rsreportserverconfig"></a><span data-ttu-id="76360-114">Recherche et modification de RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="76360-114">Finding and Modifying RSReportServer.config</span></span>  
 <span data-ttu-id="76360-115">Les paramètres de configuration des formats de sortie des rapports sont spécifiés sous forme de paramètres d'extension de rendu dans le fichier RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="76360-115">Configuration settings for report output formats are specified as rendering extension parameters in the RSReportServer.config file.</span></span> <span data-ttu-id="76360-116">Pour spécifier les paramètres d'extension de rendu dans les fichiers de configuration, vous devez savoir comment définir les structures XML qui configurent les paramètres de rendu.</span><span class="sxs-lookup"><span data-stu-id="76360-116">To specify rendering extension parameters in the configuration files, you must know how to define the XML structures that set rendering parameters.</span></span> <span data-ttu-id="76360-117">Vous pouvez modifier deux structures XML :</span><span class="sxs-lookup"><span data-stu-id="76360-117">There are two XML structures that you can modify:</span></span>  
  
-   <span data-ttu-id="76360-118">L'élément `OverrideNames` définit la langue et le nom complet de l'extension de rendu.</span><span class="sxs-lookup"><span data-stu-id="76360-118">The `OverrideNames` element defines the display name and language of the rendering extension.</span></span>  
  
-   <span data-ttu-id="76360-119">La structure XML `DeviceInfo` définit les paramètres d'informations de périphérique qui sont utilisés par une extension de rendu.</span><span class="sxs-lookup"><span data-stu-id="76360-119">The `DeviceInfo` XML structure defines the device information settings that are used by a rendering extension.</span></span> <span data-ttu-id="76360-120">La plupart des paramètres d'extension de rendu sont spécifiés en tant que paramètres d'informations de périphérique.</span><span class="sxs-lookup"><span data-stu-id="76360-120">Most rendering extension parameters are specified as device information settings.</span></span>  
  
 <span data-ttu-id="76360-121">Vous pouvez utiliser un éditeur de texte pour modifier le fichier.</span><span class="sxs-lookup"><span data-stu-id="76360-121">You can use a text editor to modify the file.</span></span> <span data-ttu-id="76360-122">Le fichier RSReportServer.config est situé dans le dossier \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="76360-122">The RSReportServer.config file can be found in the \Reporting Services\Report Server\Bin folder.</span></span> <span data-ttu-id="76360-123">Pour plus d’informations sur la modification des fichiers de configuration, consultez [Modifier un fichier de configuration Reporting Services &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="76360-123">For more information about modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span>  
  
## <a name="changing-the-display-name"></a><span data-ttu-id="76360-124">Modification du nom complet</span><span class="sxs-lookup"><span data-stu-id="76360-124">Changing the Display Name</span></span>  
 <span data-ttu-id="76360-125">Le nom complet d'une extension de rendu apparaît dans la liste Exporter de la barre d'outils Rapport.</span><span class="sxs-lookup"><span data-stu-id="76360-125">The display name for a rendering extension appears in the Export list of the report toolbar.</span></span> <span data-ttu-id="76360-126">Un nom complet par défaut peut être, par exemple, au format archive Web, fichier TIFF et fichier Acrobat (PDF).</span><span class="sxs-lookup"><span data-stu-id="76360-126">Examples of default display names include Web archive, TIFF file, and Acrobat (PDF) file.</span></span> <span data-ttu-id="76360-127">Vous pouvez remplacer le nom complet par défaut par une valeur personnalisée en indiquant l'élément `OverrideNames` dans les fichiers de configuration.</span><span class="sxs-lookup"><span data-stu-id="76360-127">You can replace the default display name with a custom value by specifying the `OverrideNames` element in the configuration files.</span></span> <span data-ttu-id="76360-128">De plus, si vous définissez deux instances d'une même extension de rendu, vous pouvez utiliser l'élément `OverrideNames` pour faire la distinction entre chaque instance dans la liste Exporter.</span><span class="sxs-lookup"><span data-stu-id="76360-128">In addition, if you are defining two instances of a single rendering extension, you can use the `OverrideNames` element to distinguish each instance in the Export list.</span></span>  
  
 <span data-ttu-id="76360-129">Étant donné que les noms complets sont localisés, vous devez définir l'attribut `Language` si vous remplacez le nom complet par défaut par une valeur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="76360-129">Because display names are localized, you must set the `Language` attribute if you are replacing the default display name with a custom value.</span></span> <span data-ttu-id="76360-130">Dans le cas contraire, le nom que vous spécifiez sera ignoré.</span><span class="sxs-lookup"><span data-stu-id="76360-130">Otherwise, any name that you specify will be ignored.</span></span> <span data-ttu-id="76360-131">La valeur de langue que vous définissez doit être valide pour l'ordinateur serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="76360-131">The language value that you set must be valid for the report server computer.</span></span> <span data-ttu-id="76360-132">Par exemple, si le serveur de rapports fonctionne sur un système d'exploitation français, vous devez indiquer « fr-FR » comme valeur d'attribut.</span><span class="sxs-lookup"><span data-stu-id="76360-132">For example, if the report server is running on a French operating system, you should specify "fr-FR" as the attribute value.</span></span>  
  
 <span data-ttu-id="76360-133">L'exemple suivant décrit comment fournir un nom personnalisé sur un serveur de rapports en anglais :</span><span class="sxs-lookup"><span data-stu-id="76360-133">The following example illustrates how to provide a custom name on an English report server:</span></span>  
  
```  
<Extension Name="XML" Type="Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport,Microsoft.ReportingServices.DataRendering">  
   <OverrideNames>  
     <Name Language="en-US">My Custom Display Name for XML Rendering</Name>  
   </OverrideNames>  
</Extension>  
```  
  
## <a name="changing-device-information-settings"></a><span data-ttu-id="76360-134">Modification des paramètres d'informations de périphérique</span><span class="sxs-lookup"><span data-stu-id="76360-134">Changing Device Information Settings</span></span>  
 <span data-ttu-id="76360-135">Pour modifier les paramètres d'informations de périphérique par défaut qui sont utilisés par une extension de rendu déjà déployée sur votre serveur de rapports, vous devez taper la structure XML `DeviceInfo` dans les fichiers de configuration.</span><span class="sxs-lookup"><span data-stu-id="76360-135">To modify default device information settings that are used by a rendering extension that is already deployed on your report server, you must type the `DeviceInfo` XML structure into the configuration files.</span></span> <span data-ttu-id="76360-136">Chaque extension de rendu prend en charge des paramètres d'informations de périphérique qui sont uniques pour cette extension.</span><span class="sxs-lookup"><span data-stu-id="76360-136">Every rendering extension supports device information settings that are unique to that extension.</span></span> <span data-ttu-id="76360-137">Pour afficher la liste complète des paramètres d’informations sur l’appareil, consultez [Transmission de paramètres d’informations de périphérique aux extensions de rendu](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="76360-137">To view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="76360-138">L'exemple suivant illustre la syntaxe et la structure XML qui modifie les paramètres par défaut de l'extension de rendu Image :</span><span class="sxs-lookup"><span data-stu-id="76360-138">The following example provides an illustration of the XML structure and syntax that modifies the default settings of the Image rendering extension:</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">Image (EMF)</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <ColorDepth>32</ColorDepth>  
                <DpiX>300</DpiX>  
                <DpiY>300</DpiY>  
                <OutputFormat>EMF</OutputFormat>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="configuring-multiple-entries-for-a-rendering-extension"></a><span data-ttu-id="76360-139">Configuration de plusieurs entrées pour une extension de rendu</span><span class="sxs-lookup"><span data-stu-id="76360-139">Configuring Multiple Entries for a Rendering Extension</span></span>  
 <span data-ttu-id="76360-140">Vous pouvez créer plusieurs instances de la même extension de rendu pour prendre en charge différentes options de présentation.</span><span class="sxs-lookup"><span data-stu-id="76360-140">You can create multiple instances of the same rendering extension to support different report presentation options.</span></span> <span data-ttu-id="76360-141">Chaque instance que vous définissez peut comporter sa propre combinaison de valeurs de paramètres.</span><span class="sxs-lookup"><span data-stu-id="76360-141">Each instance that you define can have a different combination of parameter values.</span></span> <span data-ttu-id="76360-142">Lorsque vous définissez de nouvelles instances d'une expression de rendu existante, veillez à prendre en compte les points suivants :</span><span class="sxs-lookup"><span data-stu-id="76360-142">When defining new instances of an existing rendering extension, be sure to do the following:</span></span>  
  
-   <span data-ttu-id="76360-143">Spécifiez un nom unique pour l'extension.</span><span class="sxs-lookup"><span data-stu-id="76360-143">Specify a unique name for the extension.</span></span>  
  
     <span data-ttu-id="76360-144">Chaque instance doit comporter une valeur unique pour l'attribut `Name`.</span><span class="sxs-lookup"><span data-stu-id="76360-144">Each instance must have a unique value for the `Name` attribute.</span></span> <span data-ttu-id="76360-145">L'exemple suivant utilise les noms « IMAGE (EMF Landscape) » et « IMAGE (EMF Portrait) » afin de faire la distinction entre les deux instances.</span><span class="sxs-lookup"><span data-stu-id="76360-145">The following example uses the names "IMAGE (EMF Landscape)" and "IMAGE (EMF Portrait)" to distinguish between the two instances.</span></span>  
  
     <span data-ttu-id="76360-146">Soyez vigilent lorsque vous modifiez le nom d'une extension de rendu qui est déjà déployée.</span><span class="sxs-lookup"><span data-stu-id="76360-146">Use caution when changing the name of a rendering extension that is already deployed.</span></span> <span data-ttu-id="76360-147">Les développeurs qui spécifient des extensions de rendu par programmation utilisent le nom de l'extension afin d'identifier l'instance à employer pour une opération de rendu particulière.</span><span class="sxs-lookup"><span data-stu-id="76360-147">Developers who specify rendering extensions programmatically use the extension name to identify which instance to use for a particular render operation.</span></span> <span data-ttu-id="76360-148">Si vous exécutez des applications [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] personnalisées sur votre serveur de rapports, vérifiez que le développeur est informé quand vous modifiez une extension de rendu existante ou ajoutez une nouvelle extension.</span><span class="sxs-lookup"><span data-stu-id="76360-148">If you are running custom [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] applications on your report server, make sure that the developer knows if you modify an existing extension name or add a new one.</span></span>  
  
-   <span data-ttu-id="76360-149">Spécifiez un nom complet unique afin que les utilisateurs puissent comprendre les différences de chaque format de sortie.</span><span class="sxs-lookup"><span data-stu-id="76360-149">Specify a unique display name so that users can understand the differences for each output format.</span></span>  
  
     <span data-ttu-id="76360-150">Si vous configurez plusieurs versions de la même extension, vous pouvez attribuer à chaque version un nom unique en indiquant une valeur pour `OverrideNames`.</span><span class="sxs-lookup"><span data-stu-id="76360-150">If you are configuring multiple versions of the same extension, you can give each version a unique name by providing a value for `OverrideNames`.</span></span> <span data-ttu-id="76360-151">Si vous ne le faites pas, toutes les versions de l'extension sembleront porter le même nom dans la liste d'options Exporter de la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="76360-151">Otherwise, all versions of the extension will appear to have the same name in the Export options list on the report toolbar.</span></span>  
  
 <span data-ttu-id="76360-152">L'exemple suivant illustre l'utilisation de l'extension de rendu Image par défaut (qui génère une sortie au format TIFF) vers une sortie EMF en mode Portrait avec une seconde instance qui génère des rapports au format EMF en mode Paysage.</span><span class="sxs-lookup"><span data-stu-id="76360-152">The following example illustrates how to use the default Image rendering extension (which produces TIFF output) to output EMF in Portrait mode alongside a second instance that outputs reports in EMF in Landscape mode.</span></span> <span data-ttu-id="76360-153">Notez que chaque nom d'extension est unique.</span><span class="sxs-lookup"><span data-stu-id="76360-153">Notice that each extension name is unique.</span></span> <span data-ttu-id="76360-154">Lorsque vous testez cet exemple, n'oubliez pas de choisir des rapports qui ne contiennent pas de fonctions interactives telles que les options d'affichage/masquage, des matrices ou des liens d'extraction (les fonctions interactives ne fonctionnent pas dans l'extension de rendu Image) :</span><span class="sxs-lookup"><span data-stu-id="76360-154">When testing this example, remember to choose reports that do not contain interactive features such as show/hide options, matrices, or drillthrough links (interactive features do not work in the Image rendering extension):</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF Landscape)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Landscape Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>8.5in</PageHeight>  
                <PageWidth>11in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
    <Extension Name="IMAGE (EMF Portrait)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Portait Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>11in</PageHeight>  
                <PageWidth>8.5in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76360-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76360-155">See Also</span></span>  
 <span data-ttu-id="76360-156">[Fichier de configuration RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="76360-156">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="76360-157">[Fichier de configuration RSReportDesigner](report-server/rsreportdesigner-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="76360-157">[RSReportDesigner Configuration File](report-server/rsreportdesigner-configuration-file.md) </span></span>  
 <span data-ttu-id="76360-158">[Paramètres d’informations de périphérique CSV](csv-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="76360-158">[CSV Device Information Settings](csv-device-information-settings.md) </span></span>  
 <span data-ttu-id="76360-159">[Paramètres d’informations de périphérique Excel](excel-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="76360-159">[Excel Device Information Settings](excel-device-information-settings.md) </span></span>  
 <span data-ttu-id="76360-160">[Paramètres d’informations de périphérique HTML](html-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="76360-160">[HTML Device Information Settings](html-device-information-settings.md) </span></span>  
 <span data-ttu-id="76360-161">[Paramètres d’informations de périphérique pour l’image](image-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="76360-161">[Image Device Information Settings](image-device-information-settings.md) </span></span>  
 <span data-ttu-id="76360-162">[Paramètres d’informations de périphérique pour le format de rendu MHTML](mhtml-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="76360-162">[MHTML Device Information Settings](mhtml-device-information-settings.md) </span></span>  
 <span data-ttu-id="76360-163">[Paramètres d’informations de périphérique PDF](pdf-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="76360-163">[PDF Device Information Settings](pdf-device-information-settings.md) </span></span>  
 [<span data-ttu-id="76360-164">Paramètres des informations de périphériques XML</span><span class="sxs-lookup"><span data-stu-id="76360-164">XML Device Information Settings</span></span>](xml-device-information-settings.md)  
  
  
