---
title: Mise en forme de plages sur une jauge (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ffdec8ca-3e95-41cd-850b-9e8c83be4b49
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29574c58eef6f18d685b48dd8d695a5fc42c3e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695367"
---
# <a name="formatting-ranges-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="ad22c-102">Mise en forme de plages sur une jauge (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ad22c-102">Formatting Ranges on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ad22c-103">Une plage de jauge est une zone ou une partie de l'échelle de la jauge qui indique une sous-section importante de valeurs sur la jauge.</span><span class="sxs-lookup"><span data-stu-id="ad22c-103">A gauge range is a zone or area on the gauge scale that indicates an important subsection of values on the gauge.</span></span> <span data-ttu-id="ad22c-104">Une plage de jauge vous permet d'indiquer visuellement lorsque la valeur de pointeur entre dans une certaine plage de valeurs.</span><span class="sxs-lookup"><span data-stu-id="ad22c-104">Using a gauge range, you can visually indicate when the pointer value has gone into a certain span of values.</span></span> <span data-ttu-id="ad22c-105">Les plages sont délimitées par une valeur de début et une valeur de fin.</span><span class="sxs-lookup"><span data-stu-id="ad22c-105">Ranges are defined by a start value and an end value.</span></span>  
  
 <span data-ttu-id="ad22c-106">Vous pouvez également utiliser des plages pour définir des différentes sections d'une jauge.</span><span class="sxs-lookup"><span data-stu-id="ad22c-106">You can also use ranges to define different sections of a gauge.</span></span> <span data-ttu-id="ad22c-107">Par exemple, sur une jauge dont les valeurs vont de 0 à 10, vous pouvez définir une plage rouge pour les valeurs de 0 à 3, une plage jaune pour les valeurs de 4 à 7 et une plage verte pour les valeurs de 8 à 10.</span><span class="sxs-lookup"><span data-stu-id="ad22c-107">For example, on a gauge with values from 0 to 10, you can define a red range that has a value from 0 to 3, a yellow range that has a value from 4 to 7 and a green range that has a value from 8 to 10.</span></span> <span data-ttu-id="ad22c-108">Si la valeur de début que vous avez spécifiée est supérieure à la valeur de fin spécifiée, les valeurs sont inversées, la valeur de début devenant alors la valeur de fin et vice versa.</span><span class="sxs-lookup"><span data-stu-id="ad22c-108">If the start value that you specified is greater than the end value that you specified, the values are swapped so that the start value is the end value and the end value is the start value.</span></span>  
  
 <span data-ttu-id="ad22c-109">Vous pouvez positionner la plage comme vous positionnez des pointeurs sur une échelle.</span><span class="sxs-lookup"><span data-stu-id="ad22c-109">You can position the range in the same way that you position pointers on a scale.</span></span> <span data-ttu-id="ad22c-110">Les propriétés **Position** et **Distance par rapport à l’échelle** déterminent la position de la plage.</span><span class="sxs-lookup"><span data-stu-id="ad22c-110">The **Position** and **Distance from scale** properties determine the position of the range.</span></span> <span data-ttu-id="ad22c-111">Pour plus d’informations, consultez [Jauges &#40;Générateur de rapports et SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ad22c-111">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad22c-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad22c-112">See Also</span></span>  
 <span data-ttu-id="ad22c-113">[Mise en forme des échelles sur une jauge &#40;Générateur de rapports et SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ad22c-113">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ad22c-114">[Mise en forme des pointeurs sur une jauge &#40;Générateur de rapports et SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ad22c-114">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ad22c-115">[Définir un minimum ou un maximum sur une jauge &#40;Générateur de rapports et SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ad22c-115">[Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ad22c-116">[Didacticiel : ajout d’un indicateur de performance clé à un rapport &#40;Générateur de rapports&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="ad22c-116">[Tutorial: Adding a KPI to Your Report &#40;Report Builder&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span></span>  
 [<span data-ttu-id="ad22c-117">Jauges &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ad22c-117">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
