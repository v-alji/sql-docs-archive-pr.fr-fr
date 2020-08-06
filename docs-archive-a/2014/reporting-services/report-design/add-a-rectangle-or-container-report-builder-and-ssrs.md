---
title: Ajouter un rectangle ou un conteneur (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10061"
- sql12.rtp.rptdesigner.rectangleproperties.general.f1
ms.assetid: f905c35f-754d-4d02-80f3-85e29ddda826
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fddda2f02b9f370d9742ae6add5bae444f8f55f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600541"
---
# <a name="add-a-rectangle-or-container-report-builder-and-ssrs"></a><span data-ttu-id="ea340-102">Ajouter un rectangle ou un conteneur (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ea340-102">Add a Rectangle or Container (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ea340-103">Ajoutez un rectangle à votre rapport lorsque vous souhaitez qu'un élément graphique sépare des zones du rapport, accentue des zones d'un rapport ou fournisse un arrière-plan pour un ou plusieurs éléments de rapport.</span><span class="sxs-lookup"><span data-stu-id="ea340-103">Add a rectangle to your report when you want a graphical element to separate areas of the report, emphasize areas of a report, or provide a background for one or more report items.</span></span> <span data-ttu-id="ea340-104">Les rectangles sont également utilisés comme conteneurs qui aident à contrôler la façon dont les régions de données sont rendues dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="ea340-104">Rectangles are also used as containers to help control the way data regions render in a report.</span></span> <span data-ttu-id="ea340-105">Vous pouvez personnaliser l'apparence d'un rectangle en modifiant ses propriétés, telles que les couleurs d'arrière-plan et de bordure.</span><span class="sxs-lookup"><span data-stu-id="ea340-105">You can customize the appearance of a rectangle by editing rectangle properties such as the background and border colors.</span></span> <span data-ttu-id="ea340-106">Pour plus d’informations sur l’utilisation d’un rectangle comme conteneur, consultez [Rectangles et lignes &#40;Générateur de rapports et SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) et [Afficher les mêmes données dans une matrice et sur un graphique &#40;Générateur de rapports&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ea340-106">For more information about using a rectangle as a container, see [Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-rectangle"></a><span data-ttu-id="ea340-107">Pour ajouter un rectangle</span><span class="sxs-lookup"><span data-stu-id="ea340-107">To add a rectangle</span></span>  
  
1.  <span data-ttu-id="ea340-108">Sous l'onglet **Insérer** , dans le groupe **Éléments de rapport** , cliquez sur **Rectangle**.</span><span class="sxs-lookup"><span data-stu-id="ea340-108">On the **Insert** tab, in the **Report Items** group, click **Rectangle.**</span></span>  
  
2.  <span data-ttu-id="ea340-109">Dans l'aire de conception, cliquez sur l'endroit où doit venir se positionner le coin supérieur gauche du rectangle, puis faites glisser la souris jusqu'à l'endroit où doit venir se positionner son coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="ea340-109">On the design surface, click the location where you want the upper left corner of the rectangle, and drag to where you want the lower-right corner.</span></span>  
  
     <span data-ttu-id="ea340-110">Notez qu'à mesure que vous déplacez le curseur, des lignes d'alignement apparaissent lorsque le curseur est aligné avec d'autres objets dans l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="ea340-110">Note that as you move the cursor, "snap lines" appear as the cursor lines up with other objects on the design surface.</span></span> <span data-ttu-id="ea340-111">Ces lignes d'alignement vous aident à aligner des objets.</span><span class="sxs-lookup"><span data-stu-id="ea340-111">These help you if you want objects to be aligned.</span></span>  
  
### <a name="to-create-a-container"></a><span data-ttu-id="ea340-112">Pour créer un conteneur</span><span class="sxs-lookup"><span data-stu-id="ea340-112">To create a container</span></span>  
  
1.  <span data-ttu-id="ea340-113">Ajoutez un élément de rapport de type rectangle au rapport.</span><span class="sxs-lookup"><span data-stu-id="ea340-113">Add a rectangle report item to the report.</span></span>  
  
2.  <span data-ttu-id="ea340-114">Faites glisser d'autres éléments de rapport dans le rectangle.</span><span class="sxs-lookup"><span data-stu-id="ea340-114">Drag other report items into the rectangle.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea340-115">Un rectangle est uniquement un conteneur pour les éléments que vous créez dans le rectangle ou que vous faites glisser dans le rectangle.</span><span class="sxs-lookup"><span data-stu-id="ea340-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="ea340-116">Si vous dessinez un rectangle autour d'un élément qui existe déjà dans l'aire de conception, le rectangle n'agit pas comme son conteneur.</span><span class="sxs-lookup"><span data-stu-id="ea340-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span>  
  
### <a name="to-change-rectangle-properties-such-as-color-style-or-weight"></a><span data-ttu-id="ea340-117">Pour modifier les propriétés d'un rectangle, telles que la couleur, le style ou l'épaisseur</span><span class="sxs-lookup"><span data-stu-id="ea340-117">To change rectangle properties such as color, style, or weight</span></span>  
  
1.  <span data-ttu-id="ea340-118">Sélectionnez le rectangle, puis cliquez sur les options de couleur, de style ou d'épaisseur de ligne dans la section **Bordure** de l'onglet Accueil.</span><span class="sxs-lookup"><span data-stu-id="ea340-118">Select the rectangle, and then click the line color, style, or weight options in the **Border** section of the Home tab.</span></span>  
  
2.  <span data-ttu-id="ea340-119">Cliquez sur la flèche en regard du bouton **Bordure** pour déterminer les côtés du rectangle à modifier.</span><span class="sxs-lookup"><span data-stu-id="ea340-119">Click the arrow next to the **Border** button to determine which sides of the rectangle to change.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea340-120">Si vous définissez le style de ligne sur **double** et que la largeur de ligne est 1 1/2 PT ou plus étroit, la ligne peut ne pas apparaître double lorsque vous exécutez le rapport dans Générateur de rapports, Concepteur de rapports ou gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="ea340-120">If you set the line style to **Double** and the line width is 1 1/2 pt or narrower, the line may not appear double when you run the report in Report Builder, Report Designer, or Report Manager.</span></span> <span data-ttu-id="ea340-121">Elle apparaît en double lorsque vous exportez le rapport sous d'autres formats, tels que Microsoft Word et Acrobat PDF.</span><span class="sxs-lookup"><span data-stu-id="ea340-121">It will appear double when you export the report to other formats such as Microsoft Word and Acrobat PDF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea340-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea340-122">See Also</span></span>  
 <span data-ttu-id="ea340-123">[Rectangles et lignes &#40;Générateur de rapports et SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ea340-123">[Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ea340-124">Comportements de rendu &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ea340-124">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
