---
title: Conventions pour la combinaison de conditions de recherche dans le volet critères (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], combining
- precedence [SQL Server], Criteria pane
- search criteria [SQL Server], combining conditions
- multiple OR clauses
- combining search conditions
- OR operator
- AND, Criteria pane
- multiple AND clauses
ms.assetid: d4859be5-ff5b-48b2-a101-ad40c6dbcc68
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684521baa87d5325366a0e18296cd35342a0e947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695167"
---
# <a name="conventions-for-combining-search-conditions-in-the-criteria-pane-visual-database-tools"></a><span data-ttu-id="94334-102">Conventions pour la combinaison de conditions de recherche dans le volet Critères (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="94334-102">Conventions for Combining Search Conditions in the Criteria Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="94334-103">Vous pouvez créer des requêtes qui incluent un nombre quelconque de conditions de recherche, reliées par un nombre quelconque d'opérateurs AND et OR.</span><span class="sxs-lookup"><span data-stu-id="94334-103">You can create queries that include any number of search conditions, linked with any number of AND and OR operators.</span></span> <span data-ttu-id="94334-104">Une requête avec une combinaison de clauses AND et OR peut devenir complexe ; il est donc utile de comprendre comment une telle requête est interprétée quand vous l’exécutez et comment elle est représentée dans les volets [Critères](visual-database-tools.md) et [SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94334-104">A query with a combination of AND and OR clauses can become complex, so it is helpful to understand how such a query is interpreted when you execute it, and how such a query is represented in the [Criteria Pane](visual-database-tools.md) and [SQL Pane](sql-pane-visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94334-105">Pour plus d’informations sur les conditions de recherche qui contiennent un seul opérateur AND ou OR, consultez [Spécifier plusieurs conditions de recherche pour une colonne &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) et [Spécifier plusieurs conditions de recherche pour plusieurs colonnes &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94334-105">For details about search conditions that contain only one AND or OR operator, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) and [Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="94334-106">Vous trouverez ci-dessous des informations sur les sujets suivants :</span><span class="sxs-lookup"><span data-stu-id="94334-106">Below you will find information about:</span></span>  
  
-   <span data-ttu-id="94334-107">L'ordre de priorité des opérateurs AND et OR dans les requêtes où ils apparaissent tous les deux.</span><span class="sxs-lookup"><span data-stu-id="94334-107">The precedence of AND and OR in queries that contain both.</span></span>  
  
-   <span data-ttu-id="94334-108">La relation logique entre les conditions dans les clauses AND et OR.</span><span class="sxs-lookup"><span data-stu-id="94334-108">How the conditions in AND and OR clauses relate logically to one another.</span></span>  
  
-   <span data-ttu-id="94334-109">La façon dont le Concepteur de requêtes et de vues représente les requêtes qui contiennent à la fois AND et OR dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="94334-109">How the Query and View Designer represents in the Criteria Pane queries that contain both AND and OR.</span></span>  
  
 <span data-ttu-id="94334-110">Dans les paragraphes suivants, nous prendrons comme exemple une table `employee` contenant les colonnes `hire_date`, `job_lvl`et `status`.</span><span class="sxs-lookup"><span data-stu-id="94334-110">To help you understand the discussion below, imagine that you are working with an `employee` table containing the columns `hire_date`, `job_lvl`, and `status`.</span></span> <span data-ttu-id="94334-111">Nous supposerons que vous désirez savoir depuis combien de temps un employé travaille dans la société (quelle est sa date d'embauche), quel type de fonction il exerce (quel est son niveau de travail) et quel est son statut (par exemple, retraité).</span><span class="sxs-lookup"><span data-stu-id="94334-111">The examples assume that you need to know information such as how long an employee has worked with the company (that is, what the employee's hire date is), what type of job the employee performs (what the job level is), and the employee's status (for example, retired).</span></span>  
  
## <a name="precedence-of-and-and-or"></a><span data-ttu-id="94334-112">Ordre de priorité des opérateurs AND et OR</span><span class="sxs-lookup"><span data-stu-id="94334-112">Precedence of AND and OR</span></span>  
 <span data-ttu-id="94334-113">Lorsqu'une requête est exécutée, elle évalue d'abord les clauses reliées par AND, puis celles reliées par OR.</span><span class="sxs-lookup"><span data-stu-id="94334-113">When a query is executed, it evaluates first the clauses linked with AND, and then those linked with OR.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94334-114">L'opérateur NOT est prioritaire sur AND et sur OR.</span><span class="sxs-lookup"><span data-stu-id="94334-114">The NOT operator takes precedence over both AND and OR.</span></span>  
  
 <span data-ttu-id="94334-115">Par exemple, pour rechercher les employés qui travaillent dans la société depuis plus de cinq ans, avec un niveau de qualification faible ou les employés avec un niveau de qualification moyen, quelle que soit leur date d'embauche, vous pouvez construire la clause WHERE suivante :</span><span class="sxs-lookup"><span data-stu-id="94334-115">For example, to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs without regard for their hire date, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   job_lvl = 100 OR  
   job_lvl = 200  
  
```  
  
 <span data-ttu-id="94334-116">Pour substituer la priorité par défaut de AND sur OR, vous pouvez mettre certaines conditions entre parenthèses dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="94334-116">To override the default precedence of AND over OR, you can put parentheses around specific conditions in the SQL pane.</span></span> <span data-ttu-id="94334-117">Les conditions entre parenthèses sont toujours évaluées en premier.</span><span class="sxs-lookup"><span data-stu-id="94334-117">Conditions in parentheses are always evaluated first.</span></span> <span data-ttu-id="94334-118">Par exemple, pour rechercher tous les employés qui travaillent dans la société depuis plus de cinq ans avec un niveau de qualification faible ou moyen, vous pouvez créer la clause WHERE suivante :</span><span class="sxs-lookup"><span data-stu-id="94334-118">For example, to find all employees who have been with the company more than five years in either lower or middle-level jobs, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
> [!TIP]  
>  <span data-ttu-id="94334-119">Par souci de clarté, nous vous conseillons d'inclure systématiquement des parenthèses lorsque vous combinez des clauses AND et OR, plutôt que de compter uniquement sur la priorité par défaut.</span><span class="sxs-lookup"><span data-stu-id="94334-119">It is recommended that, for clarity, you always include parentheses when combining AND and OR clauses instead of relying on the default precedence.</span></span>  
  
## <a name="how-and-works-with-multiple-or-clauses"></a><span data-ttu-id="94334-120">Utilisation de AND avec plusieurs clauses OR</span><span class="sxs-lookup"><span data-stu-id="94334-120">How AND Works with Multiple OR Clauses</span></span>  
 <span data-ttu-id="94334-121">La maîtrise des relations entre les clauses AND et OR facilitera la création et la compréhension de requêtes complexes dans le Concepteur de requêtes et de vues.</span><span class="sxs-lookup"><span data-stu-id="94334-121">Understanding how AND and OR clauses are related when combined can help you construct and understand complex queries in the Query and View Designer.</span></span>  
  
 <span data-ttu-id="94334-122">Si vous reliez plusieurs conditions avec AND, le premier groupe de conditions reliées par AND s'applique à toutes les conditions du deuxième groupe.</span><span class="sxs-lookup"><span data-stu-id="94334-122">If you link multiple conditions using AND, the first set of conditions linked with AND applies to all the conditions in the second set.</span></span> <span data-ttu-id="94334-123">Autrement dit, une condition reliée par AND à une autre condition est distribuée à toutes les conditions du second groupe.</span><span class="sxs-lookup"><span data-stu-id="94334-123">In other words, a condition linked with AND to another condition is distributed to all the conditions in the second set.</span></span> <span data-ttu-id="94334-124">Par exemple, dans la représentation schématique suivante, une condition AND est reliée à un groupe de conditions OR :</span><span class="sxs-lookup"><span data-stu-id="94334-124">For example, the following schematic representation shows an AND condition linked to a set of OR conditions:</span></span>  
  
```  
A AND (B OR C)  
```  
  
 <span data-ttu-id="94334-125">La représentation précédente équivaut logiquement à la représentation schématique suivante, qui montre bien comment la condition AND est distribuée au second groupe de conditions :</span><span class="sxs-lookup"><span data-stu-id="94334-125">The representation above is logically equivalent to the following schematic representation, which shows how the AND condition is distributed to the second set of conditions:</span></span>  
  
```  
(A AND B) OR (A AND C)  
```  
  
 <span data-ttu-id="94334-126">Ce principe distributif influe sur la manière dont vous utilisez le Concepteur de requêtes et de vues.</span><span class="sxs-lookup"><span data-stu-id="94334-126">This distributive principle affects how you use the Query and View Designer.</span></span> <span data-ttu-id="94334-127">Par exemple, supposons que vous recherchiez tous les employés qui travaillent dans la société depuis plus de cinq ans, avec un niveau de qualification faible ou moyen.</span><span class="sxs-lookup"><span data-stu-id="94334-127">For example, imagine that you are looking for all employees who have been with the company more than five years in either lower or middle-level jobs.</span></span> <span data-ttu-id="94334-128">Vous inclurez alors la clause WHERE suivante dans l'instruction à l'intérieur du volet SQL :</span><span class="sxs-lookup"><span data-stu-id="94334-128">You enter the following WHERE clause into the statement in the SQL pane:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
 <span data-ttu-id="94334-129">La clause reliée par AND s'applique aux deux clauses reliées par OR.</span><span class="sxs-lookup"><span data-stu-id="94334-129">The clause linked with AND applies to both clauses linked with OR.</span></span> <span data-ttu-id="94334-130">La formulation sera plus claire si vous répétez la condition AND pour chaque condition dans la clause OR.</span><span class="sxs-lookup"><span data-stu-id="94334-130">An explicit way to express this is to repeat the AND condition once for each condition in the OR clause.</span></span> <span data-ttu-id="94334-131">L'instruction suivante équivaut à la précédente, mais elle est plus explicite (et plus longue) :</span><span class="sxs-lookup"><span data-stu-id="94334-131">The following statement is more explicit (and longer) than the previous statement, but is logically equivalent to it:</span></span>  
  
```  
WHERE    (hire_date < '01/01/95' ) AND  
  (job_lvl = 100) OR   
  (hire_date < '01/01/95' ) AND   
  (job_lvl = 200)  
```  
  
 <span data-ttu-id="94334-132">Le principe de la distribution des clauses AND aux clauses reliées par OR s'applique, quel que soit le nombre de conditions individuelles incluses dans l'instruction.</span><span class="sxs-lookup"><span data-stu-id="94334-132">The principle of distributing AND clauses to linked OR clauses applies no matter how many individual conditions are involved.</span></span> <span data-ttu-id="94334-133">Par exemple, supposons que vous vouliez rechercher les employés avec un niveau de qualification supérieur ou moyen, qui travaillent dans la société depuis plus de cinq ans ou qui sont à la retraite.</span><span class="sxs-lookup"><span data-stu-id="94334-133">For example, imagine that you want to find higher or middle-level employees who have been with the company more than five years or are retired.</span></span> <span data-ttu-id="94334-134">La clause WHERE pourra se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="94334-134">The WHERE clause might look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 OR job_lvl = 300) AND  
   (hire_date < '01/01/95' ) OR (status = 'R')  
```  
  
 <span data-ttu-id="94334-135">Après la distribution des clauses reliées par AND, la clause WHERE aura l'aspect suivant :</span><span class="sxs-lookup"><span data-stu-id="94334-135">After the conditions linked with AND have been distributed, the WHERE clause will look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 200 AND status = 'R') OR  
   (job_lvl = 300 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 300 AND status = 'R')   
```  
  
## <a name="how-multiple-and-and-or-clauses-are-represented-in-the-criteria-pane"></a><span data-ttu-id="94334-136">Représentation de plusieurs clauses AND et OR dans le volet Critères</span><span class="sxs-lookup"><span data-stu-id="94334-136">How Multiple AND and OR Clauses Are Represented in the Criteria Pane</span></span>  
 <span data-ttu-id="94334-137">Le Concepteur de requêtes et de vues représente vos conditions de recherche dans le [volet Critères](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94334-137">The Query and View Designer represents your search conditions in the [Criteria Pane](visual-database-tools.md).</span></span> <span data-ttu-id="94334-138">Dans certains cas de figure, cependant, où plusieurs clauses sont reliées par AND et OR, la représentation dans le volet Critères risque de n'être pas conforme à votre attente.</span><span class="sxs-lookup"><span data-stu-id="94334-138">However, in some cases that involve multiple clauses linked with AND and OR, the representation in the Criteria Pane might not be what you expect.</span></span> <span data-ttu-id="94334-139">En outre, si vous modifiez votre requête dans le volet Critères ou le [volet Schéma](diagram-pane-visual-database-tools.md), vous constaterez peut-être des différences entre l’instruction SQL que vous avez entrée et celle qui est affichée.</span><span class="sxs-lookup"><span data-stu-id="94334-139">In addition, if you modify your query in the Criteria Pane or [Diagram Pane](diagram-pane-visual-database-tools.md), you might find that your SQL statement has been changed from what you entered.</span></span>  
  
 <span data-ttu-id="94334-140">En général, la façon dont les clauses AND et OR apparaissent dans le volet Critères est déterminée par les règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="94334-140">In general, these rules dictate how AND and OR clauses appear in the Criteria Pane:</span></span>  
  
-   <span data-ttu-id="94334-141">Toutes les conditions reliées par AND apparaissent dans la colonne **Filtre** de la grille ou dans la même colonne **Ou...** .</span><span class="sxs-lookup"><span data-stu-id="94334-141">All conditions linked with AND appear in the **Filter** grid column or in the same **Or...** column.</span></span>  
  
-   <span data-ttu-id="94334-142">Toutes les conditions reliées par OR apparaissent dans des colonnes **Ou...** distinctes.</span><span class="sxs-lookup"><span data-stu-id="94334-142">All conditions linked with OR appear in separate **Or...** columns.</span></span>  
  
-   <span data-ttu-id="94334-143">Si le résultat logique d'une combinaison de clauses AND et OR s'obtient en distribuant l'opérateur AND dans plusieurs clauses OR, le volet Critères représente cette distribution de façon explicite en répétant la clause AND autant de fois que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="94334-143">If the logical result of a combination of AND and OR clauses is that the AND is distributed into several OR clauses, the Criteria Pane represents this explicitly by repeating the AND clause as many times as necessary.</span></span>  
  
 <span data-ttu-id="94334-144">Par exemple, vous pouvez créer dans le volet SQL une condition de recherche similaire à la suivante, où deux clauses reliées par AND sont prioritaires sur une troisième clause reliée par OR :</span><span class="sxs-lookup"><span data-stu-id="94334-144">For example, in the SQL pane you might create a search condition such as the following, in which two clauses linked with AND take precedence over a third one linked with OR:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  (job_lvl = 100) OR   
  (status = 'R')  
```  
  
 <span data-ttu-id="94334-145">Le Concepteur de requêtes et de vues représente cette clause WHERE dans le volet Critères de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="94334-145">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="94334-146">![Précédence de clause OR dans le volet Critères](../../database-engine/media//vs-criteriapane1.gif "Précédence de clause OR dans le volet Critères")</span><span class="sxs-lookup"><span data-stu-id="94334-146">![OR clause precedence in the Criteria Pane](../../database-engine/media//vs-criteriapane1.gif "OR clause precedence in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="94334-147">En revanche, si les clauses liées par OR sont prioritaires sur une clause AND, la clause AND est répétée pour chaque clause OR.</span><span class="sxs-lookup"><span data-stu-id="94334-147">However, if the linked OR clauses take precedence over an AND clause, the AND clause is repeated for each OR clause.</span></span> <span data-ttu-id="94334-148">Nous dirons qu'elle est distribuée à chaque clause OR.</span><span class="sxs-lookup"><span data-stu-id="94334-148">This causes the AND clause to be distributed to each OR clause.</span></span> <span data-ttu-id="94334-149">Par exemple, vous pouvez créer dans le volet SQL une clause WHERE du type suivant :</span><span class="sxs-lookup"><span data-stu-id="94334-149">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ( (job_lvl = 100) OR   
  (status = 'R') )  
```  
  
 <span data-ttu-id="94334-150">Le Concepteur de requêtes et de vues représente cette clause WHERE dans le volet Critères de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="94334-150">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="94334-151">![Clauses AND et OR multiples dans le volet Critères](../../database-engine/media//vs-criteriapane2.gif "Clauses AND et OR multiples dans le volet Critères")</span><span class="sxs-lookup"><span data-stu-id="94334-151">![Multiple AND and OR clauses in the Criteria Pane](../../database-engine/media//vs-criteriapane2.gif "Multiple AND and OR clauses in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="94334-152">Si les clauses liées par OR concernent une seule colonne de données, le Concepteur de requêtes et de vues peut placer l'ensemble de la clause OR dans une seule cellule de la grille, ce qui évite de répéter la clause AND.</span><span class="sxs-lookup"><span data-stu-id="94334-152">If the linked OR clauses involve only one data column, the Query and View Designer can place the entire OR clause into a single cell of the grid, avoiding the need to repeat the AND clause.</span></span> <span data-ttu-id="94334-153">Par exemple, vous pouvez créer dans le volet SQL une clause WHERE du type suivant :</span><span class="sxs-lookup"><span data-stu-id="94334-153">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ((status = 'R') OR (status = 'A'))  
```  
  
 <span data-ttu-id="94334-154">Le Concepteur de requêtes et de vues représente cette clause WHERE dans le volet Critères de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="94334-154">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="94334-155">![Clauses OR liées définies dans le volet Critères](../../database-engine/media//vs-criteriapane3.gif "Clauses OR liées définies dans le volet Critères")</span><span class="sxs-lookup"><span data-stu-id="94334-155">![Linked OR clauses defined in the Criteria Pane](../../database-engine/media//vs-criteriapane3.gif "Linked OR clauses defined in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="94334-156">Si vous apportez des modifications à la requête (en modifiant, par exemple, une valeur dans le volet Critères), le Concepteur de requêtes et de vues recrée l'instruction SQL dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="94334-156">If you make a change to the query (such as changing one of the values in the Criteria Pane), the Query and View Designer recreates the SQL statement in the SQL pane.</span></span> <span data-ttu-id="94334-157">L'instruction SQL recréée ressemblera à celle qui est affichée dans le volet Critères, et non à votre instruction d'origine.</span><span class="sxs-lookup"><span data-stu-id="94334-157">The recreated SQL statement will resemble the Criteria Pane display rather than your original statement.</span></span> <span data-ttu-id="94334-158">Par exemple, si le volet Critères contient des clauses AND distribuées, l'instruction obtenue dans le volet SQL contiendra des clauses AND distribuées de façon explicite.</span><span class="sxs-lookup"><span data-stu-id="94334-158">For example, if the Criteria Pane contains distributed AND clauses, the resulting statement in the SQL pane will be recreated with explicit distributed AND clauses.</span></span> <span data-ttu-id="94334-159">Pour plus d'informations, consultez « Utilisation de AND avec plusieurs clauses OR », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="94334-159">For details, see "How AND Works with Multiple OR Clauses" earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94334-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94334-160">See Also</span></span>  
 [<span data-ttu-id="94334-161">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="94334-161">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
