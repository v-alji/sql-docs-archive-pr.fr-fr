---
title: Créer des sous-requêtes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], subqueries
- nested queries
- subqueries [SQL Server], SQL pane
ms.assetid: 34f6b9b4-ca3a-4a4f-9594-36e513f1c547
author: stevestein
ms.author: sstein
ms.openlocfilehash: 540228839b9734992be008b5d4fb7d717176832e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610947"
---
# <a name="create-subqueries-visual-database-tools"></a><span data-ttu-id="dd81b-102">Créer des sous-requêtes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="dd81b-102">Create Subqueries (Visual Database Tools)</span></span>
  <span data-ttu-id="dd81b-103">Vous pouvez utiliser les résultats d'une requête en tant que point de départ d'une autre requête.</span><span class="sxs-lookup"><span data-stu-id="dd81b-103">You can use the results of one query as the input for another.</span></span> <span data-ttu-id="dd81b-104">Vous pouvez utiliser les résultats d’une sous-requête en tant qu’instruction faisant appel à la fonction IN( ), à l’opérateur EXISTS ou à la clause FROM.</span><span class="sxs-lookup"><span data-stu-id="dd81b-104">You can use the results of a subquery as a statement that uses the IN( ) function, the EXISTS operator, or the FROM clause.</span></span>  
  
 <span data-ttu-id="dd81b-105">Vous pouvez créer une sous-requête en l'introduisant directement dans le volet SQL ou copier une requête et la coller dans un autre.</span><span class="sxs-lookup"><span data-stu-id="dd81b-105">You can create a subquery by entering it directly into the SQL pane or by copying a query and pasting it into another.</span></span>  
  
### <a name="to-define-a-subquery-in-the-sql-pane"></a><span data-ttu-id="dd81b-106">Pour définir une sous-requête dans le volet SQL</span><span class="sxs-lookup"><span data-stu-id="dd81b-106">To define a subquery in the SQL pane</span></span>  
  
1.  <span data-ttu-id="dd81b-107">Créez la requête de base.</span><span class="sxs-lookup"><span data-stu-id="dd81b-107">Create the primary query.</span></span>  
  
2.  <span data-ttu-id="dd81b-108">Dans le volet SQL, sélectionnez l’instruction SQL, puis utilisez la commande **Copier** pour déplacer la requête dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="dd81b-108">In the SQL pane, select the SQL statement, and then use **Copy** to move the query to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="dd81b-109">Créez la requête, puis utilisez la commande **Coller** pour coller la première requête dans la clause WHERE ou FROM de cette nouvelle requête.</span><span class="sxs-lookup"><span data-stu-id="dd81b-109">Start the new query, and then use **Paste** to move the first query into the new query's WHERE or FROM clause.</span></span>  
  
     <span data-ttu-id="dd81b-110">Imaginez, par exemple, que vous soyez en présence de deux tables ( `products` et `suppliers`) et que vous souhaitiez créer une requête indiquant tous les produits de fournisseurs suédois.</span><span class="sxs-lookup"><span data-stu-id="dd81b-110">For example, imagine you have two tables, `products` and `suppliers`, and you want to create a query showing all products for suppliers in Sweden.</span></span> <span data-ttu-id="dd81b-111">Créez la première requête relative à la table `suppliers` pour rechercher tous les fournisseurs suédois :</span><span class="sxs-lookup"><span data-stu-id="dd81b-111">Create the first query on the `suppliers` table to find all Swedish suppliers:</span></span>  
  
    ```  
    SELECT supplier_id  
    FROM supplier  
    WHERE (country = 'Sweden')  
    ```  
  
     <span data-ttu-id="dd81b-112">Utilisez la commande Copier pour copier cette requête dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="dd81b-112">Use the Copy command to move this query to the Clipboard.</span></span> <span data-ttu-id="dd81b-113">Créez la deuxième requête relative à la table `products` répertoriant toutes les informations nécessaires sur les produits :</span><span class="sxs-lookup"><span data-stu-id="dd81b-113">Create the second query using the `products` table, listing the information you need about products:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    ```  
  
     <span data-ttu-id="dd81b-114">Dans le volet SQL, ajoutez une clause WHERE à la deuxième requête, puis collez la première requête à partir du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="dd81b-114">In the SQL pane, add a WHERE clause to the second query, then paste the first query from the Clipboard.</span></span> <span data-ttu-id="dd81b-115">Ajoutez des parenthèses autour de la première requête afin d'obtenir le résultat final suivant :</span><span class="sxs-lookup"><span data-stu-id="dd81b-115">Place parentheses around the first query, so that the end result looks like this:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    WHERE supplier_id IN  
       (SELECT supplier_id  
      FROM supplier  
      WHERE (country = 'Sweden'))  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dd81b-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd81b-116">See Also</span></span>  
 <span data-ttu-id="dd81b-117">[Types de requêtes pris en charge &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dd81b-117">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="dd81b-118">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="dd81b-118">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
