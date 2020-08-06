---
title: Effectuer le rendu d’un instantané d’historique de rapports à l’aide de l’accès URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], report history
- history snapshots [Reporting Services]
- historical data [Reporting Services]
- snapshots [Reporting Services], URL access
- snapshots [Reporting Services], rendering report history
ms.assetid: 3f87f82d-0e61-4492-9c4b-f5238c39e8cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 67854a39ab7e38289627d03ac00cc4b2a6dca6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605239"
---
# <a name="render-a-report-history-snapshot-using-url-access"></a><span data-ttu-id="28d0b-102">Rendre un instantané d'historique de rapport à l'aide de l'accès URL</span><span class="sxs-lookup"><span data-stu-id="28d0b-102">Render a Report History Snapshot Using URL Access</span></span>
  <span data-ttu-id="28d0b-103">Vous pouvez effectuer le rendu d’un rapport reposant sur une capture instantanée d’historique de rapport en indiquant le paramètre *rs:Snapshot* et en définissant sa valeur sur un ID de capture instantanée valide.</span><span class="sxs-lookup"><span data-stu-id="28d0b-103">You can render a report based on a report history snapshot by supplying the *rs:Snapshot* parameter and setting its value to a valid snapshot ID.</span></span> <span data-ttu-id="28d0b-104">La valeur de ce paramètre doit être spécifiée au format AAAA-MM-JJTHH:MM:SS, conformément à la norme ISO 8601.</span><span class="sxs-lookup"><span data-stu-id="28d0b-104">The parameter value is in the format YYYY-MM-DDTHH:MM:SS, based on the International Organization for Standardization (ISO) 8601 standard.</span></span>  
  
 <span data-ttu-id="28d0b-105">Si vous omettez ce paramètre, le rapport est rendu selon le paramétrage des options d'exécution de rapports et de gestion du cache du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="28d0b-105">If you omit this parameter, the report is rendered according to the report execution and cache management option settings of the report server.</span></span> <span data-ttu-id="28d0b-106">Pour plus d’informations sur l’exécution des rapports, consultez [Définir les propriétés de traitement d’un rapport](report-server/set-report-processing-properties.md).</span><span class="sxs-lookup"><span data-stu-id="28d0b-106">For more information about report execution, see [Set Report Processing Properties](report-server/set-report-processing-properties.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28d0b-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="28d0b-107">Example</span></span>  
 <span data-ttu-id="28d0b-108">L'exemple suivant montre une URL qui extrait un instantané d'historique de rapport :</span><span class="sxs-lookup"><span data-stu-id="28d0b-108">The following example shows a URL that retrieves a report history snapshot:</span></span>  
  
```  
http://myrshost/reportserver?/SampleReports/Company Sales&rs:Snapshot=2003-04-07T13:40:02  
```  
  
## <a name="see-also"></a><span data-ttu-id="28d0b-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28d0b-109">See Also</span></span>  
 <span data-ttu-id="28d0b-110">[Accès URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28d0b-110">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="28d0b-111">Référence de paramètres d'accès URL</span><span class="sxs-lookup"><span data-stu-id="28d0b-111">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
