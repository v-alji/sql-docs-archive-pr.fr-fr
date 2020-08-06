---
title: Espace du cube | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c3a012b4-9ca0-4fb8-9c26-5ecc0e2e2b2b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6a6da73815f06aa5ab80f6ad5a9d06227ed842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604192"
---
# <a name="cube-space"></a><span data-ttu-id="ba996-102">Espace du cube</span><span class="sxs-lookup"><span data-stu-id="ba996-102">Cube Space</span></span>
  <span data-ttu-id="ba996-103">L'espace du cube est le produit des membres des hiérarchies d'attribut d'un cube associés aux mesures du cube.</span><span class="sxs-lookup"><span data-stu-id="ba996-103">Cube space is the product of the members of a cube's attribute hierarchies with the cube's measures.</span></span> <span data-ttu-id="ba996-104">Par conséquent, l'espace du cube est déterminé par le produit combinatoire de tous les membres de la hiérarchie d'attribut dans le cube et par les mesures du cube, et définit la taille maximale du cube.</span><span class="sxs-lookup"><span data-stu-id="ba996-104">Therefore, the cube space is determined by the combinatorial product of all attribute hierarchy members in the cube and the cube's measures and defines the maximum size of the cube.</span></span> <span data-ttu-id="ba996-105">Il est important de noter que cet espace inclut toutes les combinaisons possibles de membres de la hiérarchie d'attribut ; même les combinaisons qui peuvent être jugées comme impossibles dans le monde réel, c'est-à-dire les combinaisons où la ville est Paris et les pays sont l'Angleterre, l'Espagne, le Japon, l'Inde ou ailleurs.</span><span class="sxs-lookup"><span data-stu-id="ba996-105">It is important to note that this space includes all possible combinations of attribute hierarchy members; even combinations that might be deem as impossible in the real world i.e. combinations where the city is Paris and the countries are England or Spain or Japan or India or elsewhere.</span></span>  
  
## <a name="autoexists-and-cube-space"></a><span data-ttu-id="ba996-106">Fonctionnalité Autoexists et espace du cube</span><span class="sxs-lookup"><span data-stu-id="ba996-106">Autoexists and cube space</span></span>  
 <span data-ttu-id="ba996-107">La fonctionnalité d'auto-existence, *Autoexists* limite l'espace du cube aux cellules qui existent réellement.</span><span class="sxs-lookup"><span data-stu-id="ba996-107">The concept of *autoexists* limits this cube space to those cells that actually exist.</span></span> <span data-ttu-id="ba996-108">Les membres d'une hiérarchie d'attribut au sein d'une dimension ne peuvent coexister avec les membres d'une autre hiérarchie d'attribut au sein de la même dimension.</span><span class="sxs-lookup"><span data-stu-id="ba996-108">Members of an attribute hierarchy in a dimension may not exist with members of another attribute hierarchy in the same dimension.</span></span>  
  
 <span data-ttu-id="ba996-109">Par exemple, si vous travaillez avec un cube muni d'une hiérarchie d'attribut Ville, d'une hiérarchie d'attribut Pays et d'une mesure Volume de vente Internet, l'espace du cube inclut uniquement les membres qui coexistent entre eux.</span><span class="sxs-lookup"><span data-stu-id="ba996-109">For example, if you have a cube that has a City attribute hierarchy, a Country attribute hierarchy, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="ba996-110">Par exemple, si la hiérarchie d'attribut Ville inclut les villes de New York, Londres, Paris, Tokyo et Melbourne et la hiérarchie d'attribut Pays les pays États-Unis, Royaume-Uni, France, Japon et Australie, l'espace du cube n'inclut pas l'espace (cellule) à l'intersection de Paris et États-Unis.</span><span class="sxs-lookup"><span data-stu-id="ba996-110">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="ba996-111">Lorsque vous interrogez des cellules qui n'existent pas, ces cellules retournent des valeurs NULL, ce qui signifie qu'elles ne peuvent pas contenir des calculs et que vous ne pouvez pas définir un calcul autorisé à écrire dans l'espace concerné.</span><span class="sxs-lookup"><span data-stu-id="ba996-111">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="ba996-112">Par exemple, l'instruction suivante inclut des cellules qui n'existent pas :</span><span class="sxs-lookup"><span data-stu-id="ba996-112">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ba996-113">Cette requête utilise la fonction [Members (Set) (MDX)](/sql/mdx/members-set-mdx) pour retourner l’ensemble de membres de la hiérarchie d’attribut Gender sur l’axe des colonnes, puis croise cet ensemble avec l’ensemble de membres spécifié à partir de la hiérarchie d’attribut Customer sur l’axe des lignes.</span><span class="sxs-lookup"><span data-stu-id="ba996-113">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="ba996-114">Lorsque vous exécutez la requête ci-dessus, la cellule à l'intersection de Aaron A. Allen et Female affiche une valeur NULL,</span><span class="sxs-lookup"><span data-stu-id="ba996-114">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="ba996-115">tout comme la cellule à l'intersection d'Abigail Clark et Male.</span><span class="sxs-lookup"><span data-stu-id="ba996-115">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="ba996-116">Ces cellules n'existent pas et ne peuvent contenir de valeur. En revanche, les cellules non existantes peuvent apparaître dans le résultat que retourne une requête.</span><span class="sxs-lookup"><span data-stu-id="ba996-116">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="ba996-117">Quand vous utilisez la fonction [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) pour retourner le produit croisé des membres de la hiérarchie d’attributs à partir des hiérarchies d’attributs de la même dimension, l’existence automatique limite les tuples retournés à l’ensemble des tuples qui existent réellement, au lieu de retourner un produit cartésien complet.</span><span class="sxs-lookup"><span data-stu-id="ba996-117">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="ba996-118">Par exemple, exécutez et examinez les résultats de l'exécution de la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="ba996-118">For example, run and then examine the results from the execution of the following query.</span></span>  
  
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
>  <span data-ttu-id="ba996-119">Remarquez l'emploi de 0, soit la formule abrégée de Axes(0), pour désigner l'axe des colonnes.</span><span class="sxs-lookup"><span data-stu-id="ba996-119">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="ba996-120">La requête ci-dessus retourne uniquement les cellules des membres de chaque hiérarchie d'attribut dans la requête qui coexistent entre eux.</span><span class="sxs-lookup"><span data-stu-id="ba996-120">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="ba996-121">La requête précédente peut également être écrite à l’aide de la nouvelle variante \* de la fonction [ \* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="ba996-121">The previous query can also be written using the new \* variant of the [\* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="ba996-122">Cette requête peut aussi être écrite de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="ba996-122">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="ba996-123">Les valeurs retournées des cellules sont identiques, même si les métadonnées dans l'ensemble de résultats apparaissent différemment.</span><span class="sxs-lookup"><span data-stu-id="ba996-123">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="ba996-124">Par exemple, dans la requête ci-dessus, la hiérarchie Country a été déplacée vers l'axe de segment (dans la clause WHERE) et ne peut donc s'afficher de manière explicite dans l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="ba996-124">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="ba996-125">Chacune de ces trois requêtes précédentes illustre l’effet du comportement de l’auto-existence dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba996-125">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="user-defined-hierarchies-and-cube-space"></a><span data-ttu-id="ba996-126">Hiérarchies définies par l'utilisateur et espace du cube</span><span class="sxs-lookup"><span data-stu-id="ba996-126">User-Defined Hierarchies and Cube Space</span></span>  
 <span data-ttu-id="ba996-127">Les exemples présentés précédemment dans cette rubrique définissent des positions au sein de l'espace du cube par le biais des hiérarchies d'attribut.</span><span class="sxs-lookup"><span data-stu-id="ba996-127">The previous examples in this topic define positions in cube space by using attribute hierarchies.</span></span> <span data-ttu-id="ba996-128">Néanmoins, vous pouvez également définir une position dans l'espace du cube en utilisant des hiérarchies définies par l'utilisateur qui ont été conçues à partir des hiérarchies d'attribut d'une dimension.</span><span class="sxs-lookup"><span data-stu-id="ba996-128">However, you can also define a position in cube space by using user-defined hierarchies that have been defined based on attribute hierarchies in a dimension.</span></span> <span data-ttu-id="ba996-129">Une hiérarchie définie par l'utilisateur est une hiérarchie de hiérarchies d'attribut conçue pour faciliter la navigation des utilisateurs dans les données du cube.</span><span class="sxs-lookup"><span data-stu-id="ba996-129">A user-defined hierarchy is a hierarchy of attribute hierarchies designed to facilitate browsing of cube data by users.</span></span>  
  
 <span data-ttu-id="ba996-130">Par exemple, la requête `CROSSJOIN` de la section précédente aurait pu aussi être écrite de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="ba996-130">For example, the `CROSSJOIN` query in the previous section could also have been written as follows:</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[Customer Geography].[State-Province].Members  
   )   
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="ba996-131">Dans la requête ci-dessus, la hiérarchie définie par l'utilisateur Customer Geography incluse dans la dimension Customer est utilisée pour définir la position dans l'espace du cube définie auparavant à l'aide d'une hiérarchie d'attribut.</span><span class="sxs-lookup"><span data-stu-id="ba996-131">In the previous query, the Customer Geography user-defined hierarchy within the Customer dimension is used to define the position in cube space that was previously defined by using an attribute hierarchy.</span></span> <span data-ttu-id="ba996-132">La même position dans l'espace du cube peut être définie soit au moyen de hiérarchies d'attribut, soit à l'aide de hiérarchies définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ba996-132">The identical position in cube space can be defined by using either attribute hierarchies or user-defined hierarchies.</span></span>  
  
##  <a name="attribute-relationships-and-cube-space"></a><a name="AttribRelationships"></a><span data-ttu-id="ba996-133">Relations d’attributs et espace du cube</span><span class="sxs-lookup"><span data-stu-id="ba996-133">Attribute Relationships and Cube Space</span></span>  
 <span data-ttu-id="ba996-134">La définition de relations d'attributs entre des attributs associés améliore les performances des requêtes (grâce à la création facilitée d'agrégations adaptées) et affecte le membre d'une hiérarchie d'attribut associée qui apparaît avec un membre de hiérarchie d'attribut.</span><span class="sxs-lookup"><span data-stu-id="ba996-134">Defining attribute relationships between related attributes improves query performance (by facilitating the creation of appropriate aggregations) and affects the member of a related attribute hierarchy that appears with an attribute hierarchy member.</span></span> <span data-ttu-id="ba996-135">Par exemple, lorsque vous définissez un tuple qui inclut un membre de la hiérarchie d'attribut City et que le tuple ne définit pas explicitement le membre de la hiérarchie d'attribut Country, vous pouvez vous attendre à ce que le membre par défaut de la hiérarchie d'attribut Country corresponde au membre associé de la hiérarchie d'attribut Country.</span><span class="sxs-lookup"><span data-stu-id="ba996-135">For example, when you define a tuple that includes a member from the City attribute hierarchy and the tuple does not explicitly define the Country attribute hierarchy member, you might expect that the default Country attribute hierarchy member would be the related member of the Country attribute hierarchy.</span></span> <span data-ttu-id="ba996-136">Néanmoins, cette situation ne vaut que si une relation d'attribut est définie entre les hiérarchies d'attribut City et Country.</span><span class="sxs-lookup"><span data-stu-id="ba996-136">However, this is only true if an attribute relationship is defined between the City attribute hierarchy and the Country attribute hierarchy.</span></span>  
  
 <span data-ttu-id="ba996-137">L'exemple ci-après retourne le membre d'une hiérarchie d'attribut associée qui ne figure pas de manière explicite dans la requête.</span><span class="sxs-lookup"><span data-stu-id="ba996-137">The following example returns the member of a related attribute hierarchy that is not included explicitly in the query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Country.CurrentMember.Name  
SELECT Measures.x ON 0,  
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ba996-138">Notez que le `WITH` mot clé est utilisé avec les fonctions [CurrentMember (MDX)](/sql/mdx/current-mdx) et [Name (MDX)](/sql/mdx/members-string-mdx) pour créer un membre calculé à utiliser dans la requête.</span><span class="sxs-lookup"><span data-stu-id="ba996-138">Notice that the `WITH` keyword is used with the [CurrentMember (MDX)](/sql/mdx/current-mdx) and [Name (MDX)](/sql/mdx/members-string-mdx) functions to create a calculated member for use in the query.</span></span> <span data-ttu-id="ba996-139">Pour plus d’informations, consultez [Requête MDX de base &#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="ba996-139">For more information, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
 <span data-ttu-id="ba996-140">Dans la requête précédente, le nom du membre de la hiérarchie d'attribut Country associé à chaque membre de la hiérarchie d'attribut State est retourné.</span><span class="sxs-lookup"><span data-stu-id="ba996-140">In the previous query, the name of the member of the Country attribute hierarchy that is associated with each member of the State attribute hierarchy is returned.</span></span> <span data-ttu-id="ba996-141">Le membre Country attendu apparaît (puisqu'une relation d'attribut est définie entre les attributs City et Country).</span><span class="sxs-lookup"><span data-stu-id="ba996-141">The expected Country member appears (because an attribute relationship is defined between the City and Country attributes).</span></span> <span data-ttu-id="ba996-142">Par contre, si aucune relation d'attribut n'est définie entre les hiérarchies d'attribut de la même dimension, le membre (All) doit être retourné comme dans la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="ba996-142">However, if no attribute relationship were defined between attribute hierarchies in the same dimension, the (All) member would be returned, as illustrated in the following query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Education.Currentmember.Name  
SELECT Measures.x  ON 0,   
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="ba996-143">Dans cette requête, le membre (All) (« All Customers ») est retourné parce qu'il n'existe aucune relation entre Education et City.</span><span class="sxs-lookup"><span data-stu-id="ba996-143">In the previous query, the (All) member ("All Customers") is returned, because there is no relationship between Education and City.</span></span> <span data-ttu-id="ba996-144">Le membre (All) de la hiérarchie d'attribut Education serait alors le membre par défaut de cette hiérarchie utilisé dans n'importe quel tuple impliquant la hiérarchie d'attribut City où aucun membre Education n'est explicitement fourni.</span><span class="sxs-lookup"><span data-stu-id="ba996-144">Therefore, the (All) member of the Education attribute hierarchy would be the default member of the Education attribute hierarchy used in any tuple involving the City attribute hierarchy where an Education member is not explicitly provided.</span></span>  
  
## <a name="calculation-context"></a><span data-ttu-id="ba996-145">Contexte de calcul</span><span class="sxs-lookup"><span data-stu-id="ba996-145">Calculation Context</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba996-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba996-146">See Also</span></span>  
 <span data-ttu-id="ba996-147">[Concepts clés dans MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ba996-147">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="ba996-148">[Tuples](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="ba996-148">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="ba996-149">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="ba996-149">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="ba996-150">[Utilisation de membres, de tuples et de jeux &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="ba996-150">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="ba996-151">[Totaux visuels et non visuels](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="ba996-151">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="ba996-152">[Référence du langage MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="ba996-152">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="ba996-153">Référence MDX &#40;Multidimensional Expressions&#41;</span><span class="sxs-lookup"><span data-stu-id="ba996-153">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
