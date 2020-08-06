---
title: Volet SQL (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Query Designer [SQL Server], SQL pane
- View Designer, SQL pane
- SQL pane [Visual Database Tools]
ms.assetid: dbabab18-0614-415b-a2ef-9bcd0d320d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a87ec1d5517852fefb152e0ec7b3165fa32988b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695079"
---
# <a name="sql-pane-visual-database-tools"></a><span data-ttu-id="0e36c-102">Volet SQL (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0e36c-102">SQL Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="0e36c-103">Vous pouvez utiliser le volet SQL pour créer votre propre instruction SQL, ou utiliser le volet Critères et le volet Schéma pour créer l'instruction, auquel cas les instructions SQL sont créées dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="0e36c-103">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="0e36c-104">Pendant la génération de la requête, le volet SQL se met automatiquement à jour et se reformate pour une lecture plus aisée.</span><span class="sxs-lookup"><span data-stu-id="0e36c-104">As you build your query, the SQL pane automatically updates and reformats for easy readability.</span></span>  
  
 <span data-ttu-id="0e36c-105">Pour ouvrir le volet SQL, ouvrez d’abord le Concepteur de requêtes et de vues (quand un objet de base de données est sélectionné dans l’Explorateur de serveurs, cliquez sur **Nouvelle requête** dans le menu **Base de données**).</span><span class="sxs-lookup"><span data-stu-id="0e36c-105">To open the SQL pane, first open Query and View Designer (with a database object selected in Server Explorer, from the **Database** menu, click **New Query**).</span></span> <span data-ttu-id="0e36c-106">Ensuite, dans le menu **Concepteur de requêtes** , pointez sur **Volet** et cliquez sur **SQL**.</span><span class="sxs-lookup"><span data-stu-id="0e36c-106">Then from the **Query Designer** menu point to **Pane** and click **SQL**.</span></span>  
  
 <span data-ttu-id="0e36c-107">Dans le volet SQL, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="0e36c-107">In the SQL pane you can:</span></span>  
  
-   <span data-ttu-id="0e36c-108">entrer des instructions SQL pour créer des requêtes ;</span><span class="sxs-lookup"><span data-stu-id="0e36c-108">Create new queries by entering SQL statements.</span></span>  
  
-   <span data-ttu-id="0e36c-109">modifier l'instruction SQL créée par le Concepteur de requêtes et de vues sur la base des paramètres spécifiés dans les volets Schéma et Critères ;</span><span class="sxs-lookup"><span data-stu-id="0e36c-109">Modify the SQL statement created by the Query and View Designer based on settings you make in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="0e36c-110">entrer des instructions tirant parti de fonctionnalités spécifiques de la base de données que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="0e36c-110">Enter statements that take advantage of features specific to the database you are using.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e36c-111">Vous devez connaître les règles d'identification des objets de la base de données que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="0e36c-111">Be sure you know the rules for identifying database objects in the database you are using.</span></span> <span data-ttu-id="0e36c-112">Pour plus d'informations, consultez la documentation du système de gestion de votre base de données.</span><span class="sxs-lookup"><span data-stu-id="0e36c-112">For details, see the documentation for your database management system.</span></span>  
  
## <a name="statements-in-the-sql-pane"></a><span data-ttu-id="0e36c-113">Instructions dans le volet SQL</span><span class="sxs-lookup"><span data-stu-id="0e36c-113">Statements in the SQL Pane</span></span>  
 <span data-ttu-id="0e36c-114">Il est possible de modifier la requête en cours directement dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="0e36c-114">You can edit the current query directly in the SQL pane.</span></span> <span data-ttu-id="0e36c-115">Si vous allez dans un autre volet, le Concepteur de requêtes et de vues formate automatiquement l'instruction, puis modifie les volets Schéma et Critères en conséquence.</span><span class="sxs-lookup"><span data-stu-id="0e36c-115">When you move to another pane, the Query and View Designer automatically formats your statement, and then changes the Diagram and Criteria panes to match your statement.</span></span>  
  
 <span data-ttu-id="0e36c-116">Si votre instruction ne peut pas être représentée dans les volets Schéma et Critères alors que ces derniers sont visibles, le Concepteur de requêtes et de vues affiche une erreur et vous propose de choisir entre deux actions :</span><span class="sxs-lookup"><span data-stu-id="0e36c-116">If your statement cannot be represented in the Diagram and Criteria panes, and if those panes are visible, Query and View Designer displays an error and then offers you two choices:</span></span>  
  
-   <span data-ttu-id="0e36c-117">ignorer le fait que l'instruction ne peut pas être représentée dans les volets Schéma et Critères ;</span><span class="sxs-lookup"><span data-stu-id="0e36c-117">Ignore that the statement can not be represented in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="0e36c-118">annuler la modification qui ne peut pas être représentée et revenir à la version précédente de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="0e36c-118">Undo the change that can not be represented and revert to the most recent version of the SQL statement.</span></span>  
  
 <span data-ttu-id="0e36c-119">Si vous choisissez d'ignorer le fait que l'instruction ne peut pas être représentée dans les volets Schéma et Critères, le Concepteur de requêtes et de vues estompe les autres volets pour indiquer qu'ils ne reflètent plus le contenu du volet SQL.</span><span class="sxs-lookup"><span data-stu-id="0e36c-119">If you choose to ignore that the statement can not be represented in the Diagram and Criteria panes, the Query and View Designer dims the other panes to indicate that they no longer reflect the contents of the SQL pane.</span></span>  
  
 <span data-ttu-id="0e36c-120">Vous pouvez continuer à modifier l'instruction et à l'exécuter, comme vous le feriez avec n'importe quelle instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="0e36c-120">You can continue to edit the statement and execute it as you would any SQL statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e36c-121">Si vous entrez une instruction SQL, puis apportez d'autres modifications à la requête dans les volets Schéma et Critères, le Concepteur de requêtes et de vues régénère et réaffiche l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="0e36c-121">If you enter an SQL statement, but then make further changes to the query by changing the Diagram and Criteria panes, the Query and View Designer rebuilds and redisplays the SQL statement.</span></span> <span data-ttu-id="0e36c-122">Dans certains cas, l'instruction SQL obtenue a une construction différente de celle que vous aviez entrée à l'origine (mais elle donne toujours les mêmes résultats).</span><span class="sxs-lookup"><span data-stu-id="0e36c-122">In some cases, this action results in an SQL statement that is constructed differently from the one you originally entered (though it will always yield the same results).</span></span> <span data-ttu-id="0e36c-123">Vous constaterez très vraisemblablement cette différence si vous utilisez des conditions de recherche impliquant plusieurs clauses liées par AND et OR.</span><span class="sxs-lookup"><span data-stu-id="0e36c-123">This difference is particularly likely when you are working with search conditions that involve several clauses linked with AND and OR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e36c-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e36c-124">See Also</span></span>  
 <span data-ttu-id="0e36c-125">[Créer des requêtes &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0e36c-125">[Create Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="0e36c-126">[Exécuter des requêtes &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0e36c-126">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0e36c-127">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0e36c-127">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0e36c-128">[Volet Schéma &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0e36c-128">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0e36c-129">[Volet critères &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0e36c-129">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0e36c-130">Volet Résultats &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0e36c-130">Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
