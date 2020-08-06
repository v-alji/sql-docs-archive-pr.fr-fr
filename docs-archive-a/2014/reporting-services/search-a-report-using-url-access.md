---
title: Rechercher un rapport à l’aide de l’accès URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- searching reports
- text searches [Reporting Services]
- URL access [Reporting Services], report searches
ms.assetid: 6f3410c4-7944-448f-bae8-bab3e8152d46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b45f3fabf58a0980d41ee7b4b89a771655477d02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707036"
---
# <a name="search-a-report-using-url-access"></a><span data-ttu-id="5996c-102">Rechercher un rapport à l'aide de l'accès URL</span><span class="sxs-lookup"><span data-stu-id="5996c-102">Search a Report Using URL Access</span></span>
  <span data-ttu-id="5996c-103">L'accès URL vous permet de lancer des recherches sur des rapports ou sur du texte spécifique.</span><span class="sxs-lookup"><span data-stu-id="5996c-103">You can search a report for a specific set of text using URL access.</span></span> <span data-ttu-id="5996c-104">Pour effectuer une recherche dans un rapport, affectez au paramètre *rc:FindString* de l’URL le texte à rechercher.</span><span class="sxs-lookup"><span data-stu-id="5996c-104">To search a report, set the value of the *rc:FindString* parameter on the URL equal to the text for which you want to search.</span></span> <span data-ttu-id="5996c-105">Vous povuez aussi utilisez les paramètres *rc:StartFind* et *rc:EndFind* pour limiter votre recherche à certaines pages du rapport.</span><span class="sxs-lookup"><span data-stu-id="5996c-105">Additionally, use the *rc:StartFind* and *rc:EndFind* parameters to narrow your search to specific pages within the report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5996c-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="5996c-106">Example</span></span>  
 <span data-ttu-id="5996c-107">Dans l'exemple suivant, qui illustre une recherche effectuée à l'aide d'un accès URL, la recherche porte sur la première occurrence du texte « Mountain-400 » entre les pages un et cinq de l'exemple de rapport intitulé Product Catalog :</span><span class="sxs-lookup"><span data-stu-id="5996c-107">The following URL access example searches for the first occurrence of the text "Mountain-400" in the Product Catalog sample report starting with page one and ending with page five:</span></span>  
  
```  
http://server/Reportserver?/SampleReports/Product Catalog&rs:Command=Render&rc:StartFind=1&rc:EndFind=5&rc:FindString=Mountain-400  
```  
  
## <a name="see-also"></a><span data-ttu-id="5996c-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5996c-108">See Also</span></span>  
 <span data-ttu-id="5996c-109">[Accès URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5996c-109">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="5996c-110">Référence de paramètres d'accès URL</span><span class="sxs-lookup"><span data-stu-id="5996c-110">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
