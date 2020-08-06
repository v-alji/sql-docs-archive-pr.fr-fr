---
title: Associer des conditions avec priorité à l’opérateur OR (Visual Database Tools) | Microsoft Docs
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
- OR operator
ms.assetid: b30f5ac9-25e7-4163-80ed-44e4bccb455d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8be0d2f783c28662eb01f6bf191dc24d339534f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695163"
---
# <a name="combine-conditions-when-or-has-precedence-visual-database-tools"></a><span data-ttu-id="2691c-102">Associer des conditions avec priorité à l'opérateur OR (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2691c-102">Combine Conditions When OR Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="2691c-103">Pour relier des conditions à l'aide de l'opérateur OR et leur accorder la priorité sur les conditions reliées à l'aide de l'opérateur AND, vous devez répéter la condition AND pour chaque condition OR.</span><span class="sxs-lookup"><span data-stu-id="2691c-103">To link conditions with OR and give them precedence over conditions linked with AND, you must repeat the AND condition for each OR condition.</span></span>  
  
 <span data-ttu-id="2691c-104">Imaginez que vous souhaitez, par exemple, rechercher tous les employés travaillant dans la société depuis plus de cinq ans et occupant des postes de faible niveau ou étant à la retraite.</span><span class="sxs-lookup"><span data-stu-id="2691c-104">For example, imagine that you want to find all employees who have been with the company more than five years and have lower-level jobs or are retired.</span></span> <span data-ttu-id="2691c-105">Cette requête nécessite trois conditions, une condition reliée à deux autres conditions à l'aide de l'opérateur AND :</span><span class="sxs-lookup"><span data-stu-id="2691c-105">This query requires three conditions, a single condition linked to two additional conditions with AND:</span></span>  
  
-   <span data-ttu-id="2691c-106">Employés dont la date d'embauche remonte à plus de cinq ans et</span><span class="sxs-lookup"><span data-stu-id="2691c-106">Employees with a hire date earlier than five years ago, and</span></span>  
  
-   <span data-ttu-id="2691c-107">Employés dont le niveau de poste s'élève à 100 ou dont le statut est défini sur « R » (Retraite)</span><span class="sxs-lookup"><span data-stu-id="2691c-107">Employees with a job level of 100 or whose status is "R" (for retired).</span></span>  
  
 <span data-ttu-id="2691c-108">Pour créer ce type de requête dans le volet Critères, suivez la procédure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2691c-108">The following procedure illustrates how to create this type of query in the Criteria pane.</span></span>  
  
### <a name="to-combine-conditions-when-or-has-precedence"></a><span data-ttu-id="2691c-109">Pour associer des conditions avec priorité à l'opérateur OR</span><span class="sxs-lookup"><span data-stu-id="2691c-109">To combine conditions when OR has precedence</span></span>  
  
1.  <span data-ttu-id="2691c-110">Dans le [volet Critères](visual-database-tools.md), ajoutez les colonnes de données dans lesquelles vous souhaitez effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="2691c-110">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="2691c-111">Si vous souhaitez effectuer la recherche dans une même colonne à l'aide de deux conditions (voire plus) reliées à l'aide de l'opérateur AND, vous devez ajouter le nom de cette colonne de données à la grille pour chacune des valeurs que vous souhaitez rechercher.</span><span class="sxs-lookup"><span data-stu-id="2691c-111">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="2691c-112">Créez les conditions à relier à l'aide de l'opérateur OR en entrant la première condition dans la colonne de la grille **Filtre** et la deuxième condition (ainsi que les conditions suivantes) dans des colonnes **Ou...** distinctes.</span><span class="sxs-lookup"><span data-stu-id="2691c-112">Create the conditions to be linked with OR by entering the first one into the **Filter** grid column and the second (and subsequent ones) into separate **Or...** columns.</span></span> <span data-ttu-id="2691c-113">Par exemple, pour relier à l'aide de l'opérateur OR des conditions effectuant une recherche dans les colonnes `job_lvl` et `status` , entrez `= 100` dans la colonne **Filtre** pour `job_lvl` et `= 'R'` dans la colonne **Ou...** pour `status`.</span><span class="sxs-lookup"><span data-stu-id="2691c-113">For example, to link conditions with OR that search the `job_lvl` and `status` columns, enter `= 100` in the **Filter** column for `job_lvl` and `= 'R'` in the **Or...** column for `status`.</span></span>  
  
     <span data-ttu-id="2691c-114">La saisie de ces valeurs dans la grille génère la clause WHERE suivante dans l'instruction figurant dans le volet SQL :</span><span class="sxs-lookup"><span data-stu-id="2691c-114">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) OR (status = 'R')  
    ```  
  
3.  <span data-ttu-id="2691c-115">Créez la condition AND en la définissant pour chaque condition OR.</span><span class="sxs-lookup"><span data-stu-id="2691c-115">Create the AND condition by entering it once for each OR condition.</span></span> <span data-ttu-id="2691c-116">Effectuez chaque entrée dans la même colonne de la grille que celle de la condition OR à laquelle elle correspond.</span><span class="sxs-lookup"><span data-stu-id="2691c-116">Place each entry in the same grid column as the OR condition it corresponds to.</span></span> <span data-ttu-id="2691c-117">Pour ajouter, par exemple, une condition AND effectuant une recherche dans la colonne `hire_date` et s'appliquant aux deux conditions OR, entrez `< '1/1/91'` dans la colonne Critères et dans la colonne **Ou...** .</span><span class="sxs-lookup"><span data-stu-id="2691c-117">For example, to add an AND condition that searches the `hire_date` column and applies to both OR conditions, enter `< '1/1/91'` in both the Criteria column and the **Or...** column.</span></span>  
  
     <span data-ttu-id="2691c-118">La saisie de ces valeurs dans la grille génère la clause WHERE suivante dans l'instruction figurant dans le volet SQL :</span><span class="sxs-lookup"><span data-stu-id="2691c-118">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) AND   
      (hire_date < '01/01/91' ) OR  
      (status = 'R') AND   
      (hire_date < '01/01/91' )  
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="2691c-119">Vous pouvez répéter une condition AND en l'ajoutant une fois, puis en utilisant les commandes **Couper** et **Coller** du menu **Edition** pour la répéter dans d'autres conditions OR.</span><span class="sxs-lookup"><span data-stu-id="2691c-119">You can repeat an AND condition by adding it once, and then using the **Cut** and **Paste** commands from the **Edit** menu to repeat it for other OR conditions.</span></span>  
  
 <span data-ttu-id="2691c-120">La clause WHERE créée par le Concepteur de requêtes et de vues équivaut à la clause WHERE suivante, qui utilise des parenthèses pour spécifier la priorité de l'opérateur OR sur l'opérateur AND :</span><span class="sxs-lookup"><span data-stu-id="2691c-120">The WHERE clause created by the Query and View Designer is equivalent to the following WHERE clause, which uses parentheses to specify the precedence of OR over AND:</span></span>  
  
```  
WHERE (job_lvl = 100 OR status = 'R') AND  
   (hire_date < '01/01/91')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2691c-121">Quand vous entrez des conditions de requête au format indiqué immédiatement au-dessus du [volet SQL](sql-pane-visual-database-tools.md), mais que vous apportez par la suite des modifications à la requête figurant dans le volet Schéma ou dans le volet Critères, le Concepteur de requêtes recrée l'instruction SQL pour qu'elle corresponde à ce format, avec la condition AND répartie de manière explicite vers les deux conditions OR.</span><span class="sxs-lookup"><span data-stu-id="2691c-121">If you enter the search conditions in the format shown immediately above in the [SQL Pane](sql-pane-visual-database-tools.md), but then make a change to the query in the Diagram or Criteria panes, the Query and View Designer recreates the SQL statement to match the form with the AND condition explicitly distributed to both OR conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2691c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2691c-122">See Also</span></span>  
 <span data-ttu-id="2691c-123">[Conventions pour la combinaison de conditions de recherche dans le volet critères &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2691c-123">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="2691c-124">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2691c-124">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
