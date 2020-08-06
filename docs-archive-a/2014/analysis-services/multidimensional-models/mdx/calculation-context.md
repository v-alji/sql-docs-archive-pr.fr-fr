---
title: Contexte de calcul | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aec8aa98-b77d-4f8f-9684-2618b1d8e970
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6d14df51c6ec37fb96520af7acf207227ae4ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702006"
---
# <a name="calculation-context"></a><span data-ttu-id="2472b-102">Contexte de calcul</span><span class="sxs-lookup"><span data-stu-id="2472b-102">Calculation Context</span></span>
  <span data-ttu-id="2472b-103">Le contexte de calcul est le sous-espace connu du cube où une expression est évaluée et où toutes les coordonnées sont explicitement connues ou peuvent être dérivées de l'expression.</span><span class="sxs-lookup"><span data-stu-id="2472b-103">The calculation context is the known subspace of the cube where an expression is evaluated and all coordinates are either explicitly known or can be derived from the expression.</span></span>  
  
## <a name="determining-the-calculation-context"></a><span data-ttu-id="2472b-104">Détermination du contexte de calcul</span><span class="sxs-lookup"><span data-stu-id="2472b-104">Determining the calculation context</span></span>  
 <span data-ttu-id="2472b-105">Chaque jeu, membre, tuple ou fonction numérique s'exécute dans le contexte de l'instruction ou de l'expression MDX à part entière.</span><span class="sxs-lookup"><span data-stu-id="2472b-105">Every set, member, tuple, or numeric function executes in the context of the entire MDX expression or statement.</span></span> <span data-ttu-id="2472b-106">Lorsqu'un argument (par exemple, un tuple) est transmis à une fonction, seules certaines coordonnées dans l'espace du cube sont fournies de manière explicite.</span><span class="sxs-lookup"><span data-stu-id="2472b-106">When an argument, such as a tuple, is passed to a function, only some of the coordinates in the cube space are explicitly provided.</span></span> <span data-ttu-id="2472b-107">Les autres coordonnées sont obtenues sur la base du contexte de calcul actuel.</span><span class="sxs-lookup"><span data-stu-id="2472b-107">The other coordinates are obtained based on the current calculation context.</span></span>  
  
 <span data-ttu-id="2472b-108">Le contexte de calcul des coordonnées des cellules et des membres d'attribut non spécifiés est déterminé dans l'ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="2472b-108">The calculation context for unspecified cell coordinates and attribute members is determined in the following order:</span></span>  
  
1.  <span data-ttu-id="2472b-109">Clause FROM (le cas échéant) : cette clause peut spécifier soit un cube tout entier, soit un sous-cube présenté sous la forme d'une instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="2472b-109">The FROM clause (if applicable) - this clause can either specify an entire cube or can specify a subcube in the form of a SELECT statement.</span></span>  
  
2.  <span data-ttu-id="2472b-110">Clause WHERE (le cas échéant) : clause également appelée *axe de segment*et dans laquelle vous spécifiez un jeu, un tuple ou un membre qui restreint les membres retournés par une requête dans les axes des colonnes et des lignes.</span><span class="sxs-lookup"><span data-stu-id="2472b-110">The WHERE clause (if applicable) - this clause, which is also known as the *slicer axis*, on which you specify a set, tuple, or member that restricts the members returned on the column and row axis by a query.</span></span> <span data-ttu-id="2472b-111">D'un point de vue conceptuel, le membre par défaut de chaque hiérarchie d'attribut qui n'est pas explicitement défini dans l'axe des colonnes ou l'axe des lignes appartient à l'axe de segment.</span><span class="sxs-lookup"><span data-stu-id="2472b-111">Conceptually, the default member of every attribute hierarchy that is not explicitly specified on column or row axis is part of the slicer axis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2472b-112">Lorsque vous spécifiez les coordonnées des cellules d'un attribut en particulier à la fois sur l'axe de segment et sur un autre axe, les coordonnées spécifiées dans la fonction peuvent être prioritaires dans le choix des membres du jeu sur l'axe.</span><span class="sxs-lookup"><span data-stu-id="2472b-112">When cell coordinates for a particular attribute are specified on both the slicer axis and on another axis, the coordinates specified in the function may take precedence in determining the members of the set on the axis.</span></span> <span data-ttu-id="2472b-113">Les fonctions [Filter (MDX)](/sql/mdx/filter-mdx) et [Order (MDX)](/sql/mdx/order-mdx) sont des exemples de ce type de fonction ; vous pouvez filtrer ou classer un résultat par membres d’attribut exclus du contexte de calcul par la clause WHERE ou par une instruction SELECT dans la clause FROM.</span><span class="sxs-lookup"><span data-stu-id="2472b-113">The [Filter (MDX)](/sql/mdx/filter-mdx) and [Order (MDX)](/sql/mdx/order-mdx) functions are examples of such functions - you can filter or order a result by attribute members that are excluded from the calculation context by the WHERE clause, or by a SELECT statement in the FROM clause.</span></span>  
  
3.  <span data-ttu-id="2472b-114">Jeux nommés et membres calculés définis dans la requête ou l'expression.</span><span class="sxs-lookup"><span data-stu-id="2472b-114">The named sets and calculated members defined in the query or expression.</span></span>  
  
4.  <span data-ttu-id="2472b-115">Tuples et jeux spécifiés sur les axes des lignes et des colonnes à l'aide du membre par défaut des attributs qui n'apparaissent pas sur les axes des lignes ou des colonnes ou sur l'axe de segment.</span><span class="sxs-lookup"><span data-stu-id="2472b-115">The tuples and sets specified on the row and column axes, utilizing the default member for attributes that do not appear on the row, column, or slicer axis.</span></span>  
  
5.  <span data-ttu-id="2472b-116">Cellules du cube ou du sous-cube sur chaque axe avec suppression des tuples vides sur l'axe et application de la clause HAVING.</span><span class="sxs-lookup"><span data-stu-id="2472b-116">The cube or subcube cells on each axis, eliminating empty tuples on the axis and applying the HAVING clause.</span></span>  
  
6.  <span data-ttu-id="2472b-117">Pour plus d’informations, consultez [Définition d’un contexte de cube dans une requête &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="2472b-117">For more information, see [Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span></span>  
  
 <span data-ttu-id="2472b-118">Dans la requête qui suit, le contexte de calcul de l'axe des lignes est limité par les membres d'attribut Country et Calendar Year spécifiés dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="2472b-118">In the following query, the calculation context for the row axis is restricted by the Country attribute member and the Calendar Year attribute member that are specified in the WHERE clause.</span></span>  
  
```  
SELECT Customer.City.City.Members ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France, [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="2472b-119">Cependant, si vous modifiez cette requête en précisant la fonction `FILTER` sur l'axe des lignes, puis utilisez un membre de la hiérarchie d'attribut Calendar Year dans la fonction `FILTER`, vous pouvez alors modifier le membre d'attribut de la hiérarchie d'attribut Calendar Year employé pour fournir le contexte de calcul des membres du jeu sur l'axe des colonnes.</span><span class="sxs-lookup"><span data-stu-id="2472b-119">However, if you modify this query by specifying the `FILTER` function on the row axis, and utilize a Calendar Year attribute hierarchy member in the `FILTER` function, then the attribute member from the Calendar Year attribute hierarchy that is used to provide the calculation context for the members of the set on the column axis can be modified.</span></span>  
  
```  
SELECT FILTER  
   (  
      Customer.City.City.Members,   
         ([Date].[Calendar].[Calendar Year].[CY 2003],  
            Measures.[Internet Order Quantity]) > 75   
   ) ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France,  
   [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="2472b-120">Dans la requête ci-dessus, le contexte de calcul des cellules dans les tuples qui apparaissent sur l'axe des colonnes est filtré par le membre CY 2003 de la hiérarchie d'attribut Calendar Year, même si le contexte de calcul nominal de la hiérarchie d'attribut Calendar Year est CY 2004.</span><span class="sxs-lookup"><span data-stu-id="2472b-120">In the previous query, the calculation context for the cells in the tuples that appear on the column axis is filtered by the CY 2003 member of the Calendar Year attribute hierarchy, even though the nominal calculation context for the Calendar Year attribute hierarchy is CY 2004.</span></span> <span data-ttu-id="2472b-121">De plus, il est filtré par la mesure Internet Order Quantity.</span><span class="sxs-lookup"><span data-stu-id="2472b-121">Furthermore, it is filtered by the Internet Order Quantity measure.</span></span> <span data-ttu-id="2472b-122">Néanmoins, une fois les membres du jeu définis sur l'axe des colonnes, le contexte de calcul des valeurs des membres qui apparaissent sur l'axe est de nouveau déterminé par la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="2472b-122">However, once the members of the set on the column axis is set, the calculation context for the values for the members that appear on the axis is again determined by the WHERE clause.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2472b-123">Pour accroître les performances de la requête, pensez à éliminer les membres et les tuples le plus tôt possible au cours du processus de résolution.</span><span class="sxs-lookup"><span data-stu-id="2472b-123">To increase query performance, you should eliminate members and tuples as early in the resolution process as possible.</span></span> <span data-ttu-id="2472b-124">De cette manière, les calculs de temps des requêtes complexes dans le jeu de membres final peuvent cibler le plus petit nombre de cellules possible.</span><span class="sxs-lookup"><span data-stu-id="2472b-124">In this manner, complex query time calculations on the final set of members operate on the fewest cells possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2472b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2472b-125">See Also</span></span>  
 <span data-ttu-id="2472b-126">[Établissement d’un contexte de cube dans une requête &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="2472b-126">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 <span data-ttu-id="2472b-127">[Notions de base des requêtes MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="2472b-127">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="2472b-128">Concepts clés de MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2472b-128">Key Concepts in MDX &#40;Analysis Services&#41;</span></span>](../key-concepts-in-mdx-analysis-services.md)  
  
  
