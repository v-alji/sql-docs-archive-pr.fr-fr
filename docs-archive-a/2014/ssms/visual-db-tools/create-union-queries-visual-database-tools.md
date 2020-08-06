---
title: Créer des requêtes UNION (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- UNION queries
- Select query
- combining query results
- merged SELECT query [SQL Server]
ms.assetid: b5aafb1d-e4ed-4922-b790-56abc5ec551a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3c10f39c3e44844c4ec8a6a2328c41ea2de350d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610945"
---
# <a name="create-union-queries-visual-database-tools"></a><span data-ttu-id="e2d5e-102">Créer des requêtes UNION (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="e2d5e-102">Create UNION Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="e2d5e-103">Le mot clé UNION vous permet d'inclure les résultats de deux instructions SELECT dans une table résultante.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-103">The UNION keyword enables you to include the results of two SELECT statements in one resulting table.</span></span> <span data-ttu-id="e2d5e-104">Toutes les lignes retournées par l'une ou l'autre instruction SELECT sont mixées dans le résultat de l'expression UNION.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-104">All rows returned from either SELECT statement are combined into the result of the UNION expression.</span></span> <span data-ttu-id="e2d5e-105">Pour obtenir des exemples, consultez [Select exemples &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-examples-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e2d5e-105">For examples, see [SELECT Examples &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-examples-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2d5e-106">Le volet Schéma ne peut afficher qu'une clause SELECT.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-106">The Diagram pane can only display one SELECT clause.</span></span> <span data-ttu-id="e2d5e-107">Par conséquent, lorsque vous utilisez une requête UNION, le Concepteur de requêtes masque le volet Table Operations.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-107">Therefore, when you are working with a UNION query, Query Designer hides the Table Operations pane.</span></span>  
  
### <a name="to-create-a-merged-select-query"></a><span data-ttu-id="e2d5e-108">Pour créer une requête SELECT fusionnée</span><span class="sxs-lookup"><span data-stu-id="e2d5e-108">To create a Merged SELECT query</span></span>  
  
1.  <span data-ttu-id="e2d5e-109">Ouvrez une requête ou créez-en une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-109">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="e2d5e-110">Dans le volet SQL, tapez une expression UNION valide.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-110">In the SQL pane, type a valid UNION expression.</span></span>  
  
     <span data-ttu-id="e2d5e-111">L'exemple suivant est une expression UNION valide.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-111">The following example is a valid UNION expression.</span></span>  
  
    ```  
    SELECT ProductModelID, Name  
    FROM Production.ProductModel  
    UNION  
    SELECT ProductModelID, Name   
    FROM dbo.Gloves;  
    ```  
  
3.  <span data-ttu-id="e2d5e-112">Dans le menu **Concepteur de requêtes** , cliquez sur **Exécuter SQL** pour exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-112">On the **Query Designer** menu, click **Execute SQL** to run the query.</span></span>  
  
     <span data-ttu-id="e2d5e-113">Votre requête UNION est à présent mise en forme par le Concepteur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-113">Your UNION query is now formatted by Query Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d5e-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2d5e-114">See Also</span></span>  
 <span data-ttu-id="e2d5e-115">[Types de requêtes pris en charge &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e2d5e-115">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="e2d5e-116">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e2d5e-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="e2d5e-117">[Effectuer des opérations de base avec les requêtes &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e2d5e-117">[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e2d5e-118">UNION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2d5e-118">UNION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/set-operators-union-transact-sql)  
  
  
