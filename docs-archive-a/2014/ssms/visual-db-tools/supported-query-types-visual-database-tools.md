---
title: Types de requêtes pris en charge (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Delete query
- queries [SQL Server], types
- Update query
- Query Designer [SQL Server], query types
- Criteria pane
- Insert Values query
- Select query
- Make Table query
- Insert Results query
- Diagram pane [Visual Database Tools]
- View Designer, query types
ms.assetid: 72b9116c-c128-4078-a78d-257a2955a3f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b00b7018fc6d0b631696811bd1870e09842b4162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704615"
---
# <a name="supported-query-types-visual-database-tools"></a><span data-ttu-id="924c5-102">Types de requêtes pris en charge (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="924c5-102">Supported Query Types (Visual Database Tools)</span></span>
  <span data-ttu-id="924c5-103">Voici les types de requêtes pouvant être créés dans les volets Schéma et Critères (volets graphiques) du [Concepteur de requêtes et de vues](visual-database-tools.md):</span><span class="sxs-lookup"><span data-stu-id="924c5-103">You can create the following types of queries in the Diagram and Criteria panes (the graphical panes) of the [Query and View Designer](visual-database-tools.md):</span></span>  
  
-   <span data-ttu-id="924c5-104">**Requête Select** Extrait des données d’une ou de plusieurs tables ou vues.</span><span class="sxs-lookup"><span data-stu-id="924c5-104">**Select query** Retrieves data from one or more tables or views.</span></span> <span data-ttu-id="924c5-105">Ce type de requête crée une instruction SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="924c5-105">This type of query creates an SQL SELECT statement.</span></span>  
  
-   <span data-ttu-id="924c5-106">**Insert Results** Créé des lignes d’une table dans une autre, ou dans la même table en tant que nouvelles lignes.</span><span class="sxs-lookup"><span data-stu-id="924c5-106">**Insert Results** Creates new rows by copying existing rows from one table into another, or into the same table as new rows.</span></span> <span data-ttu-id="924c5-107">Ce type de requête crée une instruction SQL INSERT INTO...SELECT.</span><span class="sxs-lookup"><span data-stu-id="924c5-107">This type of query creates an SQL INSERT INTO...SELECT statement.</span></span>  
  
-   <span data-ttu-id="924c5-108">**Insert Values** Crée une ligne et insère des valeurs dans des colonnes spécifiées.</span><span class="sxs-lookup"><span data-stu-id="924c5-108">**Insert Values** Creates a new row and inserts values into specified columns.</span></span> <span data-ttu-id="924c5-109">Ce type de requête crée une instruction SQL INSERT INTO...VALUES.</span><span class="sxs-lookup"><span data-stu-id="924c5-109">This type of query creates an SQL INSERT INTO...VALUES statement.</span></span>  
  
-   <span data-ttu-id="924c5-110">**Requête Update** Modifie les valeurs de colonnes individuelles dans une ou plusieurs lignes existant dans une table.</span><span class="sxs-lookup"><span data-stu-id="924c5-110">**Update query** Changes the values of individual columns in one or more existing rows in a table.</span></span> <span data-ttu-id="924c5-111">Ce type de requête crée une instruction SQL UPDATE...SET.</span><span class="sxs-lookup"><span data-stu-id="924c5-111">This type of query creates an SQL UPDATE...SET statement.</span></span>  
  
-   <span data-ttu-id="924c5-112">**Requête Delete** Supprime une ou plusieurs lignes d’une table.</span><span class="sxs-lookup"><span data-stu-id="924c5-112">**Delete query** Removes one or more rows from a table.</span></span> <span data-ttu-id="924c5-113">Ce type de requête crée une instruction SQL DELETE.</span><span class="sxs-lookup"><span data-stu-id="924c5-113">This type of query creates an SQL DELETE statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="924c5-114">Une requête Delete supprime de la table des lignes entières.</span><span class="sxs-lookup"><span data-stu-id="924c5-114">A Delete query removes entire rows from the table.</span></span> <span data-ttu-id="924c5-115">Pour supprimer des valeurs dans des colonnes de données individuelles, utilisez une requête Update.</span><span class="sxs-lookup"><span data-stu-id="924c5-115">If you want to delete values from individual data columns, use an Update query.</span></span>  
  
-   <span data-ttu-id="924c5-116">**Requête Make Table** Copie les résultats d’une requête dans une nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="924c5-116">**Make Table query** Creates a new table and creates rows in it by copying the results of a query into it.</span></span> <span data-ttu-id="924c5-117">Ce type de requête crée une instruction SQL DELETE...INTO.</span><span class="sxs-lookup"><span data-stu-id="924c5-117">This type of query creates an SQL SELECT...INTO statement.</span></span>  
  
 <span data-ttu-id="924c5-118">Pour créer des requêtes, vous pouvez utiliser les volets graphiques, mais aussi entrer n'importe quelle instruction SQL dans le volet SQL, par exemple pour créer une requête Union.</span><span class="sxs-lookup"><span data-stu-id="924c5-118">In addition to the queries you can create using the graphical panes, you can enter any SQL statement into the SQL pane, such as Union queries.</span></span>  
  
 <span data-ttu-id="924c5-119">Si les instructions SQL que vous utilisez pour créer la requête ne peuvent pas être représentées dans les volets graphiques, le Concepteur de requêtes et de vues estompe ces volets pour indiquer qu'ils ne reflètent pas la requête en cours de création.</span><span class="sxs-lookup"><span data-stu-id="924c5-119">When you create queries using SQL statements that cannot be represented in the graphical panes, the Query and View Designer dims those panes to indicate that they do not reflect the query you are creating.</span></span> <span data-ttu-id="924c5-120">Cependant, les volets estompés restent actifs et, dans de nombreux cas, il est possible d'apporter des modifications à la requête dans ces volets.</span><span class="sxs-lookup"><span data-stu-id="924c5-120">However, the dimmed panes are still active and, in many cases, you can make changes to the query in those panes.</span></span> <span data-ttu-id="924c5-121">Si les modifications que vous apportez donnent lieu à une requête que les volets graphiques peuvent représenter, ces derniers ne sont plus estompés.</span><span class="sxs-lookup"><span data-stu-id="924c5-121">If the changes you make result in a query that can be represented in the graphical panes, those panes are no longer dimmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="924c5-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="924c5-122">See Also</span></span>  
 <span data-ttu-id="924c5-123">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="924c5-123">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="924c5-124">Types de requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="924c5-124">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
