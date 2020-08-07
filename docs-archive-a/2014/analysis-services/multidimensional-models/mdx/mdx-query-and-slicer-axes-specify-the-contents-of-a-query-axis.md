---
title: Spécification du contenu d’un axe de requête (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cellsets [MDX]
- query axis [MDX]
ms.assetid: c745ade0-738e-4a98-a3f0-3eabfd3eeba2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 28fd867b8f8caaf74e4dd704753c354368da2e89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703323"
---
# <a name="specifying-the-contents-of-a-query-axis-mdx"></a><span data-ttu-id="b1cd2-102">Spécification du contenu d'un axe de requête (MDX)</span><span class="sxs-lookup"><span data-stu-id="b1cd2-102">Specifying the Contents of a Query Axis (MDX)</span></span>
  <span data-ttu-id="b1cd2-103">Les axes de requête spécifient les bords d'un jeu de cellules retourné par une instruction SELECT MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="b1cd2-103">Query axes specify the edges of a cellset returned by a Multidimensional Expressions (MDX) SELECT statement.</span></span> <span data-ttu-id="b1cd2-104">La spécification des bords d'un jeu de cellules vous permet de restreindre les données retournées qui sont visibles par le client.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-104">Specifying the edges of a cellset lets you restrict the returned data that is visible to the client.</span></span>  
  
 <span data-ttu-id="b1cd2-105">Pour spécifier des axes de requête, utilisez la clause `<SELECT query axis clause>` pour attribuer un jeu à un axe de requête particulier.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-105">To specify query axes, you use the `<SELECT query axis clause>` to assign a set to a particular query axis.</span></span> <span data-ttu-id="b1cd2-106">Chaque valeur `<SELECT query axis clause>` définit un axe de requête.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-106">Each `<SELECT query axis clause>` value defines one query axis.</span></span> <span data-ttu-id="b1cd2-107">Le nombre d'axes du dataset est égal au nombre de valeurs `<SELECT query axis clause>` de l'instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-107">The number of axes in the dataset is equal to the number of `<SELECT query axis clause>` values in the SELECT statement.</span></span>  
  
## <a name="query-axis-syntax"></a><span data-ttu-id="b1cd2-108">Syntaxe de l'axe de requête</span><span class="sxs-lookup"><span data-stu-id="b1cd2-108">Query Axis Syntax</span></span>  
 <span data-ttu-id="b1cd2-109">L'exemple suivant indique la syntaxe de `<SELECT query axis clause>`.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-109">The following syntax shows the syntax for the `<SELECT query axis clause>`:</span></span>  
  
```  
  
<SELECT query axis clause> ::=  
   [ NON EMPTY ] Set_Expression [ <SELECT dimension property list clause> ] [<HAVING clause>]  
   ON {  
      Integer_Expression |   
      AXIS( Integer_Expression ) |   
      {COLUMNS | ROWS | PAGES | SECTIONS | CHAPTERS}     
      }  
  
```  
  
 <span data-ttu-id="b1cd2-110">Chaque axe de requête possède un numéro : 0 pour l'axe des X, 1 pour l'axe des Y, 2 pour l'axe des Z, etc.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-110">Each query axis has a number: zero (0) for the x-axis, 1 for the y-axis, 2 for the z-axis, and so on.</span></span> <span data-ttu-id="b1cd2-111">Dans la syntaxe de `<SELECT query axis clause>`, la valeur `Integer_Expression` spécifie le numéro de l'axe.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-111">In the syntax for the `<SELECT query axis clause>`, the `Integer_Expression` value specifies the axis number.</span></span> <span data-ttu-id="b1cd2-112">Une requête MDX peut prendre en charge jusqu'à 128 axes spécifiés, mais très peu de requêtes MDX en utilisent plus de 5.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-112">An MDX query can support up to 128 specified axes, but very few MDX queries will use more than 5 axes.</span></span> <span data-ttu-id="b1cd2-113">Pour les cinq premiers axes, les alias COLUMNS, ROWS, PAGES, SECTIONS et CHAPTERS peuvent remplacer les numéros.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-113">For the first 5 axes, the aliases COLUMNS, ROWS, PAGES, SECTIONS, and CHAPTERS can instead be used.</span></span>  
  
 <span data-ttu-id="b1cd2-114">Une requête MDX ne peut pas omettre les axes de requête.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-114">An MDX query cannot skip query axes.</span></span> <span data-ttu-id="b1cd2-115">C'est-à-dire qu'une requête qui comporte un ou plusieurs axes de requête ne doit pas exclure les axes dotés de numéros inférieurs ou intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-115">That is, a query that includes one or more query axes must not exclude lower-numbered or intermediate axes.</span></span> <span data-ttu-id="b1cd2-116">Par exemple, une requête ne peut pas avoir un axe ROWS sans un axe COLUMNS, ni des axes COLUMNS et PAGES sans un axe ROWS.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-116">For example, a query cannot have a ROWS axis without a COLUMNS axis, or have COLUMNS and PAGES axes without a ROWS axis.</span></span>  
  
 <span data-ttu-id="b1cd2-117">Toutefois, vous pouvez spécifier une clause SELECT sans axes (c'est-à-dire une clause SELECT vide).</span><span class="sxs-lookup"><span data-stu-id="b1cd2-117">However, you can specify a SELECT clause without any axes (that is, an empty SELECT clause).</span></span> <span data-ttu-id="b1cd2-118">Dans ce cas, toutes les dimensions sont des dimensions de découpage, et la requête MDX sélectionne une cellule.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-118">In this case, all dimensions are slicer dimensions, and the MDX query selects one cell.</span></span>  
  
 <span data-ttu-id="b1cd2-119">Dans la syntaxe d'axe de requête ci-dessus, chaque valeur `Set_Expression` spécifie le jeu définissant le contenu de l'axe de requête.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-119">In the query axis syntax previously shown, each `Set_Expression` value specifies the set that defines the contents of the query axis.</span></span> <span data-ttu-id="b1cd2-120">Pour plus d’informations sur les jeux, consultez [Utilisation de membres, de tuples et de jeux &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="b1cd2-120">For more information about sets, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b1cd2-121">Exemples</span><span class="sxs-lookup"><span data-stu-id="b1cd2-121">Examples</span></span>  
 <span data-ttu-id="b1cd2-122">L'instruction SELECT simple suivante retourne la mesure Internet Sales Amount sur l'axe des colonnes, et utilise la fonction MDX MEMBERS pour retourner tous les membres de la hiérarchie Calendar de la dimension Date sur l'axe des lignes :</span><span class="sxs-lookup"><span data-stu-id="b1cd2-122">The following simple SELECT statement returns the measure Internet Sales Amount on the Columns axis, and uses the MDX MEMBERS function to return all the members from the Calendar hierarchy on the Date dimension on the Rows axis:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="b1cd2-123">Les deux requêtes suivantes retournent exactement les mêmes résultats, mais illustrent l'utilisation de numéros d'axe plutôt que d'alias :</span><span class="sxs-lookup"><span data-stu-id="b1cd2-123">The two following queries return exactly the same results but demonstrate the use of axis numbers rather than aliases:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON 0,  
{[Date].[Calendar].MEMBERS} ON 1  
FROM [Adventure Works]  
  
SELECT {[Measures].[Internet Sales Amount]} ON AXIS(0),  
{[Date].[Calendar].MEMBERS} ON AXIS(1)  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="b1cd2-124">Le mot clé NON EMPTY, utilisé avant la définition du jeu, permet de supprimer facilement tous les tuples vides d'un axe.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-124">The NON EMPTY keyword, used before the set definition, is an easy way to remove all empty tuples from an axis.</span></span> <span data-ttu-id="b1cd2-125">Par exemple, dans les exemples que nous avons vus jusqu’à présent, il n’y a pas de données dans le cube à partir du 2004 août.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-125">For example, in the examples we've seen so far there is no data in the cube from August 2004 onwards.</span></span> <span data-ttu-id="b1cd2-126">Pour supprimer toutes les lignes de l'ensemble de cellules qui n'ont aucune donnée dans aucune colonne, ajoutez simplement NON EMPTY avant la définition du jeu sur l'axe des lignes, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b1cd2-126">To remove all rows from the cellset that have no data in any column, simply add NON EMPTY before the set on the Rows axis definition as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="b1cd2-127">Il est possible d'utiliser NON EMPTY sur tous les axes d'une requête.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-127">NON EMPTY can be used on all axes in a query.</span></span> <span data-ttu-id="b1cd2-128">Comparez les résultats des deux requêtes suivantes, la première n'utilisant pas NON EMPTY et la deuxième l'utilisant sur les deux axes :</span><span class="sxs-lookup"><span data-stu-id="b1cd2-128">Compare the results of the following two queries, the first of which does not use NON EMPTY and the second of which does on both axes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
SELECT NON EMPTY {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
```  
  
 <span data-ttu-id="b1cd2-129">La clause HAVING peut être utilisée pour filtrer le contenu d'un axe en fonction d'un critère spécifique ; elle est moins souple que d'autres méthodes qui permettent d'obtenir les mêmes résultats, telles que la fonction FILTER, mais elle est plus simple à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b1cd2-129">The HAVING clause can be used to filter the contents of an axis based on a specific criteria; it is less flexible than other methods that can achieve the same results, such as the FILTER function, but it is simpler to use.</span></span> <span data-ttu-id="b1cd2-130">Voici un exemple qui retourne uniquement les dates auxquelles la valeur Internet Sales Amount est supérieure à 15 000 $ :</span><span class="sxs-lookup"><span data-stu-id="b1cd2-130">Here is an example that returns only those dates where Internet Sales Amount is greater than $15,000:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Date].MEMBERS}   
HAVING [Measures].[Internet Sales Amount]>15000  
ON ROWS  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1cd2-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1cd2-131">See Also</span></span>  
 [<span data-ttu-id="b1cd2-132">Spécification du contenu d’un axe de secteur &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b1cd2-132">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
