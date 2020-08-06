---
title: Supprimer des jointures (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- removing joins
- joins [SQL Server], removing
- deleting joins
ms.assetid: ccc212a1-fd13-48d6-85e5-5ff310c34bbd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b037e317b629671f6ec5ea1fa90edfca6fafa627
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599725"
---
# <a name="remove-joins-visual-database-tools"></a><span data-ttu-id="7e438-102">Supprimer des jointures (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7e438-102">Remove Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="7e438-103">Si vous ne souhaitez pas que les tables soient liées par une jointure interne ou externe, vous pouvez supprimer celle-ci.</span><span class="sxs-lookup"><span data-stu-id="7e438-103">If you do not want tables to be joined via an inner join or an outer join, you can remove the join between them.</span></span> <span data-ttu-id="7e438-104">Vous pouvez par exemple supprimer une jointure créée automatiquement entre deux tables par le [Concepteur de requêtes et de vues](visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="7e438-104">For example, you might remove a join that the [Query and View Designer](visual-database-tools.md) has been created automatically between two tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e438-105">La suppression d'une jointure n'a aucune répercussion sur la relation sous-jacente existant dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="7e438-105">Removing a join from a query does not alter the underlying relationship in the database.</span></span>  
  
 <span data-ttu-id="7e438-106">Si deux tables jointes font partie de votre requête et que vous supprimez toutes les conditions de jointure entre elles, la requête obtenue devient le produit des deux tables, en d’autres termes une instruction CROSS JOIN.</span><span class="sxs-lookup"><span data-stu-id="7e438-106">If two joined tables are part of your query and you remove all join conditions between them, the resulting query becomes the product of both tables - that is, it becomes a CROSS JOIN.</span></span>  
  
### <a name="to-remove-a-join"></a><span data-ttu-id="7e438-107">Pour supprimer une jointure</span><span class="sxs-lookup"><span data-stu-id="7e438-107">To remove a join</span></span>  
  
-   <span data-ttu-id="7e438-108">Dans le [volet Schéma](diagram-pane-visual-database-tools.md), sélectionnez la ligne de jointure à supprimer, puis appuyez sur la touche Suppr.</span><span class="sxs-lookup"><span data-stu-id="7e438-108">In the [Diagram pane](diagram-pane-visual-database-tools.md), select the join line for the join to remove, and then press the DELETE key.</span></span> <span data-ttu-id="7e438-109">Il est possible de sélectionner et supprimer plusieurs lignes de jointure à la fois.</span><span class="sxs-lookup"><span data-stu-id="7e438-109">You can select and delete multiple join lines at one time.</span></span>  
  
 <span data-ttu-id="7e438-110">Le Concepteur de requêtes et de vues supprime la ligne de jointure et modifie l’instruction dans le [volet SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7e438-110">The Query and View Designer removes the join line and alters the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e438-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e438-111">See Also</span></span>  
 <span data-ttu-id="7e438-112">[Joindre automatiquement des tables &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7e438-112">[Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span></span>  
 <span data-ttu-id="7e438-113">[Joindre des tables manuellement &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7e438-113">[Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7e438-114">Interroger avec des jointures &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7e438-114">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
