---
title: Établir des relations réflexives (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- drawing reflexive relationships
- reflexive relationships
- database diagrams [SQL Server], relationships
ms.assetid: e218363f-faec-46d5-9904-a537fbcc994d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e5056b1a5d0d884edbc4fc818fe8c7ef5cc8ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611450"
---
# <a name="draw-reflexive-relationships-visual-database-tools"></a><span data-ttu-id="c7a4a-102">Établir des relations réflexives (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c7a4a-102">Draw Reflexive Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="c7a4a-103">Vous pouvez créer une relation réflexive pour relier une ou plusieurs colonnes d'une table à une ou plusieurs autres colonnes de la même table.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-103">You create a reflexive relationship to link a column or columns in a table with another column or columns in the same table.</span></span> <span data-ttu-id="c7a4a-104">Par exemple, supposons que la table `employee` possède une colonne `emp_id` et une colonne `mgr_id` .</span><span class="sxs-lookup"><span data-stu-id="c7a4a-104">For example, suppose the `employee` table has an `emp_id` column and a `mgr_id` column.</span></span> <span data-ttu-id="c7a4a-105">Dans la mesure où chaque directeur est également un employé, vous mettrez ces deux colonnes en relation en dessinant une ligne de relation de la table vers elle-même.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-105">Because each manager is also an employee, you relate these two columns by drawing a relationship line from the table to itself.</span></span> <span data-ttu-id="c7a4a-106">Cette relation garantira que chaque ID de directeur ajouté à la table correspond à un ID d'employé existant.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-106">This relationship ensures each manager ID that is added to the table matches an existing employee ID.</span></span>  
  
 <span data-ttu-id="c7a4a-107">Avant de créer une relation, vous devez définir une clé primaire ou une contrainte unique pour votre table.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-107">Before you create a relationship, you must first define a primary key or unique constraint for your table.</span></span> <span data-ttu-id="c7a4a-108">Vous mettez ensuite la colonne de clé primaire en relation avec une colonne correspondante.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-108">You then relate the primary key column to a matching column.</span></span> <span data-ttu-id="c7a4a-109">À la création de la relation, la colonne correspondante devient une clé étrangère de la table.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-109">Once you create the relationship, the matching column becomes a foreign key of the table.</span></span>  
  
### <a name="to-draw-a-reflexive-relationship"></a><span data-ttu-id="c7a4a-110">Pour dessiner une relation réflexive</span><span class="sxs-lookup"><span data-stu-id="c7a4a-110">To draw a reflexive relationship</span></span>  
  
1.  <span data-ttu-id="c7a4a-111">Dans votre diagramme de base de données, cliquez sur le sélecteur de ligne correspondant à la colonne que vous voulez mettre en relation avec une autre colonne et faites glisser le pointeur à l’extérieur de la table jusqu’à ce qu’une ligne apparaisse.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-111">In your database diagram, click the row selector for the database column that you want to relate to another column and drag the pointer outside the table until a line appears.</span></span>  
  
2.  <span data-ttu-id="c7a4a-112">Refaites glisser la ligne vers la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-112">Drag the line back to the selected table.</span></span>  
  
3.  <span data-ttu-id="c7a4a-113">Relâchez le bouton de la souris.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-113">Release the mouse button.</span></span> <span data-ttu-id="c7a4a-114">La boîte de dialogue **Tables et colonnes** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-114">The **Tables and Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="c7a4a-115">Sélectionnez la colonne de clé étrangère et la table et colonne de clé primaire avec lesquelles vous souhaitez créer une relation.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-115">Select the foreign key column and the primary key table and column with which you want form a relationship.</span></span>  
  
5.  <span data-ttu-id="c7a4a-116">Cliquez deux fois sur **OK** pour créer la relation.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-116">Choose **OK** twice to create the relationship.</span></span>  
  
 <span data-ttu-id="c7a4a-117">Lorsque vous exécutez des requêtes sur une table, vous pouvez utiliser une relation réflexive pour créer une jointure réflexive.</span><span class="sxs-lookup"><span data-stu-id="c7a4a-117">When you run queries against a table, you can use a reflexive relationship to create a self-join.</span></span> <span data-ttu-id="c7a4a-118">Pour plus d’informations sur l’interrogation de tables avec des jointures, consultez [Interroger avec des jointures &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7a4a-118">For information about querying tables with joins, see [Query with Joins &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a4a-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7a4a-119">See Also</span></span>  
 [<span data-ttu-id="c7a4a-120">Interroger avec des jointures &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c7a4a-120">Query with Joins &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
