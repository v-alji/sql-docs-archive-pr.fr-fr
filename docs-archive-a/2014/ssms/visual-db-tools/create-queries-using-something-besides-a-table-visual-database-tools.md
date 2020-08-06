---
title: Créer des requêtes à l’aide d’un tableau en dehors d’une table (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- user-defined functions [SQL Server], queries
- queries [SQL Server], creating
ms.assetid: 8e4a1f0a-8a42-4733-be8d-e21d6dbddb33
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0444c20fe10080949930f23623d5699f7fd3712c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600450"
---
# <a name="create-queries-using-something-besides-a-table-visual-database-tools"></a><span data-ttu-id="8c00e-102">Créer des requêtes qui utilisent autre chose qu'une table (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8c00e-102">Create Queries using Something Besides a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="8c00e-103">Pour écrire une requête d'extraction, il faut toujours formuler quelles sont les colonnes et les lignes à obtenir ainsi que le lieu où le processeur de requêtes trouve les données d'origine.</span><span class="sxs-lookup"><span data-stu-id="8c00e-103">Whenever you write a retrieval query, you articulate what columns you want, what rows you want, and where the query processor should find the original data.</span></span> <span data-ttu-id="8c00e-104">En général, une table ou plusieurs tables jointes constituent les données d'origine.</span><span class="sxs-lookup"><span data-stu-id="8c00e-104">Typically, this original data consists of a table or several tables joined together.</span></span> <span data-ttu-id="8c00e-105">Mais la source des données ne se trouve pas forcément dans une table.</span><span class="sxs-lookup"><span data-stu-id="8c00e-105">But the original data can come from sources other than tables.</span></span> <span data-ttu-id="8c00e-106">Les données d'origine peuvent venir de vues, de requêtes, de synonymes ou de fonctions définies par l'utilisateur et retournant une table.</span><span class="sxs-lookup"><span data-stu-id="8c00e-106">In fact, it can come from views, queries, synonyms, or user-defined functions that return a table.</span></span>  
  
## <a name="using-a-view-in-place-of-a-table"></a><span data-ttu-id="8c00e-107">Utilisation d'une vue à la place d'une table</span><span class="sxs-lookup"><span data-stu-id="8c00e-107">Using a View in Place of a Table</span></span>  
 <span data-ttu-id="8c00e-108">Il est possible de sélectionner des lignes d'une vue.</span><span class="sxs-lookup"><span data-stu-id="8c00e-108">You can select rows from a view.</span></span> <span data-ttu-id="8c00e-109">Par exemple, une base de données contient une vue « ExpensiveBooks » dont tous les titres ont un prix supérieur à 19.99 (19,99 dollars).</span><span class="sxs-lookup"><span data-stu-id="8c00e-109">For example, suppose the database includes a view called "ExpensiveBooks," in which each row describes a title whose price exceeds 19.99.</span></span> <span data-ttu-id="8c00e-110">La définition de la vue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="8c00e-110">The view definition might look like this:</span></span>  
  
```  
SELECT *  
FROM titles  
WHERE price > 19.99  
  
```  
  
 <span data-ttu-id="8c00e-111">Pour sélectionner les livres de luxe traitant de psychologie, sélectionnez cette catégorie dans la vue ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="8c00e-111">You can select the expensive psychology books merely by selecting the psychology books from the ExpensiveBooks view.</span></span> <span data-ttu-id="8c00e-112">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="8c00e-112">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM ExpensiveBooks  
WHERE type = 'psychology'  
  
```  
  
 <span data-ttu-id="8c00e-113">De façon similaire, une vue peut participer à une opération JOIN.</span><span class="sxs-lookup"><span data-stu-id="8c00e-113">Similarly, a view can participate in a JOIN operation.</span></span> <span data-ttu-id="8c00e-114">Par exemple, il est possible de rechercher les ventes de livres de luxe par une simple jointure entre la table Sales et la vue ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="8c00e-114">For example, you can find the sales of expensive books merely by joining the sales table to the ExpensiveBooks view.</span></span> <span data-ttu-id="8c00e-115">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="8c00e-115">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM sales   
         INNER JOIN   
         ExpensiveBooks   
         ON sales.title_id   
         =  ExpensiveBooks.title_id  
  
```  
  
 <span data-ttu-id="8c00e-116">Pour plus d’informations sur l’ajout d’une vue à une requête, consultez [Ajouter des tables à des requêtes &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c00e-116">For more information about adding a view to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-query-in-place-of-a-table"></a><span data-ttu-id="8c00e-117">Utilisation d'une requête à la place d'une table</span><span class="sxs-lookup"><span data-stu-id="8c00e-117">Using a Query in Place of a Table</span></span>  
 <span data-ttu-id="8c00e-118">Il est possible de sélectionner des lignes d'une requête.</span><span class="sxs-lookup"><span data-stu-id="8c00e-118">You can select rows from a query.</span></span> <span data-ttu-id="8c00e-119">Par exemple, vous avez déjà une requête qui extrait les titres et les identificateurs des livres signés par plusieurs auteurs.</span><span class="sxs-lookup"><span data-stu-id="8c00e-119">For example, suppose you have already written a query retrieving titles and identifiers of the coauthored books - the books with more than one author.</span></span> <span data-ttu-id="8c00e-120">L'instruction SQL peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="8c00e-120">The SQL might look like this:</span></span>  
  
```  
SELECT   
     titles.title_id, title, type  
FROM   
     titleauthor   
         INNER JOIN  
         titles   
         ON titleauthor.title_id   
         =  titles.title_id   
GROUP BY   
     titles.title_id, title, type  
HAVING COUNT(*) > 1  
  
```  
  
 <span data-ttu-id="8c00e-121">Vous pouvez alors écrire une autre requête qui tire parti de ce résultat.</span><span class="sxs-lookup"><span data-stu-id="8c00e-121">You can then write another query that builds on this result.</span></span> <span data-ttu-id="8c00e-122">Cette requête peut demander par exemple une extraction des livres signés par plusieurs auteurs et traitant de psychologie.</span><span class="sxs-lookup"><span data-stu-id="8c00e-122">For example, you can write a query that retrieves the coauthored psychology books.</span></span> <span data-ttu-id="8c00e-123">Utilisez la requête existante pour écrire la nouvelle. Elle constituera la source des données de la nouvelle requête.</span><span class="sxs-lookup"><span data-stu-id="8c00e-123">To write this new query, you can use the existing query as the source of the new query's data.</span></span> <span data-ttu-id="8c00e-124">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="8c00e-124">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    title  
FROM   
    (  
    SELECT   
        titles.title_id,   
        title,   
        type  
    FROM   
        titleauthor   
            INNER JOIN  
            titles   
            ON titleauthor.title_id   
            =  titles.title_id   
    GROUP BY   
        titles.title_id,   
        title,   
        type  
    HAVING COUNT(*) > 1  
    )   
    co_authored_books  
WHERE     type = 'psychology'  
  
```  
  
 <span data-ttu-id="8c00e-125">Le texte en gras montre la requête existante utilisée comme source de données de la nouvelle requête.</span><span class="sxs-lookup"><span data-stu-id="8c00e-125">The emphasized text shows the existing query used as the source of the new query's data.</span></span> <span data-ttu-id="8c00e-126">Remarquez que la nouvelle requête utilise un alias, « co_authored_books », pour indiquer la requête existante.</span><span class="sxs-lookup"><span data-stu-id="8c00e-126">Note that the new query uses an alias ("co_authored_books") for the existing query.</span></span> <span data-ttu-id="8c00e-127">Pour plus d’informations sur les alias, consultez [Créer des alias de tables &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) et [Créer des alias de colonnes &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c00e-127">For more information about aliases, see [Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) and [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="8c00e-128">De façon similaire, une requête peut participer à une opération JOIN.</span><span class="sxs-lookup"><span data-stu-id="8c00e-128">Similarly, a query can participate in a JOIN operation.</span></span> <span data-ttu-id="8c00e-129">Par exemple, il est possible de rechercher les ventes de livres de luxe signés par plusieurs auteurs en créant une jointure entre la vue ExpensiveBooks et la requête d'extraction des livres signés par plusieurs auteurs.</span><span class="sxs-lookup"><span data-stu-id="8c00e-129">For example, you can find the sales of expensive coauthored books merely by joining the ExpensiveBooks view to the query retrieving the coauthored books.</span></span> <span data-ttu-id="8c00e-130">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="8c00e-130">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    ExpensiveBooks.title  
FROM   
    ExpensiveBooks   
        INNER JOIN  
        (  
        SELECT   
            titles.title_id,   
            title,   
            type  
        FROM   
            titleauthor   
                INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
        GROUP BY   
            titles.title_id,   
            title,   
            type  
        HAVING COUNT(*) > 1  
        )  
```  
  
 <span data-ttu-id="8c00e-131">Pour plus d’informations sur l’ajout d’une requête à une requête, consultez [Ajouter des tables à des requêtes &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c00e-131">For more information about adding a query to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-user-defined-function-in-place-of-a-table"></a><span data-ttu-id="8c00e-132">Utilisation d'une fonction définie par l'utilisateur à la place d'une table</span><span class="sxs-lookup"><span data-stu-id="8c00e-132">Using a User-Defined Function in Place of a Table</span></span>  
 <span data-ttu-id="8c00e-133">Dans SQL Server 2000 ou une version ultérieure, vous pouvez créer une fonction définie par l'utilisateur et retournant une table.</span><span class="sxs-lookup"><span data-stu-id="8c00e-133">In SQL Server 2000 or higher, you can create a user-defined function that returns a table.</span></span> <span data-ttu-id="8c00e-134">Ce type de fonction permet d'utiliser une logique complexe ou procédurale.</span><span class="sxs-lookup"><span data-stu-id="8c00e-134">Such functions are useful for performing complex or procedural logic.</span></span>  
  
 <span data-ttu-id="8c00e-135">Par exemple, supposons que la table employee contienne une colonne supplémentaire, employee.manager_emp_id, et qu'il existe une clé étrangère entre manager_emp_id et employee.emp_id.</span><span class="sxs-lookup"><span data-stu-id="8c00e-135">For example, suppose the employee table contains an additional column, employee.manager_emp_id, and that a foreign key exists from manager_emp_id to employee.emp_id.</span></span> <span data-ttu-id="8c00e-136">Sur chaque ligne de la table employee, la colonne manager_emp_id indique le supérieur hiérarchique de l'employé.</span><span class="sxs-lookup"><span data-stu-id="8c00e-136">Within each row of the employee table, the manager_emp_id column indicates the employee's boss.</span></span> <span data-ttu-id="8c00e-137">Plus précisément, elle indique l'ID d'employé du responsable hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="8c00e-137">More precisely, it indicates the employee's boss's emp_id.</span></span> <span data-ttu-id="8c00e-138">La fonction que vous créez pourra renvoyer une table contenant une ligne par employé dépendant d'un responsable hiérarchique dont vous préciserez le niveau.</span><span class="sxs-lookup"><span data-stu-id="8c00e-138">You can create a user-defined function that returns a table containing one row for each employee working within a particular high-level manager's organizational hierarchy.</span></span> <span data-ttu-id="8c00e-139">Appelons cette fonction fn_GetWholeTeam et prévoyons dans son design l’utilisation d’une variable d’entrée (l’ID d’employé du responsable de l’équipe à récupérer).</span><span class="sxs-lookup"><span data-stu-id="8c00e-139">You might call the function fn_GetWholeTeam, and design it to take an input variable - the emp_id of the manager whose team you want to retrieve.</span></span>  
  
 <span data-ttu-id="8c00e-140">Il est possible d'écrire une requête utilisant la fonction fn_GetWholeTeam comme source de données.</span><span class="sxs-lookup"><span data-stu-id="8c00e-140">You can write a query that uses the fn_GetWholeTeam function as a source of data.</span></span> <span data-ttu-id="8c00e-141">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="8c00e-141">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *   
FROM   
     fn_GetWholeTeam ('VPA30890F')  
  
```  
  
 <span data-ttu-id="8c00e-142">« VPA30890F » est l'ID d'employé du responsable de l'équipe à extraire.</span><span class="sxs-lookup"><span data-stu-id="8c00e-142">"VPA30890F" is the emp_id of the manager whose organization you want to retrieve.</span></span> <span data-ttu-id="8c00e-143">Pour plus d’informations sur l’ajout d’une fonction définie par l’utilisateur à une requête, consultez [Ajouter des tables à des requêtes &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c00e-143">For more information about adding a user-defined function to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="8c00e-144">Pour obtenir une description complète des fonctions définies par l’utilisateur, consultez [Fonctions définies par l’utilisateur](../../relational-databases/user-defined-functions/user-defined-functions.md).</span><span class="sxs-lookup"><span data-stu-id="8c00e-144">For a complete description of user-defined functions, see [User-Defined Functions](../../relational-databases/user-defined-functions/user-defined-functions.md).</span></span>  
  
  
