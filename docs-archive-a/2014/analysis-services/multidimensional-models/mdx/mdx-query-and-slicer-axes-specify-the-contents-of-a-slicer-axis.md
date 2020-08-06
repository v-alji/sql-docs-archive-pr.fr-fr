---
title: Spécification du contenu d’un axe de secteur (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- filtering data [MDX]
ms.assetid: c56b0a70-cdec-427f-990e-425290344e7d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8620c54970ea14a2ac01c85262a372d2b3db0d68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696239"
---
# <a name="specifying-the-contents-of-a-slicer-axis-mdx"></a><span data-ttu-id="d96e4-102">Spécification du contenu d'un axe de secteur (MDX)</span><span class="sxs-lookup"><span data-stu-id="d96e4-102">Specifying the Contents of a Slicer Axis (MDX)</span></span>
  <span data-ttu-id="d96e4-103">L'axe de secteur filtre les données retournées par l'instruction SELECT MDX (Multidimensional Expressions), en restreignant les données retournées de telle sorte que seules les données communes aux membres spécifiés soient retournées.</span><span class="sxs-lookup"><span data-stu-id="d96e4-103">The slicer axis filters the data returned by the Multidimensional Expressions (MDX) SELECT statement, restricting the returned data so that only data intersecting with the specified members will be returned.</span></span> <span data-ttu-id="d96e4-104">Il peut être perçu comme un axe supplémentaire invisible dans une requête.</span><span class="sxs-lookup"><span data-stu-id="d96e4-104">It can be thought of as an invisible extra axis in a query.</span></span> <span data-ttu-id="d96e4-105">L'axe de secteur est défini dans la clause WHERE de l'instruction SELECT de MDX.</span><span class="sxs-lookup"><span data-stu-id="d96e4-105">The slicer axis is defined in the WHERE clause of the SELECT statement in MDX.</span></span>  
  
## <a name="slicer-axis-syntax"></a><span data-ttu-id="d96e4-106">Syntaxe de l'axe de secteur</span><span class="sxs-lookup"><span data-stu-id="d96e4-106">Slicer Axis Syntax</span></span>  
 <span data-ttu-id="d96e4-107">Pour spécifier de façon explicite un axe de secteur, utilisez la clause `<SELECT slicer axis clause>` dans MDX, comme dans la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="d96e4-107">To explicitly specify a slicer axis, you  using the `<SELECT slicer axis clause>` in MDX, as described in the following syntax:</span></span>  
  
```  
<SELECT slicer axis clause> ::=  WHERE Set_Expression  
```  
  
 <span data-ttu-id="d96e4-108">Dans la syntaxe d'axe de secteur indiquée, `Set_Expression` peut prendre soit une expression de tuple, qui est traitée comme un jeu pour les besoins d'évaluation de la clause, soit une expression d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="d96e4-108">In the slicer axis syntax shown, `Set_Expression` can take either a tuple expression, which is treated as a set for the purposes of evaluating the clause, or a set expression.</span></span> <span data-ttu-id="d96e4-109">Si une expression d'ensemble est spécifiée, MDX tentera d'évaluer le jeu, en agrégeant les cellules du résultat dans chaque tuple du jeu.</span><span class="sxs-lookup"><span data-stu-id="d96e4-109">If a set expression is specified, MDX will try to evaluate the set, aggregating the result cells in every tuple along the set.</span></span> <span data-ttu-id="d96e4-110">En d'autres termes, MDX tentera d'utiliser la fonction [Aggregate](/sql/mdx/aggregate-mdx) sur le jeu, agrégeant chaque mesure par sa fonction d'agrégation associée.</span><span class="sxs-lookup"><span data-stu-id="d96e4-110">In other words, MDX will try to use the [Aggregate](/sql/mdx/aggregate-mdx) function on the set, aggregating each measure by its associated aggregation function.</span></span> <span data-ttu-id="d96e4-111">En outre, si l'expression d'ensemble ne peut pas être exprimée comme une jointure croisée des membres d'une hiérarchie d'attributs, MDX traite les cellules exclues de l'expression d'ensemble pour le découpage comme NULL, pour les besoins de l'évaluation.</span><span class="sxs-lookup"><span data-stu-id="d96e4-111">Also, if the set expression cannot be expressed as a crossjoin of attribute hierarchy members, MDX treats cells that fall outside of the set expression for the slicer as null for evaluation purposes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d96e4-112">Contrairement à la clause WHERE dans SQL, la clause WHERE d'une instruction MDX SELECT ne filtre jamais directement ce qui est retourné sur l'axe des lignes d'une requête.</span><span class="sxs-lookup"><span data-stu-id="d96e4-112">Unlike the WHERE clause in SQL, the WHERE clause of an MDX SELECT statement never directly filters what is returned on the Rows axis of a query.</span></span> <span data-ttu-id="d96e4-113">Pour filtrer ce qui s'affiche sur l'axe des lignes ou des colonnes d'une requête, vous pouvez utiliser diverses fonctions MDX, par exemple FILTER, NONEMPTY et TOPCOUNT.</span><span class="sxs-lookup"><span data-stu-id="d96e4-113">To filter what appears on the Rows or Columns axis of a query, you can use a variety of MDX functions, for example FILTER, NONEMPTY and TOPCOUNT.</span></span>  
  
### <a name="implicit-slicer-axis"></a><span data-ttu-id="d96e4-114">Axe de secteur implicite</span><span class="sxs-lookup"><span data-stu-id="d96e4-114">Implicit Slicer Axis</span></span>  
 <span data-ttu-id="d96e4-115">Si un membre d'une hiérarchie du cube n'est pas explicitement inclus dans un axe de requête, le membre par défaut de cette hiérarchie est implicitement inclus dans l'axe de secteur.</span><span class="sxs-lookup"><span data-stu-id="d96e4-115">If a member from a hierarchy within the cube is not explicitly included in a query axis, the default member from that hierarchy is implicitly included in the slicer axis.</span></span> <span data-ttu-id="d96e4-116">Pour plus d’informations sur les membres par défaut, consultez [Définir un membre par défaut](../attribute-properties-define-a-default-member.md).</span><span class="sxs-lookup"><span data-stu-id="d96e4-116">For more information about default members, see [Define a Default Member](../attribute-properties-define-a-default-member.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d96e4-117">Exemples</span><span class="sxs-lookup"><span data-stu-id="d96e4-117">Examples</span></span>  
 <span data-ttu-id="d96e4-118">La requête suivante n'inclut pas de clause WHERE, et retourne la valeur de la mesure Internet Sales Amount pour toutes les années civiles :</span><span class="sxs-lookup"><span data-stu-id="d96e4-118">The following query does not include a WHERE clause, and returns the value of the Internet Sales Amount measure for all Calendar Years:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="d96e4-119">L'ajout d'une clause WHERE, comme suit :</span><span class="sxs-lookup"><span data-stu-id="d96e4-119">Adding a WHERE clause, as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States])  
  
```  
  
 <span data-ttu-id="d96e4-120">ne modifie pas ce qui est retourné sur les lignes ou les colonnes de la requête ; cela modifie les valeurs retournées pour chaque cellule.</span><span class="sxs-lookup"><span data-stu-id="d96e4-120">does not change what is returned on Rows or Columns in the query; it changes the values returned for each cell.</span></span> <span data-ttu-id="d96e4-121">Dans cet exemple, la requête est découpée de façon à retourner la valeur du montant des ventes sur Internet (Internet Sales Amount) de toutes les années civiles (Calendar Years), mais uniquement pour les clients (Customers) qui habitent aux États-Unis. Il est possible d'ajouter plusieurs membres de différentes hiérarchies à la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="d96e4-121">In this example, the query is sliced so that it returns the value of Internet Sales Amount for all Calendar Years but only for Customers who live in the United States.Multiple members from different hierarchies can be added to the WHERE clause.</span></span> <span data-ttu-id="d96e4-122">La requête suivante affiche la valeur du montant des ventes sur Internet (Internet Sales Amount) de toutes les années civiles (Calendar Years) pour les clients (Customers) qui habitent aux États-Unis et qui ont acheté des produits (Products) de la catégorie des vélos (Bikes) :</span><span class="sxs-lookup"><span data-stu-id="d96e4-122">The following query shows the value of Internet Sales Amount for all Calendar Years for Customers who live in the United States and who bought Products in the Category Bikes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States], [Product].[Category].&[1])  
```  
  
 <span data-ttu-id="d96e4-123">Si vous voulez utiliser plusieurs membres de la même hiérarchie, vous devez inclure un jeu dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="d96e4-123">If you want to use multiple members from the same hierarchy, you need to include a set in the WHERE clause.</span></span> <span data-ttu-id="d96e4-124">Par exemple, la requête suivante affiche la valeur du montant des ventes sur Internet (Internet Sales Amount) de toutes les années civiles (Calendar Years) pour les clients (Customers) qui ont acheté des produits (Products) de la catégorie des vélos (Bikes) et qui habitent aux États-Unis ou au Royaume-Uni :</span><span class="sxs-lookup"><span data-stu-id="d96e4-124">For example, the following query shows the value of Internet Sales Amount for all Calendar Years for Customers who bought Products in the Category Bikes and live in either the United States or the United Kingdom:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE(  
{[Customer].[Customer Geography].[Country].&[United States]  
, [Customer].[Customer Geography].[Country].&[United Kingdom]}  
, [Product].[Category].&[1])  
  
```  
  
 <span data-ttu-id="d96e4-125">Comme indiqué précédemment, l'utilisation d'un jeu dans la clause WHERE effectue implicitement un agrégat des valeurs pour tous les membres du jeu.</span><span class="sxs-lookup"><span data-stu-id="d96e4-125">As mentioned above, using a set in the WHERE clause will implicitly aggregate values for all members in the set.</span></span> <span data-ttu-id="d96e4-126">Dans le cas présent, la requête affiche les valeurs agrégées pour les États-Unis et le Royaume-Uni dans chaque cellule.</span><span class="sxs-lookup"><span data-stu-id="d96e4-126">In this case, the query shows aggregated values for the United States and the United Kingdom in each cell.</span></span>  
  
  
