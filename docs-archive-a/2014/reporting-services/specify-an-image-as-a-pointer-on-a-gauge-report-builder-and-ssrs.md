---
title: Spécifier une image en tant que pointeur sur une jauge (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d73b3c3-a068-4868-a2be-0cd261b6e92b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c694cdb90fb668c43eb7e9971bba967bad8dd9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703779"
---
# <a name="specify-an-image-as-a-pointer-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="3d938-102">Spécifier une image en tant que pointeur dans une jauge (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="3d938-102">Specify an Image as a Pointer on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3d938-103">La jauge contient trois styles intégrés pouvant être utilisés pour personnaliser l'apparence du pointeur.</span><span class="sxs-lookup"><span data-stu-id="3d938-103">The gauge contains three built-in styles that can be used to customize the appearance of the pointer.</span></span> <span data-ttu-id="3d938-104">Pour une jauge radiale, les styles intégrés sont les suivants : Aiguille, Marqueur et Barre.</span><span class="sxs-lookup"><span data-stu-id="3d938-104">For a radial gauge, the built in styles are: Needle, Marker and Bar.</span></span> <span data-ttu-id="3d938-105">Pour une jauge linéaire, les styles intégrés sont les suivants : Marqueur, Barre et Thermomètre.</span><span class="sxs-lookup"><span data-stu-id="3d938-105">For a linear gauge, the built-in styles are Marker, Bar, and Thermometer.</span></span> <span data-ttu-id="3d938-106">Si un pointeur unique est requis, l'utilisateur peut créer et spécifier une image qui sera utilisée en tant que pointeur totalement fonctionnel.</span><span class="sxs-lookup"><span data-stu-id="3d938-106">If a unique pointer is required, the user can create and specify an image which can be used as a fully functional pointer.</span></span>  
  
 <span data-ttu-id="3d938-107">Lorsque vous spécifiez une image pour le pointeur, celle-ci doit avoir les spécifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="3d938-107">When you are specifying an image for the pointer, your image must have the following specifications:</span></span>  
  
-   <span data-ttu-id="3d938-108">L'origine du pointeur, ou centre de rotation, doit être située en haut de l'image.</span><span class="sxs-lookup"><span data-stu-id="3d938-108">The origin of the pointer, or center of rotation, must be at the top of the image.</span></span>  
  
-   <span data-ttu-id="3d938-109">L'extrémité du pointeur doit pointer vers le bas.</span><span class="sxs-lookup"><span data-stu-id="3d938-109">The end of the pointer must be pointing down.</span></span>  
  
 <span data-ttu-id="3d938-110">Puisque le pointeur est de forme irrégulière, vous devrez spécifier une couleur transparente pour masquer les parties inutiles de l'image.</span><span class="sxs-lookup"><span data-stu-id="3d938-110">Since the pointer is an irregular shape, you will need to specify a transparency color to hide the unnecessary portions of the image.</span></span> <span data-ttu-id="3d938-111">Envisagez d'utiliser une couleur transparente qui n'est normalement pas affichée sur la jauge, étant donné que les couleurs spécifiées n'apparaîtront pas sur la jauge.</span><span class="sxs-lookup"><span data-stu-id="3d938-111">Consider using a color that would not normally be shown on the gauge as the transparency color, since the colors specified will not appear on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-an-image-as-a-pointer-on-the-gauge"></a><span data-ttu-id="3d938-112">Pour spécifier une image en tant que pointeur sur la jauge</span><span class="sxs-lookup"><span data-stu-id="3d938-112">To specify an image as a pointer on the gauge</span></span>  
  
1.  <span data-ttu-id="3d938-113">En mode Conception, cliquez sur le pointeur de la jauge.</span><span class="sxs-lookup"><span data-stu-id="3d938-113">In Design view, click the pointer of the gauge.</span></span>  
  
2.  <span data-ttu-id="3d938-114">Facultatif Si aucun pointeur n’existe sur la jauge, cliquez avec le bouton droit sur la jauge et sélectionnez **Ajouter un pointeur**.</span><span class="sxs-lookup"><span data-stu-id="3d938-114">(Optional) If no pointer exists on the gauge, right-click on the gauge and select **Add Pointer**.</span></span> <span data-ttu-id="3d938-115">Un pointeur est ajouté à la jauge.</span><span class="sxs-lookup"><span data-stu-id="3d938-115">A pointer is added to the gauge.</span></span>  
  
3.  <span data-ttu-id="3d938-116">Cliquez sur l’onglet **Insérer** du ruban et double-cliquez sur l’icône d’image.</span><span class="sxs-lookup"><span data-stu-id="3d938-116">Click the **Insert** tab on the ribbon and double-click the image icon.</span></span> <span data-ttu-id="3d938-117">La boîte de dialogue **Propriétés de l’image** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="3d938-117">The **Image Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="3d938-118">Ajoutez une image à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="3d938-118">Add an image to your report.</span></span> <span data-ttu-id="3d938-119">Pour plus d’informations, consultez [incorporer une image dans un rapport &#40;générateur de rapports et SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3d938-119">For more information, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="3d938-120">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="3d938-120">Open the Properties pane.</span></span>  
  
6.  <span data-ttu-id="3d938-121">Sur l'aire de conception, cliquez sur le pointeur.</span><span class="sxs-lookup"><span data-stu-id="3d938-121">On the design surface, click on the pointer.</span></span> <span data-ttu-id="3d938-122">Les propriétés du pointeur sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="3d938-122">The properties for the pointer are displayed in the Properties pane.</span></span>  
  
7.  <span data-ttu-id="3d938-123">Développez le nœud PointerImage.</span><span class="sxs-lookup"><span data-stu-id="3d938-123">Expand the PointerImage node.</span></span>  
  
8.  <span data-ttu-id="3d938-124">Dans **source**, sélectionnez **incorporé** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3d938-124">In **Source**, select **Embedded** from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3d938-125">Si votre image est stockée dans la base de données ou sur le web, vous pouvez spécifier l'option appropriée pour cette propriété.</span><span class="sxs-lookup"><span data-stu-id="3d938-125">If your image is stored in the database or on the web, you can specify the appropriate option for this property.</span></span> <span data-ttu-id="3d938-126">Pour plus d’informations, consultez [boîte de dialogue Propriétés de l’image, général &#40;générateur de rapports et SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3d938-126">For more information, see [Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span></span>  
  
9. <span data-ttu-id="3d938-127">Dans **valeur**, sélectionnez le nom de votre image dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3d938-127">In **Value**, select the name of your image from the drop-down list.</span></span>  
  
10. <span data-ttu-id="3d938-128">Dans **transparente**, sélectionnez une valeur de couleur que vous souhaitez supprimer de l’image.</span><span class="sxs-lookup"><span data-stu-id="3d938-128">In **TransparentColor**, pick a color value that you want to remove from the image.</span></span> <span data-ttu-id="3d938-129">Cette opération donne au pointeur de la jauge une apparence transparente.</span><span class="sxs-lookup"><span data-stu-id="3d938-129">This will create a seamless appearance for the pointer in the gauge.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d938-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d938-130">See Also</span></span>  
 <span data-ttu-id="3d938-131">[Mise en forme des pointeurs sur une jauge &#40;Générateur de rapports et SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3d938-131">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3d938-132">[Ajouter une jauge à un rapport &#40;Générateur de rapports et SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3d938-132">[Add a Gauge to a Report &#40;Report Builder and SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3d938-133">[Mise en forme des lignes, des couleurs et des images &#40;Générateur de rapports et SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3d938-133">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3d938-134">Jauges &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3d938-134">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
