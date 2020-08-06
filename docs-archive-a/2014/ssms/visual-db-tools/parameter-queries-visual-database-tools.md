---
title: Requêtes avec paramètres (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- parameter queries [SQL Server]
ms.assetid: 4897c41a-324a-47b8-a30b-cbc9e9e19a8b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f6fd94ef180a34ae91d52c213092898612dc77d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611449"
---
# <a name="parameter-queries-visual-database-tools"></a><span data-ttu-id="dc51b-102">Requêtes avec paramètres (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="dc51b-102">Parameter Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="dc51b-103">Dans certains cas, il est utile de créer une requête si vous devez souvent y faire appel, mais chaque fois avec une valeur différente.</span><span class="sxs-lookup"><span data-stu-id="dc51b-103">In some cases you want to create a query that you can use many times, but with a different value each time.</span></span> <span data-ttu-id="dc51b-104">Par exemple, il se peut que vous exécutiez fréquemment une requête pour rechercher tous les `title_ids` écrits par un auteur.</span><span class="sxs-lookup"><span data-stu-id="dc51b-104">For example, you might frequently run a query to find all the `title_ids` written by one author.</span></span> <span data-ttu-id="dc51b-105">Chaque demande pourrait utiliser la même requête, mais l'ID ou le nom de l'auteur serait différent à chaque fois.</span><span class="sxs-lookup"><span data-stu-id="dc51b-105">You could run the same query for each request, except that the author's ID or name would be different each time.</span></span>  
  
 <span data-ttu-id="dc51b-106">Pour que la requête prenne une valeur différente selon le cas, incluez des paramètres dans sa création.</span><span class="sxs-lookup"><span data-stu-id="dc51b-106">To create a query that can have different values at different times, you use parameters in the query.</span></span> <span data-ttu-id="dc51b-107">Un paramètre est un espace réservé, qui sera rempli par une valeur fournie au moment de l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="dc51b-107">A parameter is a placeholder for a value that is supplied when the query runs.</span></span> <span data-ttu-id="dc51b-108">Dans l'instruction SQL de l'exemple suivant, « ? » représente le paramètre de l'ID de l'auteur :</span><span class="sxs-lookup"><span data-stu-id="dc51b-108">An SQL statement with a parameter might look like the following, where "?" represents the parameter for the author's ID:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
## <a name="where-you-can-use-parameters"></a><span data-ttu-id="dc51b-109">Où utiliser des paramètres</span><span class="sxs-lookup"><span data-stu-id="dc51b-109">Where You Can Use Parameters</span></span>  
 <span data-ttu-id="dc51b-110">Vous pouvez utiliser des paramètres comme des espaces réservés pour les valeurs littérales (textuelles ou numériques).</span><span class="sxs-lookup"><span data-stu-id="dc51b-110">You can use parameters as placeholders for literal values - for either text or numeric values.</span></span> <span data-ttu-id="dc51b-111">La plupart du temps, les paramètres sont utilisés en tant qu'espaces réservés dans des conditions de recherche de lignes individuelles ou de groupes (c'est-à-dire dans les clauses WHERE ou HAVING d'une instruction SQL).</span><span class="sxs-lookup"><span data-stu-id="dc51b-111">Most commonly, parameters are used as placeholders in search conditions for individual rows or for groups (that is, in the WHERE or HAVING clauses of an SQL statement).</span></span>  
  
 <span data-ttu-id="dc51b-112">Dans les expressions, vous pouvez utiliser les paramètres comme des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="dc51b-112">You can use parameters as placeholders in expressions.</span></span> <span data-ttu-id="dc51b-113">Par exemple, il est possible de calculer des prix avec remise en fournissant une remise différente à chaque exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="dc51b-113">For example, you might want to calculate discounted prices by supplying a different discount value each time you run a query.</span></span> <span data-ttu-id="dc51b-114">Dans ce cas, vous pourriez spécifier l'expression suivante :</span><span class="sxs-lookup"><span data-stu-id="dc51b-114">To do so, you could specify the following expression:</span></span>  
  
```  
(price * ?)  
```  
  
## <a name="specifying-unnamed-and-named-parameters"></a><span data-ttu-id="dc51b-115">Spécification de paramètres nommés et sans nom</span><span class="sxs-lookup"><span data-stu-id="dc51b-115">Specifying Unnamed and Named Parameters</span></span>  
 <span data-ttu-id="dc51b-116">Vous pouvez spécifier deux types de paramètres : nommés et sans nom.</span><span class="sxs-lookup"><span data-stu-id="dc51b-116">You can specify two types of parameters: unnamed and named.</span></span> <span data-ttu-id="dc51b-117">Un paramètre sans nom est un point d'interrogation (?) que vous pouvez placer dans la requête à l'endroit où vous serez invité à indiquer une valeur littérale.</span><span class="sxs-lookup"><span data-stu-id="dc51b-117">An unnamed parameter is a question mark (?) that you put anywhere in the query that you want to prompt for or substitute a literal value.</span></span> <span data-ttu-id="dc51b-118">Par exemple, si vous utilisez un paramètre sans nom pour rechercher l’ID d’un auteur dans la table `titleauthor` , le [volet SQL](visual-database-tools.md) peut proposer l’instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="dc51b-118">For example, if you use an unnamed parameter to search for an author's id in the `titleauthor` table, the resulting statement in the [SQL Pane](visual-database-tools.md) might look like this:</span></span>  
  
```  
SELECT title_id  
FROM titleauthor  
WHERE (au_id = ?)  
```  
  
 <span data-ttu-id="dc51b-119">Quand vous exécutez la requête dans le [Concepteur de requêtes et de vues](query-and-view-designer-tools-visual-database-tools.md), la boîte de dialogue [Paramètres de la requête](query-parameters-dialog-box-visual-database-tools.md) s’affiche avec « ? » comme nom du paramètre.</span><span class="sxs-lookup"><span data-stu-id="dc51b-119">When you run the query in the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md), the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with "?" as the name of the parameter.</span></span>  
  
 <span data-ttu-id="dc51b-120">Une autre méthode consiste à assigner un nom à un paramètre.</span><span class="sxs-lookup"><span data-stu-id="dc51b-120">Alternatively, you can assign a name to a parameter.</span></span> <span data-ttu-id="dc51b-121">Cela s'avère particulièrement utile si la requête doit comporter plusieurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="dc51b-121">Named parameters are particularly useful if you have multiple parameters in a query.</span></span> <span data-ttu-id="dc51b-122">Par exemple, voici l'instruction proposée dans le volet SQL si vous utilisez des paramètres nommés pour rechercher le prénom et le nom d'un auteur dans la table `authors` :</span><span class="sxs-lookup"><span data-stu-id="dc51b-122">For example, if you use named parameters to search for an author's first and last names in the `authors` table, the resulting statement in the SQL pane might look like this:</span></span>  
  
```  
SELECT au_id  
FROM authors  
WHERE au_fname = %first name% AND  
      au_lname = %last name%  
```  
  
> [!TIP]  
>  <span data-ttu-id="dc51b-123">Vous devez définir les caractères de préfixe et de suffixe avant de créer une requête employant un paramètre nommé.</span><span class="sxs-lookup"><span data-stu-id="dc51b-123">You must define prefix and suffix characters before creating a named parameter query.</span></span>  
  
 <span data-ttu-id="dc51b-124">Quand vous exécutez la requête dans le Concepteur de requêtes et de vues, la boîte de dialogue [Paramètres de la requête](query-parameters-dialog-box-visual-database-tools.md) s’affiche avec la liste des paramètres nommés.</span><span class="sxs-lookup"><span data-stu-id="dc51b-124">When you run the query in the Query and View Designer, the [Query Parameters Dialog Box](query-parameters-dialog-box-visual-database-tools.md) appears with a list of named parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc51b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dc51b-125">See Also</span></span>  
 <span data-ttu-id="dc51b-126">[Interroger avec des paramètres &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dc51b-126">[Query with Parameters &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md) </span></span>  
 <span data-ttu-id="dc51b-127">[Types de requêtes pris en charge &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dc51b-127">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="dc51b-128">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="dc51b-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
