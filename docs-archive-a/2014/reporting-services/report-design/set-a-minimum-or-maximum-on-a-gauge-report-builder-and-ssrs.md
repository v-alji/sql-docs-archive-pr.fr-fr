---
title: Définir un minimum ou un maximum sur une jauge (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b4c260c0-5a88-4f30-8977-eb5cc78fc146
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 344122dbff647a8c35b838ecce637602f202864b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601888"
---
# <a name="set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="46b35-102">Définir un minimum ou un maximum sur une jauge (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="46b35-102">Set a Minimum or Maximum on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="46b35-103">Contrairement au graphique sur lequel plusieurs groupes sont définis, la jauge affiche seulement une valeur.</span><span class="sxs-lookup"><span data-stu-id="46b35-103">Unlike the chart, where multiple groups are defined, the gauge only shows one value.</span></span> <span data-ttu-id="46b35-104">Étant donné que le Générateur de rapports et le Concepteur de rapports détermine le contexte ou la précision relative de la valeur que vous essayez d'afficher sur la jauge, vous devez définir les valeurs minimale et maximale de l'échelle.</span><span class="sxs-lookup"><span data-stu-id="46b35-104">Since Report Builder and Report Designer determine the context or relative significance of the one value that you are trying to show on the gauge, you must define the minimum and maximum of the scale.</span></span> <span data-ttu-id="46b35-105">Par exemple, si vos valeurs de données sont comprises entre 0 et 10, vous pouvez définir le minimum sur 0 et le maximum sur 10.</span><span class="sxs-lookup"><span data-stu-id="46b35-105">For example, if your data values are rankings between 0 and 10, you will want to set the minimum to 0 and maximum to 10.</span></span> <span data-ttu-id="46b35-106">Les intervalles sont calculés automatiquement en fonction des valeurs spécifiées pour le minimum et le maximum.</span><span class="sxs-lookup"><span data-stu-id="46b35-106">The interval numbers are calculated automatically based on the values specified for the minimum and maximum.</span></span> <span data-ttu-id="46b35-107">Par défaut, le minimum et le maximum sont définis sur 0 et 100, mais il s'agit d'une valeur arbitraire que vous devez modifier.</span><span class="sxs-lookup"><span data-stu-id="46b35-107">By default, the minimum and maximum are set to 0 and 100, but this is an arbitrary value that you should change.</span></span> <span data-ttu-id="46b35-108">L'application ne calcule pas votre valeur sous la forme d'un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="46b35-108">The application does not calculate your value as a percentage.</span></span>  
  
 <span data-ttu-id="46b35-109">Si votre plage de valeurs est large, par exemple de 0 à 10 000, envisagez d'utiliser un multiplicateur pour réduire le nombre de zéros sur la jauge.</span><span class="sxs-lookup"><span data-stu-id="46b35-109">If the range of your values is large, for example from 0 to 10000, consider using a multiplier to reduce the number of zeroes on the gauge.</span></span> <span data-ttu-id="46b35-110">Le multiplicateur réduira uniquement l'échelle des nombres sur la jauge et pas la valeur proprement dite.</span><span class="sxs-lookup"><span data-stu-id="46b35-110">The multiplier will only reduce the scale of the numbers on the gauge, not the value itself.</span></span>  
  
 <span data-ttu-id="46b35-111">Vous pouvez utiliser des expressions pour définir les valeurs des options **Minimum** et **Maximum** .</span><span class="sxs-lookup"><span data-stu-id="46b35-111">You can use expressions to set the values of the **Minimum** and **Maximum** options.</span></span> <span data-ttu-id="46b35-112">Pour plus d’informations, consultez [Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="46b35-112">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-minimum-and-maximum-on-the-gauge"></a><span data-ttu-id="46b35-113">Pour définir le minimum et le maximum sur la jauge</span><span class="sxs-lookup"><span data-stu-id="46b35-113">To set the minimum and maximum on the gauge</span></span>  
  
1.  <span data-ttu-id="46b35-114">Cliquez avec le bouton droit sur l’échelle et sélectionnez **Propriétés de l’échelle**.</span><span class="sxs-lookup"><span data-stu-id="46b35-114">Right-click on the scale and select **Scale Properties**.</span></span> <span data-ttu-id="46b35-115">La boîte de dialogue **Propriétés de l’échelle** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="46b35-115">The **Scale Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="46b35-116">Dans **Général**, spécifiez une valeur pour **Minimum**.</span><span class="sxs-lookup"><span data-stu-id="46b35-116">In **General**, specify a value for **Minimum**.</span></span> <span data-ttu-id="46b35-117">Par défaut, cette valeur est 0.</span><span class="sxs-lookup"><span data-stu-id="46b35-117">By default, this value is 0.</span></span> <span data-ttu-id="46b35-118">Vous pouvez également cliquer sur le bouton **Expression** (*fx*) si vous souhaitez modifier l’expression qui définit la valeur de l’option.</span><span class="sxs-lookup"><span data-stu-id="46b35-118">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
3.  <span data-ttu-id="46b35-119">Spécifiez une valeur pour **Maximum**.</span><span class="sxs-lookup"><span data-stu-id="46b35-119">Specify a value for **Maximum**.</span></span> <span data-ttu-id="46b35-120">Par défaut, il s'agit de 100.</span><span class="sxs-lookup"><span data-stu-id="46b35-120">By default, this value is 100.</span></span> <span data-ttu-id="46b35-121">Vous pouvez également cliquer sur le bouton **Expression** (*fx*) si vous souhaitez modifier l’expression qui définit la valeur de l’option.</span><span class="sxs-lookup"><span data-stu-id="46b35-121">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="46b35-122">(Facultatif) Si les valeurs minimale et maximale sont élevées, spécifiez une valeur pour l’option **Multiplier les étiquettes d’échelle par** .</span><span class="sxs-lookup"><span data-stu-id="46b35-122">(Optional) If the values for your minimum and maximum are large, specify a value for the **Multiply scale labels by** option.</span></span> <span data-ttu-id="46b35-123">Pour spécifier un multiplicateur qui réduit votre échelle, utilisez un nombre décimal.</span><span class="sxs-lookup"><span data-stu-id="46b35-123">To specify a multiplier that reduces your scale, use a decimal number.</span></span> <span data-ttu-id="46b35-124">Par exemple, si vous utilisez une échelle de 0 à 1 000, vous pouvez spécifier une valeur de multiplicateur de 0,01 pour réduire l'échelle afin d'afficher 0 à 10.</span><span class="sxs-lookup"><span data-stu-id="46b35-124">For example, if you have a scale from 0 to 1000, you can specify a multiplier value of 0.01 to reduce the scale to read 0 to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b35-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46b35-125">See Also</span></span>  
 <span data-ttu-id="46b35-126">[Mise en forme des échelles sur une jauge &#40;Générateur de rapports et SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="46b35-126">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="46b35-127">[Mise en forme des pointeurs sur une jauge &#40;Générateur de rapports et SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="46b35-127">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="46b35-128">Jauges &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="46b35-128">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
