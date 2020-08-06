---
title: Trier des lignes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- sorting rows [SQL Server]
- sorting query results [SQL Server]
ms.assetid: 780ef467-f96e-4373-8235-6dacbedb05a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4939c08a4be8c6a7aa3a52d55928abe077f25d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705820"
---
# <a name="sort-rows-visual-database-tools"></a><span data-ttu-id="bb684-102">Trier des lignes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="bb684-102">Sort Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="bb684-103">Il est possible de choisir l'ordre des lignes qui apparaîtront dans le résultat d'une requête.</span><span class="sxs-lookup"><span data-stu-id="bb684-103">You can order the rows in a query result.</span></span> <span data-ttu-id="bb684-104">C'est-à-dire que vous pouvez indiquer dans quelle colonne, ou dans quel ensemble de colonnes, les valeurs seront triées pour déterminer l'ordre d'affichage des lignes dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="bb684-104">That is, you can name a particular column or set of columns whose values determine the order of rows in the result set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb684-105">L'ordre de tri est déterminé en partie par la séquence de classement de la colonne.</span><span class="sxs-lookup"><span data-stu-id="bb684-105">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="bb684-106">Vous pouvez modifier cette séquence dans la [boîte de dialogue Classement](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bb684-106">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="bb684-107">Vous disposez de plusieurs méthodes pour trier les résultats d'une requête :</span><span class="sxs-lookup"><span data-stu-id="bb684-107">There are several ways in which you can sort query results:</span></span>  
  
-   <span data-ttu-id="bb684-108">**Vous pouvez demander à trier les lignes par ordre croissant ou décroissant** Par défaut, SQL se réfère aux colonnes de la clause ORDER BY pour trier les lignes selon un ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="bb684-108">**You can arrange rows in ascending or descending order** By default, SQL uses order-by columns to arrange rows in ascending order.</span></span> <span data-ttu-id="bb684-109">Par exemple, pour trier les titres des livres par ordre croissant de prix, il suffit de trier les lignes selon la colonne du prix.</span><span class="sxs-lookup"><span data-stu-id="bb684-109">For example, to arrange the book titles by ascending price, simply sort the rows by the price column.</span></span> <span data-ttu-id="bb684-110">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="bb684-110">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price  
  
    ```  
  
     <span data-ttu-id="bb684-111">Cependant, si vous souhaitez faire apparaître les livres les plus chers en premier, vous pouvez demander un tri décroissant selon le prix.</span><span class="sxs-lookup"><span data-stu-id="bb684-111">On the other hand, if you want to arrange the titles with the more expensive books first, you can explicitly specify a highest-first ordering.</span></span> <span data-ttu-id="bb684-112">Dans ce cas, vous devez indiquer que les lignes obtenues dans l'ensemble des résultats devront être triées selon la colonne du prix et en ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="bb684-112">That is, you indicate that the result rows should be arranged by descending values of the price column.</span></span> <span data-ttu-id="bb684-113">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="bb684-113">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="bb684-114">**Vous pouvez demander un tri sur plusieurs colonnes** Par exemple, il est possible de demander un ensemble de résultats affichant une ligne par auteur et trié selon l'état, puis la ville.</span><span class="sxs-lookup"><span data-stu-id="bb684-114">**You can sort by multiple columns** For example, you can create a result set with one row for each author, ordering first by state and then by city.</span></span> <span data-ttu-id="bb684-115">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="bb684-115">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM authors   
    ORDER BY state, city  
  
    ```  
  
-   <span data-ttu-id="bb684-116">**Vous pouvez demander un tri en fonction de colonnes qui n'apparaîtront pas dans l'ensemble des résultats** Par exemple, l'ensemble des résultats présentera les livres les plus chers en premier, mais sans faire apparaître les prix.</span><span class="sxs-lookup"><span data-stu-id="bb684-116">**You can sort by columns not appearing in the result set** For example, you can create a result set with the most expensive titles first, even though the prices do not appear.</span></span> <span data-ttu-id="bb684-117">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="bb684-117">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title_id, title  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="bb684-118">**Vous pouvez trier en fonction des colonnes dérivées** Par exemple, dans l’ensemble des résultats, chaque ligne contiendra le titre d’un livre, les livres les plus rentables à l’unité étant présentés en premier.</span><span class="sxs-lookup"><span data-stu-id="bb684-118">**You can sort by derived columns** For example, you can create a result set in which each row contains a book title - with the books that pay the highest royalty per copy appearing first.</span></span> <span data-ttu-id="bb684-119">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="bb684-119">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title, price * royalty / 100 as royalty_per_unit  
    FROM titles  
    ORDER BY royalty_per_unit DESC  
  
    ```  
  
     <span data-ttu-id="bb684-120">(La formule calculant la rentabilité à l'unité de chaque livre est en gras.)</span><span class="sxs-lookup"><span data-stu-id="bb684-120">(The formula for calculating the royalty that each book earns per copy is emphasized.)</span></span>  
  
     <span data-ttu-id="bb684-121">Pour calculer une colonne dérivée, vous pouvez utiliser une syntaxe SQL (comme dans l'exemple précédent) ou une fonction définie par l'utilisateur qui retourne une valeur scalaire.</span><span class="sxs-lookup"><span data-stu-id="bb684-121">To calculate a derived column, you can use SQL syntax, as in the preceding example, or you can use a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="bb684-122">Pour plus d'informations sur les fonctions définies par l'utilisateur, consultez la documentation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bb684-122">For more information about user-defined functions, see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="bb684-123">**Vous pouvez trier des lignes groupées** Par exemple, dans l’ensemble des résultats, chaque ligne contiendra une ville et le nombre d’auteurs qui y résident. Les villes comprenant le plus grand nombre d’auteurs seront affichées en premier.</span><span class="sxs-lookup"><span data-stu-id="bb684-123">**You can sort grouped rows** For example; you can create a result set in which each row describes a city, plus the number of authors in that city - with the cities containing many authors appearing first.</span></span> <span data-ttu-id="bb684-124">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="bb684-124">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT city, state, COUNT(*)  
    FROM authors  
    GROUP BY city, state  
    ORDER BY COUNT(*) DESC, state  
  
    ```  
  
     <span data-ttu-id="bb684-125">Remarquez que la requête utilise `state` comme colonne secondaire du tri.</span><span class="sxs-lookup"><span data-stu-id="bb684-125">Notice that the query uses `state` as a secondary sort column.</span></span> <span data-ttu-id="bb684-126">De cette manière, si deux états ont le même nombre d'auteurs, vous pouvez les faire apparaître par ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="bb684-126">Thus, if two states have the same number of authors, those states will appear in alphabetical order.</span></span>  
  
-   <span data-ttu-id="bb684-127">**Vous pouvez demander un tri en fonction de données internationales** C'est-à-dire que vous pouvez trier une colonne selon des conventions de classement qui diffèrent des conventions utilisées par défaut pour cette colonne.</span><span class="sxs-lookup"><span data-stu-id="bb684-127">**You can sort using international data** That is; you can sort a column using collating conventions that differ from the default conventions for that column.</span></span> <span data-ttu-id="bb684-128">Par exemple, vous pouvez écrire une requête qui récupère tous les titres de livres par Jaime PATI ?? sorties.</span><span class="sxs-lookup"><span data-stu-id="bb684-128">For example, you can write a query that retrieves all the book titles by Jaime Pati??o.</span></span> <span data-ttu-id="bb684-129">Pour afficher les titres par ordre alphabétique, vous demanderez à appliquer à la colonne des titres une table de classement espagnole.</span><span class="sxs-lookup"><span data-stu-id="bb684-129">To display the titles in alphabetical order, you use a Spanish collating sequence for the title column.</span></span> <span data-ttu-id="bb684-130">L'instruction SQL obtenue peut se présenter de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="bb684-130">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title  
    FROM   
        authors   
        INNER JOIN   
            titleauthor   
            ON authors.au_id   
            =  titleauthor.au_id   
            INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
    WHERE   
         au_fname = 'Jaime' AND   
         au_lname = 'Pati??o'  
    ORDER BY   
         title COLLATE SQL_Spanish_Pref_CP1_CI_AS  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bb684-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb684-131">See Also</span></span>  
 <span data-ttu-id="bb684-132">[Trier et regrouper les résultats des requêtes &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bb684-132">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="bb684-133">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="bb684-133">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
