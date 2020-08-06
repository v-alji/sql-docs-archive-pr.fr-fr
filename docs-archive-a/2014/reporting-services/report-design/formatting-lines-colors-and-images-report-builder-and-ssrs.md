---
title: Mise en forme des lignes, couleurs et images (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.textboxproperties.border.f1
- "10502"
- "10094"
- sql12.rtp.rptdesigner.pictureproperties.border.f1
- "10063"
- sql12.rtp.rptdesigner.rectangleproperties.border.f1
- "10055"
- sql12.rtp.rptdesigner.subreportproperties.border.f1
- "10126"
- sql12.rtp.rptdesigner.shared.borderdv.f1
- "10066"
- sql12.rtp.rptdesigner.reportbody.border.f1
ms.assetid: 0f5f0d2a-9537-4152-b441-b40d7f04cf4c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 681ff6b46f692804aef5c7cbbc16e5abe99dbb2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695379"
---
# <a name="formatting-lines-colors-and-images-report-builder-and-ssrs"></a><span data-ttu-id="27bea-102">Mise en forme des lignes, couleurs et images (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="27bea-102">Formatting Lines, Colors, and Images (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="27bea-103">vous donne la possibilité de mettre en forme des lignes, des couleurs, des régions de données, des images ainsi que d'autres éléments de rapport.</span><span class="sxs-lookup"><span data-stu-id="27bea-103">gives you the ability to format lines, colors, data regions, images, and other report items.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="borders-lines-and-gridlines"></a><span data-ttu-id="27bea-104">Bordures, lignes et quadrillages</span><span class="sxs-lookup"><span data-stu-id="27bea-104">Borders, Lines and Gridlines</span></span>  
 <span data-ttu-id="27bea-105">Les bordures, lignes et quadrillages permettent de regrouper visuellement des éléments dans la page et aident les lecteurs à lire facilement le contenu des rapports.</span><span class="sxs-lookup"><span data-stu-id="27bea-105">Borders, lines, and gridlines can visually tie items together on the page and help your report readers easily read the contents of the report.</span></span> <span data-ttu-id="27bea-106">Grâce aux styles de bordure prédéfinis, vous pouvez ajouter rapidement une bordure autour d'une zone de texte, d'un groupe de zones de texte ou d'une image.</span><span class="sxs-lookup"><span data-stu-id="27bea-106">Using the predefined border styles, you can quickly add a border around a text box, a group of text boxes, or an image.</span></span> <span data-ttu-id="27bea-107">Vous pouvez en outre modifier le style, la largeur et la couleur des bordures, lignes et quadrillages.</span><span class="sxs-lookup"><span data-stu-id="27bea-107">In addition, you can change the style, width, and color for the borders, lines, and gridlines.</span></span> <span data-ttu-id="27bea-108">Les bordures sont ajoutées autour de l'élément entier sélectionné ou autour d'une bordure située le long d'un bord de l'élément, par exemple une bordure le long de la partie inférieure d'une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="27bea-108">Borders are added around the entire item selected or around a border along an edge of the item, for example, a border along the bottom of a text box.</span></span>  
  
 <span data-ttu-id="27bea-109">Pour mettre en forme des bordures et quadrillages dans une zone de texte, une disposition de rapport ou autour d'une image, utilisez l'onglet **Bordure** de la boîte de dialogue **Propriétés** de l'élément de rapport en question.</span><span class="sxs-lookup"><span data-stu-id="27bea-109">To format borders and gridlines in a text box, report layout, or around an image, use the **Border** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="27bea-110">Par exemple, si vous voulez ajouter une bordure autour d’une image, cliquez avec le bouton droit sur l’image, puis dans la boîte de dialogue **Propriétés de l’image** , cliquez sur **Bordure**.</span><span class="sxs-lookup"><span data-stu-id="27bea-110">For example, if you want to add a border around an image, right-click the image and then in the **Image Properties** dialog box, click **Border**.</span></span>  
  
 <span data-ttu-id="27bea-111">En plus des cadres de bordure standard, vous pouvez appliquer aux graphiques d'autres cadres de bordure.</span><span class="sxs-lookup"><span data-stu-id="27bea-111">In addition to the standard border frames, additional border frames can be applied to charts.</span></span> <span data-ttu-id="27bea-112">Pour plus d’informations, consultez [Ajouter un cadre de bordure à un graphique &#40;Générateur de rapports et SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27bea-112">For more information, see [Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="27bea-113">Vous pouvez également ajouter une bordure au rapport lui-même.</span><span class="sxs-lookup"><span data-stu-id="27bea-113">You can also add a border to the report itself.</span></span> <span data-ttu-id="27bea-114">Pour plus d’informations, consultez [Ajouter une bordure à un rapport &#40;Générateur de rapports et SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27bea-114">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="applying-background-colors"></a><span data-ttu-id="27bea-115">Application de couleurs d'arrière-plan</span><span class="sxs-lookup"><span data-stu-id="27bea-115">Applying Background Colors</span></span>  
 <span data-ttu-id="27bea-116">Vous pouvez ajouter une couleur unie à l'arrière-plan d'un rapport entier, à une zone de texte au sein du rapport ou bien à une cellule ou à un groupe de cellules dans une région de données.</span><span class="sxs-lookup"><span data-stu-id="27bea-116">A solid color can be added to the background of the entire report, a text box within the report, or to a cell or group of cells within a data region.</span></span> <span data-ttu-id="27bea-117">Par défaut, la couleur d'arrière-plan est le blanc. Vous pouvez toutefois sélectionner une autre couleur sous l'onglet **Remplissage** de la boîte de dialogue **Propriétés** de l'élément de rapport en question.</span><span class="sxs-lookup"><span data-stu-id="27bea-117">By default, the background color is white; however, you can select a color from the **Fill** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="27bea-118">Par exemple, si vous voulez modifier la couleur d’arrière-plan d’une zone de texte, cliquez avec le bouton droit sur la zone de texte, puis sélectionnez **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="27bea-118">For example, if you want to change the background color of a text box, right-click the text box and select **Text Box Properties**.</span></span> <span data-ttu-id="27bea-119">Cliquez sur **Remplissage** , puis sélectionnez la couleur voulue.</span><span class="sxs-lookup"><span data-stu-id="27bea-119">Click **Fill** and then select the color you want.</span></span> <span data-ttu-id="27bea-120">Vous pouvez sélectionner dans cette boîte de dialogue une couleur d'arrière-plan pour l'élément sélectionné ou vous pouvez ajouter une image qui apparaît en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="27bea-120">In this dialog box, you can select a background color for the selected item or you can add an image that appears in the background.</span></span>  
  
 <span data-ttu-id="27bea-121">Lorsque vous utilisez un graphique, vous pouvez également spécifier des dégradés et des styles de motif pour les couleurs d'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="27bea-121">When you use the chart, you can also specify gradients and pattern styles for background colors.</span></span> <span data-ttu-id="27bea-122">Pour plus d’informations, consultez [Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27bea-122">For more information, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="using-images-as-formatting"></a><span data-ttu-id="27bea-123">Utilisation d'images pour la mise en forme</span><span class="sxs-lookup"><span data-stu-id="27bea-123">Using Images as Formatting</span></span>  
 <span data-ttu-id="27bea-124">Les champs contenant des images peuvent être ajoutés à une région de données.</span><span class="sxs-lookup"><span data-stu-id="27bea-124">Fields that contain images can be added to a data region.</span></span> <span data-ttu-id="27bea-125">Si vous utilisez un champ d'image, les images apparaissent dans le rapport lorsque celui-ci est exécuté.</span><span class="sxs-lookup"><span data-stu-id="27bea-125">If you use an image field, the images appear in the report with the report is run.</span></span>  
  
 <span data-ttu-id="27bea-126">Vous pouvez également ajouter des images telles que des logos à l'arrière-plan de votre rapport, à un rectangle, une zone de texte, un tableau, une matrice ou toute partie d'un graphique, ainsi qu'aux sections de corps et de page d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="27bea-126">You can also add images such as logos to the background of your report or to a rectangle, text box, table, matrix, or some parts of a chart, or to the body and page sections of a report.</span></span> <span data-ttu-id="27bea-127">Pour plus d’informations, consultez [Images &#40;Générateur de rapports et SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27bea-127">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27bea-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27bea-128">See Also</span></span>  
 <span data-ttu-id="27bea-129">[Mise en forme du texte et des espaces réservés &#40;Générateur de rapports et SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27bea-129">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27bea-130">[Mise en forme des nombres et des dates &#40;Générateur de rapports et SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27bea-130">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27bea-131">[Mettre en forme du texte dans une zone de texte &#40;Générateur de rapports et SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27bea-131">[Format Text in a Text Box &#40;Report Builder and SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="27bea-132">Boîte de dialogue Remplissage &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="27bea-132">Fill Dialog Box &#40;Report Builder and SSRS&#41;</span></span>](../fill-dialog-box-report-builder-and-ssrs.md)  
  
  
