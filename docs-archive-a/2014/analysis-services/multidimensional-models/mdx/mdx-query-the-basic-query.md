---
title: Requête MDX de base (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], SELECT statement
- queries [MDX], about queries
- cellsets [MDX]
- SELECT statement [MDX]
- cubes [Analysis Services], SELECT statement
ms.assetid: 4fa5a95a-fec9-4584-875c-dbf030c53e82
author: minewiskan
ms.author: owend
ms.openlocfilehash: b6b1a70753abe8e477bd1e522a37f4513cc12a52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612568"
---
# <a name="the-basic-mdx-query-mdx"></a><span data-ttu-id="10549-102">Requête MDX de base (MDX)</span><span class="sxs-lookup"><span data-stu-id="10549-102">The Basic MDX Query (MDX)</span></span>
  <span data-ttu-id="10549-103">La requête MDX (Multidimensional Expressions) de base est l’instruction SELECT, la requête la plus fréquemment utilisée dans MDX.</span><span class="sxs-lookup"><span data-stu-id="10549-103">The basic Multidimensional Expressions (MDX) query is the SELECT statement-the most frequently used query in MDX.</span></span> <span data-ttu-id="10549-104">Si vous connaissez la méthode selon laquelle une instruction SELECT MDX doit spécifier un jeu de résultats, la syntaxe de l'instruction SELECT et la manière de créer une requête simple à l'aide de cette instruction, vous disposez alors de connaissances suffisamment solides pour comprendre comment utiliser MDX pour interroger des données multidimensionnelles.</span><span class="sxs-lookup"><span data-stu-id="10549-104">By understanding how an MDX SELECT statement must specify a result set, what the syntax of the SELECT statement is, and how to create a simple query using the SELECT statement, you will have a solid understanding of how to use MDX to query multidimensional data.</span></span>  
  
## <a name="specifying-a-result-set"></a><span data-ttu-id="10549-105">Spécification d'un jeu de résultats</span><span class="sxs-lookup"><span data-stu-id="10549-105">Specifying a Result Set</span></span>  
 <span data-ttu-id="10549-106">Dans MDX, l'instruction SELECT permet de spécifier un jeu de résultats doté d'un sous-ensemble de données multidimensionnelles qui ont été retournées à partir d'un cube.</span><span class="sxs-lookup"><span data-stu-id="10549-106">In MDX, the SELECT statement specifies a result set that contains a subset of multidimensional data that has been returned from a cube.</span></span> <span data-ttu-id="10549-107">Pour spécifier un jeu de résultats, une requête MDX doit renfermer les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="10549-107">To specify a result set, an MDX query must contain the following information:</span></span>  
  
-   <span data-ttu-id="10549-108">Le nombre d'axes que le jeu de résultats doit contenir.</span><span class="sxs-lookup"><span data-stu-id="10549-108">The number of axes that you want the result set to contain.</span></span> <span data-ttu-id="10549-109">Vous pouvez spécifier jusqu'à 128 axes dans une requête MDX.</span><span class="sxs-lookup"><span data-stu-id="10549-109">You can specify up to 128 axes in an MDX query.</span></span>  
  
-   <span data-ttu-id="10549-110">Le jeu de membres ou de tuples à inclure sur chaque axe de la requête MDX.</span><span class="sxs-lookup"><span data-stu-id="10549-110">The set of members or tuples to include on each axis of the MDX query.</span></span>  
  
-   <span data-ttu-id="10549-111">Le nom du cube qui définit le contexte de la requête MDX.</span><span class="sxs-lookup"><span data-stu-id="10549-111">The name of the cube that sets the context of the MDX query.</span></span>  
  
-   <span data-ttu-id="10549-112">Le jeu de membres ou de tuples à inclure sur chaque axe de secteur.</span><span class="sxs-lookup"><span data-stu-id="10549-112">The set of members or tuples to include on the slicer axis.</span></span> <span data-ttu-id="10549-113">Pour plus d’informations sur les axes de secteur et de requête, consultez [Restriction de la requête avec des axes de requête et de secteur &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span><span class="sxs-lookup"><span data-stu-id="10549-113">For more information about slicer and query axes, see[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span></span>  
  
 <span data-ttu-id="10549-114">Pour identifier les axes de requête, le cube qui sera interrogé et l'axe de secteur, l'instruction MDX SELECT utilise les clauses suivantes :</span><span class="sxs-lookup"><span data-stu-id="10549-114">To identify the query axes, the cube that will be queried, and the slicer axis, the MDX SELECT statement uses the following clauses:</span></span>  
  
-   <span data-ttu-id="10549-115">Une clause SELECT qui détermine les axes de requête d'une instruction SELECT MDX.</span><span class="sxs-lookup"><span data-stu-id="10549-115">A SELECT clause that determines the query axes of an MDX SELECT statement.</span></span> <span data-ttu-id="10549-116">Pour plus d’informations sur la construction d’axes de requête dans une clause SELECT, consultez [Spécification du contenu d’un axe de requête &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="10549-116">For more information about the construction of query axes in a SELECT clause, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="10549-117">Une clause FROM qui détermine quel cube sera interrogé.</span><span class="sxs-lookup"><span data-stu-id="10549-117">A FROM clause that determines which cube will be queried.</span></span> <span data-ttu-id="10549-118">Pour plus d’informations sur la clause FROM, consultez [Instruction SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="10549-118">For more information about the FROM clause, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
-   <span data-ttu-id="10549-119">Une clause WHERE facultative qui détermine quels membres ou tuples utiliser sur l'axe de secteur pour limiter les données retournées.</span><span class="sxs-lookup"><span data-stu-id="10549-119">An optional WHERE clause that determines which members or tuples to use on the slicer axis to restrict the data returned.</span></span> <span data-ttu-id="10549-120">Pour plus d’informations sur la construction d’un axe de secteur dans une clause WHERE, consultez [Spécification du contenu d’un axe de secteur &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="10549-120">For more information about the construction of a slicer axis in a WHERE clause, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10549-121">Pour plus d’informations détaillées sur les diverses clauses de l’instruction SELECT, consultez [Instruction SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="10549-121">For more detailed information about the various clauses of the SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="select-statement-syntax"></a><span data-ttu-id="10549-122">Syntaxe de l'instruction SELECT</span><span class="sxs-lookup"><span data-stu-id="10549-122">SELECT Statement Syntax</span></span>  
 <span data-ttu-id="10549-123">La syntaxe qui suit illustre une instruction SELECT de base qui inclut l'utilisation des clauses SELECT, FROM et WHERE :</span><span class="sxs-lookup"><span data-stu-id="10549-123">The following syntax shows a basic SELECT statement that includes the use of the SELECT, FROM, and WHERE clauses:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause>   
    [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
```  
  
 <span data-ttu-id="10549-124">L'instruction MDX SELECT prend en charge des éléments de syntaxe facultatifs, tels que le mot clé WITH, l'utilisation de fonctions MDX pour créer des membres calculés pour une inclusion dans un axe ou un axe de secteur, et la possibilité de retourner la valeur de propriétés de cellules spécifiques dans le cadre de la requête.</span><span class="sxs-lookup"><span data-stu-id="10549-124">The MDX SELECT statement supports optional syntax, such as the WITH keyword, the use of MDX functions to create calculated members for inclusion in an axis or slicer axis, and the ability to return the values of specific cell properties as part of the query.</span></span> <span data-ttu-id="10549-125">Pour plus d’informations sur l’instruction SELECT MDX, consultez [Instruction SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="10549-125">For more information about the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
### <a name="comparing-the-syntax-of-the-mdx-select-statement-to-sql"></a><span data-ttu-id="10549-126">Comparaison de la syntaxe de l'instruction SELECT MDX par rapport à SQL</span><span class="sxs-lookup"><span data-stu-id="10549-126">Comparing the Syntax of the MDX SELECT Statement to SQL</span></span>  
 <span data-ttu-id="10549-127">Le format de syntaxe de l'instruction SELECT MDX est semblable à celui de la syntaxe SQL.</span><span class="sxs-lookup"><span data-stu-id="10549-127">The syntax format for the MDX SELECT statement is similar to that of SQL syntax.</span></span> <span data-ttu-id="10549-128">Il existe toutefois quelques différences fondamentales :</span><span class="sxs-lookup"><span data-stu-id="10549-128">However, there are several fundamental differences:</span></span>  
  
-   <span data-ttu-id="10549-129">La syntaxe MDX distingue les jeux en plaçant les tuples ou les membres à l’aide d’accolades (caractères {et}). Pour plus d’informations sur les membres, les tuples et la syntaxe de définition, consultez [utilisation de membres, de tuples et de jeux &#40;&#41;MDX ](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="10549-129">MDX syntax distinguishes sets by surrounding tuples or members with braces (the { and } characters.) For more information about member, tuple, and set syntax, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
-   <span data-ttu-id="10549-130">Les requêtes MDX peuvent avoir de 0 à 128 axes de requête dans l'instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="10549-130">MDX queries can have 0, 1, 2 or up to 128 query axes in the SELECT statement.</span></span> <span data-ttu-id="10549-131">Tous les axes se comportent exactement de la même manière, contrairement à SQL où il y a des différences significatives entre la façon dont les lignes et les colonnes d'une requête se comportent.</span><span class="sxs-lookup"><span data-stu-id="10549-131">Each axis behaves in exactly the same way, unlike SQL where there are significant differences between how the rows and the columns of a query behave.</span></span>  
  
-   <span data-ttu-id="10549-132">À l'instar d'une requête SQL, la clause FROM nomme la source des données pour la requête MDX.</span><span class="sxs-lookup"><span data-stu-id="10549-132">As with an SQL query, the FROM clause names the source of the data for the MDX query.</span></span> <span data-ttu-id="10549-133">Toutefois, la clause FROM MDX est limitée à un seul cube.</span><span class="sxs-lookup"><span data-stu-id="10549-133">However, the MDX FROM clause is restricted to a single cube.</span></span> <span data-ttu-id="10549-134">Des informations issues d'autres cubes peuvent être extraites, valeur par valeur, à l'aide de la fonction LookupCube.</span><span class="sxs-lookup"><span data-stu-id="10549-134">Information from other cubes can be retrieved on a value-by-value basis by using the LookupCube function.</span></span>  
  
-   <span data-ttu-id="10549-135">La clause WHERE décrit l'axe de secteur dans une requête MDX.</span><span class="sxs-lookup"><span data-stu-id="10549-135">The WHERE clause describes the slicer axis in an MDX query.</span></span> <span data-ttu-id="10549-136">Elle agit comme un axe supplémentaire invisible dans la requête, découpant les valeurs qui s'affichent dans les cellules du jeu de résultats ; contrairement à la clause SQL WHERE, elle n'affecte pas directement ce qui s'affiche sur l'axe des lignes de la requête.</span><span class="sxs-lookup"><span data-stu-id="10549-136">It acts as something like an invisible, extra axis in the query, slicing the values that appear in the cells in the result set; unlike the SQL WHERE clause it does not directly affect what appears on the rows axis of the query.</span></span> <span data-ttu-id="10549-137">Les fonctionnalités de la clause SQL WHERE sont disponibles via d'autres fonctions MDX telles que la fonction FILTER.</span><span class="sxs-lookup"><span data-stu-id="10549-137">The functionality of the SQL WHERE clause is available through other MDX functions such as the FILTER function.</span></span>  
  
## <a name="select-statement-example"></a><span data-ttu-id="10549-138">Exemple d'instruction SELECT</span><span class="sxs-lookup"><span data-stu-id="10549-138">SELECT Statement Example</span></span>  
 <span data-ttu-id="10549-139">L'exemple qui suit illustre une requête MDX de base qui utilise l'instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="10549-139">The following example shows a basic MDX query that uses the SELECT statement.</span></span> <span data-ttu-id="10549-140">Cette requête retourne un jeu de résultats contenant le montant des ventes et des taxes 2002 et 2003 pour les secteurs du sud-ouest.</span><span class="sxs-lookup"><span data-stu-id="10549-140">This query returns a result set that contains the 2002 and 2003 sales and tax amounts for the Southwest sales territories.</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON COLUMNS,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON ROWS  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="10549-141">Dans cet exemple, la requête définit les informations de jeu de résultats suivantes :</span><span class="sxs-lookup"><span data-stu-id="10549-141">In this example, the query defines the following result set information:</span></span>  
  
-   <span data-ttu-id="10549-142">La clause SELECT définit les axes de requête comme les membres Sales Amount et Tax Amount de la dimension Measures, et les membres 2002 et 2003 de la dimension Date.</span><span class="sxs-lookup"><span data-stu-id="10549-142">The SELECT clause sets the query axes as the Sales Amount and Tax Amount members of the Measures dimension, and the 2002 and 2003 members of the Date dimension.</span></span>  
  
-   <span data-ttu-id="10549-143">La clause FROM indique que la source de données est le cube Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="10549-143">The FROM clause indicates that the data source is the Adventure Works cube.</span></span>  
  
-   <span data-ttu-id="10549-144">La clause WHERE définit l'axe de secteur comme le membre Southwest de la dimension Sales Territory.</span><span class="sxs-lookup"><span data-stu-id="10549-144">The WHERE clause defines the slicer axis as the Southwest member of the Sales Territory dimension.</span></span>  
  
 <span data-ttu-id="10549-145">Notez que cet exemple de requête utilise également les alias des axes COLUMNS et ROWS.</span><span class="sxs-lookup"><span data-stu-id="10549-145">Notice that the query example also uses the COLUMNS and ROWS axis aliases.</span></span> <span data-ttu-id="10549-146">Les positions ordinales pour ces axes auraient également pu être utilisées.</span><span class="sxs-lookup"><span data-stu-id="10549-146">The ordinal positions for these axes could also have been used.</span></span> <span data-ttu-id="10549-147">L'exemple qui suit montre comment la requête MDX pourrait également être écrite, en utilisant la position ordinale de chaque axe :</span><span class="sxs-lookup"><span data-stu-id="10549-147">The following example shows how the MDX query could have been written to use the ordinal position of each axis:</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON 0,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON 1  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="10549-148">Pour obtenir d’autres exemples détaillés, consultez [Spécification du contenu d’un axe de requête &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) et [Spécification du contenu d’un axe de secteur &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="10549-148">For more detailed examples, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)and [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10549-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10549-149">See Also</span></span>  
 <span data-ttu-id="10549-150">[Concepts clés dans MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="10549-150">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 [<span data-ttu-id="10549-151">Instruction SELECT &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="10549-151">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
