---
title: Images, zones de texte, rectangles et lignes (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aa7ad08f-dd49-401e-9619-522e27055bb9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fb9a47bb3b8d68d48be42f8f0a2adddfc3ba130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697540"
---
# <a name="images-text-boxes-rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="b0a94-102">Images, zones de texte, rectangles et lignes (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="b0a94-102">Images, Text Boxes, Rectangles, and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b0a94-103">Outre les régions de données telles que les tableaux, les matrices et les graphiques, les rapports utilisent d'autres éléments de rapport, comme des images, des zones de texte ou des rectangles, pour ajouter un attrait visuel, mettre en évidence des informations clés ou fournir des informations connexes.</span><span class="sxs-lookup"><span data-stu-id="b0a94-103">In addition to data regions like tables, matrices, and charts, reports use other report items like images, text boxes, and rectangles to add visual interest, highlight key information, or provide related information.</span></span> <span data-ttu-id="b0a94-104">Vous pouvez modifier la mise en forme d'un élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="b0a94-104">You can change the formatting of a report item.</span></span> <span data-ttu-id="b0a94-105">Par exemple, vous pouvez ajouter une bordure ou une marge intérieure, modifier la visibilité initiale ou la direction, ou encore spécifier la taille et l'emplacement exacts de l'élément.</span><span class="sxs-lookup"><span data-stu-id="b0a94-105">For example, you can add a border or padding, change the initial visibility or direction, or specify an exact size and location for the item.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="b0a94-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b0a94-106">In This Section</span></span>  
 [<span data-ttu-id="b0a94-107">Zones de texte &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b0a94-107">Text Boxes &#40;Report Builder and SSRS&#41;</span></span>](text-boxes-report-builder-and-ssrs.md)  
 <span data-ttu-id="b0a94-108">Les zones de texte peuvent être placées n'importe où dans le rapport et peuvent contenir des étiquettes, des champs ou des données calculées.</span><span class="sxs-lookup"><span data-stu-id="b0a94-108">Text boxes can be placed anywhere on a report and can contain labels, fields, or calculated data.</span></span> <span data-ttu-id="b0a94-109">La valeur à afficher dans une zone de texte lorsque vous visualisez un rapport peut être définie au moyen d'expressions.</span><span class="sxs-lookup"><span data-stu-id="b0a94-109">You use expressions to define the value to display in a text box when you view a report.</span></span>  
  
 <span data-ttu-id="b0a94-110">Chaque cellule d'un tableau ou d'une matrice contient une zone de texte, que vous pouvez mettre en forme de la même manière que les zones de texte autonomes.</span><span class="sxs-lookup"><span data-stu-id="b0a94-110">Every cell in a table or matrix is also a text box, which you can format in the same way that you format stand-alone text boxes.</span></span>  
  
 [<span data-ttu-id="b0a94-111">Rectangles et lignes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b0a94-111">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
 <span data-ttu-id="b0a94-112">Les**lignes** s’affichent à l’horizontale, à la verticale ou en diagonale.</span><span class="sxs-lookup"><span data-stu-id="b0a94-112">**Lines** display horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="b0a94-113">Une ligne se définit par un point de début et un point de fin, et peut être associée à divers styles (par exemple, une épaisseur et une couleur).</span><span class="sxs-lookup"><span data-stu-id="b0a94-113">A line is defined with a start and end point and can have various styles (for example, weight and color) assigned to it.</span></span> <span data-ttu-id="b0a94-114">Une ligne n'est associée à aucune donnée.</span><span class="sxs-lookup"><span data-stu-id="b0a94-114">A line has no data associated with it.</span></span>  
  
 <span data-ttu-id="b0a94-115">Les**rectangles** peuvent être utilisés comme éléments graphiques ou comme conteneurs pour d'autres éléments de rapport.</span><span class="sxs-lookup"><span data-stu-id="b0a94-115">**Rectangles** can be used as a graphical element, or as a container for other report items.</span></span> <span data-ttu-id="b0a94-116">Comme élément graphique, un rectangle a les mêmes propriétés qu'une ligne.</span><span class="sxs-lookup"><span data-stu-id="b0a94-116">As a graphical element, a rectangle has the same properties as a line.</span></span> <span data-ttu-id="b0a94-117">Comme conteneur, un rectangle fait office de conteneur parent pour tous les éléments de rapport qui se trouvent à l'intérieur.</span><span class="sxs-lookup"><span data-stu-id="b0a94-117">As a container, a rectangle acts as a parent container for all report items inside it.</span></span> <span data-ttu-id="b0a94-118">Placer des éléments de rapport dans un conteneur parent permet d'en contrôler l'apparence sur chaque page du rapport.</span><span class="sxs-lookup"><span data-stu-id="b0a94-118">Placing report items in a parent container helps control how they appear on each report page.</span></span>  
  
 [<span data-ttu-id="b0a94-119">Images &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b0a94-119">Images &#40;Report Builder and SSRS&#41;</span></span>](images-report-builder-and-ssrs.md)  
 <span data-ttu-id="b0a94-120">Dans un rapport, les images affichent des données binaires de type image.</span><span class="sxs-lookup"><span data-stu-id="b0a94-120">Images display binary image data in a report.</span></span> <span data-ttu-id="b0a94-121">Vous fournissez la source de l'image.</span><span class="sxs-lookup"><span data-stu-id="b0a94-121">You provide the source for the image.</span></span> <span data-ttu-id="b0a94-122">La source peut être une référence de type URL à une image stockée sur un serveur Web, une référence à des données d'image incorporées ou une référence à des données binaires de type image dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="b0a94-122">The source can be a URL reference to an image stored on a Web server, a reference to embedded image data, or a reference to binary image data in a database.</span></span> <span data-ttu-id="b0a94-123">Le Générateur de rapports et le Concepteur de rapports prennent en charge les fichiers .bmp, .jpeg, .gif et .png.</span><span class="sxs-lookup"><span data-stu-id="b0a94-123">Report Builder and Report Designer support .bmp, .jpeg, .gif, and .png files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a94-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0a94-124">See Also</span></span>  
 [<span data-ttu-id="b0a94-125">Mise en forme des éléments de rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b0a94-125">Formatting Report Items &#40;Report Builder and SSRS&#41;</span></span>](formatting-report-items-report-builder-and-ssrs.md)  
  
  
