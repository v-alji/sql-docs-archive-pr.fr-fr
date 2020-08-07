---
title: Autoexists | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 56283497-624c-45b5-8a0d-036b0e331d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd35958a364456c12d58392afe3754f6adcf97b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611374"
---
# <a name="autoexists"></a><span data-ttu-id="cf20d-102">Autoexists</span><span class="sxs-lookup"><span data-stu-id="cf20d-102">Autoexists</span></span>
  <span data-ttu-id="cf20d-103">La fonctionnalité d’auto-existence, ou *autoexists* , limite l’espace du cube aux cellules qui existent réellement dans le cube, par opposition à celles qui pourraient exister en créant toutes les combinaisons possibles de membres de la hiérarchie d’attribut à partir de la même hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="cf20d-103">The concept of *autoexists* limits the cube space to those cells that actually exist in the cube in contraposition to those that might exist as a result of creating all possible combinations of attribute hierarchy members from the same hierarchy.</span></span> <span data-ttu-id="cf20d-104">En effet, les membres d'une hiérarchie d'attribut ne peuvent coexister avec les membres d'une autre hiérarchie d'attribut au sein de la même dimension.</span><span class="sxs-lookup"><span data-stu-id="cf20d-104">This is because members of one attribute hierarchy cannot exist with members of another attribute hierarchy in the same dimension.</span></span> <span data-ttu-id="cf20d-105">Lorsque deux hiérarchies d'attribut, ou plus, de la même dimension sont utilisées dans une instruction SELECT, Analysis Services évalue les expressions des attributs pour s'assurer que les membres de ces attributs sont correctement limités afin de répondre aux critères de tous les autres attributs.</span><span class="sxs-lookup"><span data-stu-id="cf20d-105">When two or more attribute hierarchies of the same dimension are used in a SELECT statement, Analysis Services evaluates the attributes' expressions to make sure that the members of those attributes are properly confined to meet the criteria of all other attributes.</span></span>  
  
 <span data-ttu-id="cf20d-106">Supposons, par exemple, que vous utilisez des attributs de la dimension de Geography.</span><span class="sxs-lookup"><span data-stu-id="cf20d-106">For example, suppose you are working with attributes from the Geography dimension.</span></span> <span data-ttu-id="cf20d-107">Si vous avez une expression qui retourne tous les membres de l'attribut Ville et une autre expression qui limite les membres de l'attribut Pays à tous les pays d'Europe, il en résultera une limitation des membres de l'attribut Ville aux seules villes qui appartiennent à des pays d'Europe.</span><span class="sxs-lookup"><span data-stu-id="cf20d-107">If you have one expression that returns all members from the City attribute and another expression that confines members from the Country attribute to all countries in Europe, then this will result in the City members being confined to only those cities that belong to countries in Europe.</span></span> <span data-ttu-id="cf20d-108">Cela est dû à la particularité de la fonctionnalité Autoexists d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="cf20d-108">This is because of the autoexists characteristic of Analysis Services.</span></span> <span data-ttu-id="cf20d-109">En effet, elle tente d'empêcher que des enregistrements de la dimension exclus d'une expression d'attribut soient exclus par les autres expressions d'attributs.</span><span class="sxs-lookup"><span data-stu-id="cf20d-109">Autoexists only applies to attributes from the same dimension because it tries to prevent the dimension records excluded in one attribute expression from being included by the other attribute expressions.</span></span> <span data-ttu-id="cf20d-110">La fonctionnalité Autoexists peut également être interprétée comme l'intersection obtenue entre les différentes expressions d'attributs sur les lignes de la dimension.</span><span class="sxs-lookup"><span data-stu-id="cf20d-110">Autoexists can also be understood as the resulting intersection of the different attributes expressions over the dimension rows.</span></span>  
  
## <a name="cell-existence"></a><span data-ttu-id="cf20d-111">Existence des cellules</span><span class="sxs-lookup"><span data-stu-id="cf20d-111">Cell Existence</span></span>  
 <span data-ttu-id="cf20d-112">Les cellules suivantes existent toujours :</span><span class="sxs-lookup"><span data-stu-id="cf20d-112">The following cells always exist:</span></span>  
  
-   <span data-ttu-id="cf20d-113">Le membre (All), de chaque hiérarchie, lorsqu'il est croisé avec des membres d'autres hiérarchies dans la même dimension.</span><span class="sxs-lookup"><span data-stu-id="cf20d-113">The (All) member, of every hierarchy, when crossed with members of other hierarchies in the same dimension.</span></span>  
  
-   <span data-ttu-id="cf20d-114">Les membres calculés lorsqu'ils sont croisés avec leurs frères et sœurs non calculés, ou avec les parents ou descendants de leurs frères et sœurs non calculés.</span><span class="sxs-lookup"><span data-stu-id="cf20d-114">Calculated members when crossed with their non-calculated siblings, or with the parents or descendants of their non-calculated siblings.</span></span>  
  
## <a name="providing-non-existing-cells"></a><span data-ttu-id="cf20d-115">Création de cellules inexistantes</span><span class="sxs-lookup"><span data-stu-id="cf20d-115">Providing Non-existing cells</span></span>  
 <span data-ttu-id="cf20d-116">Une cellule inexistante est une cellule fournie par le système en réponse à une requête ou à un calcul qui demande une cellule qui n'existe pas dans le cube.</span><span class="sxs-lookup"><span data-stu-id="cf20d-116">A non-existing cell is a cell provided by the system as a response to a query or calculation that requests a cell that does not exist in the cube.</span></span> <span data-ttu-id="cf20d-117">Par exemple, si vous travaillez avec un cube muni d'une hiérarchie d'attribut Ville, d'une hiérarchie d'attribut Pays qui appartient à la dimension Zone géographique, et d'une mesure Montant des ventes sur Internet, l'espace de ce cube inclut uniquement les membres qui coexistent entre eux.</span><span class="sxs-lookup"><span data-stu-id="cf20d-117">For example, if you have a cube that has a City attribute hierarchy and a Country attribute hierarchy that belong to the Geography dimension, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="cf20d-118">Par exemple, si la hiérarchie d'attribut Ville inclut les villes de New York, Londres, Paris, Tokyo et Melbourne et la hiérarchie d'attribut Pays les pays États-Unis, Royaume-Uni, France, Japon et Australie, l'espace du cube n'inclut pas l'espace (cellule) à l'intersection de Paris et États-Unis.</span><span class="sxs-lookup"><span data-stu-id="cf20d-118">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="cf20d-119">Lorsque vous interrogez des cellules qui n'existent pas, ces cellules retournent des valeurs NULL, ce qui signifie qu'elles ne peuvent pas contenir des calculs et que vous ne pouvez pas définir un calcul autorisé à écrire dans l'espace concerné.</span><span class="sxs-lookup"><span data-stu-id="cf20d-119">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="cf20d-120">Par exemple, l'instruction suivante inclut des cellules qui n'existent pas :</span><span class="sxs-lookup"><span data-stu-id="cf20d-120">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="cf20d-121">Cette requête utilise la fonction [Members (Set) (MDX)](/sql/mdx/members-set-mdx) pour retourner l’ensemble de membres de la hiérarchie d’attribut Gender sur l’axe des colonnes, puis croise cet ensemble avec l’ensemble de membres spécifié à partir de la hiérarchie d’attribut Customer sur l’axe des lignes.</span><span class="sxs-lookup"><span data-stu-id="cf20d-121">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="cf20d-122">Lorsque vous exécutez la requête ci-dessus, la cellule à l'intersection de Aaron A. Allen et Female affiche une valeur NULL,</span><span class="sxs-lookup"><span data-stu-id="cf20d-122">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="cf20d-123">tout comme la cellule à l'intersection d'Abigail Clark et Male.</span><span class="sxs-lookup"><span data-stu-id="cf20d-123">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="cf20d-124">Ces cellules n'existent pas et ne peuvent contenir de valeur. En revanche, les cellules non existantes peuvent apparaître dans le résultat que retourne une requête.</span><span class="sxs-lookup"><span data-stu-id="cf20d-124">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="cf20d-125">Quand vous utilisez la fonction [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) pour retourner le produit croisé des membres de la hiérarchie d’attributs à partir des hiérarchies d’attributs de la même dimension, l’existence automatique limite les tuples retournés à l’ensemble des tuples qui existent réellement, au lieu de retourner un produit cartésien complet.</span><span class="sxs-lookup"><span data-stu-id="cf20d-125">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="cf20d-126">Par exemple, exécutez et examinez les résultats de l'exécution de la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="cf20d-126">For example, run and then examine the results from the execution of the following query.</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[State-Province].Members  
  ) ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="cf20d-127">Remarquez l'emploi de 0, soit la formule abrégée de Axes(0), pour désigner l'axe des colonnes.</span><span class="sxs-lookup"><span data-stu-id="cf20d-127">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="cf20d-128">La requête ci-dessus retourne uniquement les cellules des membres de chaque hiérarchie d'attribut dans la requête qui coexistent entre eux.</span><span class="sxs-lookup"><span data-stu-id="cf20d-128">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="cf20d-129">La requête précédente peut également être écrite à l’aide de la nouvelle variante \* de la fonction [CrossJoin (MDX)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="cf20d-129">The previous query can also be written using the new \* variant of the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="cf20d-130">Cette requête peut aussi être écrite de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="cf20d-130">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="cf20d-131">Les valeurs retournées des cellules sont identiques, même si les métadonnées dans l'ensemble de résultats apparaissent différemment.</span><span class="sxs-lookup"><span data-stu-id="cf20d-131">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="cf20d-132">Par exemple, dans la requête ci-dessus, la hiérarchie Country a été déplacée vers l'axe de segment (dans la clause WHERE) et ne peut donc s'afficher de manière explicite dans l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="cf20d-132">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="cf20d-133">Chacune de ces trois requêtes précédentes illustre l’effet du comportement de l’auto-existence dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf20d-133">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="deep-and-shallow-autoexists"></a><span data-ttu-id="cf20d-134">Fonctionnalités Deep Autoexists et Shallow Autoexists</span><span class="sxs-lookup"><span data-stu-id="cf20d-134">Deep and Shallow Autoexists</span></span>  
 <span data-ttu-id="cf20d-135">Autoexists peut être appliquée en profondeur ou superficiellement aux expressions.</span><span class="sxs-lookup"><span data-stu-id="cf20d-135">Autoexists can be applied to the expressions as Deep or Shallow.</span></span> <span data-ttu-id="cf20d-136">`Deep Autoexists` signifie que toutes les expressions seront évaluées pour rencontrer l'espace le plus profond possible après l'application des expressions de découpage, des expressions de sous-sélection dans l'axe, etc.</span><span class="sxs-lookup"><span data-stu-id="cf20d-136">`Deep Autoexists` means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span> <span data-ttu-id="cf20d-137">`Shallow Autoexists` permet d'évaluer les expressions externes avant l'expression actuelle et de passer ces résultats à l'expression actuelle.</span><span class="sxs-lookup"><span data-stu-id="cf20d-137">`Shallow Autoexists` means that external expressions are evaluated before the current expression and those results are passed to the current expression.</span></span> <span data-ttu-id="cf20d-138">La fonctionnalité Deep Autoexists est paramétrée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cf20d-138">The default setting is deep autoexists.</span></span>  
  
 <span data-ttu-id="cf20d-139">Le scénario et les exemples suivants illustrent les différents types de fonctionnalités Autoexists.</span><span class="sxs-lookup"><span data-stu-id="cf20d-139">The following scenario and samples will help to illustrate the different types of Autoexistss.</span></span> <span data-ttu-id="cf20d-140">Dans les exemples suivants, nous allons créer deux jeux : l'un sous forme d'expression calculée et l'autre sous forme d'expression constante.</span><span class="sxs-lookup"><span data-stu-id="cf20d-140">In the following examples two sets will be created: one as a calculated expression and the other as a constant expression.</span></span>  
  
 `//Obtain the Top 10 best reseller selling products by Name`  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="cf20d-141">Le jeu de résultats obtenu est le suivant :</span><span class="sxs-lookup"><span data-stu-id="cf20d-141">The obtained result set is:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="cf20d-142">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-142">**Reseller Sales Amount**</span></span>|<span data-ttu-id="cf20d-143">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-143">**Discount Amount**</span></span>|<span data-ttu-id="cf20d-144">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-144">**PCT Discount**</span></span>|  
|<span data-ttu-id="cf20d-145">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="cf20d-145">**Mountain-200**</span></span>|<span data-ttu-id="cf20d-146">**14 356 699,36 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-146">**$14,356,699.36**</span></span>|<span data-ttu-id="cf20d-147">**19 012,71 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-147">**$19,012.71**</span></span>|<span data-ttu-id="cf20d-148">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-148">**0.13%**</span></span>|  
|<span data-ttu-id="cf20d-149">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="cf20d-149">**Road-250**</span></span>|<span data-ttu-id="cf20d-150">**9 377 457,68 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-150">**$9,377,457.68**</span></span>|<span data-ttu-id="cf20d-151">**4 032,47 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-151">**$4,032.47**</span></span>|<span data-ttu-id="cf20d-152">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-152">**0.04%**</span></span>|  
|<span data-ttu-id="cf20d-153">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="cf20d-153">**Mountain-100**</span></span>|<span data-ttu-id="cf20d-154">**8 568 958,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-154">**$8,568,958.27**</span></span>|<span data-ttu-id="cf20d-155">**139 393,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-155">**$139,393.27**</span></span>|<span data-ttu-id="cf20d-156">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-156">**1.63%**</span></span>|  
|<span data-ttu-id="cf20d-157">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="cf20d-157">**Road-650**</span></span>|<span data-ttu-id="cf20d-158">**7 442 141,81 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-158">**$7,442,141.81**</span></span>|<span data-ttu-id="cf20d-159">**39 698,30 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-159">**$39,698.30**</span></span>|<span data-ttu-id="cf20d-160">**0,53 %**</span><span class="sxs-lookup"><span data-stu-id="cf20d-160">**0.53%**</span></span>|  
|<span data-ttu-id="cf20d-161">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="cf20d-161">**Touring-1000**</span></span>|<span data-ttu-id="cf20d-162">**6 723 794,29 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-162">**$6,723,794.29**</span></span>|<span data-ttu-id="cf20d-163">**166 144,17 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-163">**$166,144.17**</span></span>|<span data-ttu-id="cf20d-164">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-164">**2.47%**</span></span>|  
|<span data-ttu-id="cf20d-165">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="cf20d-165">**Road-550-W**</span></span>|<span data-ttu-id="cf20d-166">**3 668 383,88 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-166">**$3,668,383.88**</span></span>|<span data-ttu-id="cf20d-167">**1 901,97 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-167">**$1,901.97**</span></span>|<span data-ttu-id="cf20d-168">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-168">**0.05%**</span></span>|  
|<span data-ttu-id="cf20d-169">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="cf20d-169">**Road-350-W**</span></span>|<span data-ttu-id="cf20d-170">**3 665 932,31 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-170">**$3,665,932.31**</span></span>|<span data-ttu-id="cf20d-171">**20 946,50 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-171">**$20,946.50**</span></span>|<span data-ttu-id="cf20d-172">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-172">**0.57%**</span></span>|  
|<span data-ttu-id="cf20d-173">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="cf20d-173">**HL Mountain Frame**</span></span>|<span data-ttu-id="cf20d-174">**3 365 069,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-174">**$3,365,069.27**</span></span>|<span data-ttu-id="cf20d-175">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="cf20d-175">**$174.11**</span></span>|<span data-ttu-id="cf20d-176">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-176">**0.01%**</span></span>|  
|<span data-ttu-id="cf20d-177">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="cf20d-177">**Road-150**</span></span>|<span data-ttu-id="cf20d-178">**2 363 805,16 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-178">**$2,363,805.16**</span></span>|<span data-ttu-id="cf20d-179">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="cf20d-179">**$0.00**</span></span>|<span data-ttu-id="cf20d-180">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-180">**0.00%**</span></span>|  
|<span data-ttu-id="cf20d-181">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="cf20d-181">**Touring-3000**</span></span>|<span data-ttu-id="cf20d-182">**2 046 508,26 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-182">**$2,046,508.26**</span></span>|<span data-ttu-id="cf20d-183">**79 582,15 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-183">**$79,582.15**</span></span>|<span data-ttu-id="cf20d-184">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-184">**3.89%**</span></span>|  
  
 <span data-ttu-id="cf20d-185">Le jeu de produits obtenu semble être le même que jeu Preferred10Products, qui se présente ainsi :</span><span class="sxs-lookup"><span data-stu-id="cf20d-185">The obtained set of products seems to be the same as Preferred10Products; so, verifying the Preferred10Products set:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="cf20d-186">Conformément aux résultats suivants, les deux jeux (Top10SellingProducts, Preferred10Products) sont identiques :</span><span class="sxs-lookup"><span data-stu-id="cf20d-186">As per the following results, both sets (Top10SellingProducts, Preferred10Products) are the same</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="cf20d-187">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-187">**Reseller Sales Amount**</span></span>|<span data-ttu-id="cf20d-188">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-188">**Discount Amount**</span></span>|<span data-ttu-id="cf20d-189">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-189">**PCT Discount**</span></span>|  
|<span data-ttu-id="cf20d-190">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="cf20d-190">**Mountain-200**</span></span>|<span data-ttu-id="cf20d-191">**14 356 699,36 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-191">**$14,356,699.36**</span></span>|<span data-ttu-id="cf20d-192">**19 012,71 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-192">**$19,012.71**</span></span>|<span data-ttu-id="cf20d-193">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-193">**0.13%**</span></span>|  
|<span data-ttu-id="cf20d-194">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="cf20d-194">**Road-250**</span></span>|<span data-ttu-id="cf20d-195">**9 377 457,68 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-195">**$9,377,457.68**</span></span>|<span data-ttu-id="cf20d-196">**4 032,47 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-196">**$4,032.47**</span></span>|<span data-ttu-id="cf20d-197">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-197">**0.04%**</span></span>|  
|<span data-ttu-id="cf20d-198">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="cf20d-198">**Mountain-100**</span></span>|<span data-ttu-id="cf20d-199">**8 568 958,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-199">**$8,568,958.27**</span></span>|<span data-ttu-id="cf20d-200">**139 393,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-200">**$139,393.27**</span></span>|<span data-ttu-id="cf20d-201">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-201">**1.63%**</span></span>|  
|<span data-ttu-id="cf20d-202">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="cf20d-202">**Road-650**</span></span>|<span data-ttu-id="cf20d-203">**7 442 141,81 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-203">**$7,442,141.81**</span></span>|<span data-ttu-id="cf20d-204">**39 698,30 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-204">**$39,698.30**</span></span>|<span data-ttu-id="cf20d-205">**0,53 %**</span><span class="sxs-lookup"><span data-stu-id="cf20d-205">**0.53%**</span></span>|  
|<span data-ttu-id="cf20d-206">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="cf20d-206">**Touring-1000**</span></span>|<span data-ttu-id="cf20d-207">**6 723 794,29 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-207">**$6,723,794.29**</span></span>|<span data-ttu-id="cf20d-208">**166 144,17 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-208">**$166,144.17**</span></span>|<span data-ttu-id="cf20d-209">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-209">**2.47%**</span></span>|  
|<span data-ttu-id="cf20d-210">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="cf20d-210">**Road-550-W**</span></span>|<span data-ttu-id="cf20d-211">**3 668 383,88 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-211">**$3,668,383.88**</span></span>|<span data-ttu-id="cf20d-212">**1 901,97 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-212">**$1,901.97**</span></span>|<span data-ttu-id="cf20d-213">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-213">**0.05%**</span></span>|  
|<span data-ttu-id="cf20d-214">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="cf20d-214">**Road-350-W**</span></span>|<span data-ttu-id="cf20d-215">**3 665 932,31 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-215">**$3,665,932.31**</span></span>|<span data-ttu-id="cf20d-216">**20 946,50 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-216">**$20,946.50**</span></span>|<span data-ttu-id="cf20d-217">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-217">**0.57%**</span></span>|  
|<span data-ttu-id="cf20d-218">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="cf20d-218">**HL Mountain Frame**</span></span>|<span data-ttu-id="cf20d-219">**3 365 069,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-219">**$3,365,069.27**</span></span>|<span data-ttu-id="cf20d-220">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="cf20d-220">**$174.11**</span></span>|<span data-ttu-id="cf20d-221">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-221">**0.01%**</span></span>|  
|<span data-ttu-id="cf20d-222">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="cf20d-222">**Road-150**</span></span>|<span data-ttu-id="cf20d-223">**2 363 805,16 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-223">**$2,363,805.16**</span></span>|<span data-ttu-id="cf20d-224">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="cf20d-224">**$0.00**</span></span>|<span data-ttu-id="cf20d-225">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-225">**0.00%**</span></span>|  
|<span data-ttu-id="cf20d-226">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="cf20d-226">**Touring-3000**</span></span>|<span data-ttu-id="cf20d-227">**2 046 508,26 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-227">**$2,046,508.26**</span></span>|<span data-ttu-id="cf20d-228">**79 582,15 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-228">**$79,582.15**</span></span>|<span data-ttu-id="cf20d-229">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-229">**3.89%**</span></span>|  
  
 <span data-ttu-id="cf20d-230">L'exemple suivant illustre le concept de la fonctionnalité Deep Autoexists.</span><span class="sxs-lookup"><span data-stu-id="cf20d-230">The following example will illustrate the concept of deep Autoexists.</span></span> <span data-ttu-id="cf20d-231">Dans l'exemple, nous filtrons Top10SellingProducts sur l'attribut [Product].[Product Line] pour les membres du groupe [Mountain].</span><span class="sxs-lookup"><span data-stu-id="cf20d-231">In the example we are filtering Top10SellingProducts by [Product].[Product Line] attribute for those in [Mountain] group.</span></span> <span data-ttu-id="cf20d-232">Notez que les deux attributs (slicer et axis) appartiennent à la même dimension, [Product].</span><span class="sxs-lookup"><span data-stu-id="cf20d-232">Note that both attributes (slicer and axis) belong to the same dimension, [Product].</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `// Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="cf20d-233">Génère les jeux de résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="cf20d-233">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="cf20d-234">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-234">**Reseller Sales Amount**</span></span>|<span data-ttu-id="cf20d-235">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-235">**Discount Amount**</span></span>|<span data-ttu-id="cf20d-236">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-236">**PCT Discount**</span></span>|  
|<span data-ttu-id="cf20d-237">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="cf20d-237">**Mountain-200**</span></span>|<span data-ttu-id="cf20d-238">**14 356 699,36 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-238">**$14,356,699.36**</span></span>|<span data-ttu-id="cf20d-239">**19 012,71 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-239">**$19,012.71**</span></span>|<span data-ttu-id="cf20d-240">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-240">**0.13%**</span></span>|  
|<span data-ttu-id="cf20d-241">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="cf20d-241">**Mountain-100**</span></span>|<span data-ttu-id="cf20d-242">**8 568 958,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-242">**$8,568,958.27**</span></span>|<span data-ttu-id="cf20d-243">**139 393,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-243">**$139,393.27**</span></span>|<span data-ttu-id="cf20d-244">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-244">**1.63%**</span></span>|  
|<span data-ttu-id="cf20d-245">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="cf20d-245">**HL Mountain Frame**</span></span>|<span data-ttu-id="cf20d-246">**3 365 069,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-246">**$3,365,069.27**</span></span>|<span data-ttu-id="cf20d-247">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="cf20d-247">**$174.11**</span></span>|<span data-ttu-id="cf20d-248">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-248">**0.01%**</span></span>|  
|<span data-ttu-id="cf20d-249">**Mountain-300**</span><span class="sxs-lookup"><span data-stu-id="cf20d-249">**Mountain-300**</span></span>|<span data-ttu-id="cf20d-250">**1 907 249,38 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-250">**$1,907,249.38**</span></span>|<span data-ttu-id="cf20d-251">**$876.95**</span><span class="sxs-lookup"><span data-stu-id="cf20d-251">**$876.95**</span></span>|<span data-ttu-id="cf20d-252">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-252">**0.05%**</span></span>|  
|<span data-ttu-id="cf20d-253">**Mountain-500**</span><span class="sxs-lookup"><span data-stu-id="cf20d-253">**Mountain-500**</span></span>|<span data-ttu-id="cf20d-254">**1 067 327,31 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-254">**$1,067,327.31**</span></span>|<span data-ttu-id="cf20d-255">**17 266,09 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-255">**$17,266.09**</span></span>|<span data-ttu-id="cf20d-256">**1,62%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-256">**1.62%**</span></span>|  
|<span data-ttu-id="cf20d-257">**Mountain-400-W**</span><span class="sxs-lookup"><span data-stu-id="cf20d-257">**Mountain-400-W**</span></span>|<span data-ttu-id="cf20d-258">**592 450,05 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-258">**$592,450.05**</span></span>|<span data-ttu-id="cf20d-259">**$303.49**</span><span class="sxs-lookup"><span data-stu-id="cf20d-259">**$303.49**</span></span>|<span data-ttu-id="cf20d-260">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-260">**0.05%**</span></span>|  
|<span data-ttu-id="cf20d-261">**LL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="cf20d-261">**LL Mountain Frame**</span></span>|<span data-ttu-id="cf20d-262">**521 864,42 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-262">**$521,864.42**</span></span>|<span data-ttu-id="cf20d-263">**$252.41**</span><span class="sxs-lookup"><span data-stu-id="cf20d-263">**$252.41**</span></span>|<span data-ttu-id="cf20d-264">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-264">**0.05%**</span></span>|  
|<span data-ttu-id="cf20d-265">**ML Mountain Frame-W**</span><span class="sxs-lookup"><span data-stu-id="cf20d-265">**ML Mountain Frame-W**</span></span>|<span data-ttu-id="cf20d-266">**482 953,16 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-266">**$482,953.16**</span></span>|<span data-ttu-id="cf20d-267">**$206,95**</span><span class="sxs-lookup"><span data-stu-id="cf20d-267">**$206.95**</span></span>|<span data-ttu-id="cf20d-268">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-268">**0.04%**</span></span>|  
|<span data-ttu-id="cf20d-269">**ML Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="cf20d-269">**ML Mountain Frame**</span></span>|<span data-ttu-id="cf20d-270">**343 785,29 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-270">**$343,785.29**</span></span>|<span data-ttu-id="cf20d-271">**$161.82**</span><span class="sxs-lookup"><span data-stu-id="cf20d-271">**$161.82**</span></span>|<span data-ttu-id="cf20d-272">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-272">**0.05%**</span></span>|  
|<span data-ttu-id="cf20d-273">**Women's Mountain Shorts**</span><span class="sxs-lookup"><span data-stu-id="cf20d-273">**Women's Mountain Shorts**</span></span>|<span data-ttu-id="cf20d-274">**260 304,09 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-274">**$260,304.09**</span></span>|<span data-ttu-id="cf20d-275">**6 675,56 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-275">**$6,675.56**</span></span>|<span data-ttu-id="cf20d-276">**2,56%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-276">**2.56%**</span></span>|  
  
 <span data-ttu-id="cf20d-277">Dans le jeu de résultats ci-dessus, nous avons sept nouveaux venus dans la liste des articles Top10SellingProducts ; de plus, Mountain-200, Mountain-100 et HL Mountain Frame ont été déplacés en haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="cf20d-277">In the above result set we have seven newcomers to the list of Top10SellingProducts and Mountain-200, Mountain-100, and HL Mountain Frame have moved to the top of the list.</span></span> <span data-ttu-id="cf20d-278">Dans le jeu de résultats précédent, ces trois valeurs étaient entrecoupées.</span><span class="sxs-lookup"><span data-stu-id="cf20d-278">In the previous result set those three values were interspersed.</span></span>  
  
 <span data-ttu-id="cf20d-279">On parle alors de fonctionnalité Deep Autoexists, car le jeu Top10SellingProducts est évalué pour répondre aux conditions de découpage de la requête.</span><span class="sxs-lookup"><span data-stu-id="cf20d-279">This is called Deep Autoexists, because the Top10SellingProducts set is evaluated to meet the slicing conditions of the query.</span></span> <span data-ttu-id="cf20d-280">La fonctionnalité Deep Autoexists signifie que toutes les expressions seront évaluées pour rencontrer l'espace le plus profond possible après l'application des expressions de découpage, des expressions de sous-sélection dans l'axe, etc.</span><span class="sxs-lookup"><span data-stu-id="cf20d-280">Deep Autoexists means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span>  
  
 <span data-ttu-id="cf20d-281">Toutefois, vous pouvez souhaiter effectuer l'analyse sur Top10SellingProducts comme équivalent à Preferred10Products, comme dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="cf20d-281">However, one might want to be able to do the analysis over the Top10SellingProducts as equivalent to Preferred10Products, as in the following example:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="cf20d-282">Génère les jeux de résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="cf20d-282">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="cf20d-283">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-283">**Reseller Sales Amount**</span></span>|<span data-ttu-id="cf20d-284">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-284">**Discount Amount**</span></span>|<span data-ttu-id="cf20d-285">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-285">**PCT Discount**</span></span>|  
|<span data-ttu-id="cf20d-286">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="cf20d-286">**Mountain-200**</span></span>|<span data-ttu-id="cf20d-287">**14 356 699,36 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-287">**$14,356,699.36**</span></span>|<span data-ttu-id="cf20d-288">**19 012,71 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-288">**$19,012.71**</span></span>|<span data-ttu-id="cf20d-289">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-289">**0.13%**</span></span>|  
|<span data-ttu-id="cf20d-290">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="cf20d-290">**Mountain-100**</span></span>|<span data-ttu-id="cf20d-291">**8 568 958,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-291">**$8,568,958.27**</span></span>|<span data-ttu-id="cf20d-292">**139 393,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-292">**$139,393.27**</span></span>|<span data-ttu-id="cf20d-293">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-293">**1.63%**</span></span>|  
|<span data-ttu-id="cf20d-294">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="cf20d-294">**HL Mountain Frame**</span></span>|<span data-ttu-id="cf20d-295">**3 365 069,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-295">**$3,365,069.27**</span></span>|<span data-ttu-id="cf20d-296">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="cf20d-296">**$174.11**</span></span>|<span data-ttu-id="cf20d-297">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-297">**0.01%**</span></span>|  
  
 <span data-ttu-id="cf20d-298">Dans les résultats ci-dessus, le découpage donne un résultat qui contient uniquement les produits de Preferred10Products qui font partie du groupe [Mountain] dans [Product].[Product Line], comme prévu car Preferred10Products est une expression constante.</span><span class="sxs-lookup"><span data-stu-id="cf20d-298">In the above results, the slicing gives a result that contains only those products from Preferred10Products that are part of the [Mountain] group in [Product].[Product Line]; as expected, because Preferred10Products is a constant expression.</span></span>  
  
 <span data-ttu-id="cf20d-299">Ce jeu de résultats est également interprété comme une fonctionnalité Shallow Autoexists.</span><span class="sxs-lookup"><span data-stu-id="cf20d-299">This result set is also understood as Shallow Autoexists.</span></span> <span data-ttu-id="cf20d-300">En effet, l'expression est évaluée avant la clause de découpage.</span><span class="sxs-lookup"><span data-stu-id="cf20d-300">This is because the expression is evaluated before the slicing clause.</span></span> <span data-ttu-id="cf20d-301">Dans l'exemple précédent, l'expression était une expression constante à des fins d'illustration pour présenter le concept.</span><span class="sxs-lookup"><span data-stu-id="cf20d-301">In the previous example, the expression was a constant expression for illustration purposes in order to introduce the concept.</span></span>  
  
 <span data-ttu-id="cf20d-302">Le comportement d'Autoexists peut être modifié au niveau de la session à l'aide de la propriété de chaîne de connexion `Autoexists`.</span><span class="sxs-lookup"><span data-stu-id="cf20d-302">Autoexists behavior can be modified at the session level using the `Autoexists` connection string property.</span></span> <span data-ttu-id="cf20d-303">L’exemple suivant commence en ouvrant une nouvelle session et en ajoutant la propriété *Autoexists=3* à la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="cf20d-303">The following example begins by opening a new session and adding the *Autoexists=3* property to the connection string.</span></span> <span data-ttu-id="cf20d-304">Vous devez ouvrir une nouvelle connexion pour exécuter l'exemple.</span><span class="sxs-lookup"><span data-stu-id="cf20d-304">You must open a new connection in order to do the example.</span></span> <span data-ttu-id="cf20d-305">Une fois la connexion établie avec le paramètre Autoexists, elle reste effective jusqu'à ce qu'elle soit interrompue.</span><span class="sxs-lookup"><span data-stu-id="cf20d-305">Once the connection is established with the Autoexist setting it will remain in effect until that connection is finished.</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `//Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="cf20d-306">Le jeu de résultats suivant présente maintenant le comportement superficiel d'Autoexists.</span><span class="sxs-lookup"><span data-stu-id="cf20d-306">The following result set now shows the shallow behavior of Autoexists.</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="cf20d-307">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-307">**Reseller Sales Amount**</span></span>|<span data-ttu-id="cf20d-308">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-308">**Discount Amount**</span></span>|<span data-ttu-id="cf20d-309">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="cf20d-309">**PCT Discount**</span></span>|  
|<span data-ttu-id="cf20d-310">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="cf20d-310">**Mountain-200**</span></span>|<span data-ttu-id="cf20d-311">**14 356 699,36 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-311">**$14,356,699.36**</span></span>|<span data-ttu-id="cf20d-312">**19 012,71 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-312">**$19,012.71**</span></span>|<span data-ttu-id="cf20d-313">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-313">**0.13%**</span></span>|  
|<span data-ttu-id="cf20d-314">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="cf20d-314">**Mountain-100**</span></span>|<span data-ttu-id="cf20d-315">**8 568 958,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-315">**$8,568,958.27**</span></span>|<span data-ttu-id="cf20d-316">**139 393,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-316">**$139,393.27**</span></span>|<span data-ttu-id="cf20d-317">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-317">**1.63%**</span></span>|  
|<span data-ttu-id="cf20d-318">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="cf20d-318">**HL Mountain Frame**</span></span>|<span data-ttu-id="cf20d-319">**3 365 069,27 $**</span><span class="sxs-lookup"><span data-stu-id="cf20d-319">**$3,365,069.27**</span></span>|<span data-ttu-id="cf20d-320">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="cf20d-320">**$174.11**</span></span>|<span data-ttu-id="cf20d-321">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="cf20d-321">**0.01%**</span></span>|  
  
 <span data-ttu-id="cf20d-322">Le comportement d’Autoexists peut être modifié à l’aide du paramètre Autoexists = [1 | 2 | 3] dans la chaîne de connexion ; consultez les [Propriétés XMLA prises en charge &#40;les&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) et <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> l’utilisation des paramètres.</span><span class="sxs-lookup"><span data-stu-id="cf20d-322">Autoexists behavior can be modified by using the AUTOEXISTS=[1|2|3] parameter in the connection string; see [Supported XMLA Properties &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) and <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> for parameter usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf20d-323">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf20d-323">See Also</span></span>  
 <span data-ttu-id="cf20d-324">[Concepts clés dans MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="cf20d-324">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="cf20d-325">[Espace du cube](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="cf20d-325">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="cf20d-326">[Tuples](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="cf20d-326">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="cf20d-327">[Utilisation de membres, de tuples et de jeux &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="cf20d-327">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="cf20d-328">[Totaux visuels et non visuels](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="cf20d-328">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="cf20d-329">[Référence du langage MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="cf20d-329">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="cf20d-330">Référence MDX &#40;Multidimensional Expressions&#41;</span><span class="sxs-lookup"><span data-stu-id="cf20d-330">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
