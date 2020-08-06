---
title: Joindre automatiquement des tables (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- joins [SQL Server], creating
- joins [SQL Server], automatic
ms.assetid: f152af82-bcb6-49ca-af19-48cdb7fc9ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: d05100f801d972759c1b5c105814f5cdbdccf84f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695120"
---
# <a name="join-tables-automatically-visual-database-tools"></a><span data-ttu-id="c1f82-102">Joindre automatiquement des tables (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c1f82-102">Join Tables Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="c1f82-103">Quand vous ajoutez plusieurs tables à une requête, le [Concepteur de requêtes et de vues](visual-database-tools.md) tente de déterminer si elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="c1f82-103">When you add two or more tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to determine if they are related.</span></span> <span data-ttu-id="c1f82-104">Si c'est le cas, le Concepteur de requêtes et de vues place automatiquement des lignes de jointure entre les rectangles représentant des tables ou des objets de type table.</span><span class="sxs-lookup"><span data-stu-id="c1f82-104">If they are, the Query and View Designer automatically puts join lines between the rectangles representing the tables or table-structured objects.</span></span>  
  
 <span data-ttu-id="c1f82-105">Le Concepteur de requêtes et de vues identifie des tables comme étant jointes dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="c1f82-105">The Query and View Designer will recognize tables as joined if:</span></span>  
  
-   <span data-ttu-id="c1f82-106">La base de données contient des informations qui spécifient que les tables sont liées.</span><span class="sxs-lookup"><span data-stu-id="c1f82-106">The database contains information that specifies that the tables are related.</span></span>  
  
-   <span data-ttu-id="c1f82-107">Deux colonnes, une dans chaque table, ont les mêmes nom et type de données.</span><span class="sxs-lookup"><span data-stu-id="c1f82-107">If two columns, one in each table, have the same name and data type.</span></span> <span data-ttu-id="c1f82-108">La colonne doit constituer la clé primaire d'au moins une des tables.</span><span class="sxs-lookup"><span data-stu-id="c1f82-108">The column must be a primary key in at least one of the tables.</span></span> <span data-ttu-id="c1f82-109">Par exemple, si vous ajoutez les tables `employee` et `jobs` , si la colonne `job_id` est la clé primaire de la table `jobs` et enfin si chaque table possède une colonne appelée `job_id` comportant le même type de données, le Concepteur de requêtes et de vues joint automatiquement les tables.</span><span class="sxs-lookup"><span data-stu-id="c1f82-109">For example, if you add `employee` and `jobs` tables, if the `job_id` column is the primary key in the `jobs` table, and if each table has a column called `job_id` with the same data type, the Query and View Designer will automatically join the tables.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1f82-110">Le Concepteur de requêtes et de vues ne crée qu'une seule jointure basée sur les colonnes présentant un nom et un type de données identiques.</span><span class="sxs-lookup"><span data-stu-id="c1f82-110">The Query and View Designer will create only one join based on columns with the same name and data type.</span></span> <span data-ttu-id="c1f82-111">S'il existe plusieurs possibilités de jointure, le Concepteur de requêtes et de vues s'arrête après avoir créé une jointure fondée sur le premier jeu de colonnes correspondantes qu'il trouve.</span><span class="sxs-lookup"><span data-stu-id="c1f82-111">If more than one join is possible, the Query and View Designer stops after creating a join based on the first set of matching columns that it finds.</span></span>  
  
-   <span data-ttu-id="c1f82-112">Le Concepteur de requêtes et de vues détecte qu'une condition de recherche (une clause WHERE) constitue en fait une condition de jointure.</span><span class="sxs-lookup"><span data-stu-id="c1f82-112">The Query and View Designer detects that a search condition (a WHERE clause) is actually a join condition.</span></span> <span data-ttu-id="c1f82-113">Par exemple, vous pouvez ajouter les tables `employee` et `jobs`, puis créer une condition de recherche qui cherche la même valeur dans la colonne `job_id` des deux tables.</span><span class="sxs-lookup"><span data-stu-id="c1f82-113">For example, you might add the tables `employee` and `jobs`, then create a search condition that searches for the same value in the `job_id` column of both tables.</span></span> <span data-ttu-id="c1f82-114">Dans ce cas, le Concepteur de requêtes et de vues détermine que la condition de recherche donne lieu à une jointure et crée ensuite une condition de jointure basée sur la condition de recherche.</span><span class="sxs-lookup"><span data-stu-id="c1f82-114">When you do, the Query and View Designer detects that the search condition results in a join, and then creates a join condition based on the search condition.</span></span>  
  
 <span data-ttu-id="c1f82-115">Si le Concepteur de requêtes et de vues a créé une jointure qui n'est pas adaptée à votre requête, vous pouvez modifier cette jointure ou la supprimer.</span><span class="sxs-lookup"><span data-stu-id="c1f82-115">If the Query and View Designer has created a join that is not suitable to your query, you can modify the join or remove it.</span></span> <span data-ttu-id="c1f82-116">Pour plus d’informations, consultez [Modifier des opérateurs de jointure &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) et [Supprimer des jointures &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c1f82-116">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) and [Remove Joins &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="c1f82-117">Si le Concepteur de requêtes et de vues ne joint pas automatiquement les tables dans votre requête, vous pouvez créer vous-même une jointure.</span><span class="sxs-lookup"><span data-stu-id="c1f82-117">If the Query and View Designer does not automatically join the tables in your query, you can create a join yourself.</span></span> <span data-ttu-id="c1f82-118">Pour plus d’informations, consultez [Joindre manuellement des tables &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c1f82-118">For details, see [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f82-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1f82-119">See Also</span></span>  
 <span data-ttu-id="c1f82-120">[Comment le concepteur de requêtes et de vues représente des jointures &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c1f82-120">[How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span></span>  
 <span data-ttu-id="c1f82-121">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c1f82-121">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="c1f82-122">Interroger avec des jointures &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c1f82-122">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
