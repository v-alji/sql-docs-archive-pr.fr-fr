---
title: Modifier un élément dans une cellule (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91a54778-8929-41f9-bb4c-826cec636be4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 80ef171713e6505867e00e343ce17b70cab9045a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710196"
---
# <a name="change-an-item-within-a-cell-report-builder-and-ssrs"></a><span data-ttu-id="5a950-102">Modifier un élément dans une cellule (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="5a950-102">Change an Item Within a Cell (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5a950-103">Seuls les éléments non-conteneurs, tels que les zones de texte, les lignes ou les images, peuvent être remplacés par un nouvel élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="5a950-103">Only a non-container item, such as a text box, line, or image, can be replaced by a new report item.</span></span> <span data-ttu-id="5a950-104">Par exemple, vous pouvez faire glisser une table dans une zone de texte pour remplacer la zone de texte par une table.</span><span class="sxs-lookup"><span data-stu-id="5a950-104">For example, you can drag a table into a text box to replace the text box with a table.</span></span>  
  
 <span data-ttu-id="5a950-105">Si une cellule contient un élément conteneur comme un rectangle, une liste, un tableau ou une matrice, le nouvel élément est ajouté à l'élément conteneur au lieu de le remplacer.</span><span class="sxs-lookup"><span data-stu-id="5a950-105">If the cell contains a container item such as a rectangle, list, table, or matrix, the new item is added to the containing item instead of replacing it.</span></span> <span data-ttu-id="5a950-106">Pour remplacer un élément de conteneur par un nouvel élément, supprimez le conteneur.</span><span class="sxs-lookup"><span data-stu-id="5a950-106">To replace a container item with a new item, delete the container.</span></span> <span data-ttu-id="5a950-107">Sa suppression entraîne son remplacement par une zone de texte, que vous pouvez ensuite remplacer par un autre élément.</span><span class="sxs-lookup"><span data-stu-id="5a950-107">Deleting the container item replaces it with a text box, which you can then replace with another item.</span></span>  
  
 <span data-ttu-id="5a950-108">Par défaut, toutes les cellules d'une table, matrice ou région de données de type liste contiennent une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="5a950-108">By default, all cells in a table, matrix, or list data region contain a text box.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-an-item-within-a-cell"></a><span data-ttu-id="5a950-109">Pour modifier un élément dans une cellule</span><span class="sxs-lookup"><span data-stu-id="5a950-109">To change an item within a cell</span></span>  
  
-   <span data-ttu-id="5a950-110">Sous l'onglet **Insérer** , dans le groupe **Régions de données** ou **Éléments de rapport** , cliquez sur l'élément à ajouter au rapport, puis sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="5a950-110">On the **Insert** tab, in the **Data Regions** or **Report Items** group, click the item that you want to add to the report, and then click the report.</span></span> <span data-ttu-id="5a950-111">L'élément est ajouté au rapport.</span><span class="sxs-lookup"><span data-stu-id="5a950-111">The item is added to the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a950-112">La boîte de dialogue **Propriétés de l’image** s’ouvre quand vous faites glisser un élément de rapport d’image vers une cellule, où vous pouvez définir des propriétés, telles que la source de l’image, avant que l’image ne soit ajoutée à la cellule.</span><span class="sxs-lookup"><span data-stu-id="5a950-112">The **Image Properties** dialog box opens when you drag an image report item to a cell, where you can set properties such as the source of the image before the image is added to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a950-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a950-113">See Also</span></span>  
 <span data-ttu-id="5a950-114">[Images, zones de texte, rectangles et lignes &#40;Générateur de rapports et SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5a950-114">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5a950-115">Listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5a950-115">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
