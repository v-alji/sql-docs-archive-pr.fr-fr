---
title: Accès URL (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services]
- links [Reporting Services], URL access
- URL access [Reporting Services], about URL access
- parameters [Reporting Services], URL access
- report servers [Reporting Services], URL access
- hyperlinks [Reporting Services]
ms.assetid: 52c3f2a3-3d6d-4fee-9c46-83f366919398
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf44ea3c15c12f37eebf6e89faf4ff3affd64433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603805"
---
# <a name="url-access-ssrs"></a><span data-ttu-id="6e1ea-102">Accès URL (SSRS)</span><span class="sxs-lookup"><span data-stu-id="6e1ea-102">URL Access (SSRS)</span></span>
  <span data-ttu-id="6e1ea-103">L'accès URL du serveur de rapports dans SQL Server Reporting Services (SSRS) vous permet d'envoyer des commandes à un serveur de rapports par la biais d'une demande d'URL.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-103">URL access of the report server in SQL Server Reporting Services (SSRS) enables you to send commands to a report server through a URL request.</span></span> <span data-ttu-id="6e1ea-104">Par exemple, vous pouvez personnaliser le rendu d'un rapport sur un serveur de rapports en mode natif ou dans une bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-104">For example, you can customize the rendering of a report on a native mode report server or in a SharePoint library.</span></span> <span data-ttu-id="6e1ea-105">Vous avez peut-être affiché le rapport à l'aide d'un ensemble de valeurs de paramètre de rapport, ou vous avez peut-être consulté une page spécifique digne d'intérêt dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-105">You may have viewed the report using a specific set of report parameter values, or you may have been viewing a particular page of interest in the report.</span></span> <span data-ttu-id="6e1ea-106">Vous pouvez encapsuler ces informations dans l'URL à l'aide de paramètres d'accès URL prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-106">You can encapsulate this information in the URL using predefined URL access parameters.</span></span> <span data-ttu-id="6e1ea-107">Vous pouvez personnaliser davantage la façon dont le serveur de rapports traite le rapport en incorporant des paramètres pour les formats de rendu ou pour l'apparence de la visionneuse de rapports.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-107">You can further customize how the report server processes the report by embedding parameters for rendering formats or for the look and feel of the report viewer.</span></span> <span data-ttu-id="6e1ea-108">Vous pouvez ensuite coller cette URL directement dans un courrier électronique ou une page Web pour permettre à d'autres utilisateurs d'accéder à votre rapport de la même manière dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-108">You can then paste this URL directly into an email or Web page to let others to access your report in the same manner in the browser.</span></span>  
  
 <span data-ttu-id="6e1ea-109">Autres actions que vous pouvez exécuter via l'accès URL :</span><span class="sxs-lookup"><span data-stu-id="6e1ea-109">Other actions you can perform through URL access are:</span></span>  
  
-   <span data-ttu-id="6e1ea-110">Envoyer des commandes à la visionneuse HTML, notamment ajuster son apparence</span><span class="sxs-lookup"><span data-stu-id="6e1ea-110">Send commands to the HTML viewer, such as adjusting its look and feel</span></span>  
  
-   <span data-ttu-id="6e1ea-111">Répertorier les enfants d'un dossier de catalogue</span><span class="sxs-lookup"><span data-stu-id="6e1ea-111">List the children of a catalog folder</span></span>  
  
-   <span data-ttu-id="6e1ea-112">Récupérer la définition XML d'un élément de catalogue</span><span class="sxs-lookup"><span data-stu-id="6e1ea-112">Retrieve the XML definition of a catalog item</span></span>  
  
-   <span data-ttu-id="6e1ea-113">Effectuer le rendu d'un instantané d'historique de rapport</span><span class="sxs-lookup"><span data-stu-id="6e1ea-113">Render a specific report history snapshot</span></span>  
  
-   <span data-ttu-id="6e1ea-114">Gérer les sessions de rapport</span><span class="sxs-lookup"><span data-stu-id="6e1ea-114">Manage report sessions</span></span>  
  
 <span data-ttu-id="6e1ea-115">Pour obtenir la liste complète des commandes et paramètres disponibles via l’accès URL, consultez [Référence de paramètre d’accès URL](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="6e1ea-115">For the complete list of commands and settings available through URL access, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="url-access-concepts"></a><span data-ttu-id="6e1ea-116">Concepts d'accès URL</span><span class="sxs-lookup"><span data-stu-id="6e1ea-116">URL Access Concepts</span></span>  
 <span data-ttu-id="6e1ea-117">Les demandes d'URL au serveur de rapports contiennent des paramètres qui sont traités par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-117">URL requests to the report server contain parameters that are processed by the report server.</span></span> <span data-ttu-id="6e1ea-118">La façon dont le serveur de rapports gère les demandes d'URL dépend des paramètres, des préfixes de paramètres et des types d'éléments qui sont inclus dans l'URL.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-118">The way in which the report server handles URL requests depends on the parameters, parameter prefixes, and types of items that are included in the URL.</span></span> <span data-ttu-id="6e1ea-119">Les URL du serveur de rapports suivent les recommandations de mise en forme des URL indiquées dans la version préliminaire de la norme conjointe du W3C (World Wide Web Consortium) et de l'IETF.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-119">Report server URLs adhere to the URL formatting guidelines as proposed by the joint World Wide Web Consortium W3C/IETF draft standard.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="6e1ea-120">Les fonctionnalités d’URL sont compatibles avec la plupart des navigateurs et applications Internet qui prennent en charge l’adressage URL standard.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-120">URL functionality is compatible with most Internet browsers or applications that support standard URL addressing.</span></span>  
  
### <a name="url-access-syntax"></a><span data-ttu-id="6e1ea-121">Syntaxe de l'accès URL</span><span class="sxs-lookup"><span data-stu-id="6e1ea-121">URL Access Syntax</span></span>  
 <span data-ttu-id="6e1ea-122">Les demandes d'URL peuvent contenir plusieurs paramètres, indiqués sans ordre précis.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-122">URL requests can contain multiple parameters that are listed in any order.</span></span> <span data-ttu-id="6e1ea-123">Les paramètres sont séparés par une esperluette (&) et les paires nom/valeur sont séparées par un signe égal (=).</span><span class="sxs-lookup"><span data-stu-id="6e1ea-123">Parameters are separated by an ampersand (&) and name/value pairs are separated by an equal sign (=).</span></span>  
  
```  
  
rswebserviceurl  
?  
reportpath  
      [&prefix:param=value]...n]  
  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="6e1ea-124">Description de la syntaxe</span><span class="sxs-lookup"><span data-stu-id="6e1ea-124">Syntax Description</span></span>  
 <span data-ttu-id="6e1ea-125">*rswebserviceurl*</span><span class="sxs-lookup"><span data-stu-id="6e1ea-125">*rswebserviceurl*</span></span>  
 <span data-ttu-id="6e1ea-126">URL du service web du serveurs de rapports.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-126">The Web service URL of the report server.</span></span> <span data-ttu-id="6e1ea-127">Pour le mode natif, il s’agit de l’URL du service web de l’instance du serveur de rapports configurée dans le Gestionnaire de configuration de Reporting Services (consultez [Configurer des URL de serveurs de rapports &#40;Gestionnaire de configuration de SSRS&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span><span class="sxs-lookup"><span data-stu-id="6e1ea-127">For native mode, it is the Web service URL of the report server instance configured in Reporting Services Configuration Manager (see [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span></span> <span data-ttu-id="6e1ea-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6e1ea-128">For example:</span></span>  
  
```  
http://myrshost/reportserver  
https://machine.adventure-works.com/reportserver_MYNAMEDINSTANCE  
```  
  
 <span data-ttu-id="6e1ea-129">Pour le mode intégré SharePoint, il s’agit de l’URL du proxy [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] sur un site SharePoint intégré à [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e1ea-129">For SharePoint integrated mode, it is the URL of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] proxy at a SharePoint site integrated with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="6e1ea-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6e1ea-130">For example:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver  
```  
  
> [!TIP]  
>  <span data-ttu-id="6e1ea-131">Il est important que l'URL inclue la syntaxe de proxy `_vti_bin` pour acheminer la requête via SharePoint et le proxy HTTP [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e1ea-131">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="6e1ea-132">Le proxy ajoute à la requête HTTP le contexte nécessaire pour garantir une exécution correcte du rapport pour les serveurs de rapports en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-132">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
 <span data-ttu-id="6e1ea-133">*pathinfo*</span><span class="sxs-lookup"><span data-stu-id="6e1ea-133">*pathinfo*</span></span>  
 <span data-ttu-id="6e1ea-134">Chemin relatif de l’élément dans la base de données du serveur de rapports en mode natif, ou URL complète de l’élément dans un catalogue SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-134">The relative path name of the item in the native mode report server database, or the fully qualified URL of the item in a SharePoint catalog.</span></span>  
  
 <span data-ttu-id="6e1ea-135">Chemin de l’élément du catalogue.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-135">The path of the catalog item.</span></span> <span data-ttu-id="6e1ea-136">Pour le mode natif, il s'agit du chemin d'accès relatif de l'élément dans la base de données du serveur de rapports, commençant par une barre oblique (`/`).</span><span class="sxs-lookup"><span data-stu-id="6e1ea-136">For native mode, it is the relative path of the item in the report server database, beginning with a slash (`/`).</span></span> <span data-ttu-id="6e1ea-137">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6e1ea-137">For example:</span></span>  
  
```  
/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2  
```  
  
 <span data-ttu-id="6e1ea-138">Pour le mode intégré SharePoint, il s'agit de l'URL complète de l'élément dans la bibliothèque SharePoint, y compris l'extension d'élément.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-138">For SharePoint integrated mode, it is the fully qualified URL of the item in the SharePoint library, including the item extension.</span></span> <span data-ttu-id="6e1ea-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6e1ea-139">For example:</span></span>  
  
```  
http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl  
```  
  
 `&`  
 <span data-ttu-id="6e1ea-140">Utilisé pour séparer les paires nom/valeur des paramètres d'accès URL.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-140">Used to separate name and value pairs of URL access parameters.</span></span>  
  
 <span data-ttu-id="6e1ea-141">**prefix**</span><span class="sxs-lookup"><span data-stu-id="6e1ea-141">**prefix**</span></span>  
 <span data-ttu-id="6e1ea-142">facultatif.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-142">Optional.</span></span> <span data-ttu-id="6e1ea-143">Préfixe de paramètre d’accès URL (par exemple, `rs:` ou `rc:`) qui permet d’accéder à un processus spécifique exécuté sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-143">A prefix for the URL access parameter (for example, `rs:` or `rc:`) that accesses a specific process running within the report server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e1ea-144">Si aucun préfixe n'est spécifié pour un paramètre d'accès URL, ce dernier est traité par le serveur de rapports comme un paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-144">If a prefix for a URL access parameter is not included, the parameter is processed by the report server as a report parameter.</span></span> <span data-ttu-id="6e1ea-145">Les paramètres de rapport n'utilisent pas de préfixe de paramètre et respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-145">Report parameters do not use a parameter prefix and are case-sensitive.</span></span>  
  
 <span data-ttu-id="6e1ea-146">**param**</span><span class="sxs-lookup"><span data-stu-id="6e1ea-146">**param**</span></span>  
 <span data-ttu-id="6e1ea-147">Le nom du paramètre.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-147">The parameter name.</span></span>  
  
 <span data-ttu-id="6e1ea-148">*value*</span><span class="sxs-lookup"><span data-stu-id="6e1ea-148">*value*</span></span>  
 <span data-ttu-id="6e1ea-149">Texte d'URL correspondant à la valeur du paramètre utilisé.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-149">URL text corresponding to the value of the parameter being used.</span></span>  
  
 <span data-ttu-id="6e1ea-150">**Remarque :** Pour obtenir la liste des paramètres d’accès URL disponibles, consultez [Référence de paramètre d’accès URL](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="6e1ea-150">**Note:** For a list of the available URL access parameters, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span> <span data-ttu-id="6e1ea-151">Pour obtenir des exemples où des paramètres de rapport sont passés sur l’URL, consultez [Passer un paramètre de rapport dans une URL](pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="6e1ea-151">For examples passing report parameters on the URL, see [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6e1ea-152">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="6e1ea-152">Related Tasks</span></span>  
  
|<span data-ttu-id="6e1ea-153">Descriptions de tâche</span><span class="sxs-lookup"><span data-stu-id="6e1ea-153">Task Descriptions</span></span>|<span data-ttu-id="6e1ea-154">Liens</span><span class="sxs-lookup"><span data-stu-id="6e1ea-154">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="6e1ea-155">Accéder aux éléments du serveur de rapports, tels que des rapports, des sources de données partagées, et des ressources.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-155">Access report server items, such as reports, shared data sources, and resources.</span></span>|[<span data-ttu-id="6e1ea-156">Accéder à des éléments de serveurs de rapports à l'aide de l'accès URL</span><span class="sxs-lookup"><span data-stu-id="6e1ea-156">Access Report Server Items Using URL Access</span></span>](access-report-server-items-using-url-access.md)|  
|<span data-ttu-id="6e1ea-157">Passer des paramètres de rapport à un rapport.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-157">Pass report parameters to a report.</span></span>|[<span data-ttu-id="6e1ea-158">Passer un paramètre de rapport dans une URL</span><span class="sxs-lookup"><span data-stu-id="6e1ea-158">Pass a Report Parameter Within a URL</span></span>](pass-a-report-parameter-within-a-url.md)|  
|<span data-ttu-id="6e1ea-159">Définir les paramètres régionaux des paramètres de rapport dans la chaîne d'accès URL, qui définit les traductions spécifiques aux paramètres régionaux des dates, des devises, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-159">Set the locale of the report parameters in the URL access string, which defines the locale-specific interpretations of dates, currencies, and so on.</span></span>|[<span data-ttu-id="6e1ea-160">Définir la langue des paramètres de rapport dans une URL</span><span class="sxs-lookup"><span data-stu-id="6e1ea-160">Set the Language for Report Parameters in a URL</span></span>](set-the-language-for-report-parameters-in-a-url.md)|  
|<span data-ttu-id="6e1ea-161">Envoyer les paramètres spécifiques d'extension de rendu qui personnalisent le rendu du rapport.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-161">Send rendering extension specific settings that customize how the report is rendered.</span></span>|[<span data-ttu-id="6e1ea-162">Spécifier les paramètres d’informations des périphériques dans une URL</span><span class="sxs-lookup"><span data-stu-id="6e1ea-162">Specify Device Information Settings in a URL</span></span>](specify-device-information-settings-in-a-url.md)|  
|<span data-ttu-id="6e1ea-163">Exporter un rapport directement vers un format de fichier sans l'afficher dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-163">Export a report directly to a file format without viewing it in the browser.</span></span>|[<span data-ttu-id="6e1ea-164">Exporter un rapport à l’aide de l’accès URL</span><span class="sxs-lookup"><span data-stu-id="6e1ea-164">Export a Report Using URL Access</span></span>](export-a-report-using-url-access.md)|  
|<span data-ttu-id="6e1ea-165">Ouvrir un rapport et accéder directement à l'emplacement d'une chaîne.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-165">Open a report and navigate directly to the location of a string.</span></span>|[<span data-ttu-id="6e1ea-166">Rechercher un rapport à l'aide de l'accès URL</span><span class="sxs-lookup"><span data-stu-id="6e1ea-166">Search a Report Using URL Access</span></span>](search-a-report-using-url-access.md)|  
|<span data-ttu-id="6e1ea-167">Effectuer le rendu d'un instantané d'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="6e1ea-167">Render a specific report history snapshot.</span></span>|[<span data-ttu-id="6e1ea-168">Rendre un instantané d'historique de rapports à l'aide de l'accès URL</span><span class="sxs-lookup"><span data-stu-id="6e1ea-168">Render a Report History Snapshot Using URL Access</span></span>](render-a-report-history-snapshot-using-url-access.md)|  
  
## <a name="see-also"></a><span data-ttu-id="6e1ea-169">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e1ea-169">See Also</span></span>  
 <span data-ttu-id="6e1ea-170">[Passer un paramètre de rapport dans une URL](pass-a-report-parameter-within-a-url.md) </span><span class="sxs-lookup"><span data-stu-id="6e1ea-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span></span>  
 <span data-ttu-id="6e1ea-171">[Référence de paramètres d’accès URL](url-access-parameter-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6e1ea-171">[URL Access Parameter Reference](url-access-parameter-reference.md) </span></span>  
 <span data-ttu-id="6e1ea-172">[Intégration de Reporting Services à l’aide de l’accès URL](application-integration/integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="6e1ea-172">[Integrating Reporting Services Using URL Access](application-integration/integrating-reporting-services-using-url-access.md) </span></span>  
 [<span data-ttu-id="6e1ea-173">Recherche, affichage et gestion de rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6e1ea-173">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
