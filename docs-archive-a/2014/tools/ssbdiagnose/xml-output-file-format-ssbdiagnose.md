---
title: Format du fichier de sortie XML (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose]
- ssbdiagnose
ms.assetid: 3ceb991b-6f15-4504-8828-de5adf448bc5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 612b317f7220f502faf1adc82cf9c1dcc8bc20a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704532"
---
# <a name="xml-output-file-format-ssbdiagnose"></a><span data-ttu-id="366d2-102">Format du fichier de sortie XML (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="366d2-102">XML Output File Format (ssbdiagnose)</span></span>
  <span data-ttu-id="366d2-103">La sortie de l’utilitaire **ssbdiagnose** est écrite dans un fichier XML lorsque vous l’exécutez avec le commutateur **-XML** .</span><span class="sxs-lookup"><span data-stu-id="366d2-103">The **ssbdiagnose** utility delivers its output as an XML file when you run it with the **-XML** switch.</span></span> <span data-ttu-id="366d2-104">Le fichier de sortie XML répertorie les informations d'en-tête et les erreurs identifiées dans la configuration [!INCLUDE[ssSB](../../includes/sssb-md.md)] ou la conversation analysée.</span><span class="sxs-lookup"><span data-stu-id="366d2-104">The XML output file lists header information and the errors that it found in the [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration or conversation that was analyzed.</span></span> <span data-ttu-id="366d2-105">Vous pouvez écrire une application qui analyse ou effectue un rapport sur les erreurs répertoriées dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="366d2-105">You can write an application to analyze or report on the errors listed in the file.</span></span> <span data-ttu-id="366d2-106">Vous pouvez également consulter le fichier XML dans tout éditeur XML, comme le bloc-notes XML.</span><span class="sxs-lookup"><span data-stu-id="366d2-106">Or, you can view the XML file in a general XML editor, such as XML Notepad.</span></span>  
  
 <span data-ttu-id="366d2-107">Un fichier de sortie de **ssbdiangose** contient un élément racine DiagnosticInformation avec deux types enfants :</span><span class="sxs-lookup"><span data-stu-id="366d2-107">An **ssbdiangose** output file contains a DiagnosticInformation root element with two child types:</span></span>  
  
-   <span data-ttu-id="366d2-108">Un élément Banner contenant les informations d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="366d2-108">A Banner element with header information.</span></span>  
  
-   <span data-ttu-id="366d2-109">Un élément Issue pour chaque problème signalé par **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="366d2-109">An Issue element for each issue that is reported by **ssbdiagnose**.</span></span>  
  
## <a name="diagnosticinformation-root-element"></a><span data-ttu-id="366d2-110">Élément racine DiagnosticInformation</span><span class="sxs-lookup"><span data-stu-id="366d2-110">DiagnosticInformation Root Element</span></span>  
  
-   [<span data-ttu-id="366d2-111">Élément DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="366d2-111">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)  
  
## <a name="banner-element"></a><span data-ttu-id="366d2-112">Élément Banner</span><span class="sxs-lookup"><span data-stu-id="366d2-112">Banner Element</span></span>  
  
-   [<span data-ttu-id="366d2-113">Élément Banner &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="366d2-113">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)  
  
## <a name="issue-element"></a><span data-ttu-id="366d2-114">Élément Issue</span><span class="sxs-lookup"><span data-stu-id="366d2-114">Issue Element</span></span>  
  
-   [<span data-ttu-id="366d2-115">Élément Issue &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="366d2-115">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)  
  
## <a name="see-also"></a><span data-ttu-id="366d2-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="366d2-116">See Also</span></span>  
 [<span data-ttu-id="366d2-117">Utilitaire ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="366d2-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
