---
title: Passer un paramètre de rapport dans une URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], passing parameters
- passing parameters [Reporting Services]
ms.assetid: f93a94cc-27b5-435a-aa85-69e6ec6459ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cf41ed82728d5d7c840276e135937b08f83fb131
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707252"
---
# <a name="pass-a-report-parameter-within-a-url"></a><span data-ttu-id="e6fe1-102">Passer un paramètre de rapport dans une URL</span><span class="sxs-lookup"><span data-stu-id="e6fe1-102">Pass a Report Parameter Within a URL</span></span>
  <span data-ttu-id="e6fe1-103">Vous pouvez passer des paramètres de rapport à un rapport en les incluant dans une URL de rapport.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-103">You can pass report parameters to a report by including them in a report URL.</span></span> <span data-ttu-id="e6fe1-104">Ces paramètres URL ne sont pas préfixés parce qu'ils sont directement passés au moteur de traitement des rapports.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-104">These URL parameters are not prefixed because they are passed directly to the report processing engine.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e6fe1-105">Il est important que l'URL inclue la syntaxe de proxy `_vti_bin` pour acheminer la requête via SharePoint et le proxy HTTP [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6fe1-105">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="e6fe1-106">Le proxy ajoute à la requête HTTP le contexte nécessaire pour garantir une exécution correcte du rapport pour les serveurs de rapports en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-106">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
>   
>  <span data-ttu-id="e6fe1-107">Si vous n’incluez pas la syntaxe du proxy, vous devez faire précéder le paramètre du paramètre *RP :*.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-107">If you don't include the proxy syntax, then you need to prefix the parameter with *rp:*.</span></span>  
  
 <span data-ttu-id="e6fe1-108">Tous les paramètres de requête peuvent avoir des paramètres de rapport correspondants.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-108">All query parameters can have corresponding report parameters.</span></span> <span data-ttu-id="e6fe1-109">Vous passez un paramètre de requête à un rapport en transmettant le paramètre de rapport correspondant.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-109">You pass a query parameter to a report by passing the corresponding report parameter.</span></span> <span data-ttu-id="e6fe1-110">Pour plus d’informations, consultez [Générer une requête dans le Concepteur de requêtes relationnelles &#40;Générateur de rapports et SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e6fe1-110">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6fe1-111">Les paramètres de rapport respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-111">Report parameters are case-sensitive.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="e6fe1-112">Les paramètres de rapport respectent la casse et utilisent les caractères spéciaux suivants :</span><span class="sxs-lookup"><span data-stu-id="e6fe1-112">Report parameters are case-sensitive and utilize the following special characters:</span></span>  
> 
>  -   <span data-ttu-id="e6fe1-113">Tout espace figurant dans la chaîne d'URL est remplacé par le caractère « % 20 », conformément aux normes d'encodage des URL.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-113">Any space characters in the URL string are replaced with the characters "%20," according to URL encoding standards.</span></span>  
> -   <span data-ttu-id="e6fe1-114">Un espace dans la partie Paramètre de l'URL est remplacé par un caractère Plus (+).</span><span class="sxs-lookup"><span data-stu-id="e6fe1-114">A space character in the parameter portion of the URL is replaced with a plus character (+).</span></span>  
> -   <span data-ttu-id="e6fe1-115">Un point-virgule dans toute partie de la chaîne est remplacé par les caractères « %3A ».</span><span class="sxs-lookup"><span data-stu-id="e6fe1-115">A semicolon in any portion of the string is replaced with the characters "%3A."</span></span>  
> -   <span data-ttu-id="e6fe1-116">Les navigateurs doivent effectuer automatiquement l'encodage d'URL approprié.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-116">Browsers should automatically perform the proper URL encoding.</span></span> <span data-ttu-id="e6fe1-117">Vous n'avez pas besoin d'encoder manuellement les caractères.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-117">You do not have to encode any of the characters manually.</span></span>  
  
 <span data-ttu-id="e6fe1-118">Pour définir un paramètre de rapport au sein d'une URL, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="e6fe1-118">To set a report parameter within a URL, use the following syntax:</span></span>  
  
```  
  
parameter=value  
```  
  
 <span data-ttu-id="e6fe1-119">Par exemple, pour spécifier deux paramètres, « ReportMonth » et « ReportYear », définis dans un rapport, utilisez l’URL suivante pour un serveur de rapports en mode natif :</span><span class="sxs-lookup"><span data-stu-id="e6fe1-119">For example, to specify two parameters, "ReportMonth" and "ReportYear", defined in a report, use the following URL for a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="e6fe1-120">Par exemple, pour spécifier les deux paramètres définis dans un rapport, utilisez l'URL suivante pour un serveur de rapports SharePoint intégré :</span><span class="sxs-lookup"><span data-stu-id="e6fe1-120">For example, to specify the same two parameters defined in a report, use the following URL for a SharePoint integrated mode report server.</span></span> <span data-ttu-id="e6fe1-121">Notez le `/_vti_bin`:</span><span class="sxs-lookup"><span data-stu-id="e6fe1-121">Note the `/_vti_bin`:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="e6fe1-122">Pour passer une valeur NULL pour un paramètre, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="e6fe1-122">To pass a null value for a parameter, use the following syntax:</span></span>  
  
```  
  
parameter  
:isnull=true  
  
```  
  
 <span data-ttu-id="e6fe1-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e6fe1-123">For example,</span></span>  
  
```  
SalesOrderNumber:isnull=true  
```  
  
 <span data-ttu-id="e6fe1-124">Pour passer une valeur `Boolean`, utilisez 0 pour false et 1 pour true.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-124">To pass a `Boolean` value, use 0 for false and 1 for true.</span></span> <span data-ttu-id="e6fe1-125">Pour passer une valeur `Float`, incluez le séparateur décimal associé aux paramètres régionaux définis sur le serveur</span><span class="sxs-lookup"><span data-stu-id="e6fe1-125">To pass a `Float` value, include the decimal separator of the server locale</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6fe1-126">Si votre rapport contient un paramètre de rapport qui possède une valeur par défaut et que la valeur de la propriété `Prompt` est `false` (autrement dit, la propriété Demander à l'utilisateur n'est pas sélectionnée dans le Gestionnaire de rapports), vous ne pouvez pas passer de valeur pour ce paramètre de rapport dans une URL.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-126">If your report contains a report parameter that has a default value and the value of the `Prompt` property is `false` (that is, the Prompt User property is not selected in Report Manager), then you cannot pass a value for that report parameter within a URL.</span></span> <span data-ttu-id="e6fe1-127">Cela permet aux administrateurs d'empêcher les utilisateurs finaux d'ajouter ou de modifier les valeurs de certains paramètres de rapport.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-127">This provides administrators an option for preventing end users from adding or modifying the values of certain report parameters.</span></span>  
  
##  <a name="additional-examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="e6fe1-128">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="e6fe1-128">Additional Examples</span></span>  
 <span data-ttu-id="e6fe1-129">L'exemple d'URL suivante comprend des espaces et plusieurs paramètres</span><span class="sxs-lookup"><span data-stu-id="e6fe1-129">The following URL example includes spaces and multiple parameters</span></span>  
  
-   <span data-ttu-id="e6fe1-130">Le nom de dossier « SQL Server User Education Team » comprend des espaces ; par conséquent, un « + » remplace chaque espace.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-130">Folder name of "SQL Server User Education Team" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="e6fe1-131">Le nom de rapport « team project report » comprend des espaces ; par conséquent, un « + » remplace chaque espace.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-131">Report name of "team project report" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="e6fe1-132">Passe deux paramètres : « teamgrouping2 » avec la valeur « xgroup » et « teamgrouping1 » avec la valeur « ygroup ».</span><span class="sxs-lookup"><span data-stu-id="e6fe1-132">Passes two parameters of "teamgrouping2" with a value of "xgroup" and "teamgrouping1" with a value of "ygroup".</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup  
```  
  
 <span data-ttu-id="e6fe1-133">L’exemple d’URL suivant comprend un paramètre à valeurs multiples nommé OrderID.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-133">The following URL example includes a multi-value parameter "OrderID.</span></span> <span data-ttu-id="e6fe1-134">Le format d'un paramètre à valeurs multiples consiste à répéter le nom du paramètre pour chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-134">The format for a Multi-Value parameter is to repeat the parameter name for each value.</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup&OrderID=747&OrderID=787&OrderID=12  
```  
  
 <span data-ttu-id="e6fe1-135">L’exemple d’URL suivant passe un paramètre unique de *SellStartDate* avec la valeur « 7/1/2005 », pour un serveur de rapports en mode natif.</span><span class="sxs-lookup"><span data-stu-id="e6fe1-135">The following URL example passes a single parameter of *SellStartDate* with a value of "7/1/2005", for a native mode report server.</span></span>  
  
```  
http://myserver/ReportServer/Pages/ReportViewer.aspx?%2fProduct_and_Sales_Report_AdventureWorks&SellStartDate=7/1/2005  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6fe1-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6fe1-136">See Also</span></span>  
 <span data-ttu-id="e6fe1-137">[Accès URL &#40;&#41;SSRS](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6fe1-137">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="e6fe1-138">Référence de paramètres d'accès URL</span><span class="sxs-lookup"><span data-stu-id="e6fe1-138">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
