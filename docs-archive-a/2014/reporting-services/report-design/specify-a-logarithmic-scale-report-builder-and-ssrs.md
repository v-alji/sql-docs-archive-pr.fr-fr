---
title: Spécifier une échelle logarithmique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f3092c1c-b128-433d-9a95-983508b2a8d4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cc422a6f95a420445dc604d08a23e8f8e65c95d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600519"
---
# <a name="specify-a-logarithmic-scale-report-builder-and-ssrs"></a><span data-ttu-id="ea6b5-102">Spécifier une échelle logarithmique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ea6b5-102">Specify a Logarithmic Scale (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ea6b5-103">Si vos données sont proportionnelles d'un point de vue logarithmique, vous pouvez envisager d'utiliser une échelle logarithmique sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-103">If you have data that is logarithmically proportional, you may want to consider using a logarithmic scale on the chart.</span></span> <span data-ttu-id="ea6b5-104">Vous améliorerez ainsi l'apparence du graphique en facilitant la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-104">This helps improve the appearance of the chart by making your data more manageable.</span></span> <span data-ttu-id="ea6b5-105">La plupart des échelles logarithmiques utilisent une base 10.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-105">Most logarithmic scales use a base of 10.</span></span>  
  
 <span data-ttu-id="ea6b5-106">Cette fonctionnalité est uniquement disponible sur l'axe des ordonnées.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-106">This feature is only available on the value axis.</span></span> <span data-ttu-id="ea6b5-107">L'axe des ordonnées est généralement l'axe vertical, ou axe des Y.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-107">The value axis is usually the vertical, or y-axis.</span></span> <span data-ttu-id="ea6b5-108">Toutefois, dans les graphiques à barres, il s'agit de l'axe horizontal, ou axe des X.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-108">On bar charts, however, it is the horizontal, or x-axis.</span></span>  
  
 <span data-ttu-id="ea6b5-109">Avec un axe logarithmique, toutes les autres propriétés concernant l'axe seront mises à l'échelle de façon logarithmique.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-109">If your axis is logarithmic, all other properties relating to the axis will be scaled logarithmically.</span></span> <span data-ttu-id="ea6b5-110">Par exemple, si vous spécifiez une échelle logarithmique de base 10 sur votre axe, la définition d'un intervalle d'axe égal à 2 générera des intervalles de 10 à la puissance 2, soit 100.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-110">For example, if you specify a base-10 logarithmic scale on your axis, setting an axis interval of 2 will generate intervals in magnitudes of 10 to the power of 2, or 100.</span></span> <span data-ttu-id="ea6b5-111">Cela signifie que vos valeurs d'axe indiqueront 1, 100, 10 000, au lieu du résultat par défaut 1, 10, 100, 1 000, 10 000.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-111">This means your axis values will read 1, 100, 10000, instead of the default result of 1, 10, 100, 1000, 10000.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-logarithmic-scale"></a><span data-ttu-id="ea6b5-112">Pour spécifier une échelle logarithmique</span><span class="sxs-lookup"><span data-stu-id="ea6b5-112">To specify a logarithmic scale</span></span>  
  
1.  <span data-ttu-id="ea6b5-113">Cliquez avec le bouton droit sur l’axe des ordonnées de votre graphique, puis cliquez sur **Propriétés de l’axe vertical**.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-113">Right-click the y-axis of your chart, and click **VerticalAxis Properties**.</span></span> <span data-ttu-id="ea6b5-114">La boîte de dialogue **Propriétés de l’axe vertical** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-114">The **VerticalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="ea6b5-115">Dans **Options de l’axe**, sélectionnez **Utiliser l’échelle logarithmique**.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-115">In **Axis Options**, select **Uselogarithmic scale**.</span></span>  
  
3.  <span data-ttu-id="ea6b5-116">Dans la zone de texte **Base logarithmique** , tapez une valeur positive pour la base logarithmique.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-116">In the **Logbase** text box, type a positive value for the logarithmic base.</span></span> <span data-ttu-id="ea6b5-117">Si aucune valeur n'est spécifiée, la base logarithmique par défaut est 10.</span><span class="sxs-lookup"><span data-stu-id="ea6b5-117">If no value is specified, the logarithmic base defaults to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea6b5-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea6b5-118">See Also</span></span>  
 <span data-ttu-id="ea6b5-119">[Mise en forme des étiquettes des axes sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ea6b5-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ea6b5-120">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ea6b5-120">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ea6b5-121">[Mettre en forme les étiquettes des axes en tant que dates ou devises &#40;Générateur de rapports et SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ea6b5-121">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ea6b5-122">Graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ea6b5-122">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
