---
title: Mapper des relations plusieurs-à-plusieurs (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], many-to-many
- junction tables [SQL Server]
- many-to-many relationships [SQL Server]
- mapping many-to-many relationships [SQL Server]
- database diagrams [SQL Server], relationships
ms.assetid: 2977cf92-98b5-48b2-b0fd-8fbc7040f2b4
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbcbdbdf8d8371baa2a817e43b831535723be7ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613754"
---
# <a name="map-many-to-many-relationships-visual-database-tools"></a><span data-ttu-id="07ed3-102">Mapper des relations plusieurs-à-plusieurs (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="07ed3-102">Map Many-to-Many Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="07ed3-103">Les relations plusieurs-à-plusieurs vous permettent de mettre chaque ligne d'une table en relation avec plusieurs lignes d'une autre table, et vice versa.</span><span class="sxs-lookup"><span data-stu-id="07ed3-103">Many-to-many relationships let you relate each row in one table to many rows in another table, and vice versa.</span></span> <span data-ttu-id="07ed3-104">Par exemple, vous pouvez créer une relation plusieurs-à-plusieurs entre la table `authors` et la table `titles` pour établir une correspondance entre chaque auteur et tous ses livres, entre chaque livre et tous ses auteurs.</span><span class="sxs-lookup"><span data-stu-id="07ed3-104">For example, you could create a many-to-many relationship between the `authors` table and the `titles` table to match each author to all of his or her books and to match each book to all of its authors.</span></span> <span data-ttu-id="07ed3-105">Si vous choisissiez de créer une relation un-à-plusieurs à partir de l'une ou l'autre table, chaque livre ne pourrait renvoyer qu'à un seul auteur ou chaque auteur qu'à un seul livre.</span><span class="sxs-lookup"><span data-stu-id="07ed3-105">Creating a one-to-many relationship from either table would incorrectly indicate that every book can have only one author, or that every author can write only one book.</span></span>  
  
 <span data-ttu-id="07ed3-106">Les relations plusieurs-à-plusieurs entre les tables sont enregistrées dans les bases de données au moyen de tables de jonctions.</span><span class="sxs-lookup"><span data-stu-id="07ed3-106">Many-to-many relationships between tables are accommodated in databases by means of junction tables.</span></span> <span data-ttu-id="07ed3-107">Une table de jonction contient les colonnes clés primaire des deux tables à mettre en relation.</span><span class="sxs-lookup"><span data-stu-id="07ed3-107">A junction table contains the primary key columns of the two tables you want to relate.</span></span> <span data-ttu-id="07ed3-108">Vous créez ensuite une relation entre les colonnes clés primaire de chacune des deux tables et les colonnes correspondantes dans la table de jonction.</span><span class="sxs-lookup"><span data-stu-id="07ed3-108">You then create a relationship from the primary key columns of each of those two tables to the matching columns in the junction table.</span></span> <span data-ttu-id="07ed3-109">Dans la base de données pubs, la table `titleauthor` est une table de jonction.</span><span class="sxs-lookup"><span data-stu-id="07ed3-109">In the pubs database, the `titleauthor` table is a junction table.</span></span>  
  
### <a name="to-create-a-many-to-many-relationship-between-tables"></a><span data-ttu-id="07ed3-110">Pour créer une relation plusieurs-à-plusieurs entre des tables</span><span class="sxs-lookup"><span data-stu-id="07ed3-110">To create a many-to-many relationship between tables</span></span>  
  
1.  <span data-ttu-id="07ed3-111">Dans votre diagramme de base de données, ajoutez les tables entre lesquelles vous voulez créer une relation plusieurs-à-plusieurs.</span><span class="sxs-lookup"><span data-stu-id="07ed3-111">In your database diagram, add the tables that you want to create a many-to-many relationship between.</span></span>  
  
2.  <span data-ttu-id="07ed3-112">Créez une troisième table : cliquez avec le bouton droit sur le schéma, puis, dans le menu contextuel, cliquez sur **Nouvelle table** .</span><span class="sxs-lookup"><span data-stu-id="07ed3-112">Create a third table by right-clicking the diagram and choosing **New Table** from the shortcut menu.</span></span> <span data-ttu-id="07ed3-113">Cette table sera la table de jonction.</span><span class="sxs-lookup"><span data-stu-id="07ed3-113">This will become the junction table.</span></span>  
  
3.  <span data-ttu-id="07ed3-114">Dans la boîte de dialogue **Choisir un nom** , changez le nom de la table assigné par le système.</span><span class="sxs-lookup"><span data-stu-id="07ed3-114">In the **Choose Name** dialog box, change the system-assigned table name.</span></span> <span data-ttu-id="07ed3-115">Par exemple, la table de jonction entre les tables `titles` et `authors` s'intitule à présent `titleauthors`.</span><span class="sxs-lookup"><span data-stu-id="07ed3-115">For example, the junction table between the `titles` table and the `authors` table is now named `titleauthors`.</span></span>  
  
4.  <span data-ttu-id="07ed3-116">Copiez les colonnes clés primaire de chacune des deux autres tables vers la table de jonction.</span><span class="sxs-lookup"><span data-stu-id="07ed3-116">Copy the primary key columns from each of the other two tables to the junction table.</span></span> <span data-ttu-id="07ed3-117">Vous pouvez ajouter d'autres colonnes à cette table comme à n'importe quelle autre table.</span><span class="sxs-lookup"><span data-stu-id="07ed3-117">You can add other columns to this table, just as you can to any other table.</span></span>  
  
5.  <span data-ttu-id="07ed3-118">Dans la table de jonction, configurez la clé primaire de façon à inclure toutes les colonnes clés primaire des deux autres tables.</span><span class="sxs-lookup"><span data-stu-id="07ed3-118">In the junction table, set the primary key to include all the primary key columns from the other two tables.</span></span> <span data-ttu-id="07ed3-119">Pour plus d’informations, consultez [créer des clés primaires](../../relational-databases/tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="07ed3-119">For details, see [Create Primary Keys](../../relational-databases/tables/create-primary-keys.md).</span></span>  
  
6.  <span data-ttu-id="07ed3-120">Définissez une relation un-à-plusieurs entre chacune des deux tables primaires et la table de jonction.</span><span class="sxs-lookup"><span data-stu-id="07ed3-120">Define a one-to-many relationship between each of the two primary tables and the junction table.</span></span> <span data-ttu-id="07ed3-121">La table de jonction doit se trouver du côté « plusieurs » des deux relations créées.</span><span class="sxs-lookup"><span data-stu-id="07ed3-121">The junction table should be at the "many" side of both of the relationships you create.</span></span> <span data-ttu-id="07ed3-122">Pour plus d’informations, consultez [créer des relations de clé étrangère](../../relational-databases/tables/create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="07ed3-122">For details, see [Create Foreign Key Relationships](../../relational-databases/tables/create-foreign-key-relationships.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="07ed3-123">Lorsque vous créez une table de jonction dans un diagramme de base de données, les données des tables connexes ne sont pas insérées dans la table de jonction.</span><span class="sxs-lookup"><span data-stu-id="07ed3-123">The creation of a junction table in a database diagram does not insert data from the related tables into the junction table.</span></span> <span data-ttu-id="07ed3-124">Pour plus d’informations sur l’insertion de données dans une table, consultez [Créer des requêtes Insert Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="07ed3-124">For information about inserting data into a table, see [Create Insert Results Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ed3-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07ed3-125">See Also</span></span>  
 [<span data-ttu-id="07ed3-126">Utiliser des diagrammes de base de données &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="07ed3-126">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](work-with-database-diagrams-visual-database-tools.md)  
  
  
