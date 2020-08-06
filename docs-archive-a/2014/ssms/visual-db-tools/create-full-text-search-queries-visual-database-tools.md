---
title: Créer des requêtes de recherche en texte intégral (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CONTAINS predicate (Transact-SQL)
- queries [full-text search], creating
- full-text queries [SQL Server], creating
ms.assetid: 537fa556-390e-4c88-9b8e-679848d94abc
author: stevestein
ms.author: sstein
ms.openlocfilehash: f84ab465da0a1b7ac1da1211de1d5199fd28ee95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699120"
---
# <a name="create-full-text-search-queries-visual-database-tools"></a><span data-ttu-id="90abc-102">Créer des requêtes de recherche en texte intégral (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="90abc-102">Create Full-Text Search Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="90abc-103">La recherche en texte intégral utilise le prédicat CONTAINS pour localiser les lignes contenant le texte spécifié dans une colonne donnée.</span><span class="sxs-lookup"><span data-stu-id="90abc-103">Full-text searches use the CONTAINS predicate to locate rows that have specified text in a given column.</span></span> <span data-ttu-id="90abc-104">Les recherches en texte intégral ne sont possibles que sur les colonnes possédant des index de texte intégral actifs.</span><span class="sxs-lookup"><span data-stu-id="90abc-104">Full-Text searches are only possible on columns that have active full-text indexes.</span></span> <span data-ttu-id="90abc-105">Si vous tentez d'utiliser la clause CONTAINS sur une colonne qui ne possède pas d'index de texte intégral actuellement actif, une erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="90abc-105">If you attempt to use the CONTAINS clause on a column that does not have a currently active full-text index, you will receive an error.</span></span> <span data-ttu-id="90abc-106">Pour plus d’informations sur les index de recherche en texte intégral et la clause CONTAINs, consultez [recherche en texte intégral](../../relational-databases/search/full-text-search.md) et [contient &#40;&#41;Transact-SQL ](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="90abc-106">For more information on full-text indexes and the CONTAINS clause, see [Full-Text Search](../../relational-databases/search/full-text-search.md) and [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
### <a name="to-create-a-full-text-search-query"></a><span data-ttu-id="90abc-107">Pour créer une requête de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="90abc-107">To create a full-text search query</span></span>  
  
1.  <span data-ttu-id="90abc-108">Ouvrez une requête dans l'Explorateur de solutions ou créez-en une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="90abc-108">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="90abc-109">Dans la clause WHERE de votre requête, utilisez la fonction CONTAINS pour rechercher une colonne de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="90abc-109">In the WHERE clause of your query, use the CONTAINS function to search a full-text column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90abc-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90abc-110">See Also</span></span>  
 <span data-ttu-id="90abc-111">[Types de requêtes pris en charge &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="90abc-111">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="90abc-112">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="90abc-112">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="90abc-113">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="90abc-113">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
