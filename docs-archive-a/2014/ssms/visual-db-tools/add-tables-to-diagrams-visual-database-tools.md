---
title: Ajouter des tables à des schémas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
ms.assetid: 5440fdf7-ac04-4325-9f32-181f4cd402e5
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe5c1274ac390f4834bd8ac1088258061fc0406d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605885"
---
# <a name="add-tables-to-diagrams-visual-database-tools"></a><span data-ttu-id="c53c8-102">Ajouter des tables à des schémas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c53c8-102">Add Tables to Diagrams (Visual Database Tools)</span></span>
  <span data-ttu-id="c53c8-103">Vous pouvez ajouter une table à votre diagramme de base de données, afin de modifier sa structure ou de la mettre en relation avec d’autres tables du diagramme.</span><span class="sxs-lookup"><span data-stu-id="c53c8-103">You can add a table to your database diagram to edit its structure or relate it to other tables in your diagram.</span></span> <span data-ttu-id="c53c8-104">Vous pouvez soit ajouter des tables de base de données existantes à un schéma, soit insérer une nouvelle table qui n'a pas encore été définie dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c53c8-104">You can either add existing database tables to a diagram or insert a new table that has not yet been defined in the database.</span></span>  
  
### <a name="to-insert-a-new-table-into-a-diagram"></a><span data-ttu-id="c53c8-105">Pour insérer une nouvelle table dans un schéma</span><span class="sxs-lookup"><span data-stu-id="c53c8-105">To insert a new table into a diagram</span></span>  
  
1.  <span data-ttu-id="c53c8-106">Vérifiez que vous êtes connecté à la base de données dans laquelle vous voulez créer la table.</span><span class="sxs-lookup"><span data-stu-id="c53c8-106">Make sure you are connected to the database in which you want to create the table.</span></span>  
  
     <span data-ttu-id="c53c8-107">Pour créer une table dans votre schéma actuel, cliquez sur le bouton **Nouvelle table** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="c53c8-107">To create a table in your current diagram, click the **New Table** button on the toolbar.</span></span>  
  
     <span data-ttu-id="c53c8-108">-ou-</span><span class="sxs-lookup"><span data-stu-id="c53c8-108">-or-</span></span>  
  
     <span data-ttu-id="c53c8-109">Cliquez avec le bouton droit dans le schéma et, dans le menu contextuel, cliquez sur **Nouvelle table**.</span><span class="sxs-lookup"><span data-stu-id="c53c8-109">Right-click in the diagram and select **New Table**.</span></span>  
  
2.  <span data-ttu-id="c53c8-110">Dans la boîte de dialogue **Choisir un nom** , modifiez ou acceptez le nom de table assigné par le système, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c53c8-110">Modify or accept the system-assigned table name, in the **Choose Name** dialog box, and then choose **OK**.</span></span>  
  
     <span data-ttu-id="c53c8-111">Une nouvelle table apparaît dans le schéma en mode d'affichage Standard.</span><span class="sxs-lookup"><span data-stu-id="c53c8-111">A new table appears in the diagram in Standard view.</span></span>  
  
3.  <span data-ttu-id="c53c8-112">Dans la première cellule de la nouvelle table, tapez un nom de colonne.</span><span class="sxs-lookup"><span data-stu-id="c53c8-112">In the first cell of the new table, type a column name.</span></span> <span data-ttu-id="c53c8-113">Ensuite, appuyez sur la touche TAB pour passer à la cellule suivante.</span><span class="sxs-lookup"><span data-stu-id="c53c8-113">Then press the TAB key to move to the next cell.</span></span>  
  
4.  <span data-ttu-id="c53c8-114">Sous **Type de données**, sélectionnez un type de données pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="c53c8-114">Under **Data Type**, select a data type for the column.</span></span> <span data-ttu-id="c53c8-115">Chaque colonne doit avoir un nom et un type de données.</span><span class="sxs-lookup"><span data-stu-id="c53c8-115">Each column must have a name and data type.</span></span>  
  
     <span data-ttu-id="c53c8-116">Vous pouvez définir les autres propriétés des colonnes dans le Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="c53c8-116">You can set the column's other properties in Table Designer.</span></span>  
  
5.  <span data-ttu-id="c53c8-117">Répétez les étapes 3 et 4 pour chaque colonne que vous souhaitez ajouter à la table.</span><span class="sxs-lookup"><span data-stu-id="c53c8-117">Repeat steps 3 and 4 for each column you want to add to the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c53c8-118">Lorsque vous enregistrez votre diagramme de base de données, la nouvelle table est ajoutée à votre base de données.</span><span class="sxs-lookup"><span data-stu-id="c53c8-118">When you save your database diagram, the new table will be added to your database.</span></span>  
  
### <a name="to-add-an-existing-table-to-a-diagram"></a><span data-ttu-id="c53c8-119">Pour ajouter une table existante à un schéma</span><span class="sxs-lookup"><span data-stu-id="c53c8-119">To add an existing table to a diagram</span></span>  
  
1.  <span data-ttu-id="c53c8-120">Vérifiez que vous êtes connecté à la base de données dont vous voulez modifier des tables.</span><span class="sxs-lookup"><span data-stu-id="c53c8-120">Make sure you are connected to the database whose tables you want to edit.</span></span>  
  
2.  <span data-ttu-id="c53c8-121">Sélectionnez une table dans le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="c53c8-121">Select a table in the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="c53c8-122">Faites glisser la table jusqu’à votre diagramme de base de données.</span><span class="sxs-lookup"><span data-stu-id="c53c8-122">Drag the table into your database diagram.</span></span>  
  
4.  <span data-ttu-id="c53c8-123">Relâchez le bouton de la souris.</span><span class="sxs-lookup"><span data-stu-id="c53c8-123">Release the mouse button.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c53c8-124">S'il existe des relations entre la table sélectionnée et d'autres tables de votre schéma, les lignes de relation correspondantes sont dessinées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="c53c8-124">If relationships exist between the selected table and other tables in your diagram, relationship lines are automatically drawn.</span></span>  
  
### <a name="to-add-related-tables-to-a-diagram"></a><span data-ttu-id="c53c8-125">Pour ajouter des tables connexes à un schéma</span><span class="sxs-lookup"><span data-stu-id="c53c8-125">To add related tables to a diagram</span></span>  
  
1.  <span data-ttu-id="c53c8-126">Sélectionnez une ou plusieurs tables associées à des contraintes de clé étrangère dans le diagramme de base de données.</span><span class="sxs-lookup"><span data-stu-id="c53c8-126">Select one or more tables with foreign key constraints in the database diagram.</span></span>  
  
2.  <span data-ttu-id="c53c8-127">Cliquez avec le bouton droit sur l’une des tables sélectionnées et, dans le menu contextuel, cliquez sur **Ajouter les tables connexes**.</span><span class="sxs-lookup"><span data-stu-id="c53c8-127">Right-click any of the selected tables and choose **Add Related Tables**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c53c8-128">Toutes les tables référencées par une contrainte de clé étrangère depuis les tables sélectionnées et toutes les tables qui référencent les tables sélectionnées avec une contrainte de clé étrangère sont ajoutées au schéma.</span><span class="sxs-lookup"><span data-stu-id="c53c8-128">Both those tables referenced by a foreign key constraint from the selected table(s) and those referencing the selected table(s) with a foreign key constraint are added to the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53c8-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c53c8-129">See Also</span></span>  
 <span data-ttu-id="c53c8-130">[Utiliser des schémas de base de données &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c53c8-130">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="c53c8-131">Utiliser des tables dans les diagrammes de base de données &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c53c8-131">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
