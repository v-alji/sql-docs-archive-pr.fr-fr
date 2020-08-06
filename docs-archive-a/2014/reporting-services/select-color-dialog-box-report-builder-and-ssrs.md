---
title: Boîte de dialogue Sélectionner une couleur (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.selectcolor.f1
- "10090"
helpviewer_keywords:
- Select Color dialog box
ms.assetid: ac7089a3-5c7b-4f53-8348-180610e86da2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a2526b755fd4e08faf79998d351e824371fac2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707004"
---
# <a name="select-color-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="482dd-102">Boîte de dialogue Sélectionner une couleur (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="482dd-102">Select Color Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="482dd-103">Utilisez la boîte de dialogue **Sélectionner une couleur** pour spécifier les options de couleur d'un graphique ou de l'arrière-plan d'une cellule ou de plusieurs cellules dans une région de données ou une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="482dd-103">Use the **Select Color** dialog box to specify color options for the background of a single cell or multiple cells within a data region or a text box, or for a chart.</span></span>  
  
## <a name="options"></a><span data-ttu-id="482dd-104">Options</span><span class="sxs-lookup"><span data-stu-id="482dd-104">Options</span></span>  
 <span data-ttu-id="482dd-105">**Sélecteur de couleurs**</span><span class="sxs-lookup"><span data-stu-id="482dd-105">**Color selector**</span></span>  
 <span data-ttu-id="482dd-106">Choisissez une option parmi les trois proposées permettant de spécifier la façon dont vous souhaitez sélectionner des couleurs :</span><span class="sxs-lookup"><span data-stu-id="482dd-106">Choose from three options that specify how you want to select colors:</span></span>  
  
-   <span data-ttu-id="482dd-107">**Sélecteur - Cercle de couleur** Choisissez une couleur à l’aide des valeurs de couleur Teinte/Saturation/Luminosité (TSL).</span><span class="sxs-lookup"><span data-stu-id="482dd-107">**Picker - Color circle** Choose a color using Hue/Saturation/Brightness (HSB) color values.</span></span>  
  
-   <span data-ttu-id="482dd-108">**Sélecteur - Carré de couleur** Choisissez une couleur à l’aide des valeurs de couleur Rouge/Vert/Bleu (RVB).</span><span class="sxs-lookup"><span data-stu-id="482dd-108">**Picker - Color square** Choose a color using Red/Green/Blue (RGB) color values.</span></span>  
  
-   <span data-ttu-id="482dd-109">**Palette - Couleurs standard** Choisissez une couleur dans une liste prédéfinie de valeurs de couleur.</span><span class="sxs-lookup"><span data-stu-id="482dd-109">**Palette - Standard colors** Choose a color from a predefined list of color values.</span></span>  
  
 <span data-ttu-id="482dd-110">**Cercle de couleur**</span><span class="sxs-lookup"><span data-stu-id="482dd-110">**Color circle**</span></span>  
 <span data-ttu-id="482dd-111">Utilisez cette option pour les couleurs TSL, car les valeurs TSL sont associées à un système de coordonnées cylindriques.</span><span class="sxs-lookup"><span data-stu-id="482dd-111">Use for HSB colors because HSB values are mapped onto a cylindrical coordinate system.</span></span> <span data-ttu-id="482dd-112">La teinte représente la couleur réelle, la saturation correspond à la pureté de la couleur et la luminosité est la luminosité ou l'obscurité relative.</span><span class="sxs-lookup"><span data-stu-id="482dd-112">Hue is the actual color, saturation is purity of color, brightness is relative brightness or darkness.</span></span>  
  
 <span data-ttu-id="482dd-113">Lorsque vous sélectionnez une couleur, le centre du cercle détermine la couleur.</span><span class="sxs-lookup"><span data-stu-id="482dd-113">When you pick a color, the center of the circle determines the color.</span></span> <span data-ttu-id="482dd-114">Utilisez le curseur de couleur pour modifier la teinte.</span><span class="sxs-lookup"><span data-stu-id="482dd-114">Use the color slider to change the hue.</span></span> <span data-ttu-id="482dd-115">Les coordonnées x et y représentent respectivement les valeurs de saturation et de luminosité.</span><span class="sxs-lookup"><span data-stu-id="482dd-115">The x and y coordinates represent saturation and brightness values respectively.</span></span>  
  
 <span data-ttu-id="482dd-116">**Carré de couleur**</span><span class="sxs-lookup"><span data-stu-id="482dd-116">**Color square**</span></span>  
 <span data-ttu-id="482dd-117">Utilisez cette option pour les couleurs RVB, car les valeurs RVB sont associées à un système de coordonnées cartésiennes.</span><span class="sxs-lookup"><span data-stu-id="482dd-117">Use for RGB colors because RGB values are mapped to a Cartesian coordinate system.</span></span> <span data-ttu-id="482dd-118">R est la valeur pour le rouge, V est la valeur pour le vert et B, la valeur pour le bleu.</span><span class="sxs-lookup"><span data-stu-id="482dd-118">R is the value for Red, G is the value for Green, B is the value for Blue.</span></span>  
  
 <span data-ttu-id="482dd-119">Lorsque vous sélectionnez une couleur, le centre du carré détermine la couleur.</span><span class="sxs-lookup"><span data-stu-id="482dd-119">When you pick a color, the center of the square determines the color.</span></span> <span data-ttu-id="482dd-120">Utilisez le curseur de couleur pour modifier la plage de la couleur choisie.</span><span class="sxs-lookup"><span data-stu-id="482dd-120">Use the color slider to change the range of the chosen color.</span></span> <span data-ttu-id="482dd-121">Les coordonnées x et y représentent les deux autres couleurs.</span><span class="sxs-lookup"><span data-stu-id="482dd-121">The x and y coordinates represent the other two colors.</span></span> <span data-ttu-id="482dd-122">Par exemple, si vous sélectionnez le vert, le curseur affiche la plage des valeurs vertes, tandis que les coordonnées x et y représentent respectivement les valeurs rouges et bleues.</span><span class="sxs-lookup"><span data-stu-id="482dd-122">For example, if you pick green, the slider shows the range of green values, the x and y coordinates represent red and blue values respectively.</span></span>  
  
 <span data-ttu-id="482dd-123">**Couleurs standard**</span><span class="sxs-lookup"><span data-stu-id="482dd-123">**Standard palette color**</span></span>  
 <span data-ttu-id="482dd-124">Utilisez pour les couleurs nommées de l' [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` énumération.</span><span class="sxs-lookup"><span data-stu-id="482dd-124">Use for named colors from the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` enumeration.</span></span>  
  
 <span data-ttu-id="482dd-125">**Système de couleurs**</span><span class="sxs-lookup"><span data-stu-id="482dd-125">**Color system**</span></span>  
 <span data-ttu-id="482dd-126">Spécifiez des couleurs RVB ou TSL.</span><span class="sxs-lookup"><span data-stu-id="482dd-126">Specify RGB or HSB colors.</span></span> <span data-ttu-id="482dd-127">Ce choix modifie l'affichage pour afficher des valeurs RVB ou TSL, mises à jour de façon interactive lorsque vous utilisez un cercle de couleur ou un carré de couleur pour le **Sélecteur de couleurs**.</span><span class="sxs-lookup"><span data-stu-id="482dd-127">This choice changes the display to show RGB or HSB values, which are updated interactively when you use a color circle or color square for the **Color selector**.</span></span>  
  
 <span data-ttu-id="482dd-128">La valeur **Alpha** s'affiche pour certaines propriétés lorsqu'une couleur peut inclure une valeur de transparence,</span><span class="sxs-lookup"><span data-stu-id="482dd-128">The **Alpha** value displays for some properties when a color can include a transparency value.</span></span> <span data-ttu-id="482dd-129">par exemple pour un remplissage de série de graphique.</span><span class="sxs-lookup"><span data-stu-id="482dd-129">For example, Chart series fill.</span></span> <span data-ttu-id="482dd-130">Pour les propriétés qui ne prennent pas en charge la transparence, cette valeur est désactivée.</span><span class="sxs-lookup"><span data-stu-id="482dd-130">For properties that do not support transparency, this value is disabled.</span></span>  
  
 <span data-ttu-id="482dd-131">**Rouge**</span><span class="sxs-lookup"><span data-stu-id="482dd-131">**Red**</span></span>  
 <span data-ttu-id="482dd-132">Valeur décimale pour la composante rouge de la couleur RVB.</span><span class="sxs-lookup"><span data-stu-id="482dd-132">The decimal value for the red part of the RGB color.</span></span> <span data-ttu-id="482dd-133">Utilisez la zone de sélection numérique pour modifier la valeur ou tapez une valeur comprise entre 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="482dd-133">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="482dd-134">**Vert**</span><span class="sxs-lookup"><span data-stu-id="482dd-134">**Green**</span></span>  
 <span data-ttu-id="482dd-135">Valeur décimale pour la composante verte de la couleur RVB.</span><span class="sxs-lookup"><span data-stu-id="482dd-135">The decimal value for the green part of the RGB color.</span></span> <span data-ttu-id="482dd-136">Utilisez la zone de sélection numérique pour modifier la valeur ou tapez une valeur comprise entre 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="482dd-136">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="482dd-137">**Bleu**</span><span class="sxs-lookup"><span data-stu-id="482dd-137">**Blue**</span></span>  
 <span data-ttu-id="482dd-138">Valeur décimale pour la composante bleue de la couleur RVB.</span><span class="sxs-lookup"><span data-stu-id="482dd-138">The decimal value for the blue part of the RGB color.</span></span> <span data-ttu-id="482dd-139">Utilisez la zone de sélection numérique pour modifier la valeur ou tapez une valeur comprise entre 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="482dd-139">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="482dd-140">**Alpha**</span><span class="sxs-lookup"><span data-stu-id="482dd-140">**Alpha**</span></span>  
 <span data-ttu-id="482dd-141">Valeur décimale pour la composante alpha ou de transparence de la couleur.</span><span class="sxs-lookup"><span data-stu-id="482dd-141">The decimal value for the alpha or transparency part of the color.</span></span> <span data-ttu-id="482dd-142">Lorsque cette valeur est activée, vous pouvez utiliser le commutateur de curseur pour ajuster le degré de transparence voulu.</span><span class="sxs-lookup"><span data-stu-id="482dd-142">When this value is enabled, you can use the slider switch to adjust the degree of transparency you want.</span></span>  
  
 <span data-ttu-id="482dd-143">**Teinte**</span><span class="sxs-lookup"><span data-stu-id="482dd-143">**Hue**</span></span>  
 <span data-ttu-id="482dd-144">Valeur décimale pour la teinte de la couleur TSL.</span><span class="sxs-lookup"><span data-stu-id="482dd-144">The decimal value for the hue of the HSB color.</span></span> <span data-ttu-id="482dd-145">Utilisez la zone de sélection numérique pour modifier la valeur ou tapez une valeur comprise entre 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="482dd-145">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="482dd-146">**Saturation**</span><span class="sxs-lookup"><span data-stu-id="482dd-146">**Saturation**</span></span>  
 <span data-ttu-id="482dd-147">Valeur décimale pour la saturation de la couleur TSL.</span><span class="sxs-lookup"><span data-stu-id="482dd-147">The decimal value for the saturation of the HSB color.</span></span> <span data-ttu-id="482dd-148">Utilisez la zone de sélection numérique pour modifier la valeur ou tapez une valeur comprise entre 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="482dd-148">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="482dd-149">**Brightness (Luminosité)**</span><span class="sxs-lookup"><span data-stu-id="482dd-149">**Brightness**</span></span>  
 <span data-ttu-id="482dd-150">Valeur décimale pour la luminosité de la couleur TSL.</span><span class="sxs-lookup"><span data-stu-id="482dd-150">The decimal value for the brightness of the HSB color.</span></span> <span data-ttu-id="482dd-151">Utilisez la zone de sélection numérique pour modifier la valeur ou tapez une valeur comprise entre 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="482dd-151">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="482dd-152">**Échantillon de couleur**</span><span class="sxs-lookup"><span data-stu-id="482dd-152">**Color sample**</span></span>  
 <span data-ttu-id="482dd-153">Affiche la couleur actuelle dans la partie gauche du volet et affiche interactivement la nouvelle couleur que vous choisissez dans la partie droite du volet.</span><span class="sxs-lookup"><span data-stu-id="482dd-153">Shows the current color on the left half of the pane and interactively shows the new color you are choosing on the right half of the pane.</span></span> <span data-ttu-id="482dd-154">S'il n'existe pas de couleur par défaut, la partie gauche du volet est blanche.</span><span class="sxs-lookup"><span data-stu-id="482dd-154">If there is no default color, the left half of the pane is white.</span></span> <span data-ttu-id="482dd-155">La plupart des propriétés RDL n'ont aucune couleur par défaut.</span><span class="sxs-lookup"><span data-stu-id="482dd-155">Most RDL properties have no default color.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="482dd-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="482dd-156">See Also</span></span>  
 <span data-ttu-id="482dd-157">[Mise en forme des éléments de rapport &#40;Générateur de rapports et SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="482dd-157">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="482dd-158">Mise en forme du texte et des espaces réservés &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="482dd-158">Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;</span></span>](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md)  
  
  
