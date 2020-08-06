---
title: Création de jeux nommés d’étendue de requête (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- query-scoped named sets [MDX]
- WITH keyword
ms.assetid: 78bc1e9a-1bc4-4a5a-ab0b-cf430c8fbfe1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6eccb4e20fca03079a04a0219b07f6411b80a433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698627"
---
# <a name="creating-query-scoped-named-sets-mdx"></a><span data-ttu-id="5bf48-102">Création de jeux nommés d'étendue de requête (MDX)</span><span class="sxs-lookup"><span data-stu-id="5bf48-102">Creating Query-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="5bf48-103">Si un jeu nommé n'est nécessaire que pour une seule requête MDX (Multidimensional Expressions), vous pouvez le définir à l'aide du mot clé WITH.</span><span class="sxs-lookup"><span data-stu-id="5bf48-103">If a named set is only required for a single Multidimensional Expressions (MDX) query, you can define that named set by using the WITH keyword.</span></span> <span data-ttu-id="5bf48-104">Un jeu nommé créé à l'aide du mot clé WITH n'existe plus une fois que l'exécution de la requête est terminée.</span><span class="sxs-lookup"><span data-stu-id="5bf48-104">A named set that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="5bf48-105">Comme l'explique cette rubrique, la syntaxe de WITH est très souple, et accepte même l'utilisation de fonctions pour définir le jeu nommé.</span><span class="sxs-lookup"><span data-stu-id="5bf48-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even accommodating the use of functions to define the named set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5bf48-106">Pour plus d’informations sur les jeux nommés, consultez [Création de jeux nommés à l’aide d’expressions MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="5bf48-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="5bf48-107">Syntaxe du mot clé WITH</span><span class="sxs-lookup"><span data-stu-id="5bf48-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="5bf48-108">Utilisez la syntaxe suivante pour ajouter le mot clé WITH à l'instruction SELECT MDX :</span><span class="sxs-lookup"><span data-stu-id="5bf48-108">Use the following syntax to add the WITH keyword to a MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
  
<SELECT WITH clause> ::=  
   ( SET Set_Identifier AS 'Set_Expression')  
  
```  
  
 <span data-ttu-id="5bf48-109">Dans la syntaxe du mot clé WITH, le paramètre `Set_Identifier` contient l'alias du jeu nommé.</span><span class="sxs-lookup"><span data-stu-id="5bf48-109">In the syntax for the WITH keyword, the `Set_Identifier` parameter contains the alias for the named set.</span></span> <span data-ttu-id="5bf48-110">Le paramètre `Set_Expression` contient l'expression à laquelle l'alias du jeu nommé se réfère.</span><span class="sxs-lookup"><span data-stu-id="5bf48-110">The `Set_Expression` parameter contains the set expression to which the named set alias refers.</span></span>  
  
## <a name="with-keyword-example"></a><span data-ttu-id="5bf48-111">Exemple de mot clé WITH</span><span class="sxs-lookup"><span data-stu-id="5bf48-111">WITH Keyword Example</span></span>  
 <span data-ttu-id="5bf48-112">La requête MDX ci-après examine les ventes unitaires des différents vins Chardonnay et Chablis dans `FoodMart 2000`, l'exemple de base de données de Microsoft SQL Server 2000 Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="5bf48-112">The following MDX query examines the unit sales of the various Chardonnay and Chablis wines in `FoodMart 2000`, the sample database for Microsoft SQL Server 2000 Analysis Services.</span></span> <span data-ttu-id="5bf48-113">Cette requête, bien que relativement simple en termes d'ensemble de résultats, est longue et lourde à gérer.</span><span class="sxs-lookup"><span data-stu-id="5bf48-113">This query, although fairly simple in terms of the result set, is lengthy and unwieldy when you have to maintenance such a query.</span></span>  
  
```  
SELECT  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]} ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
 <span data-ttu-id="5bf48-114">Pour faciliter la maintenance de la requête MDX ci-dessus, vous pouvez créer un jeu nommé pour cette requête, à l'aide du mot clé WITH.</span><span class="sxs-lookup"><span data-stu-id="5bf48-114">To make the previous MDX query easier to maintain, you can create a named set for the query by using the WITH keyword.</span></span> <span data-ttu-id="5bf48-115">L'exemple de code ci-après montre comment utiliser le mot clé WITH pour créer un jeu nommé, `[ChardonnayChablis]`, et comment ce jeu nommé rend l'instruction SELECT plus courte et plus facile à gérer.</span><span class="sxs-lookup"><span data-stu-id="5bf48-115">The following code shows how to use the WITH keyword to create a named set, `[ChardonnayChablis]`, and how the named set makes the SELECT statement shorter and easier to maintain.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]}  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
### <a name="using-functions-together-with-the-with-keyword"></a><span data-ttu-id="5bf48-116">Utilisation de fonctions en association avec le mot clé WITH</span><span class="sxs-lookup"><span data-stu-id="5bf48-116">Using Functions Together with the WITH Keyword</span></span>  
 <span data-ttu-id="5bf48-117">Il vous est possible de définir explicitement chaque membre d'un jeu nommé, mais cette approche risque de produire une instruction très longue.</span><span class="sxs-lookup"><span data-stu-id="5bf48-117">Although you can explicitly define each member of a named set, this approach can produce a lengthy statement.</span></span> <span data-ttu-id="5bf48-118">Pour faciliter la création et la maintenance d'un jeu nommé, vous pouvez définir ses membres à l'aide de fonctions MDX.</span><span class="sxs-lookup"><span data-stu-id="5bf48-118">To make the creation and maintenance of a named set easier, you can use MDX functions to define the members.</span></span>  
  
 <span data-ttu-id="5bf48-119">Par exemple, l'exemple de requête MDX suivant utilise les fonctions MDX [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx)et [Name](/sql/mdx/members-string-mdx) ainsi que la fonction InStr VBA pour créer le jeu nommé `[ChardonnayChablis]` .</span><span class="sxs-lookup"><span data-stu-id="5bf48-119">For example, the following MDX query example uses the [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx), and [Name](/sql/mdx/members-string-mdx) MDX functions and the InStr VBA function to create the `[ChardonnayChablis]` named set.</span></span> <span data-ttu-id="5bf48-120">Cette version du jeu nommé `[ChardonnayChablis]` est identique à la version explicitement définie présentée plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5bf48-120">This version of the `[ChardonnayChablis]` named set is the same as the explicitly defined version shown previously in this topic.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   'Filter([Product].Members, (InStr(1, [Product].CurrentMember.Name, "chardonnay") <> 0) OR (InStr(1, [Product].CurrentMember.Name, "chablis") <> 0))'  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bf48-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5bf48-121">See Also</span></span>  
 <span data-ttu-id="5bf48-122">[Instruction SELECT &#40;&#41;MDX](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="5bf48-122">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="5bf48-123">Création de jeux nommés dans l’étendue de session &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="5bf48-123">Creating Session-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-session-scoped-named-sets.md)  
  
  
