---
title: Joindre manuellement des tables (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- manual joins [SQL Server]
- joins [SQL Server], manual
- joins [SQL Server], creating
ms.assetid: 9c785356-646b-4c87-82d4-25efd6051d9d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83f7615be3f5f18164dd3ca0f62ef6cbd9167be3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695123"
---
# <a name="join-tables-manually-visual-database-tools"></a><span data-ttu-id="94db7-102">Joindre manuellement des tables (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="94db7-102">Join Tables Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="94db7-103">Quand vous ajoutez plusieurs tables à une requête, le [Concepteur de requêtes et de vues](visual-database-tools.md) tente de les joindre en fonction de données communes ou d’informations enregistrées dans la base de données sur d’éventuelles liaisons entre les tables.</span><span class="sxs-lookup"><span data-stu-id="94db7-103">When you add two (or more) tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to join them based on common data or on information stored in the database about how tables are related.</span></span> <span data-ttu-id="94db7-104">Pour plus d’informations, consultez [Joindre automatiquement des tables &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94db7-104">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span></span> <span data-ttu-id="94db7-105">Néanmoins, si le Concepteur de requêtes et de vues n'a pas joint automatiquement les tables ou si vous voulez créer d'autres conditions de jointure entre les tables, vous pouvez joindre les tables manuellement.</span><span class="sxs-lookup"><span data-stu-id="94db7-105">However, if the Query and View Designer has not joined the tables automatically, or if you want to create additional join conditions between tables, you can join tables manually.</span></span>  
  
 <span data-ttu-id="94db7-106">Vous pouvez créer des jointures basées sur des comparaisons entre deux colonnes, quelles qu'elles soient et non uniquement entre des colonnes qui contiennent les mêmes informations.</span><span class="sxs-lookup"><span data-stu-id="94db7-106">You can create joins based on comparisons between any two columns, not just columns that contain the same information.</span></span> <span data-ttu-id="94db7-107">Par exemple, si votre base de données contient deux tables, `titles` et `roysched`, vous pouvez comparer des valeurs de la colonne `ytd_sales` de la table `titles` à celles des colonnes `lorange` et `hirange` de la table `roysched` .</span><span class="sxs-lookup"><span data-stu-id="94db7-107">For example, if your database contains two tables, `titles` and `roysched`, you can compare values in the `ytd_sales` column of the `titles` table against the `lorange` and `hirange` columns in the `roysched` table.</span></span> <span data-ttu-id="94db7-108">La création d'une telle jointure vous permet de trouver des titres dont les ventes de l'année à ce jour figurent entre les plages inférieure et supérieure des paiements de droits d'auteur.</span><span class="sxs-lookup"><span data-stu-id="94db7-108">Creating this join would allow you to find titles for which the year-to-date sales falls between the low and high ranges for the royalty payments.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="94db7-109">Les jointures sont réalisées plus rapidement si les colonnes de la condition de jointure ont été indexées.</span><span class="sxs-lookup"><span data-stu-id="94db7-109">Joins work fastest if the columns in the join condition have been indexed.</span></span> <span data-ttu-id="94db7-110">Dans certains cas, une jointure appliquée à des colonnes non indexées peut se traduire par une exécution très lente de la requête.</span><span class="sxs-lookup"><span data-stu-id="94db7-110">In some cases, joining on unindexed columns can result in a slow query.</span></span>  
  
### <a name="to-manually-join-tables-or-table-structured-objects"></a><span data-ttu-id="94db7-111">Pour joindre manuellement des tables ou des objets de type table</span><span class="sxs-lookup"><span data-stu-id="94db7-111">To manually join tables or table-structured objects</span></span>  
  
1.  <span data-ttu-id="94db7-112">Ajoutez les objets à joindre au [volet Schéma](diagram-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="94db7-112">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the objects you want to join.</span></span>  
  
2.  <span data-ttu-id="94db7-113">Faites glisser le nom de la colonne de jointure de la première table ou objet de type table jusqu'à la colonne liée de la seconde table ou objet de type table.</span><span class="sxs-lookup"><span data-stu-id="94db7-113">Drag the name of the join column in the first table or table-structured object and drop it onto the related column in the second table or table-structured object.</span></span> <span data-ttu-id="94db7-114">Une jointure ne peut pas être basée sur des colonnes de type `text`, `ntext` ou i`mage`.</span><span class="sxs-lookup"><span data-stu-id="94db7-114">You cannot base a join on `text`, `ntext`, or i`mage` columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94db7-115">Les colonnes de jointure doivent afficher des types de données identiques (ou compatibles).</span><span class="sxs-lookup"><span data-stu-id="94db7-115">The join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="94db7-116">Par exemple, si la colonne de jointure de la première table est une date, il faut la lier à une colonne de dates de la seconde table.</span><span class="sxs-lookup"><span data-stu-id="94db7-116">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="94db7-117">En revanche, si la première colonne de jointure est un entier, la colonne de jointure liée doit également comporter des données de type entier mais la longueur peut varier.</span><span class="sxs-lookup"><span data-stu-id="94db7-117">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="94db7-118">Le Concepteur de requêtes et de vues ne vérifie pas les types de données des colonnes utilisées pour créer une jointure mais, lorsque vous exécutez la requête, la base de données affiche une erreur si les types de données sont incompatibles.</span><span class="sxs-lookup"><span data-stu-id="94db7-118">The Query and View Designer will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="94db7-119">Le cas échéant, remplacez l'opérateur de jointure qui est, par défaut un signe égal (=).</span><span class="sxs-lookup"><span data-stu-id="94db7-119">If necessary, change the join operator; by default, the operator is an equal sign (=).</span></span> <span data-ttu-id="94db7-120">Pour plus d’informations, consultez [Modifier des opérateurs de jointure &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94db7-120">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="94db7-121">Le Concepteur de requêtes et de vues ajoute une clause INNER JOIN à l’instruction SQL dans le [volet SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94db7-121">The Query and View Designer adds an INNER JOIN clause to the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="94db7-122">Vous pouvez changer ce type de jointure en jointure externe.</span><span class="sxs-lookup"><span data-stu-id="94db7-122">You can change the type to an outer join.</span></span> <span data-ttu-id="94db7-123">Pour plus d’informations, consultez [Créer des jointures externes &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94db7-123">For details see [Create Outer Joins &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94db7-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94db7-124">See Also</span></span>  
 [<span data-ttu-id="94db7-125">Interroger avec des jointures &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="94db7-125">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
