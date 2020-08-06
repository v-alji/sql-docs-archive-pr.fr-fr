---
title: Paramètres d’informations de périphérique Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], Excel rendering
- Excel [Reporting Services], rendering
ms.assetid: bb5f3566-f033-4470-be87-1f52fb7a4ab6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d71c83195c8f91984bbbce95bd00402928fdb36e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703883"
---
# <a name="excel-device-information-settings"></a><span data-ttu-id="2c83f-102">Paramètres d'informations de périphérique Excel</span><span class="sxs-lookup"><span data-stu-id="2c83f-102">Excel Device Information Settings</span></span>
  <span data-ttu-id="2c83f-103">Le tableau suivant répertorie les paramètres d'informations de périphérique qui permettent un rendu au format [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c83f-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] format.</span></span>  
  
|<span data-ttu-id="2c83f-104">Paramètre</span><span class="sxs-lookup"><span data-stu-id="2c83f-104">Setting</span></span>|<span data-ttu-id="2c83f-105">Valeur</span><span class="sxs-lookup"><span data-stu-id="2c83f-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="2c83f-106">**OmitDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="2c83f-106">**OmitDocumentMap**</span></span>|<span data-ttu-id="2c83f-107">Indique s'il faut omettre l'explorateur de documents pour les rapports qui le prennent en charge.</span><span class="sxs-lookup"><span data-stu-id="2c83f-107">Indicates whether to omit the document map for reports that support it.</span></span> <span data-ttu-id="2c83f-108">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="2c83f-108">The default value is `false`.</span></span>|  
|<span data-ttu-id="2c83f-109">**OmitFormulas**</span><span class="sxs-lookup"><span data-stu-id="2c83f-109">**OmitFormulas**</span></span>|<span data-ttu-id="2c83f-110">Indique s'il faut omettre des formules du rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="2c83f-110">Indicates whether to omit formulas from the rendered report.</span></span> <span data-ttu-id="2c83f-111">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="2c83f-111">The default value is `false`.</span></span>|  
|<span data-ttu-id="2c83f-112">`SimplePageHeade`rs</span><span class="sxs-lookup"><span data-stu-id="2c83f-112">`SimplePageHeade`rs</span></span>|<span data-ttu-id="2c83f-113">Indique si l'en-tête de page du rapport est rendu dans l'en-tête de page Excel.</span><span class="sxs-lookup"><span data-stu-id="2c83f-113">Indicates whether the page header of the report is rendered to the Excel page header.</span></span> <span data-ttu-id="2c83f-114">La valeur `false` indique que l'en-tête de page est rendu dans la première ligne de la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="2c83f-114">A value of `false` indicates that the page header is rendered to the first row of the worksheet.</span></span> <span data-ttu-id="2c83f-115">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="2c83f-115">The default value is `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c83f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c83f-116">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="2c83f-117">[Passage de paramètres d’informations de périphérique aux extensions de rendu](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="2c83f-117">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="2c83f-118">[Personnaliser les paramètres d’extension de rendu dans RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="2c83f-118">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="2c83f-119">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2c83f-119">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
