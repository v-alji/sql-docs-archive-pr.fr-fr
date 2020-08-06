---
title: Spécifier plusieurs conditions de recherche pour plusieurs colonnes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 06617729-0d0b-4da2-9890-b7e2f5cdbc7b
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccf08a98d39d4ab808b7c2df794164b341be363a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603188"
---
# <a name="specify-multiple-search-conditions-for-multiple-columns-visual-database-tools"></a><span data-ttu-id="fba1c-102">Spécifier plusieurs conditions de recherche pour plusieurs colonnes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fba1c-102">Specify Multiple Search Conditions for Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="fba1c-103">Vous pouvez élargir ou restreindre l'étendue de votre requête en incluant plusieurs colonnes de données à votre condition de recherche.</span><span class="sxs-lookup"><span data-stu-id="fba1c-103">You can expand or narrow the scope of your query by including several data columns as part of your search condition.</span></span> <span data-ttu-id="fba1c-104">Vous pouvez, par exemple, souhaiter effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fba1c-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="fba1c-105">Rechercher des employés travaillant depuis plus de cinq ans dans la société ou occupant certains postes</span><span class="sxs-lookup"><span data-stu-id="fba1c-105">Search for employees who either have worked more than five years at the company or who hold certain jobs.</span></span>  
  
-   <span data-ttu-id="fba1c-106">Rechercher un livre qui est publié par un éditeur spécifique et qui appartient au domaine de la cuisine</span><span class="sxs-lookup"><span data-stu-id="fba1c-106">Search for a book that is both published by a specific publisher and pertains to cooking.</span></span>  
  
 <span data-ttu-id="fba1c-107">Pour créer une requête recherchant des valeurs dans l'une des deux colonnes (voire plus), spécifiez la condition OR.</span><span class="sxs-lookup"><span data-stu-id="fba1c-107">To create a query that searches for values in either of two (or more) columns, you specify an OR condition.</span></span> <span data-ttu-id="fba1c-108">Pour créer une requête répondant à l'ensemble des conditions dans deux colonnes (voire plus), spécifiez la condition AND.</span><span class="sxs-lookup"><span data-stu-id="fba1c-108">To create a query that must meet all conditions in two (or more) columns, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="fba1c-109">Spécification d'une condition OR</span><span class="sxs-lookup"><span data-stu-id="fba1c-109">Specifying an OR Condition</span></span>  
 <span data-ttu-id="fba1c-110">Pour créer plusieurs conditions reliées à l'aide de l'opérateur OR, indiquez chacune des conditions dans une colonne différente du volet Critères.</span><span class="sxs-lookup"><span data-stu-id="fba1c-110">To create multiple conditions linked with OR, you put each separate condition in a different column of the Criteria pane.</span></span>  
  
#### <a name="to-specify-an-or-condition-for-two-different-columns"></a><span data-ttu-id="fba1c-111">Pour spécifier une condition OR pour deux colonnes différentes</span><span class="sxs-lookup"><span data-stu-id="fba1c-111">To specify an OR condition for two different columns</span></span>  
  
1.  <span data-ttu-id="fba1c-112">Dans le [volet Critères](visual-database-tools.md), ajoutez les colonnes dans lesquelles vous souhaitez effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="fba1c-112">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="fba1c-113">Dans la colonne **Filtre** de la première colonne dans laquelle vous souhaitez effectuer la recherche, spécifiez la première condition.</span><span class="sxs-lookup"><span data-stu-id="fba1c-113">In the **Filter** column for the first column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="fba1c-114">Dans la colonne **Ou...** de la deuxième colonne de données dans laquelle vous souhaitez effectuer la recherche, spécifiez la deuxième condition, tout en laissant la colonne **Filtre** vide.</span><span class="sxs-lookup"><span data-stu-id="fba1c-114">In the **Or...** column for the second data column to search, specify the second condition, leaving the **Filter** column blank.</span></span>  
  
     <span data-ttu-id="fba1c-115">Le Concepteur de requêtes et de vues crée une clause WHERE comportant une condition OR de ce type :</span><span class="sxs-lookup"><span data-stu-id="fba1c-115">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
    ```  
    SELECT job_lvl, hire_date  
    FROM employee  
    WHERE (job_lvl >= 200) OR   
      (hire_date < '01/01/1998')  
    ```  
  
4.  <span data-ttu-id="fba1c-116">Répétez les étapes 2 et 3 pour chacune des autres conditions que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="fba1c-116">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span> <span data-ttu-id="fba1c-117">Utilisez une colonne **Ou...** différente pour chaque nouvelle condition.</span><span class="sxs-lookup"><span data-stu-id="fba1c-117">Use a different **Or...** column for each new condition.</span></span>  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="fba1c-118">Spécification d'une condition AND</span><span class="sxs-lookup"><span data-stu-id="fba1c-118">Specifying an AND Condition</span></span>  
 <span data-ttu-id="fba1c-119">Pour effectuer une recherche dans différentes colonnes de données reliées à l’aide de l’opérateur AND, définissez toutes les conditions dans la colonne **Filtre** de la grille.</span><span class="sxs-lookup"><span data-stu-id="fba1c-119">To search different data columns using conditions linked with AND, you put all the conditions in the **Filter** column of the grid.</span></span>  
  
#### <a name="to-specify-an-and-condition-for-two-different-columns"></a><span data-ttu-id="fba1c-120">Pour spécifier une condition AND pour deux colonnes différentes</span><span class="sxs-lookup"><span data-stu-id="fba1c-120">To specify an AND condition for two different columns</span></span>  
  
1.  <span data-ttu-id="fba1c-121">Dans le [volet Critères](visual-database-tools.md), ajoutez les colonnes dans lesquelles vous souhaitez effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="fba1c-121">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="fba1c-122">Dans la colonne **Filtre** de la première colonne de données dans laquelle vous souhaitez effectuer la recherche, spécifiez la première condition.</span><span class="sxs-lookup"><span data-stu-id="fba1c-122">In the **Filter** column for the first data column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="fba1c-123">Dans la colonne **Filtre** de la deuxième colonne de données, spécifiez la deuxième condition.</span><span class="sxs-lookup"><span data-stu-id="fba1c-123">In the **Filter** column for the second data column, specify the second condition.</span></span>  
  
     <span data-ttu-id="fba1c-124">Le Concepteur de requêtes et de vues crée une clause WHERE comportant une condition AND de ce type :</span><span class="sxs-lookup"><span data-stu-id="fba1c-124">The Query and View Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
    ```  
    SELECT pub_id, title  
    FROM titles  
    WHERE (pub_id = '0877') AND (title LIKE '%Cook%')  
    ```  
  
4.  <span data-ttu-id="fba1c-125">Répétez les étapes 2 et 3 pour chacune des autres conditions que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="fba1c-125">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba1c-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fba1c-126">See Also</span></span>  
 <span data-ttu-id="fba1c-127">[Associer des conditions avec priorité à l' &#40;de Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fba1c-127">[Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fba1c-128">[Associer des conditions avec priorité à l' &#40;de Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fba1c-128">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fba1c-129">[Conventions pour la combinaison de conditions de recherche dans le volet critères &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fba1c-129">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="fba1c-130">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fba1c-130">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
