---
title: Définir un intervalle d’alignement sur une jauge (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0ece7297-6e2f-47fb-835d-b9e9cce53fe2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdc2a621c4406791838d97e93f47cd32fa9d5f94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703780"
---
# <a name="set-a-snapping-interval-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="14f45-102">Définir un intervalle d'alignement sur une jauge (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="14f45-102">Set a Snapping Interval on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="14f45-103">Un intervalle d'alignement définit le multiple auquel les valeurs sont arrondies.</span><span class="sxs-lookup"><span data-stu-id="14f45-103">A snapping interval defines the multiple to which values are rounded.</span></span> <span data-ttu-id="14f45-104">Par défaut, la jauge pointera sur la valeur exacte du champ que vous avez spécifiée dans le volet des données.</span><span class="sxs-lookup"><span data-stu-id="14f45-104">By default, the gauge will point to the exact value of the field you have specified in the data pane.</span></span> <span data-ttu-id="14f45-105">Toutefois, vous pouvez arrondir la valeur exacte vers le haut ou vers le haut afin que le pointeur s’aligne sur un intervalle prédéfini.</span><span class="sxs-lookup"><span data-stu-id="14f45-105">However, you may want to round the exact value up or down so that the pointer will snap to a preset interval.</span></span> <span data-ttu-id="14f45-106">Par exemple, si la valeur sur votre jauge est 34,2 et que vous spécifiez un intervalle d'alignement de 5, le pointeur de jauge pointera sur 35.</span><span class="sxs-lookup"><span data-stu-id="14f45-106">For example, if the value on your gauge is 34.2 and you specify a snapping interval of 5, the gauge pointer will point to 35.</span></span> <span data-ttu-id="14f45-107">Si la valeur sur votre jauge est 31,2 et que vous spécifiez un intervalle d'alignement de 5, le pointeur de jauge pointera sur 30.</span><span class="sxs-lookup"><span data-stu-id="14f45-107">If the value on your gauge is 31.2 and you specify a snapping interval of 5, the gauge pointer will point to 30.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-snapping-interval-on-a-gauge"></a><span data-ttu-id="14f45-108">Pour définir un intervalle d'alignement sur une jauge</span><span class="sxs-lookup"><span data-stu-id="14f45-108">To set a snapping interval on a gauge</span></span>  
  
1.  <span data-ttu-id="14f45-109">Cliquez n'importe où sur les numéros de la jauge pour mettre en surbrillance l'échelle.</span><span class="sxs-lookup"><span data-stu-id="14f45-109">Click anywhere on the numbers of the gauge to highlight the scale.</span></span>  
  
2.  <span data-ttu-id="14f45-110">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="14f45-110">Open the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="14f45-111">Si vous ne voyez pas le volet Propriétés, cliquez sur l’onglet **affichage** , puis activez la case à cocher **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="14f45-111">If you do not see the Properties pane, click the **View** tab and then select the **Properties** checkbox.</span></span>  
  
3.  <span data-ttu-id="14f45-112">Dans la propriété **pointeurs** , cliquez sur le bouton (...).</span><span class="sxs-lookup"><span data-stu-id="14f45-112">In the **Pointers** property, click the (...) button.</span></span> <span data-ttu-id="14f45-113">L'Éditeur de collections du pointeur s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="14f45-113">The Pointer Collection Editor opens.</span></span>  
  
4.  <span data-ttu-id="14f45-114">Affectez à la propriété **SnappingEnabled** la valeur `True` .</span><span class="sxs-lookup"><span data-stu-id="14f45-114">Set the **SnappingEnabled** property to `True`.</span></span>  
  
5.  <span data-ttu-id="14f45-115">Définissez **SnappingInterval** sur une valeur qui représente l’intervalle d’alignement.</span><span class="sxs-lookup"><span data-stu-id="14f45-115">Set the **SnappingInterval** to a value that represents the snapping interval.</span></span> <span data-ttu-id="14f45-116">Le pointeur sera aligné sur le multiple rond le plus proche de la valeur que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="14f45-116">The pointer will be snapped to the nearest round multiple of the value that you have specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f45-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14f45-117">See Also</span></span>  
 <span data-ttu-id="14f45-118">[Mise en forme des échelles sur une jauge &#40;Générateur de rapports et SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14f45-118">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="14f45-119">[Mise en forme des pointeurs sur une jauge &#40;Générateur de rapports et SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14f45-119">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="14f45-120">Jauges &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="14f45-120">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
