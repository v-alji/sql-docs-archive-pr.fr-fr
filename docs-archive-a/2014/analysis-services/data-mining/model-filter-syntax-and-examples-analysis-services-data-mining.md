---
title: Syntaxe de filtre de modèle et exemples (Analysis Services-exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filter syntax [data mining]
- filters [data mining]
- filters [Analysis Services]
ms.assetid: c729d9b3-8fda-405e-9497-52b2d7493eae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7ca200d179c0fe81b948793a4b4478f71502657
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696331"
---
# <a name="model-filter-syntax-and-examples-analysis-services---data-mining"></a><span data-ttu-id="d9339-102">Syntaxe de filtre de modèle et exemples (Analysis Services - Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="d9339-102">Model Filter Syntax and Examples (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="d9339-103">Cette section fournit des informations détaillées sur la syntaxe des filtres de modèle, avec quelques exemples d'expressions.</span><span class="sxs-lookup"><span data-stu-id="d9339-103">This section provides detailed information about the syntax for model filters, together with sample expressions.</span></span>  
  
 
  
##  <a name="filter-syntax"></a><a name="bkmk_Syntax"></a><span data-ttu-id="d9339-104">Syntaxe de filtre</span><span class="sxs-lookup"><span data-stu-id="d9339-104">Filter Syntax</span></span>  
 <span data-ttu-id="d9339-105">Les expressions de filtre sont généralement équivalentes au contenu d'une clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="d9339-105">Filter expressions generally are equivalent to the content of a WHERE clause.</span></span> <span data-ttu-id="d9339-106">Vous pouvez connecter plusieurs conditions à l'aide des opérateurs logiques `AND`, `OR` et `NOT`.</span><span class="sxs-lookup"><span data-stu-id="d9339-106">You can connect multiple conditions by using the logical operators `AND`, `OR`, and `NOT`.</span></span>  
  
 <span data-ttu-id="d9339-107">Dans les tables imbriquées, vous pouvez également utiliser les opérateurs `EXISTS` et `NOT EXISTS`.</span><span class="sxs-lookup"><span data-stu-id="d9339-107">In nested tables, you can also use the `EXISTS` and `NOT EXISTS` operators.</span></span> <span data-ttu-id="d9339-108">Une condition `EXISTS` est évaluée à `true` si la sous-requête retourne au moins une ligne.</span><span class="sxs-lookup"><span data-stu-id="d9339-108">An `EXISTS` condition evaluates to `true` if the subquery returns at least one row.</span></span> <span data-ttu-id="d9339-109">Ceci est utile dans les cas où vous souhaitez restreindre le modèle aux cas qui contiennent une valeur particulière dans la table imbriquée : par exemple, les clients qui ont acheté un élément au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="d9339-109">This is useful in cases where you want to restrict the model to cases that contain a particular value in the nested table: for example, customers who have purchased an item at least once.</span></span>  
  
 <span data-ttu-id="d9339-110">Une condition `NOT EXISTS` est évaluée à `true` si la condition spécifiée dans la sous-requête n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="d9339-110">A `NOT EXISTS` condition evaluates to `true` if the condition specified in the subquery does not exist.</span></span> <span data-ttu-id="d9339-111">Un exemple est lorsque vous souhaitez restreindre le modèle aux clients qui n'ont jamais acheté un élément particulier.</span><span class="sxs-lookup"><span data-stu-id="d9339-111">An example is when you want to restrict the model to customers who have never purchased a particular item.</span></span>  
  
 <span data-ttu-id="d9339-112">La syntaxe générale est la suivante :</span><span class="sxs-lookup"><span data-stu-id="d9339-112">The general syntax is as follows:</span></span>  
  
```  
<filter>::=<predicate list>  | ( <predicate list> )  
<predicate list>::= <predicate> | [<logical_operator> <predicate list>]   
<logical_operator::= AND| OR  
<predicate>::= NOT <predicate>|( <predicate> ) <avPredicate> | <nestedTablePredicate> | ( <predicate> )   
<avPredicate>::= <columnName> <operator> <scalar> | <columnName> IS [NOT] NULL  
<operator>::= = | != | <> | > | >= | < | <=  
<nestedTablePredicate>::= EXISTS (<subquery>)  
<subquery>::=SELECT * FROM <columnName>[ WHERE  <predicate list> ]  
```  
  
 <span data-ttu-id="d9339-113">*filter*</span><span class="sxs-lookup"><span data-stu-id="d9339-113">*filter*</span></span>  
 <span data-ttu-id="d9339-114">Contient un ou plusieurs prédicats, connectés par des opérateurs logiques.</span><span class="sxs-lookup"><span data-stu-id="d9339-114">Contains one or more predicates, connected by logical operators.</span></span>  
  
 <span data-ttu-id="d9339-115">*predicate list*</span><span class="sxs-lookup"><span data-stu-id="d9339-115">*predicate list*</span></span>  
 <span data-ttu-id="d9339-116">Une ou plusieurs expressions de filtre valides, séparées par des opérateurs logiques.</span><span class="sxs-lookup"><span data-stu-id="d9339-116">One or more valid filter expressions, separated by logical operators.</span></span>  
  
 <span data-ttu-id="d9339-117">*NomColonne*</span><span class="sxs-lookup"><span data-stu-id="d9339-117">*columnName*</span></span>  
 <span data-ttu-id="d9339-118">Nom d'une colonne de structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d9339-118">The name of a mining structure column.</span></span>  
  
 <span data-ttu-id="d9339-119">opérateur logique</span><span class="sxs-lookup"><span data-stu-id="d9339-119">logical operator</span></span>  
 <span data-ttu-id="d9339-120">`AND`, `OR`, `NOT`</span><span class="sxs-lookup"><span data-stu-id="d9339-120">`AND`, `OR`, `NOT`</span></span>  
  
 <span data-ttu-id="d9339-121">*avPredicate*</span><span class="sxs-lookup"><span data-stu-id="d9339-121">*avPredicate*</span></span>  
 <span data-ttu-id="d9339-122">Expression de filtre qui peut s'appliquer uniquement à une colonne de structure d'exploration de données scalaire.</span><span class="sxs-lookup"><span data-stu-id="d9339-122">Filter expression that can be applied to scalar mining structure column only.</span></span> <span data-ttu-id="d9339-123">Une expression *avPredicate* peut être utilisée dans des filtres de modèle ou des filtres de table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="d9339-123">An *avPredicate* expression can be used in both model filters or nested table filters.</span></span>  
  
 <span data-ttu-id="d9339-124">Une expression qui utilise l'un des opérateurs suivants peut être appliquée uniquement à une colonne continue.</span><span class="sxs-lookup"><span data-stu-id="d9339-124">An expression that uses any of the following operators can only be applied to a continuous column.</span></span> <span data-ttu-id="d9339-125">:</span><span class="sxs-lookup"><span data-stu-id="d9339-125">:</span></span>  
  
-   <span data-ttu-id="d9339-126">**\<**(inférieur à)</span><span class="sxs-lookup"><span data-stu-id="d9339-126">**\<** (less than)</span></span>  
  
-   <span data-ttu-id="d9339-127">**>**(supérieur à)</span><span class="sxs-lookup"><span data-stu-id="d9339-127">**>** (greater than)</span></span>  
  
-   <span data-ttu-id="d9339-128">**>=**(supérieur ou égal à)</span><span class="sxs-lookup"><span data-stu-id="d9339-128">**>=** (greater than or equal to)</span></span>  
  
-   <span data-ttu-id="d9339-129">**\<=**(inférieur ou égal à)</span><span class="sxs-lookup"><span data-stu-id="d9339-129">**\<=** (less than or equal to)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9339-130">Quel que soit le type de données, ces opérateurs ne peuvent pas être appliqués à une colonne qui a le type `Discrete`, `Discretized` ou `Key`.</span><span class="sxs-lookup"><span data-stu-id="d9339-130">Regardless of the data type, these operators cannot be applied to a column that has the type `Discrete`, `Discretized`, or `Key`.</span></span>  
  
 <span data-ttu-id="d9339-131">Une expression qui utilise l'un des opérateurs suivants peut être appliquée uniquement à une colonne continue, discrète, discrétisée ou clé :</span><span class="sxs-lookup"><span data-stu-id="d9339-131">An expression that uses any of the following operators can be applied to a continuous, discrete, discretized, or key column:</span></span>  
  
-   <span data-ttu-id="d9339-132">**=** Equals</span><span class="sxs-lookup"><span data-stu-id="d9339-132">**=** (equals)</span></span>  
  
-   <span data-ttu-id="d9339-133">**! =** (différent de)</span><span class="sxs-lookup"><span data-stu-id="d9339-133">**!=** (not equal to)</span></span>  
  
-   <span data-ttu-id="d9339-134">**EST NULL**</span><span class="sxs-lookup"><span data-stu-id="d9339-134">**IS NULL**</span></span>  
  
 <span data-ttu-id="d9339-135">Si l'argument, *avPredicate*, s'applique à une colonne discrétisée, la valeur utilisée dans le filtre peut être toute valeur dans un compartiment spécifique.</span><span class="sxs-lookup"><span data-stu-id="d9339-135">If the argument, *avPredicate*, applies to a discretized column, the value used in the filter can be any value in a specific bucket.</span></span>  
  
 <span data-ttu-id="d9339-136">En d’autres termes, vous ne définissez pas la condition comme `AgeDisc = '25-35'`; au lieu de cela, vous calculez et utilisez une valeur à partir de cet intervalle.</span><span class="sxs-lookup"><span data-stu-id="d9339-136">In other words, you do not define the condition as `AgeDisc = '25-35'`, but instead compute and then use a value from that interval.</span></span>  
  
 <span data-ttu-id="d9339-137">Exemple :  `AgeDisc = 27`  signifie toute valeur dans le même intervalle que 27, ce qui dans ce cas correspond à 25-35.</span><span class="sxs-lookup"><span data-stu-id="d9339-137">Example:  `AgeDisc = 27`  means any value in the same interval as 27, which in this case is 25-35.</span></span>  
  
 <span data-ttu-id="d9339-138">*nestedTablePredicate*</span><span class="sxs-lookup"><span data-stu-id="d9339-138">*nestedTablePredicate*</span></span>  
 <span data-ttu-id="d9339-139">Expression de filtre qui s'applique à une table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="d9339-139">Filter expression that applies to a nested table.</span></span> <span data-ttu-id="d9339-140">Peut être utilisée uniquement dans les filtres de modèle.</span><span class="sxs-lookup"><span data-stu-id="d9339-140">Can be used in model filters only.</span></span>  
  
 <span data-ttu-id="d9339-141">L’argument de sous-requête de l’argument, *nestedTablePredicate*, peut s’appliquer uniquement à une colonne de structure d’exploration de données de table.</span><span class="sxs-lookup"><span data-stu-id="d9339-141">The sub-query argument of the argument, *nestedTablePredicate*, can only apply to a table mining structure column</span></span>  
  
 <span data-ttu-id="d9339-142">sous-requête</span><span class="sxs-lookup"><span data-stu-id="d9339-142">subquery</span></span>  
 <span data-ttu-id="d9339-143">Instruction SELECT suivie d'un prédicat ou d'une liste de prédicats valide.</span><span class="sxs-lookup"><span data-stu-id="d9339-143">A SELECT statement followed by a valid predicate or list of predicates.</span></span>  
  
 <span data-ttu-id="d9339-144">Tous les prédicats doivent être du type décrit dans *avPredicates*.</span><span class="sxs-lookup"><span data-stu-id="d9339-144">All the predicates must be of the type described in *avPredicates*.</span></span> <span data-ttu-id="d9339-145">En outre, les prédicats peuvent faire référence uniquement à des colonnes incluses dans la table imbriquée actuelle, identifiées par l'argument, *columnName*.</span><span class="sxs-lookup"><span data-stu-id="d9339-145">Furthermore, the predicates can refer only to columns that are included in the current nested table, identified by the argument, *columnName*.</span></span>  
  
### <a name="limitations-on-filter-syntax"></a><span data-ttu-id="d9339-146">Limitations relatives à la syntaxe de filtre</span><span class="sxs-lookup"><span data-stu-id="d9339-146">Limitations on Filter Syntax</span></span>  
 <span data-ttu-id="d9339-147">Les restrictions suivantes s'appliquent aux filtres :</span><span class="sxs-lookup"><span data-stu-id="d9339-147">The following restrictions apply to filters:</span></span>  
  
-   <span data-ttu-id="d9339-148">Un filtre peut contenir uniquement des prédicats simples.</span><span class="sxs-lookup"><span data-stu-id="d9339-148">A filter can contain only simple predicates.</span></span> <span data-ttu-id="d9339-149">Cela comprend les opérateurs mathématiques, les scalaires et les noms de colonnes.</span><span class="sxs-lookup"><span data-stu-id="d9339-149">These include mathematical operators, scalars, and column names.</span></span>  
  
-   <span data-ttu-id="d9339-150">Les fonctions définies par l'utilisateur ne sont pas prises en charge dans la syntaxe de filtre.</span><span class="sxs-lookup"><span data-stu-id="d9339-150">User-defined functions are not supported in the filter syntax.</span></span>  
  
-   <span data-ttu-id="d9339-151">Les opérateurs non booléens, tels que les signes plus ou moins, ne sont pas pris en charge dans la syntaxe de filtre.</span><span class="sxs-lookup"><span data-stu-id="d9339-151">Non-Boolean operators, such as the plus or minus signs, are not supported in the filter syntax.</span></span>  
  
## <a name="examples-of-filters"></a><span data-ttu-id="d9339-152">Exemples de filtres</span><span class="sxs-lookup"><span data-stu-id="d9339-152">Examples of Filters</span></span>  
 <span data-ttu-id="d9339-153">Les exemples suivants montrent l'utilisation de filtres appliqués à un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d9339-153">The following examples demonstrate the use of filters applied to a mining model.</span></span> <span data-ttu-id="d9339-154">Si vous créez l'expression de filtre à l'aide de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], dans la fenêtre **Propriété** et le volet **Expression** de la boîte de dialogue de filtre, vous obtiendriez uniquement la chaîne qui apparaît après les mots clés WITH FILTER.</span><span class="sxs-lookup"><span data-stu-id="d9339-154">If you create the filter expression by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Property** window and the **Expression** pane of the filter dialog box, you would see only the string that appears after the WITH FILTER keywords.</span></span> <span data-ttu-id="d9339-155">Ici, la définition de la structure d'exploration de données est incluse afin de simplifier la compréhension du type et de l'utilisation de colonne.</span><span class="sxs-lookup"><span data-stu-id="d9339-155">Here, the definition of the mining structure is included to make it easier to understand the column type and usage.</span></span>  
  
###  <a name="example-1-typical-case-level-filtering"></a><a name="bkmk_Ex1"></a> <span data-ttu-id="d9339-156">Exemple 1 : Filtrage par défaut au niveau du cas</span><span class="sxs-lookup"><span data-stu-id="d9339-156">Example 1: Typical Case-Level Filtering</span></span>  
 <span data-ttu-id="d9339-157">Cet exemple montre un filtre simple qui restreint les cas utilisés dans le modèle aux clients de plus de trente ans exerçant la profession (occupation) d'architecte.</span><span class="sxs-lookup"><span data-stu-id="d9339-157">This example shows a simple filter that restricts the cases used in the model to customers whose occupation is architect and whose age is over 30.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_1  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH FILTER (Age > 30 AND Occupation='Architect')  
```  
  

  
###  <a name="example-2-case-level-filtering-using-nested-table-attributes"></a><a name="bkmk_Ex2"></a> <span data-ttu-id="d9339-158">Exemple 2 : Filtrage au niveau du cas à l'aide d'attributs de tables imbriquées</span><span class="sxs-lookup"><span data-stu-id="d9339-158">Example 2: Case-Level Filtering using Nested Table Attributes</span></span>  
 <span data-ttu-id="d9339-159">Si votre structure d'exploration de données contient des tables imbriquées, vous pouvez filtrer sur l'existence d'une valeur dans une table imbriquée ou filtrer sur des lignes de table imbriquée qui contiennent une valeur spécifique.</span><span class="sxs-lookup"><span data-stu-id="d9339-159">If your mining structure contains nested tables, you can either filter on the existence of a value in a nested table, or filter on nested table rows that contain a specific value.</span></span> <span data-ttu-id="d9339-160">Cet exemple restreint les cas utilisés pour le modèle aux clients dont l'âge est supérieur à 30 et qui ont effectué au moins un achat incluant du lait.</span><span class="sxs-lookup"><span data-stu-id="d9339-160">This example restricts the cases used for the model to customers over the age of 30 who made at least one purchase that included milk.</span></span>  
  
 <span data-ttu-id="d9339-161">Comme le montre cet exemple, il n'est pas nécessaire que le filtre utilise uniquement des colonnes incluses dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="d9339-161">As this example shows, it is not necessary that the filter use only columns that are included in the model.</span></span> <span data-ttu-id="d9339-162">La table imbriquée **Products** fait partie de la structure d'exploration de données, mais elle n'est pas incluse dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d9339-162">The nested table **Products** is part of the mining structure, but is not included in the mining model.</span></span> <span data-ttu-id="d9339-163">Toutefois, vous pouvez toujours filtrer sur des valeurs et des attributs dans la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="d9339-163">However, you can still filter on values and attributes in the nested table.</span></span> <span data-ttu-id="d9339-164">Pour afficher les détails de ces cas, l'extraction doit être activée.</span><span class="sxs-lookup"><span data-stu-id="d9339-164">To view the details of these cases, drillthrough must be enabled.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_2  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH DRILLTHROUGH,   
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk')  
)  
```  
  
 
  
###  <a name="example-3-case-level-filtering-on-multiple-nested-table-attributes"></a><a name="bkmk_Ex3"></a> <span data-ttu-id="d9339-165">Exemple 3 : Filtrage au niveau du cas sur plusieurs attributs de tables imbriquées</span><span class="sxs-lookup"><span data-stu-id="d9339-165">Example 3: Case-Level Filtering on Multiple Nested Table Attributes</span></span>  
 <span data-ttu-id="d9339-166">Cet exemple montre un filtre en trois parties : une condition s'applique à la table de cas, une autre condition à un attribut dans la table imbriquée, et une autre condition sur une valeur spécifique dans l'une des colonnes de table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="d9339-166">This example shows a three-part filter: a condition applies to the case table, another condition to an attribute in the nested table, and another condition on a specific value in one of the nested table columns.</span></span>  
  
 <span data-ttu-id="d9339-167">La première condition du filtre, `Age > 30`, s'applique à une colonne dans la table de cas.</span><span class="sxs-lookup"><span data-stu-id="d9339-167">The first condition in the filter, `Age > 30`, applies to a column in the case table.</span></span> <span data-ttu-id="d9339-168">Les conditions restantes s'appliquent à la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="d9339-168">The remaining conditions apply to the nested table.</span></span>  
  
 <span data-ttu-id="d9339-169">La deuxième condition, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, vérifie la présence d’au moins un achat dans la table imbriquée incluant du lait.</span><span class="sxs-lookup"><span data-stu-id="d9339-169">The second condition, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, checks for the presence of at least one purchase in the nested table that included milk.</span></span> <span data-ttu-id="d9339-170">La troisième condition, `Quantity>=2`, signifie que le client doit avoir acheté au moins deux unités de lait dans une transaction unique.</span><span class="sxs-lookup"><span data-stu-id="d9339-170">The third condition, `Quantity>=2`, means that the customer must have purchased at least two units of milk in a single transaction.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_3  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
)  
)  
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk'  AND Quantity >= 2)   
)  
```  
  

  
###  <a name="example-4-case-level-filtering-on-absence-of-nested-table-attributes"></a><a name="bkmk_Ex4"></a> <span data-ttu-id="d9339-171">Exemple 4 : Filtrage au niveau du cas en l'absence d'attributs de tables imbriquées</span><span class="sxs-lookup"><span data-stu-id="d9339-171">Example 4: Case-Level Filtering On Absence of Nested Table Attributes</span></span>  
 <span data-ttu-id="d9339-172">Cet exemple indique comment limiter les cas aux clients qui n'ont pas acheté d'élément spécifique, en filtrant sur l'absence d'un attribut dans la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="d9339-172">This example shows how to limit cases to customer who did not purchase a specific item, by filtering on the absence of an attribute in the nested table.</span></span> <span data-ttu-id="d9339-173">Dans cet exemple, l'apprentissage du modèle s'effectue à l'aide de clients dont l'âge est supérieur à 30 et qui n'ont jamais acheté de lait.</span><span class="sxs-lookup"><span data-stu-id="d9339-173">In this example, the model is trained using customers over the age of 30 who have never bought milk.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_4  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName  
)  
)  
FILTER (Age > 30 AND NOT EXISTS (SELECT * FROM Products WHERE ProductName='Milk') )  
```  
  

  
###  <a name="example-5-filtering-on-multiple-nested-table-values"></a><a name="bkmk_Ex5"></a> <span data-ttu-id="d9339-174">Exemple 5 : Filtrage sur plusieurs valeurs de tables imbriquées</span><span class="sxs-lookup"><span data-stu-id="d9339-174">Example 5: Filtering on Multiple Nested Table Values</span></span>  
 <span data-ttu-id="d9339-175">Le but de l'exemple est d'illustrer le filtrage de table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="d9339-175">The purpose of the example is to show nested table filtering.</span></span> <span data-ttu-id="d9339-176">Le filtre de table imbriquée est appliqué après le filtre de cas et il restreint uniquement des lignes de table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="d9339-176">The nested table filter is applied after the case filter, and only restricts nested table rows.</span></span>  
  
 <span data-ttu-id="d9339-177">Ce modèle pourrait contenir plusieurs cas avec des tables imbriquées vides car EXISTS n'est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="d9339-177">This model could contain multiple cases with empty nested tables because EXISTS is not specified.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_5  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
WITH DRILLTHROUGH  
```  
  

  
###  <a name="example-6-filtering-on-nested-table-attributes-and-exists"></a><a name="bkmk_Ex6"></a> <span data-ttu-id="d9339-178">Exemple 6 : Filtrage sur des attributs de tables imbriquées et EXISTS</span><span class="sxs-lookup"><span data-stu-id="d9339-178">Example 6: Filtering on Nested Table Attributes and EXISTS</span></span>  
 <span data-ttu-id="d9339-179">Dans cet exemple, le filtre sur la table imbriquée restreint les lignes à celles qui contiennent du lait ou de l'eau en bouteille.</span><span class="sxs-lookup"><span data-stu-id="d9339-179">In this example, the filter on the nested table restricts the rows to those that contain either milk or bottled water.</span></span> <span data-ttu-id="d9339-180">Ensuite, les cas dans le modèle sont restreints à l'aide d'une instruction `EXISTS`.</span><span class="sxs-lookup"><span data-stu-id="d9339-180">Then, the cases in the model are restricted by using an `EXISTS` statement.</span></span> <span data-ttu-id="d9339-181">Cela permet de s'assurer que la table imbriquée n'est pas vide.</span><span class="sxs-lookup"><span data-stu-id="d9339-181">This makes sure that the nested table is not empty.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_6  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
FILTER (EXISTS (Products))  
```  
  

  
###  <a name="example-7-complex-filter-combinations"></a><a name="bkmk_Ex7"></a> <span data-ttu-id="d9339-182">Exemple 7 : Combinaisons de filtres complexes</span><span class="sxs-lookup"><span data-stu-id="d9339-182">Example 7: Complex Filter Combinations</span></span>  
 <span data-ttu-id="d9339-183">Le scénario de ce modèle ressemble à celui de l'Exemple 4, mais il est beaucoup plus complexe.</span><span class="sxs-lookup"><span data-stu-id="d9339-183">The scenario for this model resembles that of Example 4, but is far more complex.</span></span> <span data-ttu-id="d9339-184">La table imbriquée, **ProductsOnSale**, a la condition de filtre, ce `(OnSale)` qui signifie que la valeur de **onsale** doit être `true` pour le produit listé dans **ProductName**.</span><span class="sxs-lookup"><span data-stu-id="d9339-184">The nested table, **ProductsOnSale**, has the filter condition `(OnSale)` meaning that the value of **OnSale** must be `true` for the product listed in **ProductName**.</span></span> <span data-ttu-id="d9339-185">Ici, **OnSale** est une colonne de structure.</span><span class="sxs-lookup"><span data-stu-id="d9339-185">Here, **OnSale** is a structure column.</span></span>  
  
 <span data-ttu-id="d9339-186">La deuxième partie du filtre, pour **ProductsNotOnSale**, répète cette syntaxe, mais filtre les produits pour lesquels la valeur de **onsale** est `not true``(!OnSale)` .</span><span class="sxs-lookup"><span data-stu-id="d9339-186">The second part of the filter, for **ProductsNotOnSale**, repeats this syntax, but filters on products for which the value of **OnSale** is `not true``(!OnSale)`.</span></span>  
  
 <span data-ttu-id="d9339-187">Pour finir, les conditions sont combinées et une restriction supplémentaire est ajoutée à la table de cas.</span><span class="sxs-lookup"><span data-stu-id="d9339-187">Finally, the conditions are combined and one additional restriction is added to the case table.</span></span> <span data-ttu-id="d9339-188">Le résultat est la prédiction des achats de produits dans la liste **ProductsNotOnSale** , en fonction des cas inclus dans la liste **ProductsOnSale** , pour tous les clients dont l'âge est supérieur à 25.</span><span class="sxs-lookup"><span data-stu-id="d9339-188">The result is to predict purchases of products in the **ProductsNotOnSale** list, based on the cases that are included in the **ProductsOnSale** list, for all customers over the age of 25.</span></span>  
  
 `ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_7`  
  
 `(`  
  
 `CustomerId,`  
  
 `Age,`  
  
 `Occupation,`  
  
 `MaritalStatus,`  
  
 `ProductsOnSale`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(OnSale),`  
  
 `ProductsNotOnSale PREDICT ONLY`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(!OnSale)`  
  
 `)`  
  
 `WITH DRILLTHROUGH,`  
  
 `FILTER (EXISTS (ProductsOnSale) AND EXISTS(ProductsNotOnSale) AND Age > 25)`  
  
  
  
###  <a name="example-8-filtering-on-dates"></a><a name="bkmk_Ex8"></a> <span data-ttu-id="d9339-189">Exemple 8 : Filtrage sur les dates</span><span class="sxs-lookup"><span data-stu-id="d9339-189">Example 8: Filtering on Dates</span></span>  
 <span data-ttu-id="d9339-190">Vous pouvez filtrer des colonnes d'entrée sur les dates, comme vous le feriez avec d'autres données.</span><span class="sxs-lookup"><span data-stu-id="d9339-190">You can filter input columns on dates, as you would any other data.</span></span> <span data-ttu-id="d9339-191">Les dates contenues dans une colonne de type date/heure sont des valeurs continues. Vous pouvez par conséquent spécifier une plage de dates en utilisant des opérateurs tels que supérieur à (>) ou inférieur à (<).</span><span class="sxs-lookup"><span data-stu-id="d9339-191">Dates contained in a column of type date/time are continuous values; therefore, you can specify a date range by using operators such as greater than (>) or less than (<).</span></span> <span data-ttu-id="d9339-192">Si votre source de données ne représente pas les dates par un type de données Continuous, mais comme des valeurs texte ou discrètes, vous ne pouvez pas filtrer sur une plage de dates ; vous devez spécifier des valeurs discrètes individuelles.</span><span class="sxs-lookup"><span data-stu-id="d9339-192">If your data source does not represent dates by a Continuous data type, but as discrete or text values, you cannot filter on a date range, but must specify individual discrete values.</span></span>  
  
 <span data-ttu-id="d9339-193">Toutefois, vous ne pouvez pas créer de filtre sur la colonne de date d'un modèle de série chronologique si cette colonne est aussi la colonne clé du modèle.</span><span class="sxs-lookup"><span data-stu-id="d9339-193">However, you cannot create a filter on the date column in a time series model if the date column used for the filter is also the key column for the model.</span></span> <span data-ttu-id="d9339-194">En effet, dans les modèles de série chronologique et les modèles Sequence Clustering, la colonne de date peut être gérée en tant que type `KeyTime` ou `KeySequence`.</span><span class="sxs-lookup"><span data-stu-id="d9339-194">That is because, in time series models and sequence clustering models, the date column might be handled as type `KeyTime` or `KeySequence`.</span></span>  
  
 <span data-ttu-id="d9339-195">Si vous devez filtrer sur des dates continues dans un modèle de série chronologique, vous pouvez créer une copie de la colonne dans la structure d'exploration de données et filtrer le modèle sur la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="d9339-195">If you need to filter on continuous dates in a time series model, you can create a copy of the column in the mining structure, and filter the model on the new column.</span></span>  
  
 <span data-ttu-id="d9339-196">Par exemple, l'expression suivante représente un filtre sur une colonne de date de type `Continuous` qui a été ajoutée au modèle de prévision.</span><span class="sxs-lookup"><span data-stu-id="d9339-196">For example, the following expression represents a filter on a date column of type `Continuous` that has been added to the Forecasting model.</span></span>  
  
 `=[DateCopy] > '12:31:2003:00:00:00'`  
  
> [!NOTE]  
>  <span data-ttu-id="d9339-197">Notez que toutes les colonnes que vous ajoutez au modèle peuvent affecter les résultats.</span><span class="sxs-lookup"><span data-stu-id="d9339-197">Note that any extra columns that you add to the model might affect the results.</span></span> <span data-ttu-id="d9339-198">Par conséquent, si vous ne souhaitez pas que la colonne soit utilisée dans le calcul de la série, vous devez ajouter la colonne uniquement à la structure d'exploration de données et non au modèle.</span><span class="sxs-lookup"><span data-stu-id="d9339-198">Therefore, if you do not want the column to be used in computation of the series, you should add the column only to the mining structure, and not to the model.</span></span> <span data-ttu-id="d9339-199">Vous pouvez également définir `PredictOnly` ou `Ignore` pour l'indicateur de modèle de la colonne.</span><span class="sxs-lookup"><span data-stu-id="d9339-199">You can also set the model flag on the column to `PredictOnly` or to `Ignore`.</span></span> <span data-ttu-id="d9339-200">Pour plus d’informations, consultez [Indicateurs de modélisation &#40;Exploration de données&#41;](modeling-flags-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="d9339-200">For more information, see [Modeling Flags &#40;Data Mining&#41;](modeling-flags-data-mining.md).</span></span>  
  
 <span data-ttu-id="d9339-201">Pour les autres types de modèles, vous pouvez comme dans toute autre colonne utiliser des dates en tant que critères d'entrée ou de filtre.</span><span class="sxs-lookup"><span data-stu-id="d9339-201">For other model types, you can use dates as input criteria or filter criteria just like you would in any other column.</span></span> <span data-ttu-id="d9339-202">Toutefois, si vous devez utiliser un niveau spécifique de granularité, non pris en charge par un type de données `Continuous`, vous pouvez créer une valeur dérivée dans la source de données en utilisant des expressions afin d'extraire l'unité à utiliser pour le filtrage et l'analyse.</span><span class="sxs-lookup"><span data-stu-id="d9339-202">However, if you need to use a specific level of granularity that is not supported by a `Continuous` data type, you can create a derived value in the data source by using expressions to extract the unit to use in filtering and analysis.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d9339-203">Lorsque vous spécifiez des dates comme critères de filtre, vous devez utiliser le format suivant, indépendamment du format de date du système d'exploitation actuel : `mm/dd/yyyy`.</span><span class="sxs-lookup"><span data-stu-id="d9339-203">When you specify a dates as filter criteria, you must use the following format, regardless of the date format for the current OS: `mm/dd/yyyy`.</span></span> <span data-ttu-id="d9339-204">Tout autre format provoque une erreur.</span><span class="sxs-lookup"><span data-stu-id="d9339-204">Any other format results in an error.</span></span>  
  
 <span data-ttu-id="d9339-205">Par exemple, si vous souhaitez filtrer les résultats de votre centre d'appels de façon à n'afficher que les week-ends, vous pouvez, dans la vue de source de données, créer une expression qui extrait le nom du jour de la semaine correspondant à chaque date, puis utiliser ce nom comme valeur d'entrée ou comme valeur discrète pour le filtrage.</span><span class="sxs-lookup"><span data-stu-id="d9339-205">For example, if you want to filter your call center results to show only weekends, you can create an expression in the data source view that extracts the weekday name for each date, and then use that weekday name value for input or as a discrete value in filtering.</span></span> <span data-ttu-id="d9339-206">Rappelez-vous simplement que des valeurs répétées peuvent affecter le modèle, de sorte qu'il est préférable de n'utiliser que l'une des colonnes, et non la colonne de date plus la valeur dérivée.</span><span class="sxs-lookup"><span data-stu-id="d9339-206">Just remember that repeating values can affect the model, so you should use only one of the columns, not the date column plus the derived value.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="d9339-207">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9339-207">See Also</span></span>  
 <span data-ttu-id="d9339-208">[Filtres pour les modèles d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d9339-208">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="d9339-209">Test et validation &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d9339-209">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
  
