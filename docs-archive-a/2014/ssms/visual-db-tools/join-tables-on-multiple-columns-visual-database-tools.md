---
title: Joindre des tables sur plusieurs colonnes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiple column joins
- joins [SQL Server], multiple columns
ms.assetid: 56a158bc-a42a-4b78-baad-4721d2d22cd3
author: stevestein
ms.author: sstein
ms.openlocfilehash: dda52fe27b2034242c8cbf458dd010240c792146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605872"
---
# <a name="join-tables-on-multiple-columns-visual-database-tools"></a><span data-ttu-id="fcad3-102">Joindre des tables sur plusieurs colonnes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fcad3-102">Join Tables on Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="fcad3-103">Il est possible de joindre les tables sur la base de plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="fcad3-103">You can join tables with multiple columns.</span></span> <span data-ttu-id="fcad3-104">En d'autres termes, vous pouvez créer une requête qui fait correspondre les lignes de deux tables uniquement si elles satisfont à plusieurs conditions.</span><span class="sxs-lookup"><span data-stu-id="fcad3-104">That is, you can create a query that matches rows from the two tables only if they satisfy multiple conditions.</span></span> <span data-ttu-id="fcad3-105">Si la base de données contient une relation qui fait correspondre plusieurs colonnes clés étrangères d'une table à une clé primaire multicolonne de l'autre table, vous pouvez utiliser cette relation pour créer une jointure multicolonne.</span><span class="sxs-lookup"><span data-stu-id="fcad3-105">If the database contains a relationship matching multiple foreign-key columns in one table to a multicolumn primary key in the other table, you can use this relationship to create a multicolumn join.</span></span> <span data-ttu-id="fcad3-106">Pour plus d’informations, consultez [Joindre automatiquement des tables &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fcad3-106">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="fcad3-107">Même si la base de données ne comprend aucune relation de clé étrangère multicolonne, il est toujours possible de créer la jointure manuellement.</span><span class="sxs-lookup"><span data-stu-id="fcad3-107">Even if the database contains no multi-column foreign-key relationship, you can create the join manually.</span></span>  
  
### <a name="to-manually-create-a-multicolumn-join"></a><span data-ttu-id="fcad3-108">Pour créer manuellement une jointure multicolonne</span><span class="sxs-lookup"><span data-stu-id="fcad3-108">To manually create a multicolumn join</span></span>  
  
1.  <span data-ttu-id="fcad3-109">Ajoutez les tables à joindre dans le [volet Schéma](diagram-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="fcad3-109">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the tables you want to join.</span></span>  
  
2.  <span data-ttu-id="fcad3-110">Faites glisser le nom de la colonne de jointure de la fenêtre de la première table jusqu'à la colonne liée de la fenêtre de la seconde table.</span><span class="sxs-lookup"><span data-stu-id="fcad3-110">Drag the name of the first join column in the first table window and drop it onto the related column in the second table window.</span></span> <span data-ttu-id="fcad3-111">Une jointure ne peut être basée sur des colonnes de type text, ntext ou image.</span><span class="sxs-lookup"><span data-stu-id="fcad3-111">You cannot base a join on text, ntext, or image columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcad3-112">En général, les colonnes de jointure doivent afficher des types de données identiques (ou compatibles).</span><span class="sxs-lookup"><span data-stu-id="fcad3-112">In general, the join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="fcad3-113">Par exemple, si la colonne de jointure de la première table est une date, il faut la lier à une colonne de dates de la seconde table.</span><span class="sxs-lookup"><span data-stu-id="fcad3-113">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="fcad3-114">En revanche, si la première colonne de jointure est un entier, la colonne de jointure liée doit également comporter des données de type entier mais la longueur peut varier.</span><span class="sxs-lookup"><span data-stu-id="fcad3-114">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="fcad3-115">Toutefois, il peut arriver que les conversions de types de données implicites joignent des colonnes apparemment incompatibles.</span><span class="sxs-lookup"><span data-stu-id="fcad3-115">However, there may be cases where implicit data type conversions can join seemingly incompatible columns will work.</span></span>  
    >   
    >  <span data-ttu-id="fcad3-116">Le [Concepteur de requêtes et de vues](query-and-view-designer-tools-visual-database-tools.md) ne vérifie pas les types de données des colonnes utilisées pour créer une jointure mais, quand vous exécutez la requête, la base de données affiche une erreur si les types de données sont incompatibles.</span><span class="sxs-lookup"><span data-stu-id="fcad3-116">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="fcad3-117">Faites glisser le nom de la seconde colonne de jointure de la fenêtre de la première table jusqu'à la colonne associée dans la fenêtre de la seconde table.</span><span class="sxs-lookup"><span data-stu-id="fcad3-117">Drag the name of the second join column in the first table window and drop it onto the related column in the second table window.</span></span>  
  
4.  <span data-ttu-id="fcad3-118">Répétez l'étape 3 pour chaque nouvelle paire de colonnes de jointure dans les deux tables.</span><span class="sxs-lookup"><span data-stu-id="fcad3-118">Repeat step 3 for each additional pair of join columns in the two tables.</span></span>  
  
5.  <span data-ttu-id="fcad3-119">Exécute la requête.</span><span class="sxs-lookup"><span data-stu-id="fcad3-119">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcad3-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcad3-120">See Also</span></span>  
 [<span data-ttu-id="fcad3-121">Interroger avec des jointures &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fcad3-121">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
