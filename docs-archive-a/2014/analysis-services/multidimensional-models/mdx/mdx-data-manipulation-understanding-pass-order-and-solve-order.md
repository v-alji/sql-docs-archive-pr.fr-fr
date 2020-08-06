---
title: Comprendre l’ordre de passage et l’ordre de résolution (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- evaluation order [MDX]
- calculation order [MDX]
- SOLVE_ORDER property
- queries [MDX], solve orders
- solve orders [MDX]
- pass orders [MDX]
- expressions [MDX], solve orders
ms.assetid: 7ed7d4ee-4644-4c5d-99a4-c4b429d0203c
author: minewiskan
ms.author: owend
ms.openlocfilehash: d92ccd9d1eeb05272a95c6f429f8c756bcb0022e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604187"
---
# <a name="understanding-pass-order-and-solve-order-mdx"></a><span data-ttu-id="00459-102">Présentation des concepts d'ordre de passage et d'ordre de résolution (MDX)</span><span class="sxs-lookup"><span data-stu-id="00459-102">Understanding Pass Order and Solve Order (MDX)</span></span>
  <span data-ttu-id="00459-103">Lorsqu'un cube est calculé dans le cadre d'un script MDX, il peut subir de nombreuses étapes de calcul, en fonction de l'utilisation de diverses fonctionnalités liées au calcul.</span><span class="sxs-lookup"><span data-stu-id="00459-103">When a cube is calculated as the result of an MDX script, it can go through many stages of computation depending on the use of various calculation-related features.</span></span> <span data-ttu-id="00459-104">Chacune de ces étapes porte le nom de test de calcul.</span><span class="sxs-lookup"><span data-stu-id="00459-104">Each of these stages is referred to as a calculation pass.</span></span>  
  
 <span data-ttu-id="00459-105">Un test de calcul peut être désigné par sa position ordinale, appelée numéro du test de calcul.</span><span class="sxs-lookup"><span data-stu-id="00459-105">A calculation pass can be referred to by an ordinal position, called the calculation pass number.</span></span> <span data-ttu-id="00459-106">Le nombre de tests nécessaires au calcul complet de toutes les cellules d'un cube représente la profondeur du test de calcul du cube.</span><span class="sxs-lookup"><span data-stu-id="00459-106">The count of calculation passes that are required to fully compute all the cells of a cube is referred to as the calculation pass depth of the cube.</span></span>  
  
 <span data-ttu-id="00459-107">Les données de table de faits et d'écriture différée affectent uniquement le test 0.</span><span class="sxs-lookup"><span data-stu-id="00459-107">Fact table and writeback data only impact pass 0.</span></span> <span data-ttu-id="00459-108">Les scripts remplissent les données après le test 0 ; chaque instruction d'assignation et de calcul d'un script crée un test.</span><span class="sxs-lookup"><span data-stu-id="00459-108">Scripts populate data after pass 0; each assignment and calculate statement in a script creates a new pass.</span></span> <span data-ttu-id="00459-109">En dehors du script MDX, les références au test absolu 0 correspondent au dernier test créé par le script pour le cube.</span><span class="sxs-lookup"><span data-stu-id="00459-109">Outside the MDX script, references to absolute pass 0 refer to the last pass created by the script for the cube.</span></span>  
  
 <span data-ttu-id="00459-110">Des membres calculés sont créés à tous les tests, mais l'expression est appliquée au test actuel.</span><span class="sxs-lookup"><span data-stu-id="00459-110">Calculated members are created at all passes, but the expression is applied at the current pass.</span></span> <span data-ttu-id="00459-111">Les tests antérieurs contiennent la mesure calculée, mais avec une valeur Null.</span><span class="sxs-lookup"><span data-stu-id="00459-111">Prior passes contain the calculated measure, but with a null value.</span></span>  
  
## <a name="solve-order"></a><span data-ttu-id="00459-112">Ordre de résolution</span><span class="sxs-lookup"><span data-stu-id="00459-112">Solve Order</span></span>  
 <span data-ttu-id="00459-113">L'ordre de résolution détermine la priorité de calcul en cas de concurrence entre des expressions.</span><span class="sxs-lookup"><span data-stu-id="00459-113">Solve order determines the priority of calculation in the event of competing expressions.</span></span> <span data-ttu-id="00459-114">Au sein d'un même test de calcul, l'ordre de résolution détermine deux choses :</span><span class="sxs-lookup"><span data-stu-id="00459-114">Within a single pass, solve order determines two things:</span></span>  
  
-   <span data-ttu-id="00459-115">Ordre dans lequel [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] évalue les dimensions, les membres, les membres calculés, les cumuls personnalisés et les cellules calculées.</span><span class="sxs-lookup"><span data-stu-id="00459-115">The order in which [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates dimensions, members, calculated members, custom rollups, and calculated cells.</span></span>  
  
-   <span data-ttu-id="00459-116">l’ordre dans lequel [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] évalue les membres personnalisés, les membres calculés, les cumuls personnalisés et les cellules calculées.</span><span class="sxs-lookup"><span data-stu-id="00459-116">The order in which [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates custom members, calculated members, custom rollup, and calculated cells.</span></span>  
  
 <span data-ttu-id="00459-117">Le membre qui a l'ordre de résolution le plus élevé est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="00459-117">The member with the highest solve order takes precedence.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00459-118">L'exception à cette règle de priorité concerne la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="00459-118">The exception to this precedence is the Aggregate function.</span></span> <span data-ttu-id="00459-119">Les membres calculés avec la fonction d'agrégation ont un ordre de résolution inférieur à toute mesure calculée à intersection.</span><span class="sxs-lookup"><span data-stu-id="00459-119">Calculated members with the Aggregate function have a lower solve order than any intersecting calculated measure.</span></span>  
  
## <a name="solve-order-values-and-precedence"></a><span data-ttu-id="00459-120">Valeurs et priorité de l'ordre de résolution</span><span class="sxs-lookup"><span data-stu-id="00459-120">Solve Order Values and Precedence</span></span>  
 <span data-ttu-id="00459-121">Les valeurs d'ordre de résolution sont comprises entre -8 181 et 65 535.</span><span class="sxs-lookup"><span data-stu-id="00459-121">Solve order values can range from -8181 to 65535.</span></span> <span data-ttu-id="00459-122">Dans cette plage, certaines valeurs d'ordre de résolution correspondent à des types de calculs spécifiques, comme illustré dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="00459-122">In this range, some solve order values correspond to specific kinds of calculations, as shown in the following table.</span></span>  
  
|<span data-ttu-id="00459-123">Calcul</span><span class="sxs-lookup"><span data-stu-id="00459-123">Calculation</span></span>|<span data-ttu-id="00459-124">Ordre de résolution</span><span class="sxs-lookup"><span data-stu-id="00459-124">Solve Order</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="00459-125">Formules de membres personnalisées</span><span class="sxs-lookup"><span data-stu-id="00459-125">Custom member formulas</span></span>|<span data-ttu-id="00459-126">-5119</span><span class="sxs-lookup"><span data-stu-id="00459-126">-5119</span></span>|  
|<span data-ttu-id="00459-127">Opérateurs unaires</span><span class="sxs-lookup"><span data-stu-id="00459-127">Unary operators</span></span>|<span data-ttu-id="00459-128">-5119</span><span class="sxs-lookup"><span data-stu-id="00459-128">-5119</span></span>|  
|<span data-ttu-id="00459-129">Calcul des valeurs totales affichées</span><span class="sxs-lookup"><span data-stu-id="00459-129">Visual totals calculation</span></span>|<span data-ttu-id="00459-130">-4096</span><span class="sxs-lookup"><span data-stu-id="00459-130">-4096</span></span>|  
|<span data-ttu-id="00459-131">Tous les autres calculs (sauf indication contraire)</span><span class="sxs-lookup"><span data-stu-id="00459-131">All other calculations (if not otherwise specified)</span></span>|<span data-ttu-id="00459-132">0</span><span class="sxs-lookup"><span data-stu-id="00459-132">0</span></span>|  
  
 <span data-ttu-id="00459-133">Il est vivement recommandé d'utiliser uniquement des entiers positifs lors de la définition des valeurs d'ordre de résolution.</span><span class="sxs-lookup"><span data-stu-id="00459-133">It is highly recommended that you use only positive integers when setting solve order values.</span></span> <span data-ttu-id="00459-134">Si vous assignez des valeurs inférieures aux valeurs d'ordre de résolution mentionnées dans le tableau précédent, le test de calcul peut devenir imprévisible.</span><span class="sxs-lookup"><span data-stu-id="00459-134">If you assign values that are lower than the solve order values shown in the previous table, the calculation pass can become unpredictable.</span></span> <span data-ttu-id="00459-135">Par exemple, le calcul d'un membre calculé reçoit une valeur d'ordre de résolution qui est inférieure à la valeur de la formule de cumul personnalisé par défaut, à savoir -5 119.</span><span class="sxs-lookup"><span data-stu-id="00459-135">For example, the calculation for a calculated member receives a solve order value that is lower than the default custom rollup formula value of -5119.</span></span> <span data-ttu-id="00459-136">Une valeur d'ordre de résolution aussi faible entraîne le calcul des membres calculés avant le calcul des formules de cumul personnalisé, ce qui peut produire des résultats incorrects.</span><span class="sxs-lookup"><span data-stu-id="00459-136">Such a low solve order value causes the calculated members to be calculated before the custom rollup formulas, and can produce incorrect results.</span></span>  
  
### <a name="creating-and-changing-solve-order"></a><span data-ttu-id="00459-137">Création et modification de l'ordre de résolution</span><span class="sxs-lookup"><span data-stu-id="00459-137">Creating and Changing Solve Order</span></span>  
 <span data-ttu-id="00459-138">Dans le Concepteur de cube, dans le **volet Calculs**, vous pouvez modifier l’ordre de résolution des membres calculés et des cellules calculées en modifiant l’ordre des calculs.</span><span class="sxs-lookup"><span data-stu-id="00459-138">In Cube Designer, on the **Calculations Pane**, you can change the solve order for calculated members and calculated cells by changing the order of the calculations.</span></span>  
  
 <span data-ttu-id="00459-139">Dans MDX, vous pouvez utiliser le mot clé `SOLVE_ORDER` pour créer ou modifier des membres calculés et des cellules calculées.</span><span class="sxs-lookup"><span data-stu-id="00459-139">In MDX, you can use the `SOLVE_ORDER` keyword to create or change calculated members and calculated cells.</span></span>  
  
## <a name="solve-order-examples"></a><span data-ttu-id="00459-140">Exemples d'ordres de résolution</span><span class="sxs-lookup"><span data-stu-id="00459-140">Solve Order Examples</span></span>  
 <span data-ttu-id="00459-141">Afin d'illustrer la complexité potentielle de l'ordre de résolution, la série suivante de requêtes MDX commence par deux requêtes qui ne présentent individuellement aucun problème d'ordre de résolution.</span><span class="sxs-lookup"><span data-stu-id="00459-141">To illustrate the potential complexities of solve order, the following series of MDX queries starts with two queries that each individually have no solve order issues.</span></span> <span data-ttu-id="00459-142">Ces deux requêtes sont ensuite combinées dans une requête qui nécessite un ordre de résolution.</span><span class="sxs-lookup"><span data-stu-id="00459-142">These two queries are then combined into a query that requires solve order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00459-143">Vous pouvez exécuter ces requêtes MDX sur l'exemple de base de données multidimensionnelles Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="00459-143">You can run these MDX queries against the Adventure Works sample multidimensional database.</span></span> <span data-ttu-id="00459-144">Vous pouvez télécharger l’exemple de [modèles multidimensionnels AdventureWorks SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) à partir du site web Codeplex.</span><span class="sxs-lookup"><span data-stu-id="00459-144">You can download the [AdventureWorks Multidimensional Models SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) sample from the codeplex site.</span></span>  
  
### <a name="query-1-differences-in-income-and-expenses"></a><span data-ttu-id="00459-145">Requête 1-différences de revenus et de dépenses</span><span class="sxs-lookup"><span data-stu-id="00459-145">Query 1-Differences in Income and Expenses</span></span>  
 <span data-ttu-id="00459-146">Pour la première requête MDX, calculez la différence entre les ventes et les coûts pour chaque année en construisant une requête MDX simple semblable à l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="00459-146">For the first MDX query, calculate the difference in sales and costs for each year by constructing a simple MDX query similar to the following example:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] )  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="00459-147">Dans cette requête, il n'existe qu'un seul membre calculé, `Year Difference`.</span><span class="sxs-lookup"><span data-stu-id="00459-147">In this query, there is only one calculated member, `Year Difference`.</span></span> <span data-ttu-id="00459-148">L'ordre de résolution ne pose par conséquent aucun problème, tant que le cube n'utilise pas de membre calculé.</span><span class="sxs-lookup"><span data-stu-id="00459-148">Because there is only one calculated member, solve order is not an issue, as long as the cube does not use any calculated members.</span></span>  
  
 <span data-ttu-id="00459-149">Cette requête MDX produit un jeu de résultats semblable au tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="00459-149">This MDX query produces a result set similar to the following table.</span></span>  
  
||<span data-ttu-id="00459-150">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="00459-150">Internet Sales Amount</span></span>|<span data-ttu-id="00459-151">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="00459-151">Internet Total Product Cost</span></span>|  
|-|---------------------------|---------------------------------|  
|<span data-ttu-id="00459-152">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="00459-152">**CY 2007**</span></span>|<span data-ttu-id="00459-153">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="00459-153">$9,791,060.30</span></span>|<span data-ttu-id="00459-154">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="00459-154">$5,718,327.17</span></span>|  
|<span data-ttu-id="00459-155">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="00459-155">**CY 2008**</span></span>|<span data-ttu-id="00459-156">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="00459-156">$9,770,899.74</span></span>|<span data-ttu-id="00459-157">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="00459-157">$5,721,205.24</span></span>|  
|<span data-ttu-id="00459-158">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="00459-158">**Year Difference**</span></span>|<span data-ttu-id="00459-159">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="00459-159">($20,160.56)</span></span>|<span data-ttu-id="00459-160">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="00459-160">$2,878.06</span></span>|  
  
### <a name="query-2-percentage-of-income-after-expenses"></a><span data-ttu-id="00459-161">Requête 2 : pourcentage de revenus après dépenses</span><span class="sxs-lookup"><span data-stu-id="00459-161">Query 2-Percentage of Income after Expenses</span></span>  
 <span data-ttu-id="00459-162">Pour la seconde requête, calculez le pourcentage de revenus après dépenses pour chaque année à l'aide de la requête MDX suivante :</span><span class="sxs-lookup"><span data-stu-id="00459-162">For the second query, calculate the percentage of income after expenses for each year using the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Measures].[Profit Margin] AS   
([Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent"  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="00459-163">Cette requête MDX, comme la précédente, ne contient qu'un seul membre calculé, `Profit Margin`; elle ne présente donc aucune complication d'ordre de résolution.</span><span class="sxs-lookup"><span data-stu-id="00459-163">This MDX query, like the previous one, has only a single calculated member, `Profit Margin`, and therefore does not have any solve order complications.</span></span>  
  
 <span data-ttu-id="00459-164">Cette requête MDX produit un jeu de résultats légèrement différent, semblable au tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="00459-164">This MDX query produces a slightly different result set, similar to the following table.</span></span>  
  
||<span data-ttu-id="00459-165">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="00459-165">Internet Sales Amount</span></span>|<span data-ttu-id="00459-166">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="00459-166">Internet Total Product Cost</span></span>|<span data-ttu-id="00459-167">Marge de bénéfice</span><span class="sxs-lookup"><span data-stu-id="00459-167">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="00459-168">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="00459-168">**CY 2007**</span></span>|<span data-ttu-id="00459-169">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="00459-169">$9,791,060.30</span></span>|<span data-ttu-id="00459-170">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="00459-170">$5,718,327.17</span></span>|<span data-ttu-id="00459-171">41.60%</span><span class="sxs-lookup"><span data-stu-id="00459-171">41.60%</span></span>|  
|<span data-ttu-id="00459-172">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="00459-172">**CY 2008**</span></span>|<span data-ttu-id="00459-173">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="00459-173">$9,770,899.74</span></span>|<span data-ttu-id="00459-174">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="00459-174">$5,721,205.24</span></span>|<span data-ttu-id="00459-175">41.45%</span><span class="sxs-lookup"><span data-stu-id="00459-175">41.45%</span></span>|  
  
 <span data-ttu-id="00459-176">La différence entre les jeux de résultats des deux requêtes provient de la différence d'emplacement du membre calculé.</span><span class="sxs-lookup"><span data-stu-id="00459-176">The difference in result sets between the first query and the second query comes from the difference in placement of the calculated member.</span></span> <span data-ttu-id="00459-177">Dans la première requête, le membre calculé fait partie de l'axe ROWS, et non de l'axe COLUMNS illustré dans la deuxième requête.</span><span class="sxs-lookup"><span data-stu-id="00459-177">In the first query, the calculated member is part of the ROWS axis, not the COLUMNS axis shown in the second query.</span></span> <span data-ttu-id="00459-178">Cette différence d'emplacement devient importante dans la requête suivante, qui combine les deux membres calculés dans une même requête MDX.</span><span class="sxs-lookup"><span data-stu-id="00459-178">This difference in placement becomes important in the next query, which combines the two calculated members in a single MDX query.</span></span>  
  
### <a name="query-3-combined-year-difference-and-net-income-calculations"></a><span data-ttu-id="00459-179">Requête 3 : différence entre l’année combinée et le calcul du revenu net</span><span class="sxs-lookup"><span data-stu-id="00459-179">Query 3-Combined Year Difference and Net Income Calculations</span></span>  
 <span data-ttu-id="00459-180">Dans cette dernière requête combinant les deux exemples précédents en une seule requête MDX, l'ordre de résolution devient important en raison des calculs à la fois sur les colonnes et sur les lignes.</span><span class="sxs-lookup"><span data-stu-id="00459-180">In this final query combining both of the previous examples into a single MDX query, solve order becomes important because of the calculations on both columns and rows.</span></span> <span data-ttu-id="00459-181">Pour vous assurer que les calculs sont effectués dans l'ordre approprié, utilisez le mot clé `SOLVE_ORDER` afin de définir l'ordre des calculs.</span><span class="sxs-lookup"><span data-stu-id="00459-181">To make sure that the calculations occur in the correct sequence, define the sequence in which the calculations occur by using the `SOLVE_ORDER` keyword.</span></span>  
  
 <span data-ttu-id="00459-182">Le mot clé `SOLVE_ORDER` spécifie l'ordre de résolution des membres calculés dans une requête MDX ou une commande `CREATE MEMBER`.</span><span class="sxs-lookup"><span data-stu-id="00459-182">The `SOLVE_ORDER` keyword specifies the solve order of calculated members in an MDX query or a `CREATE MEMBER` command.</span></span> <span data-ttu-id="00459-183">Les valeurs entières utilisées avec le mot clé `SOLVE_ORDER` sont relatives, elles n'ont pas besoin de commencer à zéro et n'ont pas besoin d'être consécutives.</span><span class="sxs-lookup"><span data-stu-id="00459-183">The integer values used with the `SOLVE_ORDER` keyword are relative, do not need to start at zero, and do not need to be consecutive.</span></span> <span data-ttu-id="00459-184">La valeur indique simplement à la requête MDX de calculer un membre en fonction des valeurs dérivées du calcul des membres ayant une valeur supérieure.</span><span class="sxs-lookup"><span data-stu-id="00459-184">The value simply tells MDX to calculate a member based on values derived from calculating members with a higher value.</span></span> <span data-ttu-id="00459-185">Si un membre calculé est défini sans le mot clé `SOLVE_ORDER`, la valeur par défaut de ce membre calculé est zéro.</span><span class="sxs-lookup"><span data-stu-id="00459-185">If a calculated member is defined without the `SOLVE_ORDER` keyword, the default value of that calculated member is zero.</span></span>  
  
 <span data-ttu-id="00459-186">Par exemple, si vous combinez les calculs utilisés dans les deux premiers exemples de requêtes, les deux membres calculés, `Year Difference` et `Profit Margin`, se croisent à une cellule unique dans le dataset des résultats de l'exemple de requête MDX.</span><span class="sxs-lookup"><span data-stu-id="00459-186">For example, if you combine the calculations used in the first two example queries, the two calculated members, `Year Difference` and `Profit Margin`, intersect at a single cell in the result dataset of the MDX query example.</span></span> <span data-ttu-id="00459-187">Seul l’ordre de résolution permet de déterminer la façon dont [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] évaluera cette cellule.</span><span class="sxs-lookup"><span data-stu-id="00459-187">The only way to determine how [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] will evaluate this cell is by the solve order.</span></span> <span data-ttu-id="00459-188">Les formules utilisées pour construire cette cellule produiront différents résultats, en fonction de l'ordre de résolution des deux membres calculés.</span><span class="sxs-lookup"><span data-stu-id="00459-188">The formulas that are used to construct this cell will produce different results depending upon the solve order of the two calculated members.</span></span>  
  
 <span data-ttu-id="00459-189">Tout d'abord, essayez de combiner les calculs utilisés dans les deux premières requêtes dans la requête MDX suivante :</span><span class="sxs-lookup"><span data-stu-id="00459-189">First, try combining the calculations used in the first two queries in the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 1  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 2  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="00459-190">Dans cet exemple de requête MDX combinée, `Profit Margin` a l’ordre de résolution le plus élevé ; il est donc prioritaire quand les deux expressions interagissent.</span><span class="sxs-lookup"><span data-stu-id="00459-190">In this combined MDX query example, `Profit Margin` has the highest solve order, so it takes precedence when the two expressions interact.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="00459-191">évalue la cellule en question à l’aide de la formule `Profit Margin` .</span><span class="sxs-lookup"><span data-stu-id="00459-191">evaluates the cell in question by using the `Profit Margin` formula.</span></span> <span data-ttu-id="00459-192">Le tableau suivant présente les résultats de ces calculs imbriqués.</span><span class="sxs-lookup"><span data-stu-id="00459-192">The results of this nested calculation, as shown in the following table.</span></span>  
  
||<span data-ttu-id="00459-193">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="00459-193">Internet Sales Amount</span></span>|<span data-ttu-id="00459-194">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="00459-194">Internet Total Product Cost</span></span>|<span data-ttu-id="00459-195">Marge de bénéfice</span><span class="sxs-lookup"><span data-stu-id="00459-195">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="00459-196">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="00459-196">**CY 2007**</span></span>|<span data-ttu-id="00459-197">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="00459-197">$9,791,060.30</span></span>|<span data-ttu-id="00459-198">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="00459-198">$5,718,327.17</span></span>|<span data-ttu-id="00459-199">41.60%</span><span class="sxs-lookup"><span data-stu-id="00459-199">41.60%</span></span>|  
|<span data-ttu-id="00459-200">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="00459-200">**CY 2008**</span></span>|<span data-ttu-id="00459-201">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="00459-201">$9,770,899.74</span></span>|<span data-ttu-id="00459-202">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="00459-202">$5,721,205.24</span></span>|<span data-ttu-id="00459-203">41.45%</span><span class="sxs-lookup"><span data-stu-id="00459-203">41.45%</span></span>|  
|<span data-ttu-id="00459-204">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="00459-204">**Year Difference**</span></span>|<span data-ttu-id="00459-205">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="00459-205">($20,160.56)</span></span>|<span data-ttu-id="00459-206">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="00459-206">$2,878.06</span></span>|<span data-ttu-id="00459-207">114.28%</span><span class="sxs-lookup"><span data-stu-id="00459-207">114.28%</span></span>|  
  
 <span data-ttu-id="00459-208">Le résultat mentionné dans la cellule partagée est basé sur la formule de `Profit Margin`.</span><span class="sxs-lookup"><span data-stu-id="00459-208">The result in the shared cell is based on the formula for `Profit Margin`.</span></span> <span data-ttu-id="00459-209">Autrement dit, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calcule le résultat de la cellule partagée avec les données `Year Difference` , ce qui donne la formule suivante (le résultat est arrondi pour plus de clarté) :</span><span class="sxs-lookup"><span data-stu-id="00459-209">That is, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell with the `Year Difference` data, producing the following formula (the result is rounded for clarity):</span></span>  
  
```  
((9,770,899.74 - 9,791,060.30) - (5,721,205.24 - 5,718,327.17)) / (9,770,899.74 - 9,791,060.30) = 1.14275744   
```  
  
 <span data-ttu-id="00459-210">or</span><span class="sxs-lookup"><span data-stu-id="00459-210">or</span></span>  
  
```  
(23,038.63) / (20,160.56) = 114.28%  
```  
  
 <span data-ttu-id="00459-211">Ce résultat est clairement incorrect.</span><span class="sxs-lookup"><span data-stu-id="00459-211">This is clearly incorrect.</span></span> <span data-ttu-id="00459-212">Cependant, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calcule le résultat de la cellule partagée différemment si vous changez les ordres de résolution des membres calculés dans la requête MDX.</span><span class="sxs-lookup"><span data-stu-id="00459-212">However, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell differently if you switch the solve orders for the calculated members in the MDX query.</span></span> <span data-ttu-id="00459-213">La requête MDX combinée suivante inverse l'ordre de résolution des membres calculés :</span><span class="sxs-lookup"><span data-stu-id="00459-213">The following combined MDX query reverses the solve order for the calculated members:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 2  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 1  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="00459-214">L’ordre de résolution des membres calculés ayant été modifié, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] utilise la formule `Year Difference` pour évaluer la cellule, comme illustré dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="00459-214">As the order of the calculated members has been switched, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses the `Year Difference` formula to evaluate the cell, as shown in the following table.</span></span>  
  
||<span data-ttu-id="00459-215">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="00459-215">Internet Sales Amount</span></span>|<span data-ttu-id="00459-216">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="00459-216">Internet Total Product Cost</span></span>|<span data-ttu-id="00459-217">Marge de bénéfice</span><span class="sxs-lookup"><span data-stu-id="00459-217">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="00459-218">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="00459-218">**CY 2007**</span></span>|<span data-ttu-id="00459-219">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="00459-219">$9,791,060.30</span></span>|<span data-ttu-id="00459-220">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="00459-220">$5,718,327.17</span></span>|<span data-ttu-id="00459-221">41.60%</span><span class="sxs-lookup"><span data-stu-id="00459-221">41.60%</span></span>|  
|<span data-ttu-id="00459-222">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="00459-222">**CY 2008**</span></span>|<span data-ttu-id="00459-223">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="00459-223">$9,770,899.74</span></span>|<span data-ttu-id="00459-224">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="00459-224">$5,721,205.24</span></span>|<span data-ttu-id="00459-225">41.45%</span><span class="sxs-lookup"><span data-stu-id="00459-225">41.45%</span></span>|  
|<span data-ttu-id="00459-226">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="00459-226">**Year Difference**</span></span>|<span data-ttu-id="00459-227">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="00459-227">($20,160.56)</span></span>|<span data-ttu-id="00459-228">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="00459-228">$2,878.06</span></span>|<span data-ttu-id="00459-229">(0.15%)</span><span class="sxs-lookup"><span data-stu-id="00459-229">(0.15%)</span></span>|  
  
 <span data-ttu-id="00459-230">Comme cette requête utilise la formule `Year Difference` avec les données `Profit Margin` , la formule de la cellule partagée ressemble au calcul suivant :</span><span class="sxs-lookup"><span data-stu-id="00459-230">Because this query uses the `Year Difference` formula with the `Profit Margin` data, the formula for the shared cell resembles the following calculation:</span></span>  
  
```  
(($9,770,899.74 - 5,721,205.24) / $9,770,899.74) - ((9,791,060.30 - 5,718,327.17) / 9,791,060.30) = -0.15   
```  
  
 <span data-ttu-id="00459-231">ou</span><span class="sxs-lookup"><span data-stu-id="00459-231">Or</span></span>  
  
```  
0.4145 - 0.4160= -0.15  
```  
  
## <a name="additional-considerations"></a><span data-ttu-id="00459-232">Considérations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="00459-232">Additional Considerations</span></span>  
 <span data-ttu-id="00459-233">L'ordre de résolution peut s'avérer très délicat à gérer, notamment dans les cubes qui contiennent de très nombreuses dimensions impliquant des membres calculés, des formules de cumul personnalisé ou des cellules calculées.</span><span class="sxs-lookup"><span data-stu-id="00459-233">Solve order can be a very complex issue to deal with, especially in cubes with a high number of dimensions involving calculated member, custom rollup formulas, or calculated cells.</span></span> <span data-ttu-id="00459-234">Au moment où [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] évalue une requête MDX, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] prend en compte les valeurs d'ordre de résolution de tous les éléments impliqués dans un test de calcul donné, y compris les dimensions du cube spécifié dans la requête MDX.</span><span class="sxs-lookup"><span data-stu-id="00459-234">When [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates an MDX query, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] takes into account the solve order values for everything involved within a given pass, including the dimensions of the cube specified in the MDX query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00459-235">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00459-235">See Also</span></span>  
 <span data-ttu-id="00459-236">[CalculationCurrentPass&#41;MDX &#40;](/sql/mdx/calculationcurrentpass-mdx) </span><span class="sxs-lookup"><span data-stu-id="00459-236">[CalculationCurrentPass &#40;MDX&#41;](/sql/mdx/calculationcurrentpass-mdx) </span></span>  
 <span data-ttu-id="00459-237">[CalculationPassValue&#41;MDX &#40;](/sql/mdx/calculationpassvalue-mdx) </span><span class="sxs-lookup"><span data-stu-id="00459-237">[CalculationPassValue &#40;MDX&#41;](/sql/mdx/calculationpassvalue-mdx) </span></span>  
 <span data-ttu-id="00459-238">[Instruction CREATe MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="00459-238">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 [<span data-ttu-id="00459-239">Manipulation de données &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="00459-239">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
