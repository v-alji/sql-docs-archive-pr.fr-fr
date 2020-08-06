---
title: Spécifier des couleurs cohérentes pour plusieurs graphiques à formes (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d52f68e9-2ba7-4bff-9053-4089e5164ab4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c2c89f0f8cda3b7d6ef6b2acbd0de66c87170357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600517"
---
# <a name="specify-consistent-colors-across-multiple-shape-charts-report-builder-and-ssrs"></a><span data-ttu-id="1d37e-102">Spécifier des couleurs cohérentes pour plusieurs graphiques à base de formes (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="1d37e-102">Specify Consistent Colors across Multiple Shape Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1d37e-103">Sur les graphiques qui ne sont pas à base de formes, une nouvelle couleur est sélectionnée dans la palette en fonction de l’index de la série dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="1d37e-103">On non-shape charts, a new color is selected from the palette based on the index of series in the chart.</span></span> <span data-ttu-id="1d37e-104">Par exemple, la première série sur votre graphique sera associée à la première couleur dans la palette.</span><span class="sxs-lookup"><span data-stu-id="1d37e-104">For example, the first series on your chart will be mapped to the first color in the palette.</span></span> <span data-ttu-id="1d37e-105">Toutefois, ce comportement diffère pour les graphiques à base de formes.</span><span class="sxs-lookup"><span data-stu-id="1d37e-105">However, this behavior differs for shape charts.</span></span> <span data-ttu-id="1d37e-106">Sur les graphiques à base de formes, chaque couleur de la palette est associée à un point de données dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="1d37e-106">On shape charts, each color in the palette is mapped to a data point in the dataset.</span></span> <span data-ttu-id="1d37e-107">Par exemple, le point de données 1 est associé à la première couleur de la palette, le point de données 2 est associé à la deuxième couleur et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="1d37e-107">For example, data point 1 is mapped to the first color in the palette, data point 2 is mapped to the second color palette and so on.</span></span>  
  
 <span data-ttu-id="1d37e-108">Si un point de données n'a aucune valeur, il n'apparaît pas sur l'affichage du graphique à base de formes.</span><span class="sxs-lookup"><span data-stu-id="1d37e-108">If a data point has no value, it is omitted from display on a shape chart.</span></span> <span data-ttu-id="1d37e-109">Cela signifie que ce point de données n'est pas coloré.</span><span class="sxs-lookup"><span data-stu-id="1d37e-109">This means that the data point is skipped from being colored.</span></span> <span data-ttu-id="1d37e-110">Par exemple, si le point 2 a une valeur de zéro, le point 1 sera associé à la première couleur de la palette et le point 3 sera associé à la deuxième couleur de la palette.</span><span class="sxs-lookup"><span data-stu-id="1d37e-110">For example, if point 2 has a value of zero, point 1 will be mapped to the first color in the palette, and point 3 will be mapped to the second color in the palette.</span></span> <span data-ttu-id="1d37e-111">Cette approche est utile car les points vides dans le dataset d'un graphique à secteurs n'utilisent pas inutilement une couleur de la palette lorsque le point vide ne doit pas être dessiné.</span><span class="sxs-lookup"><span data-stu-id="1d37e-111">This approach is useful because the empty points in the dataset of a pie chart do not unnecessarily use a palette color when the empty point does not need to be drawn.</span></span>  
  
 <span data-ttu-id="1d37e-112">En corollaire, lorsque plusieurs graphiques à secteurs sont affichés dans un rapport, les graphiques à secteurs peuvent afficher des couleurs différentes pour des points de données correspondant aux mêmes regroupements de catégories.</span><span class="sxs-lookup"><span data-stu-id="1d37e-112">As a side effect, when multiple pie charts are displayed in a report, the pie charts may display different colors for data points that have the same category grouping.</span></span> <span data-ttu-id="1d37e-113">Pour pallier cet inconvénient, vous devez définir des couleurs individuelles associées à un groupe de catégories et non à des valeurs de données individuelles.</span><span class="sxs-lookup"><span data-stu-id="1d37e-113">To resolve this, you need to define individual colors that map to a category group instead of individual data values.</span></span> <span data-ttu-id="1d37e-114">La façon dont vous procédez varie si les graphiques à base de formes sont des graphiques sparkline dans une table ou matrice, ou s'il s'agit de graphiques à base de formes dans le rapport lui-même.</span><span class="sxs-lookup"><span data-stu-id="1d37e-114">How you do this depends on if the shape charts are sparklines in a table or matrix, or if they are shape charts in the report itself.</span></span>  
  
 <span data-ttu-id="1d37e-115">La légende est liée à la série, donc toute couleur que vous spécifiez pour la série sera automatiquement utilisée pour la légende.</span><span class="sxs-lookup"><span data-stu-id="1d37e-115">The legend is connected to the series, so any color you specify for the series will automatically be shown on the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-consistent-colors-across-multiple-sparkline-shape-charts-in-a-table-or-matrix"></a><span data-ttu-id="1d37e-116">Pour spécifier des couleurs cohérentes pour plusieurs graphiques à base de formes sparkline dans une table ou matrice</span><span class="sxs-lookup"><span data-stu-id="1d37e-116">To specify consistent colors across multiple sparkline shape charts in a table or matrix</span></span>  
  
1.  <span data-ttu-id="1d37e-117">Cliquez sur le graphique pour afficher le volet Données du graphique.</span><span class="sxs-lookup"><span data-stu-id="1d37e-117">Click the chart to display the Chart Data pane.</span></span>  
  
2.  <span data-ttu-id="1d37e-118">Dans la zone **Groupes de catégories** , cliquez avec le bouton droit sur une catégorie, puis cliquez sur **Propriétés du groupe de catégories**.</span><span class="sxs-lookup"><span data-stu-id="1d37e-118">In the **Category Groups** area, right-click a category and click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="1d37e-119">Sous l'onglet Général, dans la zone **Synchroniser les groupes dans** , cliquez sur le nom de la catégorie pour laquelle vous aimeriez synchroniser des couleurs, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d37e-119">On the General tab, in the **Synchronize groups in** box, click the name of the category for which you would like to synchronize colors, and then click **OK**.</span></span>  
  
### <a name="to-specify-consistent-colors-across-multiple-shape-charts"></a><span data-ttu-id="1d37e-120">Pour spécifier des couleurs cohérentes pour plusieurs graphiques à base de formes</span><span class="sxs-lookup"><span data-stu-id="1d37e-120">To specify consistent colors across multiple shape charts</span></span>  
  
1.  <span data-ttu-id="1d37e-121">Cliquez avec le bouton droit à l’extérieur du corps du rapport, puis sélectionnez **Propriétés du rapport**.</span><span class="sxs-lookup"><span data-stu-id="1d37e-121">Right-click outside the body of the report, and select **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="1d37e-122">Dans **Code**, tapez le code suivant dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="1d37e-122">In **Code**, type the following code into the textbox.</span></span>  
  
    ```  
    Private colorPalette As String() = {"Color1", "Color2", "Color3"}  
    Private count As Integer = 0  
    Private mapping As New System.Collections.Hashtable()  
    Public Function GetColor(ByVal groupingValue As String) As String  
        If mapping.ContainsKey(groupingValue) Then  
            Return mapping(groupingValue)  
        End If  
        Dim c As String = colorPalette(count Mod colorPalette.Length)  
        count = count + 1  
        mapping.Add(groupingValue, c)  
        Return c  
    End Function  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="1d37e-123">Vous devez remplacer les chaînes "Color1" par vos propres couleurs.</span><span class="sxs-lookup"><span data-stu-id="1d37e-123">You will need to replace the "Color1" strings with your own colors.</span></span> <span data-ttu-id="1d37e-124">Vous pouvez utiliser des couleurs nommées, par exemple "Rouge", ou vous pouvez utiliser valeur hexadécimale de six chiffres qui représente la couleur, par exemple "#FFFFFF" pour le noir.</span><span class="sxs-lookup"><span data-stu-id="1d37e-124">You can use named colors, for example "Red", or you can use six-digit hexadecimal value that represent the color, such as "#FFFFFF" for black.</span></span> <span data-ttu-id="1d37e-125">Si plus de trois couleurs sont définies, vous devez étendre le tableau de couleurs afin que le nombre de couleurs dans le tableau corresponde au nombre de points de votre graphique à base de formes.</span><span class="sxs-lookup"><span data-stu-id="1d37e-125">If you have more than three colors defined, you will need to extend the array of colors so that the number of colors in the array matches the number of points in your shape chart.</span></span> <span data-ttu-id="1d37e-126">Vous pouvez ajouter de nouvelles couleurs au tableau en spécifiant une liste séparée par des virgules de valeurs de chaîne qui contiennent des couleurs nommées ou des représentations hexadécimales de couleurs.</span><span class="sxs-lookup"><span data-stu-id="1d37e-126">You can add new colors to the array by specifying a comma-separated list of string values that contain named colors or hexadecimal representations of colors.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="1d37e-127">Cliquez avec le bouton droit sur le graphique à base de formes, puis sélectionnez **Propriétés de la série**.</span><span class="sxs-lookup"><span data-stu-id="1d37e-127">Right-click on the shape chart and select **Series Properties**.</span></span>  
  
5.  <span data-ttu-id="1d37e-128">Dans **Remplir**, cliquez sur le bouton **Expression** (*fx*) pour modifier l’expression pour la propriété **Couleur** .</span><span class="sxs-lookup"><span data-stu-id="1d37e-128">In **Fill**, click the **Expression** (*fx*) button to edit the expression for the **Color** property.</span></span>  
  
6.  <span data-ttu-id="1d37e-129">Tapez l'expression suivante, où « MyCategoryField » est le champ affiché dans la zone **Groupes d'abscisses** :</span><span class="sxs-lookup"><span data-stu-id="1d37e-129">Type the following expression, where "MyCategoryField" is the field that is displayed in the **Category Groups** area:</span></span>  
  
    ```  
    =Code.GetColor(Fields!MyCategoryField)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1d37e-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d37e-130">See Also</span></span>  
 <span data-ttu-id="1d37e-131">[Mise en forme des couleurs des séries sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d37e-131">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1d37e-132">[Ajouter des styles de biseau, de relief et de texture à un graphique &#40;Générateur de rapports et SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="1d37e-132">[Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span></span>  
 <span data-ttu-id="1d37e-133">[Définir les couleurs d’un graphique à l’aide d’une palette &#40;Générateur de rapports et SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d37e-133">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1d37e-134">[Ajouter des points vides au graphique &#40;Générateur de rapports et SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d37e-134">[Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1d37e-135">[Graphiques à base de formes &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d37e-135">[Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1d37e-136">[Liaison de plusieurs régions de données à un même dataset &#40;Générateur de rapports et SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d37e-136">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1d37e-137">[Régions de données imbriquées &#40;Générateur de rapports et SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d37e-137">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1d37e-138">Graphiques sparkline et barres de données &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1d37e-138">Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
