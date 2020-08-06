---
title: Utilisation de l’accès URL dans une application web | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- links [Reporting Services], URL access
- URL access [Reporting Services], Web applications
- POST requests
- direct addressing [Reporting Services]
- Web applications [Reporting Services]
- hyperlinks [Reporting Services]
ms.assetid: 39e7918c-ad2d-4ca6-b099-2dd4dbdb83dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd31f76658f8160cbb2a576debc335588f77e72c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599801"
---
# <a name="using-url-access-in-a-web-application"></a><span data-ttu-id="fe225-102">Utilisation de l'accès URL dans une application Web</span><span class="sxs-lookup"><span data-stu-id="fe225-102">Using URL Access in a Web Application</span></span>
  <span data-ttu-id="fe225-103">L'accès URL dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] est conçu spécifiquement pour permettre l'accès à des rapports individuels sur un réseau.</span><span class="sxs-lookup"><span data-stu-id="fe225-103">URL access in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is specifically designed to enable access to individual reports over a network.</span></span> <span data-ttu-id="fe225-104">Ce type d'accès convient pour intégrer l'affichage des rapports et la navigation au sein de ces derniers dans une application Web personnalisée.</span><span class="sxs-lookup"><span data-stu-id="fe225-104">This type of access is best for integrating report viewing and navigation into a custom Web application.</span></span> <span data-ttu-id="fe225-105">Pour utiliser l'accès URL dans des applications Web, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="fe225-105">To use URL access in Web applications, you can:</span></span>  
  
-   <span data-ttu-id="fe225-106">définir une URL vers un serveur de rapports spécifique à partir d'un site ou d'un portail Web ;</span><span class="sxs-lookup"><span data-stu-id="fe225-106">Address a URL to a specific report server from a Web site or portal.</span></span>  
  
-   <span data-ttu-id="fe225-107">utiliser une méthode POST de formulaire et passer des paramètres de chaîne de requête à une URL du serveur de rapports à l'aide de champs de formulaire.</span><span class="sxs-lookup"><span data-stu-id="fe225-107">Use a form POST method and pass query string parameters to a report server URL using form fields.</span></span>  
  
## <a name="url-access-through-direct-addressing"></a><span data-ttu-id="fe225-108">Accès URL via l'adressage direct</span><span class="sxs-lookup"><span data-stu-id="fe225-108">URL Access Through Direct Addressing</span></span>  
 <span data-ttu-id="fe225-109">Pour accéder à un serveur de rapports ou à un élément de la base de données du serveur de rapports à l’aide d’une URL, entrez simplement l’adresse URL dans un navigateur ou une application web.</span><span class="sxs-lookup"><span data-stu-id="fe225-109">To access a report server or report server database item using a URL, simply provide the URL address from within a Web browser or application.</span></span> <span data-ttu-id="fe225-110">Vous pouvez également fournir des paramètres à l'URL qui peuvent affecter l'apparence du rapport ou de la ressource en cours d'accès.</span><span class="sxs-lookup"><span data-stu-id="fe225-110">You can also supply parameters to the URL that can affect the appearance of the report or resource that is being accessed.</span></span> <span data-ttu-id="fe225-111">Une URL peut cibler un serveur de rapports par le biais de la barre d’adresses d’un navigateur web, ou elle peut être la source d’un **IFrame** qui fait partie d’une application ou d’un portail web plus important.</span><span class="sxs-lookup"><span data-stu-id="fe225-111">A URL can target a report server through the address bar of a Web browser, or a URL can be the source of an **IFrame** that is part of a larger Web application or portal.</span></span> <span data-ttu-id="fe225-112">Vous pouvez ajouter des liens hypertexte à des rapports sur différentes pages Web de votre portail, et cibler un frame spécifique pour le rapport ou ouvrir une nouvelle fenêtre de navigateur dans le processus.</span><span class="sxs-lookup"><span data-stu-id="fe225-112">You can include hyperlinks to reports on various Web pages of your portal, as well as target a specific frame for the report or open a new browser window in the process.</span></span>  
  
 <span data-ttu-id="fe225-113">Dans l'exemple suivant, le lien hypertexte cible un frame nommé « main » qui peut être différent de celui qui inclut le lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="fe225-113">In the following example, the hyperlink targets a frame named "main", which might be different from the one that includes the hyperlink.</span></span> <span data-ttu-id="fe225-114">Le lien hypertexte peut faire partie d'un portail Web.</span><span class="sxs-lookup"><span data-stu-id="fe225-114">The hyperlink might be part of Web portal.</span></span>  
  
```  
<a href="http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main" target="main" >  
   Click here for the Territory Sales Drilldown sample report  
</a>  
```  
  
 <span data-ttu-id="fe225-115">Dans l’exemple précédent, le paramètre d’informations de périphérique **LinkTarget** est passé avec une valeur « main » dans la chaîne de requête de l’URL.</span><span class="sxs-lookup"><span data-stu-id="fe225-115">In the previous example, the device information setting **LinkTarget** is passed with a value of "main" in the query string of the URL.</span></span> <span data-ttu-id="fe225-116">De cette manière, tous les liens hypertexte d'extraction dans le rapport ciblent également le frame nommé « main ».</span><span class="sxs-lookup"><span data-stu-id="fe225-116">This ensures that any drillthrough hyperlinks in the report also target the frame named "main".</span></span>  
  
 <span data-ttu-id="fe225-117">Pour plus d’informations sur les paramètres d’informations de périphérique, consultez [Transmission de paramètres d’informations de périphérique aux extensions de rendu](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="fe225-117">For more information about device information settings, see [Passing Device Information Settings to Rendering Extensions](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="fe225-118">Notez que de nombreux serveurs et navigateurs limitent le nombre de caractères autorisés dans une URL.</span><span class="sxs-lookup"><span data-stu-id="fe225-118">Note that many servers and browsers limit the number of characters allowed in a URL.</span></span> <span data-ttu-id="fe225-119">Dans certains cas, une limite de 256 caractères est imposée.</span><span class="sxs-lookup"><span data-stu-id="fe225-119">In some cases, a 256-character limit is imposed.</span></span> <span data-ttu-id="fe225-120">Pour contourner cette limitation, vous pouvez utiliser des requêtes POST à l'aide de l'envoi de formulaire.</span><span class="sxs-lookup"><span data-stu-id="fe225-120">To get around this limitation, you can use POST requests using form submission.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe225-121">Internet Explorer impose une longueur maximale de 2 083 caractères dans les URL.</span><span class="sxs-lookup"><span data-stu-id="fe225-121">Internet Explorer has a maximum URL length of 2,083 characters.</span></span> <span data-ttu-id="fe225-122">Cette limite s'applique aux URL de requêtes POST et GET.</span><span class="sxs-lookup"><span data-stu-id="fe225-122">This limit applies to both POST and GET request URLs.</span></span> <span data-ttu-id="fe225-123">Toutefois, POST n'est pas limité par la taille de l'URL pour l'envoi de paires nom/valeur dans le cadre d'un formulaire, celles-ci étant transférées dans l'en-tête et non dans l'URL.</span><span class="sxs-lookup"><span data-stu-id="fe225-123">POST, however, is not limited by the size of the URL for submitting name/value pairs as part of a form, because they are transferred in the header and not the URL.</span></span>  
  
## <a name="url-access-through-a-form-post-method"></a><span data-ttu-id="fe225-124">Accès URL via une méthode POST de formulaire</span><span class="sxs-lookup"><span data-stu-id="fe225-124">URL Access Through a Form POST Method</span></span>  
 <span data-ttu-id="fe225-125">Lorsqu'un utilisateur demande des données à partir d'un serveur de rapports à l'aide de l'accès URL, la requête HTTP utilise la méthode GET.</span><span class="sxs-lookup"><span data-stu-id="fe225-125">When a user requests data from a report server using URL access, the HTTP request uses the GET method.</span></span> <span data-ttu-id="fe225-126">Ceci équivaut à un envoi de formulaire où METHOD="GET".</span><span class="sxs-lookup"><span data-stu-id="fe225-126">This is equivalent to a form submission where METHOD="GET".</span></span> <span data-ttu-id="fe225-127">Les demandes d'URL ou les envois de formulaire qui utilisent METHOD="GET" sont limités par le nombre maximal de caractères qu'un serveur ou navigateur Web peut traiter.</span><span class="sxs-lookup"><span data-stu-id="fe225-127">URL requests or form submissions that use METHOD="GET" are limited by the maximum number of characters that a server or Web browser can process.</span></span>  
  
 <span data-ttu-id="fe225-128">Avec les requêtes POST (METHOD="POST" et champs d'entrée), les paires nom/valeur sont transférées dans l'en-tête et non dans l'URL.</span><span class="sxs-lookup"><span data-stu-id="fe225-128">With POST requests (METHOD="POST" and input fields), the name/value pairs are transferred in the header and not the URL.</span></span> <span data-ttu-id="fe225-129">Par conséquent, les paires nom/valeur de la chaîne de requête ne font pas partie de l'URL, ce qui vous permet de fournir des listes de paramètres plus longues et plus complexes.</span><span class="sxs-lookup"><span data-stu-id="fe225-129">Therefore, the name/value pairs of the query string are not part of the URL, thus enabling you to provide much longer and more complex parameter lists.</span></span>  
  
 <span data-ttu-id="fe225-130">À l'aide de l'accès direct, un utilisateur peut afficher l'URL pour le serveur de rapports et éventuellement modifier la chaîne de requête ou noter les paramètres particuliers de la demande d'URL et du serveur de rapports pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="fe225-130">Using direct access, a user can see the URL for the report server, and may be able to modify the  query string or note the particular URL request and report server parameters for later use.</span></span>  
  
 <span data-ttu-id="fe225-131">L'exemple de code HTML suivant montre l'utilisation d'un formulaire que vous pouvez utiliser pour cibler un serveur de rapports avec une URL spécifique et passer des paramètres de chaîne de requête dans le cadre des champs d'entrée du formulaire.</span><span class="sxs-lookup"><span data-stu-id="fe225-131">The following sample HTML demonstrates the use of a form that you can use to target a report server with a specific URL and pass query string parameters as part of the form's input fields.</span></span>  
  
```  
<FORM id="frmRender" action="http://server/reportserver?/SampleReports/  
   Territory Sales Drilldown" method="post" target="_self">  
   <INPUT type="hidden" name="rs:Command" value="Render">   
   <INPUT type="hidden" name="rc:LinkTarget" value="main">  
   <INPUT type="hidden" name="rs:Format" value="HTML4.0">  
   <INPUT type="submit" value="Button">  
</FORM>  
```  
  
 <span data-ttu-id="fe225-132">Dans l'exemple précédent, si un utilisateur clique sur le bouton du formulaire, le serveur de rapports retourne un rapport rendu en HTML ciblant le frame actuel.</span><span class="sxs-lookup"><span data-stu-id="fe225-132">In the previous example, if a user clicks the button on the form, the report server returns an HTML-rendered report targeted at the current frame.</span></span> <span data-ttu-id="fe225-133">Une chaîne d'accès URL comparable peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="fe225-133">A comparable URL access string might look like the following:</span></span>  
  
```  
http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main&rs:Format=HTML4.0  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe225-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe225-134">See Also</span></span>  
 <span data-ttu-id="fe225-135">[Intégration de Reporting Services dans des applications](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fe225-135">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="fe225-136">[Intégration d’Reporting Services à l’aide de l’accès URL](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="fe225-136">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="fe225-137">[Utilisation de l’accès URL dans une application Windows](integrating-reporting-services-using-url-access-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="fe225-137">[Using URL Access in a Windows Application](integrating-reporting-services-using-url-access-windows-application.md) </span></span>  
 [<span data-ttu-id="fe225-138">Accès URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fe225-138">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
