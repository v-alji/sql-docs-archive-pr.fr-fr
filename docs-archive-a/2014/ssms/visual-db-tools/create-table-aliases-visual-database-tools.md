---
title: Créer des alias de tables (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table aliases [SQL Server]
- aliases [SQL Server], tables
ms.assetid: 49e61e85-8abf-4ca7-8c70-7e9f8f1078bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f9e6269fe6e24e8d98922094e799fbf4b5af584
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610946"
---
# <a name="create-table-aliases-visual-database-tools"></a><span data-ttu-id="b80e0-102">Créer des alias de tables (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b80e0-102">Create Table Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="b80e0-103">Les alias servent à faciliter les travaux impliquant des manipulations de noms de tables.</span><span class="sxs-lookup"><span data-stu-id="b80e0-103">Aliases can make it easier to work with table names.</span></span> <span data-ttu-id="b80e0-104">L'emploi d'alias s'avère utile dans les circonstances suivantes :</span><span class="sxs-lookup"><span data-stu-id="b80e0-104">Using aliases is helpful when:</span></span>  
  
-   <span data-ttu-id="b80e0-105">Vous souhaitez raccourcir et simplifier la lecture de l’instruction dans le [volet SQL](visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="b80e0-105">You want to make the statement in the [SQL Pane](visual-database-tools.md) shorter and easier to read.</span></span>  
  
-   <span data-ttu-id="b80e0-106">Vous vous référez souvent au nom de la table dans votre requête (lors de la qualification des noms de colonnes) et vous souhaitez être sûr que vous ne dépassez pas une longueur de caractère spécifique dans votre requête</span><span class="sxs-lookup"><span data-stu-id="b80e0-106">You refer to the table name often in your query - such as in qualifying column names - and want to be sure you stay within a specific character-length limit for your query.</span></span> <span data-ttu-id="b80e0-107">(certaines bases de données imposent une longueur maximale aux requêtes).</span><span class="sxs-lookup"><span data-stu-id="b80e0-107">(Some databases impose a maximum length for queries.)</span></span>  
  
-   <span data-ttu-id="b80e0-108">Vous utilisez plusieurs instances de la même table (dans une jointure réflexive, par exemple) et vous avez besoin d'une méthode vous permettant de vous référer à l'une ou l'autre instance.</span><span class="sxs-lookup"><span data-stu-id="b80e0-108">You are working with multiple instances of the same table (such as in a self-join) and need a way to refer to one instance or the other.</span></span>  
  
 <span data-ttu-id="b80e0-109">Vous pouvez, par exemple, créer un alias `"e"` pour le nom de la table `employee`_`information`, puis vous référer à cette table sous la forme `"e"` dans le reste de la requête.</span><span class="sxs-lookup"><span data-stu-id="b80e0-109">For example, you can create an alias `"e"` for a table name `employee`_`information`, and then refer to the table as `"e"` throughout the rest of the query.</span></span>  
  
### <a name="to-create-an-alias-for-a-table-or-table-valued-object"></a><span data-ttu-id="b80e0-110">Pour créer un alias pour une table ou un objet table</span><span class="sxs-lookup"><span data-stu-id="b80e0-110">To create an alias for a table or table-valued object</span></span>  
  
1.  <span data-ttu-id="b80e0-111">Ajoutez la table ou l'objet table à votre requête.</span><span class="sxs-lookup"><span data-stu-id="b80e0-111">Add the table or table-valued object to your query.</span></span>  
  
2.  <span data-ttu-id="b80e0-112">Dans le **volet Schéma**, cliquez avec le bouton droit sur l’objet pour lequel vous souhaitez créer un alias, puis sélectionnez **Propriétés** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="b80e0-112">In the **Diagram Pane**, right-click the object for which you want to create an alias, then select **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="b80e0-113">Dans la fenêtre **Propriétés** , entrez l’alias dans le champ **Alias** .</span><span class="sxs-lookup"><span data-stu-id="b80e0-113">In the **Properties** window, enter the alias in the **Alias** field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80e0-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b80e0-114">See Also</span></span>  
 <span data-ttu-id="b80e0-115">[Ajouter des tables à des requêtes &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b80e0-115">[Add Tables to Queries &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="b80e0-116">[Trier et regrouper les résultats des requêtes &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b80e0-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="b80e0-117">[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b80e0-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b80e0-118">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b80e0-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
