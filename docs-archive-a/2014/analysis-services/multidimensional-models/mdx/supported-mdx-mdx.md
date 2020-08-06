---
title: MDX pris en charge (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], statements
- MDX [Analysis Services], functions
ms.assetid: 308bc0b3-4fd6-4435-972b-5e40d9e3c99b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e8df6a2aa6da6b88a07a2abdef99d6ea03d8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705595"
---
# <a name="supported-mdx-mdx"></a><span data-ttu-id="ad0af-102">Éléments MDX (MDX) pris en charge</span><span class="sxs-lookup"><span data-stu-id="ad0af-102">Supported MDX (MDX)</span></span>
  <span data-ttu-id="ad0af-103">Les instructions et les fonctions suivantes sont prises en charge avec les scripts MDX (Multidimensional Expressions) :</span><span class="sxs-lookup"><span data-stu-id="ad0af-103">The following statements and functions are supported within Multidimensional Expressions (MDX) Script:</span></span>  
  
 [<span data-ttu-id="ad0af-104">&#40;Commentaire&#41; &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-104">&#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="ad0af-105">-- &#40;Comment&#41; &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-105">-- &#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="ad0af-106">Commentaire &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-106">Comment &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="ad0af-107">Instruction ALTER CUBE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-107">ALTER CUBE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-alter-cube)  
  
> [!NOTE]  
>  <span data-ttu-id="ad0af-108">Seule la modification du membre par défaut est prise en charge dans les scripts MDX.</span><span class="sxs-lookup"><span data-stu-id="ad0af-108">Only altering the default member is supported in MDX Scripting.</span></span>  
  
 [<span data-ttu-id="ad0af-109">Instruction CALCULATE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-109">CALCULATE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
 [<span data-ttu-id="ad0af-110">Instruction CASE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-110">CASE Statement &#40;MDX&#41;</span></span>](/sql/mdx/case-statement-mdx)  
  
 [<span data-ttu-id="ad0af-111">Instruction CREATE CELL CALCULATION &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-111">CREATE CELL CALCULATION Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-cell-calculation)  
  
 [<span data-ttu-id="ad0af-112">Instruction CREATE MEMBER &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-112">CREATE MEMBER Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-member)  
  
 [<span data-ttu-id="ad0af-113">Instruction CREATE SET &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-113">CREATE SET Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-set)  
  
 [<span data-ttu-id="ad0af-114">Mot clé EXISTING &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-114">EXISTING Keyword &#40;MDX&#41;</span></span>](mdx-query-existing-keyword.md)  
  
 [<span data-ttu-id="ad0af-115">Instruction FREEZE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-115">FREEZE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
 [<span data-ttu-id="ad0af-116">Instruction IF &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-116">IF Statement  &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-if)  
  
 [<span data-ttu-id="ad0af-117">This &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-117">This &#40;MDX&#41;</span></span>](/sql/mdx/this-mdx)  
  
> [!NOTE]  
>  <span data-ttu-id="ad0af-118">MDX prend en charge l'assignation aux propriétés de cellule suivantes : `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME` et `FONT_SIZE`.</span><span class="sxs-lookup"><span data-stu-id="ad0af-118">MDX supports assignment to the following cell properties: `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME`, and `FONT_SIZE`.</span></span> <span data-ttu-id="ad0af-119">Pour plus d’informations, consultez [Utilisation des propriétés de cellule &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ad0af-119">For more information, see [Using Cell Properties &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md).</span></span> <span data-ttu-id="ad0af-120">MDX prend également en charge l’assignation à la `NON_EMPTY_BEHAVIOR` propriété de l’instruction [Create Member](/sql/mdx/mdx-data-definition-create-member) .</span><span class="sxs-lookup"><span data-stu-id="ad0af-120">MDX also supports assignment to the `NON_EMPTY_BEHAVIOR` property of the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span>  
  
 [<span data-ttu-id="ad0af-121">Instruction SCOPE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-121">SCOPE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-scope)  
  
## <a name="see-also"></a><span data-ttu-id="ad0af-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad0af-122">See Also</span></span>  
 [<span data-ttu-id="ad0af-123">Script MDX de base &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0af-123">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)  
  
  
