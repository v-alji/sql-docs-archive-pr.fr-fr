---
title: Paramètres d’informations de périphérique Word | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Word [Reporting Services]
- device information settings [Reporting Services], Word
ms.assetid: 28146498-fae7-4b13-b47f-6ec05aa8e057
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ddd145c5073003a8dc189e3ed9b1bbb25dc11d09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600506"
---
# <a name="word-device-information-settings"></a><span data-ttu-id="eeaca-102">Paramètres d'informations de périphérique Word</span><span class="sxs-lookup"><span data-stu-id="eeaca-102">Word Device Information Settings</span></span>
  <span data-ttu-id="eeaca-103">Le tableau suivant répertorie les paramètres d'informations de périphérique qui permettent un rendu au format [!INCLUDE[ofprword](../includes/ofprword-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eeaca-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprword](../includes/ofprword-md.md)] format.</span></span>  
  
|<span data-ttu-id="eeaca-104">Paramètre</span><span class="sxs-lookup"><span data-stu-id="eeaca-104">Setting</span></span>|<span data-ttu-id="eeaca-105">Valeur</span><span class="sxs-lookup"><span data-stu-id="eeaca-105">Value</span></span>|  
|-------------|-----------|  
|`AutoFit`|<span data-ttu-id="eeaca-106">`False`.</span><span class="sxs-lookup"><span data-stu-id="eeaca-106">`False`.</span></span> <span data-ttu-id="eeaca-107">L'ajustement automatique a la valeur `false` sur tous les tableaux Word.</span><span class="sxs-lookup"><span data-stu-id="eeaca-107">AutoFit is set to `false` set on any Word table.</span></span><br /><br /> <span data-ttu-id="eeaca-108">`True`.</span><span class="sxs-lookup"><span data-stu-id="eeaca-108">`True`.</span></span> <span data-ttu-id="eeaca-109">L'ajustement automatique a la valeur `true` sur chaque tableau Word.</span><span class="sxs-lookup"><span data-stu-id="eeaca-109">AutoFit is set to `true` on every Word table.</span></span><br /><br /> <span data-ttu-id="eeaca-110">`Never`.</span><span class="sxs-lookup"><span data-stu-id="eeaca-110">`Never`.</span></span> <span data-ttu-id="eeaca-111">Les valeurs d'ajustement automatique ne sont pas définies sur les tableaux Word et le comportement par défaut de Word est rétabli.</span><span class="sxs-lookup"><span data-stu-id="eeaca-111">AutoFit values are not set on any Word table and behavior reverts to the Word default.</span></span><br /><br /> <span data-ttu-id="eeaca-112">`Default`.</span><span class="sxs-lookup"><span data-stu-id="eeaca-112">`Default`.</span></span> <span data-ttu-id="eeaca-113">L'ajustement automatique est défini sur les tableaux qui sont plus étroits que la zone de dessin physique (largeur de page physique, marges exclues) par page logique.</span><span class="sxs-lookup"><span data-stu-id="eeaca-113">AutoFit is set on tables that are narrower than the physical drawing area (physical page width excluding margins) per logical page.</span></span>|  
|`ExpandToggles`|<span data-ttu-id="eeaca-114">Indique si tous les éléments pouvant être activés ou désactivés doivent être rendus dans leur état complètement développé.</span><span class="sxs-lookup"><span data-stu-id="eeaca-114">Indicates whether all items that can be toggled should render in their fully-expanded state.</span></span> <span data-ttu-id="eeaca-115">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="eeaca-115">The default value is `false`.</span></span>|  
|`FixedPageWidth`|<span data-ttu-id="eeaca-116">Indique si la largeur de page écrite dans le fichier DOC peut croître pour accommoder la largeur de la page la plus grande dans le corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="eeaca-116">Indicates whether the Page Width written to the DOC file will grow to accommodate the width of the largest page in the Report Body.</span></span> <span data-ttu-id="eeaca-117">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="eeaca-117">The default value is `false`.</span></span>|  
|<span data-ttu-id="eeaca-118">**OmitHyperlinks**</span><span class="sxs-lookup"><span data-stu-id="eeaca-118">**OmitHyperlinks**</span></span>|<span data-ttu-id="eeaca-119">Indique s'il faut omettre l'action de lien hypertexte sur tous les éléments dans lesquels elle est définie.</span><span class="sxs-lookup"><span data-stu-id="eeaca-119">Indicates whether to omit the Hyperlink action on all items where it is set.</span></span> <span data-ttu-id="eeaca-120">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="eeaca-120">The default value is `false`</span></span>|  
|`OmitDrillthroughs`|<span data-ttu-id="eeaca-121">Indique s'il faut omettre l'action d'extraction sur tous les éléments dans lesquels elle est définie.</span><span class="sxs-lookup"><span data-stu-id="eeaca-121">Indicates whether to omit the Drillthrough action on all items where it is set.</span></span> <span data-ttu-id="eeaca-122">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="eeaca-122">The default value is `false`</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eeaca-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eeaca-123">See Also</span></span>  
 <span data-ttu-id="eeaca-124">[Passage de paramètres d’informations de périphérique aux extensions de rendu](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="eeaca-124">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="eeaca-125">[Personnaliser les paramètres d’extension de rendu dans RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="eeaca-125">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="eeaca-126">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eeaca-126">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
