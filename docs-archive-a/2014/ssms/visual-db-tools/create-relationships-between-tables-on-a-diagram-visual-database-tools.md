---
title: Créer des relations entre des tables sur un diagramme (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- diagrams [SQL Server], designing
ms.assetid: 28e9630c-dff4-46cc-bb0e-fe77998b6ac2
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7d627a37f84dcb66b2129bb9c7dbc5890ccd46c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708039"
---
# <a name="create-relationships-between-tables-on-a-diagram-visual-database-tools"></a><span data-ttu-id="bab36-102">Créer des relations entre des tables sur un diagramme (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="bab36-102">Create Relationships Between Tables on a Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="bab36-103">Vous pouvez créer des relations entre des colonnes dans différentes tables dans le Concepteur de diagrammes en faisant glisser les colonnes entre les tables.</span><span class="sxs-lookup"><span data-stu-id="bab36-103">You can create relationships between columns in different tables in the Diagram Designer by dragging columns between tables.</span></span>  
  
### <a name="to-create-a-relationship-graphically"></a><span data-ttu-id="bab36-104">Pour créer une relation sous forme de graphique</span><span class="sxs-lookup"><span data-stu-id="bab36-104">To create a relationship graphically</span></span>  
  
1.  <span data-ttu-id="bab36-105">Dans le Concepteur de diagrammes, cliquez sur le sélectionneur de ligne d'une ou de plusieurs colonnes de base de données que vous souhaitez associer à une colonne dans une autre table.</span><span class="sxs-lookup"><span data-stu-id="bab36-105">In Database Designer, click the row selector for one or more database columns that you want to relate to a column in another table.</span></span>  
  
2.  <span data-ttu-id="bab36-106">Faites glisser la ou les colonne(s) sélectionnée(s) vers la table associée.</span><span class="sxs-lookup"><span data-stu-id="bab36-106">Drag the selected column(s) to the related table.</span></span>  
  
3.  <span data-ttu-id="bab36-107">Deux boîtes de dialogue s’ouvre : **Relation de clé étrangère** et **Tables et colonnes**, cette dernière apparaissant au premier plan.</span><span class="sxs-lookup"><span data-stu-id="bab36-107">Two dialog boxes appear: **Foreign Key Relationship** and **Tables and Columns**, with the latter appearing in the foreground.</span></span>  
  
4.  <span data-ttu-id="bab36-108">Le**nom de relation** a une nom fourni par le système au format FK_*localtable*_*foreigntable*.</span><span class="sxs-lookup"><span data-stu-id="bab36-108">**Relationship name** has a system-provided name in the format FK_*localtable*_*foreigntable*.</span></span> <span data-ttu-id="bab36-109">Vous pouvez modifier cette valeur.</span><span class="sxs-lookup"><span data-stu-id="bab36-109">You may change this value.</span></span>  
  
5.  <span data-ttu-id="bab36-110">Vérifiez que la **table de clé primaire** spécifie la bonne table.</span><span class="sxs-lookup"><span data-stu-id="bab36-110">Verify that **Primary key table** specifies the correct table.</span></span>  
  
6.  <span data-ttu-id="bab36-111">La grille affiche les colonnes locales et leurs colonnes étrangères correspondantes.</span><span class="sxs-lookup"><span data-stu-id="bab36-111">The grid lists the local columns and their matching foreign columns.</span></span> <span data-ttu-id="bab36-112">Vous pouvez ajouter ou supprimer des colonnes de table ou modifier les mappages.</span><span class="sxs-lookup"><span data-stu-id="bab36-112">You can add or remove table columns or change mappings.</span></span>  
  
7.  <span data-ttu-id="bab36-113">Choisissez **OK**.</span><span class="sxs-lookup"><span data-stu-id="bab36-113">Choose **OK**.</span></span>  
  
     <span data-ttu-id="bab36-114">La boîte de dialogue **Relation de clé étrangère** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="bab36-114">The **Foreign Key Relationship** dialog box appears.</span></span> <span data-ttu-id="bab36-115">La**Relation sélectionnée** affiche la relation créée.</span><span class="sxs-lookup"><span data-stu-id="bab36-115">**Selected Relationship** shows the relationship you have created.</span></span>  
  
8.  <span data-ttu-id="bab36-116">Modifiez les propriétés de la relation dans la grille.</span><span class="sxs-lookup"><span data-stu-id="bab36-116">Change properties for the relationship in the grid.</span></span>  
  
9. <span data-ttu-id="bab36-117">Choisissez **OK** pour créer la relation.</span><span class="sxs-lookup"><span data-stu-id="bab36-117">Choose **OK** to create the relationship.</span></span>  
  
     <span data-ttu-id="bab36-118">Le Concepteur de base de données affiche une relation entre les colonnes que vous avez choisies.</span><span class="sxs-lookup"><span data-stu-id="bab36-118">Database Designer shows a relationship between the columns you chose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab36-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bab36-119">See Also</span></span>  
 <span data-ttu-id="bab36-120">[Tables et colonnes, boîte de dialogue &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bab36-120">[Tables and Columns Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="bab36-121">[Contraintes uniques et contraintes de validation](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="bab36-121">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="bab36-122">Utiliser des tables dans les diagrammes de base de données &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="bab36-122">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
