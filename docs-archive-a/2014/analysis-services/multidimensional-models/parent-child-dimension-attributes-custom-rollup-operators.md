---
title: Opérateurs de cumul personnalisé dans les dimensions parent-enfant | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- child rollup operations
- UnaryOperatorColumn property
- custom rollup operators [Analysis Services]
- unary operators
- parent-child dimensions [Analysis Services]
ms.assetid: a3ddd9fc-5fa3-4227-9322-8c45a5b5c2c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: db12ccc6703ee4863dd3b6bd598d2317b54fce6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611362"
---
# <a name="custom-rollup-operators-in-parent-child-dimensions"></a><span data-ttu-id="0e919-102">Opérateurs de cumul personnalisé dans les dimensions parent-enfant</span><span class="sxs-lookup"><span data-stu-id="0e919-102">Custom Rollup Operators in Parent-Child Dimensions</span></span>
  <span data-ttu-id="0e919-103">Les opérateurs de cumul personnalisé proposent une façon simple de contrôler le mode de cumul des valeurs de membre dans les valeurs parentes à l'intérieur d'une hiérarchie parent-enfant.</span><span class="sxs-lookup"><span data-stu-id="0e919-103">Custom rollup operators provide a simple way to control how member values are rolled up into parent values in a parent-child hierarchy.</span></span> <span data-ttu-id="0e919-104">Dans une dimension dotée d'une relation parent-enfant, vous spécifiez une colonne contenant des opérateurs unaires qui spécifient le cumul de tous les membres non calculés de l'attribut parent.</span><span class="sxs-lookup"><span data-stu-id="0e919-104">In a dimension containing a parent-child relationship, you specify a column that contains unary operators that specify rollup for all noncalculated members of the parent attribute.</span></span> <span data-ttu-id="0e919-105">L'opérateur unaire est appliqué aux membres dès que les valeurs des membres parents sont évaluées.</span><span class="sxs-lookup"><span data-stu-id="0e919-105">The unary operator is applied to members whenever the values of the parent members are evaluated.</span></span>  
  
 <span data-ttu-id="0e919-106">Les opérateurs unaires sont stockés dans la colonne définie par la propriété `UnaryOperatorColumn` de l'attribut parent et ils sont appliqués à chaque membre de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="0e919-106">The unary operators are stored in column defined by the `UnaryOperatorColumn` property of the parent attribute, and they are applied to each member of the attribute.</span></span> <span data-ttu-id="0e919-107">La colonne spécifiée par cette propriété peut résider dans la table de dimension ou dans une table liée à la table de dimension par une clé étrangère de la table de dimension.</span><span class="sxs-lookup"><span data-stu-id="0e919-107">The column specified by this property can reside either in the dimension table or in a table related to the dimension table by a foreign key in the dimension table.</span></span>  
  
 <span data-ttu-id="0e919-108">Les opérateurs de cumul personnalisé proposent des fonctionnalités analogues aux formules de membre personnalisées, mais plus simples.</span><span class="sxs-lookup"><span data-stu-id="0e919-108">Custom rollup operators provide functionality similar to, but more simplified than, custom member formulas.</span></span> <span data-ttu-id="0e919-109">Une formule de membre personnalisée utilise les expressions MDX (Multidimensional Expressions) pour déterminer le mode de cumul des membres.</span><span class="sxs-lookup"><span data-stu-id="0e919-109">A custom member formula uses Multidimensional Expressions (MDX) expressions to determine how the members are rolled up.</span></span> <span data-ttu-id="0e919-110">De son côté, un opérateur de cumul personnalisé utilise un simple opérateur unaire pour déterminer comment la valeur d'un membre affecte le parent.</span><span class="sxs-lookup"><span data-stu-id="0e919-110">In contrast, a custom rollup operator uses a simple unary operator to determine how the value of a member affects the parent.</span></span> <span data-ttu-id="0e919-111">Les formules de membre personnalisées du niveau précédent d'une dimension remplacent l'opérateur de cumul personnalisé d'un niveau.</span><span class="sxs-lookup"><span data-stu-id="0e919-111">Custom member formulas of the preceding level in a dimension override a level's custom rollup operator.</span></span>  
  
## <a name="custom-rollup-precedence"></a><span data-ttu-id="0e919-112">Précédence du cumul personnalisé</span><span class="sxs-lookup"><span data-stu-id="0e919-112">Custom Rollup Precedence</span></span>  
 <span data-ttu-id="0e919-113">En termes de précédence, les opérateurs de cumul personnalisé de l'attribut source d'un niveau de la hiérarchie remplacent les formules de membre personnalisées du niveau précédent.</span><span class="sxs-lookup"><span data-stu-id="0e919-113">In terms of precedence, the custom rollup operators of the source attribute for a level in a hierarchy override the custom member formulas of the previous level.</span></span> <span data-ttu-id="0e919-114">Toutefois, les formules de membre personnalisées d'un niveau sont prioritaires sur les opérateurs de cumul personnalisés du niveau suivant.</span><span class="sxs-lookup"><span data-stu-id="0e919-114">However, the custom member formulas of the preceding level override the custom rollup operators of a level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e919-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e919-115">See Also</span></span>  
 <span data-ttu-id="0e919-116">[Définir des formules de membre personnalisées](attribute-properties-define-custom-member-formulas.md) </span><span class="sxs-lookup"><span data-stu-id="0e919-116">[Define Custom Member Formulas](attribute-properties-define-custom-member-formulas.md) </span></span>  
 [<span data-ttu-id="0e919-117">Opérateurs unaires dans les dimensions parent-enfant</span><span class="sxs-lookup"><span data-stu-id="0e919-117">Unary Operators in Parent-Child Dimensions</span></span>](parent-child-dimension-attributes-unary-operators.md)  
  
  
