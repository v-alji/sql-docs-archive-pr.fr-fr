---
title: Exporter un rapport à l’aide de l’accès URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- formats [Reporting Services], URL rendering
- URL access [Reporting Services], rendering formats
ms.assetid: 6a3b7fc3-3d91-4d12-8371-42ea12e74517
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 69f340855e37ffde49aec0af096c094a142659d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695435"
---
# <a name="export-a-report-using-url-access"></a><span data-ttu-id="c1566-102">Exporter un rapport à l'aide de l'accès URL</span><span class="sxs-lookup"><span data-stu-id="c1566-102">Export a Report Using URL Access</span></span>
  <span data-ttu-id="c1566-103">Vous pouvez éventuellement spécifier le format de rendu d’un rapport à l’aide du paramètre *RS : format* .</span><span class="sxs-lookup"><span data-stu-id="c1566-103">You can optionally specify the format in which to render a report by using the *rs:Format* parameter.</span></span> <span data-ttu-id="c1566-104">Par exemple, pour obtenir une copie PDF d'un rapport directement à partir d'un serveur de rapports en mode natif :</span><span class="sxs-lookup"><span data-stu-id="c1566-104">For example, to get a PDF copy of a report directly from a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/myreport&rs:Format=PDF  
```  
  
 <span data-ttu-id="c1566-105">Et, pour un serveur de rapport SharePoint en mode intégré :</span><span class="sxs-lookup"><span data-stu-id="c1566-105">And, from a SharePoint integrated mode report server:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/myrereport.rdl&rs:Format=PDF  
```  
  
 <span data-ttu-id="c1566-106">Les valeurs utilisables pour ce paramètre dépendent des extensions de rendu de rapport installées sur le serveur de rapports auquel vous accédez.</span><span class="sxs-lookup"><span data-stu-id="c1566-106">Valid values for this parameter are based on the report rendering extensions that are installed on the report server being accessed.</span></span> <span data-ttu-id="c1566-107">Les extensions les plus fréquentes sont HTML4.0, WORD, MHTML, IMAGE, EXCEL, CSV, PDF, XML et NULL.</span><span class="sxs-lookup"><span data-stu-id="c1566-107">Common extensions are HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML, and NULL.</span></span> <span data-ttu-id="c1566-108">Lorsque l'extension de rendu définie n'est pas installée sur le serveur de rapports, le rapport ne peut pas être restitué et le navigateur affiche un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="c1566-108">If a specified rendering extension is not installed on the report server, the report is not rendered and an error is generated and displayed in the browser.</span></span>  
  
 <span data-ttu-id="c1566-109">Lorsque le paramètre *Format* n'est pas ajouté à l'URL, le serveur de rapports détecte le navigateur requis et restitue le rapport dans le format HTML approprié.</span><span class="sxs-lookup"><span data-stu-id="c1566-109">If you do not include the *Format* parameter as part of the URL, the report server detects the browser and renders the report in the appropriate HTML format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1566-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1566-110">See Also</span></span>  
 <span data-ttu-id="c1566-111">[Accès URL &#40;&#41;SSRS](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c1566-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="c1566-112">Référence de paramètres d'accès URL</span><span class="sxs-lookup"><span data-stu-id="c1566-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
