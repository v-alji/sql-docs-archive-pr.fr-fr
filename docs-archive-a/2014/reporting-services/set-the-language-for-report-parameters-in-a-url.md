---
title: Définir la langue des paramètres de rapport dans une URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- overriding report language settings
- report servers [Reporting Services], language settings
- languages [Reporting Services]
- URL access [Reporting Services], language overrides
- international considerations [Reporting Services]
- global considerations [Reporting Services]
ms.assetid: e1ccf22f-80d6-45bc-aae0-f5f263275092
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8087a181906517bb60d4cd6839eed0681f52a5eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700758"
---
# <a name="set-the-language-for-report-parameters-in-a-url"></a><span data-ttu-id="fe900-102">Définir la langue des paramètres de rapport dans une URL</span><span class="sxs-lookup"><span data-stu-id="fe900-102">Set the Language for Report Parameters in a URL</span></span>
  <span data-ttu-id="fe900-103">Le paramètre de l’accès URL *rs:ParameterLanguage* permet d’atténuer un problème dans lequel des paramètres de rapports liés à la culture, tels que les dates, les heures, les monnaies et les nombres, sont interprétés à l’aide de la langue du navigateur.</span><span class="sxs-lookup"><span data-stu-id="fe900-103">The *rs:ParameterLanguage* URL access parameter alleviates a problem in which culture-sensitive report parameters, such as dates, times, currency, and numbers, are interpreted using the browser language.</span></span> <span data-ttu-id="fe900-104">Avec *rs:ParameterLanguage*, l’URL est à présent interprétée indépendamment du navigateur.</span><span class="sxs-lookup"><span data-stu-id="fe900-104">With *rs:ParameterLanguage*, the URL is now interpreted independently of the browser.</span></span> <span data-ttu-id="fe900-105">Par exemple, si le serveur de rapports est défini sur un paramètre régional allemand, mais qu'un utilisateur accède à un rapport via une URL en utilisant un navigateur défini sur l'anglais américain, les valeurs des paramètres transmises à un serveur de rapports sont mal interprétées.</span><span class="sxs-lookup"><span data-stu-id="fe900-105">For example, if the report server is set to a regional setting of German, but a user is accessing a report via a URL using a browser that is set to English-United States, parameter values that are passed to a report server will be misinterpreted.</span></span>  
  
 <span data-ttu-id="fe900-106">Considérez l'URL suivante d'un rapport :</span><span class="sxs-lookup"><span data-stu-id="fe900-106">Consider the following URL to a report:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008  
```  
  
 <span data-ttu-id="fe900-107">Dans le cas ci-dessus, le serveur, s'exécutant sous une culture « de-de », génère une URL via un abonnement par courrier électronique ou un lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="fe900-107">In the above case, the server, running under a culture of "de-de", generates a URL either through an e-mail subscription or a hyperlink.</span></span> <span data-ttu-id="fe900-108">Le lien hypertexte indique que le rapport doit être paramétré avec une date de début du 4 octobre 2008 et une date de fin du 11 octobre 2008 d'après le format allemand de date/heure standard.</span><span class="sxs-lookup"><span data-stu-id="fe900-108">The hyperlink indicates that the report should be parameterized by a start date of October 4, 2008 and an end date of October 11, 2008 according to German date/time standards.</span></span> <span data-ttu-id="fe900-109">Toutefois, un utilisateur qui accède à l'URL via un navigateur défini sur « en-us » oblige le serveur à interpréter ces valeurs comme le 10 avril 2008 et le 10 novembre 2008, selon le format standard de date/heure de l'anglais américain.</span><span class="sxs-lookup"><span data-stu-id="fe900-109">However, a user that is accessing the URL through a browser set to "en-us" forces the server to interpret the values as April 10, 2008 and November 10, 2008 under United States English date/time standards.</span></span> <span data-ttu-id="fe900-110">Pour résoudre ce problème, vous pouvez utiliser *rs:ParameterLanguage* pour remplacer la langue du navigateur afin d’interpréter le paramètre :</span><span class="sxs-lookup"><span data-stu-id="fe900-110">To fix the problem, *rs:ParameterLanguage* can be used to override the browser language for parameter interpretation:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008&rs:ParameterLanguage=de-DE  
```  
  
 <span data-ttu-id="fe900-111">Outre une valeur **true** et **false** pour le paramètre de l’accès URL *rc:Parameters*, vous pouvez à présent passer une valeur **Collapsed**.</span><span class="sxs-lookup"><span data-stu-id="fe900-111">In addition to a value of **true** and **false** for the URL access parameter *rc:Parameters*, you can now pass a value of **Collapsed**.</span></span> <span data-ttu-id="fe900-112">Quand vous utilisez *rc:Parameters*=**Collapsed** sur une URL, la zone d’invite des paramètres de la Visionneuse HTML est réduite, mais l’utilisateur peut encore basculer vers elle.</span><span class="sxs-lookup"><span data-stu-id="fe900-112">When using *rc:Parameters*=**Collapsed** on a URL, the parameter prompt area of the HTML viewer is collapsed out of sight, but can still be toggled by the user.</span></span> <span data-ttu-id="fe900-113">La valeur **false** supprime la zone d’invite des paramètres de la barre d’outils de la Visionneuse HTML et la rend indisponible pour l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="fe900-113">A value of **false** removes the parameter prompt area from the HTML viewer toolbar and makes it unavailable to the end-user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe900-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe900-114">See Also</span></span>  
 <span data-ttu-id="fe900-115">[Accès URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fe900-115">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="fe900-116">Référence de paramètres d'accès URL</span><span class="sxs-lookup"><span data-stu-id="fe900-116">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
