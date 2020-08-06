---
title: Utilisation des propriétés de membre (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DIMENSION PROPERTIES keyword
- Properties function
- member properties [MDX]
- members [MDX], properties
ms.assetid: 26b5ad08-3799-4a5e-89f3-dca25e637d45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5b7fdf989fc23ea70be7d7863f5d4c6ac0b61d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698621"
---
# <a name="using-member-properties-mdx"></a><span data-ttu-id="c550d-102">Utilisation des propriétés de membre (MDX)</span><span class="sxs-lookup"><span data-stu-id="c550d-102">Using Member Properties (MDX)</span></span>
  <span data-ttu-id="c550d-103">Les propriétés de membre couvrent les informations de base relatives à chaque membre de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="c550d-103">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="c550d-104">Ces informations de base comprennent le nom du membre, le niveau parent, le nombre d'enfants, etc.</span><span class="sxs-lookup"><span data-stu-id="c550d-104">This basic information includes the member name, parent level, the number of children, and so on.</span></span> <span data-ttu-id="c550d-105">Les propriétés de membre sont mises à la disposition de tous les membres situés à un niveau donné.</span><span class="sxs-lookup"><span data-stu-id="c550d-105">Member properties are available for all members at a given level.</span></span> <span data-ttu-id="c550d-106">D'un point de vue organisationnel, les propriétés de membre sont regroupées en dimensions et traitées comme telles.</span><span class="sxs-lookup"><span data-stu-id="c550d-106">In terms of organization, member properties are treated as dimensionally organized data, stored on a single dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c550d-107">Dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], les propriétés de membre sont appelées relations d’attributs.</span><span class="sxs-lookup"><span data-stu-id="c550d-107">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], member properties are know as attribute relationships.</span></span> <span data-ttu-id="c550d-108">Pour plus d’informations, consultez [Relations d’attributs](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="c550d-108">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
 <span data-ttu-id="c550d-109">Les propriétés de membre sont soit *intrinsèques* , soit *personnalisées*:</span><span class="sxs-lookup"><span data-stu-id="c550d-109">Member properties are either *intrinsic* or *custom*:</span></span>  
  
 <span data-ttu-id="c550d-110">Propriétés de membre intrinsèques</span><span class="sxs-lookup"><span data-stu-id="c550d-110">Intrinsic member properties</span></span>  
 <span data-ttu-id="c550d-111">Tous les membres prennent en charge les propriétés de membre intrinsèques, telles que la mise en forme de leur valeur, tandis que les dimensions et les niveaux fournissent des propriétés de membre intrinsèques supplémentaires relatives aux dimensions ou aux niveaux, telles que l'identificateur d'un membre.</span><span class="sxs-lookup"><span data-stu-id="c550d-111">All members support intrinsic member properties, such as the formatted value of a member, while dimensions and levels supply additional intrinsic dimension and level member properties, such as the ID of a member.</span></span>  
  
 <span data-ttu-id="c550d-112">Pour plus d’informations, consultez [Propriétés de membre intrinsèques &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c550d-112">For more information, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
 <span data-ttu-id="c550d-113">Propriétés de membre définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c550d-113">User-defined member properties</span></span>  
 <span data-ttu-id="c550d-114">Des propriétés supplémentaires sont souvent associées aux membres.</span><span class="sxs-lookup"><span data-stu-id="c550d-114">Members often have additional properties associated with them.</span></span> <span data-ttu-id="c550d-115">Par exemple, le niveau Products peut fournir les propriétés SKU, SRP, Weight et Volume de chaque produit.</span><span class="sxs-lookup"><span data-stu-id="c550d-115">For example, the Products level may offer the SKU, SRP, Weight, and Volume properties for each product.</span></span> <span data-ttu-id="c550d-116">Ces propriétés ne sont pas des membres, mais elles contiennent des informations supplémentaires sur les membres situés au niveau Products.</span><span class="sxs-lookup"><span data-stu-id="c550d-116">These properties are not members, but contain additional information about members at the Products level.</span></span>  
  
 <span data-ttu-id="c550d-117">Pour plus d’informations, consultez [Propriétés de membre définies par l’utilisateur &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c550d-117">For more information, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
 <span data-ttu-id="c550d-118">Les propriétés de membre intrinsèques et définies par l’utilisateur peuvent être récupérées à l’aide du `PROPERTIES` mot clé ou de la fonction [Properties](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="c550d-118">Both intrinsic and user-defined member properties can be retrieved through the use of the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
## <a name="using-the-properties-keyword"></a><span data-ttu-id="c550d-119">Utilisation du mot clé PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="c550d-119">Using the PROPERTIES Keyword</span></span>  
 <span data-ttu-id="c550d-120">Le mot clé `PROPERTIES` spécifie les propriétés de membre à utiliser pour une dimension donnée d'un axe.</span><span class="sxs-lookup"><span data-stu-id="c550d-120">The `PROPERTIES` keyword specifies the member properties that are to be used for a given axis dimension.</span></span> <span data-ttu-id="c550d-121">Le `PROPERTIES` mot clé est enfoui dans la `<axis specification>` clause de l’instruction MDX [Select](/sql/mdx/mdx-data-manipulation-select) :</span><span class="sxs-lookup"><span data-stu-id="c550d-121">The `PROPERTIES` keyword is buried within the `<axis specification>` clause of the MDX [SELECT](/sql/mdx/mdx-data-manipulation-select) statement:</span></span>  
  
```  
SELECT [<axis_specification>  
       [, <axis_specification>...]]  
  FROM [<cube_specification>]  
[WHERE [<slicer_specification>]]  
```  
  
 <span data-ttu-id="c550d-122">La clause `<axis_specification>` comprend une clause `<dim_props>` facultative, comme illustré dans la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="c550d-122">The `<axis_specification>` clause includes an optional `<dim_props>` clause, as shown in the following syntax:</span></span>  
  
```  
<axis_specification> ::= <set> [<dim_props>] ON <axis_name>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c550d-123">Pour plus d’informations sur les valeurs `<set>` et `<axis_name>`, consultez [Spécification du contenu d’un axe de requête &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="c550d-123">For more information about the `<set>` and `<axis_name>` values, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
 <span data-ttu-id="c550d-124">La clause `<dim_props>` permet d'interroger les propriétés de dimension, de niveau et de membre à l'aide du mot clé `PROPERTIES`.</span><span class="sxs-lookup"><span data-stu-id="c550d-124">The `<dim_props>` clause lets you query dimension, level, and member properties using the `PROPERTIES` keyword.</span></span> <span data-ttu-id="c550d-125">La syntaxe suivante illustre le format de la clause `<dim_props>` :</span><span class="sxs-lookup"><span data-stu-id="c550d-125">The following syntax shows the formatting of the `<dim_props>` clause:</span></span>  
  
```  
<dim_props> ::= [DIMENSION] PROPERTIES <property> [,<property>...]  
```  
  
 <span data-ttu-id="c550d-126">Le détail de la syntaxe de `<property>` varie en fonction de la propriété interrogée :</span><span class="sxs-lookup"><span data-stu-id="c550d-126">The breakdown of the `<property>` syntax varies depending on the property that you are querying:</span></span>  
  
-   <span data-ttu-id="c550d-127">Les propriétés de membre intrinsèques sensibles au contexte doivent être précédées du nom de la dimension ou du niveau.</span><span class="sxs-lookup"><span data-stu-id="c550d-127">Context sensitive intrinsic member properties must be preceded with the name of the dimension or level.</span></span> <span data-ttu-id="c550d-128">Par contre, les propriétés de membre intrinsèques non sensibles au contexte ne peuvent pas être spécifiées à l'aide du nom de la dimension ou du niveau.</span><span class="sxs-lookup"><span data-stu-id="c550d-128">However, non-context sensitive intrinsic member properties cannot be qualified by the dimension or level name.</span></span> <span data-ttu-id="c550d-129">Pour plus d’informations sur l’utilisation du `PROPERTIES` mot clé avec des propriétés de membre intrinsèques, consultez [Propriétés de membre intrinsèques &#40;&#41;MDX ](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c550d-129">For more information about how to use the `PROPERTIES` keyword with intrinsic member properties, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
-   <span data-ttu-id="c550d-130">Les propriétés de membre définies par l'utilisateur doivent être précédées du nom du niveau dans lequel elles résident.</span><span class="sxs-lookup"><span data-stu-id="c550d-130">User-defined member properties should be preceded by the name of the level in which they reside.</span></span> <span data-ttu-id="c550d-131">Pour plus d’informations sur l’utilisation du `PROPERTIES` mot clé avec des propriétés de membre définies par l’utilisateur, consultez [Propriétés de membre définies par l’utilisateur &#40;&#41;MDX ](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c550d-131">For more information about how to use the `PROPERTIES` keyword with user-defined member properties, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c550d-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c550d-132">See Also</span></span>  
 [<span data-ttu-id="c550d-133">Création et utilisation de valeurs de propriétés &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c550d-133">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)  
  
  
