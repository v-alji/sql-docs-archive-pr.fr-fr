---
title: Résumé des résultats d’une requête (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- queries [SQL Server], results
- aggregate queries [SQL Server]
ms.assetid: c9e15350-ed57-4d95-814d-815fbebfd86b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08713be2d4439e520df07ec5efd6cb761a78a994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704620"
---
# <a name="summarize-query-results-visual-database-tools"></a><span data-ttu-id="75ef1-102">Résumé des résultats d'une requête (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="75ef1-102">Summarize Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="75ef1-103">Certains principes logiques s'appliquent à la création de requêtes d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="75ef1-103">When you create aggregate queries, certain logical principles apply.</span></span> <span data-ttu-id="75ef1-104">Par exemple, il est impossible d'afficher le contenu de lignes individuelles dans une requête de synthèse.</span><span class="sxs-lookup"><span data-stu-id="75ef1-104">For example, you cannot display the contents of individual rows in a summary query.</span></span> <span data-ttu-id="75ef1-105">Le Concepteur de requêtes et de vues vous aide à respecter ces principes dans le comportement du [volet Schéma](visual-database-tools.md) et du [volet Critères](criteria-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="75ef1-105">The Query and View Designer helps you comply with these principles in the way the [Diagram pane](visual-database-tools.md) and [Criteria pane](criteria-pane-visual-database-tools.md) behave.</span></span>  
  
 <span data-ttu-id="75ef1-106">Une bonne compréhension des principes des requêtes d'agrégation et du comportement du Concepteur de requêtes et de vues permet de créer des requêtes correctes du point de vue logique.</span><span class="sxs-lookup"><span data-stu-id="75ef1-106">By understanding the principles of aggregate queries and the Query and View Designer's behavior, you can create logically correct aggregate queries.</span></span> <span data-ttu-id="75ef1-107">Le principe déterminant est que les requêtes d'agrégation ne peuvent donner que des informations de synthèse.</span><span class="sxs-lookup"><span data-stu-id="75ef1-107">The overriding principle is that aggregate queries can result only in summary information.</span></span> <span data-ttu-id="75ef1-108">C'est pourquoi la plupart des principes présentés plus loin décrivent les différentes méthodes permettant de référencer des colonnes de données individuelles dans une requête d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="75ef1-108">Thus, most of the principles that follow describe the ways that you can reference individual data columns within an aggregate query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75ef1-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="75ef1-109">In This Section</span></span>  
 [<span data-ttu-id="75ef1-110">Utiliser des colonnes dans des requêtes d'agrégation &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="75ef1-110">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](work-with-columns-in-aggregate-queries-visual-database-tools.md)  
 <span data-ttu-id="75ef1-111">Décrit les concepts relatifs au regroupement et à la synthèse de colonnes à l'aide des clauses GROUP BY, WHERE et HAVING.</span><span class="sxs-lookup"><span data-stu-id="75ef1-111">Describes concepts about grouping and summarizing columns with the GROUP BY, WHERE, and HAVING clauses.</span></span>  
  
 [<span data-ttu-id="75ef1-112">Compter les lignes d'une table &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="75ef1-112">Count Rows in a Table &#40;Visual Database Tools&#41;</span></span>](count-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="75ef1-113">Fournit la procédure de comptage du nombre de lignes dans une table ou du nombre de lignes dans une table qui répondent à un jeu de critères.</span><span class="sxs-lookup"><span data-stu-id="75ef1-113">Provides steps for counting the number of rows in a table or the number of rows in a table that meet a set of criteria.</span></span>  
  
 [<span data-ttu-id="75ef1-114">Synthétiser ou regrouper des valeurs de toutes les lignes d'une table &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="75ef1-114">Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="75ef1-115">Fournit la procédure de synthèse de toutes les lignes plutôt que d'un jeu de lignes groupées.</span><span class="sxs-lookup"><span data-stu-id="75ef1-115">Provides steps for summarizing all rows rather than for a set of grouped rows.</span></span>  
  
 [<span data-ttu-id="75ef1-116">Synthétiser ou regrouper des valeurs à l'aide d'expressions personnalisées &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="75ef1-116">Summarize or Aggregate Values Using Custom Expressions &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md)  
 <span data-ttu-id="75ef1-117">Fournit la procédure d'utilisation d'expressions pour synthétiser ou regrouper plutôt que d'utiliser des clauses prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="75ef1-117">Provides steps for using expressions to summarize or aggregate rather than using the predefined clauses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="75ef1-118">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="75ef1-118">Related Sections</span></span>  
 [<span data-ttu-id="75ef1-119">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="75ef1-119">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
 <span data-ttu-id="75ef1-120">Fournit des liens vers des rubriques qui décrivent l'utilisation du Concepteur de requêtes et de vues.</span><span class="sxs-lookup"><span data-stu-id="75ef1-120">Provides links to topics covering how to use the Query and View Designer.</span></span>  
  
  
