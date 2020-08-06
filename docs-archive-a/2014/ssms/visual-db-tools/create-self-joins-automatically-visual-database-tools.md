---
title: Créer automatiquement des jointures réflexives (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- self-joins
- joins [SQL Server], self
ms.assetid: f9ec90e8-3aad-415c-a5c4-8dfa9540e37f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a428a44d33b5990e849772b43841df472ca7f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600447"
---
# <a name="create-self-joins-automatically-visual-database-tools"></a><span data-ttu-id="9b057-102">Créer automatiquement des jointures réflexives (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9b057-102">Create Self-Joins Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="9b057-103">Si une table possède une relation réflexive dans la base de données, vous pouvez la joindre à elle-même de façon automatique.</span><span class="sxs-lookup"><span data-stu-id="9b057-103">If a table has a reflexive relationship in the database, you can join it to itself automatically.</span></span>  
  
### <a name="to-create-a-self-join-automatically"></a><span data-ttu-id="9b057-104">Pour créer automatiquement une jointure réflexive</span><span class="sxs-lookup"><span data-stu-id="9b057-104">To create a self-join automatically</span></span>  
  
1.  <span data-ttu-id="9b057-105">Ajoutez la table que vous souhaitez utiliser au [volet Schéma](visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="9b057-105">Add to the [Diagram pane](visual-database-tools.md) the table you want to work with.</span></span>  
  
2.  <span data-ttu-id="9b057-106">Ajoutez de nouveau la même table, afin que le volet Schéma affiche deux fois la même table.</span><span class="sxs-lookup"><span data-stu-id="9b057-106">Add the same table again, so that the Diagram pane shows the same table twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="9b057-107">Le [Concepteur de requêtes et de vues](query-and-view-designer-tools-visual-database-tools.md) assigne un alias à la seconde instance en ajoutant un numéro séquentiel au nom de la table.</span><span class="sxs-lookup"><span data-stu-id="9b057-107">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="9b057-108">Par ailleurs, il crée une ligne de jointure entre les deux rectangles qui représentent les deux façons différentes dont la table intervient dans la requête.</span><span class="sxs-lookup"><span data-stu-id="9b057-108">In addition, the Query and View Designer creates a join line between the two rectangles representing the two different ways the table participates in the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b057-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b057-109">See Also</span></span>  
 [<span data-ttu-id="9b057-110">Interroger avec des jointures &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9b057-110">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
