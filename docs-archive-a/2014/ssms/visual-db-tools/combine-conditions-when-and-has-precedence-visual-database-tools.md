---
title: Associer des conditions avec priorité à l’opérateur AND (Visual Database Tools) | Microsoft Docs
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
- combining search conditions
- AND, Criteria pane
ms.assetid: 450eb2eb-6ea3-405b-8dd2-1ff926c016e7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 917d5381bc83083ee1fa3c07375945c0908da521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695168"
---
# <a name="combine-conditions-when-and-has-precedence-visual-database-tools"></a><span data-ttu-id="7ab11-102">Associer des conditions avec priorité à l'opérateur AND (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7ab11-102">Combine Conditions When AND Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="7ab11-103">Pour associer des conditions avec AND, vous ajoutez deux fois la colonne à la requête, une fois pour chaque condition.</span><span class="sxs-lookup"><span data-stu-id="7ab11-103">To combine conditions with AND, you add the column to the query twice--once for each condition.</span></span> <span data-ttu-id="7ab11-104">Pour associer des conditions à l’aide de l’opérateur OR, vous indiquez la première condition dans la colonne Filtre et les autres conditions dans une colonne **Ou...** .</span><span class="sxs-lookup"><span data-stu-id="7ab11-104">To combine conditions with OR, you put the first one in the Filter column and additional conditions into an **Or...** column.</span></span>  
  
 <span data-ttu-id="7ab11-105">Imaginez que vous souhaitiez, par exemple, rechercher des employés travaillant dans la société depuis plus de cinq ans à des postes de faible niveau ou des employés occupant des postes de moyen niveau quelle que soit leur date d'embauche.</span><span class="sxs-lookup"><span data-stu-id="7ab11-105">For example, imagine that you want to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs regardless of their hire date.</span></span> <span data-ttu-id="7ab11-106">Cette requête nécessite trois conditions, deux d'entre elles étant reliées à l'aide de l'opérateur AND :</span><span class="sxs-lookup"><span data-stu-id="7ab11-106">This query requires three conditions, two of them linked with AND:</span></span>  
  
-   <span data-ttu-id="7ab11-107">Employés dont la date d'embauche remonte à plus de cinq ans ET dont le niveau de poste s'élève à 100.</span><span class="sxs-lookup"><span data-stu-id="7ab11-107">Employees with a hire date earlier than five years ago AND with a job level of 100.</span></span>  
  
     <span data-ttu-id="7ab11-108">-ou-</span><span class="sxs-lookup"><span data-stu-id="7ab11-108">-or-</span></span>  
  
-   <span data-ttu-id="7ab11-109">Employés dont le niveau de poste s'élève à 200.</span><span class="sxs-lookup"><span data-stu-id="7ab11-109">Employees with a job level of 200.</span></span>  
  
### <a name="to-combine-conditions-when-and-has-precedence"></a><span data-ttu-id="7ab11-110">Pour associer des conditions avec priorité à l'opérateur AND</span><span class="sxs-lookup"><span data-stu-id="7ab11-110">To combine conditions when AND has precedence</span></span>  
  
1.  <span data-ttu-id="7ab11-111">Dans le [volet Critères](visual-database-tools.md), ajoutez les colonnes de données dans lesquelles vous souhaitez effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="7ab11-111">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="7ab11-112">Si vous souhaitez effectuer la recherche dans une même colonne à l'aide de deux conditions (voire plus) reliées à l'aide de l'opérateur AND, vous devez ajouter le nom de cette colonne de données à la grille pour chacune des valeurs que vous souhaitez rechercher.</span><span class="sxs-lookup"><span data-stu-id="7ab11-112">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="7ab11-113">Dans la colonne **Filtre** , entrez toutes les conditions que vous souhaitez relier à l’aide de l’opérateur AND.</span><span class="sxs-lookup"><span data-stu-id="7ab11-113">In the **Filter** column, enter all the conditions that you want to link with AND.</span></span> <span data-ttu-id="7ab11-114">Par exemple, pour relier à l'aide de l'opérateur AND des conditions effectuant une recherche dans les colonnes `hire_date` et `job_lvl` , entrez respectivement les valeurs `< '1/1/91'` et `= 100`dans la colonne Filtre.</span><span class="sxs-lookup"><span data-stu-id="7ab11-114">For example, to link conditions with AND that search the `hire_date` and `job_lvl` columns, enter the values `< '1/1/91'` and `= 100`, respectively, in the Filter column.</span></span>  
  
     <span data-ttu-id="7ab11-115">Les entrées effectuées dans la grille donnent lieu à la clause WHERE suivante dans l’instruction figurant dans le [volet SQL](sql-pane-visual-database-tools.md):</span><span class="sxs-lookup"><span data-stu-id="7ab11-115">These grid entries produce the following WHERE clause in the statement in the [SQL Pane](sql-pane-visual-database-tools.md):</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91') AND  
      (job_lvl = 100)  
    ```  
  
3.  <span data-ttu-id="7ab11-116">Dans la colonne de la grille **Ou...** , entrez les conditions que vous souhaitez relier à l’aide de l’opérateur OR.</span><span class="sxs-lookup"><span data-stu-id="7ab11-116">In the **Or...** grid column, enter conditions that you want to link with OR.</span></span> <span data-ttu-id="7ab11-117">Pour ajouter, par exemple, une condition recherchant une autre valeur dans la colonne `job_lvl` , entrez dans la colonne **Ou...** une valeur supplémentaire telle que `= 200`.</span><span class="sxs-lookup"><span data-stu-id="7ab11-117">For example, to add a condition that searches for another value in the `job_lvl` column, enter an additional value in the **Or...** column, such as `= 200`.</span></span>  
  
     <span data-ttu-id="7ab11-118">Quand vous ajoutez une valeur à la colonne **Ou...** , une autre condition vient s’ajouter à la clause WHERE dans l’instruction figurant dans le volet SQL :</span><span class="sxs-lookup"><span data-stu-id="7ab11-118">Adding a value in the **Or...** column adds another condition to the WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91' ) AND  
      (job_lvl = 100) OR   
      (job_lvl = 200)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7ab11-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7ab11-119">See Also</span></span>  
 <span data-ttu-id="7ab11-120">[Associer des conditions avec priorité à l' &#40;de Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7ab11-120">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="7ab11-121">[Conventions pour la combinaison de conditions de recherche dans le volet critères &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7ab11-121">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 <span data-ttu-id="7ab11-122">[Règles pour l’entrée de valeurs de recherche &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7ab11-122">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7ab11-123">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7ab11-123">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
