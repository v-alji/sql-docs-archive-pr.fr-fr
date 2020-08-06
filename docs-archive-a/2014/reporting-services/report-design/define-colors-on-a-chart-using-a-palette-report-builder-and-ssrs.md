---
title: Définir les couleurs d’un graphique à l’aide d’une palette (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d95efc22-5a32-43d4-9bd2-12753e7fd395
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7db137ed87b0c84e43577dcf2936a6287abd8e36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605192"
---
# <a name="define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs"></a><span data-ttu-id="2c614-102">Définir les couleurs d'un graphique à l'aide d'une palette (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="2c614-102">Define Colors on a Chart Using a Palette (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2c614-103">Vous pouvez modifier la palette de couleurs d'un graphique en sélectionnant une palette prédéfinie ou en définissant une palette personnalisée.</span><span class="sxs-lookup"><span data-stu-id="2c614-103">You can change the color palette for a chart by selecting a pre-defined palette or defining a custom palette.</span></span> <span data-ttu-id="2c614-104">Les palettes personnalisées sont spécifiques au rapport.</span><span class="sxs-lookup"><span data-stu-id="2c614-104">Custom palettes are report-specific.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-colors-on-the-chart-using-a-built-in-color-palette"></a><span data-ttu-id="2c614-105">Pour modifier les couleurs sur le graphique à l'aide d'une palette de couleurs prédéfinie</span><span class="sxs-lookup"><span data-stu-id="2c614-105">To change the colors on the chart using a built-in color palette</span></span>  
  
1.  <span data-ttu-id="2c614-106">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2c614-106">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="2c614-107">Dans l'aire de conception, cliquez sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="2c614-107">On the design surface, click the chart.</span></span> <span data-ttu-id="2c614-108">Les propriétés de l'objet graphique sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2c614-108">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
     <span data-ttu-id="2c614-109">Le nom de l’objet (**Chart1** par défaut) apparaît dans la liste déroulante en haut du volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2c614-109">The object name (**Chart1** by default) appears in the drop-down list at the top of the Properties pane.</span></span>  
  
3.  <span data-ttu-id="2c614-110">Dans la section **Chart** , sélectionnez une nouvelle palette dans la liste déroulante pour la propriété Palette.</span><span class="sxs-lookup"><span data-stu-id="2c614-110">In the **Chart** section, for the Palette property, select a new palette from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2c614-111">Vous ne pouvez pas modifier les couleurs ou l'ordre dans une palette prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="2c614-111">You cannot change the colors or order in a pre-defined palette.</span></span>  
  
### <a name="to-define-your-own-colors-on-the-chart-using-a-custom-color-palette"></a><span data-ttu-id="2c614-112">Pour définir vos propres couleurs sur le graphique à l'aide d'une palette de couleurs personnalisée</span><span class="sxs-lookup"><span data-stu-id="2c614-112">To define your own colors on the chart using a custom color palette</span></span>  
  
1.  <span data-ttu-id="2c614-113">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2c614-113">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="2c614-114">Dans l'aire de conception, cliquez sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="2c614-114">On the design surface, click the chart.</span></span> <span data-ttu-id="2c614-115">Les propriétés de l'objet graphique sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2c614-115">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="2c614-116">Dans la section **graphique** , pour la `Palette` propriété, sélectionnez **personnalisé**.</span><span class="sxs-lookup"><span data-stu-id="2c614-116">In the **Chart** section, for the `Palette` property, select **Custom**.</span></span>  
  
4.  <span data-ttu-id="2c614-117">Dans la propriété CustomPaletteColors, cliquez sur le bouton Modifier la collection ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="2c614-117">In the CustomPaletteColors property, click the Edit Collection (**...**) button.</span></span> <span data-ttu-id="2c614-118">L' **Éditeur de collection ReportColorExpression** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="2c614-118">The **ReportColorExpression Collection Editor** opens.</span></span>  
  
5.  <span data-ttu-id="2c614-119">Cliquez sur **Ajouter** pour ajouter une couleur.</span><span class="sxs-lookup"><span data-stu-id="2c614-119">Click **Add** to add a color.</span></span> <span data-ttu-id="2c614-120">Sélectionnez une couleur dans la liste déroulante ou sélectionnez Expression et spécifiez une valeur hexadécimale correspondant à une couleur spécifique, par exemple ff6600 pour l'orange.</span><span class="sxs-lookup"><span data-stu-id="2c614-120">Select a color from the drop-down list or select Expression and specify a hex value for a specific color, such as ff6600 for "Orange".</span></span>  
  
     <span data-ttu-id="2c614-121">Pour plus d'informations sur les valeurs hexadécimales, consultez la [table des couleurs](https://go.microsoft.com/fwlink/?linkid=9258) (en anglais) sur MSDN.</span><span class="sxs-lookup"><span data-stu-id="2c614-121">For more information about hex values, see [Color Table](https://go.microsoft.com/fwlink/?linkid=9258) on MSDN.</span></span>  
  
6.  <span data-ttu-id="2c614-122">Cliquez sur **Ajouter** pour ajouter d'autres couleurs à la palette.</span><span class="sxs-lookup"><span data-stu-id="2c614-122">Click **Add** to add more colors to the palette.</span></span>  
  
7.  <span data-ttu-id="2c614-123">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c614-123">When you are done, click **OK**.</span></span>  
  
 <span data-ttu-id="2c614-124">Si vous utilisez une palette personnalisée, vous pouvez modifier l'ordre des couleurs pour modifier la couleur de différentes séries dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="2c614-124">If you are using a custom palette, you can change the order of the colors to change the color of different series in the chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c614-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c614-125">See Also</span></span>  
 <span data-ttu-id="2c614-126">[Mise en forme des couleurs des séries sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2c614-126">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2c614-127">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2c614-127">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2c614-128">Spécifier des couleurs cohérentes pour plusieurs graphiques à base de formes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2c614-128">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
