---
title: Création de membres calculés dans MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], calculated members
- calculated members [MDX]
- Multidimensional Expressions [Analysis Services], calculated members
- queries [MDX], calculated members
ms.assetid: 9322e8b8-43e1-4e02-a7d1-e41a586a5bb8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30dc6562ec394065cf2f177608d4e5679cbd7df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604184"
---
# <a name="building-calculated-members-in-mdx-mdx"></a><span data-ttu-id="118f3-102">Création de membres calculés dans MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="118f3-102">Building Calculated Members in MDX (MDX)</span></span>
  <span data-ttu-id="118f3-103">Dans MDX (Multidimensional Expressions), un membre calculé est un membre qui est résolu par le retour d'une valeur issue du calcul d'une expression MDX.</span><span class="sxs-lookup"><span data-stu-id="118f3-103">In Multidimensional Expressions (MDX), a calculated member is a member that is resolved by calculating an MDX expression to return a value.</span></span> <span data-ttu-id="118f3-104">Cette définition anodine couvre un vaste champ d'action.</span><span class="sxs-lookup"><span data-stu-id="118f3-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="118f3-105">La possibilité de bâtir et d'utiliser des membres calculés dans une requête MDX est un élément fondamental de la manipulation des données multidimensionnelles.</span><span class="sxs-lookup"><span data-stu-id="118f3-105">The ability to construct and use calculated members in an MDX query provides a great deal of manipulation capability for multidimensional data.</span></span>  
  
 <span data-ttu-id="118f3-106">Vous pouvez créer des membres calculés en n'importe quel point d'une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="118f3-106">You can create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="118f3-107">Vous pouvez également créer des membres calculés qui dépendent non seulement des membres existants d'un cube, mais aussi d'autres membres calculés définis dans la même expression MDX.</span><span class="sxs-lookup"><span data-stu-id="118f3-107">You can also create calculated members that depend not only on existing members in a cube, but also on other calculated members defined in the same MDX expression.</span></span>  
  
 <span data-ttu-id="118f3-108">Vous pouvez définir pour un membre calculé l'un des contextes suivants :</span><span class="sxs-lookup"><span data-stu-id="118f3-108">You can define a calculated member to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="118f3-109">**Étendue de requête** Pour créer un membre calculé défini en tant que partie d’une requête MDX, et dont l’étendue est donc limitée à la requête, utilisez le mot clé WITH.</span><span class="sxs-lookup"><span data-stu-id="118f3-109">**Query-scoped** To create a calculated member that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="118f3-110">Vous pouvez ensuite utiliser le membre calculé au sein d'une instruction MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="118f3-110">You can then use the calculated member within an MDX SELECT statement.</span></span> <span data-ttu-id="118f3-111">Ainsi, vous pouvez modifier le membre calculé créé à l'aide du mot clé WITH sans porter atteinte à l'instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="118f3-111">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="118f3-112">Pour plus d’informations sur l’utilisation du mot clé WITH pour la création de membres calculés, consultez [Création de membres calculés d’étendue de requête &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="118f3-112">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md).</span></span>  
  
-   <span data-ttu-id="118f3-113">**Étendue de session** Pour créer un membre calculé dont l’étendue est plus vaste que le contexte de la requête, c’est-à-dire dont l’étendue soit la durée de la session MDX, utilisez l’instruction CREATE MEMBER.</span><span class="sxs-lookup"><span data-stu-id="118f3-113">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE MEMBER statement.</span></span> <span data-ttu-id="118f3-114">Un membre calculé défini à l'aide de l'instruction CREATE MEMBER est disponible pour toutes les requêtes MDX de cette session.</span><span class="sxs-lookup"><span data-stu-id="118f3-114">A calculated member defined by using the CREATE MEMBER statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="118f3-115">L'instruction CREATE MEMBER est appropriée par exemple dans le cas d'une application cliente qui réutilise le même jeu dans différentes requêtes.</span><span class="sxs-lookup"><span data-stu-id="118f3-115">The CREATE MEMBER statement makes sense, for example, in a client application that consistently reuses the same set in a variety of queries.</span></span>  
  
     <span data-ttu-id="118f3-116">Pour plus d’informations sur l’utilisation de l’instruction CREATE MEMBER pour la création de membres calculés dans une session, consultez [Création de membres calculés au niveau de la session &#40;MDX&#41;](mdx-calculated-members-session-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="118f3-116">For more information about how to use the CREATE MEMBER statement to create calculated members in a session, see [Creating Session-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-session-scoped-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118f3-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="118f3-117">See Also</span></span>  
 <span data-ttu-id="118f3-118">[Instruction CREATe MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="118f3-118">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="118f3-119">[Référence des fonctions MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="118f3-119">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="118f3-120">Instruction SELECT &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="118f3-120">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
