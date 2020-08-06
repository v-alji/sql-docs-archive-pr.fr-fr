---
title: Paramètres d’informations de périphérique pour le format de rendu MHTML | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], MHTML rendering
- MHTML [Reporting Services]
ms.assetid: 60b85dd8-b4fb-4ad9-be6a-e7c89ac076fe
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 076a0179871775984799fc8ce5366a220f812867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612199"
---
# <a name="mhtml-device-information-settings"></a><span data-ttu-id="dbd5a-102">Paramètres d'informations de périphérique pour le format de rendu MHTML</span><span class="sxs-lookup"><span data-stu-id="dbd5a-102">MHTML Device Information Settings</span></span>
  <span data-ttu-id="dbd5a-103">Le tableau suivant répertorie les paramètres des informations de périphérique qui permettent de restituer les rapports au format Archive Web MHTML.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-103">The following table lists the device information settings for rendering reports in Web archive (MHTML) format.</span></span>  
  
|<span data-ttu-id="dbd5a-104">Paramètre</span><span class="sxs-lookup"><span data-stu-id="dbd5a-104">Setting</span></span>|<span data-ttu-id="dbd5a-105">Valeur</span><span class="sxs-lookup"><span data-stu-id="dbd5a-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="dbd5a-106">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="dbd5a-106">**JavaScript**</span></span>|<span data-ttu-id="dbd5a-107">Indique si JavaScript est pris en charge dans le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-107">Indicates whether JavaScript is supported in the rendered report.</span></span>|  
|<span data-ttu-id="dbd5a-108">**OutlookCompat**</span><span class="sxs-lookup"><span data-stu-id="dbd5a-108">**OutlookCompat**</span></span>|<span data-ttu-id="dbd5a-109">Indique s'il convient d'effectuer le rendu avec des métadonnées supplémentaires qui font que l'aspect du rapport est meilleur dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-109">Indicates whether to render with extra metadata that makes the report look better in Outlook.</span></span> <span data-ttu-id="dbd5a-110">La valeur par défaut est `true`.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-110">The default value is `true`.</span></span>|  
|<span data-ttu-id="dbd5a-111">**Fragment MHTML**</span><span class="sxs-lookup"><span data-stu-id="dbd5a-111">**MHTML Fragment**</span></span>|<span data-ttu-id="dbd5a-112">Indique si un fragment MHTML est créé à la place d'un document MHTML complet.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-112">Indicates whether an MHTML fragment is created in place of a full MHTML document.</span></span> <span data-ttu-id="dbd5a-113">Les fragments MHTML font figurer le contenu du rapport dans un élément TABLE et omettent les éléments HTML et BODY.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-113">An MHTML fragment includes the report content in a TABLE element and omits the HTML and BODY elements.</span></span> <span data-ttu-id="dbd5a-114">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-114">The default value is `false`.</span></span>|  
|<span data-ttu-id="dbd5a-115">**DataVisualizationFitSizing**</span><span class="sxs-lookup"><span data-stu-id="dbd5a-115">**DataVisualizationFitSizing**</span></span>|<span data-ttu-id="dbd5a-116">Indique le comportement d'ajustement de la visualisation des données à l'intérieur d'un tableau matriciel.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-116">Indicates data visualization fit behavior when inside a tablix.</span></span> <span data-ttu-id="dbd5a-117">Cela inclut le graphique, la jauge et la carte.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-117">This includes chart, gauge, and map.</span></span><br /><br /> <span data-ttu-id="dbd5a-118">Les valeurs possibles sont **Approximatif** et **Exact**.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-118">The possible values are **Approximate** and **Exact**.</span></span><br /><br /> <span data-ttu-id="dbd5a-119">La valeur par défaut est **Approximatif**.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-119">The default value is **Approximate**.</span></span> <span data-ttu-id="dbd5a-120">Si le paramètre est supprimé du fichier **rsreportserver.config** , le comportement par défaut est **Exact**.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-120">If the setting is removed from the **rsreportserver.config** file then the default behavior is **Exact**.</span></span><br /><br /> <span data-ttu-id="dbd5a-121">L’activation de l’option **Exact** peut avoir un impact sur les performances, car le traitement permettant de déterminer la taille peut prendre plus de temps.</span><span class="sxs-lookup"><span data-stu-id="dbd5a-121">Enabling **Exact** may have performance impact because the processing to determine the exact size may take longer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbd5a-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbd5a-122">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="dbd5a-123">[Transmission de paramètres d'informations de périphérique aux extensions de rendu](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="dbd5a-123">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="dbd5a-124">[Personnaliser les paramètres d’extension de rendu dans RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="dbd5a-124">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="dbd5a-125">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dbd5a-125">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
