---
title: Mot clé EXISTing (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- EXISTING
helpviewer_keywords:
- Existing keyword
ms.assetid: 651ee9ac-04ef-4316-87c9-a3df5ac27d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: 115444c832fe8fe9b258a0c23b97b97553f32e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601135"
---
# <a name="existing-keyword-mdx"></a><span data-ttu-id="c2d6b-102">Mot clé EXISTING (MDX)</span><span class="sxs-lookup"><span data-stu-id="c2d6b-102">EXISTING Keyword (MDX)</span></span>
  <span data-ttu-id="c2d6b-103">Force un jeu spécifié à être évalué dans le contexte actuel.</span><span class="sxs-lookup"><span data-stu-id="c2d6b-103">Forces a specified set to be evaluated within the current context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d6b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c2d6b-104">Syntax</span></span>  
  
```  
  
Existing Set_Expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2d6b-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="c2d6b-105">Arguments</span></span>  
 <span data-ttu-id="c2d6b-106">*Set_Expression*</span><span class="sxs-lookup"><span data-stu-id="c2d6b-106">*Set_Expression*</span></span>  
 <span data-ttu-id="c2d6b-107">Expression d'ensemble MDX (Multidimensional Expressions) valide.</span><span class="sxs-lookup"><span data-stu-id="c2d6b-107">A valid Multidimensional Expressions (MDX) set expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2d6b-108">Notes</span><span class="sxs-lookup"><span data-stu-id="c2d6b-108">Remarks</span></span>  
 <span data-ttu-id="c2d6b-109">Par défaut, les jeux sont évalués dans le contexte du cube qui contient les membres de ce jeu.</span><span class="sxs-lookup"><span data-stu-id="c2d6b-109">By default, sets are evaluated within the context of the cube that contains the members of the set.</span></span> <span data-ttu-id="c2d6b-110">Le mot clé `Existing` contraint un jeu spécifié à être évalué dans le contexte actuel à la place.</span><span class="sxs-lookup"><span data-stu-id="c2d6b-110">The `Existing` keyword forces a specified set to be evaluated within the current context instead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2d6b-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="c2d6b-111">Example</span></span>  
 <span data-ttu-id="c2d6b-112">L'exemple ci-dessous retourne le nombre de revendeurs dont les ventes ont baissé sur la période précédente en se basant sur les valeurs de membres State-Province (état-province) sélectionnées par l'utilisateur et évaluées à l'aide de la fonction `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="c2d6b-112">The following example returns the count of the resellers whose sales have declined over the previous time period, based on user-selected State-Province member values evaluated using the `Aggregate` function.</span></span> <span data-ttu-id="c2d6b-113">Le mot clé [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) et [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) sont utilisées pour retourner des valeurs de ventes en baisse concernant les catégories de produits inscrites dans la dimension Product.</span><span class="sxs-lookup"><span data-stu-id="c2d6b-113">The [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) and [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) functions are used to return values for declining sales for product categories in the Product dimension.</span></span> <span data-ttu-id="c2d6b-114">Le `Existing` mot clé force le jeu dans la `Filter` fonction à être évalué dans le contexte actuel, c’est-à-dire, pour les membres de Washington et Oregon de la hiérarchie d’attribut State-Province.</span><span class="sxs-lookup"><span data-stu-id="c2d6b-114">The `Existing` keyword forces the set in the `Filter` function to be evaluated in the current context - that is, for the Washington and Oregon members of the State-Province attribute hierarchy.</span></span>  
  
```  
WITH MEMBER Measures.[Declining Reseller Sales] AS  
   Count  
      (Filter  
         (Existing  
            (Reseller.Reseller.Reseller)  
         , [Measures].[Reseller Sales Amount] <   
            ([Measures].[Reseller Sales Amount]  
               ,[Date].Calendar.PrevMember  
            )  
        )  
      )  
MEMBER [Geography].[State-Province].x AS   
   Aggregate   
      ( {[Geography].[State-Province].&[WA]&[US]  
         , [Geography].[State-Province].&[OR]&[US] }   
      )  
SELECT NON EMPTY HIERARCHIZE   
      (AddCalculatedMembers   
         (   
            {DrillDownLevel  
               ({[Product].[All Products]}  
               )  
            }   
         )   
      ) DIMENSION PROPERTIES PARENT_UNIQUE_NAME ON COLUMNS   
FROM [Adventure Works]  
WHERE   
      ( [Geography].[State-Province].x  
        , [Date].[Calendar].[Calendar Quarter].&[2003]&[4]  
        ,[Measures].[Declining Reseller Sales]  
      )  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2d6b-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c2d6b-115">See Also</span></span>  
 <span data-ttu-id="c2d6b-116">[Nombre &#40;défini&#41; &#40;&#41;MDX](/sql/mdx/count-set-mdx) </span><span class="sxs-lookup"><span data-stu-id="c2d6b-116">[Count &#40;Set&#41; &#40;MDX&#41;](/sql/mdx/count-set-mdx) </span></span>  
 <span data-ttu-id="c2d6b-117">[AddCalculatedMembers&#41;MDX &#40;](/sql/mdx/addcalculatedmembers-mdx) </span><span class="sxs-lookup"><span data-stu-id="c2d6b-117">[AddCalculatedMembers &#40;MDX&#41;](/sql/mdx/addcalculatedmembers-mdx) </span></span>  
 <span data-ttu-id="c2d6b-118">[&#41;MDX &#40;Aggregate](/sql/mdx/aggregate-mdx) </span><span class="sxs-lookup"><span data-stu-id="c2d6b-118">[Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) </span></span>  
 <span data-ttu-id="c2d6b-119">[Filtre &#40;&#41;MDX](/sql/mdx/filter-mdx) </span><span class="sxs-lookup"><span data-stu-id="c2d6b-119">[Filter &#40;MDX&#41;](/sql/mdx/filter-mdx) </span></span>  
 <span data-ttu-id="c2d6b-120">[Propriétés &#40;MDX&#41;](/sql/mdx/properties-mdx) </span><span class="sxs-lookup"><span data-stu-id="c2d6b-120">[Properties &#40;MDX&#41;](/sql/mdx/properties-mdx) </span></span>  
 <span data-ttu-id="c2d6b-121">[DrilldownLevel&#41;MDX &#40;](/sql/mdx/drilldownlevel-mdx) </span><span class="sxs-lookup"><span data-stu-id="c2d6b-121">[DrilldownLevel &#40;MDX&#41;](/sql/mdx/drilldownlevel-mdx) </span></span>  
 <span data-ttu-id="c2d6b-122">[Hierarchize&#41;MDX &#40;](/sql/mdx/hierarchize-mdx) </span><span class="sxs-lookup"><span data-stu-id="c2d6b-122">[Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) </span></span>  
 [<span data-ttu-id="c2d6b-123">Guide de référence des fonctions MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c2d6b-123">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
