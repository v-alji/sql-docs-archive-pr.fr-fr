---
title: Accéder à des éléments de serveurs de rapports à l’aide de l’accès URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- referencing URL items for report server access
- URL access [Reporting Services], report servers
ms.assetid: a58b4ca6-129d-45e9-95c7-e9169fe5bba4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6693419490c1b3770ccb41b2645cbdba8996630a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611622"
---
# <a name="access-report-server-items-using-url-access"></a><span data-ttu-id="13842-102">Accéder à des éléments de serveur de rapports à l'aide de l'accès URL</span><span class="sxs-lookup"><span data-stu-id="13842-102">Access Report Server Items Using URL Access</span></span>
  <span data-ttu-id="13842-103">Cette rubrique explique comment accéder aux éléments du catalogue de types différents dans une base de données du serveur de rapports ou dans un site SharePoint en utilisant *rs:Command*=*Value*.</span><span class="sxs-lookup"><span data-stu-id="13842-103">This topic describes how to access catalog items of different types in a report server data base or in a SharePoint site using *rs:Command*=*Value*.</span></span>  
  
 <span data-ttu-id="13842-104">Il n'est pas nécessaire d'ajouter cette chaîne de paramètres.</span><span class="sxs-lookup"><span data-stu-id="13842-104">It is not necessary to add this parameter string.</span></span> <span data-ttu-id="13842-105">Si vous l'omettez, le serveur de rapports évalue le type d'élément et sélectionne automatiquement la valeur du paramètre appropriée.</span><span class="sxs-lookup"><span data-stu-id="13842-105">If you omit it, the report server evaluates the item type and selects the appropriate parameter value automatically.</span></span> <span data-ttu-id="13842-106">Toutefois, l’utilisation de la chaîne *rs:Command*=*Valeur* dans l’URL améliore les performances du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="13842-106">However, using the *rs:Command*=*Value* string in the URL improves the performance of the report server.</span></span>  
  
 <span data-ttu-id="13842-107">Notez la syntaxe de proxy `_vti_bin` dans les exemples ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="13842-107">Note the `_vti_bin` proxy syntax in the examples below.</span></span> <span data-ttu-id="13842-108">Pour plus d’informations sur l’utilisation de la syntaxe de proxy, consultez [Informations de référence sur les paramètres d’accès URL](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="13842-108">For more information about using the proxy syntax, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="access-a-report"></a><span data-ttu-id="13842-109">Accéder à un rapport</span><span class="sxs-lookup"><span data-stu-id="13842-109">Access a Report</span></span>  
 <span data-ttu-id="13842-110">Pour afficher un rapport dans le navigateur, utilisez le paramètre de rendu *RS : Command* = *Render* .</span><span class="sxs-lookup"><span data-stu-id="13842-110">To view a report in the browser, use the *rs:Command*=*Render* parameter.</span></span> <span data-ttu-id="13842-111">Exemple :</span><span class="sxs-lookup"><span data-stu-id="13842-111">For example:</span></span>  
  
 <span data-ttu-id="13842-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="13842-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
 <span data-ttu-id="13842-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="13842-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="13842-114">Il est important que l'URL inclue la syntaxe de proxy `_vti_bin` pour acheminer la requête via SharePoint et le proxy HTTP [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13842-114">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="13842-115">Le proxy ajoute à la requête HTTP le contexte nécessaire pour garantir une exécution correcte du rapport pour les serveurs de rapports en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="13842-115">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
## <a name="access-a-resource"></a><span data-ttu-id="13842-116">Accéder à une ressource</span><span class="sxs-lookup"><span data-stu-id="13842-116">Access a Resource</span></span>  
 <span data-ttu-id="13842-117">Pour accéder à une ressource, utilisez le paramètre *RS : Command* = *GetResourceContents* . Si la ressource est compatible avec le navigateur, telle qu’une image, elle est ouverte dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="13842-117">To access a resource, use the *rs:Command*=*GetResourceContents* parameter.If the resource is compatible with the browser, such as an image, it is opened in the browser.</span></span> <span data-ttu-id="13842-118">Sinon, vous êtes invité à ouvrir ou enregistrer le fichier ou la ressource sur le disque.</span><span class="sxs-lookup"><span data-stu-id="13842-118">Otherwise, you are prompted to open or save the file or resource to disk.</span></span>  
  
 <span data-ttu-id="13842-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="13842-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span></span>  
  
 <span data-ttu-id="13842-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="13842-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span></span>  
  
## <a name="access-a-data-source"></a><span data-ttu-id="13842-121">Accéder à une source de données</span><span class="sxs-lookup"><span data-stu-id="13842-121">Access a Data Source</span></span>  
 <span data-ttu-id="13842-122">Pour accéder à une source de données, utilisez le paramètre *RS : Command* = *GetDataSourceContents* .</span><span class="sxs-lookup"><span data-stu-id="13842-122">To access a data source, use the *rs:Command*=*GetDataSourceContents* parameter.</span></span> <span data-ttu-id="13842-123">Si votre navigateur prend en charge XML, la définition de la source de données s'affiche si vous êtes un utilisateur authentifié avec l'autorisation `Read Contents` sur la source des données.</span><span class="sxs-lookup"><span data-stu-id="13842-123">If your browser supports XML, the data source definition is displayed if you are an authenticated user with `Read Contents` permission on the data source.</span></span> <span data-ttu-id="13842-124">Exemple :</span><span class="sxs-lookup"><span data-stu-id="13842-124">For example:</span></span>  
  
 <span data-ttu-id="13842-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="13842-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="13842-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="13842-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="13842-127">La structure XML peut ressembler à l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="13842-127">The XML structure might look similar to the following example:</span></span>  
  
```  
<DataSourceDefinition>  
   <Extension>SQL</Extension>  
   <ConnectString>Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=AdventureWorks2012;Data Source=MYSERVER1;</ConnectString>  
   <CredentialRetrieval>Integrated</CredentialRetrieval>  
   <WindowsCredentials>False</WindowsCredentials>  
   <ImpersonateUser>False</ImpersonateUser>  
   <Prompt />  
   <Enabled>True</Enabled>  
</DataSourceDefinition>  
```  
  
 <span data-ttu-id="13842-128">La chaîne de connexion est retournée selon le paramètre **SecureConnectionLevel** du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="13842-128">The connection string is returned based on the **SecureConnectionLevel** setting of the report server.</span></span> <span data-ttu-id="13842-129">Pour plus d’informations sur le paramètre **SecureConnectionLevel** , consultez [Utilisation des méthodes de service web sécurisées](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="13842-129">For more information about the **SecureConnectionLevel** setting, see [Using Secure Web Service Methods](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span></span>  
  
## <a name="access-the-contents-of-a-folder"></a><span data-ttu-id="13842-130">Accéder au contenu d'un dossier</span><span class="sxs-lookup"><span data-stu-id="13842-130">Access the Contents of a Folder</span></span>  
 <span data-ttu-id="13842-131">Pour accéder au contenu d’un dossier, utilisez le paramètre *RS : Command* = *GetChildren* .</span><span class="sxs-lookup"><span data-stu-id="13842-131">To access the contents of a folder, use the *rs:Command*=*GetChildren* parameter.</span></span> <span data-ttu-id="13842-132">Il retourne une page générique de navigation des dossiers qui contient des liens vers les sous-dossiers, rapports, sources de données et ressources dans le dossier demandé.</span><span class="sxs-lookup"><span data-stu-id="13842-132">A generic folder-navigation page is returned that contains links to the subfolders, reports, data sources, and resources in the requested folder.</span></span> <span data-ttu-id="13842-133">Exemple :</span><span class="sxs-lookup"><span data-stu-id="13842-133">For example:</span></span>  
  
 <span data-ttu-id="13842-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="13842-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="13842-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="13842-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="13842-136">L'interface utilisateur qui s'affiche est similaire au mode d'exploration de répertoires utilisé par [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="13842-136">The user interface you see is similar to the directory browsing mode used by [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Information Server (IIS).</span></span> <span data-ttu-id="13842-137">Le numéro de version, y compris le numéro de build spécifique, du serveur de rapports est aussi affiché sous la liste des dossiers.</span><span class="sxs-lookup"><span data-stu-id="13842-137">The version number, including the build number, of the report server is also displayed below the folder listing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13842-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13842-138">See Also</span></span>  
 <span data-ttu-id="13842-139">[Accès URL &#40;&#41;SSRS](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="13842-139">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="13842-140">Référence de paramètres d'accès URL</span><span class="sxs-lookup"><span data-stu-id="13842-140">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
