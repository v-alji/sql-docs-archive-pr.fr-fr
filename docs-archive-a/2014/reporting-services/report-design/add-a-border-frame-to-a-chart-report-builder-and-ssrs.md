---
title: Ajouter un cadre de bordure à un graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ca0c5040-40bb-4cb7-bc2b-5bcbe73858bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c91d3de00caa4eab6ed1894042b2214b7dcf4b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707167"
---
# <a name="add-a-border-frame-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="274f2-102">Ajouter un cadre de bordure à un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="274f2-102">Add a Border Frame to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="274f2-103">Pour donner un impact plus visuel à un graphique, envisagez d'utiliser un cadre de bordure autour de l'extérieur du graphique.</span><span class="sxs-lookup"><span data-stu-id="274f2-103">To give a chart more visual impact, consider using a border frame around the outside of the chart.</span></span> <span data-ttu-id="274f2-104">Vous pouvez sélectionner un cadre de bordure à l'aide de la boîte de dialogue **Propriétés du graphique** ou du volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="274f2-104">You can select a border frame by using the **Chart Properties** dialog box or by using the Properties pane.</span></span> <span data-ttu-id="274f2-105">Les cadres de bordure de graphique ne peuvent être appliqués à aucune autre région de données.</span><span class="sxs-lookup"><span data-stu-id="274f2-105">The chart border frames cannot be applied to any other data region.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-a-border-to-a-chart"></a><span data-ttu-id="274f2-106">Pour appliquer une bordure à un graphique</span><span class="sxs-lookup"><span data-stu-id="274f2-106">To apply a border to a chart</span></span>  
  
1.  <span data-ttu-id="274f2-107">Cliquez avec le bouton droit en un point quelconque du graphique, puis sélectionnez **Propriétés du graphique**.</span><span class="sxs-lookup"><span data-stu-id="274f2-107">Right-click anywhere on the chart and select **Chart Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="274f2-108">Si **Propriétés du graphique**n’est pas visible, pointez sur **Graphique** dans le menu contextuel et sélectionnez **Propriétés du graphique**.</span><span class="sxs-lookup"><span data-stu-id="274f2-108">If you do not see the **Chart Properties**, point to **Chart** on the shortcut menu and select **Chart Properties**.</span></span>  
  
2.  <span data-ttu-id="274f2-109">Sélectionnez **Bordure**et cliquez sur le type de bordure à appliquer au graphique.</span><span class="sxs-lookup"><span data-stu-id="274f2-109">Select **Border**, and click the type of border to apply to the chart.</span></span>  
  
3.  <span data-ttu-id="274f2-110">(Facultatif) Sélectionnez une valeur ou tapez une expression qui représente le style de la bordure.</span><span class="sxs-lookup"><span data-stu-id="274f2-110">(Optional) Select a value or type an expression that represents the style of the border.</span></span>  
  
4.  <span data-ttu-id="274f2-111">(Facultatif) Spécifiez la couleur de la ligne qui sera dessinée autour du graphique comme bordure.</span><span class="sxs-lookup"><span data-stu-id="274f2-111">(Optional) Specify the color of the line that will be drawn around the chart as the border.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="274f2-112">La liste **Couleur de ligne** contient des couleurs courantes.</span><span class="sxs-lookup"><span data-stu-id="274f2-112">The **Line color** list contains common colors.</span></span> <span data-ttu-id="274f2-113">Si vous souhaitez choisir dans une liste contenant plus de couleurs, cliquez sur **Couleurs supplémentaires** dans la liste ou sur le bouton d’expression (**fx**) à côté de la liste pour afficher l’ **Éditeur d’expressions** .</span><span class="sxs-lookup"><span data-stu-id="274f2-113">If you want to select from a list of more colors, click **More colors** in the list or click the expression (**fx**) button next to the list to bring up the **Expression** editor.</span></span>  
  
5.  <span data-ttu-id="274f2-114">(Facultatif) Spécifiez la largeur de la bordure.</span><span class="sxs-lookup"><span data-stu-id="274f2-114">(Optional) Specify the width of the border.</span></span> <span data-ttu-id="274f2-115">Les valeurs valides se situent entre 0,25 et 20 points.</span><span class="sxs-lookup"><span data-stu-id="274f2-115">Valid values are between 0.25pt and 20pt.</span></span> <span data-ttu-id="274f2-116">Envisagez de définir une taille de bordure entre 1 et 3 points pour un meilleur effet visuel.</span><span class="sxs-lookup"><span data-stu-id="274f2-116">Consider keeping the size of your border to between 1 and 3pt for the best visual effect.</span></span>  
  
6.  <span data-ttu-id="274f2-117">(Facultatif) Si votre rapport contient une couleur d'arrière-plan autre que blanc, envisagez de définir une couleur de page qui est de la même couleur.</span><span class="sxs-lookup"><span data-stu-id="274f2-117">(Optional) If your report contains a background color other than white, consider defining a page color that is the same color.</span></span> <span data-ttu-id="274f2-118">La couleur de page est la couleur d'arrière-plan qui figure hors de la ligne de bordure.</span><span class="sxs-lookup"><span data-stu-id="274f2-118">The page color is the background color outside of the border line.</span></span>  
  
7.  <span data-ttu-id="274f2-119">(Facultatif) Si vous choisissez un type de cadre, spécifiez un style et une couleur pour le cadre.</span><span class="sxs-lookup"><span data-stu-id="274f2-119">(Optional) If you choose a Frame type, specify a style and color for the frame.</span></span> <span data-ttu-id="274f2-120">La liste **Couleur de remplissage du cadre** contient des couleurs courantes.</span><span class="sxs-lookup"><span data-stu-id="274f2-120">The **Frame fill color** list contains common colors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="274f2-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="274f2-121">See Also</span></span>  
 <span data-ttu-id="274f2-122">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="274f2-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="274f2-123">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="274f2-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="274f2-124">Ajouter des styles de biseau, de relief et de texture à un graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="274f2-124">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
