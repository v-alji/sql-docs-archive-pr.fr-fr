---
title: Rectangles et lignes (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d6226b0c-0398-4185-8565-96099876fc21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 96b795c3edeabb938e836be3486e28e08737a8e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613305"
---
# <a name="rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="dc9b4-102">Rectangles et lignes (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="dc9b4-102">Rectangles and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dc9b4-103">Les rectangles et les lignes permettent de créer des effets visuels dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-103">Rectangles and lines can create visual effects within a report.</span></span> <span data-ttu-id="dc9b4-104">Vous pouvez afficher des propriétés sur ces éléments de rapports à partir de la section Bordure sous l'onglet Dossier de base, puis définir d'autres propriétés à l'aide du volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-104">You can set display properties on these report items from the Border section of the Home tab, and set other properties by using the Properties pane.</span></span> <span data-ttu-id="dc9b4-105">Vous pouvez ajouter des fonctionnalités, telles qu'une couleur ou une image d'arrière-plan, une info-bulle ou un signet, à un rectangle.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-105">You can add features like a background color or image, a tooltip, or a bookmark to a rectangle.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="rectangles-and-lines-as-report-parts"></a><a name="RectanglesLinesReportParts"></a> <span data-ttu-id="dc9b4-106">Rectangles et lignes en tant que parties de rapports</span><span class="sxs-lookup"><span data-stu-id="dc9b4-106">Rectangles and Lines as Report Parts</span></span>  
 <span data-ttu-id="dc9b4-107">Vous pouvez publier des rectangles avec les éléments qu'ils contiennent, séparément des rapports, sous forme de parties de rapport.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-107">You can publish rectangles with the items that they contain separately from the report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 <span data-ttu-id="dc9b4-108">Vous ne pouvez pas publier les éléments de rapport dans le rectangle en tant que parties de rapport.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-108">You cannot publish the report items within the rectangle as report parts.</span></span> <span data-ttu-id="dc9b4-109">Lorsque des utilisateurs ajoutent le rectangle à un rapport, ils obtiennent le rectangle et les éléments qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-109">When people add the rectangle to a report, they get the rectangle and the items it contains.</span></span>  
  

  
##  <a name="using-a-rectangle-as-a-container"></a><a name="RectangleAsContainer"></a><span data-ttu-id="dc9b4-110">Utilisation d’un rectangle comme conteneur</span><span class="sxs-lookup"><span data-stu-id="dc9b4-110">Using a Rectangle as a Container</span></span>  
 <span data-ttu-id="dc9b4-111">Vous pouvez utiliser un rectangle comme conteneur d'autres éléments.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-111">You can use a rectangle as a container for other items.</span></span> <span data-ttu-id="dc9b4-112">Lorsque vous le déplacez, les éléments qu'il contient se déplacent avec lui.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-112">When you move the rectangle, the items that are contained within the rectangle move along with it.</span></span> <span data-ttu-id="dc9b4-113">Un élément dans le rectangle indique le nom du rectangle dans sa propriété **Parent** .</span><span class="sxs-lookup"><span data-stu-id="dc9b4-113">An item within the rectangle shows the name of the rectangle in its **Parent** property.</span></span> <span data-ttu-id="dc9b4-114">Pour plus d’informations sur l’utilisation d’un rectangle comme conteneur, consultez [Ajouter un rectangle ou un conteneur &#40;Générateur de rapports et SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) et [Afficher les mêmes données dans une matrice et sur un graphique &#40;Générateur de rapports&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="dc9b4-114">For more information about using a rectangle as a container, see [Add a Rectangle or Container &#40;Report Builder and SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc9b4-115">Un rectangle est uniquement un conteneur pour les éléments que vous créez dans le rectangle ou que vous faites glisser dans le rectangle.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="dc9b4-116">Si vous dessinez un rectangle autour d'un élément qui existe déjà dans l'aire de conception, le rectangle n'agit pas comme son conteneur.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span> <span data-ttu-id="dc9b4-117">Le rectangle n'est pas répertorié dans la propriété Parent de l'élément.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-117">The rectangle will not be listed in the item's Parent property.</span></span>  
  
 <span data-ttu-id="dc9b4-118">Lorsque vous utilisez des rectangles pour contenir des éléments de rapport, réfléchissez comment ces éléments seront affectés dans leur ensemble lors du rendu de rapports.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-118">When using rectangles to contain report items, consider how the items will be affected as a whole during report rendering.</span></span> <span data-ttu-id="dc9b4-119">Les éléments de rapports contenant des lignes répétées de données (des tables, par exemple) sont développés pour accueillir les données retournées par une requête. Ceci affecte le positionnement d'autres éléments dans le rectangle.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-119">Report items that contain repeated rows of data (for example, tables) will expand to accommodate the data that is returned by a query, and this affects the positioning of other items in the rectangle.</span></span> <span data-ttu-id="dc9b4-120">Une table pousse les éléments vers le bas si ceux-ci sont placés sous la région de données.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-120">A table will push items down if they are positioned below the data region.</span></span> <span data-ttu-id="dc9b4-121">Pour ancrer un élément à sa position, vous pouvez le placer à l'intérieur d'un rectangle dont le bord supérieur est situé au-dessus du bord inférieur de la table.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-121">To anchor an item in place, you can place the report item inside of a rectangle that has an upper edge above the lower edge of the table.</span></span> <span data-ttu-id="dc9b4-122">Pour plus d’informations, consultez [Comportements de rendu &#40;Générateur de rapports et SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc9b4-122">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="adding-a-report-border"></a><a name="ReportBorder"></a> <span data-ttu-id="dc9b4-123">Ajout d'une bordure de rapport</span><span class="sxs-lookup"><span data-stu-id="dc9b4-123">Adding a Report Border</span></span>  
 <span data-ttu-id="dc9b4-124">Vous pouvez entourer un rapport d'une bordure en plaçant celle-ci dans les en-têtes, les pieds de page et le corps du rapport, sans ajouter de lignes ou de rectangles.</span><span class="sxs-lookup"><span data-stu-id="dc9b4-124">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span> <span data-ttu-id="dc9b4-125">Pour plus d’informations, consultez [Ajouter une bordure à un rapport &#40;Générateur de rapports et SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc9b4-125">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="dc9b4-126">Rubriques de procédures</span><span class="sxs-lookup"><span data-stu-id="dc9b4-126">How-To Topics</span></span>  
 [<span data-ttu-id="dc9b4-127">Ajouter une bordure à un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc9b4-127">Add a Border to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-to-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="dc9b4-128">Ajouter un rectangle ou un conteneur &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc9b4-128">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="dc9b4-129">Ajouter et modifier une ligne &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc9b4-129">Add and Modify a Line &#40;Report Builder and SSRS&#41;</span></span>](add-and-modify-a-line-report-builder-and-ssrs.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc9b4-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dc9b4-130">See Also</span></span>  
 [<span data-ttu-id="dc9b4-131">Ajouter un rectangle ou un conteneur &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc9b4-131">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
  
