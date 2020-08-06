---
title: Création et utilisation des valeurs de propriété (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- property values [MDX]
- queries [MDX], property values
- MDX [Analysis Services], property values
- Multidimensional Expressions [Analysis Services], property values
ms.assetid: 0cafb269-03c8-4183-b6e9-220f071e4ef2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67eadc6bc2f0bf6f318f20ad42a5cc9e7a5afa5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610900"
---
# <a name="creating-and-using-property-values-mdx"></a><span data-ttu-id="39e31-102">Création et utilisation de valeurs de propriétés (MDX)</span><span class="sxs-lookup"><span data-stu-id="39e31-102">Creating and Using Property Values (MDX)</span></span>
  <span data-ttu-id="39e31-103">La syntaxe MDX (Multidimensional Expressions) prend en charge des propriétés intrinsèques et définies par l'utilisateur pour les dimensions, les niveaux, les membres et les cellules.</span><span class="sxs-lookup"><span data-stu-id="39e31-103">Multidimensional Expressions (MDX) supports intrinsic and user-defined properties for dimensions, levels, members, and cells.</span></span> <span data-ttu-id="39e31-104">Les propriétés intrinsèques permettent de définir des noms uniques, des légendes et même une mise en forme et une taille de caractères pour des cellules individuelles.</span><span class="sxs-lookup"><span data-stu-id="39e31-104">The intrinsic properties provide unique names, captions, and even formatting and font sizes for individual cells.</span></span> <span data-ttu-id="39e31-105">Pour leur part, les propriétés définies par l'utilisateur permettent de fournir presque n'importe quel type d'attribut supplémentaire aux membres.</span><span class="sxs-lookup"><span data-stu-id="39e31-105">User-defined properties, on the other hand, can provide almost any kind of additional attribute to members.</span></span>  
  
 <span data-ttu-id="39e31-106">Les propriétés intrinsèques et définies par l'utilisateur sont disponibles aux niveaux suivants :</span><span class="sxs-lookup"><span data-stu-id="39e31-106">Intrinsic and user-defined properties are available at the following levels:</span></span>  
  
 <span data-ttu-id="39e31-107">**Propriétés de membre**</span><span class="sxs-lookup"><span data-stu-id="39e31-107">**Member properties**</span></span>  
 <span data-ttu-id="39e31-108">Les propriétés de membre couvrent les informations de base relatives à chaque membre de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="39e31-108">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="39e31-109">Ces informations de base comprennent le nom du membre, le niveau parent, le nombre d'enfants, etc.</span><span class="sxs-lookup"><span data-stu-id="39e31-109">This basic information includes the member name, parent level, the number of children, and so on.</span></span>  
  
 <span data-ttu-id="39e31-110">Pour plus d’informations sur les propriétés de membre et leur utilisation, consultez [Utilisation des propriétés de membre &#40;MDX&#41;](multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="39e31-110">For information about member properties and how to use them, see [Using Member Properties &#40;MDX&#41;](multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
 <span data-ttu-id="39e31-111">**Propriétés de cellule**</span><span class="sxs-lookup"><span data-stu-id="39e31-111">**Cell properties**</span></span>  
 <span data-ttu-id="39e31-112">Les propriétés de cellule contiennent des informations sur le contenu et le format des cellules appartenant à une source de données multidimensionnelles, par exemple un cube.</span><span class="sxs-lookup"><span data-stu-id="39e31-112">Cell properties contain information about the content and format of cells in a multidimensional data source, such as a cube.</span></span>  
  
 <span data-ttu-id="39e31-113">Pour plus d’informations sur les propriétés de cellule et leur utilisation, consultez [Utilisation des propriétés de cellule &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-using-cell-properties.md).</span><span class="sxs-lookup"><span data-stu-id="39e31-113">For more information about cell properties and how to use them, see [Using Cell Properties &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-using-cell-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e31-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39e31-114">See Also</span></span>  
 [<span data-ttu-id="39e31-115">Principes de base des requêtes MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="39e31-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](multidimensional-models/mdx/mdx-query-fundamentals-analysis-services.md)  
  
  
