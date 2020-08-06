---
title: Créer des requêtes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], creating
ms.assetid: 696a080d-848f-44d3-a918-e29bafaab85a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52392adff03b27e1c4c19f354bc62c350cccf17a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600449"
---
# <a name="create-queries-visual-database-tools"></a><span data-ttu-id="a9a0c-102">Créer des requêtes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a9a0c-102">Create Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="a9a0c-103">Les requêtes vous permettent de récupérer des données des tables et vues contenues dans votre base de données.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-103">Queries allow you to retrieve data from the tables and views in your database.</span></span> <span data-ttu-id="a9a0c-104">Vous pouvez créer et utiliser des requêtes dans le **Concepteur de requêtes et de vues**, qui se compose de quatre volets : le [volet Schéma](visual-database-tools.md), le [volet SQL](sql-pane-visual-database-tools.md), le [volet Critères](criteria-pane-visual-database-tools.md)et le [volet Résultats](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a9a0c-104">You create and work with queries in **Query and View Designer**, which is composed of four panes: the [Diagram Pane](visual-database-tools.md), the [SQL Pane](sql-pane-visual-database-tools.md), the [Criteria Pane](criteria-pane-visual-database-tools.md), and the [Results Pane](results-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-a-new-query"></a><span data-ttu-id="a9a0c-105">Pour créer une requête</span><span class="sxs-lookup"><span data-stu-id="a9a0c-105">To create a new query</span></span>  
  
1.  <span data-ttu-id="a9a0c-106">Dans **l’Explorateur d’objets**, développez le nœud **Tables** de la base de données à interroger.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-106">In **Object Explorer**, expand the **Tables** node for the database you want to query.</span></span> <span data-ttu-id="a9a0c-107">Cliquez avec le bouton droit sur la table à valider, puis cliquez sur **Ouvrir la table**.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-107">Right-click the table you want to query and click **Open Table**.</span></span>  
  
2.  <span data-ttu-id="a9a0c-108">Pour ajouter des tables supplémentaires à la requête, dans le menu Concepteur de requêtes, sélectionnez **Ajouter une table**.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-108">To add more tables to the query, on the Query Designer menu, select **Add Table**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9a0c-109">Si les volets **Schéma**, **SQL**, **Critères**ou **Résultats** ne sont pas affichés, pointez sur **Volet** dans le menu Concepteur de requêtes et cliquez sur le volet que vous souhaitez ouvrir.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-109">If you do not see the **Diagram**, **SQL**, **Criteria**, or **Results** panes, from the Query Designer menu, point to **Pane** and click the pane you want to open.</span></span>  
  
3.  <span data-ttu-id="a9a0c-110">Dans la boîte de dialogue **Ajouter une table** , sélectionnez les tables que vous souhaitez interroger et cliquez sur **Ajouter** pour chacune d’elles.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-110">In the **Add Table** dialog box, select the tables you want to query and click **Add** for each one.</span></span>  
  
4.  <span data-ttu-id="a9a0c-111">Une fois que vous avez ajouté toutes les tables à interroger, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-111">Once you have added all the tables you want to query, click **Close**.</span></span>  
  
     <span data-ttu-id="a9a0c-112">Pour ajouter davantage de tables ultérieurement, cliquez avec le bouton droit sur l’espace ouvert dans le volet **Schéma** et cliquez sur **Ajouter une table**dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-112">To add more tables later, right-click the open space in the **Diagram** pane and from the shortcut menu click **Add Table**.</span></span>  
  
5.  <span data-ttu-id="a9a0c-113">Dans le **volet Schéma**, cochez les cases situées à côté des objets table de chaque colonne que vous souhaitez interroger.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-113">In the **Diagram Pane**, check the boxes in the table-valued objects for each column you want to query.</span></span>  
  
6.  <span data-ttu-id="a9a0c-114">Dans le menu Concepteur de requêtes, choisissez **Exécuter SQL** pour exécuter votre requête.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-114">From the Query Designer menu, choose **Execute SQL** to run your query.</span></span>  
  
 <span data-ttu-id="a9a0c-115">Pour affiner davantage votre requête, vous pouvez modifier le code SQL dans le **Volet SQL** ou choisir des options telles que l’ordre de tri et les alias de colonne dans le **Volet Critères**.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-115">To further refine your query, you can change the SQL code in the **SQL Pane** or choose options such as sort order and column aliases in the **Criteria Pane.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a0c-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a9a0c-116">See Also</span></span>  
 <span data-ttu-id="a9a0c-117">[Enregistrer des requêtes &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a9a0c-117">[Save Queries &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a9a0c-118">[Types de requêtes &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a9a0c-118">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a9a0c-119">[Spécifier les critères de recherche &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a9a0c-119">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a9a0c-120">[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a9a0c-120">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a9a0c-121">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a9a0c-121">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
