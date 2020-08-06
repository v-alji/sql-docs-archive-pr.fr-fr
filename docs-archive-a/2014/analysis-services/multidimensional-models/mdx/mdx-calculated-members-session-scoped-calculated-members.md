---
title: Création de membres calculés au niveau de la session (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE MEMBER statement
- session-scoped calculated members [MDX]
ms.assetid: 2875ed89-2c26-4645-8ed9-8848479d110f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8fe7a9f137d8b74eaa5bad104dbfdb471dd14588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612571"
---
# <a name="creating-session-scoped-calculated-members-mdx"></a><span data-ttu-id="1f501-102">Création de membres calculés au niveau de la session (MDX)</span><span class="sxs-lookup"><span data-stu-id="1f501-102">Creating Session-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="1f501-103">Pour créer un membre calculé disponible dans l’ensemble d’une session MDX (Multidimensional Expressions), vous utilisez l’instruction [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) .</span><span class="sxs-lookup"><span data-stu-id="1f501-103">To create a calculated member that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span> <span data-ttu-id="1f501-104">Un membre calculé créé à l'aide de l'instruction CREATE MEMBER n'est supprimé qu'après la fermeture de la session MDX.</span><span class="sxs-lookup"><span data-stu-id="1f501-104">A calculated member that is created by using the CREATE MEMBER statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="1f501-105">Comme décrit dans cette rubrique, la syntaxe de l'instruction CREATE MEMBER est explicite et conviviale.</span><span class="sxs-lookup"><span data-stu-id="1f501-105">As discussed in this topic, the syntax of the CREATE MEMBER statement is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f501-106">Pour plus d’informations sur les membres calculés, consultez [Création de membres calculés dans MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="1f501-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="create-member-syntax"></a><span data-ttu-id="1f501-107">Syntaxe CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="1f501-107">CREATE MEMBER Syntax</span></span>  
 <span data-ttu-id="1f501-108">Utilisez la syntaxe suivante pour ajouter l'instruction CREATE MEMBER à l'instruction MDX :</span><span class="sxs-lookup"><span data-stu-id="1f501-108">Use the following syntax to add the CREATE MEMBER statement to the MDX statement:</span></span>  
  
```  
CREATE [SESSION] MEMBER [<cube-name>.]<fully-qualified-member-name> AS <expression> [,<property-definition-list>]  
<cube name> ::= CURRENTCUBE | <Cube Name>  
<property-definition-list> ::= <property-definition>  
  | <property-definition>, <property-definition-list>  
<property-definition> ::= <property-identifier> = <property-value>  
<property-identifier> ::= VISIBLE | SOLVEORDER | SOLVE_ORDER | FORMAT_STRING | NON_EMPTY_BEHAVIOR <ole db member properties>  
```  
  
 <span data-ttu-id="1f501-109">Dans la syntaxe de l'instruction CREATE MEMBER, la valeur `fully-qualified-member-name` est le nom complet du membre calculé.</span><span class="sxs-lookup"><span data-stu-id="1f501-109">In the syntax for the CREATE MEMBER statement, the `fully-qualified-member-name` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="1f501-110">Ce nom comprend la dimension ou le niveau auquel le membre calculé est associé.</span><span class="sxs-lookup"><span data-stu-id="1f501-110">The fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="1f501-111">La valeur `expression` retourne la valeur du membre calculé après l'évaluation de la valeur de l'expression.</span><span class="sxs-lookup"><span data-stu-id="1f501-111">The `expression` value returns the value of the calculated member after the expression value has been evaluated,.</span></span>  
  
## <a name="create-member-example"></a><span data-ttu-id="1f501-112">Exemple de syntaxe CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="1f501-112">CREATE MEMBER Example</span></span>  
 <span data-ttu-id="1f501-113">L'exemple suivant utilise l'instruction CREATE MEMBER pour créer le membre calculé `LastFourStores` .</span><span class="sxs-lookup"><span data-stu-id="1f501-113">The following example uses the CREATE MEMBER statement to create the `LastFourStores` calculated member.</span></span> <span data-ttu-id="1f501-114">Ce dernier retourne la somme des unités vendues dans les quatre derniers magasins et sera disponible tout au long de la session du cube.</span><span class="sxs-lookup"><span data-stu-id="1f501-114">This calculated member returns the sum of units sold for the last four stores, and will be available throughout the whole session of the cube.</span></span>  
  
```  
Create Session Member [Store].[Measures].LastFourStores as   
sum(([Stores].[ByLocation].Lag(3) :  
[Stores].[ByLocation].NextMember), [Measures].[Units Sold])  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f501-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f501-115">See Also</span></span>  
 [<span data-ttu-id="1f501-116">Création de membres calculés d’étendue de requête &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="1f501-116">Creating Query-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-query-scoped-calculated-members.md)  
  
  
